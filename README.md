# re-graph

A graphql client for [re-frame](https://github.com/Day8/re-frame) applications

## Notes

This library behaves like the popular [Apollo client](https://github.com/apollographql/subscriptions-transport-ws)
for graphql and as such is compatible with [lacinia-pedestal](https://github.com/walmartlabs/lacinia-pedestal).

It supports HTTP and WebSockets (required for subscriptions).

## Usage

Add re-graph to your project's dependencies:
[![Clojars Project](https://img.shields.io/clojars/v/re-graph.svg)](https://clojars.org/re-graph)

```clojure
(require [re-graph.core :as re-graph]
         [re-frame.core :as re-frame])

(re-frame/dispatch [::re-graph/init])

(re-frame/reg-event-db
  ::on-thing
  (fn [db [_ payload]]
    ;; do things with payload
    ))

(re-frame/dispatch [::re-graph/subscribe
                    :my-subscription-id
                    "{ things { id } }"
                    {}
                    [::on-thing]])

```

## Development

```clojure
user> (dev)
dev> (start)
;; visit http://localhost:3449/devcards/index.html
dev> (cljs)
cljs.user>
```

[![CircleCI](https://circleci.com/gh/oliyh/re-graph.svg?style=svg)](https://circleci.com/gh/oliyh/re-graph)

## License

Copyright © 2017 oliyh

Distributed under the Eclipse Public License either version 1.0 or (at
your option) any later version.

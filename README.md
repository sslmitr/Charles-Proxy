# Charles Proxy

## Introduction

Charles Proxy is an HTTP and HTTPS debugging proxy that enables developers to inspect, analyze, and modify network traffic between client applications and remote servers. It operates as an intermediary, capturing requests and responses in real time, which makes it a practical tool for diagnosing API issues, testing integrations, and validating client-server communication. By configuring a system or device to route traffic through Charles, engineers gain full visibility into headers, payloads, cookies, and timing data.

A typical workflow involves setting Charles as the system proxy and observing outgoing requests from a browser, mobile application, or backend service. For HTTPS traffic, Charles performs SSL proxying by installing a trusted root certificate, allowing encrypted sessions to be decrypted and inspected. This capability is essential when debugging authentication flows, API contracts, or third-party service interactions.

Charles also supports request modification through breakpoints and rewrite rules. Developers can intercept a request, alter parameters, and forward it to simulate different conditions without changing application code. Response editing allows testing of edge cases such as malformed data or unexpected status codes.

The tool is widely used in web and mobile development, QA processes, and performance analysis. Its structured interface organizes traffic into sessions, making it easier to trace sequences of calls. By providing both high-level summaries and detailed packet-level views, Charles helps identify issues such as latency bottlenecks, incorrect headers, or caching problems in a controlled environment.

## SSL Proxying and Traffic Inspection

SSL proxying is a core feature that allows Charles Proxy to decrypt and inspect HTTPS traffic. By default, encrypted connections are not readable, but Charles resolves this by acting as a trusted intermediary. After installing and trusting the Charles root certificate on the client device, the proxy can transparently intercept secure requests and display their full contents.

To enable SSL proxying, specific hosts or domains must be configured in the SSL Proxying settings. This selective approach avoids unnecessary decryption and reduces overhead. For example, when debugging a REST API hosted at `api.internal.service`, adding this domain ensures only relevant traffic is inspected. Once configured, developers can view request bodies, headers, query parameters, and response payloads, even for secure endpoints.

This functionality is particularly useful when validating authentication mechanisms such as OAuth tokens or session cookies. Engineers can confirm whether headers are correctly formed or if sensitive data is transmitted securely. Additionally, it helps identify issues like incorrect content types or serialization errors in JSON responses.

Charles also provides filtering and search tools to isolate specific requests. For instance, filtering by HTTP method or status code allows quick identification of failing API calls. Combined with timeline views, developers can analyze latency and pinpoint delays introduced by network conditions or server processing. SSL proxying transforms encrypted traffic into actionable insights without modifying application code.

## Request Manipulation and Debugging Workflows

Charles Proxy provides powerful mechanisms for modifying network traffic, enabling controlled testing scenarios without altering the original application. Breakpoints are a primary feature used for this purpose. When a breakpoint is set on a request or response, Charles pauses the transaction, allowing the developer to inspect and edit data before it continues. This is useful for testing how an application behaves with modified parameters, headers, or payloads.

For example, a developer can intercept a POST request, change a JSON field, and forward it to simulate a different user role or input condition. Similarly, response breakpoints allow injection of custom responses, such as forcing an error code or altering returned data to test error handling logic in the client.

Rewrite rules automate this process by applying predefined transformations to matching requests. A rule can redirect traffic from a production endpoint to a staging server, replace specific header values, or modify query parameters dynamically. This is especially valuable in environments where backend changes are restricted or slow to deploy.

Charles also supports throttling to simulate network conditions like high latency or limited bandwidth. By configuring presets such as 3G or custom profiles, developers can observe how applications perform under constrained conditions.

These capabilities enable repeatable debugging workflows, reduce dependency on backend availability, and allow precise control over test scenarios, making Charles an effective tool for validating application resilience and correctness.

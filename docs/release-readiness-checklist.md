# Spring Boot Release Readiness Checklist

Use this before deploying a Spring Boot service to a shared test environment or production.

## Application and configuration

- [ ] Build and automated tests pass from a clean checkout.
- [ ] The application version and release notes are recorded.
- [ ] Environment-specific configuration is externalized.
- [ ] No passwords, tokens, client secrets, or production URLs are committed to source control.
- [ ] Feature flags have safe defaults and an owner.

## Health and observability

- [ ] Actuator health endpoints are enabled and access is protected appropriately.
- [ ] Liveness and readiness checks reflect real dependency needs.
- [ ] Logs include a correlation or trace ID.
- [ ] Dashboards and alerts exist for errors, latency, saturation, and dependency failures.
- [ ] Sensitive request data is excluded from logs.

## Database and integration

- [ ] Database migrations are reviewed, tested, and backward compatible where possible.
- [ ] Connections, timeouts, retries, and circuit-breaker behaviour are explicit.
- [ ] External API contract changes are tested with realistic failure cases.
- [ ] Message consumers can safely handle duplicates and retries.

## Deployment and rollback

- [ ] Deployment steps are written and verified in a lower environment.
- [ ] A rollback path is documented and does not depend on memory.
- [ ] Backward compatibility is checked for clients and in-flight messages.
- [ ] Post-deployment smoke tests and an owner are identified.
- [ ] The team knows the release window and escalation contact.

## After release

- [ ] Confirm service health, key API flows, and error rate.
- [ ] Watch logs and metrics during the agreed observation window.
- [ ] Record release outcome, follow-up work, and any incidents.

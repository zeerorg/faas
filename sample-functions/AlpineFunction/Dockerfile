FROM openfaas/classic-watchdog:0.14.4 as watchdog

FROM alpine:3.9

COPY --from=watchdog /fwatchdog /usr/bin/fwatchdog
RUN chmod +x /usr/bin/fwatchdog

# Populate example here
# ENV fprocess="wc -l"

HEALTHCHECK --interval=5s CMD [ -e /tmp/.lock ] || exit 1
CMD ["fwatchdog"]

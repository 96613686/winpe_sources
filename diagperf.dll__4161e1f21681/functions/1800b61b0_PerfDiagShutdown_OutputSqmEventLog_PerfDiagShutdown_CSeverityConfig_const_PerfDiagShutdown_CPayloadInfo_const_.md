# PerfDiagShutdown::OutputSqmEventLog(PerfDiagShutdown::CSeverityConfig const &,PerfDiagShutdown::CPayloadInfo const &,PerfDiagShutdown::CPayloadDegradation const &)

- ea: `0x1800b61b0`
- end: `0x1800b63c2`
- name: `?OutputSqmEventLog@PerfDiagShutdown@@YAJAEBVCSeverityConfig@1@AEBUCPayloadInfo@1@AEBUCPayloadDegradation@1@@Z`
- size: `530`
- prototype: `__int64 __fastcall(PerfDiagShutdown *__hidden this, const struct PerfDiagShutdown::CSeverityConfig *, const struct PerfDiagShutdown::CPayloadInfo *, const struct PerfDiagShutdown::CPayloadDegradation *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x1800b67d8`

## callees

- `0x180039814`
- `0x1800441b4`
- `0x1800b1fe8`
- `0x1800b2490`
- `0x1800b4298`
- `0x1800b5a80`
- `0x1800b5de8`
- `0x1800b61b0`
- `0x1800c9b38`
- `0x1800cf080`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x1800b61f6`
- `ntdll!EtwEventActivityIdControl` at `0x1800b6383`
- `ntdll!EtwEventActivityIdControl` at `0x1800b61f6`
- `ntdll!EtwEventActivityIdControl` at `0x1800b6383`
- `ntdll!EtwEventUnregister` at `0x1800b6299`
- `ntdll!EtwEventUnregister` at `0x1800b6300`
- `ntdll!EtwEventUnregister` at `0x1800b636f`
- `ntdll!EtwEventUnregister` at `0x1800b639a`
- `ntdll!EtwEventUnregister` at `0x1800b6299`
- `ntdll!EtwEventUnregister` at `0x1800b6300`
- `ntdll!EtwEventUnregister` at `0x1800b636f`
- `ntdll!EtwEventUnregister` at `0x1800b639a`

## pseudocode

```c

```

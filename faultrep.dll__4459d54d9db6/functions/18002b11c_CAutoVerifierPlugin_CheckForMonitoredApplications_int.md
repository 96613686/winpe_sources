# CAutoVerifierPlugin::CheckForMonitoredApplications(int *)

- ea: `0x18002b11c`
- end: `0x18002b212`
- name: `?CheckForMonitoredApplications@CAutoVerifierPlugin@@AEAAJPEAH@Z`
- size: `246`
- prototype: `__int64 __fastcall(CAutoVerifierPlugin *__hidden this, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002d57c`

## callees

- `0x180009ed8`
- `0x18002b11c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b1b2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b1b2`

## string_xrefs

- `0x18002b195`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins\Autoverifier`

## pseudocode

```c

```

# MouseProcessor::UpdateMouseAsTouchMode(HKEY__ *)

- ea: `0x180095c94`
- end: `0x180095dbc`
- name: `?UpdateMouseAsTouchMode@MouseProcessor@@AEAAXPEAUHKEY__@@@Z`
- size: `296`
- prototype: `void(MouseProcessor *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x18019a2e0`

## callees

- `0x18008dcac`
- `0x180095c94`
- `0x180095eb0`
- `0x1800964a8`
- `0x1800964f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180095cdb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180095cdb`
- `win32u!NtMITEnableMouseIntercept` at `0x180095d4a`
- `win32u!NtMITEnableMouseIntercept` at `0x180095d4a`
- `win32u!NtMITDisableMouseIntercept` at `0x180095d6b`
- `win32u!NtMITDisableMouseIntercept` at `0x180095d6b`

## pseudocode

```c

```

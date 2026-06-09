# CLogonTaskFramework::s_WaitOnShellStartup(void)

- ea: `0x14000f06c`
- end: `0x14000f131`
- name: `?s_WaitOnShellStartup@CLogonTaskFramework@@CAXXZ`
- size: `197`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14000eeb8`

## callees

- `0x14000f06c`
- `0x14000f1a0`
- `0x14001eba8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000f0c3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000f0c3`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14000f080`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14000f080`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000f109`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000f109`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f09a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f0eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f09a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f0eb`

## string_xrefs

- `0x14000f11b`: `shell\lib\logontasks\logontasks.cpp`

## pseudocode

```c

```

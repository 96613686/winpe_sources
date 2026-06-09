# Kd1394Connection::SwitchVirtualDebuggerDriverMode(ulong)

- ea: `0x1800db3fc`
- end: `0x1800db572`
- name: `?SwitchVirtualDebuggerDriverMode@Kd1394Connection@@QEAAJK@Z`
- size: `374`
- prototype: `__int64 __fastcall(Kd1394Connection *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800db1f0`
- `0x1800e2200`
- `0x1804306f0`
- `0x180437650`

## callees

- `0x1800db3fc`
- `0x1800db578`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db4f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db501`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db4f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db501`
- `api-ms-win-core-misc-l1-1-0!LocalAlloc` at `0x1800db42c`
- `api-ms-win-core-misc-l1-1-0!LocalAlloc` at `0x1800db42c`
- `api-ms-win-core-misc-l1-1-0!LocalFree` at `0x1800db533`
- `api-ms-win-core-misc-l1-1-0!LocalFree` at `0x1800db553`
- `api-ms-win-core-misc-l1-1-0!LocalFree` at `0x1800db533`
- `api-ms-win-core-misc-l1-1-0!LocalFree` at `0x1800db553`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800db48f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800db4e1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800db48f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800db4e1`

## string_xrefs

- `0x1800db51f`: `Failed to send SetConfiguration 1394 Virtual Driver Request, error 0x%x\n`

## pseudocode

```c

```

# TryGetInput(ClientListCapture *,DbsDynamicString<ushort> *,ushort const *,DbsDynamicString<ushort> *,ulong,ulong)

- ea: `0x1800dbf18`
- end: `0x1800dc3c4`
- name: `?TryGetInput@@YAKPEAUClientListCapture@@PEAV?$DbsDynamicString@G@@PEBG1KK@Z`
- size: `1196`
- prototype: `__int64 __usercall@<rax>(ClientListCapture *this@<rcx>, int, char)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180196fcc`

## callees

- `0x1800793cc`
- `0x1800797ec`
- `0x18007a230`
- `0x18007a3d4`
- `0x1800830a0`
- `0x1800866c0`
- `0x18008f12c`
- `0x180094e40`
- `0x1800957e4`
- `0x1800b3a00`
- `0x1800dbf18`
- `0x1800e320c`
- `0x1801a8f80`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800dc154`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800dc154`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800dc0b6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800dc0b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dbfd4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dbfd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc0cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc0e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc0cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc0e3`

## string_xrefs

- `0x1800dc124`: `Unable to copy input buffer, 0x%x\n`

## pseudocode

```c

```

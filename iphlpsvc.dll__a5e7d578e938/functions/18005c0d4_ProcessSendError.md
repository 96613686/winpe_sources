# ProcessSendError

- ea: `0x18005c0d4`
- end: `0x18005c2a5`
- name: `ProcessSendError`
- size: `465`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180039b60`
- `0x18003a790`

## callees

- `0x18000d7c0`
- `0x1800159d4`
- `0x180037514`
- `0x18003c748`
- `0x180041a68`
- `0x18005c0d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005c1c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005c1c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005c261`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005c261`
- `WS2_32!__imp_setsockopt` at `0x18005c19a`
- `WS2_32!__imp_setsockopt` at `0x18005c19a`
- `WS2_32!__imp_shutdown` at `0x18005c20f`
- `WS2_32!__imp_shutdown` at `0x18005c20f`
- `WS2_32!__imp_WSAGetLastError` at `0x18005c220`
- `WS2_32!__imp_WSAGetLastError` at `0x18005c220`

## string_xrefs

- `0x18005c109`: `WriteFile on ovl %p failed with error %u = 0x%x`

## pseudocode

```c

```

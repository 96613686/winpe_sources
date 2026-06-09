# CreateEmptyHandle(int)

- ea: `0x18000cd18`
- end: `0x18000cf51`
- name: `?CreateEmptyHandle@@YAPEAVCMsiHandle@@H@Z`
- size: `569`
- prototype: `struct CMsiHandle *__fastcall(int)`
- caller_count: `8`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000b8bc`
- `0x18000bb80`
- `0x18000c2a0`
- `0x18000cb24`
- `0x18000cb60`
- `0x18002a320`
- `0x1800f9200`
- `0x18011eec0`

## callees

- `0x18000c4bc`
- `0x18000cd18`
- `0x18000d6d8`
- `0x1800b9b4c`
- `0x180266010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000cda7`
- `KERNEL32!LeaveCriticalSection` at `0x18000ce1e`
- `KERNEL32!LeaveCriticalSection` at `0x18000cda7`
- `KERNEL32!LeaveCriticalSection` at `0x18000ce1e`
- `KERNEL32!GetCurrentThreadId` at `0x18000cd85`
- `KERNEL32!GetCurrentThreadId` at `0x18000cd85`
- `KERNEL32!EnterCriticalSection` at `0x18000cd31`
- `KERNEL32!EnterCriticalSection` at `0x18000cd67`
- `KERNEL32!EnterCriticalSection` at `0x18000cd31`
- `KERNEL32!EnterCriticalSection` at `0x18000cd67`
- `KERNEL32!TlsGetValue` at `0x18000ce9e`
- `KERNEL32!TlsGetValue` at `0x18000ce9e`

## string_xrefs

- `0x18000cf07`: `Creating MSIHANDLE (%d) of type %d for thread %d`

## pseudocode

```c

```

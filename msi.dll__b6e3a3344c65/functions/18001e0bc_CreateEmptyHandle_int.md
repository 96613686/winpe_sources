# CreateEmptyHandle(int)

- ea: `0x18001e0bc`
- end: `0x18001e2d0`
- name: `?CreateEmptyHandle@@YAPEAVCMsiHandle@@H@Z`
- size: `532`
- prototype: `struct CMsiHandle *__fastcall(int)`
- caller_count: `8`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18001dee8`
- `0x18001df20`
- `0x180057cf0`
- `0x180059500`
- `0x1800598c0`
- `0x180059fb0`
- `0x18009d810`
- `0x180117e10`

## callees

- `0x18001e0bc`
- `0x18001e9f8`
- `0x180025a18`
- `0x1800b00f4`
- `0x18025c010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001e139`
- `KERNEL32!LeaveCriticalSection` at `0x18001e1aa`
- `KERNEL32!LeaveCriticalSection` at `0x18001e139`
- `KERNEL32!LeaveCriticalSection` at `0x18001e1aa`
- `KERNEL32!GetCurrentThreadId` at `0x18001e11d`
- `KERNEL32!GetCurrentThreadId` at `0x18001e11d`
- `KERNEL32!EnterCriticalSection` at `0x18001e0d5`
- `KERNEL32!EnterCriticalSection` at `0x18001e105`
- `KERNEL32!EnterCriticalSection` at `0x18001e0d5`
- `KERNEL32!EnterCriticalSection` at `0x18001e105`
- `KERNEL32!TlsGetValue` at `0x18001e223`
- `KERNEL32!TlsGetValue` at `0x18001e223`

## string_xrefs

- `0x18001e286`: `Creating MSIHANDLE (%d) of type %d for thread %d`

## pseudocode

```c

```

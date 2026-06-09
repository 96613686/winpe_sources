# RegRow::LockRead(void)

- ea: `0x18001f340`
- end: `0x18001f42f`
- name: `?LockRead@RegRow@@UEAAJXZ`
- size: `239`
- prototype: `__int64 __fastcall(RegRow *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180012654`
- `0x18001f340`
- `0x180029130`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f414`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f414`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001f424`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001f424`

## string_xrefs

- `0x18001f3a6`: `com\complus\src\events\shared\utsem.cpp`
- `0x18001f3c3`: `com\complus\src\events\shared\utsem.cpp`
- `0x18001f39a`: `(m_dwFlag & READERS_MASK) != 0`
- `0x18001f3b7`: `(m_dwFlag & WRITERS_MASK) == 0`

## pseudocode

```c

```

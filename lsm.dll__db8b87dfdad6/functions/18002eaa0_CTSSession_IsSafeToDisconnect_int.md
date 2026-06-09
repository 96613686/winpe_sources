# CTSSession::IsSafeToDisconnect(int)

- ea: `0x18002eaa0`
- end: `0x18002ebba`
- name: `?IsSafeToDisconnect@CTSSession@@AEAAHH@Z`
- size: `282`
- prototype: `__int64 __fastcall(CTSSession *__hidden this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180032424`

## callees

- `0x1800074c0`
- `0x180017da0`
- `0x18001e8e0`
- `0x18001ea44`
- `0x1800242f0`
- `0x18002eaa0`

## import_xrefs

- `ntdll!NtFreeVirtualMemory` at `0x18002eb9c`
- `ntdll!NtFreeVirtualMemory` at `0x18002eb9c`
- `ntdll!NtAllocateVirtualMemory` at `0x18002eb6e`
- `ntdll!NtAllocateVirtualMemory` at `0x18002eb6e`

## string_xrefs

- `0x18002eb21`: `MinPerSessionPageCommit`
- `0x18002eb78`: `Glass session cannot disconnect. Not enough memory to create a new session!`

## pseudocode

```c

```

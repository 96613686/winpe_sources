# CTerminalTypeHelper::GetSessionSource(_GUID,_SESSIONSOURCE *)

- ea: `0x18004e09c`
- end: `0x18004e243`
- name: `?GetSessionSource@CTerminalTypeHelper@@SAJU_GUID@@PEAW4_SESSIONSOURCE@@@Z`
- size: `423`
- prototype: `__int64 __fastcall(UUID *Uuid, enum _SESSIONSOURCE *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002f020`

## callees

- `0x1800077a0`
- `0x18000af60`
- `0x18000bcc8`
- `0x180020094`
- `0x18004e09c`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x18004e16e`
- `RPCRT4!UuidToStringW` at `0x18004e16e`
- `RPCRT4!RpcStringFreeW` at `0x18004e20f`
- `RPCRT4!RpcStringFreeW` at `0x18004e20f`

## string_xrefs

- `0x18004e147`: `RegTerminal.OpenKey failed: 0x%x in %s`
- `0x18004e1c3`: `RegTerminalType.OpenKey failed: 0x%x in %s`
- `0x18004e1f3`: `RegTerminalType.ReadRegString failed: 0x%x in %s`

## pseudocode

```c

```

# CTerminalTypeHelper::GetSessionSource(_GUID,_SESSIONSOURCE *)

- ea: `0x18004accc`
- end: `0x18004ae66`
- name: `?GetSessionSource@CTerminalTypeHelper@@SAJU_GUID@@PEAW4_SESSIONSOURCE@@@Z`
- size: `410`
- prototype: `__int64 __fastcall(UUID *Uuid, enum _SESSIONSOURCE *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002d060`

## callees

- `0x1800074c0`
- `0x180017da0`
- `0x18001e8e0`
- `0x18001ea44`
- `0x18004accc`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x18004ad9e`
- `RPCRT4!UuidToStringW` at `0x18004ad9e`
- `RPCRT4!RpcStringFreeW` at `0x18004ae39`
- `RPCRT4!RpcStringFreeW` at `0x18004ae39`

## string_xrefs

- `0x18004ad77`: `RegTerminal.OpenKey failed: 0x%x in %s`
- `0x18004aded`: `RegTerminalType.OpenKey failed: 0x%x in %s`
- `0x18004ae1d`: `RegTerminalType.ReadRegString failed: 0x%x in %s`

## pseudocode

```c

```

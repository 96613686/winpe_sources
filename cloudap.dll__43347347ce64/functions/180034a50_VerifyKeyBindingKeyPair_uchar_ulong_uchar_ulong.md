# VerifyKeyBindingKeyPair(uchar *,ulong,uchar *,ulong)

- ea: `0x180034a50`
- end: `0x180034b5c`
- name: `?VerifyKeyBindingKeyPair@@YAHPEAEK0K@Z`
- size: `268`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x180034a50`
- `0x180034b64`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180034a9b`
- `RPCRT4!NdrClientCall3` at `0x180034a9b`
- `RPCRT4!RpcExceptionFilter` at `0x18007fbc4`
- `RPCRT4!RpcExceptionFilter` at `0x18007fbc4`
- `RPCRT4!I_RpcMapWin32Status` at `0x180034ab1`
- `RPCRT4!I_RpcMapWin32Status` at `0x180034ab1`

## string_xrefs

- `0x180034abf`: `onecore\ds\ext\cloudap\dll\crediso.cpp`
- `0x180034b04`: `onecore\ds\ext\cloudap\dll\crediso.cpp`

## pseudocode

```c

```

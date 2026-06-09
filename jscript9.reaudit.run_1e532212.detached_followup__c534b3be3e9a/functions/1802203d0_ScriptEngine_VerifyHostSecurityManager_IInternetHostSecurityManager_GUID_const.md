# ScriptEngine::VerifyHostSecurityManager(IInternetHostSecurityManager *,_GUID const *)

- ea: `0x1802203d0`
- end: `0x1802204d4`
- name: `?VerifyHostSecurityManager@ScriptEngine@@IEAAHPEAUIInternetHostSecurityManager@@PEBU_GUID@@@Z`
- size: `260`
- prototype: `__int64 __fastcall(ScriptEngine *__hidden this, struct IInternetHostSecurityManager *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1802177e4`

## callees

- `0x1802203d0`
- `0x180252cfc`
- `0x180341dd0`
- `0x18035e010`

## import_xrefs

- `ntdll!RtlCaptureContext` at `0x180220493`
- `ntdll!RtlCaptureContext` at `0x180220493`
- `KERNEL32!VirtualQuery` at `0x180220466`
- `KERNEL32!VirtualQuery` at `0x180220466`

## pseudocode

```c

```

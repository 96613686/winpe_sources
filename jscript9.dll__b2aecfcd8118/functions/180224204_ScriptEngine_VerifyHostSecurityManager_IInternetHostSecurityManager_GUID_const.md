# ScriptEngine::VerifyHostSecurityManager(IInternetHostSecurityManager *,_GUID const *)

- ea: `0x180224204`
- end: `0x180224315`
- name: `?VerifyHostSecurityManager@ScriptEngine@@IEAAHPEAUIInternetHostSecurityManager@@PEBU_GUID@@@Z`
- size: `273`
- prototype: `__int64 __fastcall(ScriptEngine *__hidden this, struct IInternetHostSecurityManager *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18021b0c8`

## callees

- `0x180224204`
- `0x1802572fc`
- `0x1803481f0`
- `0x180364010`

## import_xrefs

- `ntdll!RtlCaptureContext` at `0x1802242cd`
- `ntdll!RtlCaptureContext` at `0x1802242cd`
- `KERNEL32!VirtualQuery` at `0x18022429a`
- `KERNEL32!VirtualQuery` at `0x18022429a`

## pseudocode

```c

```

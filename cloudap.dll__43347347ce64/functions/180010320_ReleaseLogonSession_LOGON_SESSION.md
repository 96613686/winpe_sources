# ReleaseLogonSession(_LOGON_SESSION *)

- ea: `0x180010320`
- end: `0x1800103ab`
- name: `?ReleaseLogonSession@@YAXPEAU_LOGON_SESSION@@@Z`
- size: `139`
- prototype: `void __fastcall(struct _LOGON_SESSION *)`
- caller_count: `22`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800035b4`
- `0x18000e990`
- `0x18000f210`
- `0x18000fe60`
- `0x180011960`
- `0x180016a10`
- `0x18001b600`
- `0x180028430`
- `0x180033750`
- `0x1800358c0`
- `0x18003e2f0`
- `0x1800476a0`
- `0x1800479f0`
- `0x180048530`
- `0x18004a870`
- `0x18004bb2c`
- `0x18004d570`
- `0x18004d96c`
- `0x18004dd08`
- `0x1800571b0`
- `0x1800579a0`
- `0x180058090`

## callees

- `0x18000f100`
- `0x180010320`
- `0x180041770`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180010336`
- `ntdll!RtlAcquireResourceExclusive` at `0x180010336`
- `ntdll!RtlReleaseResource` at `0x180010356`
- `ntdll!RtlReleaseResource` at `0x180010389`
- `ntdll!RtlReleaseResource` at `0x180010356`
- `ntdll!RtlReleaseResource` at `0x180010389`

## pseudocode

```c

```

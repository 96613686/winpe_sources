# DxgkSetPointerShape(void * const,_DXGKARG_SETPOINTERPOSITION const *,_DXGKARG_SETPOINTERSHAPE const *,uint,uint,int,int,int)

- ea: `0x140313db0`
- end: `0x1403145ec`
- name: `?DxgkSetPointerShape@@YAJQEAXPEBU_DXGKARG_SETPOINTERPOSITION@@PEBU_DXGKARG_SETPOINTERSHAPE@@IIHHH@Z`
- size: `2108`
- prototype: `__int64 __fastcall(struct DXGADAPTER *, struct _DXGKARG_SETPOINTERPOSITION *, const struct _DXGKARG_SETPOINTERSHAPE *, unsigned int, unsigned int, int, int, int)`
- caller_count: `2`
- callee_count: `26`
- tags: ``

## callers

- `0x140312100`
- `0x140313d40`

## callees

- `0x140012540`
- `0x140012cd4`
- `0x140013a20`
- `0x1400146ac`
- `0x140015290`
- `0x140015940`
- `0x140015bc0`
- `0x140016388`
- `0x14001b9c0`
- `0x14001d214`
- `0x14001f630`
- `0x14002ee60`
- `0x14003d178`
- `0x140046608`
- `0x1400a0bd0`
- `0x140313db0`
- `0x1403148c4`
- `0x14031498c`
- `0x140315718`
- `0x140316a28`
- `0x140316a44`
- `0x140329ff0`
- `0x14035a180`
- `0x140375314`
- `0x1403ae998`
- `0x1403db370`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403142d1`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14031431b`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403143e3`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140314413`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403142d1`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14031431b`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403143e3`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140314413`
- `watchdog!WdLogSingleEntry2` at `0x1403143aa`
- `watchdog!WdLogSingleEntry2` at `0x1403143fd`
- `watchdog!WdLogSingleEntry2` at `0x1403143aa`
- `watchdog!WdLogSingleEntry2` at `0x1403143fd`
- `watchdog!WdLogSingleEntry3` at `0x140314296`
- `watchdog!WdLogSingleEntry3` at `0x14031452b`
- `watchdog!WdLogSingleEntry3` at `0x140314296`
- `watchdog!WdLogSingleEntry3` at `0x14031452b`
- `watchdog!WdLogSingleEntry0` at `0x140313ecf`
- `watchdog!WdLogSingleEntry0` at `0x140314103`
- `watchdog!WdLogSingleEntry0` at `0x14031415a`
- `watchdog!WdLogSingleEntry0` at `0x140314472`
- `watchdog!WdLogSingleEntry0` at `0x140313ecf`
- `watchdog!WdLogSingleEntry0` at `0x140314103`
- `watchdog!WdLogSingleEntry0` at `0x14031415a`
- `watchdog!WdLogSingleEntry0` at `0x140314472`
- `watchdog!WdLogSingleEntry5` at `0x140314305`
- `watchdog!WdLogSingleEntry5` at `0x140314305`
- `watchdog!WdLogSingleEntry1` at `0x1403144c2`
- `watchdog!WdLogSingleEntry1` at `0x1403144c2`

## string_xrefs

- `0x140314540`: `Failed to aquire adapter access on adapter = 0x%I64x%08I64x , Status = 0x%I64x.`

## pseudocode

```c

```

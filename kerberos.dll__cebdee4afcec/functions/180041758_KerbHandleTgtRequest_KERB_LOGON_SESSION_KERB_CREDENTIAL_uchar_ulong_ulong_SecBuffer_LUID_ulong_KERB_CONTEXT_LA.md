# KerbHandleTgtRequest(_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,uchar *,ulong,ulong,_SecBuffer *,_LUID *,ulong *,_KERB_CONTEXT * *,_LARGE_INTEGER *,long *)

- ea: `0x180041758`
- end: `0x180041bd0`
- name: `?KerbHandleTgtRequest@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_CREDENTIAL@@PEAEKKPEAU_SecBuffer@@PEAU_LUID@@PEAKPEAPEAU_KERB_CONTEXT@@PEAT_LARGE_INTEGER@@PEAJ@Z`
- size: `1144`
- prototype: `__int64 __usercall@<rax>(struct _KERB_LOGON_SESSION *@<rcx>, struct _KERB_CREDENTIAL *@<rdx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, unsigned int, struct _SecBuffer *, struct _LUID *, unsigned int *, struct _KERB_CONTEXT **, union _LARGE_INTEGER *, int *)`
- caller_count: `2`
- callee_count: `20`
- tags: `loader_planting`

## callers

- `0x18002db10`
- `0x1800cfc74`

## callees

- `0x1800063e8`
- `0x1800069a0`
- `0x1800069e0`
- `0x1800093f0`
- `0x180010e90`
- `0x180011150`
- `0x1800113f0`
- `0x180011520`
- `0x180020690`
- `0x18002a930`
- `0x18002ad08`
- `0x180041758`
- `0x1800484f8`
- `0x18006aa04`
- `0x18006e90c`
- `0x1800744cf`
- `0x180086d4c`
- `0x18008a49c`
- `0x18008b70c`
- `0x180092c24`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x1800419cc`
- `ntdll!RtlReleaseResource` at `0x180041b4d`
- `ntdll!RtlReleaseResource` at `0x1800419cc`
- `ntdll!RtlReleaseResource` at `0x180041b4d`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800419a3`
- `ntdll!RtlAcquireResourceExclusive` at `0x180041b2c`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800419a3`
- `ntdll!RtlAcquireResourceExclusive` at `0x180041b2c`
- `ntdll!RtlEnterCriticalSection` at `0x18004187e`
- `ntdll!RtlEnterCriticalSection` at `0x18004187e`
- `ntdll!RtlLeaveCriticalSection` at `0x180041b5d`
- `ntdll!RtlLeaveCriticalSection` at `0x180041b5d`

## string_xrefs

- `0x1800419fa`: `KerbHandleTgtRequest (TGT in TGT reply) saving ASC context->TicketCacheEntry, TGT is %p, was %p\n`
- `0x180041a7c`: `Output token is too small - sent in %d, needed %d`

## pseudocode

```c

```

# _ReleaseUserCacheEntry(_LUID *,_USER_CACHE_ENTRY *)

- ea: `0x18000f100`
- end: `0x18000f200`
- name: `?_ReleaseUserCacheEntry@@YAXPEAU_LUID@@PEAU_USER_CACHE_ENTRY@@@Z`
- size: `256`
- prototype: `void __fastcall(struct _LUID *, struct _USER_CACHE_ENTRY *)`
- caller_count: `16`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800035b4`
- `0x180007920`
- `0x1800094e0`
- `0x18000bda0`
- `0x18000ee80`
- `0x180010320`
- `0x180011960`
- `0x180015b98`
- `0x1800209d0`
- `0x180027320`
- `0x180037240`
- `0x180048e60`
- `0x18004db24`
- `0x180052358`
- `0x1800571b0`
- `0x1800579a0`

## callees

- `0x18000f100`
- `0x180010460`
- `0x18003de28`
- `0x18003df0c`
- `0x18004d514`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18000f12d`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000f12d`
- `ntdll!RtlReleaseResource` at `0x18000f144`
- `ntdll!RtlReleaseResource` at `0x18000f1a4`
- `ntdll!RtlReleaseResource` at `0x18000f144`
- `ntdll!RtlReleaseResource` at `0x18000f1a4`

## pseudocode

```c

```

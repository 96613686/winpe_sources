# KerbUnpackTgtReply(_KERB_CONTEXT *,uchar *,ulong,_KERB_INTERNAL_NAME * *,_UNICODE_STRING *,KERB_TGT_REPLY * *)

- ea: `0x180088424`
- end: `0x180088686`
- name: `?KerbUnpackTgtReply@@YAJPEAU_KERB_CONTEXT@@PEAEKPEAPEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@PEAPEAUKERB_TGT_REPLY@@@Z`
- size: `610`
- prototype: `int(struct _KERB_CONTEXT *, unsigned __int8 *, unsigned int, struct _KERB_INTERNAL_NAME **, struct _UNICODE_STRING *, struct KERB_TGT_REPLY **)`
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180021574`
- `0x1800cbea8`
- `0x1800ce114`

## callees

- `0x1800068d0`
- `0x1800069e0`
- `0x180010e90`
- `0x180011150`
- `0x1800113f0`
- `0x180011520`
- `0x18005de50`
- `0x1800643dc`
- `0x180088424`
- `0x18008b70c`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18008847e`
- `ntdll!RtlReleaseResource` at `0x18008857c`
- `ntdll!RtlReleaseResource` at `0x18008847e`
- `ntdll!RtlReleaseResource` at `0x18008857c`
- `ntdll!RtlAcquireResourceShared` at `0x18008846a`
- `ntdll!RtlAcquireResourceShared` at `0x18008846a`
- `ntdll!RtlAcquireResourceExclusive` at `0x180088561`
- `ntdll!RtlAcquireResourceExclusive` at `0x180088561`

## string_xrefs

- `0x1800884ef`: `KerbUnpackTgtReply failed to verify u2u token header\n`

## pseudocode

```c

```

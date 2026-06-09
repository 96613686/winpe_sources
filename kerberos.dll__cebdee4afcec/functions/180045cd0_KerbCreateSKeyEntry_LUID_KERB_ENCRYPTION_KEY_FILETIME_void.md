# KerbCreateSKeyEntry(_LUID *,_KERB_ENCRYPTION_KEY *,_FILETIME *,void *)

- ea: `0x180045cd0`
- end: `0x180045e50`
- name: `?KerbCreateSKeyEntry@@YAJPEAU_LUID@@PEAU_KERB_ENCRYPTION_KEY@@PEAU_FILETIME@@PEAX@Z`
- size: `384`
- prototype: `int(struct _LUID *, struct _KERB_ENCRYPTION_KEY *, struct _FILETIME *, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180021574`
- `0x1800cc8a8`

## callees

- `0x1800093f0`
- `0x180010e90`
- `0x180016550`
- `0x18002cea0`
- `0x180045cd0`
- `0x18008b70c`

## import_xrefs

- `ntdll!NtClose` at `0x180045e2c`
- `ntdll!NtClose` at `0x180045e2c`
- `ntdll!RtlReleaseResource` at `0x180045e1c`
- `ntdll!RtlReleaseResource` at `0x180045e1c`
- `ntdll!RtlAcquireResourceExclusive` at `0x180045ddf`
- `ntdll!RtlAcquireResourceExclusive` at `0x180045ddf`
- `ntdll!NtDuplicateObject` at `0x180045d6e`
- `ntdll!NtDuplicateObject` at `0x180045d6e`

## string_xrefs

- `0x180045d7a`: `KerbCreateSKeyEntry failed to duplicate client token: %#x\n`
- `0x180045d8b`: `KerbCreateSKeyEntry`

## pseudocode

```c

```

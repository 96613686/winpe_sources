# NlpShouldUpdateDpapi(void *,_LUID const *)

- ea: `0x18000cc9c`
- end: `0x18000cdde`
- name: `?NlpShouldUpdateDpapi@@YAEPEAXPEBU_LUID@@@Z`
- size: `322`
- prototype: `unsigned __int8 __fastcall(struct _SID *, const struct _LUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18000b3b0`

## callees

- `0x18000cc9c`
- `0x18000cde4`
- `0x18000ce48`
- `0x18002f014`
- `0x18002f3f4`
- `0x18003509c`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18000cd12`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000cd12`
- `ntdll!RtlReleaseResource` at `0x18000cd31`
- `ntdll!RtlReleaseResource` at `0x18000cd31`

## pseudocode

```c

```

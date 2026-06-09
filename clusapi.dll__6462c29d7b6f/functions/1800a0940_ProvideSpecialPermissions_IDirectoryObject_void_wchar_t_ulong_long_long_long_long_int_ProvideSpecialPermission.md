# ProvideSpecialPermissions(IDirectoryObject *,void *,wchar_t * *,ulong,long,long,long,long,int,ProvideSpecialPermissionsErrorStep *)

- ea: `0x1800a0940`
- end: `0x1800a0bd5`
- name: `?ProvideSpecialPermissions@@YAJPEAUIDirectoryObject@@PEAXPEAPEA_WKJJJJHPEAW4ProvideSpecialPermissionsErrorStep@@@Z`
- size: `661`
- prototype: `int(struct IDirectoryObject *, void *, wchar_t **, unsigned int, int, int, int, int, int, enum ProvideSpecialPermissionsErrorStep *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800795d0`
- `0x1800a1d98`

## callees

- `0x1800a0124`
- `0x1800a0250`
- `0x1800a07f8`
- `0x1800a0940`
- `0x1800b5010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800a099b`
- `OLEAUT32!__imp_VariantInit` at `0x1800a09a5`
- `OLEAUT32!__imp_VariantInit` at `0x1800a099b`
- `OLEAUT32!__imp_VariantInit` at `0x1800a09a5`
- `OLEAUT32!__imp_VariantClear` at `0x1800a0b73`
- `OLEAUT32!__imp_VariantClear` at `0x1800a0b7d`
- `OLEAUT32!__imp_VariantClear` at `0x1800a0b73`
- `OLEAUT32!__imp_VariantClear` at `0x1800a0b7d`

## string_xrefs

- `0x1800a0b0a`: `nTSecurityDescriptor`

## pseudocode

```c

```

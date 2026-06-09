# ARI::Internal::PackageSidFromProductId(_GUID const *,void * *)

- ea: `0x1800067f0`
- end: `0x1800067f6`
- name: `?PackageSidFromProductId@Internal@ARI@@YAJPEBU_GUID@@PEAPEAX@Z`
- size: `6`
- prototype: `int(ARI::Internal *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `KERNELBASE!PackageSidFromProductId` at `0x1800067f0`

## pseudocode

```c
// attributes: thunk
int __fastcall ARI::Internal::PackageSidFromProductId(ARI::Internal *this, const struct _GUID *a2, void **a3)
{
  return __imp_?PackageSidFromProductId@Internal@ARI@@YAJPEBU_GUID@@PEAPEAX@Z(this, a2, a3);
}

```

## disassembly

```asm
0x1800067f0  jmp     cs:__imp_?PackageSidFromProductId@Internal@ARI@@YAJPEBU_GUID@@PEAPEAX@Z
```

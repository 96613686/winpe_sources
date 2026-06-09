# ARI::Internal::MsixIsSystemPackageByPackageFullName(ushort const *,int *)

- ea: `0x1800067e0`
- end: `0x1800067e6`
- name: `?MsixIsSystemPackageByPackageFullName@Internal@ARI@@YAJPEBGPEAH@Z`
- size: `6`
- prototype: `int(ARI::Internal *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `KERNELBASE!MsixIsSystemPackageByPackageFullName` at `0x1800067e0`

## pseudocode

```c
// attributes: thunk
int __fastcall ARI::Internal::MsixIsSystemPackageByPackageFullName(
        ARI::Internal *this,
        const unsigned __int16 *a2,
        int *a3)
{
  return __imp_?MsixIsSystemPackageByPackageFullName@Internal@ARI@@YAJPEBGPEAH@Z(this, a2, a3);
}

```

## disassembly

```asm
0x1800067e0  jmp     cs:__imp_?MsixIsSystemPackageByPackageFullName@Internal@ARI@@YAJPEBGPEAH@Z
```

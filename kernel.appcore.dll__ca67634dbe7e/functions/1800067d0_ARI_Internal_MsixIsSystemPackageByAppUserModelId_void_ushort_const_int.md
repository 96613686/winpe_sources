# ARI::Internal::MsixIsSystemPackageByAppUserModelId(void *,ushort const *,int *)

- ea: `0x1800067d0`
- end: `0x1800067d6`
- name: `?MsixIsSystemPackageByAppUserModelId@Internal@ARI@@YAJPEAXPEBGPEAH@Z`
- size: `6`
- prototype: `int(ARI::Internal *__hidden this, void *, const unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `KERNELBASE!MsixIsSystemPackageByAppUserModelId` at `0x1800067d0`

## pseudocode

```c
// attributes: thunk
int __fastcall ARI::Internal::MsixIsSystemPackageByAppUserModelId(
        ARI::Internal *this,
        void *a2,
        const unsigned __int16 *a3,
        int *a4)
{
  return __imp_?MsixIsSystemPackageByAppUserModelId@Internal@ARI@@YAJPEAXPEBGPEAH@Z(this, a2, a3, a4);
}

```

## disassembly

```asm
0x1800067d0  jmp     cs:__imp_?MsixIsSystemPackageByAppUserModelId@Internal@ARI@@YAJPEAXPEBGPEAH@Z
```

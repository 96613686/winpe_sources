# PackageSidFromFamilyName

- ea: `0x1800073d0`
- end: `0x1800073d6`
- name: `PackageSidFromFamilyName`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `KERNELBASE!PackageSidFromFamilyName` at `0x1800073d0`

## pseudocode

```c
// attributes: thunk
__int64 PackageSidFromFamilyName()
{
  return __imp_PackageSidFromFamilyName();
}

```

## disassembly

```asm
0x1800073d0  jmp     cs:__imp_PackageSidFromFamilyName
```

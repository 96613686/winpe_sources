# GetStagedPackagePathByFullName2

- ea: `0x1800070d0`
- end: `0x1800070d6`
- name: `GetStagedPackagePathByFullName2`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!GetStagedPackagePathByFullName2` at `0x1800070d0`

## pseudocode

```c
// attributes: thunk
__int64 GetStagedPackagePathByFullName2()
{
  return __imp_GetStagedPackagePathByFullName2();
}

```

## disassembly

```asm
0x1800070d0  jmp     cs:__imp_GetStagedPackagePathByFullName2
```

# GetPackagePathByFullName2

- ea: `0x180006f20`
- end: `0x180006f26`
- name: `GetPackagePathByFullName2`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!GetPackagePathByFullName2` at `0x180006f20`

## pseudocode

```c
// attributes: thunk
__int64 GetPackagePathByFullName2()
{
  return __imp_GetPackagePathByFullName2();
}

```

## disassembly

```asm
0x180006f20  jmp     cs:__imp_GetPackagePathByFullName2
```

# SaveAlternatePackageRootPath

- ea: `0x180007510`
- end: `0x180007516`
- name: `SaveAlternatePackageRootPath`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!SaveAlternatePackageRootPath` at `0x180007510`

## pseudocode

```c
// attributes: thunk
__int64 SaveAlternatePackageRootPath()
{
  return __imp_SaveAlternatePackageRootPath();
}

```

## disassembly

```asm
0x180007510  jmp     cs:__imp_SaveAlternatePackageRootPath
```

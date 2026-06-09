# DeletePackageDependency

- ea: `0x180006af0`
- end: `0x180006af6`
- name: `DeletePackageDependency`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!DeletePackageDependency` at `0x180006af0`

## pseudocode

```c
// attributes: thunk
__int64 DeletePackageDependency()
{
  return __imp_DeletePackageDependency();
}

```

## disassembly

```asm
0x180006af0  jmp     cs:__imp_DeletePackageDependency
```

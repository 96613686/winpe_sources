# RemovePackageDependency

- ea: `0x1800074d0`
- end: `0x1800074d6`
- name: `RemovePackageDependency`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!RemovePackageDependency` at `0x1800074d0`

## pseudocode

```c
// attributes: thunk
__int64 RemovePackageDependency()
{
  return __imp_RemovePackageDependency();
}

```

## disassembly

```asm
0x1800074d0  jmp     cs:__imp_RemovePackageDependency
```

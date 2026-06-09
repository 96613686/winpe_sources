# WriteStateAtomValue

- ea: `0x180007710`
- end: `0x180007716`
- name: `WriteStateAtomValue`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!WriteStateAtomValue` at `0x180007710`

## pseudocode

```c
// attributes: thunk
__int64 WriteStateAtomValue()
{
  return __imp_WriteStateAtomValue();
}

```

## disassembly

```asm
0x180007710  jmp     cs:__imp_WriteStateAtomValue
```

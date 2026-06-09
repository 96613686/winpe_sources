# DeleteStateAtomValue

- ea: `0x180006b00`
- end: `0x180006b06`
- name: `DeleteStateAtomValue`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!DeleteStateAtomValue` at `0x180006b00`

## pseudocode

```c
// attributes: thunk
__int64 DeleteStateAtomValue()
{
  return __imp_DeleteStateAtomValue();
}

```

## disassembly

```asm
0x180006b00  jmp     cs:__imp_DeleteStateAtomValue
```

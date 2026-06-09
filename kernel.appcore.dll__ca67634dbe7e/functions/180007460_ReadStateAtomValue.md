# ReadStateAtomValue

- ea: `0x180007460`
- end: `0x180007466`
- name: `ReadStateAtomValue`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!ReadStateAtomValue` at `0x180007460`

## pseudocode

```c
// attributes: thunk
__int64 ReadStateAtomValue()
{
  return __imp_ReadStateAtomValue();
}

```

## disassembly

```asm
0x180007460  jmp     cs:__imp_ReadStateAtomValue
```

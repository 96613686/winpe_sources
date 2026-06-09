# ReadStateContainerValue

- ea: `0x180007470`
- end: `0x180007476`
- name: `ReadStateContainerValue`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!ReadStateContainerValue` at `0x180007470`

## pseudocode

```c
// attributes: thunk
__int64 ReadStateContainerValue()
{
  return __imp_ReadStateContainerValue();
}

```

## disassembly

```asm
0x180007470  jmp     cs:__imp_ReadStateContainerValue
```

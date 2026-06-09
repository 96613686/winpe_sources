# DeleteStateContainerValue

- ea: `0x180006b20`
- end: `0x180006b26`
- name: `DeleteStateContainerValue`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!DeleteStateContainerValue` at `0x180006b20`

## pseudocode

```c
// attributes: thunk
__int64 DeleteStateContainerValue()
{
  return __imp_DeleteStateContainerValue();
}

```

## disassembly

```asm
0x180006b20  jmp     cs:__imp_DeleteStateContainerValue
```

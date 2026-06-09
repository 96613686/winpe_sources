# WriteStateContainerValue

- ea: `0x180007720`
- end: `0x180007726`
- name: `WriteStateContainerValue`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!WriteStateContainerValue` at `0x180007720`

## pseudocode

```c
// attributes: thunk
__int64 WriteStateContainerValue()
{
  return __imp_WriteStateContainerValue();
}

```

## disassembly

```asm
0x180007720  jmp     cs:__imp_WriteStateContainerValue
```

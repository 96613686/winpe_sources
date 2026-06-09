# DeleteStateContainer

- ea: `0x180006b10`
- end: `0x180006b16`
- name: `DeleteStateContainer`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!DeleteStateContainer` at `0x180006b10`

## pseudocode

```c
// attributes: thunk
__int64 DeleteStateContainer()
{
  return __imp_DeleteStateContainer();
}

```

## disassembly

```asm
0x180006b10  jmp     cs:__imp_DeleteStateContainer
```

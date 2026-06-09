# CreateStateSubcontainer

- ea: `0x180006ae0`
- end: `0x180006ae6`
- name: `CreateStateSubcontainer`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!CreateStateSubcontainer` at `0x180006ae0`

## pseudocode

```c
// attributes: thunk
__int64 CreateStateSubcontainer()
{
  return __imp_CreateStateSubcontainer();
}

```

## disassembly

```asm
0x180006ae0  jmp     cs:__imp_CreateStateSubcontainer
```

# CreateStateContainer

- ea: `0x180006ac0`
- end: `0x180006ac6`
- name: `CreateStateContainer`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!CreateStateContainer` at `0x180006ac0`

## pseudocode

```c
// attributes: thunk
__int64 CreateStateContainer()
{
  return __imp_CreateStateContainer();
}

```

## disassembly

```asm
0x180006ac0  jmp     cs:__imp_CreateStateContainer
```

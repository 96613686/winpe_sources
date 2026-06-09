# CreateStateAtom

- ea: `0x180006aa0`
- end: `0x180006aa6`
- name: `CreateStateAtom`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!CreateStateAtom` at `0x180006aa0`

## pseudocode

```c
// attributes: thunk
__int64 CreateStateAtom()
{
  return __imp_CreateStateAtom();
}

```

## disassembly

```asm
0x180006aa0  jmp     cs:__imp_CreateStateAtom
```

# OpenStateAtom

- ea: `0x180007270`
- end: `0x180007276`
- name: `OpenStateAtom`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!OpenStateAtom` at `0x180007270`

## pseudocode

```c
// attributes: thunk
__int64 OpenStateAtom()
{
  return __imp_OpenStateAtom();
}

```

## disassembly

```asm
0x180007270  jmp     cs:__imp_OpenStateAtom
```

# CommitStateAtom

- ea: `0x180006a80`
- end: `0x180006a86`
- name: `CommitStateAtom`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNELBASE!CommitStateAtom` at `0x180006a80`

## pseudocode

```c
// attributes: thunk
__int64 CommitStateAtom()
{
  return __imp_CommitStateAtom();
}

```

## disassembly

```asm
0x180006a80  jmp     cs:__imp_CommitStateAtom
```

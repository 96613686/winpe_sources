# operator delete(void *)

- ea: `0x1800028b0`
- end: `0x1800028b5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800030a4`
- `0x1800036a0`
- `0x180003770`
- `0x180004400`
- `0x180004438`

## callees

- `0x180003854`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free(Block);
}

```

## disassembly

```asm
0x1800028b0  jmp     free
```

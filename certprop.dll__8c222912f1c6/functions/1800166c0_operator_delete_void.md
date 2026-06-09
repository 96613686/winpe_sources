# operator delete(void *)

- ea: `0x1800166c0`
- end: `0x1800166c5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180016114`
- `0x180016120`

## callees

- `0x180016a4e`

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
0x1800166c0  jmp     free
```

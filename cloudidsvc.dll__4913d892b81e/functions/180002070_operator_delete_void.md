# operator delete(void *)

- ea: `0x180002070`
- end: `0x180002075`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001a74`
- `0x180001e50`

## callees

- `0x1800024c0`

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
0x180002070  jmp     free
```

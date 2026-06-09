# operator delete(void *)

- ea: `0x180001070`
- end: `0x180001075`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001d50`
- `0x180001d80`
- `0x180001db0`
- `0x180001e20`
- `0x180002ad0`

## callees

- `0x180001635`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free_0(Block);
}

```

## disassembly

```asm
0x180001070  jmp     free_0
```

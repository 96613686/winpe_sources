# operator delete(void *)

- ea: `0x180001e7c`
- end: `0x180001e81`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001a00`
- `0x1800024a0`
- `0x180002560`

## callees

- `0x180001f64`

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
0x180001e7c  jmp     free
```

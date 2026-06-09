# operator delete(void *)

- ea: `0x180001948`
- end: `0x18000194d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001954`
- `0x180001960`
- `0x180001c50`

## callees

- `0x180002094`

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
0x180001948  jmp     free
```

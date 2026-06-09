# operator delete(void *)

- ea: `0x180001928`
- end: `0x18000192d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800021c4`
- `0x180002320`
- `0x1800023a0`

## callees

- `0x1800015d1`

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
0x180001928  jmp     free_0
```

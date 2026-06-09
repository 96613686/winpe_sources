# operator delete(void *)

- ea: `0x180001e1c`
- end: `0x180001e21`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800018f0`
- `0x180001900`

## callees

- `0x180001f7a`

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
0x180001e1c  jmp     free
```

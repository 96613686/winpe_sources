# operator delete(void *)

- ea: `0x18001028c`
- end: `0x180010291`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000fde0`
- `0x18000fdf0`

## callees

- `0x180010384`

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
0x18001028c  jmp     free
```

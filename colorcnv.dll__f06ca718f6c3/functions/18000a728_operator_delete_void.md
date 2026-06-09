# operator delete(void *)

- ea: `0x18000a728`
- end: `0x18000a72d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180008564`
- `0x180009630`
- `0x18000a6d0`

## callees

- `0x18000b444`

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
0x18000a728  jmp     free
```

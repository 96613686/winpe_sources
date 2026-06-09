# operator delete(void *)

- ea: `0x180024a7c`
- end: `0x180024a81`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `12`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001eb58`
- `0x180021aa4`
- `0x1800245f0`
- `0x180024e10`
- `0x18003f408`
- `0x180045130`
- `0x180045160`
- `0x1800451a0`
- `0x1800451e0`
- `0x18004b194`
- `0x18006d8d0`
- `0x18006d908`

## callees

- `0x180024b94`

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
0x180024a7c  jmp     free
```

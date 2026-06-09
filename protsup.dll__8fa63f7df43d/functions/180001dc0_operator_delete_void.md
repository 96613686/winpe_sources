# operator delete(void *)

- ea: `0x180001dc0`
- end: `0x180001dc5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001b70`
- `0x180001be0`
- `0x180003220`
- `0x180003250`
- `0x180003a40`

## callees

- `0x180002296`

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
0x180001dc0  jmp     free_0
```

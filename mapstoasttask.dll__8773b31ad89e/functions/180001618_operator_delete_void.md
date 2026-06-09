# operator delete(void *)

- ea: `0x180001618`
- end: `0x18000161d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001624`
- `0x180001630`
- `0x180002bf0`
- `0x180002c24`
- `0x180002cb0`
- `0x180002cf0`
- `0x180002d30`
- `0x180002d70`

## callees

- `0x180001fbe`

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
0x180001618  jmp     free
```

# operator delete(void *)

- ea: `0x180001178`
- end: `0x18000117d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `11`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001160`
- `0x180007dbc`
- `0x180007eb0`
- `0x180007ef0`
- `0x180008180`
- `0x180008ed0`
- `0x180008f00`
- `0x180008f40`
- `0x180008f80`
- `0x180009404`
- `0x1800094b8`

## callees

- `0x180001e74`

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
0x180001178  jmp     free
```

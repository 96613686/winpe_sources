# operator delete[](void *,unsigned __int64)

- ea: `0x140001fc4`
- end: `0x140001fc9`
- name: `??_V@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140004610`

## callees

- `0x140001c54`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete[](void *Block)
{
  operator delete(Block);
}

```

## disassembly

```asm
0x140001fc4  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```

# operator delete[](void *,unsigned __int64)

- ea: `0x180001830`
- end: `0x180001835`
- name: `??_V@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000961c`
- `0x1800096c4`
- `0x18000c0bc`
- `0x180025a5d`
- `0x180025ac6`

## callees

- `0x180001824`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete[](void *Block)
{
  operator delete(Block);
}

```

## disassembly

```asm
0x180001830  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```

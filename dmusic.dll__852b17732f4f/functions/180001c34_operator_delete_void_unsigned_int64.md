# operator delete[](void *,unsigned __int64)

- ea: `0x180001c34`
- end: `0x180001c39`
- name: `??_V@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180017e90`
- `0x180021b37`

## callees

- `0x1800012c4`

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
0x180001c34  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```

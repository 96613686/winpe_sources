# operator delete[](void *,unsigned __int64)

- ea: `0x180001810`
- end: `0x180001815`
- name: `??_V@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000918c`
- `0x180009234`
- `0x18000bb44`
- `0x180024b9d`
- `0x180024c05`

## callees

- `0x180001804`

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
0x180001810  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```

# operator delete[](void *)

- ea: `0x180001020`
- end: `0x180001025`
- name: `??_V@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001fec`
- `0x1800022b4`
- `0x180002bc0`
- `0x180002f24`
- `0x180003ae8`
- `0x180004498`
- `0x1800047f8`

## callees

- `0x180001008`

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
0x180001020  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

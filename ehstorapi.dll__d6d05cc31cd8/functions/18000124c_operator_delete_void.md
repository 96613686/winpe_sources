# operator delete[](void *)

- ea: `0x18000124c`
- end: `0x180001251`
- name: `??_V@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `10`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002d68`
- `0x1800046b4`
- `0x18000521c`
- `0x180006af0`
- `0x180007430`
- `0x180007f00`
- `0x1800082b0`
- `0x180008c24`
- `0x180008efc`
- `0x1800099d4`

## callees

- `0x180001240`

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
0x18000124c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

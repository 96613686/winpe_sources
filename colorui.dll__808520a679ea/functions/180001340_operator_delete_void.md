# operator delete[](void *)

- ea: `0x180001340`
- end: `0x180001345`
- name: `??_V@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `15`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003ff0`
- `0x180004ab8`
- `0x180010780`
- `0x180011050`
- `0x180011514`
- `0x1800116f8`
- `0x180011fb4`
- `0x180012840`
- `0x180013b34`
- `0x180013b7c`
- `0x180013c00`
- `0x1800144e8`
- `0x18001561c`
- `0x180016060`
- `0x1800168b8`

## callees

- `0x180001334`

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
0x180001340  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

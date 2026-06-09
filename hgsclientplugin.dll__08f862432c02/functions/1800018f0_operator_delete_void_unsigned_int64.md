# operator delete(void *,unsigned __int64)

- ea: `0x1800018f0`
- end: `0x1800018f5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `13`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002dc0`
- `0x180002e00`
- `0x180006260`
- `0x1800062ec`
- `0x180006388`
- `0x18000642c`
- `0x180006c04`
- `0x1800076ec`
- `0x1800077b8`
- `0x1800085d0`
- `0x1800085ec`
- `0x1800088cc`
- `0x180008a90`

## callees

- `0x180001e1c`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x1800018f0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

# operator delete(void *,unsigned __int64)

- ea: `0x180001564`
- end: `0x180001569`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `36`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002e54`
- `0x1800034d8`
- `0x180003648`
- `0x1800036b4`
- `0x180003750`
- `0x180003930`
- `0x1800039e0`
- `0x180003a20`
- `0x18000668c`
- `0x1800075f0`
- `0x180007dc0`
- `0x180007e20`
- `0x180007e88`
- `0x1800081d8`
- `0x180008248`
- `0x1800082b8`
- `0x180008414`
- `0x180008540`
- `0x18000a904`
- `0x18000ab80`
- `0x18000acb0`
- `0x18000adf0`
- `0x18000b140`
- `0x18000b164`
- `0x18000b1e0`
- `0x18000b24c`
- `0x18000c894`
- `0x18000ce80`
- `0x18000cee0`
- `0x18000da00`
- `0x18000e04c`
- `0x18000e070`
- `0x18000ff0c`
- `0x180010ce0`
- `0x180011014`
- `0x1800111f8`

## callees

- `0x180001960`

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
0x180001564  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

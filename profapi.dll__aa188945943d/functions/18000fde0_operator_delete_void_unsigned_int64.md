# operator delete(void *,unsigned __int64)

- ea: `0x18000fde0`
- end: `0x18000fde5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000b8e0`
- `0x18000b920`
- `0x180010dc0`
- `0x180010e00`
- `0x180012940`
- `0x180012980`

## callees

- `0x18001028c`

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
0x18000fde0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

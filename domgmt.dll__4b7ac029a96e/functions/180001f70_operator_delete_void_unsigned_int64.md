# operator delete(void *,unsigned __int64)

- ea: `0x180001f70`
- end: `0x180001f75`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `27`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003d30`
- `0x180003d70`
- `0x18000773c`
- `0x180007834`
- `0x1800079a8`
- `0x180007ae8`
- `0x180007c50`
- `0x180007da4`
- `0x180007ec0`
- `0x180007ff8`
- `0x180008d20`
- `0x180008d88`
- `0x180008ef4`
- `0x1800094b0`
- `0x180009510`
- `0x180009540`
- `0x180009580`
- `0x1800095c0`
- `0x180009630`
- `0x180009660`
- `0x1800096b0`
- `0x18000b420`
- `0x18000b450`
- `0x18000b480`
- `0x18000c06c`
- `0x18000cc30`
- `0x18000daeb`

## callees

- `0x180001fac`

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
0x180001f70  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

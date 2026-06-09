# operator delete(void *,unsigned __int64)

- ea: `0x180001bd4`
- end: `0x180001bd9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `29`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000211c`
- `0x180002f50`
- `0x180002f9c`
- `0x18000303c`
- `0x1800031d0`
- `0x180004980`
- `0x180004ba4`
- `0x180004c20`
- `0x180004c60`
- `0x180004ca0`
- `0x180004ce0`
- `0x1800065c0`
- `0x18000b040`
- `0x18000f830`
- `0x1800140cc`
- `0x1800144e0`
- `0x180014510`
- `0x180014538`
- `0x180015120`
- `0x18001541c`
- `0x180015530`
- `0x180015560`
- `0x18001559c`
- `0x180017420`
- `0x180023efc`
- `0x180023f30`
- `0x180023f70`
- `0x180023fb0`
- `0x18002c4a8`

## callees

- `0x1800022d8`

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
0x180001bd4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

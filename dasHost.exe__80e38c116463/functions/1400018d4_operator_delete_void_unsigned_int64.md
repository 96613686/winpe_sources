# operator delete(void *,unsigned __int64)

- ea: `0x1400018d4`
- end: `0x1400018d9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `36`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400038d0`
- `0x140003910`
- `0x140003950`
- `0x140003990`
- `0x14000e650`
- `0x14000e950`
- `0x14000fe60`
- `0x140010470`
- `0x140010610`
- `0x1400106b4`
- `0x1400107b0`
- `0x140010928`
- `0x140011224`
- `0x1400119bc`
- `0x1400119e0`
- `0x140011a10`
- `0x140011ab0`
- `0x140011b6c`
- `0x140011ca0`
- `0x140012748`
- `0x140012c08`
- `0x1400138ac`
- `0x140013d70`
- `0x140013da0`
- `0x140014fd8`
- `0x140016c20`
- `0x140017710`
- `0x140018220`
- `0x140018400`
- `0x1400185a0`
- `0x140018ac0`
- `0x140018ef0`
- `0x1400190f0`
- `0x1400191ec`
- `0x1400197f0`
- `0x14001b2b0`

## callees

- `0x140001ec0`

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
0x1400018d4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

# operator delete(void *,unsigned __int64)

- ea: `0x1800053f0`
- end: `0x1800053f5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `13`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004070`
- `0x1800040f0`
- `0x180004120`
- `0x180004270`
- `0x1800067d0`
- `0x180006810`
- `0x180009ae0`
- `0x180009b20`
- `0x180009b60`
- `0x180009b90`
- `0x180009be0`
- `0x18000a490`
- `0x18000a9b2`

## callees

- `0x18000542c`

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
0x1800053f0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

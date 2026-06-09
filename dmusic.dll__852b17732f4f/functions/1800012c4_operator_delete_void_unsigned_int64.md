# operator delete(void *,unsigned __int64)

- ea: `0x1800012c4`
- end: `0x1800012c9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `120`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001c34`
- `0x1800039c0`
- `0x180003a00`
- `0x180003a40`
- `0x180003a80`
- `0x180009790`
- `0x180009814`
- `0x180009b30`
- `0x18000a0ac`
- `0x18000a4c0`
- `0x18000a56c`
- `0x18000a5b8`
- `0x18000a6d0`
- `0x18000a70c`
- `0x18000b000`
- `0x18000b0e0`
- `0x18000b274`
- `0x18000b918`
- `0x18000ba24`
- `0x18000bd1c`
- `0x18000bf60`
- `0x18000c5f8`
- `0x18000cc10`
- `0x18000cd90`
- `0x18000cf7c`
- `0x18000d0e0`
- `0x18000d1e0`
- `0x18000d3d0`
- `0x18000d410`
- `0x18000d840`
- `0x18000db7c`
- `0x18000dbf0`
- `0x18000dcc0`
- `0x18000de74`
- `0x18000df64`
- `0x18000e098`
- `0x18000e178`
- `0x18000ebdc`
- `0x18000ec80`
- `0x18000ef40`
- `0x18000f260`
- `0x18000f308`
- `0x18000f340`
- `0x18000f470`
- `0x18000f5d0`
- `0x18000f6a4`
- `0x18000febc`
- `0x1800105f8`
- `0x180010798`
- `0x180010840`

## callees

- `0x180016220`

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
0x1800012c4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

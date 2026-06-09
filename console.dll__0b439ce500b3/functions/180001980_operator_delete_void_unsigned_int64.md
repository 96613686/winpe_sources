# operator delete(void *,unsigned __int64)

- ea: `0x180001980`
- end: `0x180001985`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `13`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003cf0`
- `0x180003d30`
- `0x180006900`
- `0x18000811c`
- `0x180008c34`
- `0x18000d918`
- `0x1800132b4`
- `0x180013310`
- `0x180013340`
- `0x180013370`
- `0x180015260`
- `0x1800152b0`
- `0x1800187a0`

## callees

- `0x1800019e0`

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
0x180001980  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

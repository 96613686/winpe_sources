# operator delete(void *,unsigned __int64)

- ea: `0x18000cba0`
- end: `0x18000cba5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180012560`
- `0x1800125a0`
- `0x1800125e0`
- `0x180012620`

## callees

- `0x18000cf84`

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
0x18000cba0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

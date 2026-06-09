# operator delete(void *,std::nothrow_t const &)

- ea: `0x180001944`
- end: `0x180001949`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `27`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003bc4`
- `0x180003c74`
- `0x180003dfc`
- `0x180003e68`
- `0x180005540`
- `0x180005788`
- `0x18000639c`
- `0x180007030`
- `0x180007100`
- `0x1800071d0`
- `0x1800072b0`
- `0x180007350`
- `0x180007400`
- `0x1800079d0`
- `0x180007d00`
- `0x180008730`
- `0x180008850`
- `0x180008a90`
- `0x180008c90`
- `0x180009270`
- `0x1800095a0`
- `0x180009ec0`
- `0x180009ef0`
- `0x18000af70`
- `0x18000cec0`
- `0x18000d010`
- `0x18000d260`

## callees

- `0x180001950`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block, const struct std::nothrow_t *a2)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180001944  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

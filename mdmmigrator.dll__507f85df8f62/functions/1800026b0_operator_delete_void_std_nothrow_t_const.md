# operator delete(void *,std::nothrow_t const &)

- ea: `0x1800026b0`
- end: `0x1800026b5`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `41`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004620`
- `0x180004660`
- `0x18000763c`
- `0x1800076a4`
- `0x180007720`
- `0x180007c94`
- `0x180007dd4`
- `0x180008160`
- `0x180008184`
- `0x18000820c`
- `0x180009cb4`
- `0x180009e34`
- `0x180009ed0`
- `0x18000ab84`
- `0x18000c634`
- `0x18000c69c`
- `0x18000cf04`
- `0x18000d1b0`
- `0x18000d2a8`
- `0x18000d3c4`
- `0x18000d8c0`
- `0x18000d9d0`
- `0x18000d9ec`
- `0x18000dbbc`
- `0x18000ddc0`
- `0x18000ddfc`
- `0x18000de8c`
- `0x18000ee18`
- `0x18000f004`
- `0x180010170`
- `0x180010610`
- `0x180010864`
- `0x1800110d0`
- `0x180011890`
- `0x1800121e0`
- `0x180012220`
- `0x180012ed4`
- `0x180016ca8`
- `0x18001ce54`
- `0x18001e478`
- `0x18001f43c`

## callees

- `0x180002b5c`

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
0x1800026b0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

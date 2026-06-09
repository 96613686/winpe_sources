# operator delete(void *,std::nothrow_t const &)

- ea: `0x1800024d0`
- end: `0x1800024d5`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `14`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800039b0`
- `0x1800039f0`
- `0x180006af0`
- `0x180007018`
- `0x180007268`
- `0x1800072a0`
- `0x180008380`
- `0x1800083f0`
- `0x180008430`
- `0x180008464`
- `0x18000907c`
- `0x180009121`
- `0x18000963a`
- `0x1800096d1`

## callees

- `0x1800029ac`

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
0x1800024d0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

# operator delete(void *,std::nothrow_t const &)

- ea: `0x180001a00`
- end: `0x180001a05`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `10`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003970`
- `0x1800039b0`
- `0x180009d20`
- `0x180009d50`
- `0x18000a0fc`
- `0x18000af04`
- `0x18000bd80`
- `0x18000c354`
- `0x18000c468`
- `0x18000c598`

## callees

- `0x180001e7c`

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
0x180001a00  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

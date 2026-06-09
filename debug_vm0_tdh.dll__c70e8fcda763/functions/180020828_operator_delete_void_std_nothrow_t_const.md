# operator delete(void *,std::nothrow_t const &)

- ea: `0x180020828`
- end: `0x18002082d`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `35`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001084`
- `0x180001f40`
- `0x1800123c4`
- `0x18001443c`
- `0x180018a3c`
- `0x18001d570`
- `0x18001d5c8`
- `0x18001ff4c`
- `0x18002027c`
- `0x18002088c`
- `0x180023e90`
- `0x180025510`
- `0x180026164`
- `0x180029948`
- `0x1800299c0`
- `0x180032b8c`
- `0x180032bbc`
- `0x180032bec`
- `0x180032c1c`
- `0x180032c4c`
- `0x180032c7c`
- `0x180032cac`
- `0x180032cf8`
- `0x180032d28`
- `0x180033e68`
- `0x180033f30`
- `0x18003ad30`
- `0x18003ad90`
- `0x18003eab8`
- `0x18003eae4`
- `0x18003edd8`
- `0x18003f4ec`
- `0x18004b770`
- `0x18004b7a0`
- `0x18004b7d0`

## callees

- `0x180021268`

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
0x180020828  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

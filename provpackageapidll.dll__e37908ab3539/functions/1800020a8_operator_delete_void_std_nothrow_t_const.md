# operator delete(void *,std::nothrow_t const &)

- ea: `0x1800020a8`
- end: `0x1800020ad`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `70`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002fe0`
- `0x180003020`
- `0x180005fec`
- `0x180006014`
- `0x1800060e4`
- `0x1800062e4`
- `0x180006308`
- `0x18000637c`
- `0x1800063e8`
- `0x1800064ec`
- `0x180006518`
- `0x1800068b8`
- `0x1800078e8`
- `0x180007f78`
- `0x1800088dc`
- `0x180008b70`
- `0x18000907c`
- `0x180009664`
- `0x180009740`
- `0x180009b00`
- `0x180009b30`
- `0x180009c30`
- `0x180009d40`
- `0x180009e40`
- `0x180009f40`
- `0x18000a040`
- `0x18000a1e0`
- `0x18000a2e0`
- `0x18000a3c0`
- `0x18000a5b0`
- `0x18000b7b0`
- `0x18000cf60`
- `0x18000cf70`
- `0x18000d0c4`
- `0x18000d350`
- `0x18000d708`
- `0x18000da30`
- `0x18000da5c`
- `0x18000e4b0`
- `0x18000e948`
- `0x180010154`
- `0x1800103f0`
- `0x180010414`
- `0x180012444`
- `0x180013080`
- `0x1800147fc`
- `0x180014870`
- `0x180014c70`
- `0x180014f8c`
- `0x180015530`

## callees

- `0x180002154`

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
0x1800020a8  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

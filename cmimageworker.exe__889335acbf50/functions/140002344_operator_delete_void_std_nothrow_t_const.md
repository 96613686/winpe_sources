# operator delete(void *,std::nothrow_t const &)

- ea: `0x140002344`
- end: `0x140002349`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `95`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140003b30`
- `0x140004020`
- `0x140004060`
- `0x1400040d0`
- `0x140004140`
- `0x1400046d4`
- `0x140006188`
- `0x140008f90`
- `0x140009010`
- `0x1400094c8`
- `0x14000a544`
- `0x14000a7a4`
- `0x14000aa8c`
- `0x14000ad64`
- `0x14000ae14`
- `0x14000b2ec`
- `0x14000bc44`
- `0x14000bd50`
- `0x14000bebc`
- `0x14000c064`
- `0x14000c18c`
- `0x14000c44c`
- `0x14000c868`
- `0x14000c948`
- `0x14000cbb8`
- `0x14000cd84`
- `0x14000ce58`
- `0x14000d1d4`
- `0x14000d2b8`
- `0x14000d81c`
- `0x14000d9bc`
- `0x14000db70`
- `0x14000de24`
- `0x140010274`
- `0x140010448`
- `0x140010724`
- `0x1400108f8`
- `0x140010c74`
- `0x140010e48`
- `0x1400111d0`
- `0x140011e40`
- `0x140011f60`
- `0x140012e48`
- `0x1400135c0`
- `0x1400140a0`
- `0x140014138`
- `0x140014234`
- `0x140014350`
- `0x140014490`
- `0x1400145d0`

## callees

- `0x140002920`

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
0x140002344  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

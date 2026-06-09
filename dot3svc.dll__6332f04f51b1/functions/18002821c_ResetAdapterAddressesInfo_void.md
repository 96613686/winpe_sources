# ResetAdapterAddressesInfo(void)

- ea: `0x18002821c`
- end: `0x180028284`
- name: `?ResetAdapterAddressesInfo@@YAXXZ`
- size: `104`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002807c`
- `0x1800280e0`

## callees

- `0x18002821c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002824d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002824d`
- `MobileNetworking!AcquireWriteLock` at `0x18002823b`
- `MobileNetworking!AcquireWriteLock` at `0x18002823b`
- `MobileNetworking!ReleaseWriteLock` at `0x18002827d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void ResetAdapterAddressesInfo(void)
{
  AcquireWriteLock(&Block, qword_180052DF0, "ResetAdapterAddressesInfo", 19);
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  ReleaseWriteLock(&Block, qword_180052DF0, "ResetAdapterAddressesInfo", 27);
}

```

## disassembly

```asm
0x18002821c  sub     rsp, 28h
0x180028220  mov     r9d, 13h
0x180028226  lea     r8, aResetadapterad; "ResetAdapterAddressesInfo"
0x18002822d  lea     rdx, qword_180052DF0
0x180028234  lea     rcx, Block
0x18002823b  call    cs:__imp_AcquireWriteLock
0x180028241  mov     rcx, cs:Block; Block
0x180028248  test    rcx, rcx
0x18002824b  jz      short loc_18002825E
0x18002824d  call    cs:__imp_free
0x180028253  mov     cs:Block, 0
0x18002825e  mov     r9d, 1Bh
0x180028264  lea     r8, aResetadapterad; "ResetAdapterAddressesInfo"
0x18002826b  lea     rdx, qword_180052DF0
0x180028272  lea     rcx, Block
0x180028279  add     rsp, 28h
0x18002827d  jmp     cs:__imp_ReleaseWriteLock
```

# operator new(unsigned __int64)

- ea: `0x180002fd4`
- end: `0x180003005`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `49`
- callee_count: `3`
- tags: ``

## callers

- `0x18000300c`
- `0x180003024`
- `0x1800030e8`
- `0x180003648`
- `0x1800037f0`
- `0x180005110`
- `0x180007b80`
- `0x180008f00`
- `0x180009ed8`
- `0x18000ef54`
- `0x18000f9f8`
- `0x18000faa8`
- `0x180023194`
- `0x1800245fc`
- `0x180028ee8`
- `0x1800293a8`
- `0x180029550`
- `0x18002a4e0`
- `0x18002a6fc`
- `0x18002ad68`
- `0x18002bc70`
- `0x18002bda8`
- `0x18002be70`
- `0x18002bf20`
- `0x18002bfbc`
- `0x18002c2f4`
- `0x18002c3b4`
- `0x18002c5a4`
- `0x18002cc54`
- `0x18002cde8`
- `0x18002ced4`
- `0x18002d0d4`
- `0x18002d15c`
- `0x18002dcd4`
- `0x18002de68`
- `0x18002ebe0`
- `0x18002ecbc`
- `0x18002f038`
- `0x18002fc54`
- `0x18002ff6c`
- `0x180030014`
- `0x180030638`
- `0x1800318b8`
- `0x1800322c0`
- `0x180032b70`
- `0x180033334`
- `0x180034928`
- `0x180035ceb`
- `0x1800361fd`

## callees

- `0x180002891`
- `0x180002fd4`
- `0x180003125`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180002ffe`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180002ffe`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax

  for ( i = Size; ; Size = i )
  {
    result = malloc_0(Size);
    if ( result )
      break;
    if ( !callnewh_0(i) )
    {
      std::_Xbad_alloc();
      JUMPOUT(0x180003004LL);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002fd4  push    rbx
0x180002fd6  sub     rsp, 20h
0x180002fda  mov     rbx, rcx
0x180002fdd  jmp     short loc_180002FEE
0x180002fdf  mov     rcx, rbx; Size
0x180002fe2  call    _callnewh_0
0x180002fe7  test    eax, eax
0x180002fe9  jz      short loc_180002FFE
0x180002feb  mov     rcx, rbx; Size
0x180002fee  call    malloc_0
0x180002ff3  test    rax, rax
0x180002ff6  jz      short loc_180002FDF
0x180002ff8  add     rsp, 20h
0x180002ffc  pop     rbx
0x180002ffd  retn
0x180002ffe  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```

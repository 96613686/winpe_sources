# operator new(unsigned __int64)

- ea: `0x1800011dc`
- end: `0x18000120d`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x1800011d0`
- `0x1800013b8`
- `0x1800063dc`
- `0x1800065e0`
- `0x18000837c`
- `0x180009b6c`
- `0x18000aafc`
- `0x18000e023`

## callees

- `0x1800011dc`
- `0x180001518`
- `0x18000260a`

## import_xrefs

- `msvcrt!malloc` at `0x1800011f6`
- `msvcrt!malloc` at `0x1800011f6`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax

  for ( i = Size; ; Size = i )
  {
    result = malloc(Size);
    if ( result )
      break;
    if ( !callnewh_0(i) )
      std::_Xbad_alloc();
  }
  return result;
}

```

## disassembly

```asm
0x1800011dc  push    rbx
0x1800011de  sub     rsp, 20h
0x1800011e2  mov     rbx, rcx
0x1800011e5  jmp     short loc_1800011F6
0x1800011e7  mov     rcx, rbx; Size
0x1800011ea  call    _callnewh_0
0x1800011ef  test    eax, eax
0x1800011f1  jz      short loc_180001207
0x1800011f3  mov     rcx, rbx; Size
0x1800011f6  call    cs:__imp_malloc
0x1800011fc  test    rax, rax
0x1800011ff  jz      short loc_1800011E7
0x180001201  add     rsp, 20h
0x180001205  pop     rbx
0x180001206  retn
0x180001207  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```

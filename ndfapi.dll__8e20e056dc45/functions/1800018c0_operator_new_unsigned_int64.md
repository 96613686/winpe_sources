# operator new(unsigned __int64)

- ea: `0x1800018c0`
- end: `0x1800018f1`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `25`
- callee_count: `3`
- tags: ``

## callers

- `0x1800018b4`
- `0x18000264c`
- `0x180006f9c`
- `0x180009d2c`
- `0x180009d6c`
- `0x18000fca8`
- `0x180011810`
- `0x180011fb8`
- `0x180012114`
- `0x180012260`
- `0x180012384`
- `0x1800124a4`
- `0x1800125e4`
- `0x180012704`
- `0x18001281c`
- `0x18001295c`
- `0x180012a78`
- `0x180012b70`
- `0x180012cc0`
- `0x180015aac`
- `0x18001adf8`
- `0x18001ae44`
- `0x18001d5d0`
- `0x18001fca3`
- `0x180020700`

## callees

- `0x1800018c0`
- `0x180001ac8`
- `0x18000267f`

## import_xrefs

- `msvcrt!malloc` at `0x1800018da`
- `msvcrt!malloc` at `0x1800018da`

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
0x1800018c0  push    rbx
0x1800018c2  sub     rsp, 20h
0x1800018c6  mov     rbx, rcx
0x1800018c9  jmp     short loc_1800018DA
0x1800018cb  mov     rcx, rbx; Size
0x1800018ce  call    _callnewh_0
0x1800018d3  test    eax, eax
0x1800018d5  jz      short loc_1800018EB
0x1800018d7  mov     rcx, rbx; Size
0x1800018da  call    cs:__imp_malloc
0x1800018e0  test    rax, rax
0x1800018e3  jz      short loc_1800018CB
0x1800018e5  add     rsp, 20h
0x1800018e9  pop     rbx
0x1800018ea  retn
0x1800018eb  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```

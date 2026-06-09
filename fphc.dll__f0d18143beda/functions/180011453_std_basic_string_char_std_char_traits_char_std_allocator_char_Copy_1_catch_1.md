# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x180011453`
- end: `0x180011497`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001250`
- `0x180001428`
- `0x180001588`
- `0x180011453`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  void *v4; // rax
  size_t v5; // rcx

  v3 = *(_QWORD *)(a2 + 104);
  *(_QWORD *)(a2 + 104) = v3;
  v4 = 0;
  v5 = v3 + 1;
  if ( v5 )
  {
    v4 = operator new(v5);
    if ( !v4 )
      std::_Xbad_alloc();
  }
  *(_QWORD *)(a2 + 120) = v4;
  return &loc_1800014B1;
}

```

## disassembly

```asm
0x180011453  mov     [rsp+arg_8], rdx
0x180011458  push    rbp
0x180011459  sub     rsp, 20h
0x18001145d  mov     rbp, rdx
0x180011460  mov     rcx, [rbp+68h]
0x180011464  mov     [rbp+68h], rcx
0x180011468  xor     eax, eax
0x18001146a  add     rcx, 1; Size
0x18001146e  jz      short loc_180011485
0x180011470  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180011474  ja      short loc_180011480
0x180011476  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001147b  test    rax, rax
0x18001147e  jnz     short loc_180011485
0x180011480  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180011485  mov     [rbp+78h], rax
0x180011489  lea     rax, loc_1800014B1
0x180011490  add     rsp, 20h
0x180011494  pop     rbp
0x180011495  retn
```

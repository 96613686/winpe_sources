# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x180019303`
- end: `0x180019347`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001524`
- `0x1800016f8`
- `0x180001858`
- `0x180019303`

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
  return &loc_180001781;
}

```

## disassembly

```asm
0x180019303  mov     [rsp+arg_8], rdx
0x180019308  push    rbp
0x180019309  sub     rsp, 20h
0x18001930d  mov     rbp, rdx
0x180019310  mov     rcx, [rbp+68h]
0x180019314  mov     [rbp+68h], rcx
0x180019318  xor     eax, eax
0x18001931a  add     rcx, 1; Size
0x18001931e  jz      short loc_180019335
0x180019320  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180019324  ja      short loc_180019330
0x180019326  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001932b  test    rax, rax
0x18001932e  jnz     short loc_180019335
0x180019330  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180019335  mov     [rbp+78h], rax
0x180019339  lea     rax, loc_180001781
0x180019340  add     rsp, 20h
0x180019344  pop     rbp
0x180019345  retn
```

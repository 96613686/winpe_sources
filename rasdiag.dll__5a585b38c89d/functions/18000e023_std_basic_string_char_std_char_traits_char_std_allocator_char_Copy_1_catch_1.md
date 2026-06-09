# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x18000e023`
- end: `0x18000e067`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `68`
- prototype: `void *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800011dc`
- `0x1800013b8`
- `0x180001518`
- `0x18000e023`

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
  return &loc_180001441;
}

```

## disassembly

```asm
0x18000e023  mov     [rsp+arg_8], rdx
0x18000e028  push    rbp
0x18000e029  sub     rsp, 20h
0x18000e02d  mov     rbp, rdx
0x18000e030  mov     rcx, [rbp+68h]
0x18000e034  mov     [rbp+68h], rcx
0x18000e038  xor     eax, eax
0x18000e03a  add     rcx, 1; Size
0x18000e03e  jz      short loc_18000E055
0x18000e040  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000e044  ja      short loc_18000E050
0x18000e046  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e04b  test    rax, rax
0x18000e04e  jnz     short loc_18000E055
0x18000e050  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000e055  mov     [rbp+78h], rax
0x18000e059  lea     rax, loc_180001441
0x18000e060  add     rsp, 20h
0x18000e064  pop     rbp
0x18000e065  retn
```

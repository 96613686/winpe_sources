# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x180008810`
- end: `0x180008854`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `68`
- prototype: `void *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001064`
- `0x180001238`
- `0x180001398`
- `0x180008810`

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
  return &loc_1800012C1;
}

```

## disassembly

```asm
0x180008810  mov     [rsp+arg_8], rdx
0x180008815  push    rbp
0x180008816  sub     rsp, 20h
0x18000881a  mov     rbp, rdx
0x18000881d  mov     rcx, [rbp+68h]
0x180008821  mov     [rbp+68h], rcx
0x180008825  xor     eax, eax
0x180008827  add     rcx, 1; Size
0x18000882b  jz      short loc_180008842
0x18000882d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180008831  ja      short loc_18000883D
0x180008833  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008838  test    rax, rax
0x18000883b  jnz     short loc_180008842
0x18000883d  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180008842  mov     [rbp+78h], rax
0x180008846  lea     rax, loc_1800012C1
0x18000884d  add     rsp, 20h
0x180008851  pop     rbp
0x180008852  retn
```

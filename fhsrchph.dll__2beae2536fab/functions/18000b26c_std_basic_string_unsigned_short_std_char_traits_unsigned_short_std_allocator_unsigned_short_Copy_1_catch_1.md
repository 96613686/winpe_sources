# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x18000b26c`
- end: `0x18000b2dc`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `112`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800011c4`
- `0x180001d04`
- `0x180002f58`
- `0x18000b26c`

## pseudocode

```c
__int64 __fastcall std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  void *v4; // rax
  unsigned __int64 v5; // rcx

  v3 = *(_QWORD *)(a2 + 152);
  *(_QWORD *)(a2 + 152) = v3;
  v4 = 0;
  v5 = v3 + 1;
  if ( v5 )
  {
    if ( v5 > 0x7FFFFFFFFFFFFFFFLL || (v4 = operator new(2 * v5)) == 0 )
    {
      std::bad_alloc::bad_alloc((std::bad_alloc *)(a2 + 56), (const char *)a2);
      throw (std::bad_alloc *)(a2 + 56);
    }
  }
  *(_QWORD *)(a2 + 168) = v4;
  return 0;
}

```

## disassembly

```asm
0x18000b26c  mov     [rsp+arg_8], rdx
0x18000b271  push    rbp
0x18000b272  sub     rsp, 20h
0x18000b276  mov     rbp, rdx
0x18000b279  mov     rcx, [rbp+98h]
0x18000b280  mov     [rbp+98h], rcx
0x18000b287  xor     eax, eax
0x18000b289  add     rcx, 1
0x18000b28d  jz      short loc_18000B2C4
0x18000b28f  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000b299  cmp     rcx, rax
0x18000b29c  ja      short loc_18000B2AB
0x18000b29e  add     rcx, rcx; Size
0x18000b2a1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b2a6  test    rax, rax
0x18000b2a9  jnz     short loc_18000B2C4
0x18000b2ab  lea     rcx, [rbp+38h]; this
0x18000b2af  call    ??0bad_alloc@std@@QEAA@PEBD@Z; std::bad_alloc::bad_alloc(char const *)
0x18000b2b4  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000b2bb  lea     rcx, [rbp+38h]; pExceptionObject
0x18000b2bf  call    _CxxThrowException_0
0x18000b2c4  mov     [rbp+0A8h], rax
0x18000b2cb  mov     rax, 0
0x18000b2d5  add     rsp, 20h
0x18000b2d9  pop     rbp
0x18000b2da  retn
```

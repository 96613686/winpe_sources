# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x180009fd8`
- end: `0x18000a048`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `112`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800011d8`
- `0x180001d18`
- `0x180006950`
- `0x180009fd8`

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
0x180009fd8  mov     [rsp+arg_8], rdx
0x180009fdd  push    rbp
0x180009fde  sub     rsp, 20h
0x180009fe2  mov     rbp, rdx
0x180009fe5  mov     rcx, [rbp+98h]
0x180009fec  mov     [rbp+98h], rcx
0x180009ff3  xor     eax, eax
0x180009ff5  add     rcx, 1
0x180009ff9  jz      short loc_18000A030
0x180009ffb  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000a005  cmp     rcx, rax
0x18000a008  ja      short loc_18000A017
0x18000a00a  add     rcx, rcx; Size
0x18000a00d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a012  test    rax, rax
0x18000a015  jnz     short loc_18000A030
0x18000a017  lea     rcx, [rbp+38h]; this
0x18000a01b  call    ??0bad_alloc@std@@QEAA@PEBD@Z; std::bad_alloc::bad_alloc(char const *)
0x18000a020  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000a027  lea     rcx, [rbp+38h]; pExceptionObject
0x18000a02b  call    _CxxThrowException_0
0x18000a030  mov     [rbp+0A8h], rax
0x18000a037  mov     rax, 0
0x18000a041  add     rsp, 20h
0x18000a045  pop     rbp
0x18000a046  retn
```

# std::_Fmt_write<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,bool,std::_Basic_format_specs<ushort>,std::_Lazy_locale)

- ea: `0x140017cc8`
- end: `0x140017ebf`
- name: `??$_Fmt_write@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@_NU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z`
- size: `503`
- prototype: `__int64 __fastcall(__int64, __int64, char, __int128 *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14001af1c`

## callees

- `0x140002f60`
- `0x140013df8`
- `0x140017c0c`
- `0x140017cc8`
- `0x14001bac8`
- `0x14001e5e8`
- `0x14003e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x140017d6c`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x140017d6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall std::_Fmt_write<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
        __int64 a1,
        __int64 a2,
        char a3,
        __int128 *a4,
        __int64 a5)
{
  char v8; // al
  struct std::locale::_Locimp *v9; // rdi
  void (__fastcall ***v10)(_QWORD, __int64); // r8
  __int64 *v11; // r12
  void (__fastcall ***v12)(_QWORD, __int64); // rax
  __int64 v13; // rax
  int v14; // edi
  _QWORD *v15; // rax
  __int64 v16; // rax
  _QWORD *v17; // rax
  const wchar_t *v18; // rcx
  __int64 v19; // rax
  __int128 v21; // [rsp+30h] [rbp-51h] BYREF
  int v22; // [rsp+40h] [rbp-41h]
  int v23; // [rsp+50h] [rbp-31h]
  _QWORD v24[4]; // [rsp+58h] [rbp-29h] BYREF
  _QWORD v25[4]; // [rsp+78h] [rbp-9h] BYREF

  v23 = 0;
  v8 = *((_BYTE *)a4 + 8);
  if ( !v8 || v8 == 115 )
  {
    if ( *((_BYTE *)a4 + 12) )
    {
      *((_BYTE *)a4 + 12) = 0;
      if ( a5 )
      {
        v9 = *(struct std::locale::_Locimp **)(a5 + 8);
        *((_QWORD *)&v21 + 1) = v9;
        (*(void (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v9 + 8LL))(v9);
      }
      else
      {
        v9 = std::locale::_Init(1);
        *((_QWORD *)&v21 + 1) = v9;
      }
      v11 = (__int64 *)std::use_facet<std::numpunct<unsigned short>>(&v21);
      if ( v9 )
      {
        v12 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v9 + 16LL))(v9);
        v10 = v12;
        if ( v12 )
          (**v12)(v12, 1);
      }
      v13 = *v11;
      if ( a3 )
      {
        (*(void (__fastcall **)(__int64 *, _QWORD *, void (__fastcall ***)(_QWORD, __int64)))(v13 + 56))(v11, v25, v10);
        v14 = 5;
        v15 = v25;
        if ( v25[3] > 7u )
          v15 = (_QWORD *)v25[0];
        *(_QWORD *)&v21 = v15;
        v16 = v25[2];
      }
      else
      {
        (*(void (__fastcall **)(__int64 *, _QWORD *, void (__fastcall ***)(_QWORD, __int64)))(v13 + 48))(v11, v24, v10);
        v14 = 10;
        v17 = v24;
        if ( v24[3] > 7u )
          v17 = (_QWORD *)v24[0];
        *(_QWORD *)&v21 = v17;
        v16 = v24[2];
      }
      *((_QWORD *)&v21 + 1) = v16;
      v23 = v14;
      std::_Fmt_write<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(a1, a2, &v21);
      if ( (v14 & 2) != 0 )
      {
        LOBYTE(v14) = v14 & 0xFD;
        std::wstring::_Tidy_deallocate(v24);
      }
      if ( (v14 & 1) != 0 )
        std::wstring::_Tidy_deallocate(v25);
    }
    else
    {
      v18 = L"true";
      if ( !a3 )
        v18 = L"false";
      v19 = -1;
      do
        ++v19;
      while ( v18[v19] );
      *(_QWORD *)&v21 = v18;
      *((_QWORD *)&v21 + 1) = v19;
      std::_Fmt_write<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(a1, a2, &v21);
    }
  }
  else
  {
    v21 = *a4;
    v22 = *((_DWORD *)a4 + 4);
    std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,unsigned char>(
      a1,
      a2,
      a3,
      (unsigned int)&v21,
      a5);
  }
  return a1;
}

```

## disassembly

```asm
0x140017cc8  mov     [rsp-8+arg_8], rbx
0x140017ccd  push    rbp
0x140017cce  push    rsi
0x140017ccf  push    rdi
0x140017cd0  push    r12
0x140017cd2  push    r13
0x140017cd4  push    r14
0x140017cd6  push    r15
0x140017cd8  lea     rbp, [rsp-1Fh]
0x140017cdd  sub     rsp, 0A0h
0x140017ce4  mov     rax, cs:__security_cookie
0x140017ceb  xor     rax, rsp
0x140017cee  mov     [rbp+4Fh+var_38], rax
0x140017cf2  mov     rsi, r9
0x140017cf5  mov     r15b, r8b
0x140017cf8  mov     rbx, rdx
0x140017cfb  mov     r14, rcx
0x140017cfe  xor     r13d, r13d
0x140017d01  mov     [rbp+4Fh+var_80], r13d
0x140017d05  mov     al, [r9+8]
0x140017d09  test    al, al
0x140017d0b  jz      short loc_140017D3A
0x140017d0d  cmp     al, 73h ; 's'
0x140017d0f  jz      short loc_140017D3A
0x140017d11  movaps  xmm0, xmmword ptr [r9]
0x140017d15  movaps  [rbp+4Fh+var_A0], xmm0
0x140017d19  mov     ecx, [r9+10h]
0x140017d1d  mov     [rbp+4Fh+var_90], ecx
0x140017d20  mov     rcx, [rbp+4Fh+arg_20]
0x140017d24  mov     [rsp+0D0h+var_B0], rcx
0x140017d29  lea     r9, [rbp+4Fh+var_A0]
0x140017d2d  mov     rcx, r14
0x140017d30  call    ??$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@E@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@EU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z; std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uchar,std::_Basic_format_specs<ushort>,std::_Lazy_locale)
0x140017d35  jmp     loc_140017E95
0x140017d3a  cmp     [r9+0Ch], r13b
0x140017d3e  jz      loc_140017E5E
0x140017d44  mov     [r9+0Ch], r13b
0x140017d48  mov     rax, [rbp+4Fh+arg_20]
0x140017d4c  test    rax, rax
0x140017d4f  jz      short loc_140017D6A
0x140017d51  mov     rdi, [rax+8]
0x140017d55  mov     qword ptr [rbp+4Fh+var_A0+8], rdi
0x140017d59  mov     rax, [rdi]
0x140017d5c  mov     rcx, rdi
0x140017d5f  mov     rax, [rax+8]
0x140017d63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017d68  jmp     short loc_140017D79
0x140017d6a  mov     cl, 1
0x140017d6c  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x140017d72  mov     rdi, rax
0x140017d75  mov     qword ptr [rbp+4Fh+var_A0+8], rax
0x140017d79  lea     rcx, [rbp+4Fh+var_A0]
0x140017d7d  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<ushort>>(std::locale const &)
0x140017d82  mov     r12, rax
0x140017d85  test    rdi, rdi
0x140017d88  jz      short loc_140017DB4
0x140017d8a  mov     rcx, [rdi]
0x140017d8d  mov     rax, [rcx+10h]
0x140017d91  mov     rcx, rdi
0x140017d94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017d99  mov     r8, rax
0x140017d9c  test    rax, rax
0x140017d9f  jz      short loc_140017DB4
0x140017da1  mov     rcx, [rax]
0x140017da4  mov     rax, [rcx]
0x140017da7  mov     edx, 1
0x140017dac  mov     rcx, r8
0x140017daf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017db4  mov     rax, [r12]
0x140017db8  mov     rcx, r12
0x140017dbb  test    r15b, r15b
0x140017dbe  jz      short loc_140017DEB
0x140017dc0  lea     rdx, [rbp+4Fh+var_58]
0x140017dc4  mov     rax, [rax+38h]
0x140017dc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017dcd  nop
0x140017dce  mov     edi, 5
0x140017dd3  lea     rax, [rbp+4Fh+var_58]
0x140017dd7  cmp     [rbp+4Fh+var_40], 7
0x140017ddc  cmova   rax, [rbp+4Fh+var_58]
0x140017de1  mov     qword ptr [rbp+4Fh+var_A0], rax
0x140017de5  mov     rax, [rbp+4Fh+var_48]
0x140017de9  jmp     short loc_140017E14
0x140017deb  lea     rdx, [rbp+4Fh+var_78]
0x140017def  mov     rax, [rax+30h]
0x140017df3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017df8  nop
0x140017df9  mov     edi, 0Ah
0x140017dfe  lea     rax, [rbp+4Fh+var_78]
0x140017e02  cmp     [rbp+4Fh+var_60], 7
0x140017e07  cmova   rax, [rbp+4Fh+var_78]
0x140017e0c  mov     qword ptr [rbp+4Fh+var_A0], rax
0x140017e10  mov     rax, [rbp+4Fh+var_68]
0x140017e14  mov     qword ptr [rbp+4Fh+var_A0+8], rax
0x140017e18  lea     rax, [rbp+4Fh+var_A0]
0x140017e1c  mov     [rbp+4Fh+var_80], edi
0x140017e1f  movups  xmm0, xmmword ptr [rax]
0x140017e22  movdqu  [rbp+4Fh+var_A0], xmm0
0x140017e27  mov     r9, rsi
0x140017e2a  lea     r8, [rbp+4Fh+var_A0]
0x140017e2e  mov     rdx, rbx
0x140017e31  mov     rcx, r14
0x140017e34  call    ??$_Fmt_write@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@V?$basic_string_view@GU?$char_traits@G@std@@@0@AEBU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z; std::_Fmt_write<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,std::basic_string_view<ushort>,std::_Basic_format_specs<ushort> const &,std::_Lazy_locale)
0x140017e39  nop
0x140017e3a  test    dil, 2
0x140017e3e  jz      short loc_140017E4D
0x140017e40  and     edi, 0FFFFFFFDh
0x140017e43  lea     rcx, [rbp+4Fh+var_78]
0x140017e47  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140017e4c  nop
0x140017e4d  test    dil, 1
0x140017e51  jz      short loc_140017E95
0x140017e53  lea     rcx, [rbp+4Fh+var_58]
0x140017e57  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140017e5c  jmp     short loc_140017E95
0x140017e5e  lea     rax, aFalse_0; "false"
0x140017e65  lea     rcx, aTrue; "true"
0x140017e6c  test    r15b, r15b
0x140017e6f  cmovz   rcx, rax
0x140017e73  or      rax, 0FFFFFFFFFFFFFFFFh
0x140017e77  inc     rax
0x140017e7a  cmp     [rcx+rax*2], r13w
0x140017e7f  jnz     short loc_140017E77
0x140017e81  mov     qword ptr [rbp+4Fh+var_A0], rcx
0x140017e85  mov     qword ptr [rbp+4Fh+var_A0+8], rax
0x140017e89  lea     r8, [rbp+4Fh+var_A0]
0x140017e8d  mov     rcx, r14
0x140017e90  call    ??$_Fmt_write@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@V?$basic_string_view@GU?$char_traits@G@std@@@0@AEBU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z; std::_Fmt_write<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,std::basic_string_view<ushort>,std::_Basic_format_specs<ushort> const &,std::_Lazy_locale)
0x140017e95  mov     rax, r14
0x140017e98  mov     rcx, [rbp+4Fh+var_38]
0x140017e9c  xor     rcx, rsp; StackCookie
0x140017e9f  call    __security_check_cookie
0x140017ea4  mov     rbx, [rsp+0D0h+arg_8]
0x140017eac  add     rsp, 0A0h
0x140017eb3  pop     r15
0x140017eb5  pop     r14
0x140017eb7  pop     r13
0x140017eb9  pop     r12
0x140017ebb  pop     rdi
0x140017ebc  pop     rsi
0x140017ebd  pop     rbp
0x140017ebe  retn
```

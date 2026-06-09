# std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uchar,std::_Basic_format_specs<ushort>,std::_Lazy_locale)

- ea: `0x14001bac8`
- end: `0x14001be7b`
- name: `??$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@E@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@EU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z`
- size: `947`
- prototype: `__int16 **__fastcall(__int16 **, __int16 *, unsigned __int8, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140017cc8`

## callees

- `0x140002f60`
- `0x140017b18`
- `0x14001b74c`
- `0x14001bac8`
- `0x14001e5e8`
- `0x14001f3c8`
- `0x140020bf0`
- `0x140022278`
- `0x14003e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14001bccc`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14001bccc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int16 **__fastcall std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,unsigned char>(
        __int16 **a1,
        __int16 *a2,
        unsigned __int8 a3,
        __int64 a4,
        __int64 a5)
{
  _BYTE *v5; // rsi
  char v8; // al
  int v9; // edi
  int v10; // eax
  _BYTE *v11; // r12
  int v12; // eax
  char v13; // r14
  _BYTE *v14; // rcx
  char v15; // cl
  const char *v16; // rcx
  struct std::locale::_Locimp *v17; // rdi
  __int64 v18; // rax
  void (__fastcall ***v19)(_QWORD, __int64); // rax
  char *v20; // rax
  int v21; // edx
  unsigned __int64 v22; // r8
  unsigned __int64 v23; // r9
  char *v24; // r11
  int v26; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v27; // [rsp+30h] [rbp-D0h] BYREF
  char v28; // [rsp+38h] [rbp-C8h] BYREF
  int v29; // [rsp+3Ch] [rbp-C4h] BYREF
  __int128 v30; // [rsp+40h] [rbp-C0h] BYREF
  int v31; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE *v32; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v33; // [rsp+60h] [rbp-A0h] BYREF
  int v34; // [rsp+70h] [rbp-90h]
  _QWORD v35[10]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v36; // [rsp+D0h] [rbp-30h] BYREF
  __m128i v37; // [rsp+E0h] [rbp-20h]
  __int128 v38; // [rsp+F0h] [rbp-10h] BYREF
  __m128i si128; // [rsp+100h] [rbp+0h]
  _BYTE v40[65]; // [rsp+110h] [rbp+10h] BYREF
  char v41[15]; // [rsp+151h] [rbp+51h] BYREF

  v5 = (_BYTE *)a4;
  v27 = a3;
  v8 = *(_BYTE *)(a4 + 8);
  if ( v8 == 99 )
  {
    *(_BYTE *)(a4 + 11) = 0;
    v33 = *(_OWORD *)a4;
    v34 = *(_DWORD *)(a4 + 16);
    std::_Fmt_write<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
      (__int64)a1,
      (__int64)a2,
      a3,
      &v33,
      a5);
    return a1;
  }
  v9 = 2;
  if ( !*(_BYTE *)(a4 + 10) )
    *(_BYTE *)(a4 + 10) = 2;
  if ( v8 != 66 )
  {
    if ( v8 == 88 )
    {
LABEL_12:
      v10 = 16;
      goto LABEL_14;
    }
    if ( v8 != 98 )
    {
      if ( v8 == 111 )
      {
        v10 = 8;
        goto LABEL_14;
      }
      if ( v8 != 120 )
      {
        v10 = 10;
        goto LABEL_14;
      }
      goto LABEL_12;
    }
  }
  v10 = 2;
LABEL_14:
  v26 = v10;
  LOBYTE(a4) = a3;
  v11 = *(_BYTE **)std::to_chars(&v33, v40, v41, a4);
  v32 = v40;
  v12 = (_DWORD)v11 - (unsigned int)v40;
  v29 = v12;
  if ( v5[10] != 2 )
    v29 = ++v12;
  v13 = 1;
  if ( v5[8] == 88 )
  {
    v14 = v40;
    if ( v40 != v11 )
    {
      do
      {
        if ( (unsigned __int8)(*v14 - 97) <= 0x19u )
          *v14 -= 32;
        ++v14;
      }
      while ( v14 != v11 );
      v12 = v29;
    }
  }
  v30 = 0u;
  if ( !v5[11] )
    goto LABEL_38;
  v15 = v5[8];
  switch ( v15 )
  {
    case 'B':
      v16 = "0B";
      goto LABEL_35;
    case 'X':
      v16 = "0X";
      goto LABEL_35;
    case 'b':
      v16 = "0b";
      goto LABEL_35;
    case 'o':
      if ( v27 )
      {
        v16 = "0";
        *((_QWORD *)&v30 + 1) = 1;
        v9 = 1;
LABEL_36:
        *(_QWORD *)&v30 = v16;
        goto LABEL_37;
      }
      break;
    case 'x':
      v16 = "0x";
LABEL_35:
      *((_QWORD *)&v30 + 1) = 2;
      goto LABEL_36;
  }
  v30 = 0u;
  v9 = 0;
LABEL_37:
  v12 += v9;
  v29 = v12;
LABEL_38:
  v31 = 0;
  v36 = 0;
  v37.m128i_i64[0] = 0;
  v37.m128i_i64[1] = 15;
  LOBYTE(v36) = 0;
  if ( v5[12] )
  {
    if ( a5 )
    {
      v17 = *(struct std::locale::_Locimp **)(a5 + 8);
      *((_QWORD *)&v33 + 1) = v17;
      (*(void (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v17 + 8LL))(v17);
    }
    else
    {
      v17 = std::locale::_Init(1);
      *((_QWORD *)&v33 + 1) = v17;
    }
    v18 = std::use_facet<std::numpunct<unsigned short>>(&v33);
    (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v18 + 40LL))(v18, &v38);
    std::string::_Tidy_deallocate(&v36);
    v36 = v38;
    v37 = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v38) = 0;
    std::string::_Tidy_deallocate(&v38);
    if ( v17 )
    {
      v19 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v17 + 16LL))(v17);
      if ( v19 )
        (**v19)(v19, 1);
    }
    v20 = (char *)&v36;
    if ( v37.m128i_i64[1] > 0xFuLL )
      v20 = (char *)v36;
    v21 = 0;
    if ( v37.m128i_i64[0] )
    {
      v22 = v11 - v32;
      v23 = *v20;
      if ( v11 - v32 > v23 )
      {
        v24 = &v20[v37.m128i_i64[0]];
        do
        {
          v22 -= (char)v23;
          ++v21;
          if ( v20 + 1 != v24 )
            ++v20;
          v23 = *v20;
        }
        while ( v22 > v23 );
      }
    }
    v31 = v21;
    v12 = v21 + v29;
    v29 += v21;
  }
  if ( !v5[13] || v5[9] )
    v13 = 0;
  v28 = v13;
  v35[0] = v11;
  v35[1] = v5;
  v35[2] = &v27;
  v35[3] = &v30;
  v35[4] = &v28;
  v35[5] = &v29;
  v35[6] = &v31;
  v35[7] = &v32;
  v35[8] = &v36;
  v35[9] = &a5;
  if ( v13 )
    `std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,unsigned __int64>'::`2'::_lambda_1_::operator()(
      v35,
      a1,
      a2);
  else
    ____Write_aligned_V__back_insert_iterator_V___Fmt_buffer_G_std___std__U___Basic_format_specs_G_2_AEAV_lambda_1___1_____Write_integral_GV__back_insert_iterator_V___Fmt_buffer_G_std___std__I_2_YA_AV12_V12_IU32_V_Lazy_locale_2__Z__std__YA_AV__back_insert_iterator_V___Fmt_buffer_G_std___0_V10_HAEBU___Basic_format_specs_G_0_W4_Fmt_align_0_AEAV_lambda_1___1_____Write_integral_GV__back_insert_iterator_V___Fmt_buffer_G_std___std__I_0_YA_AV10_0IU20_V_Lazy_locale_0__Z__Z(
      a1,
      a2,
      v12,
      (__int64)v5,
      v26,
      (__int64)v35);
  std::string::_Tidy_deallocate(&v36);
  return a1;
}

```

## disassembly

```asm
0x14001bac8  mov     [rsp-8+arg_8], rbx
0x14001bacd  push    rbp
0x14001bace  push    rsi
0x14001bacf  push    rdi
0x14001bad0  push    r12
0x14001bad2  push    r13
0x14001bad4  push    r14
0x14001bad6  push    r15
0x14001bad8  lea     rbp, [rsp-70h]
0x14001badd  sub     rsp, 170h
0x14001bae4  mov     rax, cs:__security_cookie
0x14001baeb  xor     rax, rsp
0x14001baee  mov     [rbp+0A0h+var_40], rax
0x14001baf2  mov     rsi, r9
0x14001baf5  mov     rbx, rdx
0x14001baf8  mov     r15, rcx
0x14001bafb  mov     [rsp+1A0h+var_170], r8b
0x14001bb00  xor     r13d, r13d
0x14001bb03  mov     al, [r9+8]
0x14001bb07  cmp     al, 63h ; 'c'
0x14001bb09  jnz     short loc_14001BB42
0x14001bb0b  mov     [r9+0Bh], r13b
0x14001bb0f  movaps  xmm0, xmmword ptr [r9]
0x14001bb13  movaps  [rsp+1A0h+var_140], xmm0
0x14001bb18  mov     ecx, [r9+10h]
0x14001bb1c  mov     [rsp+1A0h+var_130], ecx
0x14001bb20  movzx   r8d, r8b
0x14001bb24  mov     rcx, [rbp+0A0h+arg_20]
0x14001bb2b  mov     [rsp+1A0h+var_180], rcx
0x14001bb30  lea     r9, [rsp+1A0h+var_140]
0x14001bb35  mov     rcx, r15
0x14001bb38  call    ??$_Fmt_write@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@GU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z; std::_Fmt_write<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,ushort,std::_Basic_format_specs<ushort>,std::_Lazy_locale)
0x14001bb3d  jmp     loc_14001BE51
0x14001bb42  mov     edi, 2
0x14001bb47  cmp     [r9+0Ah], r13b
0x14001bb4b  jnz     short loc_14001BB51
0x14001bb4d  mov     [r9+0Ah], dil
0x14001bb51  cmp     al, 42h ; 'B'
0x14001bb53  jz      short loc_14001BB7A
0x14001bb55  cmp     al, 58h ; 'X'
0x14001bb57  jz      short loc_14001BB73
0x14001bb59  cmp     al, 62h ; 'b'
0x14001bb5b  jz      short loc_14001BB7A
0x14001bb5d  cmp     al, 6Fh ; 'o'
0x14001bb5f  jz      short loc_14001BB6C
0x14001bb61  cmp     al, 78h ; 'x'
0x14001bb63  jz      short loc_14001BB73
0x14001bb65  mov     eax, 0Ah
0x14001bb6a  jmp     short loc_14001BB7C
0x14001bb6c  mov     eax, 8
0x14001bb71  jmp     short loc_14001BB7C
0x14001bb73  mov     eax, 10h
0x14001bb78  jmp     short loc_14001BB7C
0x14001bb7a  mov     eax, edi
0x14001bb7c  mov     dword ptr [rsp+1A0h+var_180], eax
0x14001bb80  mov     r9b, r8b
0x14001bb83  lea     r8, [rbp+0A0h+var_4F]
0x14001bb87  lea     rdx, [rbp+0A0h+var_90]
0x14001bb8b  lea     rcx, [rsp+1A0h+var_140]
0x14001bb90  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0EH@Z; std::to_chars(char * const,char * const,uchar,int)
0x14001bb95  mov     r12, [rax]
0x14001bb98  lea     rcx, [rbp+0A0h+var_90]
0x14001bb9c  mov     [rsp+1A0h+var_148], rcx
0x14001bba1  mov     eax, r12d
0x14001bba4  sub     eax, ecx
0x14001bba6  mov     [rsp+1A0h+var_164], eax
0x14001bbaa  cmp     [rsi+0Ah], dil
0x14001bbae  jz      short loc_14001BBB6
0x14001bbb0  inc     eax
0x14001bbb2  mov     [rsp+1A0h+var_164], eax
0x14001bbb6  mov     r14d, 1
0x14001bbbc  cmp     byte ptr [rsi+8], 58h ; 'X'
0x14001bbc0  jnz     short loc_14001BBE9
0x14001bbc2  lea     rcx, [rbp+0A0h+var_90]
0x14001bbc6  lea     rdx, [rbp+0A0h+var_90]
0x14001bbca  cmp     rdx, r12
0x14001bbcd  jz      short loc_14001BBE9
0x14001bbcf  mov     dl, [rcx]
0x14001bbd1  lea     eax, [rdx-61h]
0x14001bbd4  cmp     al, 19h
0x14001bbd6  ja      short loc_14001BBDD
0x14001bbd8  sub     dl, 20h ; ' '
0x14001bbdb  mov     [rcx], dl
0x14001bbdd  add     rcx, r14
0x14001bbe0  cmp     rcx, r12
0x14001bbe3  jnz     short loc_14001BBCF
0x14001bbe5  mov     eax, [rsp+1A0h+var_164]
0x14001bbe9  mov     qword ptr [rsp+1A0h+var_160], r13
0x14001bbee  mov     qword ptr [rsp+1A0h+var_160+8], r13
0x14001bbf3  cmp     [rsi+0Bh], r13b
0x14001bbf7  jz      loc_14001BC7D
0x14001bbfd  mov     cl, [rsi+8]
0x14001bc00  cmp     cl, 42h ; 'B'
0x14001bc03  jz      short loc_14001BC5B
0x14001bc05  cmp     cl, 58h ; 'X'
0x14001bc08  jz      short loc_14001BC52
0x14001bc0a  cmp     cl, 62h ; 'b'
0x14001bc0d  jz      short loc_14001BC49
0x14001bc0f  cmp     cl, 6Fh ; 'o'
0x14001bc12  jz      short loc_14001BC22
0x14001bc14  cmp     cl, 78h ; 'x'
0x14001bc17  jnz     short loc_14001BC3A
0x14001bc19  lea     rcx, a0x; "0x"
0x14001bc20  jmp     short loc_14001BC62
0x14001bc22  cmp     [rsp+1A0h+var_170], r13b
0x14001bc27  jz      short loc_14001BC3A
0x14001bc29  lea     rcx, a0; "0"
0x14001bc30  mov     qword ptr [rsp+1A0h+var_160+8], r14
0x14001bc35  mov     edi, r14d
0x14001bc38  jmp     short loc_14001BC67
0x14001bc3a  mov     qword ptr [rsp+1A0h+var_160], r13
0x14001bc3f  mov     qword ptr [rsp+1A0h+var_160+8], r13
0x14001bc44  mov     edi, r13d
0x14001bc47  jmp     short loc_14001BC6C
0x14001bc49  lea     rcx, a0b; "0b"
0x14001bc50  jmp     short loc_14001BC62
0x14001bc52  lea     rcx, a0x_0; "0X"
0x14001bc59  jmp     short loc_14001BC62
0x14001bc5b  lea     rcx, a0b_0; "0B"
0x14001bc62  mov     qword ptr [rsp+1A0h+var_160+8], rdi
0x14001bc67  mov     qword ptr [rsp+1A0h+var_160], rcx
0x14001bc6c  movaps  xmm0, [rsp+1A0h+var_160]
0x14001bc71  movdqa  [rsp+1A0h+var_160], xmm0
0x14001bc77  add     eax, edi
0x14001bc79  mov     [rsp+1A0h+var_164], eax
0x14001bc7d  mov     [rsp+1A0h+var_150], r13d
0x14001bc82  xorps   xmm0, xmm0
0x14001bc85  movups  [rbp+0A0h+var_D0], xmm0
0x14001bc89  mov     qword ptr [rbp+0A0h+var_C0], r13
0x14001bc8d  mov     qword ptr [rbp+0A0h+var_C0+8], 0Fh
0x14001bc95  mov     byte ptr [rbp+0A0h+var_D0], r13b
0x14001bc99  cmp     [rsi+0Ch], r13b
0x14001bc9d  jz      loc_14001BDB6
0x14001bca3  mov     rax, [rbp+0A0h+arg_20]
0x14001bcaa  test    rax, rax
0x14001bcad  jz      short loc_14001BCC9
0x14001bcaf  mov     rdi, [rax+8]
0x14001bcb3  mov     qword ptr [rsp+1A0h+var_140+8], rdi
0x14001bcb8  mov     rax, [rdi]
0x14001bcbb  mov     rcx, rdi
0x14001bcbe  mov     rax, [rax+8]
0x14001bcc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bcc7  jmp     short loc_14001BCDA
0x14001bcc9  mov     cl, r14b
0x14001bccc  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x14001bcd2  mov     rdi, rax
0x14001bcd5  mov     qword ptr [rsp+1A0h+var_140+8], rax
0x14001bcda  lea     rcx, [rsp+1A0h+var_140]
0x14001bcdf  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<ushort>>(std::locale const &)
0x14001bce4  mov     r8, rax
0x14001bce7  mov     rcx, [rax]
0x14001bcea  mov     rax, [rcx+28h]
0x14001bcee  lea     rdx, [rbp+0A0h+var_B0]
0x14001bcf2  mov     rcx, r8
0x14001bcf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bcfa  lea     rcx, [rbp+0A0h+var_D0]
0x14001bcfe  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14001bd03  movups  xmm0, [rbp+0A0h+var_B0]
0x14001bd07  movups  [rbp+0A0h+var_D0], xmm0
0x14001bd0b  movups  xmm1, [rbp+0A0h+var_A0]
0x14001bd0f  movups  [rbp+0A0h+var_C0], xmm1
0x14001bd13  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x14001bd1b  movdqu  [rbp+0A0h+var_A0], xmm0
0x14001bd20  mov     byte ptr [rbp+0A0h+var_B0], r13b
0x14001bd24  lea     rcx, [rbp+0A0h+var_B0]
0x14001bd28  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14001bd2d  nop
0x14001bd2e  test    rdi, rdi
0x14001bd31  jz      short loc_14001BD5B
0x14001bd33  mov     rax, [rdi]
0x14001bd36  mov     rcx, rdi
0x14001bd39  mov     rax, [rax+10h]
0x14001bd3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bd42  mov     r8, rax
0x14001bd45  test    rax, rax
0x14001bd48  jz      short loc_14001BD5B
0x14001bd4a  mov     rcx, [rax]
0x14001bd4d  mov     rax, [rcx]
0x14001bd50  mov     edx, r14d
0x14001bd53  mov     rcx, r8
0x14001bd56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bd5b  lea     rax, [rbp+0A0h+var_D0]
0x14001bd5f  cmp     qword ptr [rbp+0A0h+var_C0+8], 0Fh
0x14001bd64  cmova   rax, qword ptr [rbp+0A0h+var_D0]
0x14001bd69  mov     r10, qword ptr [rbp+0A0h+var_C0]
0x14001bd6d  mov     edx, r13d
0x14001bd70  test    r10, r10
0x14001bd73  jz      short loc_14001BDA8
0x14001bd75  mov     r8, r12
0x14001bd78  sub     r8, [rsp+1A0h+var_148]
0x14001bd7d  movsx   r9, byte ptr [rax]
0x14001bd81  cmp     r8, r9
0x14001bd84  jbe     short loc_14001BDA8
0x14001bd86  lea     r11, [r10+rax]
0x14001bd8a  movsx   rcx, r9b
0x14001bd8e  sub     r8, rcx
0x14001bd91  add     edx, r14d
0x14001bd94  lea     rcx, [rax+1]
0x14001bd98  cmp     rcx, r11
0x14001bd9b  cmovnz  rax, rcx
0x14001bd9f  movsx   r9, byte ptr [rax]
0x14001bda3  cmp     r8, r9
0x14001bda6  ja      short loc_14001BD8A
0x14001bda8  mov     [rsp+1A0h+var_150], edx
0x14001bdac  mov     eax, [rsp+1A0h+var_164]
0x14001bdb0  add     eax, edx
0x14001bdb2  mov     [rsp+1A0h+var_164], eax
0x14001bdb6  cmp     [rsi+0Dh], r13b
0x14001bdba  jz      short loc_14001BDC2
0x14001bdbc  cmp     [rsi+9], r13b
0x14001bdc0  jz      short loc_14001BDC5
0x14001bdc2  mov     r14b, r13b
0x14001bdc5  mov     [rsp+1A0h+var_168], r14b
0x14001bdca  mov     [rbp+0A0h+var_120], r12
0x14001bdce  mov     [rbp+0A0h+var_118], rsi
0x14001bdd2  lea     rcx, [rsp+1A0h+var_170]
0x14001bdd7  mov     [rbp+0A0h+var_110], rcx
0x14001bddb  lea     rcx, [rsp+1A0h+var_160]
0x14001bde0  mov     [rbp+0A0h+var_108], rcx
0x14001bde4  lea     rcx, [rsp+1A0h+var_168]
0x14001bde9  mov     [rbp+0A0h+var_100], rcx
0x14001bded  lea     rcx, [rsp+1A0h+var_164]
0x14001bdf2  mov     [rbp+0A0h+var_F8], rcx
0x14001bdf6  lea     rcx, [rsp+1A0h+var_150]
0x14001bdfb  mov     [rbp+0A0h+var_F0], rcx
0x14001bdff  lea     rcx, [rsp+1A0h+var_148]
0x14001be04  mov     [rbp+0A0h+var_E8], rcx
0x14001be08  lea     rcx, [rbp+0A0h+var_D0]
0x14001be0c  mov     [rbp+0A0h+var_E0], rcx
0x14001be10  lea     rcx, [rbp+0A0h+arg_20]
0x14001be17  mov     [rbp+0A0h+var_D8], rcx
0x14001be1b  lea     rcx, [rbp+0A0h+var_120]
0x14001be1f  test    r14b, r14b
0x14001be22  jz      short loc_14001BE31
0x14001be24  mov     r8, rbx
0x14001be27  mov     rdx, r15
0x14001be2a  call    ??R_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@_K@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@1@V21@_KU?$_Basic_format_specs@G@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,unsigned __int64>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,unsigned __int64,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x14001be2f  jmp     short loc_14001BE48
0x14001be31  mov     [rsp+1A0h+var_178], rcx
0x14001be36  mov     r9, rsi
0x14001be39  mov     r8d, eax
0x14001be3c  mov     rdx, rbx
0x14001be3f  mov     rcx, r15
0x14001be42  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@U?$_Basic_format_specs@G@2@AEAV_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@I@2@YA?AV12@V12@IU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@HAEBU?$_Basic_format_specs@G@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@I@0@YA?AV10@0IU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<ushort>>,std::_Basic_format_specs<ushort>,`std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int,std::_Basic_format_specs<ushort> const &,std::_Fmt_align,`std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x14001be47  nop
0x14001be48  lea     rcx, [rbp+0A0h+var_D0]
0x14001be4c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14001be51  mov     rax, r15
0x14001be54  mov     rcx, [rbp+0A0h+var_40]
0x14001be58  xor     rcx, rsp; StackCookie
0x14001be5b  call    __security_check_cookie
0x14001be60  mov     rbx, [rsp+1A0h+arg_8]
0x14001be68  add     rsp, 170h
0x14001be6f  pop     r15
0x14001be71  pop     r14
0x14001be73  pop     r13
0x14001be75  pop     r12
0x14001be77  pop     rdi
0x14001be78  pop     rsi
0x14001be79  pop     rbp
0x14001be7a  retn
```

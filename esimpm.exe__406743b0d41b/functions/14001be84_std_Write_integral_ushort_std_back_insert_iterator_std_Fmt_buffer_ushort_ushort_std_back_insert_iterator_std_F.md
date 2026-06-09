# std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,ushort>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,ushort,std::_Basic_format_specs<ushort>,std::_Lazy_locale)

- ea: `0x14001be84`
- end: `0x14001c285`
- name: `??$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@G@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@GU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z`
- size: `1025`
- prototype: `__int16 **__fastcall(__int16 **, __int16 *, unsigned __int16, __int64, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x140017b18`
- `0x14001be84`

## callees

- `0x140002f60`
- `0x140017c0c`
- `0x14001b74c`
- `0x14001be84`
- `0x14001e5e8`
- `0x14001f3c8`
- `0x140020bf0`
- `0x140022440`
- `0x14003e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14001c0d8`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14001c0d8`

## pseudocode

```c
__int16 **__fastcall std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,unsigned short>(
        __int16 **a1,
        __int16 *a2,
        unsigned __int16 a3,
        __int64 a4,
        __int64 a5)
{
  char v8; // al
  __int128 v9; // xmm0
  int v10; // ecx
  int v11; // edi
  int v12; // eax
  _BYTE *v13; // r12
  int v14; // eax
  char v15; // r14
  _BYTE *v16; // rcx
  char v17; // cl
  const char *v18; // rcx
  struct std::locale::_Locimp *v19; // rdi
  __int64 v20; // rax
  void (__fastcall ***v21)(_QWORD, __int64); // rax
  char *v22; // rax
  int v23; // edx
  unsigned __int64 v24; // r8
  unsigned __int64 v25; // r9
  char *v26; // r11
  int v28; // [rsp+20h] [rbp-E0h]
  char v29; // [rsp+30h] [rbp-D0h] BYREF
  int v30; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int16 v31; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v32; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v33; // [rsp+50h] [rbp-B0h] BYREF
  int v34; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v35; // [rsp+60h] [rbp-A0h] BYREF
  int v36; // [rsp+70h] [rbp-90h]
  _BYTE *v37; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v38[10]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v39; // [rsp+E0h] [rbp-20h] BYREF
  __m128i v40; // [rsp+F0h] [rbp-10h]
  __int128 v41; // [rsp+100h] [rbp+0h] BYREF
  __m128i si128; // [rsp+110h] [rbp+10h]
  _BYTE v43[65]; // [rsp+120h] [rbp+20h] BYREF
  char v44[15]; // [rsp+161h] [rbp+61h] BYREF

  v31 = a3;
  v8 = *(_BYTE *)(a4 + 8);
  if ( v8 == 99 )
  {
    *(_BYTE *)(a4 + 11) = 0;
    v9 = *(_OWORD *)a4;
    v41 = *(_OWORD *)a4;
    si128.m128i_i32[0] = *(_DWORD *)(a4 + 16);
    v33 = a3;
    v10 = *(_DWORD *)(a4 + 8);
    if ( !(_BYTE)v10 || (_BYTE)v10 == 99 )
    {
      *(_QWORD *)&v35 = &v33;
      *((_QWORD *)&v35 + 1) = 1;
      std::_Fmt_write<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
        a1,
        (__int64)a2,
        &v35,
        (int *)&v41);
    }
    else
    {
      v35 = v9;
      v36 = *(_DWORD *)(a4 + 16);
      std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,unsigned short>(
        (_DWORD)a1,
        (_DWORD)a2,
        a3,
        (unsigned int)&v35,
        a5);
    }
    return a1;
  }
  v11 = 2;
  if ( !*(_BYTE *)(a4 + 10) )
    *(_BYTE *)(a4 + 10) = 2;
  if ( v8 != 66 )
  {
    if ( v8 == 88 )
    {
LABEL_15:
      v12 = 16;
      goto LABEL_17;
    }
    if ( v8 != 98 )
    {
      if ( v8 == 111 )
      {
        v12 = 8;
        goto LABEL_17;
      }
      if ( v8 != 120 )
      {
        v12 = 10;
        goto LABEL_17;
      }
      goto LABEL_15;
    }
  }
  v12 = 2;
LABEL_17:
  v28 = v12;
  v13 = *(_BYTE **)std::to_chars(&v35, v43, v44, a3);
  v37 = v43;
  v14 = (_DWORD)v13 - (unsigned int)v43;
  v30 = v14;
  if ( *(_BYTE *)(a4 + 10) != 2 )
    v30 = ++v14;
  v15 = 1;
  if ( *(_BYTE *)(a4 + 8) == 88 )
  {
    v16 = v43;
    if ( v43 != v13 )
    {
      do
      {
        if ( (unsigned __int8)(*v16 - 97) <= 0x19u )
          *v16 -= 32;
        ++v16;
      }
      while ( v16 != v13 );
      v14 = v30;
    }
  }
  v32 = 0u;
  if ( !*(_BYTE *)(a4 + 11) )
    goto LABEL_41;
  v17 = *(_BYTE *)(a4 + 8);
  switch ( v17 )
  {
    case 'B':
      v18 = "0B";
      goto LABEL_38;
    case 'X':
      v18 = "0X";
      goto LABEL_38;
    case 'b':
      v18 = "0b";
      goto LABEL_38;
    case 'o':
      if ( v31 )
      {
        v18 = "0";
        *((_QWORD *)&v32 + 1) = 1;
        v11 = 1;
LABEL_39:
        *(_QWORD *)&v32 = v18;
        goto LABEL_40;
      }
      break;
    case 'x':
      v18 = "0x";
LABEL_38:
      *((_QWORD *)&v32 + 1) = 2;
      goto LABEL_39;
  }
  v32 = 0u;
  v11 = 0;
LABEL_40:
  v14 += v11;
  v30 = v14;
LABEL_41:
  v34 = 0;
  v39 = 0;
  v40.m128i_i64[0] = 0;
  v40.m128i_i64[1] = 15;
  LOBYTE(v39) = 0;
  if ( *(_BYTE *)(a4 + 12) )
  {
    if ( a5 )
    {
      v19 = *(struct std::locale::_Locimp **)(a5 + 8);
      *((_QWORD *)&v35 + 1) = v19;
      (*(void (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v19 + 8LL))(v19);
    }
    else
    {
      v19 = std::locale::_Init(1);
      *((_QWORD *)&v35 + 1) = v19;
    }
    v20 = std::use_facet<std::numpunct<unsigned short>>(&v35);
    (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v20 + 40LL))(v20, &v41);
    std::string::_Tidy_deallocate(&v39);
    v39 = v41;
    v40 = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v41) = 0;
    std::string::_Tidy_deallocate(&v41);
    if ( v19 )
    {
      v21 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v19 + 16LL))(v19);
      if ( v21 )
        (**v21)(v21, 1);
    }
    v22 = (char *)&v39;
    if ( v40.m128i_i64[1] > 0xFuLL )
      v22 = (char *)v39;
    v23 = 0;
    if ( v40.m128i_i64[0] )
    {
      v24 = v13 - v37;
      v25 = *v22;
      if ( v13 - v37 > v25 )
      {
        v26 = &v22[v40.m128i_i64[0]];
        do
        {
          v24 -= (char)v25;
          ++v23;
          if ( v22 + 1 != v26 )
            ++v22;
          v25 = *v22;
        }
        while ( v24 > v25 );
      }
    }
    v34 = v23;
    v14 = v23 + v30;
    v30 += v23;
  }
  if ( !*(_BYTE *)(a4 + 13) || *(_BYTE *)(a4 + 9) )
    v15 = 0;
  v29 = v15;
  v38[0] = v13;
  v38[1] = a4;
  v38[2] = &v31;
  v38[3] = &v32;
  v38[4] = &v29;
  v38[5] = &v30;
  v38[6] = &v34;
  v38[7] = &v37;
  v38[8] = &v39;
  v38[9] = &a5;
  if ( v15 )
    `std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,unsigned __int64>'::`2'::_lambda_1_::operator()(
      v38,
      a1,
      a2);
  else
    ____Write_aligned_V__back_insert_iterator_V___Fmt_buffer_G_std___std__U___Basic_format_specs_G_2_AEAV_lambda_1___1_____Write_integral_GV__back_insert_iterator_V___Fmt_buffer_G_std___std__I_2_YA_AV12_V12_IU32_V_Lazy_locale_2__Z__std__YA_AV__back_insert_iterator_V___Fmt_buffer_G_std___0_V10_HAEBU___Basic_format_specs_G_0_W4_Fmt_align_0_AEAV_lambda_1___1_____Write_integral_GV__back_insert_iterator_V___Fmt_buffer_G_std___std__I_0_YA_AV10_0IU20_V_Lazy_locale_0__Z__Z(
      a1,
      a2,
      v14,
      a4,
      v28,
      (__int64)v38);
  std::string::_Tidy_deallocate(&v39);
  return a1;
}

```

## disassembly

```asm
0x14001be84  mov     [rsp-8+arg_8], rbx
0x14001be89  push    rbp
0x14001be8a  push    rsi
0x14001be8b  push    rdi
0x14001be8c  push    r12
0x14001be8e  push    r13
0x14001be90  push    r14
0x14001be92  push    r15
0x14001be94  lea     rbp, [rsp-80h]
0x14001be99  sub     rsp, 180h
0x14001bea0  mov     rax, cs:__security_cookie
0x14001bea7  xor     rax, rsp
0x14001beaa  mov     [rbp+0B0h+var_40], rax
0x14001beae  mov     rsi, r9
0x14001beb1  mov     rbx, rdx
0x14001beb4  mov     r15, rcx
0x14001beb7  mov     [rsp+1B0h+var_178], r8w
0x14001bebd  xor     r13d, r13d
0x14001bec0  mov     al, [r9+8]
0x14001bec4  cmp     al, 63h ; 'c'
0x14001bec6  jnz     loc_14001BF4D
0x14001becc  mov     [r9+0Bh], r13b
0x14001bed0  movups  xmm0, xmmword ptr [r9]
0x14001bed4  movaps  [rbp+0B0h+var_B0], xmm0
0x14001bed8  mov     eax, [r9+10h]
0x14001bedc  mov     dword ptr [rbp+0B0h+var_A0], eax
0x14001bedf  mov     rax, [rbp+0B0h+arg_20]
0x14001bee6  mov     [rsp+1B0h+var_160], r8w
0x14001beec  mov     ecx, [r9+8]
0x14001bef0  test    cl, cl
0x14001bef2  jz      short loc_14001BF1D
0x14001bef4  cmp     cl, 63h ; 'c'
0x14001bef7  jz      short loc_14001BF1D
0x14001bef9  movaps  [rsp+1B0h+var_150], xmm0
0x14001befe  mov     ecx, [r9+10h]
0x14001bf02  mov     [rsp+1B0h+var_140], ecx
0x14001bf06  mov     [rsp+1B0h+var_190], rax
0x14001bf0b  lea     r9, [rsp+1B0h+var_150]
0x14001bf10  mov     rcx, r15
0x14001bf13  call    ??$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@G@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@GU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z; std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,ushort>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,ushort,std::_Basic_format_specs<ushort>,std::_Lazy_locale)
0x14001bf18  jmp     loc_14001C25B
0x14001bf1d  lea     rcx, [rsp+1B0h+var_160]
0x14001bf22  mov     qword ptr [rsp+1B0h+var_150], rcx
0x14001bf27  mov     r14d, 1
0x14001bf2d  mov     qword ptr [rsp+1B0h+var_150+8], r14
0x14001bf32  mov     [rsp+1B0h+var_190], rax
0x14001bf37  lea     r9, [rbp+0B0h+var_B0]
0x14001bf3b  lea     r8, [rsp+1B0h+var_150]
0x14001bf40  mov     rcx, r15
0x14001bf43  call    ??$_Fmt_write@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@V?$basic_string_view@GU?$char_traits@G@std@@@0@AEBU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z; std::_Fmt_write<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,std::basic_string_view<ushort>,std::_Basic_format_specs<ushort> const &,std::_Lazy_locale)
0x14001bf48  jmp     loc_14001C25B
0x14001bf4d  mov     edi, 2
0x14001bf52  cmp     [r9+0Ah], r13b
0x14001bf56  jnz     short loc_14001BF5C
0x14001bf58  mov     [r9+0Ah], dil
0x14001bf5c  cmp     al, 42h ; 'B'
0x14001bf5e  jz      short loc_14001BF85
0x14001bf60  cmp     al, 58h ; 'X'
0x14001bf62  jz      short loc_14001BF7E
0x14001bf64  cmp     al, 62h ; 'b'
0x14001bf66  jz      short loc_14001BF85
0x14001bf68  cmp     al, 6Fh ; 'o'
0x14001bf6a  jz      short loc_14001BF77
0x14001bf6c  cmp     al, 78h ; 'x'
0x14001bf6e  jz      short loc_14001BF7E
0x14001bf70  mov     eax, 0Ah
0x14001bf75  jmp     short loc_14001BF87
0x14001bf77  mov     eax, 8
0x14001bf7c  jmp     short loc_14001BF87
0x14001bf7e  mov     eax, 10h
0x14001bf83  jmp     short loc_14001BF87
0x14001bf85  mov     eax, edi
0x14001bf87  mov     dword ptr [rsp+1B0h+var_190], eax
0x14001bf8b  movzx   r9d, r8w
0x14001bf8f  lea     r8, [rbp+0B0h+var_4F]
0x14001bf93  lea     rdx, [rbp+0B0h+var_90]
0x14001bf97  lea     rcx, [rsp+1B0h+var_150]
0x14001bf9c  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0GH@Z; std::to_chars(char * const,char * const,ushort,int)
0x14001bfa1  mov     r12, [rax]
0x14001bfa4  lea     rcx, [rbp+0B0h+var_90]
0x14001bfa8  mov     [rbp+0B0h+var_130], rcx
0x14001bfac  mov     eax, r12d
0x14001bfaf  sub     eax, ecx
0x14001bfb1  mov     [rsp+1B0h+var_17C], eax
0x14001bfb5  cmp     [rsi+0Ah], dil
0x14001bfb9  jz      short loc_14001BFC1
0x14001bfbb  inc     eax
0x14001bfbd  mov     [rsp+1B0h+var_17C], eax
0x14001bfc1  mov     r14d, 1
0x14001bfc7  cmp     byte ptr [rsi+8], 58h ; 'X'
0x14001bfcb  jnz     short loc_14001BFF4
0x14001bfcd  lea     rcx, [rbp+0B0h+var_90]
0x14001bfd1  lea     rdx, [rbp+0B0h+var_90]
0x14001bfd5  cmp     rdx, r12
0x14001bfd8  jz      short loc_14001BFF4
0x14001bfda  mov     dl, [rcx]
0x14001bfdc  lea     eax, [rdx-61h]
0x14001bfdf  cmp     al, 19h
0x14001bfe1  ja      short loc_14001BFE8
0x14001bfe3  sub     dl, 20h ; ' '
0x14001bfe6  mov     [rcx], dl
0x14001bfe8  add     rcx, r14
0x14001bfeb  cmp     rcx, r12
0x14001bfee  jnz     short loc_14001BFDA
0x14001bff0  mov     eax, [rsp+1B0h+var_17C]
0x14001bff4  mov     qword ptr [rsp+1B0h+var_170], r13
0x14001bff9  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x14001bffe  cmp     [rsi+0Bh], r13b
0x14001c002  jz      loc_14001C089
0x14001c008  mov     cl, [rsi+8]
0x14001c00b  cmp     cl, 42h ; 'B'
0x14001c00e  jz      short loc_14001C067
0x14001c010  cmp     cl, 58h ; 'X'
0x14001c013  jz      short loc_14001C05E
0x14001c015  cmp     cl, 62h ; 'b'
0x14001c018  jz      short loc_14001C055
0x14001c01a  cmp     cl, 6Fh ; 'o'
0x14001c01d  jz      short loc_14001C02D
0x14001c01f  cmp     cl, 78h ; 'x'
0x14001c022  jnz     short loc_14001C046
0x14001c024  lea     rcx, a0x; "0x"
0x14001c02b  jmp     short loc_14001C06E
0x14001c02d  cmp     [rsp+1B0h+var_178], r13w
0x14001c033  jz      short loc_14001C046
0x14001c035  lea     rcx, a0; "0"
0x14001c03c  mov     qword ptr [rsp+1B0h+var_170+8], r14
0x14001c041  mov     edi, r14d
0x14001c044  jmp     short loc_14001C073
0x14001c046  mov     qword ptr [rsp+1B0h+var_170], r13
0x14001c04b  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x14001c050  mov     edi, r13d
0x14001c053  jmp     short loc_14001C078
0x14001c055  lea     rcx, a0b; "0b"
0x14001c05c  jmp     short loc_14001C06E
0x14001c05e  lea     rcx, a0x_0; "0X"
0x14001c065  jmp     short loc_14001C06E
0x14001c067  lea     rcx, a0b_0; "0B"
0x14001c06e  mov     qword ptr [rsp+1B0h+var_170+8], rdi
0x14001c073  mov     qword ptr [rsp+1B0h+var_170], rcx
0x14001c078  movaps  xmm0, [rsp+1B0h+var_170]
0x14001c07d  movdqa  [rsp+1B0h+var_170], xmm0
0x14001c083  add     eax, edi
0x14001c085  mov     [rsp+1B0h+var_17C], eax
0x14001c089  mov     [rsp+1B0h+var_158], r13d
0x14001c08e  xorps   xmm0, xmm0
0x14001c091  movups  [rbp+0B0h+var_D0], xmm0
0x14001c095  mov     qword ptr [rbp+0B0h+var_C0], r13
0x14001c099  mov     qword ptr [rbp+0B0h+var_C0+8], 0Fh
0x14001c0a1  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x14001c0a5  cmp     [rsi+0Ch], r13b
0x14001c0a9  jz      loc_14001C1C1
0x14001c0af  mov     rax, [rbp+0B0h+arg_20]
0x14001c0b6  test    rax, rax
0x14001c0b9  jz      short loc_14001C0D5
0x14001c0bb  mov     rdi, [rax+8]
0x14001c0bf  mov     qword ptr [rsp+1B0h+var_150+8], rdi
0x14001c0c4  mov     rax, [rdi]
0x14001c0c7  mov     rcx, rdi
0x14001c0ca  mov     rax, [rax+8]
0x14001c0ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c0d3  jmp     short loc_14001C0E6
0x14001c0d5  mov     cl, r14b
0x14001c0d8  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x14001c0de  mov     rdi, rax
0x14001c0e1  mov     qword ptr [rsp+1B0h+var_150+8], rax
0x14001c0e6  lea     rcx, [rsp+1B0h+var_150]
0x14001c0eb  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<ushort>>(std::locale const &)
0x14001c0f0  mov     r8, rax
0x14001c0f3  mov     rcx, [rax]
0x14001c0f6  mov     rax, [rcx+28h]
0x14001c0fa  lea     rdx, [rbp+0B0h+var_B0]
0x14001c0fe  mov     rcx, r8
0x14001c101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c106  lea     rcx, [rbp+0B0h+var_D0]
0x14001c10a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14001c10f  movups  xmm0, [rbp+0B0h+var_B0]
0x14001c113  movups  [rbp+0B0h+var_D0], xmm0
0x14001c117  movups  xmm1, [rbp+0B0h+var_A0]
0x14001c11b  movups  [rbp+0B0h+var_C0], xmm1
0x14001c11f  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x14001c127  movdqu  [rbp+0B0h+var_A0], xmm0
0x14001c12c  mov     byte ptr [rbp+0B0h+var_B0], r13b
0x14001c130  lea     rcx, [rbp+0B0h+var_B0]
0x14001c134  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14001c139  nop
0x14001c13a  test    rdi, rdi
0x14001c13d  jz      short loc_14001C167
0x14001c13f  mov     rax, [rdi]
0x14001c142  mov     rcx, rdi
0x14001c145  mov     rax, [rax+10h]
0x14001c149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c14e  mov     r8, rax
0x14001c151  test    rax, rax
0x14001c154  jz      short loc_14001C167
0x14001c156  mov     rcx, [rax]
0x14001c159  mov     rax, [rcx]
0x14001c15c  mov     edx, r14d
0x14001c15f  mov     rcx, r8
0x14001c162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c167  lea     rax, [rbp+0B0h+var_D0]
0x14001c16b  cmp     qword ptr [rbp+0B0h+var_C0+8], 0Fh
0x14001c170  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x14001c175  mov     r10, qword ptr [rbp+0B0h+var_C0]
0x14001c179  mov     edx, r13d
0x14001c17c  test    r10, r10
0x14001c17f  jz      short loc_14001C1B3
0x14001c181  mov     r8, r12
0x14001c184  sub     r8, [rbp+0B0h+var_130]
0x14001c188  movsx   r9, byte ptr [rax]
0x14001c18c  cmp     r8, r9
0x14001c18f  jbe     short loc_14001C1B3
0x14001c191  lea     r11, [r10+rax]
0x14001c195  movsx   rcx, r9b
0x14001c199  sub     r8, rcx
0x14001c19c  add     edx, r14d
0x14001c19f  lea     rcx, [rax+1]
0x14001c1a3  cmp     rcx, r11
0x14001c1a6  cmovnz  rax, rcx
0x14001c1aa  movsx   r9, byte ptr [rax]
0x14001c1ae  cmp     r8, r9
0x14001c1b1  ja      short loc_14001C195
0x14001c1b3  mov     [rsp+1B0h+var_158], edx
0x14001c1b7  mov     eax, [rsp+1B0h+var_17C]
0x14001c1bb  add     eax, edx
0x14001c1bd  mov     [rsp+1B0h+var_17C], eax
0x14001c1c1  cmp     [rsi+0Dh], r13b
0x14001c1c5  jz      short loc_14001C1CD
0x14001c1c7  cmp     [rsi+9], r13b
0x14001c1cb  jz      short loc_14001C1D0
0x14001c1cd  mov     r14b, r13b
0x14001c1d0  mov     [rsp+1B0h+var_180], r14b
0x14001c1d5  mov     [rbp+0B0h+var_120], r12
0x14001c1d9  mov     [rbp+0B0h+var_118], rsi
0x14001c1dd  lea     rcx, [rsp+1B0h+var_178]
0x14001c1e2  mov     [rbp+0B0h+var_110], rcx
0x14001c1e6  lea     rcx, [rsp+1B0h+var_170]
0x14001c1eb  mov     [rbp+0B0h+var_108], rcx
0x14001c1ef  lea     rcx, [rsp+1B0h+var_180]
0x14001c1f4  mov     [rbp+0B0h+var_100], rcx
0x14001c1f8  lea     rcx, [rsp+1B0h+var_17C]
0x14001c1fd  mov     [rbp+0B0h+var_F8], rcx
0x14001c201  lea     rcx, [rsp+1B0h+var_158]
0x14001c206  mov     [rbp+0B0h+var_F0], rcx
0x14001c20a  lea     rcx, [rbp+0B0h+var_130]
0x14001c20e  mov     [rbp+0B0h+var_E8], rcx
0x14001c212  lea     rcx, [rbp+0B0h+var_D0]
0x14001c216  mov     [rbp+0B0h+var_E0], rcx
0x14001c21a  lea     rcx, [rbp+0B0h+arg_20]
0x14001c221  mov     [rbp+0B0h+var_D8], rcx
0x14001c225  lea     rcx, [rbp+0B0h+var_120]
0x14001c229  test    r14b, r14b
0x14001c22c  jz      short loc_14001C23B
0x14001c22e  mov     r8, rbx
0x14001c231  mov     rdx, r15
0x14001c234  call    ??R_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@_K@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@1@V21@_KU?$_Basic_format_specs@G@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,unsigned __int64>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,unsigned __int64,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x14001c239  jmp     short loc_14001C252
0x14001c23b  mov     [rsp+1B0h+var_188], rcx
0x14001c240  mov     r9, rsi
0x14001c243  mov     r8d, eax
0x14001c246  mov     rdx, rbx
0x14001c249  mov     rcx, r15
0x14001c24c  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@U?$_Basic_format_specs@G@2@AEAV_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@I@2@YA?AV12@V12@IU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@HAEBU?$_Basic_format_specs@G@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@I@0@YA?AV10@0IU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<ushort>>,std::_Basic_format_specs<ushort>,`std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int,std::_Basic_format_specs<ushort> const &,std::_Fmt_align,`std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x14001c251  nop
0x14001c252  lea     rcx, [rbp+0B0h+var_D0]
0x14001c256  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14001c25b  mov     rax, r15
0x14001c25e  mov     rcx, [rbp+0B0h+var_40]
0x14001c262  xor     rcx, rsp; StackCookie
0x14001c265  call    __security_check_cookie
0x14001c26a  mov     rbx, [rsp+1B0h+arg_8]
0x14001c272  add     rsp, 180h
0x14001c279  pop     r15
0x14001c27b  pop     r14
0x14001c27d  pop     r13
0x14001c27f  pop     r12
0x14001c281  pop     rdi
0x14001c282  pop     rsi
0x14001c283  pop     rbp
0x14001c284  retn
```

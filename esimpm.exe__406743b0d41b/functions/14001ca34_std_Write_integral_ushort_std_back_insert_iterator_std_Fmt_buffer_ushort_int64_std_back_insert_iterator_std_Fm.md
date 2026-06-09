# std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,__int64>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,__int64,std::_Basic_format_specs<ushort>,std::_Lazy_locale)

- ea: `0x14001ca34`
- end: `0x14001ce0a`
- name: `??$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@_J@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@_JU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z`
- size: `982`
- prototype: `__int16 **__fastcall(__int16 **, __int16 *, unsigned __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14001af1c`

## callees

- `0x140002f60`
- `0x140017b18`
- `0x1400195fc`
- `0x14001b904`
- `0x14001ca34`
- `0x14001e5e8`
- `0x14001f748`
- `0x140020bc4`
- `0x140020bf0`
- `0x14003e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14001cc4e`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14001cc4e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int16 **__fastcall std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,__int64>(
        __int16 **a1,
        __int16 *a2,
        unsigned __int64 a3,
        __int64 a4,
        __int64 a5)
{
  char v8; // al
  int v9; // edi
  int v10; // eax
  char *v11; // rcx
  char *v12; // r12
  int v13; // eax
  __int64 v14; // rdx
  char v15; // r14
  char v16; // cl
  const char *v17; // rcx
  struct std::locale::_Locimp *v18; // rdi
  __int64 v19; // rax
  void (__fastcall ***v20)(_QWORD, __int64); // rax
  char *v21; // rax
  int v22; // edx
  unsigned __int64 v23; // r8
  unsigned __int64 v24; // r9
  char *v25; // r11
  int v27; // [rsp+20h] [rbp-E0h]
  char v28; // [rsp+30h] [rbp-D0h] BYREF
  int v29; // [rsp+34h] [rbp-CCh] BYREF
  __int128 v30; // [rsp+40h] [rbp-C0h] BYREF
  int v31; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+58h] [rbp-A8h] BYREF
  char *v33; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v34; // [rsp+70h] [rbp-90h] BYREF
  int v35; // [rsp+80h] [rbp-80h]
  _QWORD v36[10]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v37; // [rsp+E0h] [rbp-20h] BYREF
  __m128i v38; // [rsp+F0h] [rbp-10h]
  __int128 v39; // [rsp+100h] [rbp+0h] BYREF
  __m128i si128; // [rsp+110h] [rbp+10h]
  char v41; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v42[64]; // [rsp+121h] [rbp+21h] BYREF
  char v43[15]; // [rsp+161h] [rbp+61h] BYREF

  v32 = a3;
  v8 = *(_BYTE *)(a4 + 8);
  if ( v8 == 99 )
  {
    if ( a3 > 0xFFFF )
      std::_Throw_format_error("integral cannot be stored in wchar_t");
    *(_BYTE *)(a4 + 11) = 0;
    v34 = *(_OWORD *)a4;
    v35 = *(_DWORD *)(a4 + 16);
    std::_Fmt_write<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
      (__int64)a1,
      (__int64)a2,
      a3,
      &v34,
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
LABEL_13:
      v10 = 16;
      goto LABEL_15;
    }
    if ( v8 != 98 )
    {
      if ( v8 == 111 )
      {
        v10 = 8;
        goto LABEL_15;
      }
      if ( v8 != 120 )
      {
        v10 = 10;
        goto LABEL_15;
      }
      goto LABEL_13;
    }
  }
  v10 = 2;
LABEL_15:
  v27 = v10;
  std::_Integer_to_chars<__int64>(&v34, &v41, v43, a3);
  v11 = &v41;
  v33 = &v41;
  v12 = (char *)v34;
  v13 = v34 - (unsigned int)&v41;
  v29 = v13;
  v14 = v32;
  if ( v32 < 0 )
  {
    v11 = v42;
    v33 = v42;
  }
  else if ( *(_BYTE *)(a4 + 10) != 2 )
  {
    v29 = ++v13;
  }
  v15 = 1;
  if ( *(_BYTE *)(a4 + 8) == 88 && v11 != (char *)v34 )
  {
    do
    {
      if ( (unsigned __int8)(*v11 - 97) <= 0x19u )
        *v11 -= 32;
      ++v11;
    }
    while ( v11 != v12 );
    v13 = v29;
    v14 = v32;
  }
  v30 = 0u;
  if ( !*(_BYTE *)(a4 + 11) )
    goto LABEL_41;
  v16 = *(_BYTE *)(a4 + 8);
  switch ( v16 )
  {
    case 'B':
      v17 = "0B";
      goto LABEL_38;
    case 'X':
      v17 = "0X";
      goto LABEL_38;
    case 'b':
      v17 = "0b";
      goto LABEL_38;
    case 'o':
      if ( v14 )
      {
        v17 = "0";
        *((_QWORD *)&v30 + 1) = 1;
        v9 = 1;
LABEL_39:
        *(_QWORD *)&v30 = v17;
        goto LABEL_40;
      }
      break;
    case 'x':
      v17 = "0x";
LABEL_38:
      *((_QWORD *)&v30 + 1) = 2;
      goto LABEL_39;
  }
  v30 = 0u;
  v9 = 0;
LABEL_40:
  v13 += v9;
  v29 = v13;
LABEL_41:
  v31 = 0;
  v37 = 0;
  v38.m128i_i64[0] = 0;
  v38.m128i_i64[1] = 15;
  LOBYTE(v37) = 0;
  if ( *(_BYTE *)(a4 + 12) )
  {
    if ( a5 )
    {
      v18 = *(struct std::locale::_Locimp **)(a5 + 8);
      *((_QWORD *)&v34 + 1) = v18;
      (*(void (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v18 + 8LL))(v18);
    }
    else
    {
      v18 = std::locale::_Init(1);
      *((_QWORD *)&v34 + 1) = v18;
    }
    v19 = std::use_facet<std::numpunct<unsigned short>>(&v34);
    (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v19 + 40LL))(v19, &v39);
    std::string::_Tidy_deallocate(&v37);
    v37 = v39;
    v38 = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v39) = 0;
    std::string::_Tidy_deallocate(&v39);
    if ( v18 )
    {
      v20 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v18 + 16LL))(v18);
      if ( v20 )
        (**v20)(v20, 1);
    }
    v21 = (char *)&v37;
    if ( v38.m128i_i64[1] > 0xFuLL )
      v21 = (char *)v37;
    v22 = 0;
    if ( v38.m128i_i64[0] )
    {
      v23 = v12 - v33;
      v24 = *v21;
      if ( v12 - v33 > v24 )
      {
        v25 = &v21[v38.m128i_i64[0]];
        do
        {
          v23 -= (char)v24;
          ++v22;
          if ( v21 + 1 != v25 )
            ++v21;
          v24 = *v21;
        }
        while ( v23 > v24 );
      }
    }
    v31 = v22;
    v13 = v22 + v29;
    v29 += v22;
  }
  if ( !*(_BYTE *)(a4 + 13) || *(_BYTE *)(a4 + 9) )
    v15 = 0;
  v28 = v15;
  v36[0] = v12;
  v36[1] = a4;
  v36[2] = &v32;
  v36[3] = &v30;
  v36[4] = &v28;
  v36[5] = &v29;
  v36[6] = &v31;
  v36[7] = &v33;
  v36[8] = &v37;
  v36[9] = &a5;
  if ( v15 )
    `std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,__int64>'::`2'::_lambda_1_::operator()(
      v36,
      a1,
      a2);
  else
    ____Write_aligned_V__back_insert_iterator_V___Fmt_buffer_G_std___std__U___Basic_format_specs_G_2_AEAV_lambda_1___1_____Write_integral_GV__back_insert_iterator_V___Fmt_buffer_G_std___std___J_2_YA_AV12_V12__JU32_V_Lazy_locale_2__Z__std__YA_AV__back_insert_iterator_V___Fmt_buffer_G_std___0_V10_HAEBU___Basic_format_specs_G_0_W4_Fmt_align_0_AEAV_lambda_1___1_____Write_integral_GV__back_insert_iterator_V___Fmt_buffer_G_std___std___J_0_YA_AV10_0_JU20_V_Lazy_locale_0__Z__Z(
      a1,
      a2,
      v13,
      a4,
      v27,
      (__int64)v36);
  std::string::_Tidy_deallocate(&v37);
  return a1;
}

```

## disassembly

```asm
0x14001ca34  mov     [rsp-8+arg_8], rbx
0x14001ca39  push    rbp
0x14001ca3a  push    rsi
0x14001ca3b  push    rdi
0x14001ca3c  push    r12
0x14001ca3e  push    r13
0x14001ca40  push    r14
0x14001ca42  push    r15
0x14001ca44  lea     rbp, [rsp-80h]
0x14001ca49  sub     rsp, 180h
0x14001ca50  mov     rax, cs:__security_cookie
0x14001ca57  xor     rax, rsp
0x14001ca5a  mov     [rbp+0B0h+var_40], rax
0x14001ca5e  mov     rsi, r9
0x14001ca61  mov     rbx, rdx
0x14001ca64  mov     r15, rcx
0x14001ca67  mov     [rsp+1B0h+var_158], r8
0x14001ca6c  xor     r13d, r13d
0x14001ca6f  mov     al, [r9+8]
0x14001ca73  cmp     al, 63h ; 'c'
0x14001ca75  jnz     short loc_14001CAB6
0x14001ca77  cmp     r8, 0FFFFh
0x14001ca7e  ja      loc_14001CDFD
0x14001ca84  mov     [r9+0Bh], r13b
0x14001ca88  movaps  xmm0, xmmword ptr [r9]
0x14001ca8c  movaps  [rsp+1B0h+var_140], xmm0
0x14001ca91  mov     ecx, [r9+10h]
0x14001ca95  mov     [rbp+0B0h+var_130], ecx
0x14001ca98  mov     rcx, [rbp+0B0h+arg_20]
0x14001ca9f  mov     [rsp+1B0h+var_190], rcx
0x14001caa4  lea     r9, [rsp+1B0h+var_140]
0x14001caa9  mov     rcx, r15
0x14001caac  call    ??$_Fmt_write@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@GU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z; std::_Fmt_write<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,ushort,std::_Basic_format_specs<ushort>,std::_Lazy_locale)
0x14001cab1  jmp     loc_14001CDD3
0x14001cab6  mov     edi, 2
0x14001cabb  cmp     [r9+0Ah], r13b
0x14001cabf  jnz     short loc_14001CAC5
0x14001cac1  mov     [r9+0Ah], dil
0x14001cac5  cmp     al, 42h ; 'B'
0x14001cac7  jz      short loc_14001CAEE
0x14001cac9  cmp     al, 58h ; 'X'
0x14001cacb  jz      short loc_14001CAE7
0x14001cacd  cmp     al, 62h ; 'b'
0x14001cacf  jz      short loc_14001CAEE
0x14001cad1  cmp     al, 6Fh ; 'o'
0x14001cad3  jz      short loc_14001CAE0
0x14001cad5  cmp     al, 78h ; 'x'
0x14001cad7  jz      short loc_14001CAE7
0x14001cad9  mov     eax, 0Ah
0x14001cade  jmp     short loc_14001CAF0
0x14001cae0  mov     eax, 8
0x14001cae5  jmp     short loc_14001CAF0
0x14001cae7  mov     eax, 10h
0x14001caec  jmp     short loc_14001CAF0
0x14001caee  mov     eax, edi
0x14001caf0  mov     dword ptr [rsp+1B0h+var_190], eax
0x14001caf4  mov     r9, r8
0x14001caf7  lea     r8, [rbp+0B0h+var_4F]
0x14001cafb  lea     rdx, [rbp+0B0h+var_90]
0x14001caff  lea     rcx, [rsp+1B0h+var_140]
0x14001cb04  call    ??$_Integer_to_chars@_J@std@@YA?AUto_chars_result@0@PEADQEAD_JH@Z; std::_Integer_to_chars<__int64>(char *,char * const,__int64,int)
0x14001cb09  lea     rcx, [rbp+0B0h+var_90]
0x14001cb0d  mov     [rsp+1B0h+var_150], rcx
0x14001cb12  mov     r12, qword ptr [rsp+1B0h+var_140]
0x14001cb17  mov     eax, r12d
0x14001cb1a  sub     eax, ecx
0x14001cb1c  mov     [rsp+1B0h+var_17C], eax
0x14001cb20  mov     rdx, [rsp+1B0h+var_158]
0x14001cb25  test    rdx, rdx
0x14001cb28  js      short loc_14001CB38
0x14001cb2a  cmp     [rsi+0Ah], dil
0x14001cb2e  jz      short loc_14001CB41
0x14001cb30  inc     eax
0x14001cb32  mov     [rsp+1B0h+var_17C], eax
0x14001cb36  jmp     short loc_14001CB41
0x14001cb38  lea     rcx, [rbp+0B0h+var_8F]
0x14001cb3c  mov     [rsp+1B0h+var_150], rcx
0x14001cb41  mov     r14d, 1
0x14001cb47  cmp     byte ptr [rsi+8], 58h ; 'X'
0x14001cb4b  jnz     short loc_14001CB71
0x14001cb4d  cmp     rcx, r12
0x14001cb50  jz      short loc_14001CB71
0x14001cb52  mov     dl, [rcx]
0x14001cb54  lea     eax, [rdx-61h]
0x14001cb57  cmp     al, 19h
0x14001cb59  ja      short loc_14001CB60
0x14001cb5b  sub     dl, 20h ; ' '
0x14001cb5e  mov     [rcx], dl
0x14001cb60  add     rcx, r14
0x14001cb63  cmp     rcx, r12
0x14001cb66  jnz     short loc_14001CB52
0x14001cb68  mov     eax, [rsp+1B0h+var_17C]
0x14001cb6c  mov     rdx, [rsp+1B0h+var_158]
0x14001cb71  mov     qword ptr [rsp+1B0h+var_170], r13
0x14001cb76  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x14001cb7b  cmp     [rsi+0Bh], r13b
0x14001cb7f  jz      short loc_14001CBFF
0x14001cb81  mov     cl, [rsi+8]
0x14001cb84  cmp     cl, 42h ; 'B'
0x14001cb87  jz      short loc_14001CBDD
0x14001cb89  cmp     cl, 58h ; 'X'
0x14001cb8c  jz      short loc_14001CBD4
0x14001cb8e  cmp     cl, 62h ; 'b'
0x14001cb91  jz      short loc_14001CBCB
0x14001cb93  cmp     cl, 6Fh ; 'o'
0x14001cb96  jz      short loc_14001CBA6
0x14001cb98  cmp     cl, 78h ; 'x'
0x14001cb9b  jnz     short loc_14001CBBC
0x14001cb9d  lea     rcx, a0x; "0x"
0x14001cba4  jmp     short loc_14001CBE4
0x14001cba6  test    rdx, rdx
0x14001cba9  jz      short loc_14001CBBC
0x14001cbab  lea     rcx, a0; "0"
0x14001cbb2  mov     qword ptr [rsp+1B0h+var_170+8], r14
0x14001cbb7  mov     edi, r14d
0x14001cbba  jmp     short loc_14001CBE9
0x14001cbbc  mov     qword ptr [rsp+1B0h+var_170], r13
0x14001cbc1  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x14001cbc6  mov     edi, r13d
0x14001cbc9  jmp     short loc_14001CBEE
0x14001cbcb  lea     rcx, a0b; "0b"
0x14001cbd2  jmp     short loc_14001CBE4
0x14001cbd4  lea     rcx, a0x_0; "0X"
0x14001cbdb  jmp     short loc_14001CBE4
0x14001cbdd  lea     rcx, a0b_0; "0B"
0x14001cbe4  mov     qword ptr [rsp+1B0h+var_170+8], rdi
0x14001cbe9  mov     qword ptr [rsp+1B0h+var_170], rcx
0x14001cbee  movaps  xmm0, [rsp+1B0h+var_170]
0x14001cbf3  movdqa  [rsp+1B0h+var_170], xmm0
0x14001cbf9  add     eax, edi
0x14001cbfb  mov     [rsp+1B0h+var_17C], eax
0x14001cbff  mov     [rsp+1B0h+var_160], r13d
0x14001cc04  xorps   xmm0, xmm0
0x14001cc07  movups  [rbp+0B0h+var_D0], xmm0
0x14001cc0b  mov     qword ptr [rbp+0B0h+var_C0], r13
0x14001cc0f  mov     qword ptr [rbp+0B0h+var_C0+8], 0Fh
0x14001cc17  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x14001cc1b  cmp     [rsi+0Ch], r13b
0x14001cc1f  jz      loc_14001CD38
0x14001cc25  mov     rax, [rbp+0B0h+arg_20]
0x14001cc2c  test    rax, rax
0x14001cc2f  jz      short loc_14001CC4B
0x14001cc31  mov     rdi, [rax+8]
0x14001cc35  mov     qword ptr [rsp+1B0h+var_140+8], rdi
0x14001cc3a  mov     rax, [rdi]
0x14001cc3d  mov     rcx, rdi
0x14001cc40  mov     rax, [rax+8]
0x14001cc44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001cc49  jmp     short loc_14001CC5C
0x14001cc4b  mov     cl, r14b
0x14001cc4e  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x14001cc54  mov     rdi, rax
0x14001cc57  mov     qword ptr [rsp+1B0h+var_140+8], rax
0x14001cc5c  lea     rcx, [rsp+1B0h+var_140]
0x14001cc61  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<ushort>>(std::locale const &)
0x14001cc66  mov     r8, rax
0x14001cc69  mov     rcx, [rax]
0x14001cc6c  mov     rax, [rcx+28h]
0x14001cc70  lea     rdx, [rbp+0B0h+var_B0]
0x14001cc74  mov     rcx, r8
0x14001cc77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001cc7c  lea     rcx, [rbp+0B0h+var_D0]
0x14001cc80  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14001cc85  movups  xmm0, [rbp+0B0h+var_B0]
0x14001cc89  movups  [rbp+0B0h+var_D0], xmm0
0x14001cc8d  movups  xmm1, [rbp+0B0h+var_A0]
0x14001cc91  movups  [rbp+0B0h+var_C0], xmm1
0x14001cc95  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x14001cc9d  movdqu  [rbp+0B0h+var_A0], xmm0
0x14001cca2  mov     byte ptr [rbp+0B0h+var_B0], r13b
0x14001cca6  lea     rcx, [rbp+0B0h+var_B0]
0x14001ccaa  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14001ccaf  nop
0x14001ccb0  test    rdi, rdi
0x14001ccb3  jz      short loc_14001CCDD
0x14001ccb5  mov     rax, [rdi]
0x14001ccb8  mov     rcx, rdi
0x14001ccbb  mov     rax, [rax+10h]
0x14001ccbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ccc4  mov     r8, rax
0x14001ccc7  test    rax, rax
0x14001ccca  jz      short loc_14001CCDD
0x14001cccc  mov     rcx, [rax]
0x14001cccf  mov     rax, [rcx]
0x14001ccd2  mov     edx, r14d
0x14001ccd5  mov     rcx, r8
0x14001ccd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ccdd  lea     rax, [rbp+0B0h+var_D0]
0x14001cce1  cmp     qword ptr [rbp+0B0h+var_C0+8], 0Fh
0x14001cce6  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x14001cceb  mov     r10, qword ptr [rbp+0B0h+var_C0]
0x14001ccef  mov     edx, r13d
0x14001ccf2  test    r10, r10
0x14001ccf5  jz      short loc_14001CD2A
0x14001ccf7  mov     r8, r12
0x14001ccfa  sub     r8, [rsp+1B0h+var_150]
0x14001ccff  movsx   r9, byte ptr [rax]
0x14001cd03  cmp     r8, r9
0x14001cd06  jbe     short loc_14001CD2A
0x14001cd08  lea     r11, [rax+r10]
0x14001cd0c  movsx   rcx, r9b
0x14001cd10  sub     r8, rcx
0x14001cd13  add     edx, r14d
0x14001cd16  lea     rcx, [rax+1]
0x14001cd1a  cmp     rcx, r11
0x14001cd1d  cmovnz  rax, rcx
0x14001cd21  movsx   r9, byte ptr [rax]
0x14001cd25  cmp     r8, r9
0x14001cd28  ja      short loc_14001CD0C
0x14001cd2a  mov     [rsp+1B0h+var_160], edx
0x14001cd2e  mov     eax, [rsp+1B0h+var_17C]
0x14001cd32  add     eax, edx
0x14001cd34  mov     [rsp+1B0h+var_17C], eax
0x14001cd38  cmp     [rsi+0Dh], r13b
0x14001cd3c  jz      short loc_14001CD44
0x14001cd3e  cmp     [rsi+9], r13b
0x14001cd42  jz      short loc_14001CD47
0x14001cd44  mov     r14b, r13b
0x14001cd47  mov     [rsp+1B0h+var_180], r14b
0x14001cd4c  mov     [rbp+0B0h+var_120], r12
0x14001cd50  mov     [rbp+0B0h+var_118], rsi
0x14001cd54  lea     rcx, [rsp+1B0h+var_158]
0x14001cd59  mov     [rbp+0B0h+var_110], rcx
0x14001cd5d  lea     rcx, [rsp+1B0h+var_170]
0x14001cd62  mov     [rbp+0B0h+var_108], rcx
0x14001cd66  lea     rcx, [rsp+1B0h+var_180]
0x14001cd6b  mov     [rbp+0B0h+var_100], rcx
0x14001cd6f  lea     rcx, [rsp+1B0h+var_17C]
0x14001cd74  mov     [rbp+0B0h+var_F8], rcx
0x14001cd78  lea     rcx, [rsp+1B0h+var_160]
0x14001cd7d  mov     [rbp+0B0h+var_F0], rcx
0x14001cd81  lea     rcx, [rsp+1B0h+var_150]
0x14001cd86  mov     [rbp+0B0h+var_E8], rcx
0x14001cd8a  lea     rcx, [rbp+0B0h+var_D0]
0x14001cd8e  mov     [rbp+0B0h+var_E0], rcx
0x14001cd92  lea     rcx, [rbp+0B0h+arg_20]
0x14001cd99  mov     [rbp+0B0h+var_D8], rcx
0x14001cd9d  lea     rcx, [rbp+0B0h+var_120]
0x14001cda1  test    r14b, r14b
0x14001cda4  jz      short loc_14001CDB3
0x14001cda6  mov     r8, rbx
0x14001cda9  mov     rdx, r15
0x14001cdac  call    ??R_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@_J@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@1@V21@_JU?$_Basic_format_specs@G@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,__int64>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,__int64,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x14001cdb1  jmp     short loc_14001CDCA
0x14001cdb3  mov     [rsp+1B0h+var_188], rcx
0x14001cdb8  mov     r9, rsi
0x14001cdbb  mov     r8d, eax
0x14001cdbe  mov     rdx, rbx
0x14001cdc1  mov     rcx, r15
0x14001cdc4  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@U?$_Basic_format_specs@G@2@AEAV_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@_J@2@YA?AV12@V12@_JU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@HAEBU?$_Basic_format_specs@G@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@_J@0@YA?AV10@0_JU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<ushort>>,std::_Basic_format_specs<ushort>,`std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,__int64>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,__int64,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int,std::_Basic_format_specs<ushort> const &,std::_Fmt_align,`std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,__int64>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,__int64,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x14001cdc9  nop
0x14001cdca  lea     rcx, [rbp+0B0h+var_D0]
0x14001cdce  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14001cdd3  mov     rax, r15
0x14001cdd6  mov     rcx, [rbp+0B0h+var_40]
0x14001cdda  xor     rcx, rsp; StackCookie
0x14001cddd  call    __security_check_cookie
0x14001cde2  mov     rbx, [rsp+1B0h+arg_8]
0x14001cdea  add     rsp, 180h
0x14001cdf1  pop     r15
0x14001cdf3  pop     r14
0x14001cdf5  pop     r13
0x14001cdf7  pop     r12
0x14001cdf9  pop     rdi
0x14001cdfa  pop     rsi
0x14001cdfb  pop     rbp
0x14001cdfc  retn
0x14001cdfd  lea     rcx, aIntegralCannot; "integral cannot be stored in wchar_t"
0x14001ce04  call    ?_Throw_format_error@std@@YAXPEBD@Z; std::_Throw_format_error(char const *)
```

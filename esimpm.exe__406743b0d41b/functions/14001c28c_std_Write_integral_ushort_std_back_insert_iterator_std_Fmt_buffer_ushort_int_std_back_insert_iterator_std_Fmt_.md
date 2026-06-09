# std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int,std::_Basic_format_specs<ushort>,std::_Lazy_locale)

- ea: `0x14001c28c`
- end: `0x14001c65c`
- name: `??$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@H@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@HU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z`
- size: `976`
- prototype: `__int16 **__fastcall(__int16 **, __int16 *, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14001af1c`

## callees

- `0x140002f60`
- `0x140017b18`
- `0x14001b828`
- `0x14001c28c`
- `0x14001e5e8`
- `0x14001f584`
- `0x140020bc4`
- `0x140020bf0`
- `0x140022628`
- `0x14003e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14001c4a0`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14001c4a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int16 **__fastcall std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,int>(
        __int16 **a1,
        __int16 *a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5)
{
  char v8; // al
  int v9; // edi
  int v10; // eax
  char *v11; // r12
  char *v12; // rcx
  int v13; // eax
  int v14; // edx
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
  int v32; // [rsp+58h] [rbp-A8h] BYREF
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

  v31 = a3;
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
  v11 = *(char **)std::to_chars(&v34, &v41, v43, a3);
  v12 = &v41;
  v33 = &v41;
  v13 = (_DWORD)v11 - (unsigned int)&v41;
  v29 = v13;
  v14 = v31;
  if ( v31 < 0 )
  {
    v12 = v42;
    v33 = v42;
  }
  else if ( *(_BYTE *)(a4 + 10) != 2 )
  {
    v29 = ++v13;
  }
  v15 = 1;
  if ( *(_BYTE *)(a4 + 8) == 88 && v12 != v11 )
  {
    do
    {
      if ( (unsigned __int8)(*v12 - 97) <= 0x19u )
        *v12 -= 32;
      ++v12;
    }
    while ( v12 != v11 );
    v13 = v29;
    v14 = v31;
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
  v32 = 0;
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
      v23 = v11 - v33;
      v24 = *v21;
      if ( v11 - v33 > v24 )
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
    v32 = v22;
    v13 = v22 + v29;
    v29 += v22;
  }
  if ( !*(_BYTE *)(a4 + 13) || *(_BYTE *)(a4 + 9) )
    v15 = 0;
  v28 = v15;
  v36[0] = v11;
  v36[1] = a4;
  v36[2] = &v31;
  v36[3] = &v30;
  v36[4] = &v28;
  v36[5] = &v29;
  v36[6] = &v32;
  v36[7] = &v33;
  v36[8] = &v37;
  v36[9] = &a5;
  if ( v15 )
    `std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,int>'::`2'::_lambda_1_::operator()(
      v36,
      a1,
      a2);
  else
    ____Write_aligned_V__back_insert_iterator_V___Fmt_buffer_G_std___std__U___Basic_format_specs_G_2_AEAV_lambda_1___1_____Write_integral_GV__back_insert_iterator_V___Fmt_buffer_G_std___std__H_2_YA_AV12_V12_HU32_V_Lazy_locale_2__Z__std__YA_AV__back_insert_iterator_V___Fmt_buffer_G_std___0_V10_HAEBU___Basic_format_specs_G_0_W4_Fmt_align_0_AEAV_lambda_1___1_____Write_integral_GV__back_insert_iterator_V___Fmt_buffer_G_std___std__H_0_YA_AV10_0HU20_V_Lazy_locale_0__Z__Z(
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
0x14001c28c  mov     [rsp-8+arg_8], rbx
0x14001c291  push    rbp
0x14001c292  push    rsi
0x14001c293  push    rdi
0x14001c294  push    r12
0x14001c296  push    r13
0x14001c298  push    r14
0x14001c29a  push    r15
0x14001c29c  lea     rbp, [rsp-80h]
0x14001c2a1  sub     rsp, 180h
0x14001c2a8  mov     rax, cs:__security_cookie
0x14001c2af  xor     rax, rsp
0x14001c2b2  mov     [rbp+0B0h+var_40], rax
0x14001c2b6  mov     rsi, r9
0x14001c2b9  mov     rbx, rdx
0x14001c2bc  mov     r15, rcx
0x14001c2bf  mov     [rsp+1B0h+var_160], r8d
0x14001c2c4  xor     r13d, r13d
0x14001c2c7  mov     al, [r9+8]
0x14001c2cb  cmp     al, 63h ; 'c'
0x14001c2cd  jnz     short loc_14001C30E
0x14001c2cf  cmp     r8d, 0FFFFh
0x14001c2d6  ja      loc_14001C64F
0x14001c2dc  mov     [r9+0Bh], r13b
0x14001c2e0  movaps  xmm0, xmmword ptr [r9]
0x14001c2e4  movaps  [rsp+1B0h+var_140], xmm0
0x14001c2e9  mov     ecx, [r9+10h]
0x14001c2ed  mov     [rbp+0B0h+var_130], ecx
0x14001c2f0  mov     rcx, [rbp+0B0h+arg_20]
0x14001c2f7  mov     [rsp+1B0h+var_190], rcx
0x14001c2fc  lea     r9, [rsp+1B0h+var_140]
0x14001c301  mov     rcx, r15
0x14001c304  call    ??$_Fmt_write@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@GU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z; std::_Fmt_write<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,ushort,std::_Basic_format_specs<ushort>,std::_Lazy_locale)
0x14001c309  jmp     loc_14001C625
0x14001c30e  mov     edi, 2
0x14001c313  cmp     [r9+0Ah], r13b
0x14001c317  jnz     short loc_14001C31D
0x14001c319  mov     [r9+0Ah], dil
0x14001c31d  cmp     al, 42h ; 'B'
0x14001c31f  jz      short loc_14001C346
0x14001c321  cmp     al, 58h ; 'X'
0x14001c323  jz      short loc_14001C33F
0x14001c325  cmp     al, 62h ; 'b'
0x14001c327  jz      short loc_14001C346
0x14001c329  cmp     al, 6Fh ; 'o'
0x14001c32b  jz      short loc_14001C338
0x14001c32d  cmp     al, 78h ; 'x'
0x14001c32f  jz      short loc_14001C33F
0x14001c331  mov     eax, 0Ah
0x14001c336  jmp     short loc_14001C348
0x14001c338  mov     eax, 8
0x14001c33d  jmp     short loc_14001C348
0x14001c33f  mov     eax, 10h
0x14001c344  jmp     short loc_14001C348
0x14001c346  mov     eax, edi
0x14001c348  mov     dword ptr [rsp+1B0h+var_190], eax
0x14001c34c  mov     r9d, r8d
0x14001c34f  lea     r8, [rbp+0B0h+var_4F]
0x14001c353  lea     rdx, [rbp+0B0h+var_90]
0x14001c357  lea     rcx, [rsp+1B0h+var_140]
0x14001c35c  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0HH@Z; std::to_chars(char * const,char * const,int,int)
0x14001c361  mov     r12, [rax]
0x14001c364  lea     rcx, [rbp+0B0h+var_90]
0x14001c368  mov     [rsp+1B0h+var_150], rcx
0x14001c36d  mov     eax, r12d
0x14001c370  sub     eax, ecx
0x14001c372  mov     [rsp+1B0h+var_17C], eax
0x14001c376  mov     edx, [rsp+1B0h+var_160]
0x14001c37a  test    edx, edx
0x14001c37c  js      short loc_14001C38C
0x14001c37e  cmp     [rsi+0Ah], dil
0x14001c382  jz      short loc_14001C395
0x14001c384  inc     eax
0x14001c386  mov     [rsp+1B0h+var_17C], eax
0x14001c38a  jmp     short loc_14001C395
0x14001c38c  lea     rcx, [rbp+0B0h+var_8F]
0x14001c390  mov     [rsp+1B0h+var_150], rcx
0x14001c395  mov     r14d, 1
0x14001c39b  cmp     byte ptr [rsi+8], 58h ; 'X'
0x14001c39f  jnz     short loc_14001C3C4
0x14001c3a1  cmp     rcx, r12
0x14001c3a4  jz      short loc_14001C3C4
0x14001c3a6  mov     dl, [rcx]
0x14001c3a8  lea     eax, [rdx-61h]
0x14001c3ab  cmp     al, 19h
0x14001c3ad  ja      short loc_14001C3B4
0x14001c3af  sub     dl, 20h ; ' '
0x14001c3b2  mov     [rcx], dl
0x14001c3b4  add     rcx, r14
0x14001c3b7  cmp     rcx, r12
0x14001c3ba  jnz     short loc_14001C3A6
0x14001c3bc  mov     eax, [rsp+1B0h+var_17C]
0x14001c3c0  mov     edx, [rsp+1B0h+var_160]
0x14001c3c4  mov     qword ptr [rsp+1B0h+var_170], r13
0x14001c3c9  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x14001c3ce  cmp     [rsi+0Bh], r13b
0x14001c3d2  jz      short loc_14001C451
0x14001c3d4  mov     cl, [rsi+8]
0x14001c3d7  cmp     cl, 42h ; 'B'
0x14001c3da  jz      short loc_14001C42F
0x14001c3dc  cmp     cl, 58h ; 'X'
0x14001c3df  jz      short loc_14001C426
0x14001c3e1  cmp     cl, 62h ; 'b'
0x14001c3e4  jz      short loc_14001C41D
0x14001c3e6  cmp     cl, 6Fh ; 'o'
0x14001c3e9  jz      short loc_14001C3F9
0x14001c3eb  cmp     cl, 78h ; 'x'
0x14001c3ee  jnz     short loc_14001C40E
0x14001c3f0  lea     rcx, a0x; "0x"
0x14001c3f7  jmp     short loc_14001C436
0x14001c3f9  test    edx, edx
0x14001c3fb  jz      short loc_14001C40E
0x14001c3fd  lea     rcx, a0; "0"
0x14001c404  mov     qword ptr [rsp+1B0h+var_170+8], r14
0x14001c409  mov     edi, r14d
0x14001c40c  jmp     short loc_14001C43B
0x14001c40e  mov     qword ptr [rsp+1B0h+var_170], r13
0x14001c413  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x14001c418  mov     edi, r13d
0x14001c41b  jmp     short loc_14001C440
0x14001c41d  lea     rcx, a0b; "0b"
0x14001c424  jmp     short loc_14001C436
0x14001c426  lea     rcx, a0x_0; "0X"
0x14001c42d  jmp     short loc_14001C436
0x14001c42f  lea     rcx, a0b_0; "0B"
0x14001c436  mov     qword ptr [rsp+1B0h+var_170+8], rdi
0x14001c43b  mov     qword ptr [rsp+1B0h+var_170], rcx
0x14001c440  movaps  xmm0, [rsp+1B0h+var_170]
0x14001c445  movdqa  [rsp+1B0h+var_170], xmm0
0x14001c44b  add     eax, edi
0x14001c44d  mov     [rsp+1B0h+var_17C], eax
0x14001c451  mov     [rsp+1B0h+var_158], r13d
0x14001c456  xorps   xmm0, xmm0
0x14001c459  movups  [rbp+0B0h+var_D0], xmm0
0x14001c45d  mov     qword ptr [rbp+0B0h+var_C0], r13
0x14001c461  mov     qword ptr [rbp+0B0h+var_C0+8], 0Fh
0x14001c469  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x14001c46d  cmp     [rsi+0Ch], r13b
0x14001c471  jz      loc_14001C58A
0x14001c477  mov     rax, [rbp+0B0h+arg_20]
0x14001c47e  test    rax, rax
0x14001c481  jz      short loc_14001C49D
0x14001c483  mov     rdi, [rax+8]
0x14001c487  mov     qword ptr [rsp+1B0h+var_140+8], rdi
0x14001c48c  mov     rax, [rdi]
0x14001c48f  mov     rcx, rdi
0x14001c492  mov     rax, [rax+8]
0x14001c496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c49b  jmp     short loc_14001C4AE
0x14001c49d  mov     cl, r14b
0x14001c4a0  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x14001c4a6  mov     rdi, rax
0x14001c4a9  mov     qword ptr [rsp+1B0h+var_140+8], rax
0x14001c4ae  lea     rcx, [rsp+1B0h+var_140]
0x14001c4b3  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<ushort>>(std::locale const &)
0x14001c4b8  mov     r8, rax
0x14001c4bb  mov     rcx, [rax]
0x14001c4be  mov     rax, [rcx+28h]
0x14001c4c2  lea     rdx, [rbp+0B0h+var_B0]
0x14001c4c6  mov     rcx, r8
0x14001c4c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c4ce  lea     rcx, [rbp+0B0h+var_D0]
0x14001c4d2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14001c4d7  movups  xmm0, [rbp+0B0h+var_B0]
0x14001c4db  movups  [rbp+0B0h+var_D0], xmm0
0x14001c4df  movups  xmm1, [rbp+0B0h+var_A0]
0x14001c4e3  movups  [rbp+0B0h+var_C0], xmm1
0x14001c4e7  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x14001c4ef  movdqu  [rbp+0B0h+var_A0], xmm0
0x14001c4f4  mov     byte ptr [rbp+0B0h+var_B0], r13b
0x14001c4f8  lea     rcx, [rbp+0B0h+var_B0]
0x14001c4fc  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14001c501  nop
0x14001c502  test    rdi, rdi
0x14001c505  jz      short loc_14001C52F
0x14001c507  mov     rax, [rdi]
0x14001c50a  mov     rcx, rdi
0x14001c50d  mov     rax, [rax+10h]
0x14001c511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c516  mov     r8, rax
0x14001c519  test    rax, rax
0x14001c51c  jz      short loc_14001C52F
0x14001c51e  mov     rcx, [rax]
0x14001c521  mov     rax, [rcx]
0x14001c524  mov     edx, r14d
0x14001c527  mov     rcx, r8
0x14001c52a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c52f  lea     rax, [rbp+0B0h+var_D0]
0x14001c533  cmp     qword ptr [rbp+0B0h+var_C0+8], 0Fh
0x14001c538  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x14001c53d  mov     r10, qword ptr [rbp+0B0h+var_C0]
0x14001c541  mov     edx, r13d
0x14001c544  test    r10, r10
0x14001c547  jz      short loc_14001C57C
0x14001c549  mov     r8, r12
0x14001c54c  sub     r8, [rsp+1B0h+var_150]
0x14001c551  movsx   r9, byte ptr [rax]
0x14001c555  cmp     r8, r9
0x14001c558  jbe     short loc_14001C57C
0x14001c55a  lea     r11, [rax+r10]
0x14001c55e  movsx   rcx, r9b
0x14001c562  sub     r8, rcx
0x14001c565  add     edx, r14d
0x14001c568  lea     rcx, [rax+1]
0x14001c56c  cmp     rcx, r11
0x14001c56f  cmovnz  rax, rcx
0x14001c573  movsx   r9, byte ptr [rax]
0x14001c577  cmp     r8, r9
0x14001c57a  ja      short loc_14001C55E
0x14001c57c  mov     [rsp+1B0h+var_158], edx
0x14001c580  mov     eax, [rsp+1B0h+var_17C]
0x14001c584  add     eax, edx
0x14001c586  mov     [rsp+1B0h+var_17C], eax
0x14001c58a  cmp     [rsi+0Dh], r13b
0x14001c58e  jz      short loc_14001C596
0x14001c590  cmp     [rsi+9], r13b
0x14001c594  jz      short loc_14001C599
0x14001c596  mov     r14b, r13b
0x14001c599  mov     [rsp+1B0h+var_180], r14b
0x14001c59e  mov     [rbp+0B0h+var_120], r12
0x14001c5a2  mov     [rbp+0B0h+var_118], rsi
0x14001c5a6  lea     rcx, [rsp+1B0h+var_160]
0x14001c5ab  mov     [rbp+0B0h+var_110], rcx
0x14001c5af  lea     rcx, [rsp+1B0h+var_170]
0x14001c5b4  mov     [rbp+0B0h+var_108], rcx
0x14001c5b8  lea     rcx, [rsp+1B0h+var_180]
0x14001c5bd  mov     [rbp+0B0h+var_100], rcx
0x14001c5c1  lea     rcx, [rsp+1B0h+var_17C]
0x14001c5c6  mov     [rbp+0B0h+var_F8], rcx
0x14001c5ca  lea     rcx, [rsp+1B0h+var_158]
0x14001c5cf  mov     [rbp+0B0h+var_F0], rcx
0x14001c5d3  lea     rcx, [rsp+1B0h+var_150]
0x14001c5d8  mov     [rbp+0B0h+var_E8], rcx
0x14001c5dc  lea     rcx, [rbp+0B0h+var_D0]
0x14001c5e0  mov     [rbp+0B0h+var_E0], rcx
0x14001c5e4  lea     rcx, [rbp+0B0h+arg_20]
0x14001c5eb  mov     [rbp+0B0h+var_D8], rcx
0x14001c5ef  lea     rcx, [rbp+0B0h+var_120]
0x14001c5f3  test    r14b, r14b
0x14001c5f6  jz      short loc_14001C605
0x14001c5f8  mov     r8, rbx
0x14001c5fb  mov     rdx, r15
0x14001c5fe  call    ??R_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@H@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@1@V21@HU?$_Basic_format_specs@G@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x14001c603  jmp     short loc_14001C61C
0x14001c605  mov     [rsp+1B0h+var_188], rcx
0x14001c60a  mov     r9, rsi
0x14001c60d  mov     r8d, eax
0x14001c610  mov     rdx, rbx
0x14001c613  mov     rcx, r15
0x14001c616  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@U?$_Basic_format_specs@G@2@AEAV_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@H@2@YA?AV12@V12@HU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@HAEBU?$_Basic_format_specs@G@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@H@0@YA?AV10@0HU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<ushort>>,std::_Basic_format_specs<ushort>,`std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int,std::_Basic_format_specs<ushort> const &,std::_Fmt_align,`std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x14001c61b  nop
0x14001c61c  lea     rcx, [rbp+0B0h+var_D0]
0x14001c620  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14001c625  mov     rax, r15
0x14001c628  mov     rcx, [rbp+0B0h+var_40]
0x14001c62c  xor     rcx, rsp; StackCookie
0x14001c62f  call    __security_check_cookie
0x14001c634  mov     rbx, [rsp+1B0h+arg_8]
0x14001c63c  add     rsp, 180h
0x14001c643  pop     r15
0x14001c645  pop     r14
0x14001c647  pop     r13
0x14001c649  pop     r12
0x14001c64b  pop     rdi
0x14001c64c  pop     rsi
0x14001c64d  pop     rbp
0x14001c64e  retn
0x14001c64f  lea     rcx, aIntegralCannot; "integral cannot be stored in wchar_t"
0x14001c656  call    ?_Throw_format_error@std@@YAXPEBD@Z; std::_Throw_format_error(char const *)
```

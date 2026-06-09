# std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,unsigned __int64>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,unsigned __int64,std::_Basic_format_specs<ushort>,std::_Lazy_locale)

- ea: `0x14001ce10`
- end: `0x14001d1d8`
- name: `??$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@_K@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@_KU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z`
- size: `968`
- prototype: `__int16 **__fastcall(__int16 **, __int16 *, unsigned __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14001af1c`

## callees

- `0x140002f60`
- `0x140017b18`
- `0x14001b74c`
- `0x14001ce10`
- `0x14001e5e8`
- `0x14001f3c8`
- `0x140020bc4`
- `0x140020bf0`
- `0x140022d2c`
- `0x14003e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14001d01c`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14001d01c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int16 **__fastcall std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,unsigned __int64>(
        __int16 **a1,
        __int16 *a2,
        unsigned __int64 a3,
        __int64 a4,
        __int64 a5)
{
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
  char v27; // [rsp+30h] [rbp-D0h] BYREF
  int v28; // [rsp+34h] [rbp-CCh] BYREF
  __int128 v29; // [rsp+40h] [rbp-C0h] BYREF
  int v30; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v31; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE *v32; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v33; // [rsp+70h] [rbp-90h] BYREF
  int v34; // [rsp+80h] [rbp-80h]
  _QWORD v35[10]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v36; // [rsp+E0h] [rbp-20h] BYREF
  __m128i v37; // [rsp+F0h] [rbp-10h]
  __int128 v38; // [rsp+100h] [rbp+0h] BYREF
  __m128i si128; // [rsp+110h] [rbp+10h]
  _BYTE v40[65]; // [rsp+120h] [rbp+20h] BYREF
  char v41[15]; // [rsp+161h] [rbp+61h] BYREF

  v31 = a3;
  v8 = *(_BYTE *)(a4 + 8);
  if ( v8 == 99 )
  {
    if ( a3 > 0xFFFF )
      std::_Throw_format_error("integral cannot be stored in wchar_t");
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
  v26 = v10;
  v11 = *(_BYTE **)std::to_chars(&v33, v40, v41, a3);
  v32 = v40;
  v12 = (_DWORD)v11 - (unsigned int)v40;
  v28 = v12;
  if ( *(_BYTE *)(a4 + 10) != 2 )
    v28 = ++v12;
  v13 = 1;
  if ( *(_BYTE *)(a4 + 8) == 88 )
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
      v12 = v28;
    }
  }
  v29 = 0u;
  if ( !*(_BYTE *)(a4 + 11) )
    goto LABEL_39;
  v15 = *(_BYTE *)(a4 + 8);
  switch ( v15 )
  {
    case 'B':
      v16 = "0B";
      goto LABEL_36;
    case 'X':
      v16 = "0X";
      goto LABEL_36;
    case 'b':
      v16 = "0b";
      goto LABEL_36;
    case 'o':
      if ( v31 )
      {
        v16 = "0";
        *((_QWORD *)&v29 + 1) = 1;
        v9 = 1;
LABEL_37:
        *(_QWORD *)&v29 = v16;
        goto LABEL_38;
      }
      break;
    case 'x':
      v16 = "0x";
LABEL_36:
      *((_QWORD *)&v29 + 1) = 2;
      goto LABEL_37;
  }
  v29 = 0u;
  v9 = 0;
LABEL_38:
  v12 += v9;
  v28 = v12;
LABEL_39:
  v30 = 0;
  v36 = 0;
  v37.m128i_i64[0] = 0;
  v37.m128i_i64[1] = 15;
  LOBYTE(v36) = 0;
  if ( *(_BYTE *)(a4 + 12) )
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
    v30 = v21;
    v12 = v21 + v28;
    v28 += v21;
  }
  if ( !*(_BYTE *)(a4 + 13) || *(_BYTE *)(a4 + 9) )
    v13 = 0;
  v27 = v13;
  v35[0] = v11;
  v35[1] = a4;
  v35[2] = &v31;
  v35[3] = &v29;
  v35[4] = &v27;
  v35[5] = &v28;
  v35[6] = &v30;
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
      a4,
      v26,
      (__int64)v35);
  std::string::_Tidy_deallocate(&v36);
  return a1;
}

```

## disassembly

```asm
0x14001ce10  mov     [rsp-8+arg_8], rbx
0x14001ce15  push    rbp
0x14001ce16  push    rsi
0x14001ce17  push    rdi
0x14001ce18  push    r12
0x14001ce1a  push    r13
0x14001ce1c  push    r14
0x14001ce1e  push    r15
0x14001ce20  lea     rbp, [rsp-80h]
0x14001ce25  sub     rsp, 180h
0x14001ce2c  mov     rax, cs:__security_cookie
0x14001ce33  xor     rax, rsp
0x14001ce36  mov     [rbp+0B0h+var_40], rax
0x14001ce3a  mov     rsi, r9
0x14001ce3d  mov     rbx, rdx
0x14001ce40  mov     r15, rcx
0x14001ce43  mov     [rsp+1B0h+var_158], r8
0x14001ce48  xor     r13d, r13d
0x14001ce4b  mov     al, [r9+8]
0x14001ce4f  cmp     al, 63h ; 'c'
0x14001ce51  jnz     short loc_14001CE92
0x14001ce53  cmp     r8, 0FFFFh
0x14001ce5a  ja      loc_14001D1CB
0x14001ce60  mov     [r9+0Bh], r13b
0x14001ce64  movaps  xmm0, xmmword ptr [r9]
0x14001ce68  movaps  [rsp+1B0h+var_140], xmm0
0x14001ce6d  mov     ecx, [r9+10h]
0x14001ce71  mov     [rbp+0B0h+var_130], ecx
0x14001ce74  mov     rcx, [rbp+0B0h+arg_20]
0x14001ce7b  mov     [rsp+1B0h+var_190], rcx
0x14001ce80  lea     r9, [rsp+1B0h+var_140]
0x14001ce85  mov     rcx, r15
0x14001ce88  call    ??$_Fmt_write@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@GU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z; std::_Fmt_write<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,ushort,std::_Basic_format_specs<ushort>,std::_Lazy_locale)
0x14001ce8d  jmp     loc_14001D1A1
0x14001ce92  mov     edi, 2
0x14001ce97  cmp     [r9+0Ah], r13b
0x14001ce9b  jnz     short loc_14001CEA1
0x14001ce9d  mov     [r9+0Ah], dil
0x14001cea1  cmp     al, 42h ; 'B'
0x14001cea3  jz      short loc_14001CECA
0x14001cea5  cmp     al, 58h ; 'X'
0x14001cea7  jz      short loc_14001CEC3
0x14001cea9  cmp     al, 62h ; 'b'
0x14001ceab  jz      short loc_14001CECA
0x14001cead  cmp     al, 6Fh ; 'o'
0x14001ceaf  jz      short loc_14001CEBC
0x14001ceb1  cmp     al, 78h ; 'x'
0x14001ceb3  jz      short loc_14001CEC3
0x14001ceb5  mov     eax, 0Ah
0x14001ceba  jmp     short loc_14001CECC
0x14001cebc  mov     eax, 8
0x14001cec1  jmp     short loc_14001CECC
0x14001cec3  mov     eax, 10h
0x14001cec8  jmp     short loc_14001CECC
0x14001ceca  mov     eax, edi
0x14001cecc  mov     dword ptr [rsp+1B0h+var_190], eax
0x14001ced0  mov     r9, r8
0x14001ced3  lea     r8, [rbp+0B0h+var_4F]
0x14001ced7  lea     rdx, [rbp+0B0h+var_90]
0x14001cedb  lea     rcx, [rsp+1B0h+var_140]
0x14001cee0  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0_KH@Z; std::to_chars(char * const,char * const,unsigned __int64,int)
0x14001cee5  mov     r12, [rax]
0x14001cee8  lea     rcx, [rbp+0B0h+var_90]
0x14001ceec  mov     [rsp+1B0h+var_150], rcx
0x14001cef1  mov     eax, r12d
0x14001cef4  sub     eax, ecx
0x14001cef6  mov     [rsp+1B0h+var_17C], eax
0x14001cefa  cmp     [rsi+0Ah], dil
0x14001cefe  jz      short loc_14001CF06
0x14001cf00  inc     eax
0x14001cf02  mov     [rsp+1B0h+var_17C], eax
0x14001cf06  mov     r14d, 1
0x14001cf0c  cmp     byte ptr [rsi+8], 58h ; 'X'
0x14001cf10  jnz     short loc_14001CF39
0x14001cf12  lea     rcx, [rbp+0B0h+var_90]
0x14001cf16  lea     rdx, [rbp+0B0h+var_90]
0x14001cf1a  cmp     rdx, r12
0x14001cf1d  jz      short loc_14001CF39
0x14001cf1f  mov     dl, [rcx]
0x14001cf21  lea     eax, [rdx-61h]
0x14001cf24  cmp     al, 19h
0x14001cf26  ja      short loc_14001CF2D
0x14001cf28  sub     dl, 20h ; ' '
0x14001cf2b  mov     [rcx], dl
0x14001cf2d  add     rcx, r14
0x14001cf30  cmp     rcx, r12
0x14001cf33  jnz     short loc_14001CF1F
0x14001cf35  mov     eax, [rsp+1B0h+var_17C]
0x14001cf39  mov     qword ptr [rsp+1B0h+var_170], r13
0x14001cf3e  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x14001cf43  cmp     [rsi+0Bh], r13b
0x14001cf47  jz      loc_14001CFCD
0x14001cf4d  mov     cl, [rsi+8]
0x14001cf50  cmp     cl, 42h ; 'B'
0x14001cf53  jz      short loc_14001CFAB
0x14001cf55  cmp     cl, 58h ; 'X'
0x14001cf58  jz      short loc_14001CFA2
0x14001cf5a  cmp     cl, 62h ; 'b'
0x14001cf5d  jz      short loc_14001CF99
0x14001cf5f  cmp     cl, 6Fh ; 'o'
0x14001cf62  jz      short loc_14001CF72
0x14001cf64  cmp     cl, 78h ; 'x'
0x14001cf67  jnz     short loc_14001CF8A
0x14001cf69  lea     rcx, a0x; "0x"
0x14001cf70  jmp     short loc_14001CFB2
0x14001cf72  cmp     [rsp+1B0h+var_158], r13
0x14001cf77  jz      short loc_14001CF8A
0x14001cf79  lea     rcx, a0; "0"
0x14001cf80  mov     qword ptr [rsp+1B0h+var_170+8], r14
0x14001cf85  mov     edi, r14d
0x14001cf88  jmp     short loc_14001CFB7
0x14001cf8a  mov     qword ptr [rsp+1B0h+var_170], r13
0x14001cf8f  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x14001cf94  mov     edi, r13d
0x14001cf97  jmp     short loc_14001CFBC
0x14001cf99  lea     rcx, a0b; "0b"
0x14001cfa0  jmp     short loc_14001CFB2
0x14001cfa2  lea     rcx, a0x_0; "0X"
0x14001cfa9  jmp     short loc_14001CFB2
0x14001cfab  lea     rcx, a0b_0; "0B"
0x14001cfb2  mov     qword ptr [rsp+1B0h+var_170+8], rdi
0x14001cfb7  mov     qword ptr [rsp+1B0h+var_170], rcx
0x14001cfbc  movaps  xmm0, [rsp+1B0h+var_170]
0x14001cfc1  movdqa  [rsp+1B0h+var_170], xmm0
0x14001cfc7  add     eax, edi
0x14001cfc9  mov     [rsp+1B0h+var_17C], eax
0x14001cfcd  mov     [rsp+1B0h+var_160], r13d
0x14001cfd2  xorps   xmm0, xmm0
0x14001cfd5  movups  [rbp+0B0h+var_D0], xmm0
0x14001cfd9  mov     qword ptr [rbp+0B0h+var_C0], r13
0x14001cfdd  mov     qword ptr [rbp+0B0h+var_C0+8], 0Fh
0x14001cfe5  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x14001cfe9  cmp     [rsi+0Ch], r13b
0x14001cfed  jz      loc_14001D106
0x14001cff3  mov     rax, [rbp+0B0h+arg_20]
0x14001cffa  test    rax, rax
0x14001cffd  jz      short loc_14001D019
0x14001cfff  mov     rdi, [rax+8]
0x14001d003  mov     qword ptr [rsp+1B0h+var_140+8], rdi
0x14001d008  mov     rax, [rdi]
0x14001d00b  mov     rcx, rdi
0x14001d00e  mov     rax, [rax+8]
0x14001d012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d017  jmp     short loc_14001D02A
0x14001d019  mov     cl, r14b
0x14001d01c  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x14001d022  mov     rdi, rax
0x14001d025  mov     qword ptr [rsp+1B0h+var_140+8], rax
0x14001d02a  lea     rcx, [rsp+1B0h+var_140]
0x14001d02f  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<ushort>>(std::locale const &)
0x14001d034  mov     r8, rax
0x14001d037  mov     rcx, [rax]
0x14001d03a  mov     rax, [rcx+28h]
0x14001d03e  lea     rdx, [rbp+0B0h+var_B0]
0x14001d042  mov     rcx, r8
0x14001d045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d04a  lea     rcx, [rbp+0B0h+var_D0]
0x14001d04e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14001d053  movups  xmm0, [rbp+0B0h+var_B0]
0x14001d057  movups  [rbp+0B0h+var_D0], xmm0
0x14001d05b  movups  xmm1, [rbp+0B0h+var_A0]
0x14001d05f  movups  [rbp+0B0h+var_C0], xmm1
0x14001d063  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x14001d06b  movdqu  [rbp+0B0h+var_A0], xmm0
0x14001d070  mov     byte ptr [rbp+0B0h+var_B0], r13b
0x14001d074  lea     rcx, [rbp+0B0h+var_B0]
0x14001d078  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14001d07d  nop
0x14001d07e  test    rdi, rdi
0x14001d081  jz      short loc_14001D0AB
0x14001d083  mov     rax, [rdi]
0x14001d086  mov     rcx, rdi
0x14001d089  mov     rax, [rax+10h]
0x14001d08d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d092  mov     r8, rax
0x14001d095  test    rax, rax
0x14001d098  jz      short loc_14001D0AB
0x14001d09a  mov     rcx, [rax]
0x14001d09d  mov     rax, [rcx]
0x14001d0a0  mov     edx, r14d
0x14001d0a3  mov     rcx, r8
0x14001d0a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d0ab  lea     rax, [rbp+0B0h+var_D0]
0x14001d0af  cmp     qword ptr [rbp+0B0h+var_C0+8], 0Fh
0x14001d0b4  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x14001d0b9  mov     r10, qword ptr [rbp+0B0h+var_C0]
0x14001d0bd  mov     edx, r13d
0x14001d0c0  test    r10, r10
0x14001d0c3  jz      short loc_14001D0F8
0x14001d0c5  mov     r8, r12
0x14001d0c8  sub     r8, [rsp+1B0h+var_150]
0x14001d0cd  movsx   r9, byte ptr [rax]
0x14001d0d1  cmp     r8, r9
0x14001d0d4  jbe     short loc_14001D0F8
0x14001d0d6  lea     r11, [r10+rax]
0x14001d0da  movsx   rcx, r9b
0x14001d0de  sub     r8, rcx
0x14001d0e1  add     edx, r14d
0x14001d0e4  lea     rcx, [rax+1]
0x14001d0e8  cmp     rcx, r11
0x14001d0eb  cmovnz  rax, rcx
0x14001d0ef  movsx   r9, byte ptr [rax]
0x14001d0f3  cmp     r8, r9
0x14001d0f6  ja      short loc_14001D0DA
0x14001d0f8  mov     [rsp+1B0h+var_160], edx
0x14001d0fc  mov     eax, [rsp+1B0h+var_17C]
0x14001d100  add     eax, edx
0x14001d102  mov     [rsp+1B0h+var_17C], eax
0x14001d106  cmp     [rsi+0Dh], r13b
0x14001d10a  jz      short loc_14001D112
0x14001d10c  cmp     [rsi+9], r13b
0x14001d110  jz      short loc_14001D115
0x14001d112  mov     r14b, r13b
0x14001d115  mov     [rsp+1B0h+var_180], r14b
0x14001d11a  mov     [rbp+0B0h+var_120], r12
0x14001d11e  mov     [rbp+0B0h+var_118], rsi
0x14001d122  lea     rcx, [rsp+1B0h+var_158]
0x14001d127  mov     [rbp+0B0h+var_110], rcx
0x14001d12b  lea     rcx, [rsp+1B0h+var_170]
0x14001d130  mov     [rbp+0B0h+var_108], rcx
0x14001d134  lea     rcx, [rsp+1B0h+var_180]
0x14001d139  mov     [rbp+0B0h+var_100], rcx
0x14001d13d  lea     rcx, [rsp+1B0h+var_17C]
0x14001d142  mov     [rbp+0B0h+var_F8], rcx
0x14001d146  lea     rcx, [rsp+1B0h+var_160]
0x14001d14b  mov     [rbp+0B0h+var_F0], rcx
0x14001d14f  lea     rcx, [rsp+1B0h+var_150]
0x14001d154  mov     [rbp+0B0h+var_E8], rcx
0x14001d158  lea     rcx, [rbp+0B0h+var_D0]
0x14001d15c  mov     [rbp+0B0h+var_E0], rcx
0x14001d160  lea     rcx, [rbp+0B0h+arg_20]
0x14001d167  mov     [rbp+0B0h+var_D8], rcx
0x14001d16b  lea     rcx, [rbp+0B0h+var_120]
0x14001d16f  test    r14b, r14b
0x14001d172  jz      short loc_14001D181
0x14001d174  mov     r8, rbx
0x14001d177  mov     rdx, r15
0x14001d17a  call    ??R_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@_K@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@1@V21@_KU?$_Basic_format_specs@G@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,unsigned __int64>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,unsigned __int64,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x14001d17f  jmp     short loc_14001D198
0x14001d181  mov     [rsp+1B0h+var_188], rcx
0x14001d186  mov     r9, rsi
0x14001d189  mov     r8d, eax
0x14001d18c  mov     rdx, rbx
0x14001d18f  mov     rcx, r15
0x14001d192  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@U?$_Basic_format_specs@G@2@AEAV_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@I@2@YA?AV12@V12@IU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@HAEBU?$_Basic_format_specs@G@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@I@0@YA?AV10@0IU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<ushort>>,std::_Basic_format_specs<ushort>,`std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int,std::_Basic_format_specs<ushort> const &,std::_Fmt_align,`std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x14001d197  nop
0x14001d198  lea     rcx, [rbp+0B0h+var_D0]
0x14001d19c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14001d1a1  mov     rax, r15
0x14001d1a4  mov     rcx, [rbp+0B0h+var_40]
0x14001d1a8  xor     rcx, rsp; StackCookie
0x14001d1ab  call    __security_check_cookie
0x14001d1b0  mov     rbx, [rsp+1B0h+arg_8]
0x14001d1b8  add     rsp, 180h
0x14001d1bf  pop     r15
0x14001d1c1  pop     r14
0x14001d1c3  pop     r13
0x14001d1c5  pop     r12
0x14001d1c7  pop     rdi
0x14001d1c8  pop     rsi
0x14001d1c9  pop     rbp
0x14001d1ca  retn
0x14001d1cb  lea     rcx, aIntegralCannot; "integral cannot be stored in wchar_t"
0x14001d1d2  call    ?_Throw_format_error@std@@YAXPEBD@Z; std::_Throw_format_error(char const *)
```

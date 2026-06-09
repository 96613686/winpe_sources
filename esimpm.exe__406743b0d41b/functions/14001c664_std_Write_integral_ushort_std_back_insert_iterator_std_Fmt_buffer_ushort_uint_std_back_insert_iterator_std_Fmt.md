# std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint,std::_Basic_format_specs<ushort>,std::_Lazy_locale)

- ea: `0x14001c664`
- end: `0x14001ca2c`
- name: `??$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@I@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@IU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z`
- size: `968`
- prototype: `__int16 **__fastcall(__int16 **, __int16 *, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14001af1c`

## callees

- `0x140002f60`
- `0x140017b18`
- `0x14001b74c`
- `0x14001c664`
- `0x14001e5e8`
- `0x14001f3c8`
- `0x140020bc4`
- `0x140020bf0`
- `0x140022814`
- `0x14003e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14001c870`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14001c870`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int16 **__fastcall std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,unsigned int>(
        __int16 **a1,
        __int16 *a2,
        unsigned int a3,
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
  unsigned int v31; // [rsp+58h] [rbp-A8h] BYREF
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
0x14001c664  mov     [rsp-8+arg_8], rbx
0x14001c669  push    rbp
0x14001c66a  push    rsi
0x14001c66b  push    rdi
0x14001c66c  push    r12
0x14001c66e  push    r13
0x14001c670  push    r14
0x14001c672  push    r15
0x14001c674  lea     rbp, [rsp-80h]
0x14001c679  sub     rsp, 180h
0x14001c680  mov     rax, cs:__security_cookie
0x14001c687  xor     rax, rsp
0x14001c68a  mov     [rbp+0B0h+var_40], rax
0x14001c68e  mov     rsi, r9
0x14001c691  mov     rbx, rdx
0x14001c694  mov     r15, rcx
0x14001c697  mov     [rsp+1B0h+var_158], r8d
0x14001c69c  xor     r13d, r13d
0x14001c69f  mov     al, [r9+8]
0x14001c6a3  cmp     al, 63h ; 'c'
0x14001c6a5  jnz     short loc_14001C6E6
0x14001c6a7  cmp     r8d, 0FFFFh
0x14001c6ae  ja      loc_14001CA1F
0x14001c6b4  mov     [r9+0Bh], r13b
0x14001c6b8  movaps  xmm0, xmmword ptr [r9]
0x14001c6bc  movaps  [rsp+1B0h+var_140], xmm0
0x14001c6c1  mov     ecx, [r9+10h]
0x14001c6c5  mov     [rbp+0B0h+var_130], ecx
0x14001c6c8  mov     rcx, [rbp+0B0h+arg_20]
0x14001c6cf  mov     [rsp+1B0h+var_190], rcx
0x14001c6d4  lea     r9, [rsp+1B0h+var_140]
0x14001c6d9  mov     rcx, r15
0x14001c6dc  call    ??$_Fmt_write@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@GU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z; std::_Fmt_write<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,ushort,std::_Basic_format_specs<ushort>,std::_Lazy_locale)
0x14001c6e1  jmp     loc_14001C9F5
0x14001c6e6  mov     edi, 2
0x14001c6eb  cmp     [r9+0Ah], r13b
0x14001c6ef  jnz     short loc_14001C6F5
0x14001c6f1  mov     [r9+0Ah], dil
0x14001c6f5  cmp     al, 42h ; 'B'
0x14001c6f7  jz      short loc_14001C71E
0x14001c6f9  cmp     al, 58h ; 'X'
0x14001c6fb  jz      short loc_14001C717
0x14001c6fd  cmp     al, 62h ; 'b'
0x14001c6ff  jz      short loc_14001C71E
0x14001c701  cmp     al, 6Fh ; 'o'
0x14001c703  jz      short loc_14001C710
0x14001c705  cmp     al, 78h ; 'x'
0x14001c707  jz      short loc_14001C717
0x14001c709  mov     eax, 0Ah
0x14001c70e  jmp     short loc_14001C720
0x14001c710  mov     eax, 8
0x14001c715  jmp     short loc_14001C720
0x14001c717  mov     eax, 10h
0x14001c71c  jmp     short loc_14001C720
0x14001c71e  mov     eax, edi
0x14001c720  mov     dword ptr [rsp+1B0h+var_190], eax
0x14001c724  mov     r9d, r8d
0x14001c727  lea     r8, [rbp+0B0h+var_4F]
0x14001c72b  lea     rdx, [rbp+0B0h+var_90]
0x14001c72f  lea     rcx, [rsp+1B0h+var_140]
0x14001c734  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0IH@Z; std::to_chars(char * const,char * const,uint,int)
0x14001c739  mov     r12, [rax]
0x14001c73c  lea     rcx, [rbp+0B0h+var_90]
0x14001c740  mov     [rsp+1B0h+var_150], rcx
0x14001c745  mov     eax, r12d
0x14001c748  sub     eax, ecx
0x14001c74a  mov     [rsp+1B0h+var_17C], eax
0x14001c74e  cmp     [rsi+0Ah], dil
0x14001c752  jz      short loc_14001C75A
0x14001c754  inc     eax
0x14001c756  mov     [rsp+1B0h+var_17C], eax
0x14001c75a  mov     r14d, 1
0x14001c760  cmp     byte ptr [rsi+8], 58h ; 'X'
0x14001c764  jnz     short loc_14001C78D
0x14001c766  lea     rcx, [rbp+0B0h+var_90]
0x14001c76a  lea     rdx, [rbp+0B0h+var_90]
0x14001c76e  cmp     rdx, r12
0x14001c771  jz      short loc_14001C78D
0x14001c773  mov     dl, [rcx]
0x14001c775  lea     eax, [rdx-61h]
0x14001c778  cmp     al, 19h
0x14001c77a  ja      short loc_14001C781
0x14001c77c  sub     dl, 20h ; ' '
0x14001c77f  mov     [rcx], dl
0x14001c781  add     rcx, r14
0x14001c784  cmp     rcx, r12
0x14001c787  jnz     short loc_14001C773
0x14001c789  mov     eax, [rsp+1B0h+var_17C]
0x14001c78d  mov     qword ptr [rsp+1B0h+var_170], r13
0x14001c792  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x14001c797  cmp     [rsi+0Bh], r13b
0x14001c79b  jz      loc_14001C821
0x14001c7a1  mov     cl, [rsi+8]
0x14001c7a4  cmp     cl, 42h ; 'B'
0x14001c7a7  jz      short loc_14001C7FF
0x14001c7a9  cmp     cl, 58h ; 'X'
0x14001c7ac  jz      short loc_14001C7F6
0x14001c7ae  cmp     cl, 62h ; 'b'
0x14001c7b1  jz      short loc_14001C7ED
0x14001c7b3  cmp     cl, 6Fh ; 'o'
0x14001c7b6  jz      short loc_14001C7C6
0x14001c7b8  cmp     cl, 78h ; 'x'
0x14001c7bb  jnz     short loc_14001C7DE
0x14001c7bd  lea     rcx, a0x; "0x"
0x14001c7c4  jmp     short loc_14001C806
0x14001c7c6  cmp     [rsp+1B0h+var_158], r13d
0x14001c7cb  jz      short loc_14001C7DE
0x14001c7cd  lea     rcx, a0; "0"
0x14001c7d4  mov     qword ptr [rsp+1B0h+var_170+8], r14
0x14001c7d9  mov     edi, r14d
0x14001c7dc  jmp     short loc_14001C80B
0x14001c7de  mov     qword ptr [rsp+1B0h+var_170], r13
0x14001c7e3  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x14001c7e8  mov     edi, r13d
0x14001c7eb  jmp     short loc_14001C810
0x14001c7ed  lea     rcx, a0b; "0b"
0x14001c7f4  jmp     short loc_14001C806
0x14001c7f6  lea     rcx, a0x_0; "0X"
0x14001c7fd  jmp     short loc_14001C806
0x14001c7ff  lea     rcx, a0b_0; "0B"
0x14001c806  mov     qword ptr [rsp+1B0h+var_170+8], rdi
0x14001c80b  mov     qword ptr [rsp+1B0h+var_170], rcx
0x14001c810  movaps  xmm0, [rsp+1B0h+var_170]
0x14001c815  movdqa  [rsp+1B0h+var_170], xmm0
0x14001c81b  add     eax, edi
0x14001c81d  mov     [rsp+1B0h+var_17C], eax
0x14001c821  mov     [rsp+1B0h+var_160], r13d
0x14001c826  xorps   xmm0, xmm0
0x14001c829  movups  [rbp+0B0h+var_D0], xmm0
0x14001c82d  mov     qword ptr [rbp+0B0h+var_C0], r13
0x14001c831  mov     qword ptr [rbp+0B0h+var_C0+8], 0Fh
0x14001c839  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x14001c83d  cmp     [rsi+0Ch], r13b
0x14001c841  jz      loc_14001C95A
0x14001c847  mov     rax, [rbp+0B0h+arg_20]
0x14001c84e  test    rax, rax
0x14001c851  jz      short loc_14001C86D
0x14001c853  mov     rdi, [rax+8]
0x14001c857  mov     qword ptr [rsp+1B0h+var_140+8], rdi
0x14001c85c  mov     rax, [rdi]
0x14001c85f  mov     rcx, rdi
0x14001c862  mov     rax, [rax+8]
0x14001c866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c86b  jmp     short loc_14001C87E
0x14001c86d  mov     cl, r14b
0x14001c870  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x14001c876  mov     rdi, rax
0x14001c879  mov     qword ptr [rsp+1B0h+var_140+8], rax
0x14001c87e  lea     rcx, [rsp+1B0h+var_140]
0x14001c883  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<ushort>>(std::locale const &)
0x14001c888  mov     r8, rax
0x14001c88b  mov     rcx, [rax]
0x14001c88e  mov     rax, [rcx+28h]
0x14001c892  lea     rdx, [rbp+0B0h+var_B0]
0x14001c896  mov     rcx, r8
0x14001c899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c89e  lea     rcx, [rbp+0B0h+var_D0]
0x14001c8a2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14001c8a7  movups  xmm0, [rbp+0B0h+var_B0]
0x14001c8ab  movups  [rbp+0B0h+var_D0], xmm0
0x14001c8af  movups  xmm1, [rbp+0B0h+var_A0]
0x14001c8b3  movups  [rbp+0B0h+var_C0], xmm1
0x14001c8b7  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x14001c8bf  movdqu  [rbp+0B0h+var_A0], xmm0
0x14001c8c4  mov     byte ptr [rbp+0B0h+var_B0], r13b
0x14001c8c8  lea     rcx, [rbp+0B0h+var_B0]
0x14001c8cc  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14001c8d1  nop
0x14001c8d2  test    rdi, rdi
0x14001c8d5  jz      short loc_14001C8FF
0x14001c8d7  mov     rax, [rdi]
0x14001c8da  mov     rcx, rdi
0x14001c8dd  mov     rax, [rax+10h]
0x14001c8e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c8e6  mov     r8, rax
0x14001c8e9  test    rax, rax
0x14001c8ec  jz      short loc_14001C8FF
0x14001c8ee  mov     rcx, [rax]
0x14001c8f1  mov     rax, [rcx]
0x14001c8f4  mov     edx, r14d
0x14001c8f7  mov     rcx, r8
0x14001c8fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c8ff  lea     rax, [rbp+0B0h+var_D0]
0x14001c903  cmp     qword ptr [rbp+0B0h+var_C0+8], 0Fh
0x14001c908  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x14001c90d  mov     r10, qword ptr [rbp+0B0h+var_C0]
0x14001c911  mov     edx, r13d
0x14001c914  test    r10, r10
0x14001c917  jz      short loc_14001C94C
0x14001c919  mov     r8, r12
0x14001c91c  sub     r8, [rsp+1B0h+var_150]
0x14001c921  movsx   r9, byte ptr [rax]
0x14001c925  cmp     r8, r9
0x14001c928  jbe     short loc_14001C94C
0x14001c92a  lea     r11, [r10+rax]
0x14001c92e  movsx   rcx, r9b
0x14001c932  sub     r8, rcx
0x14001c935  add     edx, r14d
0x14001c938  lea     rcx, [rax+1]
0x14001c93c  cmp     rcx, r11
0x14001c93f  cmovnz  rax, rcx
0x14001c943  movsx   r9, byte ptr [rax]
0x14001c947  cmp     r8, r9
0x14001c94a  ja      short loc_14001C92E
0x14001c94c  mov     [rsp+1B0h+var_160], edx
0x14001c950  mov     eax, [rsp+1B0h+var_17C]
0x14001c954  add     eax, edx
0x14001c956  mov     [rsp+1B0h+var_17C], eax
0x14001c95a  cmp     [rsi+0Dh], r13b
0x14001c95e  jz      short loc_14001C966
0x14001c960  cmp     [rsi+9], r13b
0x14001c964  jz      short loc_14001C969
0x14001c966  mov     r14b, r13b
0x14001c969  mov     [rsp+1B0h+var_180], r14b
0x14001c96e  mov     [rbp+0B0h+var_120], r12
0x14001c972  mov     [rbp+0B0h+var_118], rsi
0x14001c976  lea     rcx, [rsp+1B0h+var_158]
0x14001c97b  mov     [rbp+0B0h+var_110], rcx
0x14001c97f  lea     rcx, [rsp+1B0h+var_170]
0x14001c984  mov     [rbp+0B0h+var_108], rcx
0x14001c988  lea     rcx, [rsp+1B0h+var_180]
0x14001c98d  mov     [rbp+0B0h+var_100], rcx
0x14001c991  lea     rcx, [rsp+1B0h+var_17C]
0x14001c996  mov     [rbp+0B0h+var_F8], rcx
0x14001c99a  lea     rcx, [rsp+1B0h+var_160]
0x14001c99f  mov     [rbp+0B0h+var_F0], rcx
0x14001c9a3  lea     rcx, [rsp+1B0h+var_150]
0x14001c9a8  mov     [rbp+0B0h+var_E8], rcx
0x14001c9ac  lea     rcx, [rbp+0B0h+var_D0]
0x14001c9b0  mov     [rbp+0B0h+var_E0], rcx
0x14001c9b4  lea     rcx, [rbp+0B0h+arg_20]
0x14001c9bb  mov     [rbp+0B0h+var_D8], rcx
0x14001c9bf  lea     rcx, [rbp+0B0h+var_120]
0x14001c9c3  test    r14b, r14b
0x14001c9c6  jz      short loc_14001C9D5
0x14001c9c8  mov     r8, rbx
0x14001c9cb  mov     rdx, r15
0x14001c9ce  call    ??R_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@_K@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@1@V21@_KU?$_Basic_format_specs@G@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,unsigned __int64>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,unsigned __int64,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x14001c9d3  jmp     short loc_14001C9EC
0x14001c9d5  mov     [rsp+1B0h+var_188], rcx
0x14001c9da  mov     r9, rsi
0x14001c9dd  mov     r8d, eax
0x14001c9e0  mov     rdx, rbx
0x14001c9e3  mov     rcx, r15
0x14001c9e6  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@U?$_Basic_format_specs@G@2@AEAV_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@I@2@YA?AV12@V12@IU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@HAEBU?$_Basic_format_specs@G@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@I@0@YA?AV10@0IU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<ushort>>,std::_Basic_format_specs<ushort>,`std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int,std::_Basic_format_specs<ushort> const &,std::_Fmt_align,`std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x14001c9eb  nop
0x14001c9ec  lea     rcx, [rbp+0B0h+var_D0]
0x14001c9f0  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14001c9f5  mov     rax, r15
0x14001c9f8  mov     rcx, [rbp+0B0h+var_40]
0x14001c9fc  xor     rcx, rsp; StackCookie
0x14001c9ff  call    __security_check_cookie
0x14001ca04  mov     rbx, [rsp+1B0h+arg_8]
0x14001ca0c  add     rsp, 180h
0x14001ca13  pop     r15
0x14001ca15  pop     r14
0x14001ca17  pop     r13
0x14001ca19  pop     r12
0x14001ca1b  pop     rdi
0x14001ca1c  pop     rsi
0x14001ca1d  pop     rbp
0x14001ca1e  retn
0x14001ca1f  lea     rcx, aIntegralCannot; "integral cannot be stored in wchar_t"
0x14001ca26  call    ?_Throw_format_error@std@@YAXPEBD@Z; std::_Throw_format_error(char const *)
```

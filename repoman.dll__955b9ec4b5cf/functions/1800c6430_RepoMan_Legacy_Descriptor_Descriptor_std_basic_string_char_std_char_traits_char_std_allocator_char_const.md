# RepoMan::Legacy::Descriptor::Descriptor(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x1800c6430`
- end: `0x1800c693f`
- name: `??0Descriptor@Legacy@RepoMan@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `1295`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: ``

## callers

- `0x1800ced50`
- `0x1800cf530`

## callees

- `0x180008770`
- `0x180013b14`
- `0x180024a68`
- `0x18002f9b0`
- `0x18002febc`
- `0x18003a28c`
- `0x18003e358`
- `0x180045530`
- `0x1800c6430`
- `0x1800d6998`
- `0x1800dfffc`
- `0x180194664`
- `0x180198f88`
- `0x18019a840`
- `0x18019f800`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800c64b7`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800c64ef`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800c6527`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800c64b7`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800c64ef`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800c6527`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800c67d8`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800c6855`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800c68b3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800c67d8`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800c6855`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800c68b3`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800c671d`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800c67d1`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800c684b`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800c68ac`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800c671d`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800c67d1`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800c684b`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800c68ac`

## string_xrefs

- `0x1800c6914`: `Master descriptor does not have a proper culture`
- `0x1800c691b`: `src\repoman\src\inc\MasterDescriptor.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall RepoMan::Legacy::Descriptor::Descriptor(__int64 a1, __int64 *a2)
{
  __int64 *v2; // r14
  _QWORD *v4; // rax
  _QWORD *v5; // rax
  _QWORD *v6; // rax
  __int64 v7; // r8
  _QWORD *v8; // rax
  void **v9; // rdx
  __int64 v10; // rax
  __int64 v11; // r8
  unsigned __int64 v12; // rax
  _QWORD *v13; // r9
  void **v14; // rcx
  size_t v15; // rbx
  void *v16; // rsi
  void *v17; // rcx
  char *v18; // rbx
  char *v19; // rsi
  char *v20; // rcx
  void *v21; // rcx
  void *v23[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v24; // [rsp+48h] [rbp-B8h]
  void *v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+6Ch] [rbp-94h]
  _QWORD v28[3]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v29[128]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v30[3]; // [rsp+108h] [rbp+8h] BYREF
  int v31; // [rsp+120h] [rbp+20h]
  __int64 v32; // [rsp+128h] [rbp+28h]
  __int128 v33; // [rsp+130h] [rbp+30h]
  __int128 v34; // [rsp+140h] [rbp+40h]
  __int128 v35; // [rsp+150h] [rbp+50h]
  char v36; // [rsp+160h] [rbp+60h]
  void *v37[2]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int64 v38; // [rsp+180h] [rbp+80h]
  unsigned __int64 v39; // [rsp+188h] [rbp+88h]
  void *Block[2]; // [rsp+190h] [rbp+90h] BYREF
  __m128i si128; // [rsp+1A0h] [rbp+A0h]

  v2 = a2;
  v26 = a1;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  if ( (unsigned __int64)a2[3] > 0xF )
    a2 = (__int64 *)*a2;
  std::string::_Construct<2,char const *>((_QWORD *)a1, a2, v2[2]);
  v25 = (void *)(a1 + 32);
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  v4 = malloc(0x70u);
  if ( !v4 )
    std::_Xbad_alloc();
  *v4 = v4;
  v4[1] = v4;
  v4[2] = v4;
  *((_WORD *)v4 + 12) = 257;
  *(_QWORD *)(a1 + 32) = v4;
  v25 = (void *)(a1 + 48);
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  v5 = malloc(0x50u);
  if ( !v5 )
    std::_Xbad_alloc();
  *v5 = v5;
  v5[1] = v5;
  v5[2] = v5;
  *((_WORD *)v5 + 12) = 257;
  *(_QWORD *)(a1 + 48) = v5;
  v25 = (void *)(a1 + 64);
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  v6 = malloc(0x48u);
  if ( !v6 )
    std::_Xbad_alloc();
  *v6 = v6;
  v6[1] = v6;
  v6[2] = v6;
  *((_WORD *)v6 + 12) = 257;
  *(_QWORD *)(a1 + 64) = v6;
  *(_OWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 15;
  *(_BYTE *)(a1 + 88) = 0;
  *(_OWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 144) = 15;
  *(_BYTE *)(a1 + 120) = 0;
  *(_OWORD *)(a1 + 152) = 0;
  *(_QWORD *)(a1 + 168) = 0;
  *(_QWORD *)(a1 + 176) = 15;
  *(_BYTE *)(a1 + 152) = 0;
  v28[0] = &std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbtable'{for `std::istream'};
  v28[2] = &std::wostringstream::`vbtable';
  v30[1] = 0;
  v30[2] = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v30[0] = &std::ios_base::`vftable';
  v35 = 0;
  v36 = 0;
  std::iostream::basic_iostream<char>(v28, v29);
  *(_QWORD *)((char *)v28 + *(int *)(v28[0] + 4LL)) = &std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vftable';
  *(int *)((char *)&v27 + *(int *)(v28[0] + 4LL)) = *(_DWORD *)(v28[0] + 4LL) - 152;
  std::stringbuf::stringbuf(v29, v2, 3);
  *(_OWORD *)v37 = 0;
  v38 = 0;
  v39 = 15;
  LOBYTE(v37[0]) = 0;
  *(_OWORD *)v23 = 0;
  v24 = 0;
  while ( 1 )
  {
    LOBYTE(v7) = 46;
    v10 = std::getline<char,std::char_traits<char>,std::allocator<char>>(v28, v37, v7);
    if ( (*(_DWORD *)(*(int *)(*(_QWORD *)v10 + 4LL) + v10 + 16) & 6) != 0 )
      break;
    v8 = v23[1];
    if ( v23[1] == (void *)v24 )
    {
      std::vector<std::string>::_Emplace_reallocate<std::string const &>(v23, v23[1], v37);
    }
    else
    {
      v25 = v23[1];
      *(_OWORD *)v23[1] = 0;
      v8[2] = 0;
      v8[3] = 0;
      v9 = v37;
      if ( v39 > 0xF )
        v9 = (void **)v37[0];
      std::string::_Construct<2,char const *>(v8, v9, v38);
      v23[1] = (char *)v23[1] + 32;
    }
  }
  *(_OWORD *)Block = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)Block, "ship");
  v12 = ((char *)v23[1] - (char *)v23[0]) >> 5;
  if ( v12 <= 1 )
    RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
      76,
      (unsigned int)"src\\repoman\\src\\inc\\MasterDescriptor.hpp",
      (unsigned int)"Master descriptor does not have a proper culture",
      -1941503406,
      8);
  v13 = (char *)v23[0] + 32 * v12 - 64;
  v14 = (void **)(a1 + 152);
  if ( (_QWORD *)(a1 + 152) != v13 )
  {
    v15 = v13[2];
    if ( v13[3] > 0xFu )
      v13 = (_QWORD *)*v13;
    if ( v15 > *(_QWORD *)(a1 + 176) )
    {
      ____Reallocate_for_V_lambda_1___1__assign___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAAEAV34_QEBD_K_Z_PEBD___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__assign_01_QEAAAEAV01_QEBD0_Z_PEBD_Z(
        v14,
        v15,
        v11,
        v13);
    }
    else
    {
      v16 = (void *)(a1 + 152);
      if ( *(_QWORD *)(a1 + 176) > 0xFu )
        v16 = *v14;
      *(_QWORD *)(a1 + 168) = v15;
      memmove(v16, v13, v15);
      *((_BYTE *)v16 + v15) = 0;
    }
  }
  RepoMan::Legacy::Descriptor::LoadDocument(a1, Block);
  if ( si128.m128i_i64[1] > 0xFuLL )
  {
    v17 = Block[0];
    if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
    {
      v17 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v17 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v17);
  }
  v18 = (char *)v23[0];
  if ( v23[0] )
  {
    v19 = (char *)v23[1];
    if ( v23[0] != v23[1] )
    {
      do
      {
        std::string::_Tidy_deallocate(v18);
        *(_QWORD *)v18 = 19937;
        *((_QWORD *)v18 + 2) = 0;
        *((_QWORD *)v18 + 3) = 31;
        v18 += 32;
      }
      while ( v18 != v19 );
      v18 = (char *)v23[0];
    }
    v20 = v18;
    if ( ((v24 - (_QWORD)v18) & 0xFFFFFFFFFFFFFFE0uLL) >= 0x1000 )
    {
      v18 = (char *)*((_QWORD *)v18 - 1);
      if ( (unsigned __int64)(v20 - v18 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v18);
  }
  *(__m128i *)v23 = _mm_load_si128((const __m128i *)&_xmm);
  v24 = 19937;
  if ( v39 > 0xF )
  {
    v21 = v37[0];
    if ( v39 + 1 >= 0x1000 )
    {
      v21 = (void *)*((_QWORD *)v37[0] - 1);
      if ( (unsigned __int64)((char *)v37[0] - (char *)v21 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v21);
  }
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v30);
  v30[0] = &std::ios_base::`vftable';
  std::ios_base::_Ios_base_dtor((struct std::ios_base *)v30);
  return a1;
}

```

## disassembly

```asm
0x1800c6430  mov     [rsp-8+arg_10], rbx
0x1800c6435  push    rbp
0x1800c6436  push    rsi
0x1800c6437  push    rdi
0x1800c6438  push    r12
0x1800c643a  push    r13
0x1800c643c  push    r14
0x1800c643e  push    r15
0x1800c6440  lea     rbp, [rsp-0C0h]
0x1800c6448  sub     rsp, 1C0h
0x1800c644f  mov     rax, cs:__security_cookie
0x1800c6456  xor     rax, rsp
0x1800c6459  mov     [rbp+0F0h+var_40], rax
0x1800c6460  mov     r14, rdx
0x1800c6463  mov     rdi, rcx
0x1800c6466  mov     [rsp+1F0h+var_190], rcx
0x1800c646b  xor     r15d, r15d
0x1800c646e  mov     dword ptr [rsp+1F0h+var_1C0], r15d
0x1800c6473  mov     [rsp+1F0h+var_1C0], rcx
0x1800c6478  xorps   xmm0, xmm0
0x1800c647b  movups  xmmword ptr [rcx], xmm0
0x1800c647e  mov     [rcx+10h], r15
0x1800c6482  mov     [rcx+18h], r15
0x1800c6486  lea     r12d, [r15+0Fh]
0x1800c648a  cmp     [rdx+18h], r12
0x1800c648e  jbe     short loc_1800C6493
0x1800c6490  mov     rdx, [rdx]
0x1800c6493  mov     r8, [r14+10h]
0x1800c6497  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x1800c649c  nop
0x1800c649d  lea     rbx, [rdi+20h]
0x1800c64a1  mov     [rsp+1F0h+var_1C0], rbx
0x1800c64a6  mov     [rsp+1F0h+var_1A0], rbx
0x1800c64ab  mov     [rbx], r15
0x1800c64ae  mov     [rbx+8], r15
0x1800c64b2  mov     ecx, 70h ; 'p'; Size
0x1800c64b7  call    cs:__imp_malloc
0x1800c64bd  test    rax, rax
0x1800c64c0  jz      loc_1800C692D
0x1800c64c6  mov     [rax], rax
0x1800c64c9  mov     [rax+8], rax
0x1800c64cd  mov     [rax+10h], rax
0x1800c64d1  mov     word ptr [rax+18h], 101h
0x1800c64d7  mov     [rbx], rax
0x1800c64da  lea     rsi, [rbx+10h]
0x1800c64de  mov     [rsp+1F0h+var_1A0], rsi
0x1800c64e3  mov     [rsi], r15
0x1800c64e6  mov     [rsi+8], r15
0x1800c64ea  mov     ecx, 50h ; 'P'; Size
0x1800c64ef  call    cs:__imp_malloc
0x1800c64f5  test    rax, rax
0x1800c64f8  jz      loc_1800C6933
0x1800c64fe  mov     [rax], rax
0x1800c6501  mov     [rax+8], rax
0x1800c6505  mov     [rax+10h], rax
0x1800c6509  mov     word ptr [rax+18h], 101h
0x1800c650f  mov     [rsi], rax
0x1800c6512  lea     rsi, [rbx+20h]
0x1800c6516  mov     [rsp+1F0h+var_1A0], rsi
0x1800c651b  mov     [rsi], r15
0x1800c651e  mov     [rsi+8], r15
0x1800c6522  mov     ecx, 48h ; 'H'; Size
0x1800c6527  call    cs:__imp_malloc
0x1800c652d  test    rax, rax
0x1800c6530  jz      loc_1800C6939
0x1800c6536  mov     [rax], rax
0x1800c6539  mov     [rax+8], rax
0x1800c653d  mov     [rax+10h], rax
0x1800c6541  mov     word ptr [rax+18h], 101h
0x1800c6547  mov     [rsi], rax
0x1800c654a  xorps   xmm0, xmm0
0x1800c654d  movups  xmmword ptr [rbx+38h], xmm0
0x1800c6551  mov     [rbx+48h], r15
0x1800c6555  mov     [rbx+50h], r12
0x1800c6559  mov     [rbx+38h], r15b
0x1800c655d  movups  xmmword ptr [rbx+58h], xmm0
0x1800c6561  mov     [rbx+68h], r15
0x1800c6565  mov     [rbx+70h], r12
0x1800c6569  mov     [rbx+58h], r15b
0x1800c656d  movups  xmmword ptr [rbx+78h], xmm0
0x1800c6571  mov     [rbx+88h], r15
0x1800c6578  mov     [rbx+90h], r12
0x1800c657f  mov     [rbx+78h], r15b
0x1800c6583  lea     rax, ??_8?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@7B?$basic_istream@DU?$char_traits@D@std@@@1@@; const std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbtable'{for `std::istream'}
0x1800c658a  mov     [rsp+1F0h+var_180], rax
0x1800c658f  lea     rax, ??_8?$basic_ostringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@7B@; const std::wostringstream::`vbtable'
0x1800c6596  mov     [rbp+0F0h+var_170], rax
0x1800c659a  mov     [rbp+0F0h+var_E0], r15
0x1800c659e  mov     [rbp+0F0h+var_D8], r15
0x1800c65a2  mov     [rbp+0F0h+var_D0], r15d
0x1800c65a6  mov     [rbp+0F0h+var_C8], r15
0x1800c65aa  movdqa  [rbp+0F0h+var_C0], xmm0
0x1800c65af  xorps   xmm1, xmm1
0x1800c65b2  movdqa  [rbp+0F0h+var_B0], xmm1
0x1800c65b7  lea     rax, ??_7ios_base@std@@6B@; const std::ios_base::`vftable'
0x1800c65be  mov     [rbp+0F0h+var_E8], rax
0x1800c65c2  movdqa  [rbp+0F0h+var_A0], xmm0
0x1800c65c7  mov     [rbp+0F0h+var_90], r15b
0x1800c65cb  mov     dword ptr [rsp+1F0h+var_1C0], 1
0x1800c65d3  lea     rdx, [rbp+0F0h+var_168]
0x1800c65d7  lea     rcx, [rsp+1F0h+var_180]
0x1800c65dc  call    ??0?$basic_iostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@@Z; std::iostream::basic_iostream<char>(std::streambuf *)
0x1800c65e1  nop
0x1800c65e2  mov     rax, [rsp+1F0h+var_180]
0x1800c65e7  movsxd  rcx, dword ptr [rax+4]
0x1800c65eb  lea     rax, ??_7?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@6B@; const std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vftable'
0x1800c65f2  mov     [rsp+rcx+1F0h+var_180], rax
0x1800c65f7  mov     rax, [rsp+1F0h+var_180]
0x1800c65fc  movsxd  rcx, dword ptr [rax+4]
0x1800c6600  lea     r8d, [rcx-98h]
0x1800c6607  mov     [rsp+rcx+1F0h+var_184], r8d
0x1800c660c  mov     r8d, 3
0x1800c6612  mov     rdx, r14
0x1800c6615  lea     rcx, [rbp+0F0h+var_168]
0x1800c6619  call    ??0?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@H@Z; std::stringbuf::stringbuf(std::string const &,int)
0x1800c661e  nop
0x1800c661f  xorps   xmm0, xmm0
0x1800c6622  movups  xmmword ptr [rbp+0F0h+var_80], xmm0
0x1800c6626  mov     [rbp+0F0h+var_70], r15
0x1800c662d  mov     [rbp+0F0h+var_68], r12
0x1800c6634  mov     byte ptr [rbp+0F0h+var_80], r15b
0x1800c6638  movdqu  xmmword ptr [rsp+1F0h+var_1B8], xmm0
0x1800c663e  mov     [rsp+1F0h+var_1A8], r15
0x1800c6643  jmp     short loc_1800C669D
0x1800c6645  mov     rax, [rsp+1F0h+var_1B8+8]
0x1800c664a  cmp     rax, [rsp+1F0h+var_1A8]
0x1800c664f  jz      short loc_1800C668C
0x1800c6651  mov     [rsp+1F0h+var_1A0], rax
0x1800c6656  xorps   xmm0, xmm0
0x1800c6659  movups  xmmword ptr [rax], xmm0
0x1800c665c  mov     [rax+10h], r15
0x1800c6660  mov     [rax+18h], r15
0x1800c6664  lea     rdx, [rbp+0F0h+var_80]
0x1800c6668  cmp     [rbp+0F0h+var_68], r12
0x1800c666f  cmova   rdx, [rbp+0F0h+var_80]
0x1800c6674  mov     r8, [rbp+0F0h+var_70]
0x1800c667b  mov     rcx, rax
0x1800c667e  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x1800c6683  nop
0x1800c6684  add     [rsp+1F0h+var_1B8+8], 20h ; ' '
0x1800c668a  jmp     short loc_1800C669D
0x1800c668c  lea     r8, [rbp+0F0h+var_80]
0x1800c6690  mov     rdx, rax
0x1800c6693  lea     rcx, [rsp+1F0h+var_1B8]
0x1800c6698  call    ??$_Emplace_reallocate@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAPEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@QEAV21@AEBV21@@Z; std::vector<std::string>::_Emplace_reallocate<std::string const &>(std::string * const,std::string const &)
0x1800c669d  mov     r8b, 2Eh ; '.'
0x1800c66a0  lea     rdx, [rbp+0F0h+var_80]
0x1800c66a4  lea     rcx, [rsp+1F0h+var_180]
0x1800c66a9  call    ??$getline@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@YAAEAV?$basic_istream@DU?$char_traits@D@std@@@0@$$QEAV10@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@D@Z; std::getline<char,std::char_traits<char>,std::allocator<char>>(std::istream &&,std::string &,char)
0x1800c66ae  mov     rdx, rax
0x1800c66b1  mov     rax, [rax]
0x1800c66b4  movsxd  rcx, dword ptr [rax+4]
0x1800c66b8  test    dword ptr [rcx+rdx+10h], 6
0x1800c66c0  jz      short loc_1800C6645
0x1800c66c2  xorps   xmm0, xmm0
0x1800c66c5  movups  xmmword ptr [rbp+0F0h+Block], xmm0
0x1800c66cc  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000004
0x1800c66d4  movdqu  [rbp+0F0h+var_50], xmm0
0x1800c66dc  mov     dword ptr [rbp+0F0h+Block], 70696873h
0x1800c66e6  mov     byte ptr [rbp+0F0h+Block+4], r15b
0x1800c66ed  mov     rax, [rsp+1F0h+var_1B8+8]
0x1800c66f2  sub     rax, [rsp+1F0h+var_1B8]
0x1800c66f7  sar     rax, 5
0x1800c66fb  cmp     rax, 1
0x1800c66ff  jbe     loc_1800C6906
0x1800c6705  lea     r9, [rax-2]
0x1800c6709  cmp     r9, rax
0x1800c670c  jb      short loc_1800C6724
0x1800c670e  mov     [rsp+1F0h+Reserved], r15; Reserved
0x1800c6713  xor     r9d, r9d; LineNo
0x1800c6716  xor     r8d, r8d; FileName
0x1800c6719  xor     edx, edx; FunctionName
0x1800c671b  xor     ecx, ecx; Expression
0x1800c671d  call    cs:__imp__invoke_watson
0x1800c6724  shl     r9, 5
0x1800c6728  add     r9, [rsp+1F0h+var_1B8]
0x1800c672d  lea     rcx, [rdi+98h]
0x1800c6734  cmp     rcx, r9
0x1800c6737  jz      short loc_1800C6778
0x1800c6739  mov     rbx, [r9+10h]
0x1800c673d  cmp     [r9+18h], r12
0x1800c6741  jbe     short loc_1800C6746
0x1800c6743  mov     r9, [r9]
0x1800c6746  cmp     rbx, [rcx+18h]
0x1800c674a  ja      short loc_1800C6770
0x1800c674c  mov     rsi, rcx
0x1800c674f  cmp     [rcx+18h], r12
0x1800c6753  jbe     short loc_1800C6758
0x1800c6755  mov     rsi, [rcx]
0x1800c6758  mov     [rcx+10h], rbx
0x1800c675c  mov     r8, rbx; Size
0x1800c675f  mov     rdx, r9; Src
0x1800c6762  mov     rcx, rsi; void *
0x1800c6765  call    memmove
0x1800c676a  mov     [rbx+rsi], r15b
0x1800c676e  jmp     short loc_1800C6778
0x1800c6770  mov     rdx, rbx
0x1800c6773  call    ??$_Reallocate_for@V_lambda_1_@?1??assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV34@QEBD_K@Z@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??assign@01@QEAAAEAV01@QEBD0@Z@PEBD@Z; std::string::_Reallocate_for<`std::string::assign(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *>(unsigned __int64,`std::string::assign(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *)
0x1800c6778  lea     rdx, [rbp+0F0h+Block]
0x1800c677f  mov     rcx, rdi
0x1800c6782  call    ?LoadDocument@Descriptor@Legacy@RepoMan@@AEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; RepoMan::Legacy::Descriptor::LoadDocument(std::string const &)
0x1800c6787  nop
0x1800c6788  mov     r13d, 1000h
0x1800c678e  mov     r14d, 1Fh
0x1800c6794  mov     rax, qword ptr [rbp+0F0h+var_50+8]
0x1800c679b  cmp     rax, r12
0x1800c679e  jbe     short loc_1800C67DF
0x1800c67a0  mov     rcx, [rbp+0F0h+Block]; Block
0x1800c67a7  mov     rdx, rcx
0x1800c67aa  inc     rax
0x1800c67ad  cmp     rax, r13
0x1800c67b0  jb      short loc_1800C67D8
0x1800c67b2  mov     rcx, [rcx-8]
0x1800c67b6  sub     rdx, rcx
0x1800c67b9  lea     rax, [rdx-8]
0x1800c67bd  cmp     rax, r14
0x1800c67c0  jbe     short loc_1800C67D8
0x1800c67c2  mov     [rsp+1F0h+Reserved], r15; Reserved
0x1800c67c7  xor     r9d, r9d; LineNo
0x1800c67ca  xor     r8d, r8d; FileName
0x1800c67cd  xor     edx, edx; FunctionName
0x1800c67cf  xor     ecx, ecx; Expression
0x1800c67d1  call    cs:__imp__invoke_watson
0x1800c67d8  call    cs:__imp_free
0x1800c67de  nop
0x1800c67df  mov     rbx, [rsp+1F0h+var_1B8]
0x1800c67e4  test    rbx, rbx
0x1800c67e7  jz      short loc_1800C685B
0x1800c67e9  mov     rsi, [rsp+1F0h+var_1B8+8]
0x1800c67ee  cmp     rbx, rsi
0x1800c67f1  jz      short loc_1800C6818
0x1800c67f3  mov     rcx, rbx
0x1800c67f6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800c67fb  mov     qword ptr [rbx], 4DE1h
0x1800c6802  mov     [rbx+10h], r15
0x1800c6806  mov     [rbx+18h], r14
0x1800c680a  add     rbx, 20h ; ' '
0x1800c680e  cmp     rbx, rsi
0x1800c6811  jnz     short loc_1800C67F3
0x1800c6813  mov     rbx, [rsp+1F0h+var_1B8]
0x1800c6818  mov     rax, [rsp+1F0h+var_1A8]
0x1800c681d  sub     rax, rbx
0x1800c6820  mov     rcx, rbx
0x1800c6823  and     rax, 0FFFFFFFFFFFFFFE0h
0x1800c6827  cmp     rax, r13
0x1800c682a  jb      short loc_1800C6852
0x1800c682c  mov     rbx, [rbx-8]
0x1800c6830  sub     rcx, rbx
0x1800c6833  lea     rax, [rcx-8]
0x1800c6837  cmp     rax, r14
0x1800c683a  jbe     short loc_1800C6852
0x1800c683c  mov     [rsp+1F0h+Reserved], r15; Reserved
0x1800c6841  xor     r9d, r9d; LineNo
0x1800c6844  xor     r8d, r8d; FileName
0x1800c6847  xor     edx, edx; FunctionName
0x1800c6849  xor     ecx, ecx; Expression
0x1800c684b  call    cs:__imp__invoke_watson
0x1800c6852  mov     rcx, rbx; Block
0x1800c6855  call    cs:__imp_free
0x1800c685b  movdqa  xmm0, cs:__xmm@0000000000004de10000000000004de1
0x1800c6863  movdqu  xmmword ptr [rsp+1F0h+var_1B8], xmm0
0x1800c6869  mov     [rsp+1F0h+var_1A8], 4DE1h
0x1800c6872  mov     rax, [rbp+0F0h+var_68]
0x1800c6879  cmp     rax, r12
0x1800c687c  jbe     short loc_1800C68BA
0x1800c687e  mov     rcx, [rbp+0F0h+var_80]; Block
0x1800c6882  mov     rdx, rcx
0x1800c6885  inc     rax
0x1800c6888  cmp     rax, r13
0x1800c688b  jb      short loc_1800C68B3
0x1800c688d  mov     rcx, [rcx-8]
0x1800c6891  sub     rdx, rcx
0x1800c6894  lea     rax, [rdx-8]
0x1800c6898  cmp     rax, r14
0x1800c689b  jbe     short loc_1800C68B3
0x1800c689d  mov     [rsp+1F0h+Reserved], r15; Reserved
0x1800c68a2  xor     r9d, r9d; LineNo
0x1800c68a5  xor     r8d, r8d; FileName
0x1800c68a8  xor     edx, edx; FunctionName
0x1800c68aa  xor     ecx, ecx; Expression
0x1800c68ac  call    cs:__imp__invoke_watson
0x1800c68b3  call    cs:__imp_free
0x1800c68b9  nop
0x1800c68ba  lea     rcx, [rbp+0F0h+var_E8]
0x1800c68be  call    ??1?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x1800c68c3  nop
0x1800c68c4  lea     rax, ??_7ios_base@std@@6B@; const std::ios_base::`vftable'
0x1800c68cb  mov     [rbp+0F0h+var_E8], rax
0x1800c68cf  lea     rcx, [rbp+0F0h+var_E8]; this
0x1800c68d3  call    ?_Ios_base_dtor@ios_base@std@@CAXPEAV12@@Z; std::ios_base::_Ios_base_dtor(std::ios_base *)
0x1800c68d8  nop
0x1800c68d9  mov     rax, rdi
0x1800c68dc  mov     rcx, [rbp+0F0h+var_40]
0x1800c68e3  xor     rcx, rsp; StackCookie
0x1800c68e6  call    __security_check_cookie
0x1800c68eb  mov     rbx, [rsp+1F0h+arg_10]
0x1800c68f3  add     rsp, 1C0h
0x1800c68fa  pop     r15
0x1800c68fc  pop     r14
0x1800c68fe  pop     r13
  ... truncated ...
```

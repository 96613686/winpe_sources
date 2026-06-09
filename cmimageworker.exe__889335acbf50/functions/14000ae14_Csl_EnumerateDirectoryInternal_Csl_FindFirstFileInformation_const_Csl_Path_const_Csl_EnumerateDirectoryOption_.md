# Csl::EnumerateDirectoryInternal(Csl::FindFirstFileInformation const &,Csl::Path const &,Csl::EnumerateDirectoryOption,ushort const *,utl::vector<Csl::Path,utl::allocator<Csl::Path>> &)

- ea: `0x14000ae14`
- end: `0x14000b2e3`
- name: `?EnumerateDirectoryInternal@Csl@@YAJAEBUFindFirstFileInformation@1@AEBVPath@1@W4EnumerateDirectoryOption@1@PEBGAEAV?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@@Z`
- size: `1231`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x14000b2ec`

## callees

- `0x140002344`
- `0x140006fe4`
- `0x140008f90`
- `0x14000a5c4`
- `0x14000a9b8`
- `0x14000ae14`
- `0x14000b2ec`
- `0x14000c7a8`
- `0x14000ca50`
- `0x14000cd84`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14000b15c`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14000b15c`

## pseudocode

```c
__int64 __fastcall Csl::EnumerateDirectoryInternal(__int64 a1, __int64 a2, int a3, __int64 a4, __int64 *a5)
{
  __int64 *v5; // rbx
  struct _WIN32_FIND_DATAW *v6; // r15
  _WORD *v7; // r14
  __m128i si128; // xmm6
  __int64 v10; // rdi
  __int64 v12; // r8
  const void *v13; // rdx
  __int64 v14; // rax
  const void *v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rax
  int v18; // eax
  unsigned int v19; // ebx
  __int64 *v20; // r9
  _QWORD *v21; // rdi
  _QWORD *v22; // rbx
  unsigned __int64 v23; // r8
  unsigned __int64 v24; // rax
  unsigned __int64 v25; // rdx
  unsigned __int64 v26; // rax
  const char *v27; // r9
  bool v28; // zf
  __int64 v29; // rdx
  __int64 v30; // rax
  _WORD *v31; // rcx
  _WORD *v32; // rax
  __int64 v34; // rdx
  __int64 v35; // rdx
  int v36; // [rsp+28h] [rbp-B1h]
  void *v37[2]; // [rsp+38h] [rbp-A1h] BYREF
  _WORD v38[8]; // [rsp+48h] [rbp-91h] BYREF
  void *v39[2]; // [rsp+58h] [rbp-81h] BYREF
  _WORD v40[8]; // [rsp+68h] [rbp-71h] BYREF
  void *v41[2]; // [rsp+78h] [rbp-61h] BYREF
  _WORD v42[8]; // [rsp+88h] [rbp-51h] BYREF
  __m128i v43; // [rsp+98h] [rbp-41h] BYREF
  __int64 v44; // [rsp+A8h] [rbp-31h]
  _QWORD v45[2]; // [rsp+B0h] [rbp-29h] BYREF
  _QWORD v46[2]; // [rsp+C0h] [rbp-19h] BYREF
  _QWORD v47[5]; // [rsp+D0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+130h] [rbp+57h]
  __int64 v49; // [rsp+140h] [rbp+67h]

  v49 = a2;
  v5 = a5;
  v6 = (struct _WIN32_FIND_DATAW *)(a1 + 8);
  v7 = (_WORD *)(a1 + 52);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v10 = a4;
  while ( 1 )
  {
    if ( *v7 == 46 && (!v6->cFileName[1] || v6->cFileName[1] == 46 && !v6->cFileName[2]) )
      goto LABEL_48;
    if ( (a3 & 4) != 0 )
      break;
LABEL_34:
    if ( (v6->dwFileAttributes & 0x10) != 0 )
    {
      v28 = (a3 & 2) == 0;
      goto LABEL_37;
    }
LABEL_36:
    v28 = (a3 & 8) == 0;
LABEL_37:
    if ( !v28 )
    {
      v40[0] = 0;
      v39[0] = v40;
      v39[1] = v40;
      if ( (a3 & 1) != 0 )
      {
        if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                (__int64)v39,
                *(const void **)(a1 + 600),
                (__int64)(*(_QWORD *)(a1 + 608) - *(_QWORD *)(a1 + 600)) >> 1) )
        {
          v29 = 881;
LABEL_68:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v29,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
            (const char *)0x8007000ELL,
            v36);
          v31 = v39[0];
          v32 = v40;
          goto LABEL_69;
        }
      }
      else if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                   (__int64)v39,
                   *(const void **)a2,
                   (__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 1) )
      {
        v29 = 885;
        goto LABEL_68;
      }
      v47[0] = v7;
      v30 = -1;
      do
        ++v30;
      while ( v7[v30] );
      v47[1] = v30;
      if ( !Csl::Path::Append((Csl::Path *)v39, v47) )
      {
        v29 = 888;
        goto LABEL_68;
      }
      if ( !utl::vector<Csl::Path,utl::allocator<Csl::Path>>::emplace_back<Csl::Path,0>(v5, v39) )
      {
        v29 = 890;
        goto LABEL_68;
      }
      if ( v39[0] != v40 )
        operator delete(v39[0], (const struct std::nothrow_t *)&std::nothrow);
    }
LABEL_48:
    if ( !FindNextFileW(*(HANDLE *)a1, v6) )
      return 0;
    a2 = v49;
  }
  if ( (v6->dwFileAttributes & 0x10) == 0 )
    goto LABEL_36;
  v12 = *(_QWORD *)(a2 + 8) - *(_QWORD *)a2;
  v13 = *(const void **)a2;
  v37[0] = v38;
  v37[1] = v38;
  v38[0] = 0;
  if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
          (__int64)v37,
          v13,
          v12 >> 1) )
  {
    v35 = 840;
LABEL_63:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
      (const char *)0x8007000ELL,
      v36);
    goto LABEL_53;
  }
  v45[0] = v7;
  v14 = -1;
  do
    ++v14;
  while ( v7[v14] );
  v45[1] = v14;
  if ( !Csl::Path::Append((Csl::Path *)v37, v45) )
  {
    v35 = 841;
    goto LABEL_63;
  }
  v15 = *(const void **)(a1 + 600);
  v16 = *(_QWORD *)(a1 + 608);
  v41[0] = v42;
  v41[1] = v42;
  v42[0] = 0;
  if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
          (__int64)v41,
          v15,
          (v16 - (__int64)v15) >> 1) )
  {
    v34 = 845;
LABEL_60:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v34,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
      (const char *)0x8007000ELL,
      v36);
    goto LABEL_51;
  }
  v46[0] = v7;
  v17 = -1;
  do
    ++v17;
  while ( v7[v17] );
  v46[1] = v17;
  if ( !Csl::Path::Append((Csl::Path *)v41, v46) )
  {
    v34 = 846;
    goto LABEL_60;
  }
  v44 = -1;
  v43 = si128;
  v18 = Csl::EnumerateDirectoryInternal((unsigned int)v41, (unsigned int)v37, a3, (unsigned int)&v43, v10);
  v19 = v18;
  if ( v18 >= 0 )
  {
    v20 = a5;
    v21 = (_QWORD *)v43.m128i_i64[1];
    v22 = (_QWORD *)v43.m128i_i64[0];
    v23 = ((v43.m128i_i64[1] - v43.m128i_i64[0]) >> 5) + ((a5[1] - *a5) >> 5);
    v24 = (a5[2] - *a5) >> 5;
    if ( v23 > v24 )
    {
      v25 = ((v43.m128i_i64[1] - v43.m128i_i64[0]) >> 5) + ((a5[1] - *a5) >> 5);
      v26 = 7 * (v24 >> 2) + 8;
      if ( v26 >= v23 )
        v25 = v26;
      if ( v25 > 0x3FFFFFFFFFFFFFFLL )
        v25 = 0x3FFFFFFFFFFFFFFLL;
      if ( v23 <= v25 && utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_SetCapacity(a5, v25) )
      {
        v21 = (_QWORD *)v43.m128i_i64[1];
        v22 = (_QWORD *)v43.m128i_i64[0];
        goto LABEL_25;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x358,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
        (const char *)0x8007000ELL,
        v36);
      utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&v43);
LABEL_51:
      if ( v41[0] != v42 )
        operator delete(v41[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_53:
      v31 = v37[0];
      v32 = v38;
LABEL_69:
      if ( v31 != v32 )
        operator delete(v31, (const struct std::nothrow_t *)&std::nothrow);
      return 2147942414LL;
    }
    while ( v22 != v21 )
    {
      if ( !utl::vector<Csl::Path,utl::allocator<Csl::Path>>::emplace_back<Csl::Path,0>(v20, v22) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x35B,
          (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
          v27);
      v22 += 4;
LABEL_25:
      v20 = a5;
    }
    utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&v43);
    if ( v41[0] != v42 )
      operator delete(v41[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v37[0] != v38 )
      operator delete(v37[0], (const struct std::nothrow_t *)&std::nothrow);
    v10 = a4;
    a2 = v49;
    v5 = a5;
    goto LABEL_34;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x355,
    (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
    (const char *)(unsigned int)v18,
    v36);
  utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&v43);
  if ( v41[0] != v42 )
    operator delete(v41[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v37[0] != v38 )
    operator delete(v37[0], (const struct std::nothrow_t *)&std::nothrow);
  return v19;
}

```

## disassembly

```asm
0x14000ae14  mov     rax, rsp
0x14000ae17  mov     [rax+8], rbx
0x14000ae1b  mov     [rax+20h], r9
0x14000ae1f  mov     [rax+10h], rdx
0x14000ae23  push    rbp
0x14000ae24  push    rsi
0x14000ae25  push    rdi
0x14000ae26  push    r12
0x14000ae28  push    r13
0x14000ae2a  push    r14
0x14000ae2c  push    r15
0x14000ae2e  lea     rbp, [rax-57h]
0x14000ae32  sub     rsp, 0F0h
0x14000ae39  mov     rbx, [rbp+4Fh+arg_20]
0x14000ae3d  lea     r15, [rcx+8]
0x14000ae41  movaps  xmmword ptr [rax-48h], xmm6
0x14000ae45  lea     r14, [r15+2Ch]
0x14000ae49  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14000ae51  lea     rsi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14000ae58  mov     r13, rcx
0x14000ae5b  mov     rdi, r9
0x14000ae5e  mov     r12d, r8d
0x14000ae61  xor     ecx, ecx
0x14000ae63  cmp     word ptr [r14], 2Eh ; '.'
0x14000ae68  jnz     short loc_14000AE88
0x14000ae6a  cmp     [r15+2Eh], cx
0x14000ae6f  jz      loc_14000B155
0x14000ae75  cmp     word ptr [r15+2Eh], 2Eh ; '.'
0x14000ae7b  jnz     short loc_14000AE88
0x14000ae7d  cmp     [r15+30h], cx
0x14000ae82  jz      loc_14000B155
0x14000ae88  test    r12b, 4
0x14000ae8c  jz      loc_14000B083
0x14000ae92  test    byte ptr [r15], 10h
0x14000ae96  jz      loc_14000B08F
0x14000ae9c  mov     r8, [rdx+8]
0x14000aea0  lea     rax, [rsp+120h+var_E0]
0x14000aea5  sub     r8, [rdx]
0x14000aea8  lea     rcx, [rsp+120h+var_F0]
0x14000aead  mov     rdx, [rdx]
0x14000aeb0  xor     ebx, ebx
0x14000aeb2  mov     [rsp+120h+var_F0], rax
0x14000aeb7  lea     rax, [rsp+120h+var_E0]
0x14000aebc  sar     r8, 1
0x14000aebf  mov     qword ptr [rsp+120h+var_E8], rax
0x14000aec4  mov     [rsp+120h+var_E0], bx
0x14000aec9  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x14000aece  test    al, al
0x14000aed0  jz      loc_14000B25E
0x14000aed6  mov     [rbp+4Fh+var_78], r14
0x14000aeda  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000aede  inc     rax
0x14000aee1  cmp     [r14+rax*2], bx
0x14000aee6  jnz     short loc_14000AEDE
0x14000aee8  lea     rdx, [rbp+4Fh+var_78]
0x14000aeec  mov     [rbp+4Fh+var_70], rax
0x14000aef0  lea     rcx, [rsp+120h+var_F0]; this
0x14000aef5  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x14000aefa  test    al, al
0x14000aefc  jz      loc_14000B23E
0x14000af02  mov     rdx, [r13+258h]
0x14000af09  lea     rax, [rbp+4Fh+var_A0]
0x14000af0d  mov     r8, [r13+260h]
0x14000af14  lea     rcx, [rbp+4Fh+var_B0]
0x14000af18  mov     [rbp+4Fh+var_B0], rax
0x14000af1c  sub     r8, rdx
0x14000af1f  lea     rax, [rbp+4Fh+var_A0]
0x14000af23  sar     r8, 1
0x14000af26  mov     [rbp+4Fh+var_A8], rax
0x14000af2a  mov     [rbp+4Fh+var_A0], bx
0x14000af2e  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x14000af33  test    al, al
0x14000af35  jz      loc_14000B237
0x14000af3b  mov     [rbp+4Fh+var_68], r14
0x14000af3f  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000af43  inc     rax
0x14000af46  cmp     [r14+rax*2], bx
0x14000af4b  jnz     short loc_14000AF43
0x14000af4d  lea     rdx, [rbp+4Fh+var_68]
0x14000af51  mov     [rbp+4Fh+var_60], rax
0x14000af55  lea     rcx, [rbp+4Fh+var_B0]; this
0x14000af59  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x14000af5e  test    al, al
0x14000af60  jz      loc_14000B217
0x14000af66  lea     r9, [rbp+4Fh+var_90]
0x14000af6a  mov     [rbp+4Fh+var_80], 0FFFFFFFFFFFFFFFFh
0x14000af72  mov     r8d, r12d
0x14000af75  mov     qword ptr [rsp+120h+var_100], rdi; int
0x14000af7a  lea     rdx, [rsp+120h+var_F0]
0x14000af7f  lea     rcx, [rbp+4Fh+var_B0]
0x14000af83  movdqu  [rbp+4Fh+var_90], xmm6
0x14000af88  call    ?EnumerateDirectoryInternal@Csl@@YAJAEBVPath@1@0W4EnumerateDirectoryOption@1@AEAV?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@PEBG@Z; Csl::EnumerateDirectoryInternal(Csl::Path const &,Csl::Path const &,Csl::EnumerateDirectoryOption,utl::vector<Csl::Path,utl::allocator<Csl::Path>> &,ushort const *)
0x14000af8d  mov     ebx, eax
0x14000af8f  test    eax, eax
0x14000af91  js      loc_14000B1C3
0x14000af97  mov     r9, [rbp+4Fh+arg_20]
0x14000af9b  mov     rdi, qword ptr [rbp+4Fh+var_90+8]
0x14000af9f  mov     rbx, qword ptr [rbp+4Fh+var_90]
0x14000afa3  mov     rax, rdi
0x14000afa6  sub     rax, rbx
0x14000afa9  mov     r8, [r9+8]
0x14000afad  sub     r8, [r9]
0x14000afb0  sar     rax, 5
0x14000afb4  sar     r8, 5
0x14000afb8  add     r8, rax
0x14000afbb  mov     rax, [r9+10h]
0x14000afbf  sub     rax, [r9]
0x14000afc2  sar     rax, 5
0x14000afc6  cmp     r8, rax
0x14000afc9  jbe     short loc_14000B017
0x14000afcb  shr     rax, 2
0x14000afcf  mov     rdx, r8
0x14000afd2  imul    rax, 7
0x14000afd6  add     rax, 8
0x14000afda  cmp     rax, r8
0x14000afdd  cmovnb  rdx, rax
0x14000afe1  mov     rax, 3FFFFFFFFFFFFFFh
0x14000afeb  cmp     rdx, rax
0x14000afee  cmova   rdx, rax
0x14000aff2  cmp     r8, rdx
0x14000aff5  ja      loc_14000B17B
0x14000affb  mov     rcx, r9
0x14000affe  call    ?_SetCapacity@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_SetCapacity(unsigned __int64)
0x14000b003  test    al, al
0x14000b005  jz      loc_14000B17B
0x14000b00b  mov     rdi, qword ptr [rbp+4Fh+var_90+8]
0x14000b00f  mov     rbx, qword ptr [rbp+4Fh+var_90]
0x14000b013  mov     r9, [rbp+4Fh+arg_20]
0x14000b017  cmp     rbx, rdi
0x14000b01a  jz      short loc_14000B039
0x14000b01c  mov     rsi, [rbp+57h]
0x14000b020  mov     rdx, rbx
0x14000b023  mov     rcx, r9
0x14000b026  call    ??$emplace_back@VPath@Csl@@$0A@@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@QEAA_N$$QEAVPath@Csl@@@Z; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::emplace_back<Csl::Path,0>(Csl::Path &&)
0x14000b02b  test    al, al
0x14000b02d  jz      loc_14000B2CE
0x14000b033  add     rbx, 20h ; ' '
0x14000b037  jmp     short loc_14000B013
0x14000b039  lea     rcx, [rbp+4Fh+var_90]
0x14000b03d  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x14000b042  mov     rcx, [rbp+4Fh+var_B0]; void *
0x14000b046  lea     rax, [rbp+4Fh+var_A0]
0x14000b04a  lea     rsi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14000b051  cmp     rcx, rax
0x14000b054  jz      short loc_14000B05E
0x14000b056  mov     rdx, rsi; struct std::nothrow_t *
0x14000b059  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000b05e  mov     rcx, [rsp+120h+var_F0]; void *
0x14000b063  lea     rax, [rsp+120h+var_E0]
0x14000b068  cmp     rcx, rax
0x14000b06b  jz      short loc_14000B075
0x14000b06d  mov     rdx, rsi; struct std::nothrow_t *
0x14000b070  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000b075  mov     rdi, [rbp+4Fh+arg_18]
0x14000b079  xor     ecx, ecx
0x14000b07b  mov     rdx, [rbp+4Fh+arg_8]
0x14000b07f  mov     rbx, [rbp+4Fh+arg_20]
0x14000b083  test    byte ptr [r15], 10h
0x14000b087  jz      short loc_14000B08F
0x14000b089  test    r12b, 2
0x14000b08d  jmp     short loc_14000B093
0x14000b08f  test    r12b, 8
0x14000b093  jz      loc_14000B155
0x14000b099  mov     [rbp+4Fh+var_C0], cx
0x14000b09d  lea     rax, [rbp+4Fh+var_C0]
0x14000b0a1  mov     [rsp+120h+var_D0], rax
0x14000b0a6  lea     rax, [rbp+4Fh+var_C0]
0x14000b0aa  mov     [rbp+4Fh+var_C8], rax
0x14000b0ae  lea     rcx, [rsp+120h+var_D0]
0x14000b0b3  test    r12b, 1
0x14000b0b7  jz      short loc_14000B0E2
0x14000b0b9  mov     rdx, [r13+258h]
0x14000b0c0  mov     r8, [r13+260h]
0x14000b0c7  sub     r8, rdx
0x14000b0ca  sar     r8, 1
0x14000b0cd  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x14000b0d2  xor     ecx, ecx
0x14000b0d4  test    al, al
0x14000b0d6  jnz     short loc_14000B0FE
0x14000b0d8  mov     edx, 371h
0x14000b0dd  jmp     loc_14000B278
0x14000b0e2  mov     r8, [rdx+8]
0x14000b0e6  sub     r8, [rdx]
0x14000b0e9  mov     rdx, [rdx]
0x14000b0ec  sar     r8, 1
0x14000b0ef  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x14000b0f4  xor     ecx, ecx
0x14000b0f6  test    al, al
0x14000b0f8  jz      loc_14000B273
0x14000b0fe  mov     [rbp+4Fh+var_58], r14
0x14000b102  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000b106  inc     rax
0x14000b109  cmp     [r14+rax*2], cx
0x14000b10e  jnz     short loc_14000B106
0x14000b110  lea     rdx, [rbp+4Fh+var_58]
0x14000b114  mov     [rbp+4Fh+var_50], rax
0x14000b118  lea     rcx, [rsp+120h+var_D0]; this
0x14000b11d  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x14000b122  test    al, al
0x14000b124  jz      loc_14000B26C
0x14000b12a  lea     rdx, [rsp+120h+var_D0]
0x14000b12f  mov     rcx, rbx
0x14000b132  call    ??$emplace_back@VPath@Csl@@$0A@@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@QEAA_N$$QEAVPath@Csl@@@Z; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::emplace_back<Csl::Path,0>(Csl::Path &&)
0x14000b137  test    al, al
0x14000b139  jz      loc_14000B265
0x14000b13f  mov     rcx, [rsp+120h+var_D0]; void *
0x14000b144  lea     rax, [rbp+4Fh+var_C0]
0x14000b148  cmp     rcx, rax
0x14000b14b  jz      short loc_14000B155
0x14000b14d  mov     rdx, rsi; struct std::nothrow_t *
0x14000b150  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000b155  mov     rcx, [r13+0]; hFindFile
0x14000b159  mov     rdx, r15; lpFindFileData
0x14000b15c  call    cs:__imp_FindNextFileW
0x14000b163  nop     dword ptr [rax+rax+00h]
0x14000b168  xor     ecx, ecx
0x14000b16a  test    eax, eax
0x14000b16c  jz      loc_14000B2AB
0x14000b172  mov     rdx, [rbp+4Fh+arg_8]
0x14000b176  jmp     loc_14000AE63
0x14000b17b  mov     rcx, [rbp+57h]; this
0x14000b17f  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000b186  mov     r9d, 8007000Eh; char *
0x14000b18c  mov     edx, 358h; void *
0x14000b191  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b196  lea     rcx, [rbp+4Fh+var_90]
0x14000b19a  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x14000b19f  mov     rcx, [rbp+4Fh+var_B0]; void *
0x14000b1a3  lea     rax, [rbp+4Fh+var_A0]
0x14000b1a7  cmp     rcx, rax
0x14000b1aa  jz      short loc_14000B1B4
0x14000b1ac  mov     rdx, rsi; struct std::nothrow_t *
0x14000b1af  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000b1b4  mov     rcx, [rsp+120h+var_F0]
0x14000b1b9  lea     rax, [rsp+120h+var_E0]
0x14000b1be  jmp     loc_14000B297
0x14000b1c3  mov     rcx, [rbp+57h]; this
0x14000b1c7  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000b1ce  mov     r9d, ebx; char *
0x14000b1d1  mov     edx, 355h; void *
0x14000b1d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b1db  lea     rcx, [rbp+4Fh+var_90]
0x14000b1df  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x14000b1e4  mov     rcx, [rbp+4Fh+var_B0]; void *
0x14000b1e8  lea     rax, [rbp+4Fh+var_A0]
0x14000b1ec  cmp     rcx, rax
0x14000b1ef  jz      short loc_14000B1F9
0x14000b1f1  mov     rdx, rsi; struct std::nothrow_t *
0x14000b1f4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000b1f9  mov     rcx, [rsp+120h+var_F0]; void *
0x14000b1fe  lea     rax, [rsp+120h+var_E0]
0x14000b203  cmp     rcx, rax
0x14000b206  jz      short loc_14000B210
0x14000b208  mov     rdx, rsi; struct std::nothrow_t *
0x14000b20b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000b210  mov     eax, ebx
0x14000b212  jmp     loc_14000B2AD
0x14000b217  mov     edx, 34Eh; void *
0x14000b21c  mov     rcx, [rbp+57h]; this
0x14000b220  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000b227  mov     r9d, 8007000Eh; char *
0x14000b22d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b232  jmp     loc_14000B19F
0x14000b237  mov     edx, 34Dh
0x14000b23c  jmp     short loc_14000B21C
0x14000b23e  mov     edx, 349h; void *
0x14000b243  mov     rcx, [rbp+57h]; this
0x14000b247  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000b24e  mov     r9d, 8007000Eh; char *
0x14000b254  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b259  jmp     loc_14000B1B4
0x14000b25e  mov     edx, 348h
0x14000b263  jmp     short loc_14000B243
0x14000b265  mov     edx, 37Ah
0x14000b26a  jmp     short loc_14000B278
0x14000b26c  mov     edx, 378h
0x14000b271  jmp     short loc_14000B278
0x14000b273  mov     edx, 375h; void *
0x14000b278  mov     rcx, [rbp+57h]; this
0x14000b27c  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000b283  mov     r9d, 8007000Eh; char *
0x14000b289  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b28e  mov     rcx, [rsp+120h+var_D0]; void *
0x14000b293  lea     rax, [rbp+4Fh+var_C0]
0x14000b297  cmp     rcx, rax
0x14000b29a  jz      short loc_14000B2A4
0x14000b29c  mov     rdx, rsi; struct std::nothrow_t *
0x14000b29f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000b2a4  mov     eax, 8007000Eh
0x14000b2a9  jmp     short loc_14000B2AD
0x14000b2ab  xor     eax, eax
0x14000b2ad  lea     r11, [rsp+120h+var_30]
0x14000b2b5  mov     rbx, [r11+40h]
0x14000b2b9  movaps  xmm6, xmmword ptr [r11-10h]
0x14000b2be  mov     rsp, r11
0x14000b2c1  pop     r15
0x14000b2c3  pop     r14
0x14000b2c5  pop     r13
0x14000b2c7  pop     r12
0x14000b2c9  pop     rdi
  ... truncated ...
```

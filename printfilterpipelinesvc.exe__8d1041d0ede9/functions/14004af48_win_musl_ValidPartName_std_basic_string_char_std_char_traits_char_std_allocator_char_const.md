# win_musl::ValidPartName(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x14004af48`
- end: `0x14004b313`
- name: `?ValidPartName@win_musl@@YA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `971`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x14004a858`

## callees

- `0x140002070`
- `0x140015980`
- `0x140028c30`
- `0x140040fcc`
- `0x14004195c`
- `0x1400487f8`
- `0x140048834`
- `0x140048a2c`
- `0x14004910c`
- `0x140049404`
- `0x140049824`
- `0x140049b50`
- `0x14004ab8c`
- `0x14004af48`
- `0x14004b6b4`
- `0x14004bb10`
- `0x14004bc30`
- `0x14004bdb0`
- `0x14004cd2c`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x14004afd1`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x14004afd1`

## string_xrefs

- `0x14004b0e3`: `/[Content_Types].xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
char __fastcall win_musl::ValidPartName(_QWORD *a1)
{
  char v2; // si
  char UriQueryAndFragment; // r14
  _BYTE *v4; // rax
  _QWORD *v5; // rax
  char v6; // dl
  win_musl::detail *v7; // rcx
  _BYTE *v8; // rbx
  _BYTE *v9; // r14
  _QWORD *v10; // rbx
  _QWORD *v11; // rax
  __int64 v12; // r9
  __int64 v13; // rdx
  char v14; // al
  char v15; // bl
  __int64 v16; // rdx
  _BYTE *v17; // r9
  __int64 v18; // r10
  __int64 v20; // [rsp+20h] [rbp-108h] BYREF
  __int64 v21; // [rsp+28h] [rbp-100h]
  __int64 v22; // [rsp+30h] [rbp-F8h]
  _BYTE *v23; // [rsp+40h] [rbp-E8h] BYREF
  __int64 v24; // [rsp+48h] [rbp-E0h]
  __int128 v25; // [rsp+50h] [rbp-D8h] BYREF
  __int64 v26; // [rsp+60h] [rbp-C8h]
  _QWORD v27[2]; // [rsp+70h] [rbp-B8h] BYREF
  __int64 v28; // [rsp+80h] [rbp-A8h]
  unsigned __int64 v29; // [rsp+88h] [rbp-A0h]
  _BYTE v30[32]; // [rsp+90h] [rbp-98h] BYREF
  _BYTE v31[32]; // [rsp+B0h] [rbp-78h] BYREF
  _BYTE v32[32]; // [rsp+D0h] [rbp-58h] BYREF

  v2 = 0;
  LODWORD(v23) = 0;
  std::string::string(v27);
  UriQueryAndFragment = win_musl::FindUriQueryAndFragment(a1, v27, 0, 0);
  if ( !v28 )
    goto LABEL_50;
  v4 = v27;
  if ( v29 > 0xF )
    v4 = (_BYTE *)v27[0];
  if ( *v4 != 47 )
    goto LABEL_50;
  v5 = v27;
  if ( v29 > 0xF )
    v5 = (_QWORD *)v27[0];
  if ( *((_BYTE *)v5 + v28 - 1) == 47 )
    goto LABEL_50;
  if ( std::string::find(a1, "%00") != -1 )
    goto LABEL_50;
  if ( (UriQueryAndFragment & 3) != 0 )
    goto LABEL_50;
  *(_QWORD *)&v25 = 7;
  *((_QWORD *)&v25 + 1) = "--..09AZ__az~~";
  v23 = 0;
  v24 = 0;
  if ( (unsigned int)win_musl::DecodeAsciiCharacters(v27, 0, &v23, &v25) )
    goto LABEL_50;
  *(_QWORD *)&v25 = 3;
  *((_QWORD *)&v25 + 1) = "..//\\\\";
  v23 = 0;
  v24 = 0;
  if ( (unsigned int)win_musl::DecodeAsciiCharacters(v27, 0, &v23, &v25) )
    goto LABEL_50;
  v8 = *(_BYTE **)std::string::end(v27, &v23);
  v9 = v27;
  if ( v29 > 0xF )
    v9 = (_BYTE *)v27[0];
  while ( v9 != v8 )
  {
    LOBYTE(v7) = *v9;
    if ( win_musl::detail::is_non_pchar(v7, v6) )
      break;
    ++v9;
  }
  if ( v9 == *(_BYTE **)std::string::end(v27, &v25) )
    goto LABEL_24;
  std::string::string(v31, "/[Content_Types].xml");
  LODWORD(v23) = 1;
  v10 = (_QWORD *)win_musl::NormalizeUri(v30, v31);
  LODWORD(v23) = 3;
  v11 = (_QWORD *)win_musl::NormalizeUri(v32, v27);
  v2 = 7;
  v12 = v10[2];
  if ( v10[3] > 7u )
    v10 = (_QWORD *)*v10;
  v13 = v11[2];
  if ( v11[3] > 7u )
    v11 = (_QWORD *)*v11;
  v14 = std::_Traits_equal<std::char_traits<wchar_t>>(v11, v13, v10, v12);
  v15 = 1;
  if ( v14 )
LABEL_24:
    v15 = 0;
  if ( (v2 & 4) != 0 )
  {
    v2 &= ~4u;
    std::wstring::_Tidy_deallocate(v32);
  }
  if ( (v2 & 2) != 0 )
  {
    v2 &= ~2u;
    std::wstring::_Tidy_deallocate(v30);
  }
  if ( (v2 & 1) != 0 )
    std::string::_Tidy_deallocate(v31);
  if ( v15
    || std::string::find(v27, "//") != -1
    || (win_musl::segments_iterator::segments_iterator(&v20, v27), v25 = 0, v26 = 0, !v21) && !v22 )
  {
LABEL_50:
    std::string::_Tidy_deallocate(v27);
    return 0;
  }
LABEL_35:
  if ( (unsigned __int8)win_musl::segments_iterator::operator!=(&v20, &v25) )
  {
    v16 = *(_QWORD *)(v22 + 16);
    if ( v16 && *(_BYTE *)std::string::at(v22, v16 - 1) != 46 )
    {
      std::string::end(v22, &v23);
      while ( v17 != v23 )
      {
        if ( *v17 != 46 )
        {
          v22 = v18 + 32;
          win_musl::segments_iterator::CheckEnd((win_musl::segments_iterator *)&v20);
          goto LABEL_35;
        }
        ++v17;
      }
    }
LABEL_47:
    if ( v20 )
    {
      if ( v21 )
      {
        win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::NonCloneableStreamHolder *>((__int64)&v20);
        v21 = 0;
        v20 = 0;
      }
    }
    goto LABEL_50;
  }
  try
  {
    win_musl::UnicodeStringFromUri(v30, v27);
    std::wstring::_Tidy_deallocate(v30);
  }
  catch ( SplException::TSystemException )
  {
    goto LABEL_47;
  }
  if ( v20 && v21 )
  {
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::NonCloneableStreamHolder *>((__int64)&v20);
    v20 = 0;
    v21 = 0;
  }
  std::string::_Tidy_deallocate(v27);
  return 1;
}

```

## disassembly

```asm
0x14004af48  push    rbx
0x14004af4a  push    rsi
0x14004af4b  push    rdi
0x14004af4c  push    r14
0x14004af4e  sub     rsp, 108h
0x14004af55  mov     rax, cs:__security_cookie
0x14004af5c  xor     rax, rsp
0x14004af5f  mov     [rsp+128h+var_38], rax
0x14004af67  mov     rbx, rcx
0x14004af6a  xor     edi, edi
0x14004af6c  mov     esi, edi
0x14004af6e  mov     dword ptr [rsp+128h+var_E8], edi
0x14004af72  lea     rcx, [rsp+128h+var_B8]
0x14004af77  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x14004af7c  nop
0x14004af7d  xor     r9d, r9d
0x14004af80  xor     r8d, r8d
0x14004af83  lea     rdx, [rsp+128h+var_B8]
0x14004af88  mov     rcx, rbx
0x14004af8b  call    ?FindUriQueryAndFragment@win_musl@@YAIAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAV23@11@Z; win_musl::FindUriQueryAndFragment(std::string const &,std::string *,std::string *,std::string *)
0x14004af90  mov     r14d, eax
0x14004af93  mov     rcx, [rsp+128h+var_A8]
0x14004af9b  test    rcx, rcx
0x14004af9e  jz      loc_14004B2EA
0x14004afa4  lea     rax, [rsp+128h+var_B8]
0x14004afa9  cmp     [rsp+128h+var_A0], 0Fh
0x14004afb2  cmova   rax, [rsp+128h+var_B8]
0x14004afb8  cmp     byte ptr [rax], 2Fh ; '/'
0x14004afbb  jnz     loc_14004B2EA
0x14004afc1  lea     rdx, [rcx-1]
0x14004afc5  cmp     rcx, rdx
0x14004afc8  ja      short loc_14004AFD8
0x14004afca  lea     rcx, aInvalidStringP; "invalid string position"
0x14004afd1  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x14004afd7  int     3; Trap to Debugger
0x14004afd8  lea     rax, [rsp+128h+var_B8]
0x14004afdd  cmp     [rsp+128h+var_A0], 0Fh
0x14004afe6  cmova   rax, [rsp+128h+var_B8]
0x14004afec  cmp     byte ptr [rdx+rax], 2Fh ; '/'
0x14004aff0  jz      loc_14004B2EA
0x14004aff6  lea     rdx, a00; "%00"
0x14004affd  mov     rcx, rbx
0x14004b000  call    ?find@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA_KQEBD_K@Z; std::string::find(char const * const,unsigned __int64)
0x14004b005  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14004b009  jnz     loc_14004B2EA
0x14004b00f  test    r14b, 3
0x14004b013  jnz     loc_14004B2EA
0x14004b019  mov     qword ptr [rsp+128h+var_D8], 7
0x14004b022  lea     rax, a09AzAz09azAz+18h; "--..09AZ__az~~"
0x14004b029  mov     qword ptr [rsp+128h+var_D8+8], rax
0x14004b02e  mov     [rsp+128h+var_E8], rdi
0x14004b033  mov     [rsp+128h+var_E0], rdi
0x14004b038  lea     r9, [rsp+128h+var_D8]
0x14004b03d  lea     r8, [rsp+128h+var_E8]
0x14004b042  xor     edx, edx
0x14004b044  lea     rcx, [rsp+128h+var_B8]
0x14004b049  call    ?DecodeAsciiCharacters@win_musl@@YA?AW4Enum@DecodeResult@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAV45@UAsciiRangeVector@1@2@Z; win_musl::DecodeAsciiCharacters(std::string const &,std::string *,win_musl::AsciiRangeVector,win_musl::AsciiRangeVector)
0x14004b04e  test    eax, eax
0x14004b050  jnz     loc_14004B2EA
0x14004b056  mov     qword ptr [rsp+128h+var_D8], 3
0x14004b05f  lea     rax, asc_14006CFE8; "..//\\\\"
0x14004b066  mov     qword ptr [rsp+128h+var_D8+8], rax
0x14004b06b  mov     [rsp+128h+var_E8], rdi
0x14004b070  mov     [rsp+128h+var_E0], rdi
0x14004b075  lea     r9, [rsp+128h+var_D8]
0x14004b07a  lea     r8, [rsp+128h+var_E8]
0x14004b07f  xor     edx, edx
0x14004b081  lea     rcx, [rsp+128h+var_B8]
0x14004b086  call    ?DecodeAsciiCharacters@win_musl@@YA?AW4Enum@DecodeResult@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAV45@UAsciiRangeVector@1@2@Z; win_musl::DecodeAsciiCharacters(std::string const &,std::string *,win_musl::AsciiRangeVector,win_musl::AsciiRangeVector)
0x14004b08b  test    eax, eax
0x14004b08d  jnz     loc_14004B2EA
0x14004b093  lea     rdx, [rsp+128h+var_E8]
0x14004b098  lea     rcx, [rsp+128h+var_B8]
0x14004b09d  call    ?end@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@2@XZ; std::string::end(void)
0x14004b0a2  mov     rbx, [rax]
0x14004b0a5  lea     r14, [rsp+128h+var_B8]
0x14004b0aa  cmp     [rsp+128h+var_A0], 0Fh
0x14004b0b3  cmova   r14, [rsp+128h+var_B8]
0x14004b0b9  jmp     short loc_14004B0CA
0x14004b0bb  mov     cl, [r14]; this
0x14004b0be  call    ?is_non_pchar@detail@win_musl@@YA_ND@Z; win_musl::detail::is_non_pchar(char)
0x14004b0c3  test    al, al
0x14004b0c5  jnz     short loc_14004B0CF
0x14004b0c7  inc     r14
0x14004b0ca  cmp     r14, rbx
0x14004b0cd  jnz     short loc_14004B0BB
0x14004b0cf  lea     rdx, [rsp+128h+var_D8]
0x14004b0d4  lea     rcx, [rsp+128h+var_B8]
0x14004b0d9  call    ?end@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@2@XZ; std::string::end(void)
0x14004b0de  cmp     r14, [rax]
0x14004b0e1  jz      short loc_14004B162
0x14004b0e3  lea     rdx, aContentTypesXm; "/[Content_Types].xml"
0x14004b0ea  lea     rcx, [rsp+128h+var_78]
0x14004b0f2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004b0f7  nop
0x14004b0f8  mov     dword ptr [rsp+128h+var_E8], 1
0x14004b100  lea     rdx, [rsp+128h+var_78]
0x14004b108  lea     rcx, [rsp+128h+var_98]
0x14004b110  call    ?NormalizeUri@win_musl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; win_musl::NormalizeUri(std::string const &)
0x14004b115  mov     rbx, rax
0x14004b118  mov     dword ptr [rsp+128h+var_E8], 3
0x14004b120  lea     rdx, [rsp+128h+var_B8]
0x14004b125  lea     rcx, [rsp+128h+var_58]
0x14004b12d  call    ?NormalizeUri@win_musl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; win_musl::NormalizeUri(std::string const &)
0x14004b132  mov     esi, 7
0x14004b137  mov     r9, [rbx+10h]
0x14004b13b  cmp     [rbx+18h], rsi
0x14004b13f  jbe     short loc_14004B144
0x14004b141  mov     rbx, [rbx]
0x14004b144  mov     rdx, [rax+10h]
0x14004b148  cmp     [rax+18h], rsi
0x14004b14c  jbe     short loc_14004B151
0x14004b14e  mov     rax, [rax]
0x14004b151  mov     r8, rbx
0x14004b154  mov     rcx, rax
0x14004b157  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x14004b15c  test    al, al
0x14004b15e  mov     bl, 1
0x14004b160  jz      short loc_14004B165
0x14004b162  mov     bl, dil
0x14004b165  test    sil, 4
0x14004b169  jz      short loc_14004B17C
0x14004b16b  and     esi, 0FFFFFFFBh
0x14004b16e  lea     rcx, [rsp+128h+var_58]
0x14004b176  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14004b17b  nop
0x14004b17c  test    sil, 2
0x14004b180  jz      short loc_14004B193
0x14004b182  and     esi, 0FFFFFFFDh
0x14004b185  lea     rcx, [rsp+128h+var_98]
0x14004b18d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14004b192  nop
0x14004b193  test    sil, 1
0x14004b197  jz      short loc_14004B1A6
0x14004b199  lea     rcx, [rsp+128h+var_78]
0x14004b1a1  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14004b1a6  test    bl, bl
0x14004b1a8  jnz     loc_14004B2EA
0x14004b1ae  lea     rdx, asc_14006CF14; "//"
0x14004b1b5  lea     rcx, [rsp+128h+var_B8]
0x14004b1ba  call    ?find@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA_KQEBD_K@Z; std::string::find(char const * const,unsigned __int64)
0x14004b1bf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14004b1c3  jnz     loc_14004B2EA
0x14004b1c9  lea     rdx, [rsp+128h+var_B8]
0x14004b1ce  lea     rcx, [rsp+128h+var_108]
0x14004b1d3  call    ??0segments_iterator@win_musl@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; win_musl::segments_iterator::segments_iterator(std::string const &)
0x14004b1d8  nop
0x14004b1d9  xorps   xmm0, xmm0
0x14004b1dc  movdqu  [rsp+128h+var_D8], xmm0
0x14004b1e2  mov     [rsp+128h+var_C8], rdi
0x14004b1e7  cmp     [rsp+128h+var_100], rdi
0x14004b1ec  jnz     short loc_14004B1FA
0x14004b1ee  cmp     [rsp+128h+var_F8], rdi
0x14004b1f3  jnz     short loc_14004B1FA
0x14004b1f5  jmp     loc_14004B2EA
0x14004b1fa  lea     rdx, [rsp+128h+var_D8]
0x14004b1ff  lea     rcx, [rsp+128h+var_108]
0x14004b204  call    ??9segments_iterator@win_musl@@QEBA_NAEBV01@@Z; win_musl::segments_iterator::operator!=(win_musl::segments_iterator const &)
0x14004b209  test    al, al
0x14004b20b  jz      short loc_14004B276
0x14004b20d  mov     rcx, [rsp+128h+var_F8]
0x14004b212  mov     rdx, [rcx+10h]
0x14004b216  test    rdx, rdx
0x14004b219  jz      short loc_14004B274
0x14004b21b  dec     rdx
0x14004b21e  call    ?at@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAAEBD_K@Z; std::string::at(unsigned __int64)
0x14004b223  cmp     byte ptr [rax], 2Eh ; '.'
0x14004b226  jz      short loc_14004B272
0x14004b228  mov     r10, [rsp+128h+var_F8]
0x14004b22d  cmp     qword ptr [r10+18h], 0Fh
0x14004b232  jbe     short loc_14004B239
0x14004b234  mov     r9, [r10]
0x14004b237  jmp     short loc_14004B23C
0x14004b239  mov     r9, r10
0x14004b23c  lea     rdx, [rsp+128h+var_E8]
0x14004b241  mov     rcx, r10
0x14004b244  call    ?end@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@2@XZ; std::string::end(void)
0x14004b249  cmp     r9, [rsp+128h+var_E8]
0x14004b24e  jz      short loc_14004B270
0x14004b250  cmp     byte ptr [r9], 2Eh ; '.'
0x14004b254  jnz     short loc_14004B25B
0x14004b256  inc     r9
0x14004b259  jmp     short loc_14004B249
0x14004b25b  add     r10, 20h ; ' '
0x14004b25f  mov     [rsp+128h+var_F8], r10
0x14004b264  lea     rcx, [rsp+128h+var_108]; this
0x14004b269  call    ?CheckEnd@segments_iterator@win_musl@@AEAAXXZ; win_musl::segments_iterator::CheckEnd(void)
0x14004b26e  jmp     short loc_14004B1FA
0x14004b270  jmp     short loc_14004B2C8
0x14004b272  jmp     short loc_14004B2C8
0x14004b274  jmp     short loc_14004B2C8
0x14004b276  lea     rdx, [rsp+128h+var_B8]
0x14004b27b  lea     rcx, [rsp+128h+var_98]
0x14004b283  call    ?UnicodeStringFromUri@win_musl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; win_musl::UnicodeStringFromUri(std::string const &)
0x14004b288  lea     rcx, [rsp+128h+var_98]
0x14004b290  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14004b295  nop
0x14004b296  cmp     [rsp+128h+var_108], rdi
0x14004b29b  jz      short loc_14004B2B8
0x14004b29d  cmp     [rsp+128h+var_100], rdi
0x14004b2a2  jz      short loc_14004B2B8
0x14004b2a4  lea     rcx, [rsp+128h+var_108]
0x14004b2a9  call    ??$close@PEAVNonCloneableStreamHolder@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVNonCloneableStreamHolder@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::NonCloneableStreamHolder *>(win_scope::counted_store<win_dox::NonCloneableStreamHolder *> *)
0x14004b2ae  mov     [rsp+128h+var_108], rdi
0x14004b2b3  mov     [rsp+128h+var_100], rdi
0x14004b2b8  lea     rcx, [rsp+128h+var_B8]
0x14004b2bd  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14004b2c2  mov     al, 1
0x14004b2c4  jmp     short loc_14004B2F6
0x14004b2c6  xor     edi, edi
0x14004b2c8  cmp     [rsp+128h+var_108], rdi
0x14004b2cd  jz      short loc_14004B2EA
0x14004b2cf  cmp     [rsp+128h+var_100], rdi
0x14004b2d4  jz      short loc_14004B2EA
0x14004b2d6  lea     rcx, [rsp+128h+var_108]
0x14004b2db  call    ??$close@PEAVNonCloneableStreamHolder@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVNonCloneableStreamHolder@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::NonCloneableStreamHolder *>(win_scope::counted_store<win_dox::NonCloneableStreamHolder *> *)
0x14004b2e0  mov     [rsp+128h+var_100], rdi
0x14004b2e5  mov     [rsp+128h+var_108], rdi
0x14004b2ea  lea     rcx, [rsp+128h+var_B8]
0x14004b2ef  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14004b2f4  xor     al, al
0x14004b2f6  mov     rcx, [rsp+128h+var_38]
0x14004b2fe  xor     rcx, rsp; StackCookie
0x14004b301  call    __security_check_cookie
0x14004b306  add     rsp, 108h
0x14004b30d  pop     r14
0x14004b30f  pop     rdi
0x14004b310  pop     rsi
0x14004b311  pop     rbx
0x14004b312  retn
```

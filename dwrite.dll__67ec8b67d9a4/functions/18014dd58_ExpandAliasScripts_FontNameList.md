# ExpandAliasScripts(FontNameList &)

- ea: `0x18014dd58`
- end: `0x18014e22e`
- name: `?ExpandAliasScripts@@YAXAEAVFontNameList@@@Z`
- size: `1238`
- prototype: `void __fastcall(struct FontNameList *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18014db1c`

## callees

- `0x18014dd58`
- `0x18014e234`
- `0x1801644d0`
- `0x180167320`
- `0x18016a174`
- `0x1801cdf7c`
- `0x1801ee584`
- `0x1801ef8d4`
- `0x1801ef914`
- `0x1801efaac`
- `0x1801f0074`
- `0x1801f3020`
- `0x1801f37b0`
- `0x1802066a4`
- `0x180207194`
- `0x180212490`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18014de9b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18014de9b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18014e21c`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18014e21c`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall ExpandAliasScripts(struct FontNameList *a1)
{
  __int64 v2; // rbx
  __int64 v3; // rdi
  unsigned __int64 v4; // rdi
  unsigned int v5; // eax
  struct DWrite::RefString::Data **v6; // r14
  __int64 v7; // r13
  struct DWrite::RefString::Data *v8; // rcx
  struct DWrite::RefString::Data **v9; // r12
  wchar_t ***v10; // rsi
  wchar_t ***v11; // rbx
  const WCHAR **v12; // rax
  const WCHAR *v13; // r8
  unsigned __int64 v14; // r9
  __int64 v15; // rdx
  const WCHAR *v16; // rcx
  int v17; // eax
  struct DWrite::RefString::Data *v18; // r14
  __int64 lower; // rax
  __int64 v20; // rcx
  __int128 v21; // xmm6
  __int64 v22; // r8
  __int64 v23; // rsi
  __int64 v24; // rax
  const wchar_t **v25; // rbx
  struct DWrite::RefString::Data **v26; // r13
  __int64 v27; // rcx
  __int64 v28; // rdi
  __int64 v29; // rax
  struct DWrite::RefString::Data **j; // rdi
  struct DWrite::RefString::Data *v31; // r12
  __int64 v32; // rcx
  __int64 v33; // rsi
  __int64 v34; // rax
  __int64 v35; // rax
  struct DWrite::RefString::Data **v36; // r12
  struct DWrite::RefString::Data **i; // rsi
  struct DWrite::RefString::Data *v38; // r13
  __int64 v39; // rax
  __int64 v40; // rcx
  __int128 v41; // xmm6
  __int64 v42; // r8
  __int64 v43; // rbx
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // [rsp+38h] [rbp-99h] BYREF
  __int64 v47; // [rsp+40h] [rbp-91h]
  unsigned int v48; // [rsp+48h] [rbp-89h]
  struct DWrite::RefString::Data *v49[2]; // [rsp+58h] [rbp-79h] BYREF
  struct DWrite::RefString::Data *v50; // [rsp+68h] [rbp-69h] BYREF
  __int64 v51; // [rsp+70h] [rbp-61h]
  __int128 v52; // [rsp+78h] [rbp-59h] BYREF
  __int64 v53; // [rsp+88h] [rbp-49h]
  _BYTE v54[24]; // [rsp+98h] [rbp-39h] BYREF
  _BYTE v55[32]; // [rsp+B0h] [rbp-21h] BYREF

  std::wstring::wstring(v55);
  v46 = 0;
  v47 = 0;
  std::_Tree<std::_Tset_traits<DWrite::RefString,std::less<DWrite::RefString>,std::allocator<DWrite::RefString>,0>>::_Alloc_sentinel_and_proxy(&v46);
  v2 = *(_QWORD *)a1;
  v3 = *((_QWORD *)a1 + 1);
  while ( v2 != v3 )
  {
    v18 = (struct DWrite::RefString::Data *)(*(_QWORD *)(v2 + 32) + 8LL);
    v49[0] = v18;
    lower = std::_Tree<std::_Tset_traits<wchar_t const *,FontNameList::StringLessThanIgnoreCase,std::allocator<wchar_t const *>,0>>::_Find_lower_bound<wchar_t const *>(
              &v46,
              &v52,
              v49);
    v21 = *(_OWORD *)lower;
    v22 = *(_QWORD *)(lower + 16);
    if ( *(_BYTE *)(v22 + 25)
      || (unsigned __int8)FontNameList::StringLessThanIgnoreCase::operator()(v20, v18, *(_QWORD *)(v22 + 32)) )
    {
      if ( v47 == 0x666666666666666LL )
LABEL_55:
        std::_Xlength_error("map/set too long");
      v23 = v46;
      v50 = (struct DWrite::RefString::Data *)&v46;
      v51 = 0;
      v24 = std::_Allocate<16,std::_Default_allocate_traits>(40);
      *(_QWORD *)(v24 + 32) = v18;
      *(_QWORD *)v24 = v23;
      *(_QWORD *)(v24 + 8) = v23;
      *(_QWORD *)(v24 + 16) = v23;
      *(_WORD *)(v24 + 24) = 0;
      v51 = 0;
      v52 = v21;
      std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short const,DWriteCore::CacheHelpers::CoalescedRegionPtr<DWriteCore::CacheHelpers::ArrayRegion<DWriteCore::FontApi::NameDictionaryEntry>>>>>::_Insert_node(
        &v46,
        &v52,
        v24);
    }
    v2 += 40;
  }
  v4 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)a1 + 1) - *(_QWORD *)a1) >> 3);
  v5 = 0;
  v48 = 0;
  v6 = (struct DWrite::RefString::Data **)off_1804AF0E0;
  if ( !(_DWORD)v4 )
    goto LABEL_26;
  while ( 2 )
  {
    v7 = *(_QWORD *)a1;
    if ( v5 >= 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)a1 + 1) - *(_QWORD *)a1) >> 3) )
    {
      FailAssert(0x35u, (const char *)0xCCCCCCCCCCCCCCCDLL);
      JUMPOUT(0x18014E22DLL);
    }
    v8 = (struct DWrite::RefString::Data *)(5LL * v5);
    v49[0] = v8;
    v9 = &off_1804AF1D0;
    v10 = off_1804AF0E0;
    while ( v10 < (wchar_t ***)v9 )
    {
      v11 = &v10[2 * ((((char *)v9 - (char *)v10) >> 4) / 2)];
      v12 = (const WCHAR **)*v11;
      v13 = **v11;
      v14 = -1;
      do
        ++v14;
      while ( v13[v14] );
      v15 = *(_QWORD *)(v7 + 8LL * (_QWORD)v8 + 32);
      v16 = (const WCHAR *)(v15 + 8);
      if ( v15 == -8 )
      {
        if ( !v13 )
          goto LABEL_44;
LABEL_14:
        v9 = (struct DWrite::RefString::Data **)&v10[2 * ((((char *)v9 - (char *)v10) >> 4) / 2)];
        goto LABEL_15;
      }
      if ( v13 )
      {
        if ( v14 > 0x7FFFFFFF || (v15 = *(unsigned int *)(v15 + 4), (unsigned int)v15 > 0x7FFFFFFF) )
          SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(v16, v15);
        v17 = CompareStringOrdinal(v16, v15, v13, v14, 1) - 2;
        if ( v17 < 0 )
          goto LABEL_14;
        if ( v17 <= 0 )
        {
          v12 = (const WCHAR **)*v11;
LABEL_44:
          v36 = (struct DWrite::RefString::Data **)v11[1];
          for ( i = (struct DWrite::RefString::Data **)(v12 + 1); i != v36; ++i )
          {
            v38 = *i;
            v49[0] = *i;
            v39 = std::_Tree<std::_Tset_traits<wchar_t const *,FontNameList::StringLessThanIgnoreCase,std::allocator<wchar_t const *>,0>>::_Find_lower_bound<wchar_t const *>(
                    &v46,
                    v54,
                    v49);
            v41 = *(_OWORD *)v39;
            v42 = *(_QWORD *)(v39 + 16);
            if ( *(_BYTE *)(v42 + 25)
              || (unsigned __int8)FontNameList::StringLessThanIgnoreCase::operator()(v40, v38, *(_QWORD *)(v42 + 32)) )
            {
              if ( v47 == 0x666666666666666LL )
                goto LABEL_55;
              v43 = v46;
              v52 = (unsigned __int64)&v46;
              v44 = std::_Allocate<16,std::_Default_allocate_traits>(40);
              *(_QWORD *)(v44 + 32) = v38;
              *(_QWORD *)v44 = v43;
              *(_QWORD *)(v44 + 8) = v43;
              *(_QWORD *)(v44 + 16) = v43;
              *(_WORD *)(v44 + 24) = 0;
              *((_QWORD *)&v52 + 1) = 0;
              *(_OWORD *)v49 = v41;
              std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short const,DWriteCore::CacheHelpers::CoalescedRegionPtr<DWriteCore::CacheHelpers::ArrayRegion<DWriteCore::FontApi::NameDictionaryEntry>>>>>::_Insert_node(
                &v46,
                v49,
                v44);
              v45 = DWrite::RefString::RefString((DWrite::RefString *)&v50, (const wchar_t *)v38);
              FontNameList::AppendItem(a1, v55, v45);
              DWrite::RefString::DecrementRef(v50);
            }
          }
          break;
        }
      }
      v10 = v11 + 2;
LABEL_15:
      v8 = v49[0];
    }
    v5 = v48 + 1;
    v48 = v5;
    if ( v5 < (unsigned int)v4 )
      continue;
    break;
  }
  do
  {
LABEL_26:
    v25 = (const wchar_t **)*v6;
    v26 = (struct DWrite::RefString::Data **)v6[1];
    if ( (unsigned __int64)(((char *)v26 - (char *)*v6) >> 3) > 2 )
    {
      std::_Tree<std::_Tset_traits<wchar_t const *,FontNameList::StringLessThanIgnoreCase,std::allocator<wchar_t const *>,0>>::_Find_lower_bound<wchar_t const *>(
        &v46,
        &v52,
        *v6);
      v28 = v53;
      if ( *(_BYTE *)(v53 + 25)
        || (unsigned __int8)FontNameList::StringLessThanIgnoreCase::operator()(v27, *v25, *(_QWORD *)(v53 + 32)) )
      {
        v29 = v46;
        v28 = v46;
      }
      else
      {
        v29 = v46;
      }
      if ( v28 == v29 )
      {
        for ( j = (struct DWrite::RefString::Data **)(v25 + 1); j != v26; ++j )
        {
          v31 = *j;
          v50 = *j;
          std::_Tree<std::_Tset_traits<wchar_t const *,FontNameList::StringLessThanIgnoreCase,std::allocator<wchar_t const *>,0>>::_Find_lower_bound<wchar_t const *>(
            &v46,
            &v52,
            &v50);
          v33 = v53;
          if ( *(_BYTE *)(v53 + 25)
            || (unsigned __int8)FontNameList::StringLessThanIgnoreCase::operator()(v32, v31, *(_QWORD *)(v53 + 32)) )
          {
            v34 = v46;
            v33 = v46;
          }
          else
          {
            v34 = v46;
          }
          if ( v33 == v34 )
            goto LABEL_37;
        }
        v35 = DWrite::RefString::RefString((DWrite::RefString *)v49, *v25);
        FontNameList::AppendItem(a1, v55, v35);
        DWrite::RefString::DecrementRef(v49[0]);
      }
    }
LABEL_37:
    v6 += 2;
  }
  while ( v6 != &off_1804AF1D0 );
  std::_Tree_val<std::_Tree_simple_types<wchar_t const *>>::_Erase_tree<std::allocator<std::_Tree_node<wchar_t const *,void *>>>(
    &v46,
    &v46,
    *(_QWORD *)(v46 + 8),
    2);
  std::_Deallocate<16>(v46, 40);
  std::wstring::_Tidy_deallocate(v55);
}

```

## disassembly

```asm
0x18014dd58  mov     rax, rsp
0x18014dd5b  push    rbp
0x18014dd5c  push    rbx
0x18014dd5d  push    rsi
0x18014dd5e  push    rdi
0x18014dd5f  push    r12
0x18014dd61  push    r13
0x18014dd63  push    r14
0x18014dd65  push    r15
0x18014dd67  lea     rbp, [rax-5Fh]
0x18014dd6b  sub     rsp, 0E8h
0x18014dd72  movaps  xmmword ptr [rax-58h], xmm6
0x18014dd76  mov     rax, cs:__security_cookie
0x18014dd7d  xor     rax, rsp
0x18014dd80  mov     qword ptr [rbp+57h+var_58], rax
0x18014dd84  mov     r15, rcx
0x18014dd87  lea     rcx, [rbp+57h+var_78]; void *
0x18014dd8b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18014dd90  nop
0x18014dd91  xor     r12d, r12d
0x18014dd94  mov     [rsp+120h+var_F0], r12
0x18014dd99  mov     [rsp+120h+var_E8], r12
0x18014dd9e  lea     rcx, [rsp+120h+var_F0]
0x18014dda3  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tset_traits@VRefString@DWrite@@U?$less@VRefString@DWrite@@@std@@V?$allocator@VRefString@DWrite@@@4@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tset_traits<DWrite::RefString,std::less<DWrite::RefString>,std::allocator<DWrite::RefString>,0>>::_Alloc_sentinel_and_proxy(void)
0x18014dda8  nop
0x18014dda9  mov     rbx, [r15]
0x18014ddac  mov     rdi, [r15+8]
0x18014ddb0  mov     rsi, 666666666666666h
0x18014ddba  cmp     rbx, rdi
0x18014ddbd  jnz     loc_18014DEF4
0x18014ddc3  mov     rdi, [r15+8]
0x18014ddc7  sub     rdi, [r15]
0x18014ddca  sar     rdi, 3
0x18014ddce  mov     rdx, 0CCCCCCCCCCCCCCCDh; char *
0x18014ddd8  imul    rdi, rdx
0x18014dddc  mov     eax, r12d
0x18014dddf  mov     [rsp+120h+var_E0], eax
0x18014dde3  lea     r8, off_1804AF1D0
0x18014ddea  lea     r14, off_1804AF0E0
0x18014ddf1  mov     r9d, 2
0x18014ddf7  test    edi, edi
0x18014ddf9  jz      loc_18014DFA4
0x18014ddff  mov     r13, [r15]
0x18014de02  mov     ecx, eax
0x18014de04  mov     rax, [r15+8]
0x18014de08  sub     rax, r13
0x18014de0b  sar     rax, 3
0x18014de0f  imul    rax, rdx
0x18014de13  cmp     rcx, rax
0x18014de16  jnb     loc_18014E223
0x18014de1c  lea     rcx, [rcx+rcx*4]
0x18014de20  mov     [rbp+57h+var_D0], rcx
0x18014de24  mov     r12, r8
0x18014de27  mov     rsi, r14
0x18014de2a  cmp     rsi, r12
0x18014de2d  jnb     loc_18014DECC
0x18014de33  mov     rax, r12
0x18014de36  sub     rax, rsi
0x18014de39  sar     rax, 4
0x18014de3d  cqo
0x18014de3f  idiv    r9
0x18014de42  add     rax, rax
0x18014de45  lea     rbx, [rsi+rax*8]
0x18014de49  mov     rax, [rbx]
0x18014de4c  mov     r8, [rax]; lpString2
0x18014de4f  or      r9, 0FFFFFFFFFFFFFFFFh
0x18014de53  xor     r10d, r10d
0x18014de56  inc     r9; cchCount2
0x18014de59  cmp     [r8+r9*2], r10w
0x18014de5e  jnz     short loc_18014DE56
0x18014de60  mov     rdx, [r13+rcx*8+20h]
0x18014de65  lea     rcx, [rdx+8]; lpString1
0x18014de69  test    rcx, rcx
0x18014de6c  jz      loc_18014E207
0x18014de72  test    r8, r8
0x18014de75  jz      short loc_18014DEC0
0x18014de77  cmp     r9, 7FFFFFFFh
0x18014de7e  ja      loc_18014E201
0x18014de84  mov     edx, [rdx+4]; cchCount1
0x18014de87  cmp     edx, 7FFFFFFFh
0x18014de8d  ja      loc_18014E201
0x18014de93  mov     dword ptr [rsp+20h], 1; bIgnoreCase
0x18014de9b  call    cs:__imp_CompareStringOrdinal
0x18014dea1  add     eax, 0FFFFFFFEh
0x18014dea4  jns     short loc_18014DEB8
0x18014dea6  mov     r12, rbx
0x18014dea9  mov     rcx, [rbp+57h+var_D0]
0x18014dead  mov     r9d, 2
0x18014deb3  jmp     loc_18014DE2A
0x18014deb8  test    eax, eax
0x18014deba  jle     loc_18014E109
0x18014dec0  lea     rsi, [rbx+10h]
0x18014dec4  jmp     short loc_18014DEA9
0x18014dec6  mov     r9d, 2
0x18014decc  mov     eax, [rsp+120h+var_E0]
0x18014ded0  inc     eax
0x18014ded2  mov     [rsp+120h+var_E0], eax
0x18014ded6  lea     r8, off_1804AF1D0
0x18014dedd  cmp     eax, edi
0x18014dedf  jnb     loc_18014DFA1
0x18014dee5  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x18014deef  jmp     loc_18014DDFF
0x18014def4  mov     r14, [rbx+20h]
0x18014def8  add     r14, 8
0x18014defc  mov     [rbp+57h+var_D0], r14
0x18014df00  lea     r8, [rbp+57h+var_D0]
0x18014df04  lea     rdx, [rbp+57h+var_B0]
0x18014df08  lea     rcx, [rsp+120h+var_F0]
0x18014df0d  call    ??$_Find_lower_bound@PEB_W@?$_Tree@V?$_Tset_traits@PEB_WUStringLessThanIgnoreCase@FontNameList@@V?$allocator@PEB_W@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@PEB_WPEAX@std@@@1@AEBQEB_W@Z; std::_Tree<std::_Tset_traits<wchar_t const *,FontNameList::StringLessThanIgnoreCase,std::allocator<wchar_t const *>,0>>::_Find_lower_bound<wchar_t const *>(wchar_t const * const &)
0x18014df12  movups  xmm6, xmmword ptr [rax]
0x18014df15  mov     r8, [rax+10h]
0x18014df19  cmp     [r8+19h], r12b
0x18014df1d  jz      short loc_18014DF8F
0x18014df1f  cmp     [rsp+120h+var_E8], rsi
0x18014df24  jz      loc_18014E215
0x18014df2a  mov     rsi, [rsp+120h+var_F0]
0x18014df2f  lea     rax, [rsp+120h+var_F0]
0x18014df34  mov     [rbp+57h+var_C0], rax
0x18014df38  mov     [rbp+57h+var_B8], r12
0x18014df3c  mov     [rbp+57h+var_B8], r12
0x18014df40  mov     ecx, 28h ; '('
0x18014df45  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18014df4a  mov     [rbp+57h+var_B8], rax
0x18014df4e  mov     [rax+20h], r14
0x18014df52  mov     [rax], rsi
0x18014df55  mov     [rax+8], rsi
0x18014df59  mov     [rax+10h], rsi
0x18014df5d  mov     [rax+18h], r12w
0x18014df62  mov     [rbp+57h+var_B8], r12
0x18014df66  movdqu  [rbp+57h+var_B0], xmm6
0x18014df6b  mov     r8, rax
0x18014df6e  lea     rdx, [rbp+57h+var_B0]
0x18014df72  lea     rcx, [rsp+120h+var_F0]
0x18014df77  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBGV?$CoalescedRegionPtr@V?$ArrayRegion@UNameDictionaryEntry@FontApi@DWriteCore@@@CacheHelpers@DWriteCore@@@CacheHelpers@DWriteCore@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBGV?$CoalescedRegionPtr@V?$ArrayRegion@UNameDictionaryEntry@FontApi@DWriteCore@@@CacheHelpers@DWriteCore@@@CacheHelpers@DWriteCore@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBGV?$CoalescedRegionPtr@V?$ArrayRegion@UNameDictionaryEntry@FontApi@DWriteCore@@@CacheHelpers@DWriteCore@@@CacheHelpers@DWriteCore@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ushort const,DWriteCore::CacheHelpers::CoalescedRegionPtr<DWriteCore::CacheHelpers::ArrayRegion<DWriteCore::FontApi::NameDictionaryEntry>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<ushort const,DWriteCore::CacheHelpers::CoalescedRegionPtr<DWriteCore::CacheHelpers::ArrayRegion<DWriteCore::FontApi::NameDictionaryEntry>>>,void *> *>,std::_Tree_node<std::pair<ushort const,DWriteCore::CacheHelpers::CoalescedRegionPtr<DWriteCore::CacheHelpers::ArrayRegion<DWriteCore::FontApi::NameDictionaryEntry>>>,void *> * const)
0x18014df7c  mov     rsi, 666666666666666h
0x18014df86  add     rbx, 28h ; '('
0x18014df8a  jmp     loc_18014DDBA
0x18014df8f  mov     r8, [r8+20h]
0x18014df93  mov     rdx, r14
0x18014df96  call    ??RStringLessThanIgnoreCase@FontNameList@@QEBA_NPEB_W0@Z; FontNameList::StringLessThanIgnoreCase::operator()(wchar_t const *,wchar_t const *)
0x18014df9b  test    al, al
0x18014df9d  jnz     short loc_18014DF1F
0x18014df9f  jmp     short loc_18014DF86
0x18014dfa1  xor     r12d, r12d
0x18014dfa4  mov     rbx, [r14]
0x18014dfa7  mov     r13, [r14+8]
0x18014dfab  mov     rax, r13
0x18014dfae  sub     rax, rbx
0x18014dfb1  sar     rax, 3
0x18014dfb5  cmp     rax, r9
0x18014dfb8  jbe     loc_18014E063
0x18014dfbe  mov     r8, rbx
0x18014dfc1  lea     rdx, [rbp+57h+var_B0]
0x18014dfc5  lea     rcx, [rsp+120h+var_F0]
0x18014dfca  call    ??$_Find_lower_bound@PEB_W@?$_Tree@V?$_Tset_traits@PEB_WUStringLessThanIgnoreCase@FontNameList@@V?$allocator@PEB_W@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@PEB_WPEAX@std@@@1@AEBQEB_W@Z; std::_Tree<std::_Tset_traits<wchar_t const *,FontNameList::StringLessThanIgnoreCase,std::allocator<wchar_t const *>,0>>::_Find_lower_bound<wchar_t const *>(wchar_t const * const &)
0x18014dfcf  mov     rdi, [rbp+57h+var_A0]
0x18014dfd3  cmp     [rdi+19h], r12b
0x18014dfd7  jz      loc_18014E0EB
0x18014dfdd  mov     rax, [rsp+120h+var_F0]
0x18014dfe2  mov     rdi, rax
0x18014dfe5  cmp     rdi, rax
0x18014dfe8  jnz     short loc_18014E056
0x18014dfea  lea     rdi, [rbx+8]
0x18014dfee  cmp     rdi, r13
0x18014dff1  jz      short loc_18014E030
0x18014dff3  mov     r12, [rdi]
0x18014dff6  mov     [rbp+57h+var_C0], r12
0x18014dffa  lea     r8, [rbp+57h+var_C0]
0x18014dffe  lea     rdx, [rbp+57h+var_B0]
0x18014e002  lea     rcx, [rsp+120h+var_F0]
0x18014e007  call    ??$_Find_lower_bound@PEB_W@?$_Tree@V?$_Tset_traits@PEB_WUStringLessThanIgnoreCase@FontNameList@@V?$allocator@PEB_W@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@PEB_WPEAX@std@@@1@AEBQEB_W@Z; std::_Tree<std::_Tset_traits<wchar_t const *,FontNameList::StringLessThanIgnoreCase,std::allocator<wchar_t const *>,0>>::_Find_lower_bound<wchar_t const *>(wchar_t const * const &)
0x18014e00c  mov     rsi, [rbp+57h+var_A0]
0x18014e010  cmp     byte ptr [rsi+19h], 0
0x18014e014  jz      loc_18014E0CA
0x18014e01a  xor     r12d, r12d
0x18014e01d  mov     rax, [rsp+120h+var_F0]
0x18014e022  mov     rsi, rax
0x18014e025  cmp     rsi, rax
0x18014e028  jz      short loc_18014E056
0x18014e02a  add     rdi, 8
0x18014e02e  jmp     short loc_18014DFEE
0x18014e030  mov     rdx, [rbx]; wchar_t *
0x18014e033  lea     rcx, [rbp+57h+var_D0]; this
0x18014e037  call    ??0RefString@DWrite@@QEAA@PEB_W@Z; DWrite::RefString::RefString(wchar_t const *)
0x18014e03c  nop
0x18014e03d  mov     r8, rax
0x18014e040  lea     rdx, [rbp+57h+var_78]
0x18014e044  mov     rcx, r15
0x18014e047  call    ?AppendItem@FontNameList@@QEAAXAEBV?$GenericLanguageTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@AEBVRefString@DWrite@@@Z; FontNameList::AppendItem(GenericLanguageTag<std::wstring> const &,DWrite::RefString const &)
0x18014e04c  nop
0x18014e04d  mov     rcx, [rbp+57h+var_D0]; struct DWrite::RefString::Data *
0x18014e051  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18014e056  lea     r8, off_1804AF1D0
0x18014e05d  mov     r9d, 2
0x18014e063  add     r14, 10h
0x18014e067  cmp     r14, r8
0x18014e06a  jnz     loc_18014DFA4
0x18014e070  mov     r8, [rsp+120h+var_F0]
0x18014e075  mov     r8, [r8+8]
0x18014e079  lea     rdx, [rsp+120h+var_F0]
0x18014e07e  lea     rcx, [rsp+120h+var_F0]
0x18014e083  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@PEB_WPEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@PEB_W@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@PEB_WPEAX@std@@@1@PEAU?$_Tree_node@PEB_WPEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<wchar_t const *>>::_Erase_tree<std::allocator<std::_Tree_node<wchar_t const *,void *>>>(std::allocator<std::_Tree_node<wchar_t const *,void *>> &,std::_Tree_node<wchar_t const *,void *> *)
0x18014e088  mov     edx, 28h ; '('
0x18014e08d  mov     rcx, [rsp+120h+var_F0]
0x18014e092  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18014e097  nop
0x18014e098  lea     rcx, [rbp+57h+var_78]
0x18014e09c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18014e0a1  nop
0x18014e0a2  mov     rcx, qword ptr [rbp+57h+var_58]
0x18014e0a6  xor     rcx, rsp; StackCookie
0x18014e0a9  call    __security_check_cookie
0x18014e0ae  movaps  xmm6, [rsp+120h+var_58+8]
0x18014e0b6  add     rsp, 0E8h
0x18014e0bd  pop     r15
0x18014e0bf  pop     r14
0x18014e0c1  pop     r13
0x18014e0c3  pop     r12
0x18014e0c5  pop     rdi
0x18014e0c6  pop     rsi
0x18014e0c7  pop     rbx
0x18014e0c8  pop     rbp
0x18014e0c9  retn
0x18014e0ca  mov     r8, [rsi+20h]
0x18014e0ce  mov     rdx, r12
0x18014e0d1  call    ??RStringLessThanIgnoreCase@FontNameList@@QEBA_NPEB_W0@Z; FontNameList::StringLessThanIgnoreCase::operator()(wchar_t const *,wchar_t const *)
0x18014e0d6  xor     r12d, r12d
0x18014e0d9  test    al, al
0x18014e0db  jnz     loc_18014E01D
0x18014e0e1  mov     rax, [rsp+120h+var_F0]
0x18014e0e6  jmp     loc_18014E025
0x18014e0eb  mov     r8, [rdi+20h]
0x18014e0ef  mov     rdx, [rbx]
0x18014e0f2  call    ??RStringLessThanIgnoreCase@FontNameList@@QEBA_NPEB_W0@Z; FontNameList::StringLessThanIgnoreCase::operator()(wchar_t const *,wchar_t const *)
0x18014e0f7  test    al, al
0x18014e0f9  jnz     loc_18014DFDD
0x18014e0ff  mov     rax, [rsp+120h+var_F0]
0x18014e104  jmp     loc_18014DFE5
0x18014e109  mov     rax, [rbx]
0x18014e10c  mov     r12, [rbx+8]
0x18014e110  lea     rsi, [rax+8]
0x18014e114  cmp     rsi, r12
0x18014e117  jz      loc_18014DEC6
0x18014e11d  mov     r13, [rsi]
0x18014e120  mov     [rbp+57h+var_D0], r13
0x18014e124  lea     r8, [rbp+57h+var_D0]
0x18014e128  lea     rdx, [rbp+57h+var_90]
0x18014e12c  lea     rcx, [rsp+120h+var_F0]
0x18014e131  call    ??$_Find_lower_bound@PEB_W@?$_Tree@V?$_Tset_traits@PEB_WUStringLessThanIgnoreCase@FontNameList@@V?$allocator@PEB_W@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@PEB_WPEAX@std@@@1@AEBQEB_W@Z; std::_Tree<std::_Tset_traits<wchar_t const *,FontNameList::StringLessThanIgnoreCase,std::allocator<wchar_t const *>,0>>::_Find_lower_bound<wchar_t const *>(wchar_t const * const &)
0x18014e136  movups  xmm6, xmmword ptr [rax]
0x18014e139  mov     r8, [rax+10h]
0x18014e13d  cmp     byte ptr [r8+19h], 0
0x18014e142  jz      loc_18014E1EB
0x18014e148  mov     rax, 666666666666666h
0x18014e152  cmp     [rsp+120h+var_E8], rax
0x18014e157  jz      loc_18014E215
0x18014e15d  mov     rbx, [rsp+120h+var_F0]
0x18014e162  lea     rax, [rsp+120h+var_F0]
0x18014e167  mov     qword ptr [rbp+57h+var_B0], rax
0x18014e16b  mov     qword ptr [rbp+57h+var_B0+8], 0
0x18014e173  mov     qword ptr [rbp+57h+var_B0+8], 0
0x18014e17b  mov     ecx, 28h ; '('
0x18014e180  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18014e185  mov     qword ptr [rbp+57h+var_B0+8], rax
0x18014e189  mov     [rax+20h], r13
0x18014e18d  mov     [rax], rbx
0x18014e190  mov     [rax+8], rbx
0x18014e194  mov     [rax+10h], rbx
0x18014e198  mov     word ptr [rax+18h], 0
0x18014e19e  mov     qword ptr [rbp+57h+var_B0+8], 0
0x18014e1a6  movdqu  xmmword ptr [rbp+57h+var_D0], xmm6
0x18014e1ab  mov     r8, rax
0x18014e1ae  lea     rdx, [rbp+57h+var_D0]
0x18014e1b2  lea     rcx, [rsp+120h+var_F0]
0x18014e1b7  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBGV?$CoalescedRegionPtr@V?$ArrayRegion@UNameDictionaryEntry@FontApi@DWriteCore@@@CacheHelpers@DWriteCore@@@CacheHelpers@DWriteCore@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBGV?$CoalescedRegionPtr@V?$ArrayRegion@UNameDictionaryEntry@FontApi@DWriteCore@@@CacheHelpers@DWriteCore@@@CacheHelpers@DWriteCore@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBGV?$CoalescedRegionPtr@V?$ArrayRegion@UNameDictionaryEntry@FontApi@DWriteCore@@@CacheHelpers@DWriteCore@@@CacheHelpers@DWriteCore@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ushort const,DWriteCore::CacheHelpers::CoalescedRegionPtr<DWriteCore::CacheHelpers::ArrayRegion<DWriteCore::FontApi::NameDictionaryEntry>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<ushort const,DWriteCore::CacheHelpers::CoalescedRegionPtr<DWriteCore::CacheHelpers::ArrayRegion<DWriteCore::FontApi::NameDictionaryEntry>>>,void *> *>,std::_Tree_node<std::pair<ushort const,DWriteCore::CacheHelpers::CoalescedRegionPtr<DWriteCore::CacheHelpers::ArrayRegion<DWriteCore::FontApi::NameDictionaryEntry>>>,void *> * const)
0x18014e1bc  mov     rdx, r13; wchar_t *
0x18014e1bf  lea     rcx, [rbp+57h+var_C0]; this
0x18014e1c3  call    ??0RefString@DWrite@@QEAA@PEB_W@Z; DWrite::RefString::RefString(wchar_t const *)
0x18014e1c8  nop
0x18014e1c9  mov     r8, rax
0x18014e1cc  lea     rdx, [rbp+57h+var_78]
0x18014e1d0  mov     rcx, r15
0x18014e1d3  call    ?AppendItem@FontNameList@@QEAAXAEBV?$GenericLanguageTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@AEBVRefString@DWrite@@@Z; FontNameList::AppendItem(GenericLanguageTag<std::wstring> const &,DWrite::RefString const &)
0x18014e1d8  nop
0x18014e1d9  mov     rcx, [rbp+57h+var_C0]; struct DWrite::RefString::Data *
0x18014e1dd  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18014e1e2  add     rsi, 8
0x18014e1e6  jmp     loc_18014E114
0x18014e1eb  mov     r8, [r8+20h]
0x18014e1ef  mov     rdx, r13
0x18014e1f2  call    ??RStringLessThanIgnoreCase@FontNameList@@QEBA_NPEB_W0@Z; FontNameList::StringLessThanIgnoreCase::operator()(wchar_t const *,wchar_t const *)
0x18014e1f7  test    al, al
0x18014e1f9  jnz     loc_18014E148
0x18014e1ff  jmp     short loc_18014E1E2
0x18014e201  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@@@@SAXXZ; SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(void)
0x18014e207  test    r8, r8
0x18014e20a  jz      loc_18014E10C
0x18014e210  jmp     loc_18014DEA6
0x18014e215  lea     rcx, aMapSetTooLong; "map/set too long"
0x18014e21c  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
  ... truncated ...
```

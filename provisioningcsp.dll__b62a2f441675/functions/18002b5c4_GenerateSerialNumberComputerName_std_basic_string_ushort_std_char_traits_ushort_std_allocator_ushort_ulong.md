# GenerateSerialNumberComputerName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ulong)

- ea: `0x18002b5c4`
- end: `0x18002bc69`
- name: `?GenerateSerialNumberComputerName@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `1701`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180011e80`

## callees

- `0x180006974`
- `0x18000918c`
- `0x1800092cc`
- `0x180009fac`
- `0x1800123ac`
- `0x180029e00`
- `0x18002a4e0`
- `0x18002aa1c`
- `0x18002b5c4`
- `0x18003130c`
- `0x1800358a0`

## import_xrefs

- `msvcrt!iswalnum` at `0x18002b830`
- `msvcrt!iswalnum` at `0x18002b84d`
- `msvcrt!iswalnum` at `0x18002b830`
- `msvcrt!iswalnum` at `0x18002b84d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b704`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b740`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b76e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b8fb`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b949`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b980`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b9ae`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002ba5e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002ba94`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002bae2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002bb1d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002bb41`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002bb8f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002bbc6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002bbf4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002bc1c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b704`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b740`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b76e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b8fb`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b949`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b980`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b9ae`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002ba5e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002ba94`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002bae2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002bb1d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002bb41`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002bb8f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002bbc6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002bbf4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002bc1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b6e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b929`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bac2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bb6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b6e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b929`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bac2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bb6f`
- `DMCmnUtils!DmGetSmbiosSerialNumber` at `0x18002b6a9`
- `DMCmnUtils!DmGetSmbiosSerialNumber` at `0x18002b6a9`

## string_xrefs

- `0x18002b6ca`: `onecoreuap\admin\dm\dmcmnutils\computernameutils\computernameutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall GenerateSerialNumberComputerName(void *a1)
{
  int SmbiosSerialNumber; // eax
  unsigned int v3; // edi
  _WORD *v5; // rdx
  __int64 v6; // r8
  void **v7; // rax
  void **v8; // rdx
  unsigned __int64 v9; // r8
  char *v10; // r14
  void **v11; // rax
  wint_t *v12; // r12
  wint_t *v13; // rdi
  wint_t *v14; // rsi
  void **v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r14
  HLOCAL hMem; // [rsp+20h] [rbp-158h] BYREF
  _BYTE v19[40]; // [rsp+28h] [rbp-150h] BYREF
  __int64 v20; // [rsp+50h] [rbp-128h] BYREF
  char v21; // [rsp+58h] [rbp-120h]
  __int128 v22; // [rsp+60h] [rbp-118h]
  __int128 v23; // [rsp+70h] [rbp-108h] BYREF
  __int64 v24; // [rsp+80h] [rbp-F8h]
  char v25; // [rsp+88h] [rbp-F0h]
  __int128 v26; // [rsp+90h] [rbp-E8h] BYREF
  char v27; // [rsp+A0h] [rbp-D8h]
  __int64 v28; // [rsp+A8h] [rbp-D0h]
  __int64 v29; // [rsp+B0h] [rbp-C8h]
  char v30; // [rsp+B8h] [rbp-C0h]
  void *v31[2]; // [rsp+C0h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+D0h] [rbp-A8h]
  unsigned __int64 v33; // [rsp+D8h] [rbp-A0h]
  void *v34[2]; // [rsp+E0h] [rbp-98h] BYREF
  __int64 v35; // [rsp+F0h] [rbp-88h]
  unsigned __int64 v36; // [rsp+F8h] [rbp-80h]
  void *v37; // [rsp+100h] [rbp-78h] BYREF
  __int64 v38; // [rsp+110h] [rbp-68h]
  unsigned __int64 v39; // [rsp+118h] [rbp-60h]
  void *v40[3]; // [rsp+120h] [rbp-58h] BYREF
  unsigned __int64 v41; // [rsp+138h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(
    v19,
    L"(%SERIAL%)");
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  if ( (unsigned __int8)std::regex_search<std::char_traits<unsigned short>,std::allocator<unsigned short>,std::allocator<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>,unsigned short,std::regex_traits<unsigned short>>(
                          a1,
                          &v20,
                          v19) )
  {
    std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::str(
      (char *)&v23 + 8,
      &v37);
    std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::str(&v26, v34);
    hMem = 0;
    SmbiosSerialNumber = DmGetSmbiosSerialNumber((unsigned __int16 **)&hMem);
    v3 = SmbiosSerialNumber;
    if ( SmbiosSerialNumber < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x47,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\computernameutils\\computernameutils.cpp",
        (const char *)(unsigned int)SmbiosSerialNumber,
        (int)hMem);
      if ( hMem )
        LocalFree(hMem);
      if ( v36 >= 8 )
        operator delete(v34[0]);
      v36 = 7;
      v35 = 0;
      LOWORD(v34[0]) = 0;
      if ( v39 >= 8 )
        operator delete(v37);
      v39 = 7;
      v38 = 0;
      LOWORD(v37) = 0;
      if ( (_QWORD)v22 )
        operator delete((void *)v22);
      std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v19);
      return v3;
    }
    v5 = hMem;
    hMem = 0;
    v33 = 7;
    v32 = 0;
    LOWORD(v31[0]) = 0;
    if ( *v5 )
    {
      v6 = -1;
      do
        ++v6;
      while ( v5[v6] );
    }
    std::wstring::assign(v31, v5);
    v7 = v31;
    v8 = (void **)v31[0];
    v9 = v33;
    if ( v33 >= 8 )
      v7 = (void **)v31[0];
    v10 = (char *)v7 + 2 * v32;
    v11 = v31;
    if ( v33 >= 8 )
      v11 = (void **)v31[0];
    v12 = (wint_t *)v11 + v32;
    v13 = (wint_t *)v31;
    if ( v33 >= 8 )
      v13 = (wint_t *)v31[0];
    if ( v13 != v12 )
    {
      while ( 1 )
      {
        v14 = v13 + 1;
        if ( !iswalnum(*v13) )
          break;
        ++v13;
        if ( v14 == v12 )
          goto LABEL_29;
      }
      while ( v14 != v12 )
      {
        if ( iswalnum(*v14) )
          *v13++ = *v14;
        ++v14;
      }
LABEL_29:
      v8 = (void **)v31[0];
      v9 = v33;
    }
    v15 = v31;
    if ( v9 >= 8 )
      v15 = v8;
    if ( v13 )
      v16 = ((char *)v13 - (char *)v15) >> 1;
    else
      v16 = 0;
    if ( v10 )
      v17 = (v10 - (char *)v13) >> 1;
    else
      v17 = 0;
    std::wstring::erase(v31, v16, v17);
    if ( (unsigned int)(v38 + v35) > 0xF )
    {
      if ( v33 >= 8 )
        operator delete(v31[0]);
      v33 = 7;
      v32 = 0;
      LOWORD(v31[0]) = 0;
      if ( hMem )
        LocalFree(hMem);
      if ( v36 >= 8 )
        operator delete(v34[0]);
      v36 = 7;
      v35 = 0;
      LOWORD(v34[0]) = 0;
      if ( v39 >= 8 )
        operator delete(v37);
      v39 = 7;
      v38 = 0;
      LOWORD(v37) = 0;
      if ( (_QWORD)v22 )
        operator delete((void *)v22);
      goto LABEL_50;
    }
    if ( 15 == (_DWORD)v38 + (_DWORD)v35 )
    {
      if ( v33 >= 8 )
        operator delete(v31[0]);
      v33 = 7;
      v32 = 0;
      LOWORD(v31[0]) = 0;
      if ( hMem )
        LocalFree(hMem);
      if ( v36 >= 8 )
        operator delete(v34[0]);
      v36 = 7;
      v35 = 0;
      LOWORD(v34[0]) = 0;
      if ( v39 >= 8 )
        operator delete(v37);
      v39 = 7;
      v38 = 0;
      LOWORD(v37) = 0;
      if ( (_QWORD)v22 )
        operator delete((void *)v22);
LABEL_50:
      std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v19);
      return 2147944751LL;
    }
    std::wstring::assign(a1);
    v41 = 7;
    v40[2] = 0;
    LOWORD(v40[0]) = 0;
    std::wstring::assign(v40);
    std::wstring::append(a1, v40, 0, -1);
    if ( v41 >= 8 )
      operator delete(v40[0]);
    std::wstring::append(a1, v34, 0, -1);
    if ( v33 >= 8 )
      operator delete(v31[0]);
    v33 = 7;
    v32 = 0;
    LOWORD(v31[0]) = 0;
    if ( hMem )
      LocalFree(hMem);
    if ( v36 >= 8 )
      operator delete(v34[0]);
    v36 = 7;
    v35 = 0;
    LOWORD(v34[0]) = 0;
    if ( v39 >= 8 )
      operator delete(v37);
  }
  if ( (_QWORD)v22 )
    operator delete((void *)v22);
  std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v19);
  return 0;
}

```

## disassembly

```asm
0x18002b5c4  mov     [rsp+arg_8], rbx
0x18002b5c9  mov     [rsp+arg_10], rsi
0x18002b5ce  push    rdi
0x18002b5cf  push    r12
0x18002b5d1  push    r13
0x18002b5d3  push    r14
0x18002b5d5  push    r15
0x18002b5d7  sub     rsp, 150h
0x18002b5de  mov     rax, cs:__security_cookie
0x18002b5e5  xor     rax, rsp
0x18002b5e8  mov     [rsp+178h+var_38], rax
0x18002b5f0  mov     r13, rcx
0x18002b5f3  xor     esi, esi
0x18002b5f5  lea     rdx, aSerial; "(%SERIAL%)"
0x18002b5fc  lea     rcx, [rsp+178h+var_150]
0x18002b601  call    ??0?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@PEBGW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::basic_regex<ushort,std::regex_traits<ushort>>(ushort const *,std::regex_constants::syntax_option_type)
0x18002b606  nop
0x18002b607  mov     [rsp+178h+var_128], rsi
0x18002b60c  mov     [rsp+178h+var_120], sil
0x18002b611  xorps   xmm0, xmm0
0x18002b614  movdqa  [rsp+178h+var_118], xmm0
0x18002b61a  xorps   xmm1, xmm1
0x18002b61d  movdqa  [rsp+178h+var_108], xmm1
0x18002b623  mov     [rsp+178h+var_F8], rsi
0x18002b62b  mov     [rsp+178h+var_F0], sil
0x18002b633  movdqa  [rsp+178h+var_E8], xmm0
0x18002b63c  mov     [rsp+178h+var_D8], sil
0x18002b644  mov     [rsp+178h+var_D0], rsi
0x18002b64c  mov     [rsp+178h+var_C8], rsi
0x18002b654  mov     [rsp+178h+var_C0], sil
0x18002b65c  lea     r8, [rsp+178h+var_150]
0x18002b661  lea     rdx, [rsp+178h+var_128]
0x18002b666  mov     rcx, r13
0x18002b669  call    ??$regex_search@U?$char_traits@G@std@@V?$allocator@G@2@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@GV?$regex_traits@G@2@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEAV?$match_results@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@@0@AEBV?$basic_regex@GV?$regex_traits@G@std@@@0@W4match_flag_type@regex_constants@0@@Z; std::regex_search<std::char_traits<ushort>,std::allocator<ushort>,std::allocator<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>,ushort,std::regex_traits<ushort>>(std::wstring const &,std::match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> &,std::basic_regex<ushort,std::regex_traits<ushort>> const &,std::regex_constants::match_flag_type)
0x18002b66e  test    al, al
0x18002b670  jz      loc_18002BC12
0x18002b676  lea     rdx, [rsp+178h+var_78]
0x18002b67e  lea     rcx, [rsp+178h+var_108+8]
0x18002b683  call    ?str@?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::str(void)
0x18002b688  nop
0x18002b689  lea     rdx, [rsp+178h+var_98]
0x18002b691  lea     rcx, [rsp+178h+var_E8]
0x18002b699  call    ?str@?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::str(void)
0x18002b69e  nop
0x18002b69f  mov     [rsp+178h+hMem], rsi; int
0x18002b6a4  lea     rcx, [rsp+178h+hMem]
0x18002b6a9  call    cs:__imp_?DmGetSmbiosSerialNumber@@YAJPEAPEAG@Z; DmGetSmbiosSerialNumber(ushort * *)
0x18002b6b0  nop     dword ptr [rax+rax+00h]
0x18002b6b5  mov     edi, eax
0x18002b6b7  test    eax, eax
0x18002b6b9  jns     loc_18002B78C
0x18002b6bf  mov     rcx, [rsp+178h]; this
0x18002b6c7  mov     r9d, eax; char *
0x18002b6ca  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\dm\\dmcmnutils\\comp"...
0x18002b6d1  lea     edx, [rsi+47h]; void *
0x18002b6d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b6d9  nop
0x18002b6da  mov     rcx, [rsp+178h+hMem]; hMem
0x18002b6df  test    rcx, rcx
0x18002b6e2  jz      short loc_18002B6F1
0x18002b6e4  call    cs:__imp_LocalFree
0x18002b6eb  nop     dword ptr [rax+rax+00h]
0x18002b6f0  nop
0x18002b6f1  cmp     [rsp+178h+var_80], 8
0x18002b6fa  jb      short loc_18002B710
0x18002b6fc  mov     rcx, [rsp+178h+var_98]
0x18002b704  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b70b  nop     dword ptr [rax+rax+00h]
0x18002b710  mov     ebx, 7
0x18002b715  mov     [rsp+178h+var_80], rbx
0x18002b71d  mov     [rsp+178h+var_88], rsi
0x18002b725  mov     word ptr [rsp+178h+var_98], si
0x18002b72d  cmp     [rsp+178h+var_60], 8
0x18002b736  jb      short loc_18002B74C
0x18002b738  mov     rcx, [rsp+178h+var_78]
0x18002b740  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b747  nop     dword ptr [rax+rax+00h]
0x18002b74c  mov     [rsp+178h+var_60], rbx
0x18002b754  mov     [rsp+178h+var_68], rsi
0x18002b75c  mov     word ptr [rsp+178h+var_78], si
0x18002b764  mov     rcx, qword ptr [rsp+178h+var_118]
0x18002b769  test    rcx, rcx
0x18002b76c  jz      short loc_18002B77B
0x18002b76e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b775  nop     dword ptr [rax+rax+00h]
0x18002b77a  nop
0x18002b77b  lea     rcx, [rsp+178h+var_150]
0x18002b780  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x18002b785  mov     eax, edi
0x18002b787  jmp     loc_18002BC3B
0x18002b78c  mov     rdx, [rsp+178h+hMem]; Src
0x18002b791  mov     [rsp+178h+hMem], rsi
0x18002b796  mov     ebx, 7
0x18002b79b  mov     [rsp+178h+var_A0], rbx
0x18002b7a3  mov     [rsp+178h+var_A8], rsi
0x18002b7ab  mov     word ptr [rsp+178h+var_B8], si
0x18002b7b3  or      r15, 0FFFFFFFFFFFFFFFFh
0x18002b7b7  cmp     [rdx], si
0x18002b7ba  jnz     short loc_18002B7C1
0x18002b7bc  mov     r8, rsi
0x18002b7bf  jmp     short loc_18002B7CE
0x18002b7c1  mov     r8, r15
0x18002b7c4  inc     r8
0x18002b7c7  cmp     [rdx+r8*2], si
0x18002b7cc  jnz     short loc_18002B7C4
0x18002b7ce  lea     rcx, [rsp+178h+var_B8]; void *
0x18002b7d6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18002b7db  nop
0x18002b7dc  lea     rax, [rsp+178h+var_B8]
0x18002b7e4  mov     rdx, [rsp+178h+var_B8]
0x18002b7ec  mov     r8, [rsp+178h+var_A0]
0x18002b7f4  cmp     r8, 8
0x18002b7f8  cmovnb  rax, rdx
0x18002b7fc  mov     rcx, [rsp+178h+var_A8]
0x18002b804  lea     r14, [rax+rcx*2]
0x18002b808  lea     rax, [rsp+178h+var_B8]
0x18002b810  cmovnb  rax, rdx
0x18002b814  lea     r12, [rax+rcx*2]
0x18002b818  lea     rdi, [rsp+178h+var_B8]
0x18002b820  cmovnb  rdi, rdx
0x18002b824  cmp     rdi, r12
0x18002b827  jz      short loc_18002B882
0x18002b829  lea     rsi, [rdi+2]
0x18002b82d  movzx   ecx, word ptr [rdi]; C
0x18002b830  call    cs:__imp_iswalnum
0x18002b837  nop     dword ptr [rax+rax+00h]
0x18002b83c  test    eax, eax
0x18002b83e  jz      short loc_18002B86B
0x18002b840  mov     rdi, rsi
0x18002b843  cmp     rsi, r12
0x18002b846  jnz     short loc_18002B829
0x18002b848  jmp     short loc_18002B870
0x18002b84a  movzx   ecx, word ptr [rsi]; C
0x18002b84d  call    cs:__imp_iswalnum
0x18002b854  nop     dword ptr [rax+rax+00h]
0x18002b859  test    eax, eax
0x18002b85b  jz      short loc_18002B867
0x18002b85d  movzx   eax, word ptr [rsi]
0x18002b860  mov     [rdi], ax
0x18002b863  add     rdi, 2
0x18002b867  add     rsi, 2
0x18002b86b  cmp     rsi, r12
0x18002b86e  jnz     short loc_18002B84A
0x18002b870  xor     esi, esi
0x18002b872  mov     rdx, [rsp+178h+var_B8]
0x18002b87a  mov     r8, [rsp+178h+var_A0]
0x18002b882  lea     rax, [rsp+178h+var_B8]
0x18002b88a  cmp     r8, 8
0x18002b88e  cmovnb  rax, rdx
0x18002b892  test    rdi, rdi
0x18002b895  jnz     short loc_18002B89C
0x18002b897  mov     rdx, rsi
0x18002b89a  jmp     short loc_18002B8A5
0x18002b89c  mov     rdx, rdi
0x18002b89f  sub     rdx, rax
0x18002b8a2  sar     rdx, 1
0x18002b8a5  test    r14, r14
0x18002b8a8  jnz     short loc_18002B8AF
0x18002b8aa  mov     r14, rsi
0x18002b8ad  jmp     short loc_18002B8B5
0x18002b8af  sub     r14, rdi
0x18002b8b2  sar     r14, 1
0x18002b8b5  mov     r8, r14
0x18002b8b8  lea     rcx, [rsp+178h+var_B8]
0x18002b8c0  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x18002b8c5  mov     edx, dword ptr [rsp+178h+var_88]
0x18002b8cc  add     edx, dword ptr [rsp+178h+var_68]
0x18002b8d3  mov     eax, 0Fh
0x18002b8d8  cmp     edx, eax
0x18002b8da  ja      loc_18002BB2E
0x18002b8e0  sub     eax, edx
0x18002b8e2  jnz     loc_18002B9CF
0x18002b8e8  cmp     [rsp+178h+var_A0], 8
0x18002b8f1  jb      short loc_18002B907
0x18002b8f3  mov     rcx, [rsp+178h+var_B8]
0x18002b8fb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b902  nop     dword ptr [rax+rax+00h]
0x18002b907  mov     [rsp+178h+var_A0], rbx
0x18002b90f  mov     [rsp+178h+var_A8], rsi
0x18002b917  mov     word ptr [rsp+178h+var_B8], si
0x18002b91f  mov     rcx, [rsp+178h+hMem]; hMem
0x18002b924  test    rcx, rcx
0x18002b927  jz      short loc_18002B936
0x18002b929  call    cs:__imp_LocalFree
0x18002b930  nop     dword ptr [rax+rax+00h]
0x18002b935  nop
0x18002b936  cmp     [rsp+178h+var_80], 8
0x18002b93f  jb      short loc_18002B955
0x18002b941  mov     rcx, [rsp+178h+var_98]
0x18002b949  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b950  nop     dword ptr [rax+rax+00h]
0x18002b955  mov     [rsp+178h+var_80], rbx
0x18002b95d  mov     [rsp+178h+var_88], rsi
0x18002b965  mov     word ptr [rsp+178h+var_98], si
0x18002b96d  cmp     [rsp+178h+var_60], 8
0x18002b976  jb      short loc_18002B98C
0x18002b978  mov     rcx, [rsp+178h+var_78]
0x18002b980  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b987  nop     dword ptr [rax+rax+00h]
0x18002b98c  mov     [rsp+178h+var_60], rbx
0x18002b994  mov     [rsp+178h+var_68], rsi
0x18002b99c  mov     word ptr [rsp+178h+var_78], si
0x18002b9a4  mov     rcx, qword ptr [rsp+178h+var_118]
0x18002b9a9  test    rcx, rcx
0x18002b9ac  jz      short loc_18002B9BB
0x18002b9ae  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b9b5  nop     dword ptr [rax+rax+00h]
0x18002b9ba  nop
0x18002b9bb  lea     rcx, [rsp+178h+var_150]
0x18002b9c0  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x18002b9c5  mov     eax, 8007092Fh
0x18002b9ca  jmp     loc_18002BC3B
0x18002b9cf  mov     edx, dword ptr [rsp+178h+var_A8]
0x18002b9d6  cmp     edx, eax
0x18002b9d8  jb      short loc_18002B9E0
0x18002b9da  mov     ecx, edx
0x18002b9dc  sub     ecx, eax
0x18002b9de  jmp     short loc_18002B9E3
0x18002b9e0  or      ecx, 0FFFFFFFFh
0x18002b9e3  mov     edi, esi
0x18002b9e5  cmp     edx, eax
0x18002b9e7  cmovnb  edi, ecx
0x18002b9ea  mov     r9, r15
0x18002b9ed  xor     r8d, r8d
0x18002b9f0  lea     rdx, [rsp+178h+var_78]
0x18002b9f8  mov     rcx, r13; void *
0x18002b9fb  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18002ba00  mov     [rsp+178h+var_40], rbx
0x18002ba08  mov     [rsp+178h+var_48], rsi
0x18002ba10  mov     word ptr [rsp+178h+var_58], si
0x18002ba18  mov     r8d, edi
0x18002ba1b  mov     r9, r15
0x18002ba1e  lea     rdx, [rsp+178h+var_B8]
0x18002ba26  lea     rcx, [rsp+178h+var_58]; void *
0x18002ba2e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18002ba33  nop
0x18002ba34  mov     r9, r15
0x18002ba37  xor     r8d, r8d
0x18002ba3a  lea     rdx, [rsp+178h+var_58]
0x18002ba42  mov     rcx, r13
0x18002ba45  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18002ba4a  nop
0x18002ba4b  cmp     [rsp+178h+var_40], 8
0x18002ba54  jb      short loc_18002BA6A
0x18002ba56  mov     rcx, [rsp+178h+var_58]
0x18002ba5e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002ba65  nop     dword ptr [rax+rax+00h]
0x18002ba6a  mov     r9, r15
0x18002ba6d  xor     r8d, r8d
0x18002ba70  lea     rdx, [rsp+178h+var_98]
0x18002ba78  mov     rcx, r13
0x18002ba7b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18002ba80  nop
0x18002ba81  cmp     [rsp+178h+var_A0], 8
0x18002ba8a  jb      short loc_18002BAA0
0x18002ba8c  mov     rcx, [rsp+178h+var_B8]
0x18002ba94  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002ba9b  nop     dword ptr [rax+rax+00h]
0x18002baa0  mov     [rsp+178h+var_A0], rbx
0x18002baa8  mov     [rsp+178h+var_A8], rsi
0x18002bab0  mov     word ptr [rsp+178h+var_B8], si
0x18002bab8  mov     rcx, [rsp+178h+hMem]; hMem
0x18002babd  test    rcx, rcx
0x18002bac0  jz      short loc_18002BACF
0x18002bac2  call    cs:__imp_LocalFree
0x18002bac9  nop     dword ptr [rax+rax+00h]
0x18002bace  nop
0x18002bacf  cmp     [rsp+178h+var_80], 8
0x18002bad8  jb      short loc_18002BAEE
0x18002bada  mov     rcx, [rsp+178h+var_98]
0x18002bae2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002bae9  nop     dword ptr [rax+rax+00h]
0x18002baee  mov     [rsp+178h+var_80], rbx
0x18002baf6  mov     [rsp+178h+var_88], rsi
0x18002bafe  mov     word ptr [rsp+178h+var_98], si
0x18002bb06  cmp     [rsp+178h+var_60], 8
0x18002bb0f  jb      loc_18002BC12
0x18002bb15  mov     rcx, [rsp+178h+var_78]
0x18002bb1d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002bb24  nop     dword ptr [rax+rax+00h]
0x18002bb29  jmp     loc_18002BC12
0x18002bb2e  cmp     [rsp+178h+var_A0], 8
0x18002bb37  jb      short loc_18002BB4D
0x18002bb39  mov     rcx, [rsp+178h+var_B8]
0x18002bb41  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002bb48  nop     dword ptr [rax+rax+00h]
0x18002bb4d  mov     [rsp+178h+var_A0], rbx
0x18002bb55  mov     [rsp+178h+var_A8], rsi
0x18002bb5d  mov     word ptr [rsp+178h+var_B8], si
0x18002bb65  mov     rcx, [rsp+178h+hMem]; hMem
0x18002bb6a  test    rcx, rcx
0x18002bb6d  jz      short loc_18002BB7C
0x18002bb6f  call    cs:__imp_LocalFree
0x18002bb76  nop     dword ptr [rax+rax+00h]
0x18002bb7b  nop
0x18002bb7c  cmp     [rsp+178h+var_80], 8
0x18002bb85  jb      short loc_18002BB9B
0x18002bb87  mov     rcx, [rsp+178h+var_98]
0x18002bb8f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002bb96  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```

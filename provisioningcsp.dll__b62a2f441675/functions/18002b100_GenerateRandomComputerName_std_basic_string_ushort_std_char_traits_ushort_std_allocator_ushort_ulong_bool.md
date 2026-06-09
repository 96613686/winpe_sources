# GenerateRandomComputerName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ulong,bool *)

- ea: `0x18002b100`
- end: `0x18002b5bd`
- name: `?GenerateRandomComputerName@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KPEA_N@Z`
- size: `1213`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180011e80`

## callees

- `0x180006974`
- `0x180007268`
- `0x18000918c`
- `0x1800123ac`
- `0x1800124ac`
- `0x180029e00`
- `0x18002a4e0`
- `0x18002aa1c`
- `0x18002b100`
- `0x18003130c`
- `0x1800358a0`

## import_xrefs

- `msvcrt!srand` at `0x18002b3ae`
- `msvcrt!srand` at `0x18002b3ae`
- `msvcrt!_wtoi` at `0x18002b205`
- `msvcrt!_wtoi` at `0x18002b205`
- `msvcrt!rand` at `0x18002b3dc`
- `msvcrt!rand` at `0x18002b3dc`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b237`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b26e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b306`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b343`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b372`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b456`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b493`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b4c2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b520`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b55d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b574`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b237`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b26e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b306`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b343`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b372`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b456`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b493`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b4c2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b520`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b55d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b574`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b390`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b390`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002b39e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002b39e`

## string_xrefs

- `0x18002b252`: `onecoreuap\admin\dm\dmcmnutils\computernameutils\computernameutils.cpp`
- `0x18002b2e1`: `onecoreuap\admin\dm\dmcmnutils\computernameutils\computernameutils.cpp`
- `0x18002b431`: `onecoreuap\admin\dm\dmcmnutils\computernameutils\computernameutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall GenerateRandomComputerName(void *a1, __int64 a2, _BYTE *a3)
{
  _QWORD *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // esi
  unsigned int v9; // ebx
  DWORD CurrentThreadId; // ebx
  DWORD TickCount; // eax
  unsigned int i; // ebx
  int v14; // eax
  int v15; // eax
  unsigned int v16; // r14d
  unsigned __int16 v17[2]; // [rsp+20h] [rbp-128h] BYREF
  _BYTE v18[40]; // [rsp+28h] [rbp-120h] BYREF
  __int64 v19; // [rsp+50h] [rbp-F8h] BYREF
  char v20; // [rsp+58h] [rbp-F0h]
  __int128 v21; // [rsp+60h] [rbp-E8h]
  __int128 v22; // [rsp+70h] [rbp-D8h] BYREF
  __int64 v23; // [rsp+80h] [rbp-C8h]
  char v24; // [rsp+88h] [rbp-C0h]
  __int128 v25; // [rsp+90h] [rbp-B8h] BYREF
  char v26; // [rsp+A0h] [rbp-A8h]
  _QWORD v27[2]; // [rsp+A8h] [rbp-A0h] BYREF
  char v28; // [rsp+B8h] [rbp-90h]
  void *v29[2]; // [rsp+C0h] [rbp-88h] BYREF
  __int64 v30; // [rsp+D0h] [rbp-78h]
  unsigned __int64 v31; // [rsp+D8h] [rbp-70h]
  void *v32; // [rsp+E0h] [rbp-68h] BYREF
  __int64 v33; // [rsp+F0h] [rbp-58h]
  unsigned __int64 v34; // [rsp+F8h] [rbp-50h]
  void *v35[4]; // [rsp+100h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(
    v18,
    L"(%RAND:)(\\d+)(%)");
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27[0] = 0;
  v27[1] = 0;
  v28 = 0;
  *a3 = 0;
  if ( (unsigned __int8)std::regex_search<std::char_traits<unsigned short>,std::allocator<unsigned short>,std::allocator<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>,unsigned short,std::regex_traits<unsigned short>>(
                          a1,
                          &v19,
                          v18) )
  {
    *a3 = 1;
    if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v21 + 1) - v21) >> 3) > 2 )
      v5 = (_QWORD *)(v21 + 48);
    else
      v5 = v27;
    v6 = std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::str(v5, v35);
    if ( *(_QWORD *)(v6 + 24) >= 8u )
      v6 = *(_QWORD *)v6;
    v7 = _wtoi((const wchar_t *)v6);
    v8 = -1;
    if ( v7 >= 0 )
      v8 = v7;
    v9 = (v7 >> 31) & 0x80070216;
    if ( v35[3] >= (void *)8 )
      operator delete(v35[0]);
    if ( (v9 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\computernameutils\\computernameutils.cpp",
        (const char *)v9,
        *(int *)v17);
      if ( (_QWORD)v21 )
        operator delete((void *)v21);
      std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v18);
      return v9;
    }
    std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::str(
      (char *)&v22 + 8,
      &v32);
    std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::str(&v25, v29);
    if ( v33 + v30 + (unsigned __int64)v8 > 0xF )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\computernameutils\\computernameutils.cpp",
        (const char *)0x8007092FLL,
        *(int *)v17);
      if ( v31 >= 8 )
        operator delete(v29[0]);
      v31 = 7;
      v30 = 0;
      LOWORD(v29[0]) = 0;
      if ( v34 >= 8 )
        operator delete(v32);
      v34 = 7;
      v33 = 0;
      LOWORD(v32) = 0;
      if ( (_QWORD)v21 )
        operator delete((void *)v21);
      std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v18);
      return 2147944751LL;
    }
    CurrentThreadId = GetCurrentThreadId();
    TickCount = GetTickCount();
    srand(TickCount ^ CurrentThreadId);
    std::wstring::assign(a1);
    for ( i = 0; i < v8; ++i )
    {
      v14 = rand();
      v15 = StringCchPrintfW(v17, 2u, L"%d", (unsigned int)(v14 % 10));
      v16 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2D,
          (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\computernameutils\\computernameutils.cpp",
          (const char *)(unsigned int)v15,
          *(int *)v17);
        if ( v31 >= 8 )
          operator delete(v29[0]);
        v31 = 7;
        v30 = 0;
        LOWORD(v29[0]) = 0;
        if ( v34 >= 8 )
          operator delete(v32);
        v34 = 7;
        v33 = 0;
        LOWORD(v32) = 0;
        if ( (_QWORD)v21 )
          operator delete((void *)v21);
        std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v18);
        return v16;
      }
      std::wstring::append(a1, v17);
    }
    std::wstring::append(a1, v29, 0, -1);
    if ( v31 >= 8 )
      operator delete(v29[0]);
    v31 = 7;
    v30 = 0;
    LOWORD(v29[0]) = 0;
    if ( v34 >= 8 )
      operator delete(v32);
  }
  if ( (_QWORD)v21 )
    operator delete((void *)v21);
  std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v18);
  return 0;
}

```

## disassembly

```asm
0x18002b100  mov     [rsp+arg_8], rbx
0x18002b105  mov     [rsp+arg_18], rsi
0x18002b10a  push    rdi
0x18002b10b  push    r14
0x18002b10d  push    r15
0x18002b10f  sub     rsp, 130h
0x18002b116  mov     rax, cs:__security_cookie
0x18002b11d  xor     rax, rsp
0x18002b120  mov     [rsp+148h+var_28], rax
0x18002b128  mov     rbx, r8
0x18002b12b  mov     rdi, rcx
0x18002b12e  lea     rdx, aRandD; "(%RAND:)(\\d+)(%)"
0x18002b135  lea     rcx, [rsp+148h+var_120]
0x18002b13a  call    ??0?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@PEBGW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::basic_regex<ushort,std::regex_traits<ushort>>(ushort const *,std::regex_constants::syntax_option_type)
0x18002b13f  nop
0x18002b140  xor     r15d, r15d
0x18002b143  mov     [rsp+148h+var_F8], r15
0x18002b148  mov     [rsp+148h+var_F0], r15b
0x18002b14d  xorps   xmm0, xmm0
0x18002b150  movdqa  [rsp+148h+var_E8], xmm0
0x18002b156  xorps   xmm1, xmm1
0x18002b159  movdqa  [rsp+148h+var_D8], xmm1
0x18002b15f  mov     [rsp+148h+var_C8], r15
0x18002b167  mov     [rsp+148h+var_C0], r15b
0x18002b16f  movdqa  [rsp+148h+var_B8], xmm0
0x18002b178  mov     [rsp+148h+var_A8], r15b
0x18002b180  mov     [rsp+148h+var_A0], r15
0x18002b188  mov     [rsp+148h+var_98], r15
0x18002b190  mov     [rsp+148h+var_90], r15b
0x18002b198  mov     [rbx], r15b
0x18002b19b  lea     r8, [rsp+148h+var_120]
0x18002b1a0  lea     rdx, [rsp+148h+var_F8]
0x18002b1a5  mov     rcx, rdi
0x18002b1a8  call    ??$regex_search@U?$char_traits@G@std@@V?$allocator@G@2@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@GV?$regex_traits@G@2@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEAV?$match_results@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@@0@AEBV?$basic_regex@GV?$regex_traits@G@std@@@0@W4match_flag_type@regex_constants@0@@Z; std::regex_search<std::char_traits<ushort>,std::allocator<ushort>,std::allocator<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>,ushort,std::regex_traits<ushort>>(std::wstring const &,std::match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> &,std::basic_regex<ushort,std::regex_traits<ushort>> const &,std::regex_constants::match_flag_type)
0x18002b1ad  test    al, al
0x18002b1af  jz      loc_18002B56A
0x18002b1b5  mov     byte ptr [rbx], 1
0x18002b1b8  mov     rcx, qword ptr [rsp+148h+var_E8]
0x18002b1bd  mov     rax, qword ptr [rsp+148h+var_E8+8]
0x18002b1c2  sub     rax, rcx
0x18002b1c5  sar     rax, 3
0x18002b1c9  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18002b1d3  imul    rax, rdx
0x18002b1d7  cmp     rax, 2
0x18002b1db  ja      short loc_18002B1E7
0x18002b1dd  lea     rcx, [rsp+148h+var_A0]
0x18002b1e5  jmp     short loc_18002B1EB
0x18002b1e7  add     rcx, 30h ; '0'
0x18002b1eb  lea     rdx, [rsp+148h+var_48]
0x18002b1f3  call    ?str@?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::str(void)
0x18002b1f8  cmp     qword ptr [rax+18h], 8
0x18002b1fd  jb      short loc_18002B202
0x18002b1ff  mov     rax, [rax]
0x18002b202  mov     rcx, rax; String
0x18002b205  call    cs:__imp__wtoi
0x18002b20c  nop     dword ptr [rax+rax+00h]
0x18002b211  mov     ebx, eax
0x18002b213  or      esi, 0FFFFFFFFh
0x18002b216  test    eax, eax
0x18002b218  cmovns  esi, eax
0x18002b21b  sar     ebx, 1Fh
0x18002b21e  and     ebx, 80070216h
0x18002b224  cmp     [rsp+148h+var_30], 8
0x18002b22d  jb      short loc_18002B243
0x18002b22f  mov     rcx, [rsp+148h+var_48]
0x18002b237  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b23e  nop     dword ptr [rax+rax+00h]
0x18002b243  test    ebx, ebx
0x18002b245  jns     short loc_18002B28C
0x18002b247  mov     rcx, [rsp+148h]; this
0x18002b24f  mov     r9d, ebx; char *
0x18002b252  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\dm\\dmcmnutils\\comp"...
0x18002b259  mov     edx, 21h ; '!'; void *
0x18002b25e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b263  nop
0x18002b264  mov     rcx, qword ptr [rsp+148h+var_E8]
0x18002b269  test    rcx, rcx
0x18002b26c  jz      short loc_18002B27B
0x18002b26e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b275  nop     dword ptr [rax+rax+00h]
0x18002b27a  nop
0x18002b27b  lea     rcx, [rsp+148h+var_120]
0x18002b280  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x18002b285  mov     eax, ebx
0x18002b287  jmp     loc_18002B593
0x18002b28c  lea     rdx, [rsp+148h+var_68]
0x18002b294  lea     rcx, [rsp+148h+var_D8+8]
0x18002b299  call    ?str@?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::str(void)
0x18002b29e  nop
0x18002b29f  lea     rdx, [rsp+148h+var_88]
0x18002b2a7  lea     rcx, [rsp+148h+var_B8]
0x18002b2af  call    ?str@?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::str(void)
0x18002b2b4  nop
0x18002b2b5  mov     eax, esi
0x18002b2b7  add     rax, [rsp+148h+var_78]
0x18002b2bf  add     rax, [rsp+148h+var_58]
0x18002b2c7  cmp     rax, 0Fh
0x18002b2cb  jbe     loc_18002B390
0x18002b2d1  mov     rcx, [rsp+148h]; this
0x18002b2d9  mov     edi, 8007092Fh
0x18002b2de  mov     r9d, edi; char *
0x18002b2e1  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\dm\\dmcmnutils\\comp"...
0x18002b2e8  mov     edx, 26h ; '&'; void *
0x18002b2ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b2f2  nop
0x18002b2f3  cmp     [rsp+148h+var_70], 8
0x18002b2fc  jb      short loc_18002B312
0x18002b2fe  mov     rcx, [rsp+148h+var_88]
0x18002b306  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b30d  nop     dword ptr [rax+rax+00h]
0x18002b312  mov     ebx, 7
0x18002b317  mov     [rsp+148h+var_70], rbx
0x18002b31f  mov     [rsp+148h+var_78], r15
0x18002b327  mov     word ptr [rsp+148h+var_88], r15w
0x18002b330  cmp     [rsp+148h+var_50], 8
0x18002b339  jb      short loc_18002B34F
0x18002b33b  mov     rcx, [rsp+148h+var_68]
0x18002b343  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b34a  nop     dword ptr [rax+rax+00h]
0x18002b34f  mov     [rsp+148h+var_50], rbx
0x18002b357  mov     [rsp+148h+var_58], r15
0x18002b35f  mov     word ptr [rsp+148h+var_68], r15w
0x18002b368  mov     rcx, qword ptr [rsp+148h+var_E8]
0x18002b36d  test    rcx, rcx
0x18002b370  jz      short loc_18002B37F
0x18002b372  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b379  nop     dword ptr [rax+rax+00h]
0x18002b37e  nop
0x18002b37f  lea     rcx, [rsp+148h+var_120]
0x18002b384  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x18002b389  mov     eax, edi
0x18002b38b  jmp     loc_18002B593
0x18002b390  call    cs:__imp_GetCurrentThreadId
0x18002b397  nop     dword ptr [rax+rax+00h]
0x18002b39c  mov     ebx, eax
0x18002b39e  call    cs:__imp_GetTickCount
0x18002b3a5  nop     dword ptr [rax+rax+00h]
0x18002b3aa  xor     ebx, eax
0x18002b3ac  mov     ecx, ebx; Seed
0x18002b3ae  call    cs:__imp_srand
0x18002b3b5  nop     dword ptr [rax+rax+00h]
0x18002b3ba  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002b3be  xor     r8d, r8d
0x18002b3c1  lea     rdx, [rsp+148h+var_68]
0x18002b3c9  mov     rcx, rdi; void *
0x18002b3cc  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18002b3d1  mov     ebx, r15d
0x18002b3d4  cmp     ebx, esi
0x18002b3d6  jnb     loc_18002B4F5
0x18002b3dc  call    cs:__imp_rand
0x18002b3e3  nop     dword ptr [rax+rax+00h]
0x18002b3e8  mov     r9d, eax
0x18002b3eb  mov     eax, 66666667h
0x18002b3f0  imul    r9d
0x18002b3f3  sar     edx, 2
0x18002b3f6  mov     eax, edx
0x18002b3f8  shr     eax, 1Fh
0x18002b3fb  add     edx, eax
0x18002b3fd  lea     eax, [rdx+rdx*4]
0x18002b400  add     eax, eax
0x18002b402  sub     r9d, eax
0x18002b405  lea     r8, aD; "%d"
0x18002b40c  mov     edx, 2; unsigned __int64
0x18002b411  lea     rcx, [rsp+148h+var_128]; unsigned __int16 *
0x18002b416  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002b41b  mov     r14d, eax
0x18002b41e  test    eax, eax
0x18002b420  jns     loc_18002B4E1
0x18002b426  mov     rcx, [rsp+148h]; this
0x18002b42e  mov     r9d, eax; char *
0x18002b431  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\dm\\dmcmnutils\\comp"...
0x18002b438  mov     edx, 2Dh ; '-'; void *
0x18002b43d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b442  nop
0x18002b443  cmp     [rsp+148h+var_70], 8
0x18002b44c  jb      short loc_18002B462
0x18002b44e  mov     rcx, [rsp+148h+var_88]
0x18002b456  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b45d  nop     dword ptr [rax+rax+00h]
0x18002b462  mov     ebx, 7
0x18002b467  mov     [rsp+148h+var_70], rbx
0x18002b46f  mov     [rsp+148h+var_78], r15
0x18002b477  mov     word ptr [rsp+148h+var_88], r15w
0x18002b480  cmp     [rsp+148h+var_50], 8
0x18002b489  jb      short loc_18002B49F
0x18002b48b  mov     rcx, [rsp+148h+var_68]
0x18002b493  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b49a  nop     dword ptr [rax+rax+00h]
0x18002b49f  mov     [rsp+148h+var_50], rbx
0x18002b4a7  mov     [rsp+148h+var_58], r15
0x18002b4af  mov     word ptr [rsp+148h+var_68], r15w
0x18002b4b8  mov     rcx, qword ptr [rsp+148h+var_E8]
0x18002b4bd  test    rcx, rcx
0x18002b4c0  jz      short loc_18002B4CF
0x18002b4c2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b4c9  nop     dword ptr [rax+rax+00h]
0x18002b4ce  nop
0x18002b4cf  lea     rcx, [rsp+148h+var_120]
0x18002b4d4  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x18002b4d9  mov     eax, r14d
0x18002b4dc  jmp     loc_18002B593
0x18002b4e1  lea     rdx, [rsp+148h+var_128]; void *
0x18002b4e6  mov     rcx, rdi; Src
0x18002b4e9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18002b4ee  inc     ebx
0x18002b4f0  jmp     loc_18002B3D4
0x18002b4f5  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002b4f9  xor     r8d, r8d
0x18002b4fc  lea     rdx, [rsp+148h+var_88]
0x18002b504  mov     rcx, rdi
0x18002b507  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18002b50c  nop
0x18002b50d  cmp     [rsp+148h+var_70], 8
0x18002b516  jb      short loc_18002B52C
0x18002b518  mov     rcx, [rsp+148h+var_88]
0x18002b520  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b527  nop     dword ptr [rax+rax+00h]
0x18002b52c  mov     ebx, 7
0x18002b531  mov     [rsp+148h+var_70], rbx
0x18002b539  mov     [rsp+148h+var_78], r15
0x18002b541  mov     word ptr [rsp+148h+var_88], r15w
0x18002b54a  cmp     [rsp+148h+var_50], 8
0x18002b553  jb      short loc_18002B56A
0x18002b555  mov     rcx, [rsp+148h+var_68]
0x18002b55d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b564  nop     dword ptr [rax+rax+00h]
0x18002b569  nop
0x18002b56a  mov     rcx, qword ptr [rsp+148h+var_E8]
0x18002b56f  test    rcx, rcx
0x18002b572  jz      short loc_18002B581
0x18002b574  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b57b  nop     dword ptr [rax+rax+00h]
0x18002b580  nop
0x18002b581  lea     rcx, [rsp+148h+var_120]
0x18002b586  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x18002b58b  xor     eax, eax
0x18002b58d  jmp     short loc_18002B593
0x18002b58f  mov     eax, dword ptr [rsp+148h+var_128]
0x18002b593  mov     rcx, [rsp+148h+var_28]
0x18002b59b  xor     rcx, rsp; StackCookie
0x18002b59e  call    __security_check_cookie
0x18002b5a3  lea     r11, [rsp+148h+var_18]
0x18002b5ab  mov     rbx, [r11+28h]
0x18002b5af  mov     rsi, [r11+38h]
0x18002b5b3  mov     rsp, r11
0x18002b5b6  pop     r15
0x18002b5b8  pop     r14
0x18002b5ba  pop     rdi
0x18002b5bb  retn
```

# OfflineRegistry::CloneNode(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,OfflineRegistry::VisitNode &,OfflineRegistry::Key const &,TokenMap const &,std::unordered_set<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,bool)

- ea: `0x18005c6d4`
- end: `0x18005cf0b`
- name: `?CloneNode@OfflineRegistry@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUVisitNode@1@AEBVKey@1@AEBVTokenMap@@AEAV?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@3@_N@Z`
- size: `2103`
- prototype: ``
- caller_count: `3`
- callee_count: `31`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180037cd0`
- `0x18005cf14`
- `0x18007a1d0`

## callees

- `0x1800053a0`
- `0x180005794`
- `0x180006158`
- `0x180011300`
- `0x180011820`
- `0x180011a64`
- `0x180013100`
- `0x180013188`
- `0x180014a7c`
- `0x18002a3fc`
- `0x18002c9c8`
- `0x1800357ac`
- `0x180041c64`
- `0x18004f2d8`
- `0x18004f554`
- `0x18005a590`
- `0x18005a878`
- `0x18005a8e8`
- `0x18005ab64`
- `0x18005af8c`
- `0x18005b9f8`
- `0x18005bc74`
- `0x18005bd30`
- `0x18005beb0`
- `0x18005c6d4`
- `0x18005d274`
- `0x18005ddfc`
- `0x1800a1084`
- `0x1800a141c`
- `0x1800a17c0`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18005c893`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18005c893`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005cd82`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005cd82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ce08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ce08`

## string_xrefs

- `0x18005c7b0`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x18005ce92`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x18005cea7`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x18005cecf`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x18005cee4`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x18005cef9`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall OfflineRegistry::CloneNode(__int64 a1, __int64 *a2, _QWORD *a3, __int64 a4, __int64 a5, char a6)
{
  unsigned int v9; // eax
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rax
  void *v14; // rcx
  unsigned __int64 v15; // rdx
  __int64 *DetokenizedString; // rax
  __int64 *v17; // rax
  __int64 *v18; // rdi
  _QWORD *v19; // r14
  __int64 v20; // rsi
  unsigned int v21; // eax
  int v22; // esi
  __int64 v23; // r13
  int i; // eax
  __int64 v25; // rcx
  __int128 *p_Src; // rax
  char v27; // di
  __int128 *v28; // rdx
  __int64 v29; // r9
  unsigned __int64 j; // rcx
  __int64 v31; // rbx
  __int64 v32; // rbx
  __int64 v33; // r8
  __int64 v34; // r8
  __int64 v35; // rax
  _QWORD *v36; // rdx
  __int64 v37; // rcx
  unsigned int v38; // eax
  unsigned int v39; // eax
  __int64 v40; // rbx
  __int64 v41; // rax
  struct _RTL_CRITICAL_SECTION *v42; // rdi
  unsigned int v43; // ebx
  _QWORD *v44; // rcx
  unsigned int v45; // [rsp+20h] [rbp-E0h]
  unsigned int v46; // [rsp+20h] [rbp-E0h]
  char *v47; // [rsp+28h] [rbp-D8h]
  unsigned int v48; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v49[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v50; // [rsp+70h] [rbp-90h]
  __int64 v51; // [rsp+78h] [rbp-88h]
  char v52[4]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v53; // [rsp+90h] [rbp-70h]
  __int64 v54; // [rsp+98h] [rbp-68h]
  __int128 Src; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v56; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v57; // [rsp+B8h] [rbp-48h]
  _QWORD v58[3]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v59; // [rsp+D8h] [rbp-28h]
  unsigned int v60; // [rsp+E0h] [rbp-20h]
  __int64 v61; // [rsp+E8h] [rbp-18h]
  __int64 v62; // [rsp+F0h] [rbp-10h]
  __int128 v63; // [rsp+100h] [rbp+0h] BYREF
  __int64 v64; // [rsp+110h] [rbp+10h]
  __int64 v65; // [rsp+118h] [rbp+18h]
  __int128 v66; // [rsp+120h] [rbp+20h] BYREF
  __int64 v67; // [rsp+130h] [rbp+30h]
  __int64 v68; // [rsp+138h] [rbp+38h]
  __int128 v69; // [rsp+140h] [rbp+40h] BYREF
  _QWORD v70[4]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v71; // [rsp+170h] [rbp+70h] BYREF
  int v72; // [rsp+178h] [rbp+78h]
  __int64 v73; // [rsp+188h] [rbp+88h]
  _QWORD *v74; // [rsp+190h] [rbp+90h]
  __int64 v75; // [rsp+198h] [rbp+98h]
  int v76; // [rsp+1A0h] [rbp+A0h]
  __int64 v77; // [rsp+1A8h] [rbp+A8h] BYREF
  int v78; // [rsp+1B0h] [rbp+B0h]
  int v79; // [rsp+1B4h] [rbp+B4h] BYREF
  __int64 v80; // [rsp+1B8h] [rbp+B8h]
  __int128 v81; // [rsp+1C0h] [rbp+C0h]
  __int128 v82; // [rsp+1D0h] [rbp+D0h]
  _OWORD v83[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  _WORD v84[8]; // [rsp+200h] [rbp+100h] BYREF
  __m128i si128; // [rsp+210h] [rbp+110h]
  int v86; // [rsp+220h] [rbp+120h]
  __int64 v87; // [rsp+228h] [rbp+128h]
  __int128 v88; // [rsp+230h] [rbp+130h]
  _BYTE v89[40]; // [rsp+240h] [rbp+140h] BYREF
  __int64 v90; // [rsp+268h] [rbp+168h]
  __int64 v91; // [rsp+270h] [rbp+170h]
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v54 = a4;
  v53 = a1;
  v48 = 0;
  *(_DWORD *)v52 = 0;
  v9 = ORGetValue(*a2, 0, 0, (unsigned int)&v48, 0, (__int64)v52);
  if ( v9 == 2 )
  {
    memset_0(v84, 0, 0x40u);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v84[0] = 0;
    v86 = 0;
    v87 = 0;
    v88 = 0;
  }
  else
  {
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x1A7,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistry.cpp",
      (const char *)v9,
      (unsigned int)"ORGetValue failed to get default value",
      v47);
    std::vector<unsigned char>::vector<unsigned char>(v49, *(unsigned int *)v52);
    v10 = ORGetValue(*a2, 0, 0, (unsigned int)&v48, *(__int64 *)v49, (__int64)v52);
    if ( v10 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1AA,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistry.cpp",
        (const char *)v10,
        v45);
    v11 = v51;
    v51 = 0;
    v12 = v50;
    v50 = 0;
    v13 = *(_QWORD *)v49;
    *(_QWORD *)v49 = 0;
    *(_QWORD *)&v63 = v13;
    *((_QWORD *)&v63 + 1) = v12;
    v64 = v11;
    v66 = 0;
    v67 = 0;
    v68 = 7;
    LOWORD(v66) = 0;
    OfflineRegistry::Value::Value(v84, &v66, v48, &v63);
    v14 = *(void **)v49;
    if ( *(_QWORD *)v49 )
    {
      v15 = v51 - *(_QWORD *)v49;
      if ( (unsigned __int64)(v51 - *(_QWORD *)v49) >= 0x1000 )
      {
        v15 += 39LL;
        v14 = *(void **)(*(_QWORD *)v49 - 8LL);
        if ( (unsigned __int64)(*(_QWORD *)v49 - (_QWORD)v14 - 8LL) > 0x1F )
        {
          _o__invalid_parameter_noinfo_noreturn(v14, v15);
          __debugbreak();
        }
      }
      operator delete(v14, v15);
    }
  }
  if ( (v86 & 0x10000) == 0 && *a3 )
  {
    v83[0] = 0;
    v83[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v83[0]) = 0;
    DetokenizedString = (__int64 *)TokenMap::GetDetokenizedString(a4, a2 + 2, v83);
    v17 = (__int64 *)OfflineRegistry::Key::CloneTo(a2, (__int64)&v69, a3, DetokenizedString, **(_QWORD **)(a4 + 8), a6);
    v18 = v17;
    v19 = a2 + 6;
    if ( a2 + 6 != v17 )
    {
      v20 = *v17;
      if ( *v19 )
        ((void (*)(void))a2[7])();
      *v19 = v20;
      a2[7] = v18[1];
      *v18 = 0;
    }
    std::wstring::operator=(a2 + 8, v18 + 2);
    std::wstring::~wstring(v70);
    if ( (_QWORD)v69 )
      (*((void (**)(void))&v69 + 1))();
    Src = 0;
    v56 = 0;
    v57 = 7;
    LOWORD(Src) = 0;
    OfflineRegistry::Key::begin_values(a2, &v71);
    v77 = *a2;
    v78 = 0;
    v80 = 0;
    v81 = 0;
    v82 = 0;
    v21 = ORQueryInfoKey(v77, 0, 0, 0, 0, 0, (__int64)&v79, 0, 0, 0, 0);
    if ( v21 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xB9,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistry.cpp",
        (const char *)v21,
        v46);
    v22 = v79;
    v78 = v79;
    v23 = v77;
    for ( i = v72; ; i = ++v72 )
    {
      if ( v71 == v23 && i == v22 )
      {
        OfflineRegistry::Key::const_value_iterator::~const_value_iterator((OfflineRegistry::Key::const_value_iterator *)&v77);
        OfflineRegistry::Key::const_value_iterator::~const_value_iterator((OfflineRegistry::Key::const_value_iterator *)&v71);
        std::wstring::~wstring(&Src);
        std::wstring::~wstring(v83);
        goto LABEL_79;
      }
      OfflineRegistry::Key::const_value_iterator::operator*(&v71, v58);
      if ( (v60 & 0x20000) == 0 )
      {
        if ( (_WORD)v60 )
          break;
      }
LABEL_59:
      OfflineRegistry::Value::~Value((OfflineRegistry::Value *)v58);
      v40 = v71;
      if ( *(_WORD *)(v71 + 28) != 29806 || (v41 = *(_QWORD *)(v71 + 16), *(_DWORD *)v41 != -1092567328) )
      {
        v43 = 6;
LABEL_84:
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x85,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistry.cpp",
          (const char *)v43,
          v46);
      }
      if ( v71 != v73 )
      {
        v43 = 87;
        goto LABEL_84;
      }
      v42 = (struct _RTL_CRITICAL_SECTION *)(v41 + 136);
      EnterCriticalSection((LPCRITICAL_SECTION)(v41 + 136));
      if ( *(_WORD *)(v40 + 30) )
      {
        v43 = 1018;
      }
      else if ( *(_QWORD *)(v40 + 168) == v75 )
      {
        if ( (v76 & 1) == 0 )
        {
          if ( !v74 )
          {
            v43 = 87;
            goto LABEL_75;
          }
          v44 = 0;
          if ( *v74 != v40 + 128 )
            v44 = (_QWORD *)*v74;
          v74 = v44;
          if ( v44 )
          {
            v43 = 0;
            goto LABEL_75;
          }
          v76 |= 1u;
        }
        v43 = 259;
      }
      else
      {
        v43 = 1006;
      }
LABEL_75:
      LeaveCriticalSection(v42);
      if ( v43 && v43 != 259 )
        goto LABEL_84;
    }
    if ( (v60 & 0x40000) != 0 )
      v60 &= ~0x40000u;
    std::wstring::reserve(&Src, *(_QWORD *)(v53 + 16) + v58[2] + 2LL);
    std::wstring::operator=(&Src);
    v25 = v56;
    if ( v57 == v56 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(
        &Src,
        92);
    }
    else
    {
      ++v56;
      p_Src = &Src;
      if ( v57 > 7 )
        p_Src = (__int128 *)Src;
      *(_DWORD *)((char *)p_Src + 2 * v25) = 92;
    }
    std::wstring::append(&Src);
    v27 = 0;
    v28 = &Src;
    if ( v57 > 7 )
      v28 = (__int128 *)Src;
    v29 = 0xCBF29CE484222325uLL;
    for ( j = 0; j < 2 * v56; ++j )
      v29 = 0x100000001B3LL * (*((unsigned __int8 *)v28 + j) ^ (unsigned __int64)v29);
    v31 = *(_QWORD *)(std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Find_last<std::wstring>(
                        a5,
                        v52,
                        &Src,
                        v29)
                    + 8);
    if ( v31 )
    {
      if ( v31 != *(_QWORD *)(a5 + 8) )
      {
        if ( (_WORD)v60 == 7 )
          v27 = 1;
        goto LABEL_40;
      }
    }
    else
    {
      v31 = *(_QWORD *)(a5 + 8);
    }
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::insert(
      a5,
      v49,
      &Src);
LABEL_40:
    if ( v31 == *(_QWORD *)(a5 + 8) || v27 )
    {
      v32 = v54;
      TokenMap::DetokenizeString(v54, v58, 0);
      v33 = v60;
      if ( (v60 & 0x400000) != 0 )
      {
        LODWORD(v33) = v60 & 0xFFBFFFFF;
        v60 &= ~0x400000u;
      }
      if ( (unsigned int)(unsigned __int16)v33 - 1 <= 1 || (unsigned __int16)v33 == 7 )
      {
        v63 = 0;
        v64 = 0;
        v65 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v63, v61, (unsigned __int64)(v62 - v61) >> 1);
        LOBYTE(v34) = (_WORD)v60 == 2;
        TokenMap::DetokenizeString(v32, &v63, v34);
        if ( (_WORD)v60 == 7 )
        {
          v66 = 0;
          v67 = 0;
          v68 = 7;
          LOWORD(v66) = 0;
          if ( v27 )
          {
            OfflineRegistry::Key::GetValue(a2 + 6, v89, v58);
            v69 = 0;
            v70[0] = 0;
            v70[1] = 0;
            std::wstring::_Construct<1,unsigned short const *>(&v69, v90, (unsigned __int64)(v91 - v90) >> 1);
            std::wstring::operator=(&v66, &v69);
            std::wstring::~wstring(&v69);
            OfflineRegistry::Value::~Value((OfflineRegistry::Value *)v89);
          }
          v35 = OfflineRegistry::MergeMultistring(&v69);
          std::wstring::operator=(&v63, v35);
          std::wstring::~wstring(&v69);
          std::wstring::~wstring(&v66);
        }
        OfflineRegistry::Value::SetData(v58, &v63);
        std::wstring::~wstring(&v63);
        v33 = v60;
      }
      v36 = v58;
      v37 = a2[6];
      if ( v27 )
      {
        if ( v59 > 7 )
          v36 = (_QWORD *)v58[0];
        v46 = v62 - v61;
        v38 = ORSetValueInternal(v37, v36, v33);
        if ( v38 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x17F,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistry.cpp",
            (const char *)v38,
            v46);
      }
      else
      {
        if ( v59 > 7 )
          v36 = (_QWORD *)v58[0];
        v46 = v62 - v61;
        v39 = ORSetValueInternal(v37, v36, v33);
        if ( v39 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x17A,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistry.cpp",
            (const char *)v39,
            v46);
      }
    }
    goto LABEL_59;
  }
LABEL_79:
  OfflineRegistry::Value::~Value((OfflineRegistry::Value *)v84);
}

```

## disassembly

```asm
0x18005c6d4  push    rbp
0x18005c6d6  push    rbx
0x18005c6d7  push    rsi
0x18005c6d8  push    rdi
0x18005c6d9  push    r12
0x18005c6db  push    r13
0x18005c6dd  push    r14
0x18005c6df  push    r15
0x18005c6e1  lea     rbp, [rsp-198h]
0x18005c6e9  sub     rsp, 298h
0x18005c6f0  mov     rax, cs:__security_cookie
0x18005c6f7  xor     rax, rsp
0x18005c6fa  mov     [rbp+1D0h+var_50], rax
0x18005c701  mov     rsi, r9
0x18005c704  mov     [rbp+1D0h+var_238], r9
0x18005c708  mov     rbx, r8
0x18005c70b  mov     r12, rdx
0x18005c70e  mov     [rbp+1D0h+var_240], rcx
0x18005c712  mov     r15, [rbp+1D0h+arg_20]
0x18005c719  mov     dil, [rbp+1D0h+arg_28]
0x18005c720  xor     r13d, r13d
0x18005c723  mov     [rsp+2D0h+var_270], r13d
0x18005c728  mov     dword ptr [rbp+1D0h+var_250], r13d
0x18005c72c  lea     rax, [rbp+1D0h+var_250]
0x18005c730  mov     [rsp+2D0h+var_2A8], rax; char *
0x18005c735  mov     qword ptr [rsp+2D0h+var_2B0], r13
0x18005c73a  lea     r9, [rsp+2D0h+var_270]
0x18005c73f  xor     r8d, r8d
0x18005c742  xor     edx, edx
0x18005c744  mov     rcx, [r12]
0x18005c748  call    ORGetValue
0x18005c74d  cmp     eax, 2
0x18005c750  jnz     short loc_18005C79A
0x18005c752  xor     edx, edx; Val
0x18005c754  lea     r8d, [r13+40h]; Size
0x18005c758  lea     rcx, [rbp+1D0h+var_D0]; void *
0x18005c75f  call    memset_0
0x18005c764  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18005c76c  movdqa  [rbp+1D0h+var_C0], xmm0
0x18005c774  mov     [rbp+1D0h+var_D0], r13w
0x18005c77c  mov     [rbp+1D0h+var_B0], r13d
0x18005c783  mov     [rbp+1D0h+var_A8], r13
0x18005c78a  xorps   xmm0, xmm0
0x18005c78d  movdqa  [rbp+1D0h+var_A0], xmm0
0x18005c795  jmp     loc_18005C8A6
0x18005c79a  mov     rcx, [rbp+1D8h]; this
0x18005c7a1  lea     rdx, aOrgetvalueFail_0; "ORGetValue failed to get default value"
0x18005c7a8  mov     qword ptr [rsp+2D0h+var_2B0], rdx; unsigned int
0x18005c7ad  mov     r9d, eax; char *
0x18005c7b0  lea     r8, aOnecoreBaseApp_51; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005c7b7  mov     edx, 1A7h; void *
0x18005c7bc  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18005c7c1  mov     edx, dword ptr [rbp+1D0h+var_250]
0x18005c7c4  lea     rcx, [rsp+2D0h+var_268]
0x18005c7c9  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18005c7ce  nop
0x18005c7cf  lea     rax, [rbp+1D0h+var_250]
0x18005c7d3  mov     [rsp+2D0h+var_2A8], rax
0x18005c7d8  mov     rax, qword ptr [rsp+2D0h+var_268]
0x18005c7dd  mov     qword ptr [rsp+2D0h+var_2B0], rax; unsigned int
0x18005c7e2  lea     r9, [rsp+2D0h+var_270]
0x18005c7e7  xor     r8d, r8d
0x18005c7ea  xor     edx, edx
0x18005c7ec  mov     rcx, [r12]
0x18005c7f0  call    ORGetValue
0x18005c7f5  mov     rcx, [rbp+1D8h]; this
0x18005c7fc  test    eax, eax
0x18005c7fe  jnz     loc_18005CEE1
0x18005c804  mov     rdx, [rsp+2D0h+var_258]
0x18005c809  mov     [rsp+2D0h+var_258], r13
0x18005c80e  mov     rcx, [rsp+2D0h+var_260]
0x18005c813  mov     [rsp+2D0h+var_260], r13
0x18005c818  mov     rax, qword ptr [rsp+2D0h+var_268]
0x18005c81d  mov     qword ptr [rsp+2D0h+var_268], r13
0x18005c822  mov     qword ptr [rbp+1D0h+var_1D0], rax
0x18005c826  mov     qword ptr [rbp+1D0h+var_1D0+8], rcx
0x18005c82a  mov     [rbp+1D0h+var_1C0], rdx
0x18005c82e  xorps   xmm0, xmm0
0x18005c831  movups  [rbp+1D0h+var_1B0], xmm0
0x18005c835  mov     [rbp+1D0h+var_1A0], r13
0x18005c839  mov     [rbp+1D0h+var_198], 7
0x18005c841  mov     word ptr [rbp+1D0h+var_1B0], r13w
0x18005c846  lea     r9, [rbp+1D0h+var_1D0]
0x18005c84a  mov     r8d, [rsp+2D0h+var_270]
0x18005c84f  lea     rdx, [rbp+1D0h+var_1B0]
0x18005c853  lea     rcx, [rbp+1D0h+var_D0]
0x18005c85a  call    ??0Value@OfflineRegistry@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$vector@EV?$allocator@E@std@@@3@@Z; OfflineRegistry::Value::Value(std::wstring,ulong,std::vector<uchar>)
0x18005c85f  nop
0x18005c860  mov     rcx, qword ptr [rsp+2D0h+var_268]
0x18005c865  test    rcx, rcx
0x18005c868  jz      short loc_18005C8A6
0x18005c86a  mov     rdx, [rsp+2D0h+var_258]
0x18005c86f  sub     rdx, rcx
0x18005c872  mov     rax, rcx
0x18005c875  cmp     rdx, 1000h
0x18005c87c  jb      short loc_18005C8A0
0x18005c87e  add     rdx, 27h ; '''
0x18005c882  mov     rcx, [rcx-8]
0x18005c886  sub     rax, rcx
0x18005c889  add     rax, 0FFFFFFFFFFFFFFF8h
0x18005c88d  cmp     rax, 1Fh
0x18005c891  jbe     short loc_18005C8A0
0x18005c893  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x18005c89a  nop     dword ptr [rax+rax+00h]
0x18005c89f  int     3; Trap to Debugger
0x18005c8a0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005c8a5  nop
0x18005c8a6  test    [rbp+1D0h+var_B0], 10000h
0x18005c8b0  jnz     loc_18005CE5F
0x18005c8b6  cmp     [rbx], r13
0x18005c8b9  jz      loc_18005CE5F
0x18005c8bf  xorps   xmm0, xmm0
0x18005c8c2  movups  [rbp+1D0h+var_F0], xmm0
0x18005c8c9  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18005c8d1  movdqu  [rbp+1D0h+var_E0], xmm1
0x18005c8d9  mov     word ptr [rbp+1D0h+var_F0], r13w
0x18005c8e1  lea     rdx, [r12+10h]
0x18005c8e6  lea     r8, [rbp+1D0h+var_F0]
0x18005c8ed  mov     rcx, rsi
0x18005c8f0  call    ?GetDetokenizedString@TokenMap@@QEBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@AEAV23@_N@Z; TokenMap::GetDetokenizedString(std::wstring const &,std::wstring &,bool)
0x18005c8f5  mov     rcx, [rsi+8]
0x18005c8f9  mov     rdx, [rcx]
0x18005c8fc  mov     byte ptr [rsp+2D0h+var_2A8], dil
0x18005c901  mov     qword ptr [rsp+2D0h+var_2B0], rdx
0x18005c906  mov     r9, rax
0x18005c909  mov     r8, rbx
0x18005c90c  lea     rdx, [rbp+1D0h+var_190]
0x18005c910  mov     rcx, r12
0x18005c913  call    ?CloneTo@Key@OfflineRegistry@@QEBA?AV12@AEBV12@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAX_N@Z; OfflineRegistry::Key::CloneTo(OfflineRegistry::Key const &,std::wstring const &,void * const,bool)
0x18005c918  mov     rdi, rax
0x18005c91b  lea     r14, [r12+30h]
0x18005c920  cmp     r14, rax
0x18005c923  jz      short loc_18005C947
0x18005c925  mov     rsi, [rax]
0x18005c928  mov     rcx, [r14]
0x18005c92b  test    rcx, rcx
0x18005c92e  jz      short loc_18005C939
0x18005c930  mov     rax, [r14+8]
0x18005c934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c939  mov     [r14], rsi
0x18005c93c  mov     rax, [rdi+8]
0x18005c940  mov     [r14+8], rax
0x18005c944  mov     [rdi], r13
0x18005c947  lea     rdx, [rdi+10h]
0x18005c94b  lea     rcx, [r14+10h]
0x18005c94f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18005c954  lea     rcx, [rbp+1D0h+var_180]; void *
0x18005c958  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005c95d  nop
0x18005c95e  mov     rcx, qword ptr [rbp+1D0h+var_190]
0x18005c962  test    rcx, rcx
0x18005c965  jz      short loc_18005C971
0x18005c967  mov     rax, qword ptr [rbp+1D0h+var_190+8]
0x18005c96b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c970  nop
0x18005c971  xorps   xmm0, xmm0
0x18005c974  movups  [rbp+1D0h+Src], xmm0
0x18005c978  mov     [rbp+1D0h+var_220], r13
0x18005c97c  mov     [rbp+1D0h+var_218], 7
0x18005c984  mov     word ptr [rbp+1D0h+Src], r13w
0x18005c989  lea     rdx, [rbp+1D0h+var_160]
0x18005c98d  mov     rcx, r12
0x18005c990  call    ?begin_values@Key@OfflineRegistry@@QEBA?AVconst_value_iterator@12@XZ; OfflineRegistry::Key::begin_values(void)
0x18005c995  nop
0x18005c996  mov     rcx, [r12]
0x18005c99a  mov     [rbp+1D0h+var_128], rcx
0x18005c9a1  mov     [rbp+1D0h+var_120], r13d
0x18005c9a8  mov     [rbp+1D0h+var_118], r13
0x18005c9af  xorps   xmm0, xmm0
0x18005c9b2  movups  [rbp+1D0h+var_110], xmm0
0x18005c9b9  movups  [rbp+1D0h+var_100], xmm0
0x18005c9c0  mov     [rsp+2D0h+var_280], r13
0x18005c9c5  mov     [rsp+2D0h+var_288], r13
0x18005c9ca  mov     [rsp+2D0h+var_290], r13
0x18005c9cf  mov     [rsp+2D0h+var_298], r13
0x18005c9d4  lea     rax, [rbp+1D0h+var_11C]
0x18005c9db  mov     [rsp+2D0h+var_2A0], rax
0x18005c9e0  mov     [rsp+2D0h+var_2A8], r13
0x18005c9e5  mov     qword ptr [rsp+2D0h+var_2B0], r13; unsigned int
0x18005c9ea  xor     r9d, r9d
0x18005c9ed  xor     r8d, r8d
0x18005c9f0  xor     edx, edx
0x18005c9f2  call    ORQueryInfoKey
0x18005c9f7  mov     rcx, [rbp+1D8h]; this
0x18005c9fe  test    eax, eax
0x18005ca00  jnz     loc_18005CEF6
0x18005ca06  mov     esi, [rbp+1D0h+var_11C]
0x18005ca0c  mov     [rbp+1D0h+var_120], esi
0x18005ca12  mov     r13, [rbp+1D0h+var_128]
0x18005ca19  mov     eax, [rbp+1D0h+var_158]
0x18005ca1c  cmp     [rbp+1D0h+var_160], r13
0x18005ca20  jnz     short loc_18005CA2A
0x18005ca22  cmp     eax, esi
0x18005ca24  jz      loc_18005CE31
0x18005ca2a  lea     rdx, [rbp+1D0h+var_210]
0x18005ca2e  lea     rcx, [rbp+1D0h+var_160]
0x18005ca32  call    ??Dconst_value_iterator@Key@OfflineRegistry@@QEBA?AVValue@2@XZ; OfflineRegistry::Key::const_value_iterator::operator*(void)
0x18005ca37  nop
0x18005ca38  mov     ecx, [rbp+1D0h+var_1F0]
0x18005ca3b  bt      ecx, 11h
0x18005ca3f  jb      loc_18005CD3F
0x18005ca45  test    cx, cx
0x18005ca48  jz      loc_18005CD3F
0x18005ca4e  bt      ecx, 12h
0x18005ca52  jnb     short loc_18005CA5B
0x18005ca54  btr     ecx, 12h
0x18005ca58  mov     [rbp+1D0h+var_1F0], ecx
0x18005ca5b  mov     rbx, [rbp+1D0h+var_240]
0x18005ca5f  mov     rdx, [rbp+1D0h+var_200]
0x18005ca63  add     rdx, 2
0x18005ca67  add     rdx, [rbx+10h]
0x18005ca6b  lea     rcx, [rbp+1D0h+Src]
0x18005ca6f  call    ?reserve@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::reserve(unsigned __int64)
0x18005ca74  mov     rdx, rbx
0x18005ca77  lea     rcx, [rbp+1D0h+Src]; void *
0x18005ca7b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18005ca80  mov     rcx, [rbp+1D0h+var_220]
0x18005ca84  mov     rax, [rbp+1D0h+var_218]
0x18005ca88  sub     rax, rcx
0x18005ca8b  mov     ebx, 1
0x18005ca90  cmp     rax, rbx
0x18005ca93  jb      short loc_18005CAB4
0x18005ca95  lea     rax, [rcx+1]
0x18005ca99  mov     [rbp+1D0h+var_220], rax
0x18005ca9d  lea     rax, [rbp+1D0h+Src]
0x18005caa1  cmp     [rbp+1D0h+var_218], 7
0x18005caa6  cmova   rax, qword ptr [rbp+1D0h+Src]
0x18005caab  mov     dword ptr [rax+rcx*2], 5Ch ; '\'
0x18005cab2  jmp     short loc_18005CACA
0x18005cab4  mov     word ptr [rsp+2D0h+var_2B0], 5Ch ; '\'; __int16
0x18005cabb  mov     r9, rbx
0x18005cabe  mov     rdx, rbx
0x18005cac1  lea     rcx, [rbp+1D0h+Src]; Src
0x18005cac5  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x18005caca  lea     rdx, [rbp+1D0h+var_210]
0x18005cace  cmp     [rbp+1D0h+var_1F8], 7
0x18005cad3  cmova   rdx, [rbp+1D0h+var_210]
0x18005cad8  mov     r8, [rbp+1D0h+var_200]
0x18005cadc  lea     rcx, [rbp+1D0h+Src]; Src
0x18005cae0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::append(ushort const * const,unsigned __int64)
0x18005cae5  xor     r10d, r10d
0x18005cae8  mov     dil, r10b
0x18005caeb  lea     rdx, [rbp+1D0h+Src]
0x18005caef  cmp     [rbp+1D0h+var_218], 7
0x18005caf4  cmova   rdx, qword ptr [rbp+1D0h+Src]
0x18005caf9  mov     r9, 0CBF29CE484222325h
0x18005cb03  mov     rax, [rbp+1D0h+var_220]
0x18005cb07  lea     r8, [rax+rax]
0x18005cb0b  mov     ecx, r10d
0x18005cb0e  test    r8, r8
0x18005cb11  jz      short loc_18005CB30
0x18005cb13  movzx   eax, byte ptr [rcx+rdx]
0x18005cb17  xor     r9, rax
0x18005cb1a  mov     r10, 100000001B3h
0x18005cb24  imul    r9, r10
0x18005cb28  add     rcx, rbx
0x18005cb2b  cmp     rcx, r8
0x18005cb2e  jb      short loc_18005CB13
0x18005cb30  lea     r8, [rbp+1D0h+Src]
0x18005cb34  lea     rdx, [rbp+1D0h+var_250]
0x18005cb38  mov     rcx, r15
0x18005cb3b  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x18005cb40  mov     rbx, [rax+8]
0x18005cb44  xor     ecx, ecx
0x18005cb46  test    rbx, rbx
0x18005cb49  jz      short loc_18005CB5D
0x18005cb4b  cmp     rbx, [r15+8]
0x18005cb4f  jz      short loc_18005CB61
0x18005cb51  cmp     word ptr [rbp+1D0h+var_1F0], 7
0x18005cb56  jnz     short loc_18005CB72
0x18005cb58  mov     dil, 1
0x18005cb5b  jmp     short loc_18005CB72
0x18005cb5d  mov     rbx, [r15+8]
0x18005cb61  lea     r8, [rbp+1D0h+Src]
0x18005cb65  lea     rdx, [rsp+2D0h+var_268]
0x18005cb6a  mov     rcx, r15
0x18005cb6d  call    ?insert@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::insert(std::wstring const &)
0x18005cb72  cmp     rbx, [r15+8]
0x18005cb76  jz      short loc_18005CB81
0x18005cb78  test    dil, dil
0x18005cb7b  jz      loc_18005CD3F
0x18005cb81  xor     r8d, r8d
0x18005cb84  lea     rdx, [rbp+1D0h+var_210]
0x18005cb88  mov     rbx, [rbp+1D0h+var_238]
0x18005cb8c  mov     rcx, rbx
0x18005cb8f  call    ?DetokenizeString@TokenMap@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; TokenMap::DetokenizeString(std::wstring &,bool)
0x18005cb94  mov     r8d, [rbp+1D0h+var_1F0]
0x18005cb98  bt      r8d, 16h
0x18005cb9d  jnb     short loc_18005CBA8
0x18005cb9f  btr     r8d, 16h
0x18005cba4  mov     [rbp+1D0h+var_1F0], r8d
0x18005cba8  movzx   ecx, r8w
0x18005cbac  lea     eax, [rcx-1]
0x18005cbaf  cmp     eax, 1
0x18005cbb2  jbe     short loc_18005CBBD
0x18005cbb4  cmp     ecx, 7
0x18005cbb7  jnz     loc_18005CCD2
0x18005cbbd  mov     r8, [rbp+1D0h+var_1E0]
0x18005cbc1  mov     rdx, [rbp+1D0h+var_1E8]
0x18005cbc5  sub     r8, rdx
  ... truncated ...
```

# win_dox::OpcDigitalSignatureCom<win_scope::scope<win_dox::OpcDigitalSignatureImpl *,win_scope::const_policies<win_scope::shared_policies>>,IOpcDigitalSignature>::GetNamespaces_Safe(wchar_t * * *,wchar_t * * *,uint *)

- ea: `0x1800fb150`
- end: `0x1800fb461`
- name: `?GetNamespaces_Safe@?$OpcDigitalSignatureCom@V?$scope@PEAVOpcDigitalSignatureImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcDigitalSignature@@@win_dox@@AEAAXPEAPEAPEA_W0PEAI@Z`
- size: `785`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18002db70`
- `0x180058f20`
- `0x18009193c`
- `0x1800afe88`
- `0x1800b8608`
- `0x1800cd6fc`
- `0x1800d0a04`
- `0x1800ecc40`
- `0x1800ecd10`
- `0x1800ecdb0`
- `0x1800fb150`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fb2ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fb333`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fb2ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fb333`

## string_xrefs

- `0x1800fb341`: `Unable to allocate memory for XML namespaces`
- `0x1800fb2dc`: `Unable to allocate memory for XML prefixes`
- `0x1800fb1c0`: `OpcDigitalSignatureCom`
- `0x1800fb202`: `OpcDigitalSignatureCom`
- `0x1800fb241`: `OpcDigitalSignatureCom`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall win_dox::OpcDigitalSignatureCom<win_scope::scope<win_dox::OpcDigitalSignatureImpl *,win_scope::const_policies<win_scope::shared_policies>>,IOpcDigitalSignature>::GetNamespaces_Safe(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        _DWORD *a4)
{
  int v6; // eax
  SIZE_T v7; // rdi
  _QWORD *v8; // rax
  _QWORD *v9; // r14
  _QWORD *v10; // rax
  _QWORD *v11; // r12
  _QWORD *v12; // r13
  __int64 v13; // rbx
  int v14; // esi
  __int64 i; // rax
  char v18[8]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v19; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v20; // [rsp+60h] [rbp-A0h]
  __int64 v21; // [rsp+68h] [rbp-98h]
  _BYTE v22[24]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v23[24]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+A0h] [rbp-60h] BYREF

  v21 = -2;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( !a2 )
    win_musl::detail::ThrowParameter(
      a1,
      "(no filename)",
      a3,
      78,
      L"OpcDigitalSignatureCom",
      L"GetNamespaces",
      L"prefixes",
      0);
  *a2 = 0;
  if ( !a3 )
    win_musl::detail::ThrowParameter(
      a1,
      "(no filename)",
      0,
      81,
      L"OpcDigitalSignatureCom",
      L"GetNamespaces",
      L"namespaces",
      0);
  if ( !a4 )
    win_musl::detail::ThrowParameter(
      a1,
      "(no filename)",
      a3,
      82,
      L"OpcDigitalSignatureCom",
      L"GetNamespaces",
      L"count",
      0);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(
    v18,
    *(_QWORD *)(a1 + 16) + 184LL);
  v6 = v20;
  if ( v20 > 0x1FFFFFFF )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x5Bu,
      0x8000FFFF,
      (struct win_musl::TStringEllipseBase *)L"too many strings.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  *a4 = v20;
  v7 = (unsigned int)(8 * v6);
  v8 = CoTaskMemAlloc(v7);
  v9 = v8;
  if ( !v8 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x66u,
      0x8007000E,
      (struct win_musl::TStringEllipseBase *)L"Unable to allocate memory for XML prefixes");
    throw (SplException::THResultException *)pExceptionObject;
  }
  win_dox::ScopedResourceArrayManager<wchar_t *>::ScopedResourceArrayManager<wchar_t *>(v23, v8, (unsigned int)*a4);
  v10 = CoTaskMemAlloc(v7);
  v11 = v10;
  if ( !v10 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x71u,
      0x8007000E,
      (struct win_musl::TStringEllipseBase *)L"Unable to allocate memory for XML namespaces");
    throw (SplException::THResultException *)pExceptionObject;
  }
  win_dox::ScopedResourceArrayManager<wchar_t *>::ScopedResourceArrayManager<wchar_t *>(v22, v10, (unsigned int)*a4);
  v12 = v19;
  v13 = *v19;
  v14 = 0;
  while ( (_QWORD *)v13 != v12 )
  {
    v9[v14] = win_dox::AllocAndCopyString(v13 + 24);
    v11[v14++] = win_dox::AllocAndCopyString(v13 + 64);
    if ( *(_BYTE *)(v13 + 105) )
      invalid_parameter(0, 0, 0, 0, 0);
    if ( *(_BYTE *)(*(_QWORD *)(v13 + 16) + 105LL) )
    {
      for ( i = *(_QWORD *)(v13 + 8); !*(_BYTE *)(i + 105) && v13 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
        v13 = i;
    }
    else
    {
      i = std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Min();
    }
    v13 = i;
  }
  *a2 = v9;
  *a3 = v11;
  v23[16] = 1;
  v22[16] = 1;
  win_dox::ScopedResourceArrayManager<wchar_t *>::~ScopedResourceArrayManager<wchar_t *>(v22);
  win_dox::ScopedResourceArrayManager<wchar_t *>::~ScopedResourceArrayManager<wchar_t *>(v23);
  return std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Tidy(v18);
}

```

## disassembly

```asm
0x1800fb150  push    rbp
0x1800fb152  push    rbx
0x1800fb153  push    rsi
0x1800fb154  push    rdi
0x1800fb155  push    r12
0x1800fb157  push    r13
0x1800fb159  push    r14
0x1800fb15b  push    r15
0x1800fb15d  lea     rbp, [rsp-58h]
0x1800fb162  sub     rsp, 158h
0x1800fb169  mov     [rsp+190h+var_128], 0FFFFFFFFFFFFFFFEh
0x1800fb172  mov     rax, cs:__security_cookie
0x1800fb179  xor     rax, rsp
0x1800fb17c  mov     [rbp+90h+var_50], rax
0x1800fb180  mov     rbx, r9
0x1800fb183  mov     [rsp+190h+var_148], r8
0x1800fb188  mov     r15, rdx
0x1800fb18b  xor     r13d, r13d
0x1800fb18e  test    r8, r8
0x1800fb191  jz      short loc_1800FB196
0x1800fb193  mov     [r8], r13
0x1800fb196  test    rbx, rbx
0x1800fb199  jz      short loc_1800FB19E
0x1800fb19b  mov     [r9], r13d
0x1800fb19e  test    r15, r15
0x1800fb1a1  jnz     short loc_1800FB1DD
0x1800fb1a3  mov     [rsp+190h+var_158], r13d
0x1800fb1a8  lea     rax, aPrefixes; "prefixes"
0x1800fb1af  mov     [rsp+190h+var_160], rax
0x1800fb1b4  lea     rax, aGetnamespaces; "GetNamespaces"
0x1800fb1bb  mov     qword ptr [rsp+190h+var_168], rax
0x1800fb1c0  lea     rax, aOpcdigitalsign_0; "OpcDigitalSignatureCom"
0x1800fb1c7  mov     [rsp+190h+Reserved], rax
0x1800fb1cc  lea     r9d, [r15+4Eh]
0x1800fb1d0  lea     rdx, aNoFilename; "(no filename)"
0x1800fb1d7  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800fb1dd  mov     [rdx], r13
0x1800fb1e0  test    r8, r8
0x1800fb1e3  jnz     short loc_1800FB21F
0x1800fb1e5  mov     [rsp+190h+var_158], r13d
0x1800fb1ea  lea     rax, aNamespaces; "namespaces"
0x1800fb1f1  mov     [rsp+190h+var_160], rax
0x1800fb1f6  lea     rax, aGetnamespaces; "GetNamespaces"
0x1800fb1fd  mov     qword ptr [rsp+190h+var_168], rax
0x1800fb202  lea     rax, aOpcdigitalsign_0; "OpcDigitalSignatureCom"
0x1800fb209  mov     [rsp+190h+Reserved], rax
0x1800fb20e  lea     r9d, [r8+51h]
0x1800fb212  lea     rdx, aNoFilename; "(no filename)"
0x1800fb219  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800fb21f  test    rbx, rbx
0x1800fb222  jnz     short loc_1800FB25E
0x1800fb224  mov     [rsp+190h+var_158], r13d
0x1800fb229  lea     rax, aCount; "count"
0x1800fb230  mov     [rsp+190h+var_160], rax
0x1800fb235  lea     rax, aGetnamespaces; "GetNamespaces"
0x1800fb23c  mov     qword ptr [rsp+190h+var_168], rax
0x1800fb241  lea     rax, aOpcdigitalsign_0; "OpcDigitalSignatureCom"
0x1800fb248  mov     [rsp+190h+Reserved], rax
0x1800fb24d  lea     r9d, [rbx+52h]
0x1800fb251  lea     rdx, aNoFilename; "(no filename)"
0x1800fb258  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800fb25e  mov     rdx, [rcx+10h]
0x1800fb262  add     rdx, 0B8h
0x1800fb269  lea     rcx, [rsp+190h+var_140]
0x1800fb26e  call    ??0?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@AEBV01@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>> const &)
0x1800fb273  nop
0x1800fb274  mov     rax, [rsp+190h+var_130]
0x1800fb279  cmp     rax, 1FFFFFFFh
0x1800fb27f  jbe     short loc_1800FB2C5
0x1800fb281  lea     rax, aTooManyStrings; "too many strings."
0x1800fb288  mov     [rsp+190h+var_160], rax; struct win_musl::TStringEllipseBase *
0x1800fb28d  mov     [rsp+190h+var_168], 8000FFFFh; unsigned int
0x1800fb295  mov     dword ptr [rsp+190h+Reserved], 5Bh ; '['; unsigned int
0x1800fb29d  lea     r9, word_180139126
0x1800fb2a4  lea     r8, aNoFilename; "(no filename)"
0x1800fb2ab  lea     rcx, [rbp+90h+pExceptionObject]; this
0x1800fb2af  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800fb2b4  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800fb2bb  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x1800fb2bf  call    _CxxThrowException_0
0x1800fb2c5  mov     [rbx], eax
0x1800fb2c7  shl     eax, 3
0x1800fb2ca  mov     edi, eax
0x1800fb2cc  mov     ecx, eax; cb
0x1800fb2ce  call    cs:__imp_CoTaskMemAlloc
0x1800fb2d4  mov     r14, rax
0x1800fb2d7  test    rax, rax
0x1800fb2da  jnz     short loc_1800FB320
0x1800fb2dc  lea     rax, aUnableToAlloca; "Unable to allocate memory for XML prefi"...
0x1800fb2e3  mov     [rsp+190h+var_160], rax; struct win_musl::TStringEllipseBase *
0x1800fb2e8  mov     [rsp+190h+var_168], 8007000Eh; unsigned int
0x1800fb2f0  mov     dword ptr [rsp+190h+Reserved], 66h ; 'f'; unsigned int
0x1800fb2f8  lea     r9, word_180139126
0x1800fb2ff  lea     r8, aNoFilename; "(no filename)"
0x1800fb306  lea     rcx, [rbp+90h+pExceptionObject]; this
0x1800fb30a  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800fb30f  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800fb316  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x1800fb31a  call    _CxxThrowException_0
0x1800fb320  mov     r8d, [rbx]
0x1800fb323  mov     rdx, r14
0x1800fb326  lea     rcx, [rbp+90h+var_108]
0x1800fb32a  call    ??0?$ScopedResourceArrayManager@PEA_W@win_dox@@QEAA@PEAPEA_W_K_N@Z; win_dox::ScopedResourceArrayManager<wchar_t *>::ScopedResourceArrayManager<wchar_t *>(wchar_t * *,unsigned __int64,bool)
0x1800fb32f  nop
0x1800fb330  mov     rcx, rdi; cb
0x1800fb333  call    cs:__imp_CoTaskMemAlloc
0x1800fb339  mov     r12, rax
0x1800fb33c  test    rax, rax
0x1800fb33f  jnz     short loc_1800FB385
0x1800fb341  lea     rax, aUnableToAlloca_0; "Unable to allocate memory for XML names"...
0x1800fb348  mov     [rsp+190h+var_160], rax; struct win_musl::TStringEllipseBase *
0x1800fb34d  mov     [rsp+190h+var_168], 8007000Eh; unsigned int
0x1800fb355  mov     dword ptr [rsp+190h+Reserved], 71h ; 'q'; unsigned int
0x1800fb35d  lea     r9, word_180139126
0x1800fb364  lea     r8, aNoFilename; "(no filename)"
0x1800fb36b  lea     rcx, [rbp+90h+pExceptionObject]; this
0x1800fb36f  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800fb374  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800fb37b  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x1800fb37f  call    _CxxThrowException_0
0x1800fb385  mov     r8d, [rbx]
0x1800fb388  mov     rdx, r12
0x1800fb38b  lea     rcx, [rsp+190h+var_120]
0x1800fb390  call    ??0?$ScopedResourceArrayManager@PEA_W@win_dox@@QEAA@PEAPEA_W_K_N@Z; win_dox::ScopedResourceArrayManager<wchar_t *>::ScopedResourceArrayManager<wchar_t *>(wchar_t * *,unsigned __int64,bool)
0x1800fb395  nop
0x1800fb396  mov     r13, [rsp+190h+var_138]
0x1800fb39b  mov     rbx, [r13+0]
0x1800fb39f  xor     edx, edx
0x1800fb3a1  mov     esi, edx
0x1800fb3a3  cmp     rbx, r13
0x1800fb3a6  jz      short loc_1800FB40E
0x1800fb3a8  mov     edi, esi
0x1800fb3aa  lea     rcx, [rbx+18h]
0x1800fb3ae  call    ?AllocAndCopyString@win_dox@@YAPEA_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_dox::AllocAndCopyString(std::wstring const &)
0x1800fb3b3  mov     [r14+rdi*8], rax
0x1800fb3b7  lea     rcx, [rbx+40h]
0x1800fb3bb  call    ?AllocAndCopyString@win_dox@@YAPEA_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_dox::AllocAndCopyString(std::wstring const &)
0x1800fb3c0  mov     [r12+rdi*8], rax
0x1800fb3c4  inc     esi
0x1800fb3c6  xor     edx, edx; FunctionName
0x1800fb3c8  cmp     [rbx+69h], dl
0x1800fb3cb  jz      short loc_1800FB3E1
0x1800fb3cd  mov     [rsp+190h+Reserved], rdx; Reserved
0x1800fb3d2  xor     r9d, r9d; LineNo
0x1800fb3d5  xor     r8d, r8d; FileName
0x1800fb3d8  xor     ecx, ecx; Expression
0x1800fb3da  call    _invalid_parameter
0x1800fb3df  jmp     short loc_1800FB3A3
0x1800fb3e1  mov     rcx, [rbx+10h]
0x1800fb3e5  cmp     [rcx+69h], dl
0x1800fb3e8  jnz     short loc_1800FB3F1
0x1800fb3ea  call    ?_Min@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@@std@@@2@$0A@@std@@@std@@KAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@@std@@@2@$0A@@std@@@2@PEAU342@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Min(std::_Tree_nod<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Node *)
0x1800fb3ef  jmp     short loc_1800FB409
0x1800fb3f1  mov     rax, [rbx+8]
0x1800fb3f5  jmp     short loc_1800FB404
0x1800fb3f7  cmp     rbx, [rax+10h]
0x1800fb3fb  jnz     short loc_1800FB409
0x1800fb3fd  mov     rbx, rax
0x1800fb400  mov     rax, [rax+8]
0x1800fb404  cmp     [rax+69h], dl
0x1800fb407  jz      short loc_1800FB3F7
0x1800fb409  mov     rbx, rax
0x1800fb40c  jmp     short loc_1800FB3A3
0x1800fb40e  mov     [r15], r14
0x1800fb411  mov     rsi, [rsp+190h+var_148]
0x1800fb416  mov     [rsi], r12
0x1800fb419  mov     [rbp+90h+var_F8], 1
0x1800fb41d  mov     [rbp+90h+var_110], 1
0x1800fb421  lea     rcx, [rsp+190h+var_120]
0x1800fb426  call    ??1?$ScopedResourceArrayManager@PEA_W@win_dox@@QEAA@XZ; win_dox::ScopedResourceArrayManager<wchar_t *>::~ScopedResourceArrayManager<wchar_t *>(void)
0x1800fb42b  nop
0x1800fb42c  lea     rcx, [rbp+90h+var_108]
0x1800fb430  call    ??1?$ScopedResourceArrayManager@PEA_W@win_dox@@QEAA@XZ; win_dox::ScopedResourceArrayManager<wchar_t *>::~ScopedResourceArrayManager<wchar_t *>(void)
0x1800fb435  nop
0x1800fb436  lea     rcx, [rsp+190h+var_140]
0x1800fb43b  call    ?_Tidy@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Tidy(void)
0x1800fb440  nop
0x1800fb441  mov     rcx, [rbp+90h+var_50]
0x1800fb445  xor     rcx, rsp; StackCookie
0x1800fb448  call    __security_check_cookie
0x1800fb44d  add     rsp, 158h
0x1800fb454  pop     r15
0x1800fb456  pop     r14
0x1800fb458  pop     r13
0x1800fb45a  pop     r12
0x1800fb45c  pop     rdi
0x1800fb45d  pop     rsi
0x1800fb45e  pop     rbx
0x1800fb45f  pop     rbp
0x1800fb460  retn
```

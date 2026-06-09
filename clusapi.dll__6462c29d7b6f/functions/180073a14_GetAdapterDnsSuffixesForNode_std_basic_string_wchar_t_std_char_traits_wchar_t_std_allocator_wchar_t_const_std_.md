# GetAdapterDnsSuffixesForNode(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::set<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,bool (*)(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &),std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> &)

- ea: `0x180073a14`
- end: `0x180073d71`
- name: `?GetAdapterDnsSuffixesForNode@@YAKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@P6A_NAEBV12@0@ZV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@Z`
- size: `861`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config`

## callers

- `0x1800738b0`

## callees

- `0x180002f50`
- `0x180003c44`
- `0x18001cc2c`
- `0x18001cec4`
- `0x180027f00`
- `0x180028f30`
- `0x180029578`
- `0x18003180c`
- `0x18006f910`
- `0x180070514`
- `0x180070600`
- `0x180070c2c`
- `0x180071538`
- `0x180073a14`
- `0x180076d98`
- `0x1800aab00`
- `0x1800ab08c`
- `0x1800ab12c`
- `0x1800ab660`
- `0x1800ab9e4`
- `0x1800aba10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073d12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073d42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073d12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073d42`

## string_xrefs

- `0x180073a5c`: `Attempting to connect to WMI on machine '%ws'`
- `0x180073d4a`: `Could not create MiApplication`
- `0x180073d1b`: `Could not create MiSession`
- `0x180073b11`: `SELECT * FROM Win32_NetworkAdapterConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall GetAdapterDnsSuffixesForNode(__int64 a1, __int64 a2)
{
  unsigned int v4; // edi
  __int64 v5; // rax
  __int64 v6; // rsi
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rcx
  __m128i si128; // xmm6
  __int64 v11; // rax
  int v12; // edi
  bool v13; // bl
  unsigned int v14; // edi
  __int64 v15; // rbx
  __int64 v16; // rcx
  DWORD v18; // eax
  DWORD LastError; // eax
  __int64 v20; // [rsp+40h] [rbp-C8h] BYREF
  std::_Ref_count_base *v21; // [rsp+48h] [rbp-C0h]
  _BYTE v22[16]; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v23[16]; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+78h] [rbp-90h]
  __int64 v25; // [rsp+80h] [rbp-88h]
  __int64 v26; // [rsp+88h] [rbp-80h]
  char v27; // [rsp+90h] [rbp-78h]
  __int64 v28; // [rsp+98h] [rbp-70h] BYREF
  std::_Ref_count_base *v29; // [rsp+A0h] [rbp-68h]
  _BYTE v30[80]; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v31; // [rsp+F8h] [rbp-10h] BYREF
  __m128i v32; // [rsp+108h] [rbp+0h] BYREF
  __int64 v33; // [rsp+118h] [rbp+10h]
  __int64 v34; // [rsp+120h] [rbp+18h]
  __int64 v35; // [rsp+128h] [rbp+20h]
  char v36; // [rsp+130h] [rbp+28h]
  _BYTE v37[32]; // [rsp+138h] [rbp+30h] BYREF
  _BYTE v38[32]; // [rsp+158h] [rbp+50h] BYREF
  void **v39; // [rsp+178h] [rbp+70h] BYREF
  _BYTE v40[76]; // [rsp+180h] [rbp+78h] BYREF
  int v41; // [rsp+1CCh] [rbp+C4h]
  _BYTE pExceptionObject[272]; // [rsp+1D8h] [rbp+D0h] BYREF

  v4 = 0;
  v5 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1);
  TraceMsg(
    4u,
    0,
    (__int64)L"GetAdapterDnsSuffixesForNode",
    1926,
    L"Attempting to connect to WMI on machine '%ws'",
    v5,
    0);
  std::wstring::wstring(&v31, L"GetAdapterDnsSuffixesForNode");
  mi::MiApplication::Create(&v28, &v31);
  std::wstring::_Tidy_deallocate(&v31);
  v6 = v28;
  if ( !v28 )
  {
    LastError = GetLastError();
    ClusRtl::ExceptionMsg::ExceptionMsg(
      (ClusRtl::ExceptionMsg *)pExceptionObject,
      LastError,
      L"Could not create MiApplication");
    throw (ClusRtl::ExceptionMsg *)pExceptionObject;
  }
  std::wstring::wstring(v37, L"root\\cimv2");
  mi::MiApplication::CreateSession(v6, &v20, v37, a1);
  std::wstring::_Tidy_deallocate(v37);
  if ( !v20 )
  {
    v18 = GetLastError();
    ClusRtl::ExceptionMsg::ExceptionMsg((ClusRtl::ExceptionMsg *)pExceptionObject, v18, L"Could not create MiSession");
    throw (ClusRtl::ExceptionMsg *)pExceptionObject;
  }
  TraceMsg(4u, 0, (__int64)L"GetAdapterDnsSuffixesForNode", 1940, L"Querying Adapters via WMI");
  std::wstring::wstring(v38, L"SELECT * FROM Win32_NetworkAdapterConfiguration");
  v7 = v20;
  v8 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v38);
  std::wstring::wstring(&v31, v8);
  mi::MiSession::Query<0>(v7, v30, &v31);
  std::wstring::_Tidy_deallocate(&v31);
  mi::MiInstanceOperation::begin(v30, v22);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    v11 = mi::MiInstanceOperation::end(v9, &v31);
    v12 = v4 | 1;
    v13 = v24 != *(_QWORD *)(v11 + 32) && !*(_DWORD *)(v25 + 56);
    v14 = v12 & 0xFFFFFFFE;
    mi::object_iterator<mi::MiInstance,mi::MiInstance>::~object_iterator<mi::MiInstance,mi::MiInstance>(&v31);
    if ( !v13 )
      break;
    v15 = v25;
    std::wstring::wstring(&v31, L"DNSDomain");
    mi::MiInstance::operator[](v15, &v39, &v31);
    std::wstring::_Tidy_deallocate(&v31);
    if ( (v41 & 0x20000000) == 0 )
    {
      v31 = 0;
      v32 = si128;
      LOWORD(v31) = 0;
      mi::MiValue::GetValue<std::wstring>(&v39, &v31);
      if ( v32.m128i_i64[0] )
        std::_Tree<std::_Tset_traits<std::wstring,bool (*)(std::wstring const &,std::wstring const &),std::allocator<std::wstring>,0>>::insert<0,0>(
          a2,
          v37,
          &v31);
      std::wstring::_Tidy_deallocate(&v31);
    }
    v39 = &mi::MiValue::`vftable';
    std::wstring::_Tidy_deallocate(v40);
    std::shared_ptr<cxl::ParallelConnector<void *,std::unique_ptr<AutoImpersonation>,ClusterHandleConnector>::LibrarySafety>::shared_ptr<cxl::ParallelConnector<void *,std::unique_ptr<AutoImpersonation>,ClusterHandleConnector>::LibrarySafety>(
      &v31,
      v22);
    std::shared_ptr<cxl::ParallelConnector<void *,std::unique_ptr<AutoImpersonation>,ClusterHandleConnector>::LibrarySafety>::shared_ptr<cxl::ParallelConnector<void *,std::unique_ptr<AutoImpersonation>,ClusterHandleConnector>::LibrarySafety>(
      &v32,
      v23);
    v33 = v24;
    v16 = v26;
    if ( v26 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v26 + 8));
      v16 = v26;
    }
    v34 = v25;
    v35 = v16;
    v36 = v27;
    mi::object_iterator<mi::MiInstance,mi::MiInstance>::get_next(v22);
    v4 = v14 & 0xFFFFFFFD;
    mi::object_iterator<mi::MiInstance,mi::MiInstance>::~object_iterator<mi::MiInstance,mi::MiInstance>(&v31);
  }
  mi::object_iterator<mi::MiInstance,mi::MiInstance>::~object_iterator<mi::MiInstance,mi::MiInstance>(v22);
  mi::MiInstanceOperation::~MiInstanceOperation((mi::MiInstanceOperation *)v30);
  std::wstring::_Tidy_deallocate(v38);
  if ( v21 )
    std::_Ref_count_base::_Decref(v21);
  if ( v29 )
    std::_Ref_count_base::_Decref(v29);
  return 0;
}

```

## disassembly

```asm
0x180073a14  mov     rax, rsp
0x180073a17  mov     [rax+18h], rbx
0x180073a1b  mov     [rax+20h], rsi
0x180073a1f  push    rbp
0x180073a20  push    rdi
0x180073a21  push    r14
0x180073a23  lea     rbp, [rax-218h]
0x180073a2a  sub     rsp, 300h
0x180073a31  movaps  xmmword ptr [rax-28h], xmm6
0x180073a35  mov     rax, cs:__security_cookie
0x180073a3c  xor     rax, rsp
0x180073a3f  mov     [rbp+210h+var_30], rax
0x180073a46  mov     r14, rdx
0x180073a49  mov     rbx, rcx
0x180073a4c  xor     edi, edi
0x180073a4e  mov     dword ptr [rsp+310h+var_2E0], edi
0x180073a52  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180073a57  mov     qword ptr [rsp+310h+var_2E8], rax
0x180073a5c  lea     rax, aAttemptingToCo; "Attempting to connect to WMI on machine"...
0x180073a63  mov     [rsp+310h+var_2F0], rax
0x180073a68  mov     r9d, 786h
0x180073a6e  lea     r8, aGetadapterdnss; "GetAdapterDnsSuffixesForNode"
0x180073a75  xor     edx, edx
0x180073a77  lea     ecx, [rdi+4]
0x180073a7a  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180073a7f  lea     rdx, aGetadapterdnss; "GetAdapterDnsSuffixesForNode"
0x180073a86  lea     rcx, [rbp+210h+var_220]
0x180073a8a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180073a8f  nop
0x180073a90  lea     rdx, [rbp+210h+var_220]
0x180073a94  lea     rcx, [rbp+210h+var_280]
0x180073a98  call    ?Create@MiApplication@mi@@SA?AV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::Create(std::wstring const &)
0x180073a9d  nop
0x180073a9e  lea     rcx, [rbp+210h+var_220]
0x180073aa2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180073aa7  mov     rsi, [rbp+210h+var_280]
0x180073aab  test    rsi, rsi
0x180073aae  jz      loc_180073D42
0x180073ab4  lea     rdx, aRootCimv2; "root\\cimv2"
0x180073abb  lea     rcx, [rbp+210h+var_1E0]
0x180073abf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180073ac4  nop
0x180073ac5  mov     r9, rbx
0x180073ac8  lea     r8, [rbp+210h+var_1E0]
0x180073acc  lea     rdx, [rsp+310h+var_2D8]
0x180073ad1  mov     rcx, rsi
0x180073ad4  call    ?CreateSession@MiApplication@mi@@QEAA?AV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@0@Z; mi::MiApplication::CreateSession(std::wstring const &,std::wstring const &)
0x180073ad9  nop
0x180073ada  lea     rcx, [rbp+210h+var_1E0]
0x180073ade  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180073ae3  cmp     [rsp+310h+var_2D8], rdi
0x180073ae8  jz      loc_180073D12
0x180073aee  lea     rax, aQueryingAdapte; "Querying Adapters via WMI"
0x180073af5  mov     [rsp+310h+var_2F0], rax
0x180073afa  mov     r9d, 794h
0x180073b00  lea     r8, aGetadapterdnss; "GetAdapterDnsSuffixesForNode"
0x180073b07  xor     edx, edx
0x180073b09  lea     ecx, [rdi+4]
0x180073b0c  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180073b11  lea     rdx, aSelectFromWin3; "SELECT * FROM Win32_NetworkAdapterConfi"...
0x180073b18  lea     rcx, [rbp+210h+var_1C0]
0x180073b1c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180073b21  nop
0x180073b22  mov     rbx, [rsp+310h+var_2D8]
0x180073b27  lea     rcx, [rbp+210h+var_1C0]
0x180073b2b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180073b30  mov     rdx, rax
0x180073b33  lea     rcx, [rbp+210h+var_220]
0x180073b37  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180073b3c  nop
0x180073b3d  lea     r8, [rbp+210h+var_220]
0x180073b41  lea     rdx, [rbp+210h+var_270]
0x180073b45  mov     rcx, rbx
0x180073b48  call    ??$Query@$0A@@MiSession@mi@@QEBA?AVMiInstanceOperation@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; mi::MiSession::Query<0>(std::wstring const &)
0x180073b4d  nop
0x180073b4e  lea     rcx, [rbp+210h+var_220]
0x180073b52  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180073b57  lea     rdx, [rsp+310h+var_2C0]
0x180073b5c  lea     rcx, [rbp+210h+var_270]
0x180073b60  call    ?begin@MiInstanceOperation@mi@@QEBA?AV?$object_iterator@VMiInstance@mi@@V12@@2@XZ; mi::MiInstanceOperation::begin(void)
0x180073b65  nop
0x180073b66  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180073b6e  lea     rdx, [rbp+210h+var_220]
0x180073b72  call    ?end@MiInstanceOperation@mi@@QEBA?AV?$object_iterator@VMiInstance@mi@@V12@@2@XZ; mi::MiInstanceOperation::end(void)
0x180073b77  or      edi, 1
0x180073b7a  mov     rax, [rax+20h]
0x180073b7e  cmp     [rsp+310h+var_2A0], rax
0x180073b83  jz      short loc_180073B94
0x180073b85  mov     rax, [rsp+310h+var_298]
0x180073b8a  cmp     dword ptr [rax+38h], 0
0x180073b8e  jnz     short loc_180073B94
0x180073b90  mov     bl, 1
0x180073b92  jmp     short loc_180073B96
0x180073b94  xor     bl, bl
0x180073b96  and     edi, 0FFFFFFFEh
0x180073b99  lea     rcx, [rbp+210h+var_220]
0x180073b9d  call    ??1?$object_iterator@VMiInstance@mi@@V12@@mi@@QEAA@XZ; mi::object_iterator<mi::MiInstance,mi::MiInstance>::~object_iterator<mi::MiInstance,mi::MiInstance>(void)
0x180073ba2  test    bl, bl
0x180073ba4  jz      loc_180073CA7
0x180073baa  mov     rbx, [rsp+310h+var_298]
0x180073baf  lea     rdx, aDnsdomain_0; "DNSDomain"
0x180073bb6  lea     rcx, [rbp+210h+var_220]
0x180073bba  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180073bbf  nop
0x180073bc0  lea     r8, [rbp+210h+var_220]
0x180073bc4  lea     rdx, [rbp+210h+var_1A0]
0x180073bc8  mov     rcx, rbx
0x180073bcb  call    ??AMiInstance@mi@@QEBA?AVMiProperty@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; mi::MiInstance::operator[](std::wstring const &)
0x180073bd0  nop
0x180073bd1  lea     rcx, [rbp+210h+var_220]
0x180073bd5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180073bda  test    [rbp+210h+var_14C], 20000000h
0x180073be4  jnz     short loc_180073C27
0x180073be6  xorps   xmm0, xmm0
0x180073be9  movups  [rbp+210h+var_220], xmm0
0x180073bed  movdqu  [rbp+210h+var_210], xmm6
0x180073bf2  xor     eax, eax
0x180073bf4  mov     word ptr [rbp+210h+var_220], ax
0x180073bf8  lea     rdx, [rbp+210h+var_220]
0x180073bfc  lea     rcx, [rbp+210h+var_1A0]
0x180073c00  call    ??$GetValue@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiValue@mi@@QEBAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; mi::MiValue::GetValue<std::wstring>(std::wstring &)
0x180073c05  cmp     qword ptr [rbp+210h+var_210], 0
0x180073c0a  jz      short loc_180073C1D
0x180073c0c  lea     r8, [rbp+210h+var_220]
0x180073c10  lea     rdx, [rbp+210h+var_1E0]
0x180073c14  mov     rcx, r14
0x180073c17  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@P6A_NAEBV12@0@ZV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,bool (*)(std::wstring const &,std::wstring const &),std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring const &)
0x180073c1c  nop
0x180073c1d  lea     rcx, [rbp+210h+var_220]
0x180073c21  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180073c26  nop
0x180073c27  lea     rax, ??_7MiValue@mi@@6B@; const mi::MiValue::`vftable'
0x180073c2e  mov     [rbp+210h+var_1A0], rax
0x180073c32  lea     rcx, [rbp+210h+var_198]
0x180073c36  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180073c3b  nop
0x180073c3c  lea     rdx, [rsp+310h+var_2C0]
0x180073c41  lea     rcx, [rbp+210h+var_220]
0x180073c45  call    ??0?$shared_ptr@VLibrarySafety@?$ParallelConnector@PEAXV?$unique_ptr@VAutoImpersonation@@U?$default_delete@VAutoImpersonation@@@std@@@std@@UClusterHandleConnector@@@cxl@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<cxl::ParallelConnector<void *,std::unique_ptr<AutoImpersonation>,ClusterHandleConnector>::LibrarySafety>::shared_ptr<cxl::ParallelConnector<void *,std::unique_ptr<AutoImpersonation>,ClusterHandleConnector>::LibrarySafety>(std::shared_ptr<cxl::ParallelConnector<void *,std::unique_ptr<AutoImpersonation>,ClusterHandleConnector>::LibrarySafety> const &)
0x180073c4a  lea     rdx, [rsp+310h+var_2B0]
0x180073c4f  lea     rcx, [rbp+210h+var_210]
0x180073c53  call    ??0?$shared_ptr@VLibrarySafety@?$ParallelConnector@PEAXV?$unique_ptr@VAutoImpersonation@@U?$default_delete@VAutoImpersonation@@@std@@@std@@UClusterHandleConnector@@@cxl@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<cxl::ParallelConnector<void *,std::unique_ptr<AutoImpersonation>,ClusterHandleConnector>::LibrarySafety>::shared_ptr<cxl::ParallelConnector<void *,std::unique_ptr<AutoImpersonation>,ClusterHandleConnector>::LibrarySafety>(std::shared_ptr<cxl::ParallelConnector<void *,std::unique_ptr<AutoImpersonation>,ClusterHandleConnector>::LibrarySafety> const &)
0x180073c58  mov     rcx, [rsp+310h+var_2A0]
0x180073c5d  mov     [rbp+210h+var_200], rcx
0x180073c61  mov     rcx, [rbp+210h+var_290]
0x180073c65  test    rcx, rcx
0x180073c68  jz      short loc_180073C72
0x180073c6a  lock inc dword ptr [rcx+8]
0x180073c6e  mov     rcx, [rbp+210h+var_290]
0x180073c72  mov     rax, [rsp+310h+var_298]
0x180073c77  mov     [rbp+210h+var_1F8], rax
0x180073c7b  mov     [rbp+210h+var_1F0], rcx
0x180073c7f  mov     al, [rbp+210h+var_288]
0x180073c82  mov     [rbp+210h+var_1E8], al
0x180073c85  or      edi, 2
0x180073c88  mov     dword ptr [rsp+310h+var_2E0], edi
0x180073c8c  lea     rcx, [rsp+310h+var_2C0]
0x180073c91  call    ?get_next@?$object_iterator@VMiInstance@mi@@V12@@mi@@AEAAXXZ; mi::object_iterator<mi::MiInstance,mi::MiInstance>::get_next(void)
0x180073c96  and     edi, 0FFFFFFFDh
0x180073c99  lea     rcx, [rbp+210h+var_220]
0x180073c9d  call    ??1?$object_iterator@VMiInstance@mi@@V12@@mi@@QEAA@XZ; mi::object_iterator<mi::MiInstance,mi::MiInstance>::~object_iterator<mi::MiInstance,mi::MiInstance>(void)
0x180073ca2  jmp     loc_180073B6E
0x180073ca7  lea     rcx, [rsp+310h+var_2C0]
0x180073cac  call    ??1?$object_iterator@VMiInstance@mi@@V12@@mi@@QEAA@XZ; mi::object_iterator<mi::MiInstance,mi::MiInstance>::~object_iterator<mi::MiInstance,mi::MiInstance>(void)
0x180073cb1  nop
0x180073cb2  lea     rcx, [rbp+210h+var_270]; this
0x180073cb6  call    ??1MiInstanceOperation@mi@@UEAA@XZ; mi::MiInstanceOperation::~MiInstanceOperation(void)
0x180073cbb  nop
0x180073cbc  lea     rcx, [rbp+210h+var_1C0]
0x180073cc0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180073cc5  nop
0x180073cc6  mov     rcx, [rsp+310h+var_2D0]; this
0x180073ccb  test    rcx, rcx
0x180073cce  jz      short loc_180073CD6
0x180073cd0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180073cd5  nop
0x180073cd6  mov     rcx, [rbp+210h+var_278]; this
0x180073cda  test    rcx, rcx
0x180073cdd  jz      short loc_180073CE4
0x180073cdf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180073ce4  xor     eax, eax
0x180073ce6  mov     rcx, [rbp+210h+var_30]
0x180073ced  xor     rcx, rsp; StackCookie
0x180073cf0  call    __security_check_cookie
0x180073cf5  lea     r11, [rsp+310h+var_10]
0x180073cfd  mov     rbx, [r11+30h]
0x180073d01  mov     rsi, [r11+38h]
0x180073d05  movaps  xmm6, xmmword ptr [r11-10h]
0x180073d0a  mov     rsp, r11
0x180073d0d  pop     r14
0x180073d0f  pop     rdi
0x180073d10  pop     rbp
0x180073d11  retn
0x180073d12  call    cs:__imp_GetLastError
0x180073d18  nop
0x180073d19  mov     edx, eax; int
0x180073d1b  lea     r8, aCouldNotCreate_0; "Could not create MiSession"
0x180073d22  lea     rcx, [rbp+210h+pExceptionObject]; this
0x180073d29  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x180073d2e  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x180073d35  lea     rcx, [rbp+210h+pExceptionObject]; pExceptionObject
0x180073d3c  call    _CxxThrowException_0
0x180073d42  call    cs:__imp_GetLastError
0x180073d48  mov     edx, eax; int
0x180073d4a  lea     r8, aCouldNotCreate; "Could not create MiApplication"
0x180073d51  lea     rcx, [rbp+210h+pExceptionObject]; this
0x180073d58  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x180073d5d  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x180073d64  lea     rcx, [rbp+210h+pExceptionObject]; pExceptionObject
0x180073d6b  call    _CxxThrowException_0
```

# win_dox::ParseObjectBlob(_CRYPT_XML_BLOB const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70> const &,__MIDL___MIDL_itf_msopc_0001_0076_0005 *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70> *,std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70> const,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70>>>> *)

- ea: `0x180108ed4`
- end: `0x1801091c2`
- name: `?ParseObjectBlob@win_dox@@YAXPEBU_CRYPT_XML_BLOB@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@PEAW4__MIDL___MIDL_itf_msopc_0001_0076_0005@@PEAV34@PEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@@std@@@2@@4@@Z`
- size: `750`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting`

## callers

- `0x18009ff64`

## callees

- `0x18000531c`
- `0x18000f9a0`
- `0x180015660`
- `0x1800240dc`
- `0x18002db70`
- `0x18003c8e8`
- `0x18009193c`
- `0x18009c7bc`
- `0x1800b893c`
- `0x1800bb190`
- `0x1800bf5f8`
- `0x1800cd6fc`
- `0x1800d0848`
- `0x1800d0a04`
- `0x1800ed204`
- `0x1800ed654`
- `0x180107124`
- `0x180108228`
- `0x180108ed4`
- `0x180109f90`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `SHLWAPI!__imp_SHCreateMemStream` at `0x180109013`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x180109013`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall win_dox::ParseObjectBlob(__int64 a1, __int64 a2, _DWORD *a3, __int64 a4, __int64 a5)
{
  const char *v9; // rdx
  unsigned int v10; // r8d
  void *v11; // rax
  __int64 v12; // rsi
  win_scope::counted_strong_weak_base *v13; // r14
  IStream *v14; // rax
  IStream *v15; // rdi
  signed int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // r9
  __int64 *v19; // rsi
  __int64 i; // rbx
  __int64 j; // rax
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v24; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+60h] [rbp-A0h]
  LPVOID ppv; // [rsp+70h] [rbp-90h] BYREF
  __int128 v27; // [rsp+78h] [rbp-88h] BYREF
  char v28; // [rsp+88h] [rbp-78h]
  __int64 v29; // [rsp+90h] [rbp-70h]
  char v30[8]; // [rsp+98h] [rbp-68h] BYREF
  __int16 v31; // [rsp+A0h] [rbp-60h]
  __int64 v32; // [rsp+B0h] [rbp-50h]
  __int64 v33; // [rsp+B8h] [rbp-48h]
  win_scope::counted_strong_weak_base *v34[2]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+D0h] [rbp-30h] BYREF

  v29 = -2;
  *a3 = 0;
  std::wstring::clear(a4);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::clear(a5);
  v33 = 7;
  v32 = 0;
  v31 = 0;
  *(_OWORD *)v34 = 0;
  *((_QWORD *)&v27 + 1) = v30;
  v28 = 1;
  *(_QWORD *)&v27 = win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::ObjectBlob>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::ObjectBlob>>();
  v11 = operator new(0x140u, v9, v10);
  v23 = (__int64)v11;
  if ( v11 )
    v12 = win_musl::consumption::SignaturePropertiesContentHandler::SignaturePropertiesContentHandler(v11, &v27);
  else
    v12 = 0;
  v27 = 0;
  v23 = v12;
  if ( v12 )
  {
    v13 = (win_scope::counted_strong_weak_base *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v13 )
    {
      win_scope::close_delete::close<win_musl::CallingThread>(&v23);
      win_scope::report_policy_throw::report_init_failure();
    }
    *((_QWORD *)v13 + 1) = 0;
    *(_QWORD *)v13 = &win_scope::counted_strong_weak<win_musl::consumption::ZipConsumptionPart *,win_scope::const_policies<win_scope::resource_policies>>::`vftable';
    *((_QWORD *)v13 + 2) = v12;
    *(_QWORD *)&v27 = v13;
    win_scope::counted_strong_weak_base::AddRef(v13);
    *((_QWORD *)&v27 + 1) = v12;
  }
  else
  {
    v12 = *((_QWORD *)&v27 + 1);
    v13 = (win_scope::counted_strong_weak_base *)v27;
  }
  win_musl::consumption::CreateSaxParser<win_scope::scope<win_musl::consumption::SignaturePropertiesContentHandler *,win_scope::const_policies<win_scope::shared_policies>>>(&ppv);
  v14 = SHCreateMemStream(*(const BYTE **)(a1 + 8), *(_DWORD *)(a1 + 4));
  v15 = 0;
  if ( v14 )
    v15 = v14;
  v23 = (__int64)v15;
  *(_QWORD *)&v24 = 13;
  *((_QWORD *)&v24 + 1) = v15;
  v25 = 0;
  v16 = (*(__int64 (__fastcall **)(LPVOID, __int128 *))(*(_QWORD *)ppv + 152LL))(ppv, &v24);
  if ( v16 < 0 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x2C7u,
      v16,
      (struct win_musl::TStringEllipseBase *)L"Parsing <SignatureProperties> failed");
    throw (SplException::THResultException *)pExceptionObject;
  }
  win_dox::ValidateSignatureProperties(v34, a2);
  v24 = 0;
  if ( v34[0] )
  {
    win_scope::counted_strong_weak_base::AddRef(v34[0]);
    *(_QWORD *)&v24 = v17;
    *((_QWORD *)&v24 + 1) = v18;
  }
  win_dox::GetSignatureTime(&v24, a3, a4);
  v19 = *(__int64 **)(v12 + 296);
  for ( i = *v19; (__int64 *)i != v19; i = j )
  {
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::insert(
      a5,
      &v24,
      i + 24);
    if ( *(_BYTE *)(i + 105) )
      invalid_parameter(0, 0, 0, 0, 0);
    if ( *(_BYTE *)(*(_QWORD *)(i + 16) + 105LL) )
    {
      for ( j = *(_QWORD *)(i + 8); !*(_BYTE *)(j + 105) && i == *(_QWORD *)(j + 16); j = *(_QWORD *)(j + 8) )
        i = j;
    }
    else
    {
      j = std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Min();
    }
  }
  if ( v15 )
    ((void (__fastcall *)(IStream *))v15->lpVtbl->Release)(v15);
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v13 )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v27);
  return std::pair<std::wstring,win_scope::scope<win_musl::consumption::ZipConsumptionPart *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>>::~pair<std::wstring,win_scope::scope<win_musl::consumption::ZipConsumptionPart *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>>(v30);
}

```

## disassembly

```asm
0x180108ed4  push    rbp
0x180108ed6  push    rbx
0x180108ed7  push    rsi
0x180108ed8  push    rdi
0x180108ed9  push    r12
0x180108edb  push    r13
0x180108edd  push    r14
0x180108edf  push    r15
0x180108ee1  lea     rbp, [rsp-88h]
0x180108ee9  sub     rsp, 188h
0x180108ef0  mov     [rbp+0C0h+var_130], 0FFFFFFFFFFFFFFFEh
0x180108ef8  mov     rax, cs:__security_cookie
0x180108eff  xor     rax, rsp
0x180108f02  mov     [rbp+0C0h+var_50], rax
0x180108f06  mov     r15, r9
0x180108f09  mov     rbx, r8
0x180108f0c  mov     r13, rdx
0x180108f0f  mov     rdi, rcx
0x180108f12  mov     r12, [rbp+0C0h+arg_20]
0x180108f19  mov     dword ptr [r8], 0
0x180108f20  mov     rcx, r9
0x180108f23  call    ?clear@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAXXZ; std::wstring::clear(void)
0x180108f28  mov     rcx, r12
0x180108f2b  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::clear(void)
0x180108f30  mov     [rbp+0C0h+var_108], 7
0x180108f38  mov     [rbp+0C0h+var_110], 0
0x180108f40  xor     eax, eax
0x180108f42  mov     [rbp+0C0h+var_120], ax
0x180108f46  xorps   xmm0, xmm0
0x180108f49  movdqu  xmmword ptr [rbp+0C0h+var_100], xmm0
0x180108f4e  lea     rax, [rbp+0C0h+var_128]
0x180108f52  mov     qword ptr [rbp+0C0h+var_148+8], rax
0x180108f56  mov     [rbp+0C0h+var_138], 1
0x180108f5a  lea     rcx, [rbp+0C0h+var_128]
0x180108f5e  call    ??$Get@V?$SingletonInitializer@VObjectBlob@Model@win_dox@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VObjectBlob@Model@win_dox@@@234@@win_musl@@SAPEBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@1@V?$SingletonInitializer@VObjectBlob@Model@win_dox@@@341@@Z; win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::ObjectBlob>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::ObjectBlob>>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::ObjectBlob>)
0x180108f63  mov     qword ptr [rsp+1C0h+var_148], rax
0x180108f68  mov     ecx, 140h; unsigned __int64
0x180108f6d  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x180108f72  mov     [rsp+1C0h+var_180], rax
0x180108f77  test    rax, rax
0x180108f7a  jz      short loc_180108F8E
0x180108f7c  lea     rdx, [rsp+1C0h+var_148]
0x180108f81  mov     rcx, rax
0x180108f84  call    ??0SignaturePropertiesContentHandler@consumption@win_musl@@QEAA@AEBV?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@12@@Z; win_musl::consumption::SignaturePropertiesContentHandler::SignaturePropertiesContentHandler(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl> const &)
0x180108f89  mov     rsi, rax
0x180108f8c  jmp     short loc_180108F90
0x180108f8e  xor     esi, esi
0x180108f90  xorps   xmm0, xmm0
0x180108f93  movdqu  [rsp+1C0h+var_148], xmm0
0x180108f99  mov     [rsp+1C0h+var_180], rsi
0x180108f9e  test    rsi, rsi
0x180108fa1  jz      short loc_180108FF3
0x180108fa3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180108faa  mov     ecx, 18h; unsigned __int64
0x180108faf  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180108fb4  mov     r14, rax
0x180108fb7  xor     eax, eax
0x180108fb9  test    r14, r14
0x180108fbc  jz      short loc_180108FE3
0x180108fbe  mov     [r14+8], rax
0x180108fc2  lea     rax, ??_7?$counted_strong_weak@PEAVZipConsumptionPart@consumption@win_musl@@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@6B@; const win_scope::counted_strong_weak<win_musl::consumption::ZipConsumptionPart *,win_scope::const_policies<win_scope::resource_policies>>::`vftable'
0x180108fc9  mov     [r14], rax
0x180108fcc  mov     [r14+10h], rsi
0x180108fd0  mov     qword ptr [rsp+1C0h+var_148], r14
0x180108fd5  mov     rcx, r14; this
0x180108fd8  call    ?AddRef@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::AddRef(void)
0x180108fdd  mov     qword ptr [rbp+0C0h+var_148+8], rsi
0x180108fe1  jmp     short loc_180108FFC
0x180108fe3  lea     rcx, [rsp+1C0h+var_180]
0x180108fe8  call    ??$close@VCallingThread@win_musl@@@close_delete@win_scope@@SAXPEAPEAVCallingThread@win_musl@@@Z; win_scope::close_delete::close<win_musl::CallingThread>(win_musl::CallingThread * *)
0x180108fed  call    ?report_init_failure@report_policy_throw@win_scope@@SAXXZ; win_scope::report_policy_throw::report_init_failure(void)
0x180108ff3  mov     rsi, qword ptr [rbp+0C0h+var_148+8]
0x180108ff7  mov     r14, qword ptr [rsp+1C0h+var_148]
0x180108ffc  lea     rdx, [rsp+1C0h+var_148]
0x180109001  lea     rcx, [rsp+1C0h+ppv]; ppv
0x180109006  call    ??$CreateSaxParser@V?$scope@PEAVSignaturePropertiesContentHandler@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@consumption@win_musl@@YA?AV?$scope@PEAUISAXXMLReader@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEAV?$scope@PEAVSignaturePropertiesContentHandler@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@3@@Z; win_musl::consumption::CreateSaxParser<win_scope::scope<win_musl::consumption::SignaturePropertiesContentHandler *,win_scope::const_policies<win_scope::shared_policies>>>(win_scope::scope<win_musl::consumption::SignaturePropertiesContentHandler *,win_scope::const_policies<win_scope::shared_policies>> &)
0x18010900b  nop
0x18010900c  mov     edx, [rdi+4]; cbInit
0x18010900f  mov     rcx, [rdi+8]; pInit
0x180109013  call    cs:__imp_SHCreateMemStream
0x180109019  xor     edi, edi
0x18010901b  test    rax, rax
0x18010901e  cmovnz  rdi, rax
0x180109022  mov     [rsp+1C0h+var_180], rdi
0x180109027  xorps   xmm0, xmm0
0x18010902a  xor     edx, edx
0x18010902c  movups  [rsp+1C0h+var_170], xmm0
0x180109031  lea     eax, [rdx+0Dh]
0x180109034  mov     word ptr [rsp+1C0h+var_170], ax
0x180109039  mov     qword ptr [rsp+1C0h+var_170+8], rdi
0x18010903e  mov     rcx, [rsp+1C0h+ppv]
0x180109043  movups  xmm0, [rsp+1C0h+var_170]
0x180109048  movaps  [rsp+1C0h+var_170], xmm0
0x18010904d  mov     [rsp+1C0h+var_160], rdx
0x180109052  mov     rax, [rcx]
0x180109055  lea     rdx, [rsp+1C0h+var_170]
0x18010905a  mov     rax, [rax+98h]
0x180109061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109066  test    eax, eax
0x180109068  jns     short loc_1801090AA
0x18010906a  lea     rcx, aParsingSignatu; "Parsing <SignatureProperties> failed"
0x180109071  mov     [rsp+1C0h+var_190], rcx; struct win_musl::TStringEllipseBase *
0x180109076  mov     [rsp+1C0h+var_198], eax; unsigned int
0x18010907a  mov     dword ptr [rsp+1C0h+Reserved], 2C7h; unsigned int
0x180109082  lea     r9, word_180139126
0x180109089  lea     r8, aNoFilename; "(no filename)"
0x180109090  lea     rcx, [rbp+0C0h+pExceptionObject]; this
0x180109094  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180109099  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1801090a0  lea     rcx, [rbp+0C0h+pExceptionObject]; pExceptionObject
0x1801090a4  call    _CxxThrowException_0
0x1801090aa  mov     rdx, r13
0x1801090ad  lea     rcx, [rbp+0C0h+var_100]
0x1801090b1  call    ?ValidateSignatureProperties@win_dox@@YAXAEBV?$scope@PEAVSignatureProperties@Model@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_dox::ValidateSignatureProperties(win_scope::scope<win_dox::Model::SignatureProperties *,win_scope::const_policies<win_scope::shared_policies>> const &,std::wstring const &)
0x1801090b6  xorps   xmm0, xmm0
0x1801090b9  movdqu  [rsp+1C0h+var_170], xmm0
0x1801090bf  mov     rcx, [rbp+0C0h+var_100]; this
0x1801090c3  xor     r13d, r13d
0x1801090c6  test    rcx, rcx
0x1801090c9  jz      short loc_1801090DE
0x1801090cb  mov     r9, [rbp+0C0h+var_100+8]
0x1801090cf  call    ?AddRef@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::AddRef(void)
0x1801090d4  mov     qword ptr [rsp+1C0h+var_170], rcx
0x1801090d9  mov     qword ptr [rsp+1C0h+var_170+8], r9
0x1801090de  mov     r8, r15
0x1801090e1  mov     rdx, rbx
0x1801090e4  lea     rcx, [rsp+1C0h+var_170]
0x1801090e9  call    ?GetSignatureTime@win_dox@@YAXV?$scope@PEAVSignatureProperties@Model@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEAW4__MIDL___MIDL_itf_msopc_0001_0076_0005@@PEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_dox::GetSignatureTime(win_scope::scope<win_dox::Model::SignatureProperties *,win_scope::const_policies<win_scope::shared_policies>>,__MIDL___MIDL_itf_msopc_0001_0076_0005 *,std::wstring *)
0x1801090ee  mov     rsi, [rsi+128h]
0x1801090f5  mov     rbx, [rsi]
0x1801090f8  cmp     rbx, rsi
0x1801090fb  jz      short loc_180109159
0x1801090fd  lea     r8, [rbx+18h]
0x180109101  lea     rdx, [rsp+1C0h+var_170]
0x180109106  mov     rcx, r12
0x180109109  call    ?insert@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@Viterator@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@@std@@@2@$0A@@std@@@std@@_N@2@AEBU?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::insert(std::pair<std::wstring const,std::wstring> const &)
0x18010910e  cmp     [rbx+69h], r13b
0x180109112  jz      short loc_18010912A
0x180109114  mov     [rsp+1C0h+Reserved], r13; Reserved
0x180109119  xor     r9d, r9d; LineNo
0x18010911c  xor     r8d, r8d; FileName
0x18010911f  xor     edx, edx; FunctionName
0x180109121  xor     ecx, ecx; Expression
0x180109123  call    _invalid_parameter
0x180109128  jmp     short loc_1801090F8
0x18010912a  mov     rcx, [rbx+10h]
0x18010912e  cmp     [rcx+69h], r13b
0x180109132  jnz     short loc_18010913B
0x180109134  call    ?_Min@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@@std@@@2@$0A@@std@@@std@@KAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V12@@std@@@2@$0A@@std@@@2@PEAU342@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Min(std::_Tree_nod<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Node *)
0x180109139  jmp     short loc_180109154
0x18010913b  mov     rax, [rbx+8]
0x18010913f  jmp     short loc_18010914E
0x180109141  cmp     rbx, [rax+10h]
0x180109145  jnz     short loc_180109154
0x180109147  mov     rbx, rax
0x18010914a  mov     rax, [rax+8]
0x18010914e  cmp     [rax+69h], r13b
0x180109152  jz      short loc_180109141
0x180109154  mov     rbx, rax
0x180109157  jmp     short loc_1801090F8
0x180109159  test    rdi, rdi
0x18010915c  jz      short loc_18010916E
0x18010915e  mov     rax, [rdi]
0x180109161  mov     rcx, rdi
0x180109164  mov     rax, [rax+10h]
0x180109168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010916d  nop
0x18010916e  mov     rcx, [rsp+1C0h+ppv]
0x180109173  test    rcx, rcx
0x180109176  jz      short loc_180109189
0x180109178  mov     rax, [rcx]
0x18010917b  mov     rax, [rax+10h]
0x18010917f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109184  mov     [rsp+1C0h+ppv], r13
0x180109189  test    r14, r14
0x18010918c  jz      short loc_180109199
0x18010918e  lea     rcx, [rsp+1C0h+var_148]
0x180109193  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x180109198  nop
0x180109199  lea     rcx, [rbp+0C0h+var_128]
0x18010919d  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVZipConsumptionPart@consumption@win_musl@@U?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@std@@QEAA@XZ; std::pair<std::wstring,win_scope::scope<win_musl::consumption::ZipConsumptionPart *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>>::~pair<std::wstring,win_scope::scope<win_musl::consumption::ZipConsumptionPart *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>>(void)
0x1801091a2  mov     rcx, [rbp+0C0h+var_50]
0x1801091a6  xor     rcx, rsp; StackCookie
0x1801091a9  call    __security_check_cookie
0x1801091ae  add     rsp, 188h
0x1801091b5  pop     r15
0x1801091b7  pop     r14
0x1801091b9  pop     r13
0x1801091bb  pop     r12
0x1801091bd  pop     rdi
0x1801091be  pop     rsi
0x1801091bf  pop     rbx
0x1801091c0  pop     rbp
0x1801091c1  retn
```

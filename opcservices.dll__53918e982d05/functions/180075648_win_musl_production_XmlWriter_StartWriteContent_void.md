# win_musl::production::XmlWriter::StartWriteContent(void)

- ea: `0x180075648`
- end: `0x1800758a0`
- name: `?StartWriteContent@XmlWriter@production@win_musl@@QEAA?AV?$scope@PEAUISAXContentHandler@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ`
- size: `600`
- prototype: `__int64 __fastcall(void **ppvObject)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a3ca0`
- `0x1800a3dc4`

## callees

- `0x180002f10`
- `0x180011fe8`
- `0x1800120a4`
- `0x180012468`
- `0x1800124f4`
- `0x18002db70`
- `0x180075648`
- `0x1800758a8`
- `0x1800cd6fc`
- `0x1800d6354`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x18007571f`
- `XmlLite!CreateXmlWriter` at `0x18007571f`

## string_xrefs

- `0x1800757be`: `Call to IXmlWriter::SetOutput failed with HResult 0x%X.`
- `0x18007573f`: `Call to ::CreateXmlWriter failed with HResult 0x%X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall win_musl::production::XmlWriter::StartWriteContent(void **ppvObject, _QWORD *a2)
{
  __int64 v4; // rcx
  HRESULT XmlWriter; // esi
  signed int v6; // esi
  _QWORD *v7; // rax
  _QWORD v9[3]; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v10[40]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v12[160]; // [rsp+C8h] [rbp-40h] BYREF
  wchar_t v13[512]; // [rsp+168h] [rbp+60h] BYREF

  v9[2] = -2;
  v9[0] = a2;
  if ( *((_DWORD *)ppvObject + 4) == 2 )
  {
    win_musl::DebugLogHelper("(no filename)", &word_180139126, 212, 1024, -2147418113, L"Writing content started");
    std::string::string(v10, "Program has entered an unexpected state");
    std::logic_error::logic_error(pExceptionObject, v10);
    throw (std::logic_error *)pExceptionObject;
  }
  v4 = (__int64)*ppvObject;
  *ppvObject = 0;
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  *ppvObject = 0;
  XmlWriter = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, ppvObject, 0);
  if ( XmlWriter < 0 )
  {
    memset_0(v13, 0, sizeof(v13));
    StringCchPrintfW(v13, 0x200u, L"Call to ::CreateXmlWriter failed with HResult 0x%X.", (unsigned int)XmlWriter);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)v12,
      0xE1u,
      XmlWriter,
      (struct win_musl::TStringEllipseBase *)v13);
    throw (SplException::THResultException *)v12;
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD, void *))(*(_QWORD *)*ppvObject + 24LL))(*ppvObject, ppvObject[1]);
  if ( v6 < 0 )
  {
    memset_0(v13, 0, sizeof(v13));
    StringCchPrintfW(v13, 0x200u, L"Call to IXmlWriter::SetOutput failed with HResult 0x%X.", (unsigned int)v6);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)v12,
      0xE5u,
      v6,
      (struct win_musl::TStringEllipseBase *)v13);
    throw (SplException::THResultException *)v12;
  }
  (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*ppvObject + 40LL))(*ppvObject, 2);
  (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*ppvObject + 40LL))(*ppvObject, 1);
  *((_DWORD *)ppvObject + 4) = 2;
  v7 = (_QWORD *)win_musl::UnknownOnlyLite<win_musl::production::XmlWriterAdapter,win_mp_lib::type_list<ISAXContentHandler,win_mp_lib::null_type>,win_mp_lib::null_type>::CreateInstance<win_scope::no_addref_release<IXmlWriter> *>(
                   v9,
                   *ppvObject);
  *a2 = 0;
  win_scope::detail::scope_helper<win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *,win_scope::const_policies<win_scope::types_6<win_scope::close_com,win_scope::convert_normal,win_scope::acquire_com,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_com>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::reset(
    a2,
    *v7);
  if ( v9[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v9[0] + 16LL))(v9[0]);
  return a2;
}

```

## disassembly

```asm
0x180075648  mov     rax, rsp
0x18007564b  push    rbp
0x18007564c  push    rsi
0x18007564d  push    rdi
0x18007564e  lea     rbp, [rax-488h]
0x180075655  sub     rsp, 570h
0x18007565c  mov     qword ptr [rsp+580h+var_530], 0FFFFFFFFFFFFFFFEh
0x180075665  mov     [rax+18h], rbx
0x180075669  mov     rax, cs:__security_cookie
0x180075670  xor     rax, rsp
0x180075673  mov     [rbp+480h+var_20], rax
0x18007567a  mov     rdi, rdx
0x18007567d  mov     rbx, rcx
0x180075680  mov     [rsp+40h], rdx
0x180075685  cmp     dword ptr [rcx+10h], 2
0x180075689  jnz     short loc_1800756EF
0x18007568b  lea     rax, aWritingContent; "Writing content started"
0x180075692  mov     qword ptr [rsp+580h+var_558], rax
0x180075697  mov     [rsp+580h+var_560], 8000FFFFh
0x18007569f  mov     r9d, 400h
0x1800756a5  mov     r8d, 0D4h
0x1800756ab  lea     rdx, word_180139126
0x1800756b2  lea     rcx, aNoFilename; "(no filename)"
0x1800756b9  call    ?DebugLogHelper@win_musl@@YAXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z; win_musl::DebugLogHelper(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *)
0x1800756be  lea     rdx, aProgramHasEnte; "Program has entered an unexpected state"
0x1800756c5  lea     rcx, [rsp+58h]
0x1800756ca  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x1800756cf  nop
0x1800756d0  lea     rdx, [rsp+58h]
0x1800756d5  lea     rcx, [rbp+480h+pExceptionObject]
0x1800756d9  call    ??0logic_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@1@@Z; std::logic_error::logic_error(std::string const &)
0x1800756de  lea     rdx, _TI2?AVlogic_error@std@@; pThrowInfo
0x1800756e5  lea     rcx, [rbp+480h+pExceptionObject]; pExceptionObject
0x1800756e9  call    _CxxThrowException_0
0x1800756ef  mov     rcx, [rcx]
0x1800756f2  mov     qword ptr [rbx], 0
0x1800756f9  test    rcx, rcx
0x1800756fc  jz      short loc_18007570B
0x1800756fe  mov     rax, [rcx]
0x180075701  mov     rax, [rax+10h]
0x180075705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007570a  nop
0x18007570b  mov     qword ptr [rbx], 0
0x180075712  xor     r8d, r8d; pMalloc
0x180075715  mov     rdx, rbx; ppvObject
0x180075718  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x18007571f  call    cs:__imp_CreateXmlWriter
0x180075725  mov     esi, eax
0x180075727  test    eax, eax
0x180075729  jns     short loc_180075791
0x18007572b  xor     edx, edx; Val
0x18007572d  mov     r8d, 400h; Size
0x180075733  lea     rcx, [rbp+480h+var_420]; void *
0x180075737  call    memset_0
0x18007573c  mov     r9d, esi
0x18007573f  lea     r8, aCallToCreatexm; "Call to ::CreateXmlWriter failed with H"...
0x180075746  mov     edx, 200h; unsigned __int64
0x18007574b  lea     rcx, [rbp+480h+var_420]; wchar_t *
0x18007574f  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180075754  lea     rax, [rbp+480h+var_420]
0x180075758  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x18007575d  mov     [rsp+580h+var_558], esi; unsigned int
0x180075761  mov     [rsp+580h+var_560], 0E1h; unsigned int
0x180075769  lea     r9, word_180139126
0x180075770  lea     r8, aNoFilename; "(no filename)"
0x180075777  lea     rcx, [rbp+480h+var_4C0]; this
0x18007577b  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180075780  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180075787  lea     rcx, [rbp+480h+var_4C0]; pExceptionObject
0x18007578b  call    _CxxThrowException_0
0x180075791  mov     rcx, [rbx]
0x180075794  mov     rax, [rcx]
0x180075797  mov     rdx, [rbx+8]
0x18007579b  mov     rax, [rax+18h]
0x18007579f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800757a4  mov     esi, eax
0x1800757a6  test    eax, eax
0x1800757a8  jns     short loc_180075810
0x1800757aa  xor     edx, edx; Val
0x1800757ac  mov     r8d, 400h; Size
0x1800757b2  lea     rcx, [rbp+480h+var_420]; void *
0x1800757b6  call    memset_0
0x1800757bb  mov     r9d, esi
0x1800757be  lea     r8, aCallToIxmlwrit; "Call to IXmlWriter::SetOutput failed wi"...
0x1800757c5  mov     edx, 200h; unsigned __int64
0x1800757ca  lea     rcx, [rbp+480h+var_420]; wchar_t *
0x1800757ce  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800757d3  lea     rax, [rbp+480h+var_420]
0x1800757d7  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x1800757dc  mov     [rsp+580h+var_558], esi; unsigned int
0x1800757e0  mov     [rsp+580h+var_560], 0E5h; unsigned int
0x1800757e8  lea     r9, word_180139126
0x1800757ef  lea     r8, aNoFilename; "(no filename)"
0x1800757f6  lea     rcx, [rbp+480h+var_4C0]; this
0x1800757fa  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800757ff  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180075806  lea     rcx, [rbp+480h+var_4C0]; pExceptionObject
0x18007580a  call    _CxxThrowException_0
0x180075810  mov     rcx, [rbx]
0x180075813  mov     rax, [rcx]
0x180075816  xor     r8d, r8d
0x180075819  lea     edx, [r8+2]
0x18007581d  mov     rax, [rax+28h]
0x180075821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075826  mov     rcx, [rbx]
0x180075829  mov     rax, [rcx]
0x18007582c  xor     r8d, r8d
0x18007582f  lea     edx, [r8+1]
0x180075833  mov     rax, [rax+28h]
0x180075837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007583c  mov     dword ptr [rbx+10h], 2
0x180075843  mov     rdx, [rbx]
0x180075846  lea     rcx, [rsp+40h]
0x18007584b  call    ??$CreateInstance@PEAV?$no_addref_release@UIXmlWriter@@@win_scope@@@?$UnknownOnlyLite@VXmlWriterAdapter@production@win_musl@@V?$type_list@UISAXContentHandler@@Vnull_type@win_mp_lib@@@win_mp_lib@@Vnull_type@5@@win_musl@@SA?AV?$scope@PEAV?$UnknownOnlyLite@VXmlWriterAdapter@production@win_musl@@V?$type_list@UISAXContentHandler@@Vnull_type@win_mp_lib@@@win_mp_lib@@Vnull_type@5@@win_musl@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@PEAV?$no_addref_release@UIXmlWriter@@@3@@Z; win_musl::UnknownOnlyLite<win_musl::production::XmlWriterAdapter,win_mp_lib::type_list<ISAXContentHandler,win_mp_lib::null_type>,win_mp_lib::null_type>::CreateInstance<win_scope::no_addref_release<IXmlWriter> *>(win_scope::no_addref_release<IXmlWriter> *)
0x180075850  nop
0x180075851  mov     qword ptr [rdi], 0
0x180075858  mov     rdx, [rax]
0x18007585b  mov     rcx, rdi
0x18007585e  call    ?reset@?$scope_helper@PEAV?$ByteReceiverUnique@VZipLocalConsumer@consumption@win_musl@@$00UIUnknown@@@win_musl@@U?$const_policies@U?$types_6@Uclose_com@win_scope@@Uconvert_normal@2@Uacquire_com@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Usafe_types_com@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAV?$ByteReceiverUnique@VZipLocalConsumer@consumption@win_musl@@$00UIUnknown@@@win_musl@@U?$const_policies@U?$types_6@Uclose_com@win_scope@@Uconvert_normal@2@Uacquire_com@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Usafe_types_com@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@3@PEAV?$ByteReceiverUnique@VZipLocalConsumer@consumption@win_musl@@$00UIUnknown@@@win_musl@@@Z; win_scope::detail::scope_helper<win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *,win_scope::const_policies<win_scope::types_6<win_scope::close_com,win_scope::convert_normal,win_scope::acquire_com,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_com>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::reset(win_scope::scope<win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *,win_scope::const_policies<win_scope::types_6<win_scope::close_com,win_scope::convert_normal,win_scope::acquire_com,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_com>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> &,win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *)
0x180075863  nop
0x180075864  mov     rcx, [rsp+40h]
0x180075869  test    rcx, rcx
0x18007586c  jz      short loc_18007587B
0x18007586e  mov     rdx, [rcx]
0x180075871  mov     rax, [rdx+10h]
0x180075875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007587a  nop
0x18007587b  mov     rax, rdi
0x18007587e  mov     rcx, [rbp+480h+var_20]
0x180075885  xor     rcx, rsp; StackCookie
0x180075888  call    __security_check_cookie
0x18007588d  mov     rbx, [rsp+580h+arg_10]
0x180075895  add     rsp, 570h
0x18007589c  pop     rdi
0x18007589d  pop     rsi
0x18007589e  pop     rbp
0x18007589f  retn
```

# win_dox::OpcRelationshipStream::OpcRelationshipStream(void)

- ea: `0x1800f7768`
- end: `0x1800f78c1`
- name: `??0OpcRelationshipStream@win_dox@@QEAA@XZ`
- size: `345`
- prototype: `__int64 __fastcall(win_dox::OpcRelationshipStream *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a97a8`

## callees

- `0x180002f10`
- `0x180004680`
- `0x180012468`
- `0x18002cfa8`
- `0x18002db70`
- `0x180070ab0`
- `0x1800a44b8`
- `0x1800cd6fc`
- `0x1800d6354`
- `0x1800f7768`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f77d9`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f77d9`

## string_xrefs

- `0x1800f77f9`: `Call to CreateStreamOnHGlobal failed with HResult 0x%X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
win_dox::OpcRelationshipStream *__fastcall win_dox::OpcRelationshipStream::OpcRelationshipStream(
        win_dox::OpcRelationshipStream *this)
{
  HRESULT v2; // edi
  _QWORD *v3; // rax
  LPSTREAM ppstm; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v6[8]; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v7[4]; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+78h] [rbp-90h] BYREF
  wchar_t v9[512]; // [rsp+118h] [rbp+10h] BYREF

  v7[1] = -2;
  v7[2] = this;
  *(_QWORD *)this = 0;
  *((_BYTE *)this + 8) = 0;
  ppstm = 0;
  win_scope::detail::scope_helper<win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *,win_scope::const_policies<win_scope::types_6<win_scope::close_com,win_scope::convert_normal,win_scope::acquire_com,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_com>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::reset(
    &ppstm,
    0);
  ppstm = 0;
  v2 = CreateStreamOnHGlobal(0, 1, &ppstm);
  if ( v2 < 0 )
  {
    memset_0(v9, 0, sizeof(v9));
    StringCchPrintfW(v9, 0x200u, L"Call to CreateStreamOnHGlobal failed with HResult 0x%X.", (unsigned int)v2);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x1Bu,
      v2,
      (struct win_musl::TStringEllipseBase *)v9);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v3 = (_QWORD *)win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>(
                   v7,
                   &ppstm);
  win_dox::Stream::Stream((__int64)v6, v3);
  win_dox::Stream::operator=(this, v6);
  win_dox::Uri::~Uri((win_dox::Uri *)v6);
  if ( ppstm )
    ((void (__fastcall *)(LPSTREAM, struct IStreamVtbl *))ppstm->lpVtbl->Release)(ppstm, ppstm->lpVtbl);
  return this;
}

```

## disassembly

```asm
0x1800f7768  mov     rax, rsp
0x1800f776b  push    rbp
0x1800f776c  lea     rbp, [rax-428h]
0x1800f7773  sub     rsp, 520h
0x1800f777a  mov     [rsp+520h+var_4C8], 0FFFFFFFFFFFFFFFEh
0x1800f7783  mov     [rax+10h], rbx
0x1800f7787  mov     [rax+18h], rdi
0x1800f778b  mov     rax, cs:__security_cookie
0x1800f7792  xor     rax, rsp
0x1800f7795  mov     [rbp+420h+var_10], rax
0x1800f779c  mov     rbx, rcx
0x1800f779f  mov     [rsp+520h+var_4C0], rcx
0x1800f77a4  mov     qword ptr [rcx], 0
0x1800f77ab  mov     byte ptr [rcx+8], 0
0x1800f77af  mov     [rsp+520h+ppstm], 0
0x1800f77b8  xor     edx, edx
0x1800f77ba  lea     rcx, [rsp+520h+ppstm]
0x1800f77bf  call    ?reset@?$scope_helper@PEAV?$ByteReceiverUnique@VZipLocalConsumer@consumption@win_musl@@$00UIUnknown@@@win_musl@@U?$const_policies@U?$types_6@Uclose_com@win_scope@@Uconvert_normal@2@Uacquire_com@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Usafe_types_com@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAV?$ByteReceiverUnique@VZipLocalConsumer@consumption@win_musl@@$00UIUnknown@@@win_musl@@U?$const_policies@U?$types_6@Uclose_com@win_scope@@Uconvert_normal@2@Uacquire_com@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Usafe_types_com@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@3@PEAV?$ByteReceiverUnique@VZipLocalConsumer@consumption@win_musl@@$00UIUnknown@@@win_musl@@@Z; win_scope::detail::scope_helper<win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *,win_scope::const_policies<win_scope::types_6<win_scope::close_com,win_scope::convert_normal,win_scope::acquire_com,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_com>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::reset(win_scope::scope<win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *,win_scope::const_policies<win_scope::types_6<win_scope::close_com,win_scope::convert_normal,win_scope::acquire_com,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_com>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> &,win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *)
0x1800f77c4  mov     [rsp+520h+ppstm], 0
0x1800f77cd  lea     r8, [rsp+520h+ppstm]; ppstm
0x1800f77d2  mov     edx, 1; fDeleteOnRelease
0x1800f77d7  xor     ecx, ecx; hGlobal
0x1800f77d9  call    cs:__imp_CreateStreamOnHGlobal
0x1800f77df  mov     edi, eax
0x1800f77e1  test    eax, eax
0x1800f77e3  jns     short loc_1800F784D
0x1800f77e5  xor     edx, edx; Val
0x1800f77e7  mov     r8d, 400h; Size
0x1800f77ed  lea     rcx, [rbp+420h+var_410]; void *
0x1800f77f1  call    memset_0
0x1800f77f6  mov     r9d, edi
0x1800f77f9  lea     r8, aCallToCreatest; "Call to CreateStreamOnHGlobal failed wi"...
0x1800f7800  mov     edx, 200h; unsigned __int64
0x1800f7805  lea     rcx, [rbp+420h+var_410]; wchar_t *
0x1800f7809  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800f780e  lea     rax, [rbp+420h+var_410]
0x1800f7812  mov     [rsp+520h+var_4F0], rax; struct win_musl::TStringEllipseBase *
0x1800f7817  mov     [rsp+520h+var_4F8], edi; unsigned int
0x1800f781b  mov     [rsp+520h+var_500], 1Bh; unsigned int
0x1800f7823  lea     r9, word_180139126
0x1800f782a  lea     r8, aNoFilename; "(no filename)"
0x1800f7831  lea     rcx, [rsp+520h+pExceptionObject]; this
0x1800f7836  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800f783b  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800f7842  lea     rcx, [rsp+520h+pExceptionObject]; pExceptionObject
0x1800f7847  call    _CxxThrowException_0
0x1800f784d  lea     rdx, [rsp+520h+ppstm]
0x1800f7852  lea     rcx, [rsp+520h+var_4D0]
0x1800f7857  call    ??0?$scope@PEAVContainerSender@consumption@win_musl@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>> const &)
0x1800f785c  mov     rdx, rax
0x1800f785f  lea     rcx, [rsp+520h+var_4D8]
0x1800f7864  call    ??$?0V?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@Stream@win_dox@@QEAA@V?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::Stream::Stream(win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>)
0x1800f7869  nop
0x1800f786a  lea     rdx, [rsp+520h+var_4D8]
0x1800f786f  mov     rcx, rbx
0x1800f7872  call    ??4Stream@win_dox@@QEAAAEAV01@AEBV01@@Z; win_dox::Stream::operator=(win_dox::Stream const &)
0x1800f7877  nop
0x1800f7878  lea     rcx, [rsp+520h+var_4D8]; this
0x1800f787d  call    ??1Uri@win_dox@@QEAA@XZ; win_dox::Uri::~Uri(void)
0x1800f7882  nop
0x1800f7883  mov     rcx, [rsp+520h+ppstm]
0x1800f7888  test    rcx, rcx
0x1800f788b  jz      short loc_1800F789A
0x1800f788d  mov     rdx, [rcx]
0x1800f7890  mov     rax, [rdx+10h]
0x1800f7894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7899  nop
0x1800f789a  mov     rax, rbx
0x1800f789d  mov     rcx, [rbp+420h+var_10]
0x1800f78a4  xor     rcx, rsp; StackCookie
0x1800f78a7  call    __security_check_cookie
0x1800f78ac  lea     r11, [rsp+520h+var_s0]
0x1800f78b4  mov     rbx, [r11+18h]
0x1800f78b8  mov     rdi, [r11+20h]
0x1800f78bc  mov     rsp, r11
0x1800f78bf  pop     rbp
0x1800f78c0  retn
```

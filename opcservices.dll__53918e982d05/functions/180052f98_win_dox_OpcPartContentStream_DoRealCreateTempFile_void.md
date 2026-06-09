# win_dox::OpcPartContentStream::DoRealCreateTempFile(void)

- ea: `0x180052f98`
- end: `0x18005331f`
- name: `?DoRealCreateTempFile@OpcPartContentStream@win_dox@@AEAAXXZ`
- size: `903`
- prototype: `void __fastcall(win_dox::OpcPartContentStream *__hidden this)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800b5170`

## callees

- `0x1800034d8`
- `0x180004680`
- `0x18000531c`
- `0x18000f9a0`
- `0x180012468`
- `0x180015660`
- `0x18002b6c8`
- `0x18002bad0`
- `0x18002cf10`
- `0x18002db70`
- `0x180034468`
- `0x18004f700`
- `0x180052f98`
- `0x180053328`
- `0x1800538b0`
- `0x18006458c`
- `0x180064624`
- `0x1800646e8`
- `0x1800652d0`
- `0x180065458`
- `0x18006554c`
- `0x18008f584`
- `0x1800cd1c4`
- `0x1800cd6fc`
- `0x1800d6354`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180053014`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180053014`

## string_xrefs

- `0x1800532c7`: `Call to ::CreateFile failed with HResult 0x%X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall win_dox::OpcPartContentStream::DoRealCreateTempFile(win_dox::OpcPartContentStream *this)
{
  __int64 TemporaryFileName; // rax
  const WCHAR *v3; // rcx
  HANDLE FileW; // rdx
  const char *v5; // rdx
  win_musl::detail *v6; // rcx
  unsigned int v7; // r8d
  win_scope::counted_strong_weak_base *v8; // rdi
  __int64 v9; // rbx
  _QWORD *v10; // rax
  __int64 v11; // rdx
  __int128 *v12; // rax
  __int128 v13; // xmm1
  int v14; // ebx
  __int64 v15; // rax
  const char *v16; // rdx
  unsigned int v17; // r8d
  win_dox::Stream *v18; // rax
  win_dox::Stream *v19; // rbx
  win_scope::counted_strong_weak_base *v20; // rbx
  win_scope::counted_strong_weak_base *v21; // rsi
  __int64 Bytes; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  unsigned int LastErrorAsFailHR; // ebx
  _QWORD *v26; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v27; // [rsp+50h] [rbp-B8h] BYREF
  void **v28; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+68h] [rbp-A0h]
  void **v30; // [rsp+70h] [rbp-98h] BYREF
  __int64 v31; // [rsp+78h] [rbp-90h]
  win_scope::counted_strong_weak_base *v32[2]; // [rsp+80h] [rbp-88h] BYREF
  win_scope::counted_strong_weak_base *v33; // [rsp+90h] [rbp-78h] BYREF
  __int64 v34; // [rsp+98h] [rbp-70h]
  __int64 v35; // [rsp+A0h] [rbp-68h]
  _BYTE v36[24]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v37[8]; // [rsp+C0h] [rbp-48h] BYREF
  void *Block; // [rsp+C8h] [rbp-40h]
  __int64 v39; // [rsp+D8h] [rbp-30h]
  unsigned __int64 v40; // [rsp+E0h] [rbp-28h]
  _BYTE pExceptionObject[160]; // [rsp+E8h] [rbp-20h] BYREF
  wchar_t v42[512]; // [rsp+188h] [rbp+80h] BYREF

  v35 = -2;
  TemporaryFileName = win_musl::CreateTemporaryFileName(v37);
  v3 = (const WCHAR *)(TemporaryFileName + 8);
  if ( *(_QWORD *)(TemporaryFileName + 32) >= 8u )
    v3 = *(const WCHAR **)v3;
  FileW = CreateFileW(v3, 0xC0000000, 0, 0, 1u, 0x4000100u, 0);
  win_scope::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::value_const<void *,-1>>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::value_const<void *,-1>>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>(
    &v33,
    FileW);
  if ( v40 >= 8 )
    operator delete(Block);
  v40 = 7;
  v39 = 0;
  LOWORD(Block) = 0;
  v8 = v33;
  if ( !v33 || (v9 = v34, v34 == -1) )
  {
    LastErrorAsFailHR = win_musl::detail::GetLastErrorAsFailHR(v6);
    memset_0(v42, 0, sizeof(v42));
    StringCchPrintfW(v42, 0x200u, L"Call to ::CreateFile failed with HResult 0x%X.", LastErrorAsFailHR);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x18Bu,
      LastErrorAsFailHR,
      (struct win_musl::TStringEllipseBase *)v42);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v10 = operator new(0x20u, v5, v7);
  v26 = v10;
  if ( v10 )
  {
    *v10 = 0;
    v10[1] = 0;
    v10[2] = -1;
    win_scope::counted_strong_weak_base::AddRef(v8);
    *(_QWORD *)(v11 + 8) = v8;
    *(_QWORD *)(v11 + 16) = v9;
    *(_DWORD *)(v11 + 24) = 1;
  }
  else
  {
    v11 = 0;
  }
  v12 = (__int128 *)win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>(
                      &v27,
                      v11);
  v13 = *v12;
  *v12 = *((_OWORD *)this + 3);
  *((_OWORD *)this + 3) = v13;
  if ( *((_QWORD *)&v27 + 1) && (_QWORD)v27 )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v27);
  win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>(
    &v26,
    (char *)this + 24);
  v14 = -1;
  if ( v26 )
  {
    v14 = dword_1801C4EA8;
    (*(void (**)(void))(*v26 + 16LL))();
  }
  if ( v14 != -1 )
  {
    v15 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
            &v28,
            (char *)this + 48);
    win_dox::CreateInstanceFromInner<IStream,win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>>(
      &v26,
      v15);
    v18 = (win_dox::Stream *)operator new(0x10u, v16, v17);
    v19 = v18;
    *(_QWORD *)&v27 = v18;
    if ( v18 )
    {
      win_dox::Stream::Stream(v18, (const struct Stream *)&v26);
      *((_BYTE *)v19 + 8) = 1;
    }
    else
    {
      v19 = 0;
    }
    win_scope::scope<win_dox::ByteReceiverOnStream *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::ByteReceiverOnStream *,win_scope::const_policies<win_scope::shared_policies>>(
      v32,
      v19);
    v27 = 0;
    v20 = v32[0];
    v21 = v32[1];
    if ( v32[0] )
    {
      win_scope::counted_strong_weak_base::AddRef(v32[0]);
      *(_QWORD *)&v27 = v20;
      *((_QWORD *)&v27 + 1) = v21;
    }
    win_dox::CreateInstanceFromInner<IByteReceiver,win_scope::scope<win_dox::ByteReceiverOnStream *,win_scope::const_policies<win_scope::shared_policies>>>(
      v36,
      &v27);
    Bytes = win_dox::OpcPartContent::GetBytes((char *)this + 24, &v28);
    v23 = win_dox::CreateSenderBase<IByteCollection>::CreateSender(Bytes, &v30);
    win_dox::StartSendBase<IByteSender>::StartSend<win_dox::ByteReceiver>(v23, v36);
    v30 = &win_dox::OpcRelationshipSender::`vftable';
    if ( v31 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      v31 = 0;
    }
    v28 = &win_dox::OpcRelationshipSender::`vftable';
    if ( v29 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    win_dox::ByteReceiver::~ByteReceiver((win_dox::ByteReceiver *)v36);
    if ( v20 && v21 )
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(v32);
    if ( v26 )
      (*(void (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
  }
  v24 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
          &v28,
          (char *)this + 48);
  win_dox::OpcPartContentStream::SendNotifications(this, v24);
  if ( v8 )
    win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::value_const<void *,-1>>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::close<void *>(&v33);
}

```

## disassembly

```asm
0x180052f98  mov     rax, rsp
0x180052f9b  push    rbp
0x180052f9c  push    rdi
0x180052f9d  push    r12
0x180052f9f  push    r14
0x180052fa1  push    r15
0x180052fa3  lea     rbp, [rax-4B8h]
0x180052faa  sub     rsp, 590h
0x180052fb1  mov     [rbp+4B0h+var_518], 0FFFFFFFFFFFFFFFEh
0x180052fb9  mov     [rax+10h], rbx
0x180052fbd  mov     [rax+18h], rsi
0x180052fc1  mov     rax, cs:__security_cookie
0x180052fc8  xor     rax, rsp
0x180052fcb  mov     [rbp+4B0h+var_30], rax
0x180052fd2  mov     r15, rcx
0x180052fd5  lea     rcx, [rbp+4B0h+var_4F8]
0x180052fd9  call    ?CreateTemporaryFileName@win_musl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_musl::CreateTemporaryFileName(void)
0x180052fde  nop
0x180052fdf  lea     rcx, [rax+8]
0x180052fe3  cmp     qword ptr [rax+20h], 8
0x180052fe8  jb      short loc_180052FED
0x180052fea  mov     rcx, [rcx]; lpFileName
0x180052fed  mov     [rsp+5B0h+hTemplateFile], 0; hTemplateFile
0x180052ff6  mov     [rsp+5B0h+dwFlagsAndAttributes], 4000100h; dwFlagsAndAttributes
0x180052ffe  mov     r14d, 1
0x180053004  mov     [rsp+5B0h+dwCreationDisposition], r14d; dwCreationDisposition
0x180053009  xor     r9d, r9d; lpSecurityAttributes
0x18005300c  xor     r8d, r8d; dwShareMode
0x18005300f  mov     edx, 0C0000000h; dwDesiredAccess
0x180053014  call    cs:__imp_CreateFileW
0x18005301a  mov     rdx, rax
0x18005301d  lea     rcx, [rbp+4B0h+var_528]
0x180053021  call    ??0?$scope@PEAXU?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@U?$types_6@U?$close_function@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@win_scope@@Uconvert_forbidden@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@U?$value_const@PEAX$0?0@win_scope@@@win_scope@@Usafe_types_detach_forbidden@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@PEAX@Z; win_scope::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::value_const<void *,-1>>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::value_const<void *,-1>>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>(void *)
0x180053026  nop
0x180053027  cmp     [rbp+4B0h+var_4D8], 8
0x18005302c  jb      short loc_180053037
0x18005302e  mov     rcx, [rbp+4B0h+Block]; Block
0x180053032  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180053037  mov     [rbp+4B0h+var_4D8], 7
0x18005303f  mov     [rbp+4B0h+var_4E0], 0
0x180053047  xor     eax, eax
0x180053049  mov     word ptr [rbp+4B0h+Block], ax
0x18005304d  mov     rdi, [rbp+4B0h+var_528]
0x180053051  test    rdi, rdi
0x180053054  jz      loc_1800532A8
0x18005305a  mov     rbx, [rbp+4B0h+var_520]
0x18005305e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180053062  cmp     rbx, rsi
0x180053065  jz      loc_1800532A8
0x18005306b  lea     ecx, [rax+20h]; unsigned __int64
0x18005306e  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x180053073  mov     rdx, rax
0x180053076  mov     qword ptr [rsp+5B0h+var_570], rax
0x18005307b  test    rax, rax
0x18005307e  jz      short loc_1800530A9
0x180053080  mov     qword ptr [rax], 0
0x180053087  mov     qword ptr [rax+8], 0
0x18005308f  mov     [rax+10h], rsi
0x180053093  mov     rcx, rdi; this
0x180053096  call    ?AddRef@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::AddRef(void)
0x18005309b  mov     [rdx+8], rdi
0x18005309f  mov     [rdx+10h], rbx
0x1800530a3  mov     [rdx+18h], r14d
0x1800530a7  jmp     short loc_1800530AB
0x1800530a9  xor     edx, edx
0x1800530ab  lea     rcx, [rsp+5B0h+var_570+8]
0x1800530b0  call    ??0?$scope@PEAVStreamOnFileHandle@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAVStreamOnFileHandle@win_dox@@@Z; win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>(win_dox::StreamOnFileHandle *)
0x1800530b5  lea     r14, [r15+30h]
0x1800530b9  movups  xmm1, xmmword ptr [rax]
0x1800530bc  movups  xmm0, xmmword ptr [r14]
0x1800530c0  movdqu  xmmword ptr [rax], xmm0
0x1800530c4  movdqu  xmmword ptr [r14], xmm1
0x1800530c9  cmp     [rsp+5B0h+var_560], 0
0x1800530cf  jz      short loc_1800530E4
0x1800530d1  cmp     qword ptr [rsp+5B0h+var_570+8], 0
0x1800530d7  jz      short loc_1800530E4
0x1800530d9  lea     rcx, [rsp+5B0h+var_570+8]
0x1800530de  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x1800530e3  nop
0x1800530e4  lea     rdx, [r15+18h]
0x1800530e8  lea     rcx, [rsp+5B0h+var_570]
0x1800530ed  call    ??0?$scope@PEAVContainerSender@consumption@win_musl@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>> const &)
0x1800530f2  mov     ebx, esi
0x1800530f4  mov     rcx, qword ptr [rsp+5B0h+var_570]
0x1800530f9  test    rcx, rcx
0x1800530fc  cmovnz  ebx, cs:dword_1801C4EA8
0x180053103  jz      short loc_180053112
0x180053105  mov     rax, [rcx]
0x180053108  mov     rax, [rax+10h]
0x18005310c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053111  nop
0x180053112  cmp     ebx, esi
0x180053114  jz      loc_180053255
0x18005311a  mov     rdx, r14
0x18005311d  lea     rcx, [rsp+5B0h+var_558]
0x180053122  call    ??0?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> const &)
0x180053127  mov     rdx, rax
0x18005312a  lea     rcx, [rsp+5B0h+var_570]
0x18005312f  call    ??$CreateInstanceFromInner@UIStream@@V?$scope@PEAVStreamOnFileHandle@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@win_dox@@YA?AVStream@0@V?$scope@PEAVStreamOnFileHandle@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::CreateInstanceFromInner<IStream,win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>>(win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>)
0x180053134  nop
0x180053135  mov     ecx, 10h; unsigned __int64
0x18005313a  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x18005313f  mov     rbx, rax
0x180053142  mov     qword ptr [rsp+5B0h+var_570+8], rax
0x180053147  test    rax, rax
0x18005314a  jz      short loc_18005315F
0x18005314c  lea     rdx, [rsp+5B0h+var_570]; struct Stream *
0x180053151  mov     rcx, rax; this
0x180053154  call    ??0Stream@win_dox@@QEAA@AEBV01@@Z; win_dox::Stream::Stream(win_dox::Stream const &)
0x180053159  mov     byte ptr [rbx+8], 1
0x18005315d  jmp     short loc_180053161
0x18005315f  xor     ebx, ebx
0x180053161  mov     rdx, rbx
0x180053164  lea     rcx, [rsp+5B0h+var_538]
0x180053169  call    ??0?$scope@PEAVByteReceiverOnStream@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAVByteReceiverOnStream@win_dox@@@Z; win_scope::scope<win_dox::ByteReceiverOnStream *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::ByteReceiverOnStream *,win_scope::const_policies<win_scope::shared_policies>>(win_dox::ByteReceiverOnStream *)
0x18005316e  nop
0x18005316f  xorps   xmm0, xmm0
0x180053172  movdqu  [rsp+5B0h+var_570+8], xmm0
0x180053178  mov     rbx, [rsp+5B0h+var_538]
0x18005317d  mov     rsi, [rbp+4B0h+var_530]
0x180053181  test    rbx, rbx
0x180053184  jz      short loc_180053198
0x180053186  mov     rcx, rbx; this
0x180053189  call    ?AddRef@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::AddRef(void)
0x18005318e  mov     qword ptr [rsp+5B0h+var_570+8], rbx
0x180053193  mov     [rsp+5B0h+var_560], rsi
0x180053198  lea     rdx, [rsp+5B0h+var_570+8]
0x18005319d  lea     rcx, [rbp+4B0h+var_510]
0x1800531a1  call    ??$CreateInstanceFromInner@UIByteReceiver@@V?$scope@PEAVByteReceiverOnStream@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@win_dox@@YA?AVByteReceiver@0@V?$scope@PEAVByteReceiverOnStream@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::CreateInstanceFromInner<IByteReceiver,win_scope::scope<win_dox::ByteReceiverOnStream *,win_scope::const_policies<win_scope::shared_policies>>>(win_scope::scope<win_dox::ByteReceiverOnStream *,win_scope::const_policies<win_scope::shared_policies>>)
0x1800531a6  nop
0x1800531a7  lea     rdx, [rsp+5B0h+var_558]
0x1800531ac  lea     rcx, [r15+18h]
0x1800531b0  call    ?GetBytes@OpcPartContent@win_dox@@QEBA?AVByteCollection@2@XZ; win_dox::OpcPartContent::GetBytes(void)
0x1800531b5  nop
0x1800531b6  lea     rdx, [rsp+5B0h+var_548]
0x1800531bb  mov     rcx, rax
0x1800531be  call    ?CreateSender@?$CreateSenderBase@UIByteCollection@@@win_dox@@QEBA?AVByteSender@2@XZ; win_dox::CreateSenderBase<IByteCollection>::CreateSender(void)
0x1800531c3  nop
0x1800531c4  lea     rdx, [rbp+4B0h+var_510]
0x1800531c8  mov     rcx, rax
0x1800531cb  call    ??$StartSend@VByteReceiver@win_dox@@@?$StartSendBase@UIByteSender@@@win_dox@@QEAAXAEAVByteReceiver@1@@Z; win_dox::StartSendBase<IByteSender>::StartSend<win_dox::ByteReceiver>(win_dox::ByteReceiver &)
0x1800531d0  nop
0x1800531d1  lea     rax, ??_7OpcRelationshipSender@win_dox@@6B@; const win_dox::OpcRelationshipSender::`vftable'
0x1800531d8  mov     [rsp+5B0h+var_548], rax
0x1800531dd  mov     rcx, [rsp+5B0h+var_540]
0x1800531e2  test    rcx, rcx
0x1800531e5  jz      short loc_1800531FC
0x1800531e7  mov     rax, [rcx]
0x1800531ea  mov     rax, [rax+10h]
0x1800531ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800531f3  mov     [rsp+5B0h+var_540], 0
0x1800531fc  lea     rax, ??_7OpcRelationshipSender@win_dox@@6B@; const win_dox::OpcRelationshipSender::`vftable'
0x180053203  mov     [rsp+5B0h+var_558], rax
0x180053208  mov     rcx, [rsp+5B0h+var_550]
0x18005320d  test    rcx, rcx
0x180053210  jz      short loc_18005321F
0x180053212  mov     rax, [rcx]
0x180053215  mov     rax, [rax+10h]
0x180053219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005321e  nop
0x18005321f  lea     rcx, [rbp+4B0h+var_510]; this
0x180053223  call    ??1ByteReceiver@win_dox@@UEAA@XZ; win_dox::ByteReceiver::~ByteReceiver(void)
0x180053228  nop
0x180053229  test    rbx, rbx
0x18005322c  jz      short loc_18005323E
0x18005322e  test    rsi, rsi
0x180053231  jz      short loc_18005323E
0x180053233  lea     rcx, [rsp+5B0h+var_538]
0x180053238  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18005323d  nop
0x18005323e  mov     rcx, qword ptr [rsp+5B0h+var_570]
0x180053243  test    rcx, rcx
0x180053246  jz      short loc_180053255
0x180053248  mov     rax, [rcx]
0x18005324b  mov     rax, [rax+10h]
0x18005324f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053254  nop
0x180053255  mov     rdx, r14
0x180053258  lea     rcx, [rsp+5B0h+var_558]
0x18005325d  call    ??0?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> const &)
0x180053262  mov     rdx, rax
0x180053265  mov     rcx, r15
0x180053268  call    ?SendNotifications@OpcPartContentStream@win_dox@@AEAAXV?$scope@PEAVStreamOnFileHandle@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::OpcPartContentStream::SendNotifications(win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>)
0x18005326d  nop
0x18005326e  test    rdi, rdi
0x180053271  jz      short loc_18005327D
0x180053273  lea     rcx, [rbp+4B0h+var_528]
0x180053277  call    ??$close@PEAX@?$counted_strong@U?$const_policies@U?$types_6@U?$close_function@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@win_scope@@Uconvert_forbidden@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@U?$value_const@PEAX$0?0@win_scope@@@win_scope@@Usafe_types_detach_forbidden@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAX@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::value_const<void *,-1>>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::close<void *>(win_scope::counted_store<void *> *)
0x18005327c  nop
0x18005327d  mov     rcx, [rbp+4B0h+var_30]
0x180053284  xor     rcx, rsp; StackCookie
0x180053287  call    __security_check_cookie
0x18005328c  lea     r11, [rsp+5B0h+var_20]
0x180053294  mov     rbx, [r11+38h]
0x180053298  mov     rsi, [r11+40h]
0x18005329c  mov     rsp, r11
0x18005329f  pop     r15
0x1800532a1  pop     r14
0x1800532a3  pop     r12
0x1800532a5  pop     rdi
0x1800532a6  pop     rbp
0x1800532a7  retn
0x1800532a8  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1800532ad  nop
0x1800532ae  mov     ebx, eax
0x1800532b0  xor     edx, edx; Val
0x1800532b2  mov     r8d, 400h; Size
0x1800532b8  lea     rcx, [rbp+4B0h+var_430]; void *
0x1800532bf  call    memset_0
0x1800532c4  mov     r9d, ebx
0x1800532c7  lea     r8, aCallToCreatefi; "Call to ::CreateFile failed with HResul"...
0x1800532ce  mov     edx, 200h; unsigned __int64
0x1800532d3  lea     rcx, [rbp+4B0h+var_430]; wchar_t *
0x1800532da  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800532df  lea     rax, [rbp+4B0h+var_430]
0x1800532e6  mov     [rsp+5B0h+hTemplateFile], rax; struct win_musl::TStringEllipseBase *
0x1800532eb  mov     [rsp+5B0h+dwFlagsAndAttributes], ebx; unsigned int
0x1800532ef  mov     [rsp+5B0h+dwCreationDisposition], 18Bh; unsigned int
0x1800532f7  lea     r9, word_180139126
0x1800532fe  lea     r8, aNoFilename; "(no filename)"
0x180053305  lea     rcx, [rbp+4B0h+pExceptionObject]; this
0x180053309  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18005330e  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180053315  lea     rcx, [rbp+4B0h+pExceptionObject]; pExceptionObject
0x180053319  call    _CxxThrowException_0
```

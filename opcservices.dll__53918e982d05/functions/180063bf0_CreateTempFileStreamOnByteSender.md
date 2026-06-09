# CreateTempFileStreamOnByteSender

- ea: `0x180063bf0`
- end: `0x18006434c`
- name: `CreateTempFileStreamOnByteSender`
- size: `1884`
- prototype: `__int64 __fastcall(__int64, __int64, win_dox::Stream **)`
- caller_count: `0`
- callee_count: `27`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000531c`
- `0x18000f9a0`
- `0x180012468`
- `0x180015660`
- `0x180017320`
- `0x18002b6c8`
- `0x18002bad0`
- `0x18002ca40`
- `0x18002cf10`
- `0x18002db70`
- `0x180060c90`
- `0x1800629f8`
- `0x180063bf0`
- `0x18006458c`
- `0x180064624`
- `0x1800646e8`
- `0x1800652d0`
- `0x180065458`
- `0x180065510`
- `0x18006554c`
- `0x180084010`
- `0x18008f584`
- `0x1800cd1c4`
- `0x1800cd6fc`
- `0x1800d6354`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180063cd8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180063cd8`

## string_xrefs

- `0x180063dc6`: `Call to ::CreateFile failed with HResult 0x%X.`
- `0x1800641c2`: `CreateTempFileStreamOnByteSender parameter rootFolder cannot be NULL`
- `0x180064232`: `CreateTempFileStreamOnByteSender parameter byteSender cannot be NULL`
- `0x1800642a2`: `CreateTempFileStreamOnByteSender parameter stream cannot be NULL`

## pseudocode

```c
__int64 __fastcall CreateTempFileStreamOnByteSender(__int64 a1, __int64 a2, win_dox::Stream **a3)
{
  __int64 v6; // rdi
  __int64 TemporaryFileName; // rax
  const WCHAR *v8; // rcx
  HANDLE FileW; // rdx
  const char *v10; // rdx
  win_musl::detail *v11; // rcx
  unsigned int v12; // r8d
  unsigned int LastErrorAsFailHR; // ebx
  win_musl *v14; // rcx
  _QWORD *v16; // rax
  _QWORD *v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rdx
  const char *v22; // rdx
  unsigned int v23; // r8d
  win_dox::Stream *v24; // rax
  win_dox::Stream *v25; // rbx
  __int64 v26; // rcx
  __int64 v27; // rdx
  const char *v28; // rdx
  unsigned int v29; // r8d
  _QWORD *v30; // rax
  _QWORD *v31; // r8
  __int64 v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rax
  win_musl::Formatter *v37; // rcx
  struct win_musl::TStringEllipseBase *v38; // rax
  win_musl::Formatter *v39; // rax
  struct win_musl::TStringEllipseBase *v40; // rax
  win_musl::Formatter *v41; // rax
  struct win_musl::TStringEllipseBase *v42; // rax
  win_dox::Stream *v43; // [rsp+40h] [rbp-858h] BYREF
  __int64 v44; // [rsp+48h] [rbp-850h] BYREF
  __int128 v45; // [rsp+50h] [rbp-848h] BYREF
  __int64 v46; // [rsp+60h] [rbp-838h] BYREF
  win_scope::counted_strong_weak_base *v47; // [rsp+68h] [rbp-830h] BYREF
  __int64 v48; // [rsp+70h] [rbp-828h]
  __int128 v49; // [rsp+78h] [rbp-820h] BYREF
  win_musl *v50; // [rsp+88h] [rbp-810h] BYREF
  win_scope::counted_strong_weak_base *v51; // [rsp+90h] [rbp-808h] BYREF
  __int64 v52; // [rsp+98h] [rbp-800h]
  win_scope::counted_strong_weak_base *v53; // [rsp+A0h] [rbp-7F8h] BYREF
  __int64 v54; // [rsp+A8h] [rbp-7F0h]
  win_scope::counted_strong_weak_base *v55; // [rsp+B0h] [rbp-7E8h] BYREF
  __int64 v56; // [rsp+B8h] [rbp-7E0h]
  __int64 v57; // [rsp+C0h] [rbp-7D8h]
  _BYTE v58[24]; // [rsp+C8h] [rbp-7D0h] BYREF
  char v59[8]; // [rsp+E0h] [rbp-7B8h] BYREF
  void *v60; // [rsp+E8h] [rbp-7B0h]
  __int64 v61; // [rsp+F8h] [rbp-7A0h]
  unsigned __int64 v62; // [rsp+100h] [rbp-798h]
  char v63[8]; // [rsp+108h] [rbp-790h] BYREF
  void *v64; // [rsp+110h] [rbp-788h]
  __int64 v65; // [rsp+120h] [rbp-778h]
  unsigned __int64 v66; // [rsp+128h] [rbp-770h]
  char v67[8]; // [rsp+130h] [rbp-768h] BYREF
  void *v68; // [rsp+138h] [rbp-760h]
  __int64 v69; // [rsp+148h] [rbp-750h]
  unsigned __int64 v70; // [rsp+150h] [rbp-748h]
  char v71[8]; // [rsp+158h] [rbp-740h] BYREF
  void *Block; // [rsp+160h] [rbp-738h]
  __int64 v73; // [rsp+170h] [rbp-728h]
  unsigned __int64 v74; // [rsp+178h] [rbp-720h]
  _BYTE v75[96]; // [rsp+180h] [rbp-718h] BYREF
  _BYTE v76[160]; // [rsp+1E0h] [rbp-6B8h] BYREF
  _BYTE v77[160]; // [rsp+280h] [rbp-618h] BYREF
  _BYTE v78[160]; // [rsp+320h] [rbp-578h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+3C0h] [rbp-4D8h] BYREF
  wchar_t v80[512]; // [rsp+460h] [rbp-438h] BYREF

  v57 = -2;
  try
  {
    if ( !a1 )
    {
      std::wstring::wstring(v59, L"CreateTempFileStreamOnByteSender parameter rootFolder cannot be NULL");
      v37 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v75, v59);
      v38 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v37);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v76,
        0x240u,
        0x80004003,
        v38);
      throw (SplException::THResultException *)v76;
    }
    if ( !a2 )
    {
      std::wstring::wstring(v59, L"CreateTempFileStreamOnByteSender parameter byteSender cannot be NULL");
      v39 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v75, v59);
      v40 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v39);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v77,
        0x247u,
        0x80004003,
        v40);
      throw (SplException::THResultException *)v77;
    }
    if ( !a3 )
    {
      std::wstring::wstring(v59, L"CreateTempFileStreamOnByteSender parameter stream cannot be NULL");
      v41 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v75, v59);
      v42 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v41);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v78,
        0x24Eu,
        0x80004003,
        v42);
      throw (SplException::THResultException *)v78;
    }
    v6 = std::wstring::wstring(v59, L".tmp");
    std::wstring::wstring(v67, L"APPX");
    std::wstring::wstring(v63, a1);
    TemporaryFileName = win_musl::CreateTemporaryFileName(v71, v63, v67, v6);
    v8 = (const WCHAR *)(TemporaryFileName + 8);
    if ( *(_QWORD *)(TemporaryFileName + 32) >= 8u )
      v8 = *(const WCHAR **)v8;
    FileW = CreateFileW(v8, 0xC0000000, 0, 0, 2u, 0x4000100u, 0);
    win_scope::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::value_const<void *,-1>>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::value_const<void *,-1>>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>(
      &v47,
      FileW);
    if ( v74 >= 8 )
      operator delete(Block);
    v74 = 7;
    v73 = 0;
    LOWORD(Block) = 0;
    if ( v66 >= 8 )
      operator delete(v64);
    v66 = 7;
    v65 = 0;
    LOWORD(v64) = 0;
    if ( v70 >= 8 )
      operator delete(v68);
    v70 = 7;
    v69 = 0;
    LOWORD(v68) = 0;
    if ( v62 >= 8 )
      operator delete(v60);
    v62 = 7;
    v61 = 0;
    LOWORD(v60) = 0;
    if ( !v47 || v48 == -1 )
    {
      LastErrorAsFailHR = win_musl::detail::GetLastErrorAsFailHR(v11);
      memset_0(v80, 0, sizeof(v80));
      StringCchPrintfW(v80, 0x200u, L"Call to ::CreateFile failed with HResult 0x%X.", LastErrorAsFailHR);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x25Bu,
        LastErrorAsFailHR,
        (struct win_musl::TStringEllipseBase *)v80);
      throw (SplException::THResultException *)pExceptionObject;
    }
    v16 = operator new(0x20u, v10, v12);
    v17 = v16;
    v43 = (win_dox::Stream *)v16;
    if ( v16 )
    {
      *v16 = 0;
      v16[1] = 0;
      v16[2] = -1;
      if ( v47 )
      {
        win_scope::counted_strong_weak_base::AddRef(v47);
        v17[1] = v18;
        v17[2] = v19;
      }
      *((_DWORD *)v17 + 6) = 2;
    }
    else
    {
      v17 = 0;
    }
    win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>(
      &v55,
      v17);
    v45 = 0;
    if ( v55 )
    {
      win_scope::counted_strong_weak_base::AddRef(v55);
      *(_QWORD *)&v45 = v20;
      *((_QWORD *)&v45 + 1) = v21;
    }
    win_dox::CreateInstanceFromInner<IStream,win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>>(
      &v50,
      &v45);
    v24 = (win_dox::Stream *)operator new(0x10u, v22, v23);
    v25 = v24;
    v43 = v24;
    if ( v24 )
    {
      win_dox::Stream::Stream(v24, (const struct Stream *)&v50);
      *((_BYTE *)v25 + 8) = 1;
    }
    else
    {
      v25 = 0;
    }
    win_scope::scope<win_dox::ByteReceiverOnStream *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::ByteReceiverOnStream *,win_scope::const_policies<win_scope::shared_policies>>(
      &v53,
      v25);
    v49 = 0;
    if ( v53 )
    {
      win_scope::counted_strong_weak_base::AddRef(v53);
      *(_QWORD *)&v49 = v26;
      *((_QWORD *)&v49 + 1) = v27;
    }
    win_dox::CreateInstanceFromInner<IByteReceiver,win_scope::scope<win_dox::ByteReceiverOnStream *,win_scope::const_policies<win_scope::shared_policies>>>(
      v58,
      &v49);
    *(_QWORD *)&v45 = &win_dox::OpcRelationshipSender::`vftable';
    v46 = a2;
    *((_QWORD *)&v45 + 1) = 0;
    win_scope::detail::scope_helper<IByteSender *,win_scope::const_policies<win_scope::com_policies>>::construct_acquire<IByteSender *,win_scope::const_policies<win_scope::com_policies>,IByteSender *>(
      (char *)&v45 + 8,
      &v46);
    *(_QWORD *)&v45 = &win_dox::OpcRelationshipCollection::`vftable';
    win_dox::StartSendBase<IByteSender>::StartSend<win_dox::ByteReceiver>(&v45, v58);
    v30 = operator new(0x20u, v28, v29);
    v31 = v30;
    v43 = (win_dox::Stream *)v30;
    if ( v30 )
    {
      *v30 = 0;
      v30[1] = 0;
      v30[2] = -1;
      if ( v47 )
      {
        win_scope::counted_strong_weak_base::AddRef(v47);
        v31[1] = v32;
        v31[2] = v33;
      }
      *((_DWORD *)v31 + 6) = 0;
    }
    else
    {
      v31 = 0;
    }
    win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>(
      &v51,
      v31);
    v49 = 0;
    if ( v51 )
    {
      win_scope::counted_strong_weak_base::AddRef(v51);
      *(_QWORD *)&v49 = v34;
      *((_QWORD *)&v49 + 1) = v35;
    }
    win_dox::CreateInstanceFromInner<IStream,win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>>(
      &v44,
      &v49);
    v36 = win_dox::Stream::Stream((win_dox::Stream *)&v46, (const struct Stream *)&v44);
    win_dox::to_interface_with_create<IStream>::resolve<win_dox::Stream>(&v43, v36);
    *a3 = v43;
    if ( v44 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
      v44 = 0;
    }
    if ( v52 && v51 )
    {
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v51);
      v51 = 0;
      v52 = 0;
    }
    if ( *((_QWORD *)&v45 + 1) )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v45 + 1) + 16LL))(*((_QWORD *)&v45 + 1));
    win_dox::ByteReceiver::~ByteReceiver((win_dox::ByteReceiver *)v58);
    if ( v54 && v53 )
    {
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v53);
      v53 = 0;
      v54 = 0;
    }
    v14 = v50;
    if ( v50 )
    {
      (*(void (__fastcall **)(win_musl *))(*(_QWORD *)v50 + 16LL))(v50);
      v50 = 0;
    }
    if ( v56 && v55 )
    {
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v55);
      v55 = 0;
      v56 = 0;
    }
    if ( v48 != -1 && v47 )
      win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::value_const<void *,-1>>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::close<void *>(&v47);
  }
  catch ( ... )
  {
    win_musl::detail_process_errors(v14);
  }
  return 0;
}

```

## disassembly

```asm
0x180063bf0  mov     r11, rsp
0x180063bf3  push    rsi
0x180063bf4  push    rdi
0x180063bf5  push    r12
0x180063bf7  push    r14
0x180063bf9  push    r15
0x180063bfb  sub     rsp, 870h
0x180063c02  mov     qword ptr [r11-7D8h], 0FFFFFFFFFFFFFFFEh
0x180063c0d  mov     [r11+10h], rbx
0x180063c11  mov     rax, cs:__security_cookie
0x180063c18  xor     rax, rsp
0x180063c1b  mov     [rsp+898h+var_38], rax
0x180063c23  mov     r14, r8
0x180063c26  mov     rsi, rdx
0x180063c29  mov     rbx, rcx
0x180063c2c  xor     r12d, r12d
0x180063c2f  mov     r15d, r12d
0x180063c32  lea     rcx, [r11-7B8h]
0x180063c39  test    rbx, rbx
0x180063c3c  jz      loc_1800641C2
0x180063c42  test    rdx, rdx
0x180063c45  jz      loc_180064232
0x180063c4b  test    r8, r8
0x180063c4e  jz      loc_1800642A2
0x180063c54  lea     rdx, aTmp; ".tmp"
0x180063c5b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180063c60  mov     rdi, rax
0x180063c63  lea     rdx, aAppx; "APPX"
0x180063c6a  lea     rcx, [rsp+898h+var_768]
0x180063c72  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180063c77  nop
0x180063c78  mov     rdx, rbx
0x180063c7b  lea     rcx, [rsp+898h+var_790]
0x180063c83  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180063c88  nop
0x180063c89  mov     r9, rdi
0x180063c8c  lea     r8, [rsp+898h+var_768]
0x180063c94  lea     rdx, [rsp+898h+var_790]
0x180063c9c  lea     rcx, [rsp+898h+var_740]
0x180063ca4  call    ?CreateTemporaryFileName@win_musl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBV23@00@Z; win_musl::CreateTemporaryFileName(std::wstring const &,std::wstring const &,std::wstring const &)
0x180063ca9  nop
0x180063caa  lea     rcx, [rax+8]
0x180063cae  cmp     qword ptr [rax+20h], 8
0x180063cb3  jb      short loc_180063CB8
0x180063cb5  mov     rcx, [rcx]; lpFileName
0x180063cb8  mov     [rsp+898h+hTemplateFile], r12; hTemplateFile
0x180063cbd  mov     [rsp+898h+dwFlagsAndAttributes], 4000100h; dwFlagsAndAttributes
0x180063cc5  mov     [rsp+898h+dwCreationDisposition], 2; dwCreationDisposition
0x180063ccd  xor     r9d, r9d; lpSecurityAttributes
0x180063cd0  xor     r8d, r8d; dwShareMode
0x180063cd3  mov     edx, 0C0000000h; dwDesiredAccess
0x180063cd8  call    cs:__imp_CreateFileW
0x180063cde  mov     rdx, rax
0x180063ce1  lea     rcx, [rsp+898h+var_830]
0x180063ce6  call    ??0?$scope@PEAXU?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@U?$types_6@U?$close_function@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@win_scope@@Uconvert_forbidden@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@U?$value_const@PEAX$0?0@win_scope@@@win_scope@@Usafe_types_detach_forbidden@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@PEAX@Z; win_scope::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::value_const<void *,-1>>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::value_const<void *,-1>>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>(void *)
0x180063ceb  nop
0x180063cec  cmp     [rsp+898h+var_720], 8
0x180063cf5  jnb     loc_180063E28
0x180063cfb  mov     ebx, 7
0x180063d00  mov     [rsp+898h+var_720], rbx
0x180063d08  mov     [rsp+898h+var_728], r12
0x180063d10  mov     word ptr [rsp+898h+Block], r12w
0x180063d19  cmp     [rsp+898h+var_770], 8
0x180063d22  jnb     loc_180063E3A
0x180063d28  mov     [rsp+898h+var_770], rbx
0x180063d30  mov     [rsp+898h+var_778], r12
0x180063d38  mov     word ptr [rsp+898h+var_788], r12w
0x180063d41  cmp     [rsp+898h+var_748], 8
0x180063d4a  jnb     loc_180063E4C
0x180063d50  mov     [rsp+898h+var_748], rbx
0x180063d58  mov     [rsp+898h+var_750], r12
0x180063d60  mov     word ptr [rsp+898h+var_760], r12w
0x180063d69  cmp     [rsp+898h+var_798], 8
0x180063d72  jnb     loc_180063E5E
0x180063d78  mov     [rsp+898h+var_798], rbx
0x180063d80  mov     [rsp+898h+var_7A0], r12
0x180063d88  mov     word ptr [rsp+898h+var_7B0], r12w
0x180063d91  cmp     [rsp+898h+var_830], r12
0x180063d96  jz      short loc_180063DA7
0x180063d98  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180063d9c  cmp     [rsp+898h+var_828], rdi
0x180063da1  jnz     loc_180063F23
0x180063da7  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x180063dac  mov     ebx, eax
0x180063dae  xor     edx, edx; Val
0x180063db0  mov     r8d, 400h; Size
0x180063db6  lea     rcx, [rsp+898h+var_438]; void *
0x180063dbe  call    memset_0
0x180063dc3  mov     r9d, ebx
0x180063dc6  lea     r8, aCallToCreatefi; "Call to ::CreateFile failed with HResul"...
0x180063dcd  mov     edx, 200h; unsigned __int64
0x180063dd2  lea     rcx, [rsp+898h+var_438]; wchar_t *
0x180063dda  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180063ddf  lea     rax, [rsp+898h+var_438]
0x180063de7  mov     [rsp+898h+hTemplateFile], rax; struct win_musl::TStringEllipseBase *
0x180063dec  mov     [rsp+898h+dwFlagsAndAttributes], ebx; unsigned int
0x180063df0  mov     [rsp+898h+dwCreationDisposition], 25Bh; unsigned int
0x180063df8  lea     r9, word_180139126
0x180063dff  lea     r8, aNoFilename; "(no filename)"
0x180063e06  lea     rcx, [rsp+898h+pExceptionObject]; this
0x180063e0e  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180063e13  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180063e1a  lea     rcx, [rsp+898h+pExceptionObject]; pExceptionObject
0x180063e22  call    _CxxThrowException_0
0x180063e28  mov     rcx, [rsp+898h+Block]; Block
0x180063e30  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180063e35  jmp     loc_180063CFB
0x180063e3a  mov     rcx, [rsp+898h+var_788]; Block
0x180063e42  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180063e47  jmp     loc_180063D28
0x180063e4c  mov     rcx, [rsp+898h+var_760]; Block
0x180063e54  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180063e59  jmp     loc_180063D50
0x180063e5e  mov     rcx, [rsp+898h+var_7B0]; Block
0x180063e66  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180063e6b  jmp     loc_180063D78
0x180063e70  lea     rcx, [rsp+898h+var_7D0]; this
0x180063e78  call    ??1ByteReceiver@win_dox@@UEAA@XZ; win_dox::ByteReceiver::~ByteReceiver(void)
0x180063e7d  nop
0x180063e7e  cmp     [rsp+898h+var_7F0], r12
0x180063e86  jnz     loc_180064312
0x180063e8c  mov     rcx, [rsp+898h+var_810]
0x180063e94  test    rcx, rcx
0x180063e97  jz      short loc_180063EAD
0x180063e99  mov     rax, [rcx]
0x180063e9c  mov     rax, [rax+10h]
0x180063ea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063ea5  mov     [rsp+898h+var_810], r12
0x180063ead  cmp     [rsp+898h+var_7E0], r12
0x180063eb5  jz      short loc_180063EDE
0x180063eb7  cmp     [rsp+898h+var_7E8], r12
0x180063ebf  jz      short loc_180063EDE
0x180063ec1  lea     rcx, [rsp+898h+var_7E8]
0x180063ec9  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x180063ece  mov     [rsp+898h+var_7E8], r12
0x180063ed6  mov     [rsp+898h+var_7E0], r12
0x180063ede  cmp     [rsp+898h+var_828], rdi
0x180063ee3  jnz     short loc_180063F10
0x180063ee5  mov     eax, r15d
0x180063ee8  mov     rcx, [rsp+898h+var_38]
0x180063ef0  xor     rcx, rsp; StackCookie
0x180063ef3  call    __security_check_cookie
0x180063ef8  mov     rbx, [rsp+898h+arg_8]
0x180063f00  add     rsp, 870h
0x180063f07  pop     r15
0x180063f09  pop     r14
0x180063f0b  pop     r12
0x180063f0d  pop     rdi
0x180063f0e  pop     rsi
0x180063f0f  retn
0x180063f10  cmp     [rsp+898h+var_830], r12
0x180063f15  jz      short loc_180063EE5
0x180063f17  lea     rcx, [rsp+898h+var_830]
0x180063f1c  call    ??$close@PEAX@?$counted_strong@U?$const_policies@U?$types_6@U?$close_function@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@win_scope@@Uconvert_forbidden@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@U?$value_const@PEAX$0?0@win_scope@@@win_scope@@Usafe_types_detach_forbidden@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAX@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::value_const<void *,-1>>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::close<void *>(win_scope::counted_store<void *> *)
0x180063f21  jmp     short loc_180063EE5
0x180063f23  mov     ecx, 20h ; ' '; unsigned __int64
0x180063f28  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x180063f2d  mov     r8, rax
0x180063f30  mov     [rsp+898h+var_858], rax
0x180063f35  test    rax, rax
0x180063f38  jz      loc_1800641BA
0x180063f3e  mov     [rax], r12
0x180063f41  mov     [rax+8], r12
0x180063f45  mov     [rax+10h], rdi
0x180063f49  mov     rcx, [rsp+898h+var_830]; this
0x180063f4e  test    rcx, rcx
0x180063f51  jz      short loc_180063F65
0x180063f53  mov     rdx, [rsp+898h+var_828]
0x180063f58  call    ?AddRef@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::AddRef(void)
0x180063f5d  mov     [r8+8], rcx
0x180063f61  mov     [r8+10h], rdx
0x180063f65  mov     dword ptr [r8+18h], 2
0x180063f6d  mov     rdx, r8
0x180063f70  lea     rcx, [rsp+898h+var_7E8]
0x180063f78  call    ??0?$scope@PEAVStreamOnFileHandle@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAVStreamOnFileHandle@win_dox@@@Z; win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>(win_dox::StreamOnFileHandle *)
0x180063f7d  nop
0x180063f7e  xorps   xmm0, xmm0
0x180063f81  movdqu  [rsp+898h+var_848], xmm0
0x180063f87  mov     rcx, [rsp+898h+var_7E8]; this
0x180063f8f  test    rcx, rcx
0x180063f92  jz      short loc_180063FAB
0x180063f94  mov     rdx, [rsp+898h+var_7E0]
0x180063f9c  call    ?AddRef@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::AddRef(void)
0x180063fa1  mov     qword ptr [rsp+898h+var_848], rcx
0x180063fa6  mov     qword ptr [rsp+898h+var_848+8], rdx
0x180063fab  lea     rdx, [rsp+898h+var_848]
0x180063fb0  lea     rcx, [rsp+898h+var_810]
0x180063fb8  call    ??$CreateInstanceFromInner@UIStream@@V?$scope@PEAVStreamOnFileHandle@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@win_dox@@YA?AVStream@0@V?$scope@PEAVStreamOnFileHandle@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::CreateInstanceFromInner<IStream,win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>>(win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>)
0x180063fbd  nop
0x180063fbe  mov     ecx, 10h; unsigned __int64
0x180063fc3  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x180063fc8  mov     rbx, rax
0x180063fcb  mov     [rsp+898h+var_858], rax
0x180063fd0  test    rax, rax
0x180063fd3  jz      loc_1800641AA
0x180063fd9  lea     rdx, [rsp+898h+var_810]; struct Stream *
0x180063fe1  mov     rcx, rax; this
0x180063fe4  call    ??0Stream@win_dox@@QEAA@AEBV01@@Z; win_dox::Stream::Stream(win_dox::Stream const &)
0x180063fe9  mov     byte ptr [rbx+8], 1
0x180063fed  mov     rdx, rbx
0x180063ff0  lea     rcx, [rsp+898h+var_7F8]
0x180063ff8  call    ??0?$scope@PEAVByteReceiverOnStream@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAVByteReceiverOnStream@win_dox@@@Z; win_scope::scope<win_dox::ByteReceiverOnStream *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::ByteReceiverOnStream *,win_scope::const_policies<win_scope::shared_policies>>(win_dox::ByteReceiverOnStream *)
0x180063ffd  nop
0x180063ffe  xorps   xmm0, xmm0
0x180064001  movdqu  [rsp+898h+var_820], xmm0
0x180064007  mov     rcx, [rsp+898h+var_7F8]; this
0x18006400f  test    rcx, rcx
0x180064012  jz      short loc_18006402E
0x180064014  mov     rdx, [rsp+898h+var_7F0]
0x18006401c  call    ?AddRef@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::AddRef(void)
0x180064021  mov     qword ptr [rsp+898h+var_820], rcx
0x180064026  mov     qword ptr [rsp+898h+var_820+8], rdx
0x18006402e  lea     rdx, [rsp+898h+var_820]
0x180064033  lea     rcx, [rsp+898h+var_7D0]
0x18006403b  call    ??$CreateInstanceFromInner@UIByteReceiver@@V?$scope@PEAVByteReceiverOnStream@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@win_dox@@YA?AVByteReceiver@0@V?$scope@PEAVByteReceiverOnStream@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::CreateInstanceFromInner<IByteReceiver,win_scope::scope<win_dox::ByteReceiverOnStream *,win_scope::const_policies<win_scope::shared_policies>>>(win_scope::scope<win_dox::ByteReceiverOnStream *,win_scope::const_policies<win_scope::shared_policies>>)
0x180064040  nop
0x180064041  lea     rax, ??_7OpcRelationshipSender@win_dox@@6B@; const win_dox::OpcRelationshipSender::`vftable'
0x180064048  mov     qword ptr [rsp+898h+var_848], rax
0x18006404d  mov     [rsp+898h+var_838], rsi
0x180064052  mov     qword ptr [rsp+898h+var_848+8], r12
0x180064057  lea     rdx, [rsp+898h+var_838]
0x18006405c  lea     rcx, [rsp+898h+var_848+8]
0x180064061  call    ??$construct_acquire@PEAUIByteSender@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@PEAU1@@?$scope_helper@PEAUIByteSender@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXPEAV?$scope@PEAUIByteSender@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@2@PEAPEAUIByteSender@@@Z; win_scope::detail::scope_helper<IByteSender *,win_scope::const_policies<win_scope::com_policies>>::construct_acquire<IByteSender *,win_scope::const_policies<win_scope::com_policies>,IByteSender *>(win_scope::scope<IByteSender *,win_scope::const_policies<win_scope::com_policies>> *,IByteSender * *)
0x180064066  lea     rax, ??_7OpcRelationshipCollection@win_dox@@6B@; const win_dox::OpcRelationshipCollection::`vftable'
0x18006406d  mov     qword ptr [rsp+898h+var_848], rax
0x180064072  lea     rdx, [rsp+898h+var_7D0]
0x18006407a  lea     rcx, [rsp+898h+var_848]
0x18006407f  call    ??$StartSend@VByteReceiver@win_dox@@@?$StartSendBase@UIByteSender@@@win_dox@@QEAAXAEAVByteReceiver@1@@Z; win_dox::StartSendBase<IByteSender>::StartSend<win_dox::ByteReceiver>(win_dox::ByteReceiver &)
0x180064084  mov     ecx, 20h ; ' '; unsigned __int64
0x180064089  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x18006408e  mov     r8, rax
0x180064091  mov     [rsp+898h+var_858], rax
0x180064096  test    rax, rax
0x180064099  jz      loc_1800641B2
0x18006409f  mov     [rax], r12
0x1800640a2  mov     [rax+8], r12
0x1800640a6  mov     [rax+10h], rdi
0x1800640aa  mov     rcx, [rsp+898h+var_830]; this
0x1800640af  test    rcx, rcx
0x1800640b2  jz      short loc_1800640C6
0x1800640b4  mov     rdx, [rsp+898h+var_828]
0x1800640b9  call    ?AddRef@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::AddRef(void)
0x1800640be  mov     [r8+8], rcx
0x1800640c2  mov     [r8+10h], rdx
0x1800640c6  mov     [r8+18h], r12d
0x1800640ca  mov     rdx, r8
0x1800640cd  lea     rcx, [rsp+898h+var_808]
0x1800640d5  call    ??0?$scope@PEAVStreamOnFileHandle@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAVStreamOnFileHandle@win_dox@@@Z; win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>(win_dox::StreamOnFileHandle *)
0x1800640da  nop
0x1800640db  xorps   xmm0, xmm0
0x1800640de  movdqu  [rsp+898h+var_820], xmm0
0x1800640e4  mov     rcx, [rsp+898h+var_808]; this
0x1800640ec  test    rcx, rcx
0x1800640ef  jz      short loc_18006410B
0x1800640f1  mov     rdx, [rsp+898h+var_800]
0x1800640f9  call    ?AddRef@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::AddRef(void)
0x1800640fe  mov     qword ptr [rsp+898h+var_820], rcx
0x180064103  mov     qword ptr [rsp+898h+var_820+8], rdx
0x18006410b  lea     rdx, [rsp+898h+var_820]
0x180064110  lea     rcx, [rsp+898h+var_850]
0x180064115  call    ??$CreateInstanceFromInner@UIStream@@V?$scope@PEAVStreamOnFileHandle@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@win_dox@@YA?AVStream@0@V?$scope@PEAVStreamOnFileHandle@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::CreateInstanceFromInner<IStream,win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>>(win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>)
0x18006411a  nop
0x18006411b  lea     rdx, [rsp+898h+var_850]; struct Stream *
0x180064120  lea     rcx, [rsp+898h+var_838]; this
0x180064125  call    ??0Stream@win_dox@@QEAA@AEBV01@@Z; win_dox::Stream::Stream(win_dox::Stream const &)
0x18006412a  mov     rdx, rax
0x18006412d  lea     rcx, [rsp+898h+var_858]
0x180064132  call    ??$resolve@VStream@win_dox@@@?$to_interface_with_create@UIStream@@@win_dox@@SA?AV?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@VStream@1@@Z; win_dox::to_interface_with_create<IStream>::resolve<win_dox::Stream>(win_dox::Stream)
0x180064137  mov     rax, [rsp+898h+var_858]
0x18006413c  mov     [r14], rax
0x18006413f  mov     rcx, [rsp+898h+var_850]
0x180064144  test    rcx, rcx
0x180064147  jz      short loc_18006415A
0x180064149  mov     rax, [rcx]
0x18006414c  mov     rax, [rax+10h]
0x180064150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064155  mov     [rsp+898h+var_850], r12
0x18006415a  cmp     [rsp+898h+var_800], r12
0x180064162  jz      short loc_18006418B
0x180064164  cmp     [rsp+898h+var_808], r12
0x18006416c  jz      short loc_18006418B
0x18006416e  lea     rcx, [rsp+898h+var_808]
0x180064176  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18006417b  mov     [rsp+898h+var_808], r12
0x180064183  mov     [rsp+898h+var_800], r12
0x18006418b  mov     rcx, qword ptr [rsp+898h+var_848+8]
0x180064190  test    rcx, rcx
0x180064193  jz      loc_180063E70
0x180064199  mov     rax, [rcx]
0x18006419c  mov     rax, [rax+10h]
0x1800641a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800641a5  jmp     loc_180063E70
0x1800641aa  mov     rbx, r12
0x1800641ad  jmp     loc_180063FED
0x1800641b2  mov     r8, r12
0x1800641b5  jmp     loc_1800640CA
0x1800641ba  mov     r8, r12
0x1800641bd  jmp     loc_180063F6D
0x1800641c2  lea     rdx, aCreatetempfile_2; "CreateTempFileStreamOnByteSender parame"...
0x1800641c9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
  ... truncated ...
```

# CreateLogOnAreaInternal(ushort const *,ushort const *,MdmLogCollectorOutputOption,void *)

- ea: `0x1800f9bb4`
- end: `0x1800fa3c2`
- name: `?CreateLogOnAreaInternal@@YAJPEBG0W4MdmLogCollectorOutputOption@@PEAX@Z`
- size: `2062`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, unsigned int, void *)`
- caller_count: `2`
- callee_count: `29`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f9b90`
- `0x1800fa3d0`

## callees

- `0x180019000`
- `0x180019024`
- `0x180019fc4`
- `0x1800e66dc`
- `0x1800ece5c`
- `0x1800ee878`
- `0x1800ef134`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800f89d8`
- `0x1800f8a0c`
- `0x1800f8aa0`
- `0x1800f9504`
- `0x1800f9558`
- `0x1800f9614`
- `0x1800f97d0`
- `0x1800f9a0c`
- `0x1800f9bb4`
- `0x1800faae0`
- `0x1800fad60`
- `0x180103ae0`
- `0x18010412c`
- `0x18010440c`
- `0x18010792c`
- `0x180108ae0`
- `0x180108be4`
- `0x18010b6d4`
- `0x18010e684`
- `0x180128e28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800fa010`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800fa049`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800fa010`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800fa049`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f9cbc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f9ccf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f9e51`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f9e64`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f9ee7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f9efa`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f9f7a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f9f8d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800fa1b5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800fa1c8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800fa2f8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800fa30b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800fa354`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800fa367`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f9cbc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f9ccf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f9e51`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f9e64`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f9ee7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f9efa`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f9f7a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f9f8d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800fa1b5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800fa1c8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800fa2f8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800fa30b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800fa354`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800fa367`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1800f9d7b`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1800f9d7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9e21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9e21`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800f9d5a`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800f9d5a`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800f9fe1`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800f9fe1`
- `DMCmnUtils!IsDesktopSku` at `0x1800f9d00`
- `DMCmnUtils!IsDesktopSku` at `0x1800f9d00`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x1800f9ffc`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x1800f9ffc`

## string_xrefs

- `0x1800f9c8f`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\dllmain.cpp`
- `0x1800f9eba`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\dllmain.cpp`
- `0x1800f9f4d`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\dllmain.cpp`
- `0x1800fa081`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\dllmain.cpp`
- `0x1800fa153`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\dllmain.cpp`
- `0x1800fa2cb`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\dllmain.cpp`
- `0x1800f9d9f`: `MDMDiagReport.xml`
- `0x1800f9e9d`: `%osdatadrive%\Public\Users\Documents\MDMDiagReport.xml`
- `0x1800fa0be`: `%programdata%\microsoft\dmclient\`

## pseudocode

```c
__int64 __fastcall CreateLogOnAreaInternal(const unsigned __int16 *a1, __int64 a2, unsigned int a3, void *a4)
{
  unsigned int v8; // edx
  MdmLogCollector *v9; // rbx
  int v10; // eax
  unsigned int v11; // edi
  const WCHAR *v12; // rax
  const WCHAR *v13; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  signed int LastError; // eax
  unsigned int v18; // ebx
  const WCHAR *v19; // rax
  const WCHAR *v20; // rax
  int v21; // eax
  unsigned int v22; // edi
  const WCHAR *v23; // rax
  const WCHAR *v24; // rax
  int v25; // eax
  unsigned int v26; // edi
  const WCHAR *v27; // rax
  const WCHAR *v28; // rax
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v29; // rax
  int EnrollmentId; // eax
  __int64 v31; // rdx
  __int64 v32; // rax
  const WCHAR *v33; // rcx
  int v34; // eax
  unsigned int v35; // edi
  const WCHAR *v36; // rax
  const WCHAR *v37; // rax
  const unsigned __int16 *v38; // rax
  const unsigned __int16 *v39; // rcx
  const unsigned __int16 *v40; // rax
  const unsigned __int16 *v41; // rax
  const unsigned __int16 *v42; // rax
  int v43; // eax
  unsigned int v44; // ebx
  const WCHAR *v45; // rax
  const WCHAR *v46; // rax
  const WCHAR *v47; // rax
  const WCHAR *v48; // rax
  int v49[2]; // [rsp+20h] [rbp-568h] BYREF
  unsigned __int16 *v50; // [rsp+28h] [rbp-560h] BYREF
  __int128 v51; // [rsp+30h] [rbp-558h] BYREF
  _BYTE v52[16]; // [rsp+40h] [rbp-548h] BYREF
  __int128 *v53; // [rsp+50h] [rbp-538h]
  __int128 *v54; // [rsp+58h] [rbp-530h]
  char v55; // [rsp+60h] [rbp-528h]
  __int128 v56; // [rsp+68h] [rbp-520h] BYREF
  __int64 v57; // [rsp+78h] [rbp-510h]
  __int64 v58; // [rsp+80h] [rbp-508h]
  __int128 v59; // [rsp+88h] [rbp-500h] BYREF
  __int64 v60; // [rsp+98h] [rbp-4F0h]
  __int64 v61; // [rsp+A0h] [rbp-4E8h]
  __int128 v62; // [rsp+A8h] [rbp-4E0h] BYREF
  __int64 v63; // [rsp+B8h] [rbp-4D0h]
  __int64 v64; // [rsp+C0h] [rbp-4C8h]
  _BYTE v65[32]; // [rsp+C8h] [rbp-4C0h] BYREF
  _BYTE v66[32]; // [rsp+E8h] [rbp-4A0h] BYREF
  _BYTE v67[40]; // [rsp+108h] [rbp-480h] BYREF
  WCHAR szShortPath; // [rsp+130h] [rbp-458h] BYREF
  _BYTE v69[526]; // [rsp+132h] [rbp-456h] BYREF
  WCHAR szLongPath; // [rsp+340h] [rbp-248h] BYREF
  _BYTE v71[526]; // [rsp+342h] [rbp-246h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+588h] [rbp+0h]

  v59 = 0;
  v60 = 0;
  v61 = 7;
  LOWORD(v59) = 0;
  v56 = 0;
  v57 = 0;
  v58 = 7;
  LOWORD(v56) = 0;
  v52[0] = 0;
  v52[2] = 0;
  v53 = &v59;
  v54 = &v56;
  v55 = 1;
  *(_QWORD *)&v51 = operator new(0xE8u);
  v9 = MdmLogCollector::MdmLogCollector((MdmLogCollector *)v51, v8, a4);
  *(_QWORD *)v49 = v9;
  v10 = MdmLogCollector::AddPreDefinedListByAreaName(v9, a1, 1);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x277,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\dllmain.cpp",
      (const char *)(unsigned int)v10,
      v49[0]);
    std::unique_ptr<MdmLogCollector>::~unique_ptr<MdmLogCollector>(v49);
    v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v59);
    DeleteFileW(v12);
    v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v56);
    DeleteFileW(v13);
    AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v52);
    std::wstring::_Tidy_deallocate(&v56);
    std::wstring::_Tidy_deallocate(&v59);
    return v11;
  }
  if ( IsDesktopSku() )
  {
    szShortPath = 0;
    memset_0(v69, 0, 0x206u);
    szLongPath = 0;
    memset_0(v71, 0, 0x206u);
    if ( !(unsigned int)GetTempPath2W(260, &szShortPath) || !GetLongPathNameW(&szShortPath, &szLongPath, 0x104u) )
    {
      LastError = GetLastError();
      v18 = LastError;
      if ( LastError > 0 )
        v18 = (unsigned __int16)LastError | 0x80070000;
      std::unique_ptr<MdmLogCollector>::~unique_ptr<MdmLogCollector>(v49);
      v19 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v59);
      DeleteFileW(v19);
      v20 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v56);
      DeleteFileW(v20);
      AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v52);
      std::wstring::_Tidy_deallocate(&v56);
      std::wstring::_Tidy_deallocate(&v59);
      return v18;
    }
    std::wstring::wstring(&v62, &szLongPath);
    v15 = std::operator+<unsigned short>(v65, &v62, L"MDMDiagReport.xml");
    std::wstring::operator=(&v59, v15);
    std::wstring::_Tidy_deallocate(v65);
    v16 = std::operator+<unsigned short>(v65, &v62, L"MDMDiagHTMLReport.html");
    std::wstring::operator=(&v56, v16);
    std::wstring::_Tidy_deallocate(v65);
    std::wstring::_Tidy_deallocate(&v62);
  }
  else
  {
    v21 = MdmLogCollector::ExpandEnvironmentVariable(L"%osdatadrive%\\Public\\Users\\Documents\\MDMDiagReport.xml");
    v22 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x28E,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\dllmain.cpp",
        (const char *)(unsigned int)v21,
        v49[0]);
      std::unique_ptr<MdmLogCollector>::~unique_ptr<MdmLogCollector>(v49);
      v23 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v59);
      DeleteFileW(v23);
      v24 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v56);
      DeleteFileW(v24);
      AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v52);
      std::wstring::_Tidy_deallocate(&v56);
      std::wstring::_Tidy_deallocate(&v59);
      return v22;
    }
    v25 = MdmLogCollector::ExpandEnvironmentVariable(L"%osdatadrive%\\Public\\Users\\Documents\\MDMDiagHtmlReport.html");
    v26 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x28F,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\dllmain.cpp",
        (const char *)(unsigned int)v25,
        v49[0]);
      std::unique_ptr<MdmLogCollector>::~unique_ptr<MdmLogCollector>(v49);
      v27 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v59);
      DeleteFileW(v27);
      v28 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v56);
      DeleteFileW(v28);
      AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v52);
      std::wstring::_Tidy_deallocate(&v56);
      std::wstring::_Tidy_deallocate(&v59);
      return v26;
    }
    v50 = 0;
    *(_QWORD *)&v51 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v50,
      0);
    if ( (int)DmGetActiveUserSid(&v50) >= 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v51,
        0);
      if ( (int)DmGetCurrentUserSid((unsigned __int16 **)&v51) >= 0 )
      {
        if ( (unsigned int)_o__wcsicmp(v51, v50) )
          AutoImpersonate::ImpersonateSID((AutoImpersonate *)v52, v50);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v51);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v50);
  }
  if ( !(unsigned int)_o__wcsicmp(a1, L"DeviceEnrollment") )
  {
    v51 = 0;
    v29 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
    EnrollmentId = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentId(v29, &v51);
    if ( EnrollmentId >= 0 )
    {
      if ( (_QWORD)v51 )
        v31 = *(_QWORD *)v51;
      else
        v31 = 0;
      std::wstring::wstring(v65, v31);
      v32 = std::operator+<unsigned short>(v67, L"%programdata%\\microsoft\\dmclient\\", v65);
      std::operator+<unsigned short>(v66, v32, L"\\*.*");
      std::wstring::_Tidy_deallocate(v67);
      v62 = 0;
      v63 = 0;
      v64 = 7;
      LOWORD(v62) = 0;
      v33 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v66);
      v34 = MdmLogCollector::ExpandEnvironmentVariable(v33);
      v35 = v34;
      if ( v34 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2AA,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\dllmain.cpp",
          (const char *)(unsigned int)v34,
          v49[0]);
        std::wstring::_Tidy_deallocate(&v62);
        std::wstring::_Tidy_deallocate(v66);
        std::wstring::_Tidy_deallocate(v65);
        std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v51);
        std::unique_ptr<MdmLogCollector>::~unique_ptr<MdmLogCollector>(v49);
        v36 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v59);
        DeleteFileW(v36);
        v37 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v56);
        DeleteFileW(v37);
        AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v52);
        std::wstring::_Tidy_deallocate(&v56);
        std::wstring::_Tidy_deallocate(&v59);
        return v35;
      }
      v38 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v62);
      MdmLogCollector::AddFileEntry(v9, v38);
      std::wstring::_Tidy_deallocate(&v62);
      std::wstring::_Tidy_deallocate(v66);
      std::wstring::_Tidy_deallocate(v65);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2A5,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\dllmain.cpp",
        (const char *)(unsigned int)EnrollmentId,
        v49[0]);
    }
    std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v51);
  }
  v39 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v59);
  if ( (int)CreateMdmEnterpriseDiagnosticReport(v39) >= 0 )
  {
    v40 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v59);
    MdmLogCollector::AddFileEntry(v9, v40);
  }
  v41 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v56);
  if ( (int)CreateMdmEnterpriseDiagnosticHTMLReport(v41) >= 0 )
  {
    v42 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v56);
    MdmLogCollector::AddFileEntry(v9, v42);
  }
  AutoImpersonate::RevertToSelf((AutoImpersonate *)v52);
  v43 = MdmLogCollector::CollectLog(v9, a2, a3);
  v44 = v43;
  if ( v43 >= 0 )
  {
    std::unique_ptr<MdmLogCollector>::~unique_ptr<MdmLogCollector>(v49);
    v47 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v59);
    DeleteFileW(v47);
    v48 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v56);
    DeleteFileW(v48);
    AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v52);
    std::wstring::_Tidy_deallocate(&v56);
    std::wstring::_Tidy_deallocate(&v59);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2BC,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\dllmain.cpp",
      (const char *)(unsigned int)v43,
      v49[0]);
    std::unique_ptr<MdmLogCollector>::~unique_ptr<MdmLogCollector>(v49);
    v45 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v59);
    DeleteFileW(v45);
    v46 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v56);
    DeleteFileW(v46);
    AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v52);
    std::wstring::_Tidy_deallocate(&v56);
    std::wstring::_Tidy_deallocate(&v59);
    return v44;
  }
}

```

## disassembly

```asm
0x1800f9bb4  mov     r11, rsp
0x1800f9bb7  mov     [r11+20h], rbx
0x1800f9bbb  push    rsi
0x1800f9bbc  push    rdi
0x1800f9bbd  push    r13
0x1800f9bbf  push    r14
0x1800f9bc1  push    r15
0x1800f9bc3  sub     rsp, 560h
0x1800f9bca  mov     rax, cs:__security_cookie
0x1800f9bd1  xor     rax, rsp
0x1800f9bd4  mov     [rsp+588h+var_38], rax
0x1800f9bdc  mov     rbx, r9
0x1800f9bdf  mov     r15d, r8d
0x1800f9be2  mov     r14, rdx
0x1800f9be5  mov     rsi, rcx
0x1800f9be8  xorps   xmm0, xmm0
0x1800f9beb  movups  [rsp+588h+var_500], xmm0
0x1800f9bf3  mov     qword ptr [r11-4F0h], 0
0x1800f9bfe  mov     r13d, 7
0x1800f9c04  mov     [r11-4E8h], r13
0x1800f9c0b  xor     eax, eax
0x1800f9c0d  mov     word ptr [rsp+588h+var_500], ax
0x1800f9c15  movups  [rsp+588h+var_520], xmm0
0x1800f9c1a  mov     [rsp+588h+var_510], rax
0x1800f9c1f  mov     [r11-508h], r13
0x1800f9c26  mov     word ptr [rsp+588h+var_520], ax
0x1800f9c2b  mov     [rsp+588h+var_548], al
0x1800f9c2f  mov     [rsp+588h+var_546], al
0x1800f9c33  lea     rax, [r11-500h]
0x1800f9c3a  mov     [rsp+588h+var_538], rax
0x1800f9c3f  lea     rax, [rsp+588h+var_520]
0x1800f9c44  mov     [rsp+588h+var_530], rax
0x1800f9c49  mov     [rsp+588h+var_528], 1
0x1800f9c4e  mov     ecx, 0E8h; Size
0x1800f9c53  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f9c58  mov     qword ptr [rsp+588h+var_558], rax
0x1800f9c5d  mov     r8, rbx; void *
0x1800f9c60  mov     rcx, rax; this
0x1800f9c63  call    ??0MdmLogCollector@@QEAA@KPEAX@Z; MdmLogCollector::MdmLogCollector(ulong,void *)
0x1800f9c68  mov     rbx, rax
0x1800f9c6b  mov     qword ptr [rsp+588h+var_568], rax; int
0x1800f9c70  mov     r8b, 1; bool
0x1800f9c73  mov     rdx, rsi; unsigned __int16 *
0x1800f9c76  mov     rcx, rax; this
0x1800f9c79  call    ?AddPreDefinedListByAreaName@MdmLogCollector@@QEAAJPEBG_N@Z; MdmLogCollector::AddPreDefinedListByAreaName(ushort const *,bool)
0x1800f9c7e  mov     edi, eax
0x1800f9c80  test    eax, eax
0x1800f9c82  jns     short loc_1800F9D00
0x1800f9c84  mov     rcx, [rsp+588h]; this
0x1800f9c8c  mov     r9d, eax; char *
0x1800f9c8f  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f9c96  mov     edx, 277h; void *
0x1800f9c9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f9ca0  nop
0x1800f9ca1  lea     rcx, [rsp+588h+var_568]
0x1800f9ca6  call    ??1?$unique_ptr@VMdmLogCollector@@U?$default_delete@VMdmLogCollector@@@std@@@std@@QEAA@XZ; std::unique_ptr<MdmLogCollector>::~unique_ptr<MdmLogCollector>(void)
0x1800f9cab  nop
0x1800f9cac  lea     rcx, [rsp+588h+var_500]
0x1800f9cb4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800f9cb9  mov     rcx, rax; lpFileName
0x1800f9cbc  call    cs:__imp_DeleteFileW
0x1800f9cc2  lea     rcx, [rsp+588h+var_520]
0x1800f9cc7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800f9ccc  mov     rcx, rax; lpFileName
0x1800f9ccf  call    cs:__imp_DeleteFileW
0x1800f9cd5  nop
0x1800f9cd6  lea     rcx, [rsp+588h+var_548]; this
0x1800f9cdb  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x1800f9ce0  nop
0x1800f9ce1  lea     rcx, [rsp+588h+var_520]
0x1800f9ce6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f9ceb  nop
0x1800f9cec  lea     rcx, [rsp+588h+var_500]
0x1800f9cf4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f9cf9  mov     eax, edi
0x1800f9cfb  jmp     loc_1800FA399
0x1800f9d00  call    cs:__imp_?IsDesktopSku@@YAHXZ; IsDesktopSku(void)
0x1800f9d06  test    eax, eax
0x1800f9d08  jz      loc_1800F9E95
0x1800f9d0e  xor     eax, eax
0x1800f9d10  mov     [rsp+588h+szShortPath], ax
0x1800f9d18  mov     edi, 206h
0x1800f9d1d  mov     r8d, edi; Size
0x1800f9d20  xor     edx, edx; Val
0x1800f9d22  lea     rcx, [rsp+588h+var_456]; void *
0x1800f9d2a  call    memset_0
0x1800f9d2f  xor     eax, eax
0x1800f9d31  mov     [rsp+588h+szLongPath], ax
0x1800f9d39  mov     r8d, edi; Size
0x1800f9d3c  xor     edx, edx; Val
0x1800f9d3e  lea     rcx, [rsp+588h+var_246]; void *
0x1800f9d46  call    memset_0
0x1800f9d4b  lea     rdx, [rsp+588h+szShortPath]
0x1800f9d53  mov     edi, 104h
0x1800f9d58  mov     ecx, edi
0x1800f9d5a  call    cs:__imp_GetTempPath2W
0x1800f9d60  test    eax, eax
0x1800f9d62  jz      loc_1800F9E21
0x1800f9d68  mov     r8d, edi; cchBuffer
0x1800f9d6b  lea     rdx, [rsp+588h+szLongPath]; lpszLongPath
0x1800f9d73  lea     rcx, [rsp+588h+szShortPath]; lpszShortPath
0x1800f9d7b  call    cs:__imp_GetLongPathNameW
0x1800f9d81  test    eax, eax
0x1800f9d83  jz      loc_1800F9E21
0x1800f9d89  lea     rdx, [rsp+588h+szLongPath]
0x1800f9d91  lea     rcx, [rsp+588h+var_4E0]
0x1800f9d99  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800f9d9e  nop
0x1800f9d9f  lea     r8, aMdmdiagreportX; "MDMDiagReport.xml"
0x1800f9da6  lea     rdx, [rsp+588h+var_4E0]
0x1800f9dae  lea     rcx, [rsp+588h+var_4C0]
0x1800f9db6  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800f9dbb  mov     rdx, rax
0x1800f9dbe  lea     rcx, [rsp+588h+var_500]
0x1800f9dc6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800f9dcb  lea     rcx, [rsp+588h+var_4C0]
0x1800f9dd3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f9dd8  lea     r8, aMdmdiaghtmlrep; "MDMDiagHTMLReport.html"
0x1800f9ddf  lea     rdx, [rsp+588h+var_4E0]
0x1800f9de7  lea     rcx, [rsp+588h+var_4C0]
0x1800f9def  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800f9df4  mov     rdx, rax
0x1800f9df7  lea     rcx, [rsp+588h+var_520]
0x1800f9dfc  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800f9e01  lea     rcx, [rsp+588h+var_4C0]
0x1800f9e09  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f9e0e  nop
0x1800f9e0f  lea     rcx, [rsp+588h+var_4E0]
0x1800f9e17  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f9e1c  jmp     loc_1800FA03F
0x1800f9e21  call    cs:__imp_GetLastError
0x1800f9e27  mov     ebx, eax
0x1800f9e29  test    eax, eax
0x1800f9e2b  jle     short loc_1800F9E36
0x1800f9e2d  movzx   ebx, ax
0x1800f9e30  or      ebx, 80070000h
0x1800f9e36  lea     rcx, [rsp+588h+var_568]
0x1800f9e3b  call    ??1?$unique_ptr@VMdmLogCollector@@U?$default_delete@VMdmLogCollector@@@std@@@std@@QEAA@XZ; std::unique_ptr<MdmLogCollector>::~unique_ptr<MdmLogCollector>(void)
0x1800f9e40  nop
0x1800f9e41  lea     rcx, [rsp+588h+var_500]
0x1800f9e49  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800f9e4e  mov     rcx, rax; lpFileName
0x1800f9e51  call    cs:__imp_DeleteFileW
0x1800f9e57  lea     rcx, [rsp+588h+var_520]
0x1800f9e5c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800f9e61  mov     rcx, rax; lpFileName
0x1800f9e64  call    cs:__imp_DeleteFileW
0x1800f9e6a  nop
0x1800f9e6b  lea     rcx, [rsp+588h+var_548]; this
0x1800f9e70  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x1800f9e75  nop
0x1800f9e76  lea     rcx, [rsp+588h+var_520]
0x1800f9e7b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f9e80  nop
0x1800f9e81  lea     rcx, [rsp+588h+var_500]
0x1800f9e89  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f9e8e  mov     eax, ebx
0x1800f9e90  jmp     loc_1800FA399
0x1800f9e95  lea     rdx, [rsp+588h+var_500]
0x1800f9e9d  lea     rcx, aOsdatadrivePub; "%osdatadrive%\\Public\\Users\\Documents"...
0x1800f9ea4  call    ?ExpandEnvironmentVariable@MdmLogCollector@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmLogCollector::ExpandEnvironmentVariable(ushort const *,std::wstring &)
0x1800f9ea9  mov     edi, eax
0x1800f9eab  test    eax, eax
0x1800f9ead  jns     short loc_1800F9F2B
0x1800f9eaf  mov     rcx, [rsp+588h]; this
0x1800f9eb7  mov     r9d, eax; char *
0x1800f9eba  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f9ec1  mov     edx, 28Eh; void *
0x1800f9ec6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f9ecb  nop
0x1800f9ecc  lea     rcx, [rsp+588h+var_568]
0x1800f9ed1  call    ??1?$unique_ptr@VMdmLogCollector@@U?$default_delete@VMdmLogCollector@@@std@@@std@@QEAA@XZ; std::unique_ptr<MdmLogCollector>::~unique_ptr<MdmLogCollector>(void)
0x1800f9ed6  nop
0x1800f9ed7  lea     rcx, [rsp+588h+var_500]
0x1800f9edf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800f9ee4  mov     rcx, rax; lpFileName
0x1800f9ee7  call    cs:__imp_DeleteFileW
0x1800f9eed  lea     rcx, [rsp+588h+var_520]
0x1800f9ef2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800f9ef7  mov     rcx, rax; lpFileName
0x1800f9efa  call    cs:__imp_DeleteFileW
0x1800f9f00  nop
0x1800f9f01  lea     rcx, [rsp+588h+var_548]; this
0x1800f9f06  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x1800f9f0b  nop
0x1800f9f0c  lea     rcx, [rsp+588h+var_520]
0x1800f9f11  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f9f16  nop
0x1800f9f17  lea     rcx, [rsp+588h+var_500]
0x1800f9f1f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f9f24  mov     eax, edi
0x1800f9f26  jmp     loc_1800FA399
0x1800f9f2b  lea     rdx, [rsp+588h+var_520]
0x1800f9f30  lea     rcx, aOsdatadrivePub_0; "%osdatadrive%\\Public\\Users\\Documents"...
0x1800f9f37  call    ?ExpandEnvironmentVariable@MdmLogCollector@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmLogCollector::ExpandEnvironmentVariable(ushort const *,std::wstring &)
0x1800f9f3c  mov     edi, eax
0x1800f9f3e  test    eax, eax
0x1800f9f40  jns     short loc_1800F9FBE
0x1800f9f42  mov     rcx, [rsp+588h]; this
0x1800f9f4a  mov     r9d, eax; char *
0x1800f9f4d  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f9f54  mov     edx, 28Fh; void *
0x1800f9f59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f9f5e  nop
0x1800f9f5f  lea     rcx, [rsp+588h+var_568]
0x1800f9f64  call    ??1?$unique_ptr@VMdmLogCollector@@U?$default_delete@VMdmLogCollector@@@std@@@std@@QEAA@XZ; std::unique_ptr<MdmLogCollector>::~unique_ptr<MdmLogCollector>(void)
0x1800f9f69  nop
0x1800f9f6a  lea     rcx, [rsp+588h+var_500]
0x1800f9f72  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800f9f77  mov     rcx, rax; lpFileName
0x1800f9f7a  call    cs:__imp_DeleteFileW
0x1800f9f80  lea     rcx, [rsp+588h+var_520]
0x1800f9f85  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800f9f8a  mov     rcx, rax; lpFileName
0x1800f9f8d  call    cs:__imp_DeleteFileW
0x1800f9f93  nop
0x1800f9f94  lea     rcx, [rsp+588h+var_548]; this
0x1800f9f99  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x1800f9f9e  nop
0x1800f9f9f  lea     rcx, [rsp+588h+var_520]
0x1800f9fa4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f9fa9  nop
0x1800f9faa  lea     rcx, [rsp+588h+var_500]
0x1800f9fb2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f9fb7  mov     eax, edi
0x1800f9fb9  jmp     loc_1800FA399
0x1800f9fbe  mov     [rsp+588h+var_560], 0
0x1800f9fc7  mov     qword ptr [rsp+588h+var_558], 0
0x1800f9fd0  xor     edx, edx
0x1800f9fd2  lea     rcx, [rsp+588h+var_560]
0x1800f9fd7  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800f9fdc  lea     rcx, [rsp+588h+var_560]
0x1800f9fe1  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x1800f9fe7  test    eax, eax
0x1800f9fe9  js      short loc_1800FA02A
0x1800f9feb  xor     edx, edx
0x1800f9fed  lea     rcx, [rsp+588h+var_558]
0x1800f9ff2  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800f9ff7  lea     rcx, [rsp+588h+var_558]
0x1800f9ffc  call    cs:__imp_?DmGetCurrentUserSid@@YAJPEAPEAG@Z; DmGetCurrentUserSid(ushort * *)
0x1800fa002  test    eax, eax
0x1800fa004  js      short loc_1800FA02A
0x1800fa006  mov     rdx, [rsp+588h+var_560]
0x1800fa00b  mov     rcx, qword ptr [rsp+588h+var_558]
0x1800fa010  call    cs:__imp__o__wcsicmp
0x1800fa016  test    eax, eax
0x1800fa018  jz      short loc_1800FA02A
0x1800fa01a  mov     rdx, [rsp+588h+var_560]; unsigned __int16 *
0x1800fa01f  lea     rcx, [rsp+588h+var_548]; this
0x1800fa024  call    ?ImpersonateSID@AutoImpersonate@@QEAAJPEBG@Z; AutoImpersonate::ImpersonateSID(ushort const *)
0x1800fa029  nop
0x1800fa02a  lea     rcx, [rsp+588h+var_558]
0x1800fa02f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800fa034  nop
0x1800fa035  lea     rcx, [rsp+588h+var_560]
0x1800fa03a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800fa03f  lea     rdx, aDeviceenrollme; "DeviceEnrollment"
0x1800fa046  mov     rcx, rsi
0x1800fa049  call    cs:__imp__o__wcsicmp
0x1800fa04f  test    eax, eax
0x1800fa051  jnz     loc_1800FA246
0x1800fa057  xorps   xmm1, xmm1
0x1800fa05a  movdqu  [rsp+588h+var_558], xmm1
0x1800fa060  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x1800fa065  lea     rdx, [rsp+588h+var_558]
0x1800fa06a  mov     rcx, rax
0x1800fa06d  call    ?GetEnrollmentId@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentId(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>> &)
0x1800fa072  mov     rcx, [rsp+588h]; this
0x1800fa07a  test    eax, eax
0x1800fa07c  jns     short loc_1800FA097
0x1800fa07e  mov     r9d, eax; char *
0x1800fa081  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800fa088  mov     edx, 2A5h; void *
0x1800fa08d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800fa092  jmp     loc_1800FA23C
0x1800fa097  mov     rax, qword ptr [rsp+588h+var_558]
0x1800fa09c  test    rax, rax
0x1800fa09f  jz      short loc_1800FA0A6
0x1800fa0a1  mov     rdx, [rax]
0x1800fa0a4  jmp     short loc_1800FA0A8
0x1800fa0a6  xor     edx, edx
0x1800fa0a8  lea     rcx, [rsp+588h+var_4C0]
0x1800fa0b0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800fa0b5  nop
0x1800fa0b6  lea     r8, [rsp+588h+var_4C0]
0x1800fa0be  lea     rdx, aProgramdataMic; "%programdata%\\microsoft\\dmclient\\"
0x1800fa0c5  lea     rcx, [rsp+588h+var_480]
0x1800fa0cd  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x1800fa0d2  nop
0x1800fa0d3  lea     r8, asc_1801BF310; "\\*.*"
0x1800fa0da  mov     rdx, rax
0x1800fa0dd  lea     rcx, [rsp+588h+var_4A0]
0x1800fa0e5  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800fa0ea  nop
0x1800fa0eb  lea     rcx, [rsp+588h+var_480]
0x1800fa0f3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800fa0f8  xorps   xmm0, xmm0
0x1800fa0fb  movups  [rsp+588h+var_4E0], xmm0
0x1800fa103  mov     [rsp+588h+var_4D0], 0
0x1800fa10f  mov     [rsp+588h+var_4C8], r13
  ... truncated ...
```

# WriteConnectionInfo(void)

- ea: `0x18012b354`
- end: `0x18012bec9`
- name: `?WriteConnectionInfo@@YAJXZ`
- size: `2933`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801266fc`

## callees

- `0x180019000`
- `0x1800e4348`
- `0x1800e66b8`
- `0x1800e66dc`
- `0x1800e7c08`
- `0x1800ece5c`
- `0x1800ee878`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800ef8c8`
- `0x1800ef900`
- `0x1800f9558`
- `0x1800f9a0c`
- `0x180104270`
- `0x18010440c`
- `0x1801058cc`
- `0x180105c40`
- `0x18011129c`
- `0x180127960`
- `0x180127fa8`
- `0x1801283b0`
- `0x180128780`
- `0x180128e28`
- `0x1801293f4`
- `0x18012b354`
- `0x180131140`
- `0x180131d60`
- `0x180132f88`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18012bb82`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18012bb82`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18012bc39`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18012bc39`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012bcf9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012bcf9`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18012ba79`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18012ba79`
- `DMCmnUtils!DmRevertToSelf` at `0x18012babf`
- `DMCmnUtils!DmRevertToSelf` at `0x18012bb47`
- `DMCmnUtils!DmRevertToSelf` at `0x18012bbdb`
- `DMCmnUtils!DmRevertToSelf` at `0x18012bc8d`
- `DMCmnUtils!DmRevertToSelf` at `0x18012be0a`
- `DMCmnUtils!DmRevertToSelf` at `0x18012be63`
- `DMCmnUtils!DmRevertToSelf` at `0x18012babf`
- `DMCmnUtils!DmRevertToSelf` at `0x18012bb47`
- `DMCmnUtils!DmRevertToSelf` at `0x18012bbdb`
- `DMCmnUtils!DmRevertToSelf` at `0x18012bc8d`
- `DMCmnUtils!DmRevertToSelf` at `0x18012be0a`
- `DMCmnUtils!DmRevertToSelf` at `0x18012be63`
- `DMCmnUtils!DmImpersonate` at `0x18012bb95`
- `DMCmnUtils!DmImpersonate` at `0x18012bb95`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x18012bb01`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x18012bb01`
- `dmiso8601utils!ISO8601StringToSystemTime` at `0x18012b668`
- `dmiso8601utils!ISO8601StringToSystemTime` at `0x18012b668`

## string_xrefs

- `0x18012b3b8`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012b438`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012b4a0`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012b5cd`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012b67f`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012b6fd`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012b88f`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012b9ed`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012ba90`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012bb18`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012bbac`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012bc50`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012bdcd`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=50 #try_helpers=1
__int64 WriteConnectionInfo(void)
{
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v0; // rax
  int EnrollmentId; // eax
  unsigned int v2; // ebx
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v4; // rax
  int OmadmAccountInfo; // eax
  unsigned int v6; // ebx
  int v7; // eax
  unsigned int v8; // ebx
  HKEY v9; // rbx
  __int64 v10; // rax
  int v11; // eax
  unsigned int v12; // edi
  int v13; // eax
  unsigned int v14; // edi
  int v15; // eax
  unsigned int v16; // edi
  __int64 v17; // rax
  int v18; // eax
  unsigned int v19; // edi
  __int64 v20; // rdx
  int v21; // eax
  unsigned int v22; // ebx
  int ActiveUserSid; // eax
  unsigned int v24; // ebx
  int CurrentUserSid; // eax
  int v26; // eax
  LSTATUS v27; // eax
  int v28; // eax
  int pdwType; // [rsp+20h] [rbp-358h]
  int pdwTypea; // [rsp+20h] [rbp-358h]
  char v31; // [rsp+40h] [rbp-338h] BYREF
  _BYTE v32[8]; // [rsp+48h] [rbp-330h] BYREF
  __int64 v33; // [rsp+50h] [rbp-328h]
  __int64 v34; // [rsp+58h] [rbp-320h]
  unsigned __int16 *v35; // [rsp+60h] [rbp-318h] BYREF
  unsigned __int16 *v36; // [rsp+68h] [rbp-310h] BYREF
  __int128 v37; // [rsp+70h] [rbp-308h] BYREF
  DWORD pcbData; // [rsp+80h] [rbp-2F8h] BYREF
  HKEY phkResult[2]; // [rsp+88h] [rbp-2F0h] BYREF
  _BYTE v40[32]; // [rsp+98h] [rbp-2E0h] BYREF
  _BYTE v41[32]; // [rsp+B8h] [rbp-2C0h] BYREF
  char *v42; // [rsp+D8h] [rbp-2A0h] BYREF
  char v43; // [rsp+E0h] [rbp-298h]
  _BYTE v44[80]; // [rsp+100h] [rbp-278h] BYREF
  _WORD pvData[264]; // [rsp+150h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+378h] [rbp+0h]

  std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(v32);
  v37 = 0;
  v0 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
  EnrollmentId = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentId(v0, &v37);
  v2 = EnrollmentId;
  if ( EnrollmentId < 0 )
  {
    if ( EnrollmentId == -2147023728 )
    {
      std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v37);
      std::vector<std::wstring>::_Tidy(v32);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x478,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
        (const char *)(unsigned int)EnrollmentId,
        pdwType);
      std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v37);
      std::vector<std::wstring>::_Tidy(v32);
      return v2;
    }
  }
  phkResult[0] = 0;
  v4 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
  OmadmAccountInfo = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetOmadmAccountInfo(
                       v4,
                       (const struct tagOMADMACCTINFO **)phkResult);
  v6 = OmadmAccountInfo;
  if ( OmadmAccountInfo < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47D,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)(unsigned int)OmadmAccountInfo,
      pdwType);
    std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v37);
    std::vector<std::wstring>::_Tidy(v32);
    return v6;
  }
  Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::SimpleTable(
    (Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v44,
    L"Connection Info",
    L"ConnectionInfoTable");
  v7 = Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::WriteSectionHeaderForTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v44);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x480,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)(unsigned int)v7,
      pdwType);
    Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v44);
    std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v37);
    std::vector<std::wstring>::_Tidy(v32);
    return v8;
  }
  pcbData = 260;
  v9 = phkResult[0];
  std::wstring::wstring(&v42, *((_QWORD *)phkResult[0] + 4));
  std::wstring::wstring(v41, L"Managed by");
  if ( v33 == v34 )
    std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v32, v33, v41);
  else
    std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v32, v41);
  std::wstring::_Tidy_deallocate(v41);
  v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v42);
  std::wstring::wstring(v41, v10);
  if ( v33 == v34 )
    std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v32, v33, v41);
  else
    std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v32, v41);
  std::wstring::_Tidy_deallocate(v41);
  v11 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v44, v32);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48B,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)(unsigned int)v11,
      pdwType);
    std::wstring::_Tidy_deallocate(&v42);
    Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v44);
    std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v37);
    std::vector<std::wstring>::_Tidy(v32);
    return v12;
  }
  std::wstring::_Tidy_deallocate(&v42);
  std::wstring::wstring(v41);
  std::wstring::wstring(&v42);
  LODWORD(v35) = 0;
  *(_OWORD *)phkResult = 0;
  v13 = ISO8601StringToSystemTime(*((_QWORD *)v9 + 46), 1, phkResult, &v35);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x494,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)(unsigned int)v13,
      pdwType);
    std::wstring::_Tidy_deallocate(&v42);
    std::wstring::_Tidy_deallocate(v41);
    Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v44);
    std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v37);
    std::vector<std::wstring>::_Tidy(v32);
    return v14;
  }
  v15 = ConvertSystemTimeToString(phkResult, v41);
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x495,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)(unsigned int)v15,
      pdwType);
    std::wstring::_Tidy_deallocate(&v42);
    std::wstring::_Tidy_deallocate(v41);
    Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v44);
    std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v37);
    std::vector<std::wstring>::_Tidy(v32);
    return v16;
  }
  std::wstring::assign(&v42, L"The last sync ");
  if ( !*((_QWORD *)v9 + 46) || *((_DWORD *)v9 + 99) )
    std::wstring::append(&v42, L"failed ");
  else
    std::wstring::append(&v42, L"was successful ");
  std::wstring::append(&v42, v41);
  std::vector<std::wstring>::clear(v32);
  std::wstring::wstring(v40, L"Last sync");
  if ( v33 == v34 )
    std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v32, v33, v40);
  else
    std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v32, v40);
  std::wstring::_Tidy_deallocate(v40);
  v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v42);
  std::wstring::wstring(v40, v17);
  if ( v33 == v34 )
    std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v32, v33, v40);
  else
    std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v32, v40);
  std::wstring::_Tidy_deallocate(v40);
  v18 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v44, v32);
  v19 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A5,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)(unsigned int)v18,
      pdwType);
    std::wstring::_Tidy_deallocate(&v42);
    std::wstring::_Tidy_deallocate(v41);
    Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v44);
    std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v37);
    std::vector<std::wstring>::_Tidy(v32);
    return v19;
  }
  std::wstring::_Tidy_deallocate(&v42);
  std::wstring::_Tidy_deallocate(v41);
  std::wstring::wstring(v41, *((_QWORD *)v9 + 19));
  std::vector<std::wstring>::clear(v32);
  std::wstring::wstring(v40, L"Management server address");
  if ( v33 == v34 )
    std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v32, v33, v40);
  else
    std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v32, v40);
  std::wstring::_Tidy_deallocate(v40);
  v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v41);
  std::wstring::wstring(v40, v20);
  if ( v33 == v34 )
    std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v32, v33, v40);
  else
    std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v32, v40);
  std::wstring::_Tidy_deallocate(v40);
  v21 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v44, v32);
  v22 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4AF,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)(unsigned int)v21,
      pdwType);
    std::wstring::_Tidy_deallocate(v41);
    Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v44);
    std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v37);
    std::vector<std::wstring>::_Tidy(v32);
    return v22;
  }
  std::wstring::_Tidy_deallocate(v41);
  v31 = 0;
  v42 = &v31;
  v43 = 1;
  v35 = 0;
  v36 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v35,
    0);
  ActiveUserSid = DmGetActiveUserSid(&v35);
  v24 = ActiveUserSid;
  if ( ActiveUserSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C2,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)(unsigned int)ActiveUserSid,
      pdwType);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v36);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
    if ( v31 )
      DmRevertToSelf();
LABEL_68:
    Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v44);
    std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v37);
    std::vector<std::wstring>::_Tidy(v32);
    return v24;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v36,
    0);
  CurrentUserSid = DmGetCurrentUserSid(&v36);
  v24 = CurrentUserSid;
  if ( CurrentUserSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C3,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)(unsigned int)CurrentUserSid,
      pdwType);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v36);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
    if ( v31 )
      DmRevertToSelf();
    goto LABEL_68;
  }
  if ( (unsigned int)_o__wcsicmp(v36, v35) )
  {
    v26 = DmImpersonate(v35);
    v24 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4C7,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
        (const char *)(unsigned int)v26,
        pdwType);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v36);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
      if ( v31 )
        DmRevertToSelf();
      goto LABEL_68;
    }
    v31 = 1;
  }
  pvData[0] = 0;
  pcbData = 260;
  phkResult[0] = 0;
  v27 = RegOpenCurrentUser(1u, phkResult);
  v24 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4CE,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)(unsigned int)v27,
      pdwType);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(phkResult);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v36);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
    if ( v31 )
      DmRevertToSelf();
    goto LABEL_68;
  }
  RegGetValueW(phkResult[0], L"Software\\Microsoft\\ActiveSync\\Partners", L"DeviceID", 2u, 0, pvData, &pcbData);
  std::vector<std::wstring>::clear(v32);
  std::wstring::wstring(v40, L"Exchange ID");
  if ( v33 == v34 )
    std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v32, v33, v40);
  else
    std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v32, v40);
  std::wstring::_Tidy_deallocate(v40);
  std::wstring::wstring(v40, pvData);
  if ( v33 == v34 )
    std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v32, v33, v40);
  else
    std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v32, v40);
  std::wstring::_Tidy_deallocate(v40);
  v28 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v44, v32);
  v24 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D5,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)(unsigned int)v28,
      pdwTypea);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(phkResult);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v36);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
    if ( v31 )
      DmRevertToSelf();
    goto LABEL_68;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(phkResult);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v36);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
  if ( v31 )
    DmRevertToSelf();
  WriteUserDetails((struct Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v44);
  Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v44);
  std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v37);
  std::vector<std::wstring>::_Tidy(v32);
  return 0;
}

```

## disassembly

```asm
0x18012b354  mov     [rsp+arg_0], rbx
0x18012b359  mov     [rsp+arg_8], rsi
0x18012b35e  push    rdi
0x18012b35f  sub     rsp, 370h
0x18012b366  mov     rax, cs:__security_cookie
0x18012b36d  xor     rax, rsp
0x18012b370  mov     [rsp+378h+var_18], rax
0x18012b378  lea     rcx, [rsp+378h+var_330]
0x18012b37d  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x18012b382  nop
0x18012b383  xorps   xmm1, xmm1
0x18012b386  movdqu  [rsp+378h+var_308], xmm1
0x18012b38c  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18012b391  lea     rdx, [rsp+378h+var_308]
0x18012b396  mov     rcx, rax
0x18012b399  call    ?GetEnrollmentId@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentId(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>> &)
0x18012b39e  mov     ebx, eax
0x18012b3a0  xor     esi, esi
0x18012b3a2  test    eax, eax
0x18012b3a4  jns     short loc_18012B3E6
0x18012b3a6  cmp     eax, 80070490h
0x18012b3ab  jz      short loc_18012B3EE
0x18012b3ad  mov     rcx, [rsp+378h]; this
0x18012b3b5  mov     r9d, eax; char *
0x18012b3b8  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012b3bf  mov     edx, 478h; void *
0x18012b3c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012b3c9  nop
0x18012b3ca  lea     rcx, [rsp+378h+var_308]
0x18012b3cf  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x18012b3d4  nop
0x18012b3d5  lea     rcx, [rsp+378h+var_330]
0x18012b3da  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012b3df  mov     eax, ebx
0x18012b3e1  jmp     loc_18012BEA3
0x18012b3e6  cmp     ebx, 80070490h
0x18012b3ec  jnz     short loc_18012B40A
0x18012b3ee  lea     rcx, [rsp+378h+var_308]
0x18012b3f3  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x18012b3f8  nop
0x18012b3f9  lea     rcx, [rsp+378h+var_330]
0x18012b3fe  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012b403  xor     eax, eax
0x18012b405  jmp     loc_18012BEA3
0x18012b40a  mov     [rsp+378h+phkResult], rsi
0x18012b412  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18012b417  lea     rdx, [rsp+378h+phkResult]; struct tagOMADMACCTINFO **
0x18012b41f  mov     rcx, rax; this
0x18012b422  call    ?GetOmadmAccountInfo@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAPEBUtagOMADMACCTINFO@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetOmadmAccountInfo(tagOMADMACCTINFO const * &)
0x18012b427  mov     ebx, eax
0x18012b429  test    eax, eax
0x18012b42b  jns     short loc_18012B466
0x18012b42d  mov     rcx, [rsp+378h]; this
0x18012b435  mov     r9d, eax; char *
0x18012b438  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012b43f  mov     edx, 47Dh; void *
0x18012b444  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012b449  nop
0x18012b44a  lea     rcx, [rsp+378h+var_308]
0x18012b44f  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x18012b454  nop
0x18012b455  lea     rcx, [rsp+378h+var_330]
0x18012b45a  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012b45f  mov     eax, ebx
0x18012b461  jmp     loc_18012BEA3
0x18012b466  lea     r8, aConnectioninfo; "ConnectionInfoTable"
0x18012b46d  lea     rdx, aConnectionInfo; "Connection Info"
0x18012b474  lea     rcx, [rsp+378h+var_278]; this
0x18012b47c  call    ??0SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@PEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::SimpleTable(ushort const *,ushort const *)
0x18012b481  nop
0x18012b482  lea     rcx, [rsp+378h+var_278]; this
0x18012b48a  call    ?WriteSectionHeaderForTable@SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJXZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::WriteSectionHeaderForTable(void)
0x18012b48f  mov     ebx, eax
0x18012b491  test    eax, eax
0x18012b493  jns     short loc_18012B4DC
0x18012b495  mov     rcx, [rsp+378h]; this
0x18012b49d  mov     r9d, eax; char *
0x18012b4a0  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012b4a7  mov     edx, 480h; void *
0x18012b4ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012b4b1  nop
0x18012b4b2  lea     rcx, [rsp+378h+var_278]; this
0x18012b4ba  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012b4bf  nop
0x18012b4c0  lea     rcx, [rsp+378h+var_308]
0x18012b4c5  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x18012b4ca  nop
0x18012b4cb  lea     rcx, [rsp+378h+var_330]
0x18012b4d0  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012b4d5  mov     eax, ebx
0x18012b4d7  jmp     loc_18012BEA3
0x18012b4dc  mov     [rsp+378h+var_2F8], 104h
0x18012b4e7  mov     rbx, [rsp+378h+phkResult]
0x18012b4ef  mov     rdx, [rbx+20h]
0x18012b4f3  lea     rcx, [rsp+378h+var_2A0]
0x18012b4fb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012b500  nop
0x18012b501  lea     rdx, aManagedBy; "Managed by"
0x18012b508  lea     rcx, [rsp+378h+var_2C0]
0x18012b510  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012b515  nop
0x18012b516  mov     rdx, [rsp+378h+var_328]
0x18012b51b  lea     rcx, [rsp+378h+var_330]
0x18012b520  cmp     rdx, [rsp+378h+var_320]
0x18012b525  jz      short loc_18012B536
0x18012b527  lea     rdx, [rsp+378h+var_2C0]
0x18012b52f  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012b534  jmp     short loc_18012B544
0x18012b536  lea     r8, [rsp+378h+var_2C0]
0x18012b53e  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012b543  nop
0x18012b544  lea     rcx, [rsp+378h+var_2C0]
0x18012b54c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012b551  lea     rcx, [rsp+378h+var_2A0]
0x18012b559  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18012b55e  mov     rdx, rax
0x18012b561  lea     rcx, [rsp+378h+var_2C0]
0x18012b569  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012b56e  nop
0x18012b56f  mov     rdx, [rsp+378h+var_328]
0x18012b574  lea     rcx, [rsp+378h+var_330]
0x18012b579  cmp     rdx, [rsp+378h+var_320]
0x18012b57e  jz      short loc_18012B58F
0x18012b580  lea     rdx, [rsp+378h+var_2C0]
0x18012b588  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012b58d  jmp     short loc_18012B59D
0x18012b58f  lea     r8, [rsp+378h+var_2C0]
0x18012b597  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012b59c  nop
0x18012b59d  lea     rcx, [rsp+378h+var_2C0]
0x18012b5a5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012b5aa  lea     rdx, [rsp+378h+var_330]
0x18012b5af  lea     rcx, [rsp+378h+var_278]
0x18012b5b7  call    ?AddTableRow@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(std::vector<std::wstring> &)
0x18012b5bc  mov     edi, eax
0x18012b5be  test    eax, eax
0x18012b5c0  jns     short loc_18012B617
0x18012b5c2  mov     rcx, [rsp+378h]; this
0x18012b5ca  mov     r9d, eax; char *
0x18012b5cd  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012b5d4  mov     edx, 48Bh; void *
0x18012b5d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012b5de  nop
0x18012b5df  lea     rcx, [rsp+378h+var_2A0]
0x18012b5e7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012b5ec  nop
0x18012b5ed  lea     rcx, [rsp+378h+var_278]; this
0x18012b5f5  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012b5fa  nop
0x18012b5fb  lea     rcx, [rsp+378h+var_308]
0x18012b600  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x18012b605  nop
0x18012b606  lea     rcx, [rsp+378h+var_330]
0x18012b60b  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012b610  mov     eax, edi
0x18012b612  jmp     loc_18012BEA3
0x18012b617  lea     rcx, [rsp+378h+var_2A0]
0x18012b61f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012b624  lea     rcx, [rsp+378h+var_2C0]
0x18012b62c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18012b631  nop
0x18012b632  lea     rcx, [rsp+378h+var_2A0]
0x18012b63a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18012b63f  nop
0x18012b640  mov     dword ptr [rsp+378h+var_318], esi
0x18012b644  xorps   xmm0, xmm0
0x18012b647  movups  xmmword ptr [rsp+378h+phkResult], xmm0
0x18012b64f  lea     r9, [rsp+378h+var_318]
0x18012b654  lea     r8, [rsp+378h+phkResult]
0x18012b65c  mov     edx, 1
0x18012b661  mov     rcx, [rbx+170h]
0x18012b668  call    cs:__imp_ISO8601StringToSystemTime
0x18012b66e  mov     edi, eax
0x18012b670  test    eax, eax
0x18012b672  jns     short loc_18012B6D7
0x18012b674  mov     rcx, [rsp+378h]; this
0x18012b67c  mov     r9d, eax; char *
0x18012b67f  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012b686  mov     edx, 494h; void *
0x18012b68b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012b690  nop
0x18012b691  lea     rcx, [rsp+378h+var_2A0]
0x18012b699  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012b69e  nop
0x18012b69f  lea     rcx, [rsp+378h+var_2C0]
0x18012b6a7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012b6ac  nop
0x18012b6ad  lea     rcx, [rsp+378h+var_278]; this
0x18012b6b5  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012b6ba  nop
0x18012b6bb  lea     rcx, [rsp+378h+var_308]
0x18012b6c0  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x18012b6c5  nop
0x18012b6c6  lea     rcx, [rsp+378h+var_330]
0x18012b6cb  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012b6d0  mov     eax, edi
0x18012b6d2  jmp     loc_18012BEA3
0x18012b6d7  lea     rdx, [rsp+378h+var_2C0]
0x18012b6df  lea     rcx, [rsp+378h+phkResult]
0x18012b6e7  call    ?ConvertSystemTimeToString@@YAJAEAU_SYSTEMTIME@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConvertSystemTimeToString(_SYSTEMTIME &,std::wstring &)
0x18012b6ec  mov     edi, eax
0x18012b6ee  test    eax, eax
0x18012b6f0  jns     short loc_18012B755
0x18012b6f2  mov     rcx, [rsp+378h]; this
0x18012b6fa  mov     r9d, eax; char *
0x18012b6fd  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012b704  mov     edx, 495h; void *
0x18012b709  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012b70e  nop
0x18012b70f  lea     rcx, [rsp+378h+var_2A0]
0x18012b717  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012b71c  nop
0x18012b71d  lea     rcx, [rsp+378h+var_2C0]
0x18012b725  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012b72a  nop
0x18012b72b  lea     rcx, [rsp+378h+var_278]; this
0x18012b733  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012b738  nop
0x18012b739  lea     rcx, [rsp+378h+var_308]
0x18012b73e  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x18012b743  nop
0x18012b744  lea     rcx, [rsp+378h+var_330]
0x18012b749  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012b74e  mov     eax, edi
0x18012b750  jmp     loc_18012BEA3
0x18012b755  lea     rdx, aTheLastSync; "The last sync "
0x18012b75c  lea     rcx, [rsp+378h+var_2A0]
0x18012b764  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18012b769  cmp     [rbx+170h], rsi
0x18012b770  jz      short loc_18012B790
0x18012b772  cmp     [rbx+18Ch], esi
0x18012b778  jnz     short loc_18012B790
0x18012b77a  lea     rdx, aWasSuccessful; "was successful "
0x18012b781  lea     rcx, [rsp+378h+var_2A0]
0x18012b789  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18012b78e  jmp     short loc_18012B7A4
0x18012b790  lea     rdx, aFailed; "failed "
0x18012b797  lea     rcx, [rsp+378h+var_2A0]
0x18012b79f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18012b7a4  lea     rdx, [rsp+378h+var_2C0]
0x18012b7ac  lea     rcx, [rsp+378h+var_2A0]
0x18012b7b4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18012b7b9  lea     rcx, [rsp+378h+var_330]
0x18012b7be  call    ?clear@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x18012b7c3  lea     rdx, aLastSync; "Last sync"
0x18012b7ca  lea     rcx, [rsp+378h+var_2E0]
0x18012b7d2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012b7d7  nop
0x18012b7d8  mov     rdx, [rsp+378h+var_328]
0x18012b7dd  lea     rcx, [rsp+378h+var_330]
0x18012b7e2  cmp     rdx, [rsp+378h+var_320]
0x18012b7e7  jz      short loc_18012B7F8
0x18012b7e9  lea     rdx, [rsp+378h+var_2E0]
0x18012b7f1  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012b7f6  jmp     short loc_18012B806
0x18012b7f8  lea     r8, [rsp+378h+var_2E0]
0x18012b800  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012b805  nop
0x18012b806  lea     rcx, [rsp+378h+var_2E0]
0x18012b80e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012b813  lea     rcx, [rsp+378h+var_2A0]
0x18012b81b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18012b820  mov     rdx, rax
0x18012b823  lea     rcx, [rsp+378h+var_2E0]
0x18012b82b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012b830  nop
0x18012b831  mov     rdx, [rsp+378h+var_328]
0x18012b836  lea     rcx, [rsp+378h+var_330]
0x18012b83b  cmp     rdx, [rsp+378h+var_320]
0x18012b840  jz      short loc_18012B851
0x18012b842  lea     rdx, [rsp+378h+var_2E0]
0x18012b84a  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012b84f  jmp     short loc_18012B85F
0x18012b851  lea     r8, [rsp+378h+var_2E0]
0x18012b859  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012b85e  nop
0x18012b85f  lea     rcx, [rsp+378h+var_2E0]
0x18012b867  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012b86c  lea     rdx, [rsp+378h+var_330]
0x18012b871  lea     rcx, [rsp+378h+var_278]
0x18012b879  call    ?AddTableRow@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(std::vector<std::wstring> &)
0x18012b87e  mov     edi, eax
0x18012b880  test    eax, eax
0x18012b882  jns     short loc_18012B8E7
0x18012b884  mov     rcx, [rsp+378h]; this
0x18012b88c  mov     r9d, eax; char *
0x18012b88f  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012b896  mov     edx, 4A5h; void *
0x18012b89b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012b8a0  nop
0x18012b8a1  lea     rcx, [rsp+378h+var_2A0]
0x18012b8a9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012b8ae  nop
0x18012b8af  lea     rcx, [rsp+378h+var_2C0]
0x18012b8b7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012b8bc  nop
0x18012b8bd  lea     rcx, [rsp+378h+var_278]; this
0x18012b8c5  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012b8ca  nop
0x18012b8cb  lea     rcx, [rsp+378h+var_308]
  ... truncated ...
```

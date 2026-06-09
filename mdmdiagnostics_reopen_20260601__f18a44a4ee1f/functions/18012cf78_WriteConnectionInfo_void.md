# WriteConnectionInfo(void)

- ea: `0x18012cf78`
- end: `0x18012db3b`
- name: `?WriteConnectionInfo@@YAJXZ`
- size: `3011`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180128138`

## callees

- `0x180019080`
- `0x1800e4408`
- `0x1800e688c`
- `0x1800e68b0`
- `0x1800e7de8`
- `0x1800ed46c`
- `0x1800eef08`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f00ac`
- `0x1800f00e4`
- `0x1800fa538`
- `0x1800faa0c`
- `0x180105480`
- `0x18010562c`
- `0x180106b6c`
- `0x180106ee0`
- `0x18011273c`
- `0x18012944c`
- `0x180129aac`
- `0x180129ee0`
- `0x18012a29c`
- `0x18012a958`
- `0x18012af58`
- `0x18012cf78`
- `0x180132f50`
- `0x180133b9c`
- `0x180134e3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18012d7c4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18012d7c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18012d88d`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18012d88d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012d959`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012d959`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18012d6a3`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18012d6a3`
- `DMCmnUtils!DmRevertToSelf` at `0x18012d6ef`
- `DMCmnUtils!DmRevertToSelf` at `0x18012d783`
- `DMCmnUtils!DmRevertToSelf` at `0x18012d829`
- `DMCmnUtils!DmRevertToSelf` at `0x18012d8e7`
- `DMCmnUtils!DmRevertToSelf` at `0x18012da70`
- `DMCmnUtils!DmRevertToSelf` at `0x18012dacf`
- `DMCmnUtils!DmRevertToSelf` at `0x18012d6ef`
- `DMCmnUtils!DmRevertToSelf` at `0x18012d783`
- `DMCmnUtils!DmRevertToSelf` at `0x18012d829`
- `DMCmnUtils!DmRevertToSelf` at `0x18012d8e7`
- `DMCmnUtils!DmRevertToSelf` at `0x18012da70`
- `DMCmnUtils!DmRevertToSelf` at `0x18012dacf`
- `DMCmnUtils!DmImpersonate` at `0x18012d7dd`
- `DMCmnUtils!DmImpersonate` at `0x18012d7dd`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x18012d737`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x18012d737`
- `dmiso8601utils!ISO8601StringToSystemTime` at `0x18012d28c`
- `dmiso8601utils!ISO8601StringToSystemTime` at `0x18012d28c`

## string_xrefs

- `0x18012cfdc`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012d05c`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012d0c4`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012d1f1`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012d2a9`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012d327`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012d4b9`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012d617`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012d6c0`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012d754`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012d7fa`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012d8aa`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012da33`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15 #try_helpers=1
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
0x18012cf78  mov     [rsp+arg_0], rbx
0x18012cf7d  mov     [rsp+arg_8], rsi
0x18012cf82  push    rdi
0x18012cf83  sub     rsp, 370h
0x18012cf8a  mov     rax, cs:__security_cookie
0x18012cf91  xor     rax, rsp
0x18012cf94  mov     [rsp+378h+var_18], rax
0x18012cf9c  lea     rcx, [rsp+378h+var_330]
0x18012cfa1  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x18012cfa6  nop
0x18012cfa7  xorps   xmm1, xmm1
0x18012cfaa  movdqu  [rsp+378h+var_308], xmm1
0x18012cfb0  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18012cfb5  lea     rdx, [rsp+378h+var_308]
0x18012cfba  mov     rcx, rax
0x18012cfbd  call    ?GetEnrollmentId@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentId(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>> &)
0x18012cfc2  mov     ebx, eax
0x18012cfc4  xor     esi, esi
0x18012cfc6  test    eax, eax
0x18012cfc8  jns     short loc_18012D00A
0x18012cfca  cmp     eax, 80070490h
0x18012cfcf  jz      short loc_18012D012
0x18012cfd1  mov     rcx, [rsp+378h]; this
0x18012cfd9  mov     r9d, eax; char *
0x18012cfdc  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012cfe3  mov     edx, 478h; void *
0x18012cfe8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012cfed  nop
0x18012cfee  lea     rcx, [rsp+378h+var_308]
0x18012cff3  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x18012cff8  nop
0x18012cff9  lea     rcx, [rsp+378h+var_330]
0x18012cffe  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012d003  mov     eax, ebx
0x18012d005  jmp     loc_18012DB15
0x18012d00a  cmp     ebx, 80070490h
0x18012d010  jnz     short loc_18012D02E
0x18012d012  lea     rcx, [rsp+378h+var_308]
0x18012d017  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x18012d01c  nop
0x18012d01d  lea     rcx, [rsp+378h+var_330]
0x18012d022  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012d027  xor     eax, eax
0x18012d029  jmp     loc_18012DB15
0x18012d02e  mov     [rsp+378h+phkResult], rsi
0x18012d036  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18012d03b  lea     rdx, [rsp+378h+phkResult]; struct tagOMADMACCTINFO **
0x18012d043  mov     rcx, rax; this
0x18012d046  call    ?GetOmadmAccountInfo@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAPEBUtagOMADMACCTINFO@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetOmadmAccountInfo(tagOMADMACCTINFO const * &)
0x18012d04b  mov     ebx, eax
0x18012d04d  test    eax, eax
0x18012d04f  jns     short loc_18012D08A
0x18012d051  mov     rcx, [rsp+378h]; this
0x18012d059  mov     r9d, eax; char *
0x18012d05c  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012d063  mov     edx, 47Dh; void *
0x18012d068  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012d06d  nop
0x18012d06e  lea     rcx, [rsp+378h+var_308]
0x18012d073  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x18012d078  nop
0x18012d079  lea     rcx, [rsp+378h+var_330]
0x18012d07e  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012d083  mov     eax, ebx
0x18012d085  jmp     loc_18012DB15
0x18012d08a  lea     r8, aConnectioninfo; "ConnectionInfoTable"
0x18012d091  lea     rdx, aConnectionInfo; "Connection Info"
0x18012d098  lea     rcx, [rsp+378h+var_278]; this
0x18012d0a0  call    ??0SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@PEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::SimpleTable(ushort const *,ushort const *)
0x18012d0a5  nop
0x18012d0a6  lea     rcx, [rsp+378h+var_278]; this
0x18012d0ae  call    ?WriteSectionHeaderForTable@SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJXZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::WriteSectionHeaderForTable(void)
0x18012d0b3  mov     ebx, eax
0x18012d0b5  test    eax, eax
0x18012d0b7  jns     short loc_18012D100
0x18012d0b9  mov     rcx, [rsp+378h]; this
0x18012d0c1  mov     r9d, eax; char *
0x18012d0c4  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012d0cb  mov     edx, 480h; void *
0x18012d0d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012d0d5  nop
0x18012d0d6  lea     rcx, [rsp+378h+var_278]; this
0x18012d0de  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012d0e3  nop
0x18012d0e4  lea     rcx, [rsp+378h+var_308]
0x18012d0e9  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x18012d0ee  nop
0x18012d0ef  lea     rcx, [rsp+378h+var_330]
0x18012d0f4  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012d0f9  mov     eax, ebx
0x18012d0fb  jmp     loc_18012DB15
0x18012d100  mov     [rsp+378h+var_2F8], 104h
0x18012d10b  mov     rbx, [rsp+378h+phkResult]
0x18012d113  mov     rdx, [rbx+20h]
0x18012d117  lea     rcx, [rsp+378h+var_2A0]
0x18012d11f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012d124  nop
0x18012d125  lea     rdx, aManagedBy; "Managed by"
0x18012d12c  lea     rcx, [rsp+378h+var_2C0]
0x18012d134  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012d139  nop
0x18012d13a  mov     rdx, [rsp+378h+var_328]
0x18012d13f  lea     rcx, [rsp+378h+var_330]
0x18012d144  cmp     rdx, [rsp+378h+var_320]
0x18012d149  jz      short loc_18012D15A
0x18012d14b  lea     rdx, [rsp+378h+var_2C0]
0x18012d153  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012d158  jmp     short loc_18012D168
0x18012d15a  lea     r8, [rsp+378h+var_2C0]
0x18012d162  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012d167  nop
0x18012d168  lea     rcx, [rsp+378h+var_2C0]
0x18012d170  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d175  lea     rcx, [rsp+378h+var_2A0]
0x18012d17d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18012d182  mov     rdx, rax
0x18012d185  lea     rcx, [rsp+378h+var_2C0]
0x18012d18d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012d192  nop
0x18012d193  mov     rdx, [rsp+378h+var_328]
0x18012d198  lea     rcx, [rsp+378h+var_330]
0x18012d19d  cmp     rdx, [rsp+378h+var_320]
0x18012d1a2  jz      short loc_18012D1B3
0x18012d1a4  lea     rdx, [rsp+378h+var_2C0]
0x18012d1ac  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012d1b1  jmp     short loc_18012D1C1
0x18012d1b3  lea     r8, [rsp+378h+var_2C0]
0x18012d1bb  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012d1c0  nop
0x18012d1c1  lea     rcx, [rsp+378h+var_2C0]
0x18012d1c9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d1ce  lea     rdx, [rsp+378h+var_330]
0x18012d1d3  lea     rcx, [rsp+378h+var_278]
0x18012d1db  call    ?AddTableRow@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(std::vector<std::wstring> &)
0x18012d1e0  mov     edi, eax
0x18012d1e2  test    eax, eax
0x18012d1e4  jns     short loc_18012D23B
0x18012d1e6  mov     rcx, [rsp+378h]; this
0x18012d1ee  mov     r9d, eax; char *
0x18012d1f1  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012d1f8  mov     edx, 48Bh; void *
0x18012d1fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012d202  nop
0x18012d203  lea     rcx, [rsp+378h+var_2A0]
0x18012d20b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d210  nop
0x18012d211  lea     rcx, [rsp+378h+var_278]; this
0x18012d219  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012d21e  nop
0x18012d21f  lea     rcx, [rsp+378h+var_308]
0x18012d224  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x18012d229  nop
0x18012d22a  lea     rcx, [rsp+378h+var_330]
0x18012d22f  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012d234  mov     eax, edi
0x18012d236  jmp     loc_18012DB15
0x18012d23b  lea     rcx, [rsp+378h+var_2A0]
0x18012d243  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d248  lea     rcx, [rsp+378h+var_2C0]
0x18012d250  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18012d255  nop
0x18012d256  lea     rcx, [rsp+378h+var_2A0]
0x18012d25e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18012d263  nop
0x18012d264  mov     dword ptr [rsp+378h+var_318], esi
0x18012d268  xorps   xmm0, xmm0
0x18012d26b  movups  xmmword ptr [rsp+378h+phkResult], xmm0
0x18012d273  lea     r9, [rsp+378h+var_318]
0x18012d278  lea     r8, [rsp+378h+phkResult]
0x18012d280  mov     edx, 1
0x18012d285  mov     rcx, [rbx+170h]
0x18012d28c  call    cs:__imp_ISO8601StringToSystemTime
0x18012d293  nop     dword ptr [rax+rax+00h]
0x18012d298  mov     edi, eax
0x18012d29a  test    eax, eax
0x18012d29c  jns     short loc_18012D301
0x18012d29e  mov     rcx, [rsp+378h]; this
0x18012d2a6  mov     r9d, eax; char *
0x18012d2a9  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012d2b0  mov     edx, 494h; void *
0x18012d2b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012d2ba  nop
0x18012d2bb  lea     rcx, [rsp+378h+var_2A0]
0x18012d2c3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d2c8  nop
0x18012d2c9  lea     rcx, [rsp+378h+var_2C0]
0x18012d2d1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d2d6  nop
0x18012d2d7  lea     rcx, [rsp+378h+var_278]; this
0x18012d2df  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012d2e4  nop
0x18012d2e5  lea     rcx, [rsp+378h+var_308]
0x18012d2ea  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x18012d2ef  nop
0x18012d2f0  lea     rcx, [rsp+378h+var_330]
0x18012d2f5  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012d2fa  mov     eax, edi
0x18012d2fc  jmp     loc_18012DB15
0x18012d301  lea     rdx, [rsp+378h+var_2C0]
0x18012d309  lea     rcx, [rsp+378h+phkResult]
0x18012d311  call    ?ConvertSystemTimeToString@@YAJAEAU_SYSTEMTIME@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConvertSystemTimeToString(_SYSTEMTIME &,std::wstring &)
0x18012d316  mov     edi, eax
0x18012d318  test    eax, eax
0x18012d31a  jns     short loc_18012D37F
0x18012d31c  mov     rcx, [rsp+378h]; this
0x18012d324  mov     r9d, eax; char *
0x18012d327  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012d32e  mov     edx, 495h; void *
0x18012d333  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012d338  nop
0x18012d339  lea     rcx, [rsp+378h+var_2A0]
0x18012d341  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d346  nop
0x18012d347  lea     rcx, [rsp+378h+var_2C0]
0x18012d34f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d354  nop
0x18012d355  lea     rcx, [rsp+378h+var_278]; this
0x18012d35d  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012d362  nop
0x18012d363  lea     rcx, [rsp+378h+var_308]
0x18012d368  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x18012d36d  nop
0x18012d36e  lea     rcx, [rsp+378h+var_330]
0x18012d373  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012d378  mov     eax, edi
0x18012d37a  jmp     loc_18012DB15
0x18012d37f  lea     rdx, aTheLastSync; "The last sync "
0x18012d386  lea     rcx, [rsp+378h+var_2A0]
0x18012d38e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18012d393  cmp     [rbx+170h], rsi
0x18012d39a  jz      short loc_18012D3BA
0x18012d39c  cmp     [rbx+18Ch], esi
0x18012d3a2  jnz     short loc_18012D3BA
0x18012d3a4  lea     rdx, aWasSuccessful; "was successful "
0x18012d3ab  lea     rcx, [rsp+378h+var_2A0]
0x18012d3b3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18012d3b8  jmp     short loc_18012D3CE
0x18012d3ba  lea     rdx, aFailed; "failed "
0x18012d3c1  lea     rcx, [rsp+378h+var_2A0]
0x18012d3c9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18012d3ce  lea     rdx, [rsp+378h+var_2C0]
0x18012d3d6  lea     rcx, [rsp+378h+var_2A0]
0x18012d3de  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18012d3e3  lea     rcx, [rsp+378h+var_330]
0x18012d3e8  call    ?clear@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x18012d3ed  lea     rdx, aLastSync; "Last sync"
0x18012d3f4  lea     rcx, [rsp+378h+var_2E0]
0x18012d3fc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012d401  nop
0x18012d402  mov     rdx, [rsp+378h+var_328]
0x18012d407  lea     rcx, [rsp+378h+var_330]
0x18012d40c  cmp     rdx, [rsp+378h+var_320]
0x18012d411  jz      short loc_18012D422
0x18012d413  lea     rdx, [rsp+378h+var_2E0]
0x18012d41b  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012d420  jmp     short loc_18012D430
0x18012d422  lea     r8, [rsp+378h+var_2E0]
0x18012d42a  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012d42f  nop
0x18012d430  lea     rcx, [rsp+378h+var_2E0]
0x18012d438  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d43d  lea     rcx, [rsp+378h+var_2A0]
0x18012d445  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18012d44a  mov     rdx, rax
0x18012d44d  lea     rcx, [rsp+378h+var_2E0]
0x18012d455  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012d45a  nop
0x18012d45b  mov     rdx, [rsp+378h+var_328]
0x18012d460  lea     rcx, [rsp+378h+var_330]
0x18012d465  cmp     rdx, [rsp+378h+var_320]
0x18012d46a  jz      short loc_18012D47B
0x18012d46c  lea     rdx, [rsp+378h+var_2E0]
0x18012d474  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012d479  jmp     short loc_18012D489
0x18012d47b  lea     r8, [rsp+378h+var_2E0]
0x18012d483  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012d488  nop
0x18012d489  lea     rcx, [rsp+378h+var_2E0]
0x18012d491  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d496  lea     rdx, [rsp+378h+var_330]
0x18012d49b  lea     rcx, [rsp+378h+var_278]
0x18012d4a3  call    ?AddTableRow@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(std::vector<std::wstring> &)
0x18012d4a8  mov     edi, eax
0x18012d4aa  test    eax, eax
0x18012d4ac  jns     short loc_18012D511
0x18012d4ae  mov     rcx, [rsp+378h]; this
0x18012d4b6  mov     r9d, eax; char *
0x18012d4b9  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012d4c0  mov     edx, 4A5h; void *
0x18012d4c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012d4ca  nop
0x18012d4cb  lea     rcx, [rsp+378h+var_2A0]
0x18012d4d3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d4d8  nop
0x18012d4d9  lea     rcx, [rsp+378h+var_2C0]
0x18012d4e1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d4e6  nop
0x18012d4e7  lea     rcx, [rsp+378h+var_278]; this
0x18012d4ef  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012d4f4  nop
  ... truncated ...
```

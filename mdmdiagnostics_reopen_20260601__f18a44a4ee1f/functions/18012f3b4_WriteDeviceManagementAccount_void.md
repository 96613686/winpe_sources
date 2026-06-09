# WriteDeviceManagementAccount(void)

- ea: `0x18012f3b4`
- end: `0x1801305b2`
- name: `?WriteDeviceManagementAccount@@YAJXZ`
- size: `4606`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180128138`

## callees

- `0x180019080`
- `0x18001a054`
- `0x1800e68b0`
- `0x1800e734c`
- `0x1800e7de8`
- `0x1800e8508`
- `0x1800ed46c`
- `0x1800eef08`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f99d4`
- `0x1800faa0c`
- `0x180105480`
- `0x180105e98`
- `0x180105f3c`
- `0x180106b6c`
- `0x180106ee0`
- `0x1801081c4`
- `0x180108a90`
- `0x180109344`
- `0x18012944c`
- `0x180129aac`
- `0x180129ee0`
- `0x18012a958`
- `0x18012ac74`
- `0x18012b39c`
- `0x18012b470`
- `0x18012e790`
- `0x18012f3b4`
- `0x180132f50`
- `0x180134d60`
- `0x180134e3c`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18012f6c8`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18012f873`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18012f6c8`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18012f873`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1801300a2`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1801300a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012f79e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012f96f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180130170`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012f79e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012f96f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180130170`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012f759`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012f92a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012f759`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012f92a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012fb7b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012fd08`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012feea`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180130257`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012fb7b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012fd08`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012feea`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180130257`

## string_xrefs

- `0x18012f447`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012f648`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012f816`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012f9f7`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012faa6`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012fc4f`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012fe2e`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012ffc8`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x1801300cc`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18013019a`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180130342`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180130494`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012ff00`: `OMADM protocol version`
- `0x18013041d`: `Unconfigured`
- `0x18012f5a1`: `LinkedEnrollmentAccountTable`
- `0x18012f58c`: `Linked Enrollment Account`

## pseudocode

```c
// Hidden C++ exception states: #wind=26 #try_helpers=1
__int64 WriteDeviceManagementAccount(void)
{
  __int64 v0; // rcx
  int v1; // eax
  unsigned int v2; // ebx
  __int64 v4; // rax
  char v5; // di
  __int64 i; // rbx
  __int64 v7; // rsi
  const unsigned __int16 *v8; // rax
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v9; // rcx
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v10; // rax
  int EnrollmentId; // eax
  signed int v12; // ebx
  __int64 v13; // rdx
  char IsStateSeparationEnabled; // al
  const wchar_t *v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rax
  const WCHAR *v18; // rax
  unsigned int v19; // edi
  char v20; // al
  const wchar_t *v21; // rdx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  HKEY v25; // rdi
  const WCHAR *v26; // rax
  bool v27; // sf
  int v28; // eax
  unsigned int v29; // ebx
  int v30; // eax
  unsigned int v31; // ebx
  __int64 v32; // rax
  __int64 v33; // rdx
  int v34; // eax
  unsigned int v35; // ebx
  int v36; // eax
  unsigned int v37; // ebx
  LSTATUS v38; // eax
  unsigned int v39; // ebx
  LSTATUS v40; // eax
  unsigned int v41; // ebx
  LSTATUS ValueW; // eax
  bool v43; // sf
  int v44; // eax
  unsigned int v45; // ebx
  int v46; // eax
  unsigned int v47; // ebx
  int phkResult; // [rsp+20h] [rbp-5F8h]
  int phkResulta; // [rsp+20h] [rbp-5F8h]
  int phkResultb; // [rsp+20h] [rbp-5F8h]
  int phkResultc; // [rsp+20h] [rbp-5F8h]
  int phkResultd; // [rsp+20h] [rbp-5F8h]
  int phkResulte; // [rsp+20h] [rbp-5F8h]
  int phkResultf; // [rsp+20h] [rbp-5F8h]
  int phkResultg; // [rsp+20h] [rbp-5F8h]
  int phkResulth; // [rsp+20h] [rbp-5F8h]
  __int128 v57; // [rsp+40h] [rbp-5D8h] BYREF
  __int64 v58; // [rsp+50h] [rbp-5C8h]
  DWORD pcbData; // [rsp+58h] [rbp-5C0h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-5B8h] BYREF
  HKEY v61; // [rsp+68h] [rbp-5B0h] BYREF
  DWORD cchName; // [rsp+70h] [rbp-5A8h] BYREF
  HKEY hkey; // [rsp+78h] [rbp-5A0h] BYREF
  _BYTE v64[8]; // [rsp+80h] [rbp-598h] BYREF
  __int128 v65; // [rsp+88h] [rbp-590h] BYREF
  _BYTE v66[32]; // [rsp+A0h] [rbp-578h] BYREF
  __int128 v67; // [rsp+C0h] [rbp-558h] BYREF
  __int64 v68; // [rsp+D0h] [rbp-548h]
  __int64 v69; // [rsp+D8h] [rbp-540h]
  _BYTE v70[32]; // [rsp+E0h] [rbp-538h] BYREF
  _BYTE v71[32]; // [rsp+100h] [rbp-518h] BYREF
  _BYTE v72[80]; // [rsp+120h] [rbp-4F8h] BYREF
  _BYTE v73[32]; // [rsp+170h] [rbp-4A8h] BYREF
  _BYTE v74[42]; // [rsp+190h] [rbp-488h] BYREF
  _BYTE v75[6]; // [rsp+1BAh] [rbp-45Eh] BYREF
  int pvData; // [rsp+1C0h] [rbp-458h] BYREF
  _BYTE v77[524]; // [rsp+1C4h] [rbp-454h] BYREF
  WCHAR Name; // [rsp+3D0h] [rbp-248h] BYREF
  _BYTE v79[526]; // [rsp+3D2h] [rbp-246h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+618h] [rbp+0h]

  v58 = 0;
  v57 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_DMDiagLinkedEnrollment>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_DMDiagLinkedEnrollment>::GetImpl'::`2'::impl) )
  {
    Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
    v1 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::ListEnrollmentId(v0, &v57);
    v2 = v1;
    v67 = 0;
    v68 = 0;
    v69 = 7;
    LOWORD(v67) = 0;
    if ( v1 >= 0 )
    {
      v4 = std::vector<std::wstring>::vector<std::wstring>(&v65, &v57);
      v5 = IsDeviceMMPCDualEnrolled(v4);
      v7 = *((_QWORD *)&v57 + 1);
      for ( i = v57; i != v7; i += 32 )
      {
        pcbData = 63;
        Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
        v8 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i);
        Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentType(v9, v8, &pcbData);
        if ( !v5 || ((pcbData - 24) & 0xFFFFFFFD) != 0 )
        {
          std::wstring::wstring(v70, L"Device Management Account");
          std::wstring::wstring(v66, L"DeviceManagementAccountTable");
          WriteDeviceManagementAccount(i, v70, v66);
          std::wstring::_Tidy_deallocate(v66);
          std::wstring::_Tidy_deallocate(v70);
        }
        else
        {
          std::wstring::operator=(&v67, i);
        }
      }
      if ( v5 && v68 )
      {
        std::wstring::wstring(v70, L"Linked Enrollment Account");
        std::wstring::wstring(v66, L"LinkedEnrollmentAccountTable");
        WriteDeviceManagementAccount(&v67, v70, v66);
        std::wstring::_Tidy_deallocate(v66);
        std::wstring::_Tidy_deallocate(v70);
      }
    }
    else if ( v1 != -2147023728 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x57B,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
        (const char *)(unsigned int)v1,
        phkResult);
      std::wstring::_Tidy_deallocate(&v67);
      std::vector<std::wstring>::_Tidy(&v57);
      return v2;
    }
    std::wstring::_Tidy_deallocate(&v67);
    std::vector<std::wstring>::_Tidy(&v57);
    return 0;
  }
  else
  {
    v65 = 0;
    v10 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
    EnrollmentId = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentId(v10, &v65);
    v12 = EnrollmentId;
    if ( EnrollmentId >= 0 )
    {
      hKey = 0;
      if ( (_QWORD)v65 )
        v13 = *(_QWORD *)v65;
      else
        v13 = 0;
      std::wstring::wstring(v71, v13);
      IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
      v15 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM\\Accounts";
      if ( !IsStateSeparationEnabled )
        v15 = L"Software\\Microsoft\\Provisioning\\OMADM\\Accounts";
      v16 = std::wstring::wstring(v66, v15);
      v17 = std::operator+<unsigned short>(v73, v16, L"\\");
      std::operator+<unsigned short>(v70, v17, v71);
      std::wstring::_Tidy_deallocate(v73);
      std::wstring::_Tidy_deallocate(v66);
      hKey = 0;
      v18 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v70);
      if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, v18, 0, 0x20019u, &hKey) == 2 )
      {
        std::wstring::_Tidy_deallocate(v70);
        std::wstring::_Tidy_deallocate(v71);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v65);
        std::vector<std::wstring>::_Tidy(&v57);
        return 0;
      }
      if ( v12 > 0 )
        v19 = (unsigned __int16)v12 | 0x80070000;
      else
        v19 = v12;
      if ( (v19 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5A9,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
          (const char *)v19,
          phkResulta);
        std::wstring::_Tidy_deallocate(v70);
        std::wstring::_Tidy_deallocate(v71);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v65);
        std::vector<std::wstring>::_Tidy(&v57);
        return v19;
      }
      v61 = 0;
      v20 = RtlIsStateSeparationEnabled();
      v21 = L"OSData\\Software\\Microsoft\\Enrollments";
      if ( !v20 )
        v21 = L"Software\\Microsoft\\Enrollments";
      v22 = std::wstring::wstring(v74, v21);
      v23 = std::operator+<unsigned short>(v66, v22, L"\\");
      v24 = std::operator+<unsigned short>(v73, v23, v71);
      std::operator+<unsigned short>(&v67, v24, L"\\DMClient");
      std::wstring::_Tidy_deallocate(v73);
      std::wstring::_Tidy_deallocate(v66);
      std::wstring::_Tidy_deallocate(v74);
      v25 = v61;
      if ( v61 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&hkey);
        RegCloseKey(v25);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&hkey);
      }
      v61 = 0;
      v26 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v67);
      if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, v26, 0, 0x20019u, &v61) == 2 )
      {
        std::wstring::_Tidy_deallocate(&v67);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v61);
        std::wstring::_Tidy_deallocate(v70);
        std::wstring::_Tidy_deallocate(v71);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v65);
        std::vector<std::wstring>::_Tidy(&v57);
        return 0;
      }
      v27 = v12 < 0;
      if ( v12 > 0 )
      {
        v12 = (unsigned __int16)v12 | 0x80070000;
        v27 = v12 < 0;
      }
      if ( v27 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5B0,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
          (const char *)(unsigned int)v12,
          phkResultb);
        std::wstring::_Tidy_deallocate(&v67);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v61);
        std::wstring::_Tidy_deallocate(v70);
        std::wstring::_Tidy_deallocate(v71);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v65);
        std::vector<std::wstring>::_Tidy(&v57);
        return (unsigned int)v12;
      }
      Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::SimpleTable(
        (Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v72,
        L"Device Management Account",
        L"DeviceManagementAccountTable");
      v28 = Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::WriteSectionHeaderForTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v72);
      v29 = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5B3,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
          (const char *)(unsigned int)v28,
          phkResultb);
        Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v72);
        std::wstring::_Tidy_deallocate(&v67);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v61);
        std::wstring::_Tidy_deallocate(v70);
        std::wstring::_Tidy_deallocate(v71);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v65);
        std::vector<std::wstring>::_Tidy(&v57);
        return v29;
      }
      pvData = 0;
      memset_0(v77, 0, 0x204u);
      pcbData = 260;
      RegGetValueW(hKey, 0, L"AcctUId", 2u, 0, &pvData, &pcbData);
      std::wstring::wstring(v66, L"Account UID");
      if ( *((_QWORD *)&v57 + 1) == v58 )
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v57, *((_QWORD *)&v57 + 1), v66);
      else
        std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(&v57, v66);
      std::wstring::_Tidy_deallocate(v66);
      std::wstring::wstring(v66, &pvData);
      if ( *((_QWORD *)&v57 + 1) == v58 )
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v57, *((_QWORD *)&v57 + 1), v66);
      else
        std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(&v57, v66);
      std::wstring::_Tidy_deallocate(v66);
      v30 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v72, &v57);
      v31 = v30;
      if ( v30 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5BE,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
          (const char *)(unsigned int)v30,
          phkResultc);
        Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v72);
        std::wstring::_Tidy_deallocate(&v67);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v61);
        std::wstring::_Tidy_deallocate(v70);
        std::wstring::_Tidy_deallocate(v71);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v65);
        std::vector<std::wstring>::_Tidy(&v57);
        return v31;
      }
      cchName = 0;
      pcbData = 4;
      RegGetValueW(hKey, 0, L"Flags", 0x10u, 0, &cchName, &pcbData);
      std::vector<std::wstring>::clear(&v57);
      std::wstring::wstring(v66, L"Flags");
      if ( *((_QWORD *)&v57 + 1) == v58 )
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v57, *((_QWORD *)&v57 + 1), v66);
      else
        std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(&v57, v66);
      std::wstring::_Tidy_deallocate(v66);
      v32 = std::_UIntegral_to_buff<unsigned short,unsigned int>(v75, cchName);
      std::wstring::wstring(v73, v32, v75, v64);
      v33 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v73);
      std::wstring::wstring(v66, v33);
      if ( *((_QWORD *)&v57 + 1) == v58 )
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v57, *((_QWORD *)&v57 + 1), v66);
      else
        std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(&v57, v66);
      std::wstring::_Tidy_deallocate(v66);
      std::wstring::_Tidy_deallocate(v73);
      v34 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v72, &v57);
      v35 = v34;
      if ( v34 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5CA,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
          (const char *)(unsigned int)v34,
          phkResultd);
        Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v72);
        std::wstring::_Tidy_deallocate(&v67);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v61);
        std::wstring::_Tidy_deallocate(v70);
        std::wstring::_Tidy_deallocate(v71);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v65);
        std::vector<std::wstring>::_Tidy(&v57);
        return v35;
      }
      LOWORD(pvData) = 0;
      pcbData = 260;
      RegGetValueW(hKey, 0, L"ProtoVer", 2u, 0, &pvData, &pcbData);
      std::vector<std::wstring>::clear(&v57);
      std::wstring::wstring(v66, L"OMADM protocol version");
      if ( *((_QWORD *)&v57 + 1) == v58 )
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v57, *((_QWORD *)&v57 + 1), v66);
      else
        std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(&v57, v66);
      std::wstring::_Tidy_deallocate(v66);
      std::wstring::wstring(v66, &pvData);
      if ( *((_QWORD *)&v57 + 1) == v58 )
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v57, *((_QWORD *)&v57 + 1), v66);
      else
        std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(&v57, v66);
      std::wstring::_Tidy_deallocate(v66);
      v36 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v72, &v57);
      v37 = v36;
      if ( v36 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5D6,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
          (const char *)(unsigned int)v36,
          phkResulte);
        Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v72);
        std::wstring::_Tidy_deallocate(&v67);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v61);
        std::wstring::_Tidy_deallocate(v70);
        std::wstring::_Tidy_deallocate(v71);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v65);
        std::vector<std::wstring>::_Tidy(&v57);
        return v37;
      }
      LOWORD(pvData) = 0;
      pcbData = 260;
      cchName = 261;
      Name = 0;
      memset_0(v79, 0, 0x208u);
      v38 = RegEnumKeyExW(v61, 0, &Name, &cchName, 0, 0, 0, 0);
      v39 = v38;
      if ( v38 > 0 )
        v39 = (unsigned __int16)v38 | 0x80070000;
      if ( (v39 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5E2,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
          (const char *)v39,
          phkResultf);
        Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v72);
        std::wstring::_Tidy_deallocate(&v67);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v61);
        std::wstring::_Tidy_deallocate(v70);
        std::wstring::_Tidy_deallocate(v71);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v65);
        std::vector<std::wstring>::_Tidy(&v57);
        return v39;
      }
      hkey = 0;
      v40 = RegOpenKeyExW(v61, &Name, 0, 0x20019u, &hkey);
      v41 = v40;
      if ( v40 > 0 )
        v41 = (unsigned __int16)v40 | 0x80070000;
      if ( (v41 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5E4,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
          (const char *)v41,
          phkResultg);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v72);
        std::wstring::_Tidy_deallocate(&v67);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v61);
        std::wstring::_Tidy_deallocate(v70);
        std::wstring::_Tidy_deallocate(v71);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v65);
        std::vector<std::wstring>::_Tidy(&v57);
        return v41;
      }
      ValueW = RegGetValueW(hkey, 0, L"EntDMID", 2u, 0, &pvData, &pcbData);
      v43 = ValueW < 0;
      if ( ValueW > 0 )
        v43 = 1;
      if ( v43 )
      {
        std::vector<std::wstring>::clear(&v57);
        std::wstring::wstring(v66, L"EntDMID");
        if ( *((_QWORD *)&v57 + 1) == v58 )
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v57, *((_QWORD *)&v57 + 1), v66);
        else
          std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(&v57, v66);
        std::wstring::_Tidy_deallocate(v66);
        std::wstring::wstring(v66, L"Unconfigured");
        if ( *((_QWORD *)&v57 + 1) == v58 )
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v57, *((_QWORD *)&v57 + 1), v66);
        else
          std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(&v57, v66);
        std::wstring::_Tidy_deallocate(v66);
        v46 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v72, &v57);
        v47 = v46;
        if ( v46 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5F2,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
            (const char *)(unsigned int)v46,
            phkResulth);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v72);
          std::wstring::_Tidy_deallocate(&v67);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v61);
          std::wstring::_Tidy_deallocate(v70);
          std::wstring::_Tidy_deallocate(v71);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v65);
          std::vector<std::wstring>::_Tidy(&v57);
          return v47;
        }
      }
      else
      {
        std::vector<std::wstring>::clear(&v57);
        std::wstring::wstring(v66, L"EntDMID");
        if ( *((_QWORD *)&v57 + 1) == v58 )
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v57, *((_QWORD *)&v57 + 1), v66);
        else
          std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(&v57, v66);
        std::wstring::_Tidy_deallocate(v66);
        std::wstring::wstring(v66, &pvData);
        if ( *((_QWORD *)&v57 + 1) == v58 )
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v57, *((_QWORD *)&v57 + 1), v66);
        else
          std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(&v57, v66);
        std::wstring::_Tidy_deallocate(v66);
        v44 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v72, &v57);
        v45 = v44;
        if ( v44 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5EB,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
            (const char *)(unsigned int)v44,
            phkResulth);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v72);
          std::wstring::_Tidy_deallocate(&v67);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v61);
          std::wstring::_Tidy_deallocate(v70);
          std::wstring::_Tidy_deallocate(v71);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v65);
          std::vector<std::wstring>::_Tidy(&v57);
          return v45;
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v72);
      std::wstring::_Tidy_deallocate(&v67);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v61);
      std::wstring::_Tidy_deallocate(v70);
      std::wstring::_Tidy_deallocate(v71);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v65);
      std::vector<std::wstring>::_Tidy(&v57);
      return 0;
    }
    else if ( EnrollmentId == -2147023728 )
    {
      std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v65);
      std::vector<std::wstring>::_Tidy(&v57);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5A0,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
        (const char *)(unsigned int)EnrollmentId,
        phkResult);
      std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v65);
      std::vector<std::wstring>::_Tidy(&v57);
      return (unsigned int)v12;
    }
  }
}

```

## disassembly

```asm
0x18012f3b4  push    rbx
0x18012f3b6  push    rsi
0x18012f3b7  push    rdi
0x18012f3b8  push    r14
0x18012f3ba  sub     rsp, 5F8h
0x18012f3c1  mov     rax, cs:__security_cookie
0x18012f3c8  xor     rax, rsp
0x18012f3cb  mov     [rsp+618h+var_38], rax
0x18012f3d3  xor     r14d, r14d
0x18012f3d6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_DMDiagLinkedEnrollment@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_DMDiagLinkedEnrollment@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_DMDiagLinkedEnrollment> `wil::Feature<__WilFeatureTraits_Feature_Servicing_DMDiagLinkedEnrollment>::GetImpl(void)'::`2'::impl
0x18012f3dd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_DMDiagLinkedEnrollment@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_DMDiagLinkedEnrollment>::__private_IsEnabled(void)
0x18012f3e2  xorps   xmm0, xmm0
0x18012f3e5  mov     [rsp+618h+var_5C8], r14
0x18012f3ea  movdqu  [rsp+618h+var_5D8], xmm0
0x18012f3f0  test    al, al
0x18012f3f2  jz      loc_18012F60F
0x18012f3f8  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18012f3fd  lea     rdx, [rsp+618h+var_5D8]
0x18012f402  call    ?ListEnrollmentId@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::ListEnrollmentId(std::vector<std::wstring> &)
0x18012f407  mov     ebx, eax
0x18012f409  xorps   xmm0, xmm0
0x18012f40c  movups  [rsp+618h+var_558], xmm0
0x18012f414  mov     [rsp+618h+var_548], r14
0x18012f41c  mov     [rsp+618h+var_540], 7
0x18012f428  mov     word ptr [rsp+618h+var_558], r14w
0x18012f431  test    eax, eax
0x18012f433  jns     short loc_18012F478
0x18012f435  cmp     eax, 80070490h
0x18012f43a  jz      short loc_18012F480
0x18012f43c  mov     rcx, [rsp+618h]; this
0x18012f444  mov     r9d, eax; char *
0x18012f447  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012f44e  mov     edx, 57Bh; void *
0x18012f453  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f458  nop
0x18012f459  lea     rcx, [rsp+618h+var_558]
0x18012f461  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012f466  nop
0x18012f467  lea     rcx, [rsp+618h+var_5D8]
0x18012f46c  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012f471  mov     eax, ebx
0x18012f473  jmp     loc_180130594
0x18012f478  cmp     ebx, 80070490h
0x18012f47e  jnz     short loc_18012F49F
0x18012f480  lea     rcx, [rsp+618h+var_558]
0x18012f488  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012f48d  nop
0x18012f48e  lea     rcx, [rsp+618h+var_5D8]
0x18012f493  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012f498  xor     eax, eax
0x18012f49a  jmp     loc_180130594
0x18012f49f  lea     rdx, [rsp+618h+var_5D8]
0x18012f4a4  lea     rcx, [rsp+618h+var_590]
0x18012f4ac  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x18012f4b1  mov     rcx, rax
0x18012f4b4  call    ?IsDeviceMMPCDualEnrolled@@YA_NV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; IsDeviceMMPCDualEnrolled(std::vector<std::wstring>)
0x18012f4b9  mov     dil, al
0x18012f4bc  mov     rbx, qword ptr [rsp+618h+var_5D8]
0x18012f4c1  mov     rsi, qword ptr [rsp+618h+var_5D8+8]
0x18012f4c6  cmp     rbx, rsi
0x18012f4c9  jz      loc_18012F57D
0x18012f4cf  mov     [rsp+618h+var_5C0], 3Fh ; '?'
0x18012f4d7  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18012f4dc  mov     rcx, rbx
0x18012f4df  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18012f4e4  lea     r8, [rsp+618h+var_5C0]; unsigned int *
0x18012f4e9  mov     rdx, rax; unsigned __int16 *
0x18012f4ec  call    ?GetEnrollmentType@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJPEBGPEAK@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentType(ushort const *,ulong *)
0x18012f4f1  test    dil, dil
0x18012f4f4  jz      short loc_18012F516
0x18012f4f6  mov     eax, [rsp+618h+var_5C0]
0x18012f4fa  add     eax, 0FFFFFFE8h
0x18012f4fd  test    eax, 0FFFFFFFDh
0x18012f502  jnz     short loc_18012F516
0x18012f504  mov     rdx, rbx
0x18012f507  lea     rcx, [rsp+618h+var_558]
0x18012f50f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18012f514  jmp     short loc_18012F574
0x18012f516  lea     rdx, aDeviceManageme_2; "Device Management Account"
0x18012f51d  lea     rcx, [rsp+618h+var_538]
0x18012f525  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012f52a  nop
0x18012f52b  lea     rdx, aDevicemanageme; "DeviceManagementAccountTable"
0x18012f532  lea     rcx, [rsp+618h+var_578]
0x18012f53a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012f53f  nop
0x18012f540  lea     r8, [rsp+618h+var_578]
0x18012f548  lea     rdx, [rsp+618h+var_538]
0x18012f550  mov     rcx, rbx
0x18012f553  call    ?WriteDeviceManagementAccount@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z; WriteDeviceManagementAccount(std::wstring &,std::wstring &,std::wstring &)
0x18012f558  nop
0x18012f559  lea     rcx, [rsp+618h+var_578]
0x18012f561  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012f566  nop
0x18012f567  lea     rcx, [rsp+618h+var_538]
0x18012f56f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012f574  add     rbx, 20h ; ' '
0x18012f578  jmp     loc_18012F4C6
0x18012f57d  test    dil, dil
0x18012f580  jz      short loc_18012F5F0
0x18012f582  cmp     [rsp+618h+var_548], r14
0x18012f58a  jz      short loc_18012F5F0
0x18012f58c  lea     rdx, aLinkedEnrollme; "Linked Enrollment Account"
0x18012f593  lea     rcx, [rsp+618h+var_538]
0x18012f59b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012f5a0  nop
0x18012f5a1  lea     rdx, aLinkedenrollme_0; "LinkedEnrollmentAccountTable"
0x18012f5a8  lea     rcx, [rsp+618h+var_578]
0x18012f5b0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012f5b5  nop
0x18012f5b6  lea     r8, [rsp+618h+var_578]
0x18012f5be  lea     rdx, [rsp+618h+var_538]
0x18012f5c6  lea     rcx, [rsp+618h+var_558]
0x18012f5ce  call    ?WriteDeviceManagementAccount@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z; WriteDeviceManagementAccount(std::wstring &,std::wstring &,std::wstring &)
0x18012f5d3  nop
0x18012f5d4  lea     rcx, [rsp+618h+var_578]
0x18012f5dc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012f5e1  nop
0x18012f5e2  lea     rcx, [rsp+618h+var_538]
0x18012f5ea  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012f5ef  nop
0x18012f5f0  lea     rcx, [rsp+618h+var_558]
0x18012f5f8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012f5fd  nop
0x18012f5fe  lea     rcx, [rsp+618h+var_5D8]
0x18012f603  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012f608  xor     eax, eax
0x18012f60a  jmp     loc_180130594
0x18012f60f  xorps   xmm1, xmm1
0x18012f612  movdqu  [rsp+618h+var_590], xmm1
0x18012f61b  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18012f620  lea     rdx, [rsp+618h+var_590]
0x18012f628  mov     rcx, rax
0x18012f62b  call    ?GetEnrollmentId@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentId(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>> &)
0x18012f630  mov     ebx, eax
0x18012f632  test    eax, eax
0x18012f634  jns     short loc_18012F679
0x18012f636  cmp     eax, 80070490h
0x18012f63b  jz      short loc_18012F681
0x18012f63d  mov     rcx, [rsp+618h]; this
0x18012f645  mov     r9d, eax; char *
0x18012f648  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012f64f  mov     edx, 5A0h; void *
0x18012f654  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f659  nop
0x18012f65a  lea     rcx, [rsp+618h+var_590]
0x18012f662  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x18012f667  nop
0x18012f668  lea     rcx, [rsp+618h+var_5D8]
0x18012f66d  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012f672  mov     eax, ebx
0x18012f674  jmp     loc_180130594
0x18012f679  cmp     ebx, 80070490h
0x18012f67f  jnz     short loc_18012F6A0
0x18012f681  lea     rcx, [rsp+618h+var_590]
0x18012f689  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x18012f68e  nop
0x18012f68f  lea     rcx, [rsp+618h+var_5D8]
0x18012f694  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012f699  xor     eax, eax
0x18012f69b  jmp     loc_180130594
0x18012f6a0  mov     [rsp+618h+hKey], r14
0x18012f6a5  mov     rax, qword ptr [rsp+618h+var_590]
0x18012f6ad  test    rax, rax
0x18012f6b0  jz      short loc_18012F6B7
0x18012f6b2  mov     rdx, [rax]
0x18012f6b5  jmp     short loc_18012F6BA
0x18012f6b7  mov     rdx, r14
0x18012f6ba  lea     rcx, [rsp+618h+var_518]
0x18012f6c2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012f6c7  nop
0x18012f6c8  call    cs:__imp_RtlIsStateSeparationEnabled
0x18012f6cf  nop     dword ptr [rax+rax+00h]
0x18012f6d4  lea     rcx, aSoftwareMicros_1; "Software\\Microsoft\\Provisioning\\OMAD"...
0x18012f6db  lea     rdx, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Provisioni"...
0x18012f6e2  test    al, al
0x18012f6e4  cmovz   rdx, rcx
0x18012f6e8  lea     rcx, [rsp+618h+var_578]
0x18012f6f0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012f6f5  nop
0x18012f6f6  lea     r8, psz; "\\"
0x18012f6fd  mov     rdx, rax
0x18012f700  lea     rcx, [rsp+618h+var_4A8]
0x18012f708  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18012f70d  nop
0x18012f70e  lea     r8, [rsp+618h+var_518]
0x18012f716  mov     rdx, rax
0x18012f719  lea     rcx, [rsp+618h+var_538]
0x18012f721  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18012f726  nop
0x18012f727  lea     rcx, [rsp+618h+var_4A8]
0x18012f72f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012f734  nop
0x18012f735  lea     rcx, [rsp+618h+var_578]
0x18012f73d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012f742  mov     rdi, [rsp+618h+hKey]
0x18012f747  test    rdi, rdi
0x18012f74a  jz      short loc_18012F76F
0x18012f74c  lea     rcx, [rsp+618h+hkey]; this
0x18012f751  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18012f756  mov     rcx, rdi; hKey
0x18012f759  call    cs:__imp_RegCloseKey
0x18012f760  nop     dword ptr [rax+rax+00h]
0x18012f765  lea     rcx, [rsp+618h+hkey]; this
0x18012f76a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18012f76f  mov     [rsp+618h+hKey], r14
0x18012f774  lea     rcx, [rsp+618h+var_538]
0x18012f77c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18012f781  mov     rdx, rax; lpSubKey
0x18012f784  lea     rax, [rsp+618h+hKey]
0x18012f789  mov     [rsp+618h+phkResult], rax; int
0x18012f78e  mov     r9d, 20019h; samDesired
0x18012f794  xor     r8d, r8d; ulOptions
0x18012f797  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18012f79e  call    cs:__imp_RegOpenKeyExW
0x18012f7a5  nop     dword ptr [rax+rax+00h]
0x18012f7aa  cmp     eax, 2
0x18012f7ad  jnz     short loc_18012F7F5
0x18012f7af  lea     rcx, [rsp+618h+var_538]
0x18012f7b7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012f7bc  nop
0x18012f7bd  lea     rcx, [rsp+618h+var_518]
0x18012f7c5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012f7ca  nop
0x18012f7cb  lea     rcx, [rsp+618h+hKey]
0x18012f7d0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012f7d5  nop
0x18012f7d6  lea     rcx, [rsp+618h+var_590]
0x18012f7de  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x18012f7e3  nop
0x18012f7e4  lea     rcx, [rsp+618h+var_5D8]
0x18012f7e9  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012f7ee  xor     eax, eax
0x18012f7f0  jmp     loc_180130594
0x18012f7f5  mov     esi, 80070000h
0x18012f7fa  test    ebx, ebx
0x18012f7fc  jg      short loc_18012F802
0x18012f7fe  mov     edi, ebx
0x18012f800  jmp     short loc_18012F807
0x18012f802  movzx   edi, bx
0x18012f805  or      edi, esi
0x18012f807  test    edi, edi
0x18012f809  jns     short loc_18012F86E
0x18012f80b  mov     rcx, [rsp+618h]; this
0x18012f813  mov     r9d, edi; char *
0x18012f816  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012f81d  mov     edx, 5A9h; void *
0x18012f822  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f827  nop
0x18012f828  lea     rcx, [rsp+618h+var_538]
0x18012f830  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012f835  nop
0x18012f836  lea     rcx, [rsp+618h+var_518]
0x18012f83e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012f843  nop
0x18012f844  lea     rcx, [rsp+618h+hKey]
0x18012f849  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012f84e  nop
0x18012f84f  lea     rcx, [rsp+618h+var_590]
0x18012f857  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x18012f85c  nop
0x18012f85d  lea     rcx, [rsp+618h+var_5D8]
0x18012f862  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012f867  mov     eax, edi
0x18012f869  jmp     loc_180130594
0x18012f86e  mov     [rsp+618h+var_5B0], r14
0x18012f873  call    cs:__imp_RtlIsStateSeparationEnabled
0x18012f87a  nop     dword ptr [rax+rax+00h]
0x18012f87f  lea     rcx, aSoftwareMicros_2; "Software\\Microsoft\\Enrollments"
0x18012f886  lea     rdx, aOsdataSoftware_7; "OSData\\Software\\Microsoft\\Enrollment"...
0x18012f88d  test    al, al
0x18012f88f  cmovz   rdx, rcx
0x18012f893  lea     rcx, [rsp+618h+var_488]
0x18012f89b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012f8a0  nop
0x18012f8a1  lea     r8, psz; "\\"
0x18012f8a8  mov     rdx, rax
0x18012f8ab  lea     rcx, [rsp+618h+var_578]
0x18012f8b3  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18012f8b8  nop
0x18012f8b9  lea     r8, [rsp+618h+var_518]
0x18012f8c1  mov     rdx, rax
0x18012f8c4  lea     rcx, [rsp+618h+var_4A8]
0x18012f8cc  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18012f8d1  nop
0x18012f8d2  lea     r8, aDmclient; "\\DMClient"
0x18012f8d9  mov     rdx, rax
0x18012f8dc  lea     rcx, [rsp+618h+var_558]
0x18012f8e4  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18012f8e9  nop
0x18012f8ea  lea     rcx, [rsp+618h+var_4A8]
0x18012f8f2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012f8f7  nop
0x18012f8f8  lea     rcx, [rsp+618h+var_578]
0x18012f900  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012f905  nop
0x18012f906  lea     rcx, [rsp+618h+var_488]
0x18012f90e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012f913  mov     rdi, [rsp+618h+var_5B0]
0x18012f918  test    rdi, rdi
  ... truncated ...
```

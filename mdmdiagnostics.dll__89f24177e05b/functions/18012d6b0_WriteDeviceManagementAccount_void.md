# WriteDeviceManagementAccount(void)

- ea: `0x18012d6b0`
- end: `0x18012e866`
- name: `?WriteDeviceManagementAccount@@YAJXZ`
- size: `4534`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801266fc`

## callees

- `0x180019000`
- `0x180019fc4`
- `0x1800e66dc`
- `0x1800e7124`
- `0x1800e7c08`
- `0x1800e82e4`
- `0x1800ece5c`
- `0x1800ee878`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800f89d8`
- `0x1800f9a0c`
- `0x180104270`
- `0x180104bdc`
- `0x180104c80`
- `0x1801058cc`
- `0x180105c40`
- `0x180106ef0`
- `0x180107878`
- `0x180108060`
- `0x180127960`
- `0x180127fa8`
- `0x1801283b0`
- `0x180128e28`
- `0x18012913c`
- `0x1801297e8`
- `0x1801298b8`
- `0x18012cad4`
- `0x18012d6b0`
- `0x180131140`
- `0x180132eb0`
- `0x180132f88`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18012d9c4`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18012db5d`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18012d9c4`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18012db5d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18012e368`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18012e368`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012da8e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012dc4d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012e430`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012da8e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012dc4d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012e430`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012da4f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012dc0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012da4f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012dc0e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012de53`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012dfda`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012e1b6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012e511`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012de53`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012dfda`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012e1b6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012e511`

## string_xrefs

- `0x18012d743`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012d944`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012db00`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012dccf`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012dd7e`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012df21`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012e0fa`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012e28e`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012e38c`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012e454`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012e5f6`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012e748`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012e1c6`: `OMADM protocol version`
- `0x18012e6d1`: `Unconfigured`
- `0x18012d89d`: `LinkedEnrollmentAccountTable`
- `0x18012d888`: `Linked Enrollment Account`

## pseudocode

```c
// Hidden C++ exception states: #wind=15 #try_helpers=1
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
          WriteDeviceManagementAccount(i, (__int64)v70, (__int64)v66);
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
        WriteDeviceManagementAccount((__int64)&v67, (__int64)v70, (__int64)v66);
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
0x18012d6b0  push    rbx
0x18012d6b2  push    rsi
0x18012d6b3  push    rdi
0x18012d6b4  push    r14
0x18012d6b6  sub     rsp, 5F8h
0x18012d6bd  mov     rax, cs:__security_cookie
0x18012d6c4  xor     rax, rsp
0x18012d6c7  mov     [rsp+618h+var_38], rax
0x18012d6cf  xor     r14d, r14d
0x18012d6d2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_DMDiagLinkedEnrollment@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_DMDiagLinkedEnrollment@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_DMDiagLinkedEnrollment> `wil::Feature<__WilFeatureTraits_Feature_Servicing_DMDiagLinkedEnrollment>::GetImpl(void)'::`2'::impl
0x18012d6d9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_DMDiagLinkedEnrollment@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_DMDiagLinkedEnrollment>::__private_IsEnabled(void)
0x18012d6de  xorps   xmm0, xmm0
0x18012d6e1  mov     [rsp+618h+var_5C8], r14
0x18012d6e6  movdqu  [rsp+618h+var_5D8], xmm0
0x18012d6ec  test    al, al
0x18012d6ee  jz      loc_18012D90B
0x18012d6f4  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18012d6f9  lea     rdx, [rsp+618h+var_5D8]
0x18012d6fe  call    ?ListEnrollmentId@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::ListEnrollmentId(std::vector<std::wstring> &)
0x18012d703  mov     ebx, eax
0x18012d705  xorps   xmm0, xmm0
0x18012d708  movups  [rsp+618h+var_558], xmm0
0x18012d710  mov     [rsp+618h+var_548], r14
0x18012d718  mov     [rsp+618h+var_540], 7
0x18012d724  mov     word ptr [rsp+618h+var_558], r14w
0x18012d72d  test    eax, eax
0x18012d72f  jns     short loc_18012D774
0x18012d731  cmp     eax, 80070490h
0x18012d736  jz      short loc_18012D77C
0x18012d738  mov     rcx, [rsp+618h]; this
0x18012d740  mov     r9d, eax; char *
0x18012d743  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012d74a  mov     edx, 57Bh; void *
0x18012d74f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012d754  nop
0x18012d755  lea     rcx, [rsp+618h+var_558]
0x18012d75d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d762  nop
0x18012d763  lea     rcx, [rsp+618h+var_5D8]
0x18012d768  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012d76d  mov     eax, ebx
0x18012d76f  jmp     loc_18012E848
0x18012d774  cmp     ebx, 80070490h
0x18012d77a  jnz     short loc_18012D79B
0x18012d77c  lea     rcx, [rsp+618h+var_558]
0x18012d784  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d789  nop
0x18012d78a  lea     rcx, [rsp+618h+var_5D8]
0x18012d78f  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012d794  xor     eax, eax
0x18012d796  jmp     loc_18012E848
0x18012d79b  lea     rdx, [rsp+618h+var_5D8]
0x18012d7a0  lea     rcx, [rsp+618h+var_590]
0x18012d7a8  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x18012d7ad  mov     rcx, rax
0x18012d7b0  call    ?IsDeviceMMPCDualEnrolled@@YA_NV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; IsDeviceMMPCDualEnrolled(std::vector<std::wstring>)
0x18012d7b5  mov     dil, al
0x18012d7b8  mov     rbx, qword ptr [rsp+618h+var_5D8]
0x18012d7bd  mov     rsi, qword ptr [rsp+618h+var_5D8+8]
0x18012d7c2  cmp     rbx, rsi
0x18012d7c5  jz      loc_18012D879
0x18012d7cb  mov     [rsp+618h+var_5C0], 3Fh ; '?'
0x18012d7d3  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18012d7d8  mov     rcx, rbx
0x18012d7db  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18012d7e0  lea     r8, [rsp+618h+var_5C0]; unsigned int *
0x18012d7e5  mov     rdx, rax; unsigned __int16 *
0x18012d7e8  call    ?GetEnrollmentType@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJPEBGPEAK@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentType(ushort const *,ulong *)
0x18012d7ed  test    dil, dil
0x18012d7f0  jz      short loc_18012D812
0x18012d7f2  mov     eax, [rsp+618h+var_5C0]
0x18012d7f6  add     eax, 0FFFFFFE8h
0x18012d7f9  test    eax, 0FFFFFFFDh
0x18012d7fe  jnz     short loc_18012D812
0x18012d800  mov     rdx, rbx
0x18012d803  lea     rcx, [rsp+618h+var_558]
0x18012d80b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18012d810  jmp     short loc_18012D870
0x18012d812  lea     rdx, aDeviceManageme_2; "Device Management Account"
0x18012d819  lea     rcx, [rsp+618h+var_538]
0x18012d821  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012d826  nop
0x18012d827  lea     rdx, aDevicemanageme; "DeviceManagementAccountTable"
0x18012d82e  lea     rcx, [rsp+618h+var_578]
0x18012d836  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012d83b  nop
0x18012d83c  lea     r8, [rsp+618h+var_578]
0x18012d844  lea     rdx, [rsp+618h+var_538]
0x18012d84c  mov     rcx, rbx
0x18012d84f  call    ?WriteDeviceManagementAccount@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z; WriteDeviceManagementAccount(std::wstring &,std::wstring &,std::wstring &)
0x18012d854  nop
0x18012d855  lea     rcx, [rsp+618h+var_578]
0x18012d85d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d862  nop
0x18012d863  lea     rcx, [rsp+618h+var_538]
0x18012d86b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d870  add     rbx, 20h ; ' '
0x18012d874  jmp     loc_18012D7C2
0x18012d879  test    dil, dil
0x18012d87c  jz      short loc_18012D8EC
0x18012d87e  cmp     [rsp+618h+var_548], r14
0x18012d886  jz      short loc_18012D8EC
0x18012d888  lea     rdx, aLinkedEnrollme; "Linked Enrollment Account"
0x18012d88f  lea     rcx, [rsp+618h+var_538]
0x18012d897  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012d89c  nop
0x18012d89d  lea     rdx, aLinkedenrollme_0; "LinkedEnrollmentAccountTable"
0x18012d8a4  lea     rcx, [rsp+618h+var_578]
0x18012d8ac  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012d8b1  nop
0x18012d8b2  lea     r8, [rsp+618h+var_578]
0x18012d8ba  lea     rdx, [rsp+618h+var_538]
0x18012d8c2  lea     rcx, [rsp+618h+var_558]
0x18012d8ca  call    ?WriteDeviceManagementAccount@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z; WriteDeviceManagementAccount(std::wstring &,std::wstring &,std::wstring &)
0x18012d8cf  nop
0x18012d8d0  lea     rcx, [rsp+618h+var_578]
0x18012d8d8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d8dd  nop
0x18012d8de  lea     rcx, [rsp+618h+var_538]
0x18012d8e6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d8eb  nop
0x18012d8ec  lea     rcx, [rsp+618h+var_558]
0x18012d8f4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d8f9  nop
0x18012d8fa  lea     rcx, [rsp+618h+var_5D8]
0x18012d8ff  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012d904  xor     eax, eax
0x18012d906  jmp     loc_18012E848
0x18012d90b  xorps   xmm1, xmm1
0x18012d90e  movdqu  [rsp+618h+var_590], xmm1
0x18012d917  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18012d91c  lea     rdx, [rsp+618h+var_590]
0x18012d924  mov     rcx, rax
0x18012d927  call    ?GetEnrollmentId@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentId(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>> &)
0x18012d92c  mov     ebx, eax
0x18012d92e  test    eax, eax
0x18012d930  jns     short loc_18012D975
0x18012d932  cmp     eax, 80070490h
0x18012d937  jz      short loc_18012D97D
0x18012d939  mov     rcx, [rsp+618h]; this
0x18012d941  mov     r9d, eax; char *
0x18012d944  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012d94b  mov     edx, 5A0h; void *
0x18012d950  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012d955  nop
0x18012d956  lea     rcx, [rsp+618h+var_590]
0x18012d95e  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x18012d963  nop
0x18012d964  lea     rcx, [rsp+618h+var_5D8]
0x18012d969  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012d96e  mov     eax, ebx
0x18012d970  jmp     loc_18012E848
0x18012d975  cmp     ebx, 80070490h
0x18012d97b  jnz     short loc_18012D99C
0x18012d97d  lea     rcx, [rsp+618h+var_590]
0x18012d985  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x18012d98a  nop
0x18012d98b  lea     rcx, [rsp+618h+var_5D8]
0x18012d990  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012d995  xor     eax, eax
0x18012d997  jmp     loc_18012E848
0x18012d99c  mov     [rsp+618h+hKey], r14
0x18012d9a1  mov     rax, qword ptr [rsp+618h+var_590]
0x18012d9a9  test    rax, rax
0x18012d9ac  jz      short loc_18012D9B3
0x18012d9ae  mov     rdx, [rax]
0x18012d9b1  jmp     short loc_18012D9B6
0x18012d9b3  mov     rdx, r14
0x18012d9b6  lea     rcx, [rsp+618h+var_518]
0x18012d9be  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012d9c3  nop
0x18012d9c4  call    cs:__imp_RtlIsStateSeparationEnabled
0x18012d9ca  lea     rcx, aSoftwareMicros_1; "Software\\Microsoft\\Provisioning\\OMAD"...
0x18012d9d1  lea     rdx, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Provisioni"...
0x18012d9d8  test    al, al
0x18012d9da  cmovz   rdx, rcx
0x18012d9de  lea     rcx, [rsp+618h+var_578]
0x18012d9e6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012d9eb  nop
0x18012d9ec  lea     r8, psz; "\\"
0x18012d9f3  mov     rdx, rax
0x18012d9f6  lea     rcx, [rsp+618h+var_4A8]
0x18012d9fe  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18012da03  nop
0x18012da04  lea     r8, [rsp+618h+var_518]
0x18012da0c  mov     rdx, rax
0x18012da0f  lea     rcx, [rsp+618h+var_538]
0x18012da17  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18012da1c  nop
0x18012da1d  lea     rcx, [rsp+618h+var_4A8]
0x18012da25  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012da2a  nop
0x18012da2b  lea     rcx, [rsp+618h+var_578]
0x18012da33  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012da38  mov     rdi, [rsp+618h+hKey]
0x18012da3d  test    rdi, rdi
0x18012da40  jz      short loc_18012DA5F
0x18012da42  lea     rcx, [rsp+618h+hkey]; this
0x18012da47  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18012da4c  mov     rcx, rdi; hKey
0x18012da4f  call    cs:__imp_RegCloseKey
0x18012da55  lea     rcx, [rsp+618h+hkey]; this
0x18012da5a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18012da5f  mov     [rsp+618h+hKey], r14
0x18012da64  lea     rcx, [rsp+618h+var_538]
0x18012da6c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18012da71  mov     rdx, rax; lpSubKey
0x18012da74  lea     rax, [rsp+618h+hKey]
0x18012da79  mov     [rsp+618h+phkResult], rax; int
0x18012da7e  mov     r9d, 20019h; samDesired
0x18012da84  xor     r8d, r8d; ulOptions
0x18012da87  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18012da8e  call    cs:__imp_RegOpenKeyExW
0x18012da94  cmp     eax, 2
0x18012da97  jnz     short loc_18012DADF
0x18012da99  lea     rcx, [rsp+618h+var_538]
0x18012daa1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012daa6  nop
0x18012daa7  lea     rcx, [rsp+618h+var_518]
0x18012daaf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012dab4  nop
0x18012dab5  lea     rcx, [rsp+618h+hKey]
0x18012daba  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012dabf  nop
0x18012dac0  lea     rcx, [rsp+618h+var_590]
0x18012dac8  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x18012dacd  nop
0x18012dace  lea     rcx, [rsp+618h+var_5D8]
0x18012dad3  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012dad8  xor     eax, eax
0x18012dada  jmp     loc_18012E848
0x18012dadf  mov     esi, 80070000h
0x18012dae4  test    ebx, ebx
0x18012dae6  jg      short loc_18012DAEC
0x18012dae8  mov     edi, ebx
0x18012daea  jmp     short loc_18012DAF1
0x18012daec  movzx   edi, bx
0x18012daef  or      edi, esi
0x18012daf1  test    edi, edi
0x18012daf3  jns     short loc_18012DB58
0x18012daf5  mov     rcx, [rsp+618h]; this
0x18012dafd  mov     r9d, edi; char *
0x18012db00  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012db07  mov     edx, 5A9h; void *
0x18012db0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012db11  nop
0x18012db12  lea     rcx, [rsp+618h+var_538]
0x18012db1a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012db1f  nop
0x18012db20  lea     rcx, [rsp+618h+var_518]
0x18012db28  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012db2d  nop
0x18012db2e  lea     rcx, [rsp+618h+hKey]
0x18012db33  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012db38  nop
0x18012db39  lea     rcx, [rsp+618h+var_590]
0x18012db41  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x18012db46  nop
0x18012db47  lea     rcx, [rsp+618h+var_5D8]
0x18012db4c  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012db51  mov     eax, edi
0x18012db53  jmp     loc_18012E848
0x18012db58  mov     [rsp+618h+var_5B0], r14
0x18012db5d  call    cs:__imp_RtlIsStateSeparationEnabled
0x18012db63  lea     rcx, aSoftwareMicros_2; "Software\\Microsoft\\Enrollments"
0x18012db6a  lea     rdx, aOsdataSoftware_7; "OSData\\Software\\Microsoft\\Enrollment"...
0x18012db71  test    al, al
0x18012db73  cmovz   rdx, rcx
0x18012db77  lea     rcx, [rsp+618h+var_488]
0x18012db7f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012db84  nop
0x18012db85  lea     r8, psz; "\\"
0x18012db8c  mov     rdx, rax
0x18012db8f  lea     rcx, [rsp+618h+var_578]
0x18012db97  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18012db9c  nop
0x18012db9d  lea     r8, [rsp+618h+var_518]
0x18012dba5  mov     rdx, rax
0x18012dba8  lea     rcx, [rsp+618h+var_4A8]
0x18012dbb0  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18012dbb5  nop
0x18012dbb6  lea     r8, aDmclient; "\\DMClient"
0x18012dbbd  mov     rdx, rax
0x18012dbc0  lea     rcx, [rsp+618h+var_558]
0x18012dbc8  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18012dbcd  nop
0x18012dbce  lea     rcx, [rsp+618h+var_4A8]
0x18012dbd6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012dbdb  nop
0x18012dbdc  lea     rcx, [rsp+618h+var_578]
0x18012dbe4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012dbe9  nop
0x18012dbea  lea     rcx, [rsp+618h+var_488]
0x18012dbf2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012dbf7  mov     rdi, [rsp+618h+var_5B0]
0x18012dbfc  test    rdi, rdi
0x18012dbff  jz      short loc_18012DC1E
0x18012dc01  lea     rcx, [rsp+618h+hkey]; this
0x18012dc06  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18012dc0b  mov     rcx, rdi; hKey
  ... truncated ...
```

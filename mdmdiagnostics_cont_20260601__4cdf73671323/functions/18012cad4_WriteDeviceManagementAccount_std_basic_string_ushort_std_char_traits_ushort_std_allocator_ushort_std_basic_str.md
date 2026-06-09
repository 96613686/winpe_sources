# WriteDeviceManagementAccount(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18012cad4`
- end: `0x18012d6a8`
- name: `?WriteDeviceManagementAccount@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z`
- size: `3028`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18012d6b0`

## callees

- `0x180019000`
- `0x180019fc4`
- `0x1800e66dc`
- `0x1800e7124`
- `0x1800e7c08`
- `0x1800e82e4`
- `0x1800ece5c`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800ef8c8`
- `0x1800ef900`
- `0x1800f89d8`
- `0x1800f9a0c`
- `0x180104270`
- `0x180104bdc`
- `0x180104c80`
- `0x18010589c`
- `0x1801058cc`
- `0x180105b28`
- `0x180105c40`
- `0x180106ef0`
- `0x18011129c`
- `0x180127960`
- `0x180127fa8`
- `0x1801283b0`
- `0x18012913c`
- `0x180129214`
- `0x18012cad4`
- `0x180131140`
- `0x180132f88`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18012cb23`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18012cc1d`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18012cb23`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18012cc1d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18012d321`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18012d321`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012cbd3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012cce4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012d368`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012cbd3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012cce4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012d368`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012cb95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012ccad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012cb95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012ccad`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012d016`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012d0fc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012d21e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012d3d8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012d016`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012d0fc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012d21e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012d3d8`

## string_xrefs

- `0x18012cc02`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012cd13`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012cd9b`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012cfc1`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012d38d`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012d617`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012ceb2`: `Windows Declared Configuration(WinDC)`
- `0x18012d594`: `Linked Enrollment ID`
- `0x18012d22e`: `OMADM protocol version`
- `0x18012d4dc`: `Unconfigured`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
__int64 __fastcall WriteDeviceManagementAccount(__int64 a1, __int64 a2, __int64 a3)
{
  char IsStateSeparationEnabled; // al
  const wchar_t *v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rax
  const WCHAR *v10; // rax
  LSTATUS v11; // eax
  signed int v12; // ebx
  char v13; // al
  const wchar_t *v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  const WCHAR *v18; // rax
  LSTATUS v19; // eax
  const unsigned __int16 *v20; // rbx
  const unsigned __int16 *v21; // rax
  int v22; // eax
  __int64 v23; // rdx
  unsigned __int64 v24; // r9
  const unsigned __int16 *v25; // rax
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v26; // rcx
  const wchar_t *v27; // rdx
  __int64 v28; // rax
  int v29; // eax
  __int128 *v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rax
  LSTATUS v33; // eax
  LSTATUS v34; // eax
  unsigned __int64 v35; // r9
  __int64 v36; // rdx
  LSTATUS ValueW; // eax
  bool v38; // sf
  int v39; // eax
  int v40; // eax
  __int64 v41; // rax
  __int64 v42; // rcx
  int v43; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  __int128 v48; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v49; // [rsp+50h] [rbp-B0h]
  HKEY v50; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v51[4]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD pcbData; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hkey; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v54; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v56; // [rsp+80h] [rbp-80h] BYREF
  DWORD cchName; // [rsp+84h] [rbp-7Ch] BYREF
  _BYTE v58[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v59[32]; // [rsp+A8h] [rbp-58h] BYREF
  _OWORD v60[2]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v61[80]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v62[32]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v63; // [rsp+160h] [rbp+60h] BYREF
  __int64 v64; // [rsp+170h] [rbp+70h]
  __int64 v65; // [rsp+178h] [rbp+78h]
  _BYTE v66[48]; // [rsp+18Ah] [rbp+8Ah] BYREF
  _BYTE v67[6]; // [rsp+1BAh] [rbp+BAh] BYREF
  int pvData; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v69[524]; // [rsp+1C4h] [rbp+C4h] BYREF
  WCHAR Name; // [rsp+3D0h] [rbp+2D0h] BYREF
  _BYTE v71[526]; // [rsp+3D2h] [rbp+2D2h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+628h] [rbp+528h]

  v48 = 0;
  v49 = 0;
  hKey = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v7 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM\\Accounts";
  if ( !IsStateSeparationEnabled )
    v7 = L"Software\\Microsoft\\Provisioning\\OMADM\\Accounts";
  v8 = std::wstring::wstring(&v63, v7);
  v9 = std::operator+<unsigned short>(v59, v8, L"\\");
  std::operator+<unsigned short>(v62, v9, a1);
  std::wstring::_Tidy_deallocate(v59);
  std::wstring::_Tidy_deallocate(&v63);
  hKey = 0;
  v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v62);
  v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v10, 0, 0x20019u, &hKey);
  v12 = v11;
  if ( v11 == 2 )
    goto LABEL_111;
  if ( v11 > 0 )
    v12 = (unsigned __int16)v11 | 0x80070000;
  if ( v12 >= 0 )
  {
    v50 = 0;
    v13 = RtlIsStateSeparationEnabled();
    v14 = L"OSData\\Software\\Microsoft\\Enrollments";
    if ( !v13 )
      v14 = L"Software\\Microsoft\\Enrollments";
    v15 = std::wstring::wstring(v60, v14);
    v16 = std::operator+<unsigned short>(&v63, v15, L"\\");
    v17 = std::operator+<unsigned short>(v59, v16, a1);
    std::operator+<unsigned short>(v58, v17, L"\\DMClient");
    std::wstring::_Tidy_deallocate(v59);
    std::wstring::_Tidy_deallocate(&v63);
    std::wstring::_Tidy_deallocate(v60);
    v50 = 0;
    v18 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v58);
    v19 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v18, 0, 0x20019u, &v50);
    v12 = v19;
    if ( v19 != 2 )
    {
      if ( v19 > 0 )
        v12 = (unsigned __int16)v19 | 0x80070000;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4F4,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
          (const char *)(unsigned int)v12,
          phkResulta);
LABEL_15:
        std::wstring::_Tidy_deallocate(v58);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v50);
        goto LABEL_112;
      }
      pvData = 0;
      memset_0(v69, 0, 0x204u);
      pcbData = 260;
      v20 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
      v21 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
      Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::SimpleTable(
        (Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v61,
        v21,
        v20);
      v22 = Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::WriteSectionHeaderForTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v61);
      v12 = v22;
      if ( v22 < 0 )
      {
        v23 = 1273;
LABEL_18:
        v24 = (unsigned int)v22;
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v23,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
          (const char *)v24,
          phkResulta);
LABEL_20:
        Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v61);
        goto LABEL_15;
      }
      std::vector<std::wstring>::clear(&v48);
      std::wstring::wstring(&v63, L"Enrollment ID");
      if ( *((_QWORD *)&v48 + 1) == v49 )
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v48, *((_QWORD *)&v48 + 1), &v63);
      else
        std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(&v48, &v63);
      std::wstring::_Tidy_deallocate(&v63);
      if ( *((_QWORD *)&v48 + 1) == v49 )
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v48, *((_QWORD *)&v48 + 1), a1);
      else
        std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(&v48, a1);
      v22 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v61, &v48);
      v12 = v22;
      if ( v22 < 0 )
      {
        v23 = 1280;
        goto LABEL_18;
      }
      v54 = 63;
      v60[0] = 0;
      v60[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v60[0]) = 0;
      Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
      v25 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
      Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentType(v26, v25, &v54);
      if ( v54 == 6 )
      {
        v27 = L"MDM Device with Entra ID";
      }
      else if ( v54 == 13 )
      {
        v27 = L"MDM Enrollment with Entra ID";
      }
      else if ( ((v54 - 24) & 0xFFFFFFFD) != 0 )
      {
        v27 = L"Other";
        if ( v54 == 63 )
          v27 = L"Invalid";
      }
      else
      {
        v27 = L"Windows Declared Configuration(WinDC)";
      }
      std::wstring::assign(v60, v27);
      std::wstring::append(v60, L"(");
      v28 = std::_UIntegral_to_buff<unsigned short,unsigned int>(v66, v54);
      std::wstring::wstring(v59, v28, v66, v51);
      std::wstring::append(v60, v59);
      std::wstring::_Tidy_deallocate(v59);
      std::wstring::append(v60, L")");
      std::vector<std::wstring>::clear(&v48);
      std::wstring::wstring(&v63, L"Enrollment Type");
      if ( *((_QWORD *)&v48 + 1) == v49 )
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v48, *((_QWORD *)&v48 + 1), &v63);
      else
        std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(&v48, &v63);
      std::wstring::_Tidy_deallocate(&v63);
      if ( *((_QWORD *)&v48 + 1) == v49 )
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v48, *((_QWORD *)&v48 + 1), v60);
      else
        std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(&v48, v60);
      v29 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v61, &v48);
      v12 = v29;
      if ( v29 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x521,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
          (const char *)(unsigned int)v29,
          phkResulta);
        v30 = v60;
LABEL_46:
        std::wstring::_Tidy_deallocate(v30);
        goto LABEL_20;
      }
      std::wstring::_Tidy_deallocate(v60);
      RegGetValueW(hKey, 0, L"AcctUId", 2u, 0, &pvData, &pcbData);
      std::vector<std::wstring>::clear(&v48);
      std::wstring::wstring(&v63, L"Account UID");
      if ( *((_QWORD *)&v48 + 1) == v49 )
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v48, *((_QWORD *)&v48 + 1), &v63);
      else
        std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(&v48, &v63);
      std::wstring::_Tidy_deallocate(&v63);
      std::wstring::wstring(&v63, &pvData);
      if ( *((_QWORD *)&v48 + 1) == v49 )
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v48, *((_QWORD *)&v48 + 1), &v63);
      else
        std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(&v48, &v63);
      std::wstring::_Tidy_deallocate(&v63);
      v22 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v61, &v48);
      v12 = v22;
      if ( v22 < 0 )
      {
        v23 = 1323;
        goto LABEL_18;
      }
      v56 = 0;
      pcbData = 4;
      RegGetValueW(hKey, 0, L"Flags", 0x10u, 0, &v56, &pcbData);
      std::vector<std::wstring>::clear(&v48);
      std::wstring::wstring(&v63, L"Flags");
      if ( *((_QWORD *)&v48 + 1) == v49 )
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v48, *((_QWORD *)&v48 + 1), &v63);
      else
        std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(&v48, &v63);
      std::wstring::_Tidy_deallocate(&v63);
      v31 = std::_UIntegral_to_buff<unsigned short,unsigned int>(v67, v56);
      std::wstring::wstring(v59, v31, v67, v51);
      v32 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
      std::wstring::wstring(&v63, v32);
      if ( *((_QWORD *)&v48 + 1) == v49 )
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v48, *((_QWORD *)&v48 + 1), &v63);
      else
        std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(&v48, &v63);
      std::wstring::_Tidy_deallocate(&v63);
      std::wstring::_Tidy_deallocate(v59);
      v22 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v61, &v48);
      v12 = v22;
      if ( v22 < 0 )
      {
        v23 = 1335;
        goto LABEL_18;
      }
      LOWORD(pvData) = 0;
      pcbData = 260;
      RegGetValueW(hKey, 0, L"ProtoVer", 2u, 0, &pvData, &pcbData);
      std::vector<std::wstring>::clear(&v48);
      std::wstring::wstring(&v63, L"OMADM protocol version");
      if ( *((_QWORD *)&v48 + 1) == v49 )
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v48, *((_QWORD *)&v48 + 1), &v63);
      else
        std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(&v48, &v63);
      std::wstring::_Tidy_deallocate(&v63);
      std::wstring::wstring(&v63, &pvData);
      if ( *((_QWORD *)&v48 + 1) == v49 )
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v48, *((_QWORD *)&v48 + 1), &v63);
      else
        std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(&v48, &v63);
      std::wstring::_Tidy_deallocate(&v63);
      v22 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v61, &v48);
      v12 = v22;
      if ( v22 < 0 )
      {
        v23 = 1347;
        goto LABEL_18;
      }
      LOWORD(pvData) = 0;
      pcbData = 260;
      cchName = 261;
      Name = 0;
      memset_0(v71, 0, 0x208u);
      v33 = RegEnumKeyExW(v50, 0, &Name, &cchName, 0, 0, 0, 0);
      v12 = v33;
      if ( v33 > 0 )
        v12 = (unsigned __int16)v33 | 0x80070000;
      if ( v12 < 0 )
      {
        v24 = (unsigned int)v12;
        v23 = 1359;
        goto LABEL_19;
      }
      hkey = 0;
      v34 = RegOpenKeyExW(v50, &Name, 0, 0x20019u, &hkey);
      v12 = v34;
      if ( v34 > 0 )
        v12 = (unsigned __int16)v34 | 0x80070000;
      if ( v12 < 0 )
      {
        v35 = (unsigned int)v12;
        v36 = 1361;
LABEL_79:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v36,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
          (const char *)v35,
          phkResultb);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        goto LABEL_20;
      }
      ValueW = RegGetValueW(hkey, 0, L"EntDMID", 2u, 0, &pvData, &pcbData);
      v38 = ValueW < 0;
      if ( ValueW > 0 )
        v38 = 1;
      if ( v38 )
      {
        std::vector<std::wstring>::clear(&v48);
        std::wstring::wstring(&v63, L"EntDMID");
        if ( *((_QWORD *)&v48 + 1) == v49 )
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v48, *((_QWORD *)&v48 + 1), &v63);
        else
          std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(&v48, &v63);
        std::wstring::_Tidy_deallocate(&v63);
        std::wstring::wstring(&v63, L"Unconfigured");
        if ( *((_QWORD *)&v48 + 1) == v49 )
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v48, *((_QWORD *)&v48 + 1), &v63);
        else
          std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(&v48, &v63);
        std::wstring::_Tidy_deallocate(&v63);
        v40 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v61, &v48);
        v12 = v40;
        if ( v40 < 0 )
        {
          v35 = (unsigned int)v40;
          v36 = 1375;
          goto LABEL_79;
        }
      }
      else
      {
        std::vector<std::wstring>::clear(&v48);
        std::wstring::wstring(&v63, L"EntDMID");
        if ( *((_QWORD *)&v48 + 1) == v49 )
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v48, *((_QWORD *)&v48 + 1), &v63);
        else
          std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(&v48, &v63);
        std::wstring::_Tidy_deallocate(&v63);
        std::wstring::wstring(&v63, &pvData);
        if ( *((_QWORD *)&v48 + 1) == v49 )
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v48, *((_QWORD *)&v48 + 1), &v63);
        else
          std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(&v48, &v63);
        std::wstring::_Tidy_deallocate(&v63);
        v39 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v61, &v48);
        v12 = v39;
        if ( v39 < 0 )
        {
          v35 = (unsigned int)v39;
          v36 = 1368;
          goto LABEL_79;
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      v63 = 0;
      v64 = 0;
      v65 = 7;
      LOWORD(v63) = 0;
      Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
      v41 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
      if ( !(unsigned int)Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetLinkedEnrollmentId(v42, v41, &v63)
        && v64 )
      {
        std::vector<std::wstring>::clear(&v48);
        std::wstring::wstring(v59, L"Linked Enrollment ID");
        if ( *((_QWORD *)&v48 + 1) == v49 )
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v48, *((_QWORD *)&v48 + 1), v59);
        else
          std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(&v48, v59);
        std::wstring::_Tidy_deallocate(v59);
        if ( *((_QWORD *)&v48 + 1) == v49 )
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v48, *((_QWORD *)&v48 + 1), &v63);
        else
          std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(&v48, &v63);
        v43 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v61, &v48);
        v12 = v43;
        if ( v43 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x56A,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
            (const char *)(unsigned int)v43,
            phkResultb);
          v30 = &v63;
          goto LABEL_46;
        }
      }
      std::wstring::_Tidy_deallocate(&v63);
      Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v61);
    }
    std::wstring::_Tidy_deallocate(v58);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v50);
LABEL_111:
    v12 = 0;
    goto LABEL_112;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4EB,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
    (const char *)(unsigned int)v12,
    phkResult);
LABEL_112:
  std::wstring::_Tidy_deallocate(v62);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  std::vector<std::wstring>::_Tidy(&v48);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18012cad4  mov     [rsp-8+arg_18], rbx
0x18012cad9  push    rbp
0x18012cada  push    rsi
0x18012cadb  push    rdi
0x18012cadc  push    r12
0x18012cade  push    r13
0x18012cae0  push    r14
0x18012cae2  push    r15
0x18012cae4  lea     rbp, [rsp-4F0h]
0x18012caec  sub     rsp, 5F0h
0x18012caf3  mov     rax, cs:__security_cookie
0x18012cafa  xor     rax, rsp
0x18012cafd  mov     [rbp+520h+var_40], rax
0x18012cb04  mov     r14, r8
0x18012cb07  mov     rsi, rdx
0x18012cb0a  mov     rdi, rcx
0x18012cb0d  xor     r15d, r15d
0x18012cb10  xorps   xmm0, xmm0
0x18012cb13  movdqu  [rsp+620h+var_5E0], xmm0
0x18012cb19  mov     [rsp+620h+var_5D0], r15
0x18012cb1e  mov     [rsp+620h+hKey], r15
0x18012cb23  call    cs:__imp_RtlIsStateSeparationEnabled
0x18012cb29  lea     rcx, aSoftwareMicros_1; "Software\\Microsoft\\Provisioning\\OMAD"...
0x18012cb30  lea     rdx, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Provisioni"...
0x18012cb37  test    al, al
0x18012cb39  cmovz   rdx, rcx
0x18012cb3d  lea     rcx, [rbp+520h+var_4C0]
0x18012cb41  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012cb46  nop
0x18012cb47  lea     r8, psz; "\\"
0x18012cb4e  mov     rdx, rax
0x18012cb51  lea     rcx, [rbp+520h+var_578]
0x18012cb55  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18012cb5a  nop
0x18012cb5b  mov     r8, rdi
0x18012cb5e  mov     rdx, rax
0x18012cb61  lea     rcx, [rbp+520h+var_4E0]
0x18012cb65  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18012cb6a  nop
0x18012cb6b  lea     rcx, [rbp+520h+var_578]
0x18012cb6f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012cb74  nop
0x18012cb75  lea     rcx, [rbp+520h+var_4C0]
0x18012cb79  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012cb7e  mov     rbx, [rsp+620h+hKey]
0x18012cb83  test    rbx, rbx
0x18012cb86  jz      short loc_18012CBA5
0x18012cb88  lea     rcx, [rsp+620h+hkey]; this
0x18012cb8d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18012cb92  mov     rcx, rbx; hKey
0x18012cb95  call    cs:__imp_RegCloseKey
0x18012cb9b  lea     rcx, [rsp+620h+hkey]; this
0x18012cba0  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18012cba5  mov     [rsp+620h+hKey], r15
0x18012cbaa  lea     rcx, [rbp+520h+var_4E0]
0x18012cbae  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18012cbb3  mov     rdx, rax; lpSubKey
0x18012cbb6  lea     rax, [rsp+620h+hKey]
0x18012cbbb  mov     [rsp+620h+phkResult], rax; int
0x18012cbc0  mov     r9d, 20019h; samDesired
0x18012cbc6  xor     r8d, r8d; ulOptions
0x18012cbc9  mov     r13, 0FFFFFFFF80000002h
0x18012cbd0  mov     rcx, r13; hKey
0x18012cbd3  call    cs:__imp_RegOpenKeyExW
0x18012cbd9  mov     ebx, eax
0x18012cbdb  cmp     eax, 2
0x18012cbde  jz      loc_18012D65A
0x18012cbe4  mov     r12d, 80070000h
0x18012cbea  test    eax, eax
0x18012cbec  jle     short loc_18012CBF4
0x18012cbee  movzx   ebx, ax
0x18012cbf1  or      ebx, r12d
0x18012cbf4  test    ebx, ebx
0x18012cbf6  jns     short loc_18012CC18
0x18012cbf8  mov     rcx, [rbp+528h]; this
0x18012cbff  mov     r9d, ebx; char *
0x18012cc02  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012cc09  mov     edx, 4EBh; void *
0x18012cc0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012cc13  jmp     loc_18012D65D
0x18012cc18  mov     [rsp+620h+var_5C8], r15
0x18012cc1d  call    cs:__imp_RtlIsStateSeparationEnabled
0x18012cc23  lea     rcx, aSoftwareMicros_2; "Software\\Microsoft\\Enrollments"
0x18012cc2a  lea     rdx, aOsdataSoftware_7; "OSData\\Software\\Microsoft\\Enrollment"...
0x18012cc31  test    al, al
0x18012cc33  cmovz   rdx, rcx
0x18012cc37  lea     rcx, [rbp+520h+var_558]
0x18012cc3b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012cc40  nop
0x18012cc41  lea     r8, psz; "\\"
0x18012cc48  mov     rdx, rax
0x18012cc4b  lea     rcx, [rbp+520h+var_4C0]
0x18012cc4f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18012cc54  nop
0x18012cc55  mov     r8, rdi
0x18012cc58  mov     rdx, rax
0x18012cc5b  lea     rcx, [rbp+520h+var_578]
0x18012cc5f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18012cc64  nop
0x18012cc65  lea     r8, aDmclient; "\\DMClient"
0x18012cc6c  mov     rdx, rax
0x18012cc6f  lea     rcx, [rbp+520h+var_598]
0x18012cc73  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18012cc78  nop
0x18012cc79  lea     rcx, [rbp+520h+var_578]
0x18012cc7d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012cc82  nop
0x18012cc83  lea     rcx, [rbp+520h+var_4C0]
0x18012cc87  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012cc8c  nop
0x18012cc8d  lea     rcx, [rbp+520h+var_558]
0x18012cc91  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012cc96  mov     rbx, [rsp+620h+var_5C8]
0x18012cc9b  test    rbx, rbx
0x18012cc9e  jz      short loc_18012CCBD
0x18012cca0  lea     rcx, [rsp+620h+hkey]; this
0x18012cca5  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18012ccaa  mov     rcx, rbx; hKey
0x18012ccad  call    cs:__imp_RegCloseKey
0x18012ccb3  lea     rcx, [rsp+620h+hkey]; this
0x18012ccb8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18012ccbd  mov     [rsp+620h+var_5C8], r15
0x18012ccc2  lea     rcx, [rbp+520h+var_598]
0x18012ccc6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18012cccb  mov     rdx, rax; lpSubKey
0x18012ccce  lea     rax, [rsp+620h+var_5C8]
0x18012ccd3  mov     [rsp+620h+phkResult], rax; int
0x18012ccd8  mov     r9d, 20019h; samDesired
0x18012ccde  xor     r8d, r8d; ulOptions
0x18012cce1  mov     rcx, r13; hKey
0x18012cce4  call    cs:__imp_RegOpenKeyExW
0x18012ccea  mov     ebx, eax
0x18012ccec  mov     r13d, 2
0x18012ccf2  cmp     eax, r13d
0x18012ccf5  jz      loc_18012D646
0x18012ccfb  test    eax, eax
0x18012ccfd  jle     short loc_18012CD05
0x18012ccff  movzx   ebx, ax
0x18012cd02  or      ebx, r12d
0x18012cd05  test    ebx, ebx
0x18012cd07  jns     short loc_18012CD3E
0x18012cd09  mov     rcx, [rbp+528h]; this
0x18012cd10  mov     r9d, ebx; char *
0x18012cd13  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012cd1a  mov     edx, 4F4h; void *
0x18012cd1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012cd24  nop
0x18012cd25  lea     rcx, [rbp+520h+var_598]
0x18012cd29  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012cd2e  nop
0x18012cd2f  lea     rcx, [rsp+620h+var_5C8]
0x18012cd34  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012cd39  jmp     loc_18012D65D
0x18012cd3e  mov     [rbp+520h+var_460], r15d
0x18012cd45  xor     edx, edx; Val
0x18012cd47  mov     r8d, 204h; Size
0x18012cd4d  lea     rcx, [rbp+520h+var_45C]; void *
0x18012cd54  call    memset_0
0x18012cd59  mov     [rsp+620h+var_5BC], 104h
0x18012cd61  mov     rcx, r14
0x18012cd64  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18012cd69  mov     rbx, rax
0x18012cd6c  mov     rcx, rsi
0x18012cd6f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18012cd74  mov     r8, rbx; unsigned __int16 *
0x18012cd77  mov     rdx, rax; unsigned __int16 *
0x18012cd7a  lea     rcx, [rbp+520h+var_530]; this
0x18012cd7e  call    ??0SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@PEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::SimpleTable(ushort const *,ushort const *)
0x18012cd83  nop
0x18012cd84  lea     rcx, [rbp+520h+var_530]; this
0x18012cd88  call    ?WriteSectionHeaderForTable@SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJXZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::WriteSectionHeaderForTable(void)
0x18012cd8d  mov     ebx, eax
0x18012cd8f  test    eax, eax
0x18012cd91  jns     short loc_18012CDBD
0x18012cd93  mov     edx, 4F9h; void *
0x18012cd98  mov     r9d, eax; char *
0x18012cd9b  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012cda2  mov     rcx, [rbp+528h]; this
0x18012cda9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012cdae  nop
0x18012cdaf  lea     rcx, [rbp+520h+var_530]; this
0x18012cdb3  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012cdb8  jmp     loc_18012CD25
0x18012cdbd  lea     rcx, [rsp+620h+var_5E0]
0x18012cdc2  call    ?clear@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x18012cdc7  lea     rdx, aEnrollmentId; "Enrollment ID"
0x18012cdce  lea     rcx, [rbp+520h+var_4C0]
0x18012cdd2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012cdd7  nop
0x18012cdd8  mov     rdx, qword ptr [rsp+620h+var_5E0+8]
0x18012cddd  lea     rcx, [rsp+620h+var_5E0]
0x18012cde2  cmp     rdx, [rsp+620h+var_5D0]
0x18012cde7  jz      short loc_18012CDF4
0x18012cde9  lea     rdx, [rbp+520h+var_4C0]
0x18012cded  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012cdf2  jmp     short loc_18012CDFE
0x18012cdf4  lea     r8, [rbp+520h+var_4C0]
0x18012cdf8  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012cdfd  nop
0x18012cdfe  lea     rcx, [rbp+520h+var_4C0]
0x18012ce02  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012ce07  mov     rdx, qword ptr [rsp+620h+var_5E0+8]
0x18012ce0c  lea     rcx, [rsp+620h+var_5E0]
0x18012ce11  cmp     rdx, [rsp+620h+var_5D0]
0x18012ce16  jz      short loc_18012CE22
0x18012ce18  mov     rdx, rdi
0x18012ce1b  call    ??$_Emplace_back_with_unused_capacity@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(std::wstring const &)
0x18012ce20  jmp     short loc_18012CE2A
0x18012ce22  mov     r8, rdi
0x18012ce25  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18012ce2a  lea     rdx, [rsp+620h+var_5E0]
0x18012ce2f  lea     rcx, [rbp+520h+var_530]
0x18012ce33  call    ?AddTableRow@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(std::vector<std::wstring> &)
0x18012ce38  mov     ebx, eax
0x18012ce3a  test    eax, eax
0x18012ce3c  jns     short loc_18012CE48
0x18012ce3e  mov     edx, 500h
0x18012ce43  jmp     loc_18012CD98
0x18012ce48  mov     [rsp+620h+var_5B0], 3Fh ; '?'
0x18012ce50  xorps   xmm0, xmm0
0x18012ce53  movups  [rbp+520h+var_558], xmm0
0x18012ce57  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18012ce5f  movdqu  [rbp+520h+var_548], xmm1
0x18012ce64  mov     word ptr [rbp+520h+var_558], r15w
0x18012ce69  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18012ce6e  mov     rcx, rdi
0x18012ce71  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18012ce76  lea     r8, [rsp+620h+var_5B0]; unsigned int *
0x18012ce7b  mov     rdx, rax; unsigned __int16 *
0x18012ce7e  call    ?GetEnrollmentType@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJPEBGPEAK@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentType(ushort const *,ulong *)
0x18012ce83  mov     ecx, [rsp+620h+var_5B0]
0x18012ce87  cmp     ecx, 6
0x18012ce8a  jz      short loc_18012CEC4
0x18012ce8c  cmp     ecx, 0Dh
0x18012ce8f  jz      short loc_18012CEBB
0x18012ce91  lea     eax, [rcx-18h]
0x18012ce94  test    eax, 0FFFFFFFDh
0x18012ce99  jz      short loc_18012CEB2
0x18012ce9b  lea     rdx, aOther; "Other"
0x18012cea2  lea     rax, aInvalid; "Invalid"
0x18012cea9  cmp     ecx, 3Fh ; '?'
0x18012ceac  cmovz   rdx, rax
0x18012ceb0  jmp     short loc_18012CECB
0x18012ceb2  lea     rdx, aWindowsDeclare; "Windows Declared Configuration(WinDC)"
0x18012ceb9  jmp     short loc_18012CECB
0x18012cebb  lea     rdx, aMdmEnrollmentW; "MDM Enrollment with Entra ID"
0x18012cec2  jmp     short loc_18012CECB
0x18012cec4  lea     rdx, aMdmDeviceWithE; "MDM Device with Entra ID"
0x18012cecb  lea     rcx, [rbp+520h+var_558]
0x18012cecf  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18012ced4  lea     rdx, asc_1801ED2A4; "("
0x18012cedb  lea     rcx, [rbp+520h+var_558]
0x18012cedf  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18012cee4  mov     edx, [rsp+620h+var_5B0]
0x18012cee8  lea     rcx, [rbp+520h+var_496]
0x18012ceef  call    ??$_UIntegral_to_buff@GI@std@@YAPEAGPEAGI@Z; std::_UIntegral_to_buff<ushort,uint>(ushort *,uint)
0x18012cef4  lea     r9, [rsp+620h+var_5C0]
0x18012cef9  lea     r8, [rbp+520h+var_496]
0x18012cf00  mov     rdx, rax
0x18012cf03  lea     rcx, [rbp+520h+var_578]
0x18012cf07  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x18012cf0c  nop
0x18012cf0d  lea     rdx, [rbp+520h+var_578]
0x18012cf11  lea     rcx, [rbp+520h+var_558]
0x18012cf15  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18012cf1a  nop
0x18012cf1b  lea     rcx, [rbp+520h+var_578]
0x18012cf1f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012cf24  lea     rdx, asc_1801EC8F0; ")"
0x18012cf2b  lea     rcx, [rbp+520h+var_558]
0x18012cf2f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18012cf34  lea     rcx, [rsp+620h+var_5E0]
0x18012cf39  call    ?clear@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x18012cf3e  lea     rdx, aEnrollmentType; "Enrollment Type"
0x18012cf45  lea     rcx, [rbp+520h+var_4C0]
0x18012cf49  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012cf4e  nop
0x18012cf4f  mov     rdx, qword ptr [rsp+620h+var_5E0+8]
0x18012cf54  lea     rcx, [rsp+620h+var_5E0]
0x18012cf59  cmp     rdx, [rsp+620h+var_5D0]
0x18012cf5e  jz      short loc_18012CF6B
0x18012cf60  lea     rdx, [rbp+520h+var_4C0]
0x18012cf64  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012cf69  jmp     short loc_18012CF75
0x18012cf6b  lea     r8, [rbp+520h+var_4C0]
0x18012cf6f  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012cf74  nop
0x18012cf75  lea     rcx, [rbp+520h+var_4C0]
0x18012cf79  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012cf7e  mov     rdx, qword ptr [rsp+620h+var_5E0+8]
0x18012cf83  lea     rcx, [rsp+620h+var_5E0]
0x18012cf88  cmp     rdx, [rsp+620h+var_5D0]
0x18012cf8d  jz      short loc_18012CF9A
0x18012cf8f  lea     rdx, [rbp+520h+var_558]
0x18012cf93  call    ??$_Emplace_back_with_unused_capacity@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(std::wstring const &)
0x18012cf98  jmp     short loc_18012CFA3
0x18012cf9a  lea     r8, [rbp+520h+var_558]
0x18012cf9e  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18012cfa3  lea     rdx, [rsp+620h+var_5E0]
0x18012cfa8  lea     rcx, [rbp+520h+var_530]
  ... truncated ...
```

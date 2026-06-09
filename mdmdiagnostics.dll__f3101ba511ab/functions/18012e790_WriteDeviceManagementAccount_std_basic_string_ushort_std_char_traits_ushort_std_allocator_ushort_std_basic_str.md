# WriteDeviceManagementAccount(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18012e790`
- end: `0x18012f3ad`
- name: `?WriteDeviceManagementAccount@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z`
- size: `3101`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18012f3b4`

## callees

- `0x180019080`
- `0x18001a054`
- `0x1800e68b0`
- `0x1800e734c`
- `0x1800e7de8`
- `0x1800e8508`
- `0x1800ed46c`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f00ac`
- `0x1800f00e4`
- `0x1800f99d4`
- `0x1800faa0c`
- `0x180105480`
- `0x180105e98`
- `0x180105f3c`
- `0x180106b3c`
- `0x180106b6c`
- `0x180106dc8`
- `0x180106ee0`
- `0x1801081c4`
- `0x18011273c`
- `0x18012944c`
- `0x180129aac`
- `0x180129ee0`
- `0x18012ac74`
- `0x18012ad58`
- `0x18012e790`
- `0x180132f50`
- `0x180134e3c`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18012e7df`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18012e8eb`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18012e7df`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18012e8eb`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18012f013`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18012f013`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012e89b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012e9be`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012f060`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012e89b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012e9be`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012f060`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012e857`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012e981`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012e857`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012e981`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012ecf6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012ede2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012ef0a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012f0d6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012ecf6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012ede2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012ef0a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012f0d6`

## string_xrefs

- `0x18012e8d0`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012e9f3`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012ea7b`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012eca1`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012f08b`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012f31b`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012eb92`: `Windows Declared Configuration(WinDC)`
- `0x18012f298`: `Linked Enrollment ID`
- `0x18012ef20`: `OMADM protocol version`
- `0x18012f1e0`: `Unconfigured`

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
0x18012e790  mov     [rsp-8+arg_18], rbx
0x18012e795  push    rbp
0x18012e796  push    rsi
0x18012e797  push    rdi
0x18012e798  push    r12
0x18012e79a  push    r13
0x18012e79c  push    r14
0x18012e79e  push    r15
0x18012e7a0  lea     rbp, [rsp-4F0h]
0x18012e7a8  sub     rsp, 5F0h
0x18012e7af  mov     rax, cs:__security_cookie
0x18012e7b6  xor     rax, rsp
0x18012e7b9  mov     [rbp+520h+var_40], rax
0x18012e7c0  mov     r14, r8
0x18012e7c3  mov     rsi, rdx
0x18012e7c6  mov     rdi, rcx
0x18012e7c9  xor     r15d, r15d
0x18012e7cc  xorps   xmm0, xmm0
0x18012e7cf  movdqu  [rsp+620h+var_5E0], xmm0
0x18012e7d5  mov     [rsp+620h+var_5D0], r15
0x18012e7da  mov     [rsp+620h+hKey], r15
0x18012e7df  call    cs:__imp_RtlIsStateSeparationEnabled
0x18012e7e6  nop     dword ptr [rax+rax+00h]
0x18012e7eb  lea     rcx, aSoftwareMicros_1; "Software\\Microsoft\\Provisioning\\OMAD"...
0x18012e7f2  lea     rdx, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Provisioni"...
0x18012e7f9  test    al, al
0x18012e7fb  cmovz   rdx, rcx
0x18012e7ff  lea     rcx, [rbp+520h+var_4C0]
0x18012e803  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012e808  nop
0x18012e809  lea     r8, psz; "\\"
0x18012e810  mov     rdx, rax
0x18012e813  lea     rcx, [rbp+520h+var_578]
0x18012e817  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18012e81c  nop
0x18012e81d  mov     r8, rdi
0x18012e820  mov     rdx, rax
0x18012e823  lea     rcx, [rbp+520h+var_4E0]
0x18012e827  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18012e82c  nop
0x18012e82d  lea     rcx, [rbp+520h+var_578]
0x18012e831  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012e836  nop
0x18012e837  lea     rcx, [rbp+520h+var_4C0]
0x18012e83b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012e840  mov     rbx, [rsp+620h+hKey]
0x18012e845  test    rbx, rbx
0x18012e848  jz      short loc_18012E86D
0x18012e84a  lea     rcx, [rsp+620h+hkey]; this
0x18012e84f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18012e854  mov     rcx, rbx; hKey
0x18012e857  call    cs:__imp_RegCloseKey
0x18012e85e  nop     dword ptr [rax+rax+00h]
0x18012e863  lea     rcx, [rsp+620h+hkey]; this
0x18012e868  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18012e86d  mov     [rsp+620h+hKey], r15
0x18012e872  lea     rcx, [rbp+520h+var_4E0]
0x18012e876  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18012e87b  mov     rdx, rax; lpSubKey
0x18012e87e  lea     rax, [rsp+620h+hKey]
0x18012e883  mov     [rsp+620h+phkResult], rax; int
0x18012e888  mov     r9d, 20019h; samDesired
0x18012e88e  xor     r8d, r8d; ulOptions
0x18012e891  mov     r13, 0FFFFFFFF80000002h
0x18012e898  mov     rcx, r13; hKey
0x18012e89b  call    cs:__imp_RegOpenKeyExW
0x18012e8a2  nop     dword ptr [rax+rax+00h]
0x18012e8a7  mov     ebx, eax
0x18012e8a9  cmp     eax, 2
0x18012e8ac  jz      loc_18012F35E
0x18012e8b2  mov     r12d, 80070000h
0x18012e8b8  test    eax, eax
0x18012e8ba  jle     short loc_18012E8C2
0x18012e8bc  movzx   ebx, ax
0x18012e8bf  or      ebx, r12d
0x18012e8c2  test    ebx, ebx
0x18012e8c4  jns     short loc_18012E8E6
0x18012e8c6  mov     rcx, [rbp+528h]; this
0x18012e8cd  mov     r9d, ebx; char *
0x18012e8d0  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012e8d7  mov     edx, 4EBh; void *
0x18012e8dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012e8e1  jmp     loc_18012F361
0x18012e8e6  mov     [rsp+620h+var_5C8], r15
0x18012e8eb  call    cs:__imp_RtlIsStateSeparationEnabled
0x18012e8f2  nop     dword ptr [rax+rax+00h]
0x18012e8f7  lea     rcx, aSoftwareMicros_2; "Software\\Microsoft\\Enrollments"
0x18012e8fe  lea     rdx, aOsdataSoftware_7; "OSData\\Software\\Microsoft\\Enrollment"...
0x18012e905  test    al, al
0x18012e907  cmovz   rdx, rcx
0x18012e90b  lea     rcx, [rbp+520h+var_558]
0x18012e90f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012e914  nop
0x18012e915  lea     r8, psz; "\\"
0x18012e91c  mov     rdx, rax
0x18012e91f  lea     rcx, [rbp+520h+var_4C0]
0x18012e923  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18012e928  nop
0x18012e929  mov     r8, rdi
0x18012e92c  mov     rdx, rax
0x18012e92f  lea     rcx, [rbp+520h+var_578]
0x18012e933  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18012e938  nop
0x18012e939  lea     r8, aDmclient; "\\DMClient"
0x18012e940  mov     rdx, rax
0x18012e943  lea     rcx, [rbp+520h+var_598]
0x18012e947  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18012e94c  nop
0x18012e94d  lea     rcx, [rbp+520h+var_578]
0x18012e951  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012e956  nop
0x18012e957  lea     rcx, [rbp+520h+var_4C0]
0x18012e95b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012e960  nop
0x18012e961  lea     rcx, [rbp+520h+var_558]
0x18012e965  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012e96a  mov     rbx, [rsp+620h+var_5C8]
0x18012e96f  test    rbx, rbx
0x18012e972  jz      short loc_18012E997
0x18012e974  lea     rcx, [rsp+620h+hkey]; this
0x18012e979  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18012e97e  mov     rcx, rbx; hKey
0x18012e981  call    cs:__imp_RegCloseKey
0x18012e988  nop     dword ptr [rax+rax+00h]
0x18012e98d  lea     rcx, [rsp+620h+hkey]; this
0x18012e992  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18012e997  mov     [rsp+620h+var_5C8], r15
0x18012e99c  lea     rcx, [rbp+520h+var_598]
0x18012e9a0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18012e9a5  mov     rdx, rax; lpSubKey
0x18012e9a8  lea     rax, [rsp+620h+var_5C8]
0x18012e9ad  mov     [rsp+620h+phkResult], rax; int
0x18012e9b2  mov     r9d, 20019h; samDesired
0x18012e9b8  xor     r8d, r8d; ulOptions
0x18012e9bb  mov     rcx, r13; hKey
0x18012e9be  call    cs:__imp_RegOpenKeyExW
0x18012e9c5  nop     dword ptr [rax+rax+00h]
0x18012e9ca  mov     ebx, eax
0x18012e9cc  mov     r13d, 2
0x18012e9d2  cmp     eax, r13d
0x18012e9d5  jz      loc_18012F34A
0x18012e9db  test    eax, eax
0x18012e9dd  jle     short loc_18012E9E5
0x18012e9df  movzx   ebx, ax
0x18012e9e2  or      ebx, r12d
0x18012e9e5  test    ebx, ebx
0x18012e9e7  jns     short loc_18012EA1E
0x18012e9e9  mov     rcx, [rbp+528h]; this
0x18012e9f0  mov     r9d, ebx; char *
0x18012e9f3  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012e9fa  mov     edx, 4F4h; void *
0x18012e9ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012ea04  nop
0x18012ea05  lea     rcx, [rbp+520h+var_598]
0x18012ea09  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012ea0e  nop
0x18012ea0f  lea     rcx, [rsp+620h+var_5C8]
0x18012ea14  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012ea19  jmp     loc_18012F361
0x18012ea1e  mov     [rbp+520h+var_460], r15d
0x18012ea25  xor     edx, edx; Val
0x18012ea27  mov     r8d, 204h; Size
0x18012ea2d  lea     rcx, [rbp+520h+var_45C]; void *
0x18012ea34  call    memset_0
0x18012ea39  mov     [rsp+620h+var_5BC], 104h
0x18012ea41  mov     rcx, r14
0x18012ea44  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18012ea49  mov     rbx, rax
0x18012ea4c  mov     rcx, rsi
0x18012ea4f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18012ea54  mov     r8, rbx; unsigned __int16 *
0x18012ea57  mov     rdx, rax; unsigned __int16 *
0x18012ea5a  lea     rcx, [rbp+520h+var_530]; this
0x18012ea5e  call    ??0SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@PEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::SimpleTable(ushort const *,ushort const *)
0x18012ea63  nop
0x18012ea64  lea     rcx, [rbp+520h+var_530]; this
0x18012ea68  call    ?WriteSectionHeaderForTable@SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJXZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::WriteSectionHeaderForTable(void)
0x18012ea6d  mov     ebx, eax
0x18012ea6f  test    eax, eax
0x18012ea71  jns     short loc_18012EA9D
0x18012ea73  mov     edx, 4F9h; void *
0x18012ea78  mov     r9d, eax; char *
0x18012ea7b  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012ea82  mov     rcx, [rbp+528h]; this
0x18012ea89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012ea8e  nop
0x18012ea8f  lea     rcx, [rbp+520h+var_530]; this
0x18012ea93  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012ea98  jmp     loc_18012EA05
0x18012ea9d  lea     rcx, [rsp+620h+var_5E0]
0x18012eaa2  call    ?clear@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x18012eaa7  lea     rdx, aEnrollmentId; "Enrollment ID"
0x18012eaae  lea     rcx, [rbp+520h+var_4C0]
0x18012eab2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012eab7  nop
0x18012eab8  mov     rdx, qword ptr [rsp+620h+var_5E0+8]
0x18012eabd  lea     rcx, [rsp+620h+var_5E0]
0x18012eac2  cmp     rdx, [rsp+620h+var_5D0]
0x18012eac7  jz      short loc_18012EAD4
0x18012eac9  lea     rdx, [rbp+520h+var_4C0]
0x18012eacd  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012ead2  jmp     short loc_18012EADE
0x18012ead4  lea     r8, [rbp+520h+var_4C0]
0x18012ead8  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012eadd  nop
0x18012eade  lea     rcx, [rbp+520h+var_4C0]
0x18012eae2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012eae7  mov     rdx, qword ptr [rsp+620h+var_5E0+8]
0x18012eaec  lea     rcx, [rsp+620h+var_5E0]
0x18012eaf1  cmp     rdx, [rsp+620h+var_5D0]
0x18012eaf6  jz      short loc_18012EB02
0x18012eaf8  mov     rdx, rdi
0x18012eafb  call    ??$_Emplace_back_with_unused_capacity@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(std::wstring const &)
0x18012eb00  jmp     short loc_18012EB0A
0x18012eb02  mov     r8, rdi
0x18012eb05  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18012eb0a  lea     rdx, [rsp+620h+var_5E0]
0x18012eb0f  lea     rcx, [rbp+520h+var_530]
0x18012eb13  call    ?AddTableRow@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(std::vector<std::wstring> &)
0x18012eb18  mov     ebx, eax
0x18012eb1a  test    eax, eax
0x18012eb1c  jns     short loc_18012EB28
0x18012eb1e  mov     edx, 500h
0x18012eb23  jmp     loc_18012EA78
0x18012eb28  mov     [rsp+620h+var_5B0], 3Fh ; '?'
0x18012eb30  xorps   xmm0, xmm0
0x18012eb33  movups  [rbp+520h+var_558], xmm0
0x18012eb37  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18012eb3f  movdqu  [rbp+520h+var_548], xmm1
0x18012eb44  mov     word ptr [rbp+520h+var_558], r15w
0x18012eb49  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18012eb4e  mov     rcx, rdi
0x18012eb51  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18012eb56  lea     r8, [rsp+620h+var_5B0]; unsigned int *
0x18012eb5b  mov     rdx, rax; unsigned __int16 *
0x18012eb5e  call    ?GetEnrollmentType@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJPEBGPEAK@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentType(ushort const *,ulong *)
0x18012eb63  mov     ecx, [rsp+620h+var_5B0]
0x18012eb67  cmp     ecx, 6
0x18012eb6a  jz      short loc_18012EBA4
0x18012eb6c  cmp     ecx, 0Dh
0x18012eb6f  jz      short loc_18012EB9B
0x18012eb71  lea     eax, [rcx-18h]
0x18012eb74  test    eax, 0FFFFFFFDh
0x18012eb79  jz      short loc_18012EB92
0x18012eb7b  lea     rdx, aOther; "Other"
0x18012eb82  lea     rax, aInvalid; "Invalid"
0x18012eb89  cmp     ecx, 3Fh ; '?'
0x18012eb8c  cmovz   rdx, rax
0x18012eb90  jmp     short loc_18012EBAB
0x18012eb92  lea     rdx, aWindowsDeclare; "Windows Declared Configuration(WinDC)"
0x18012eb99  jmp     short loc_18012EBAB
0x18012eb9b  lea     rdx, aMdmEnrollmentW; "MDM Enrollment with Entra ID"
0x18012eba2  jmp     short loc_18012EBAB
0x18012eba4  lea     rdx, aMdmDeviceWithE; "MDM Device with Entra ID"
0x18012ebab  lea     rcx, [rbp+520h+var_558]
0x18012ebaf  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18012ebb4  lea     rdx, asc_1801EF264; "("
0x18012ebbb  lea     rcx, [rbp+520h+var_558]
0x18012ebbf  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18012ebc4  mov     edx, [rsp+620h+var_5B0]
0x18012ebc8  lea     rcx, [rbp+520h+var_496]
0x18012ebcf  call    ??$_UIntegral_to_buff@GI@std@@YAPEAGPEAGI@Z; std::_UIntegral_to_buff<ushort,uint>(ushort *,uint)
0x18012ebd4  lea     r9, [rsp+620h+var_5C0]
0x18012ebd9  lea     r8, [rbp+520h+var_496]
0x18012ebe0  mov     rdx, rax
0x18012ebe3  lea     rcx, [rbp+520h+var_578]
0x18012ebe7  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x18012ebec  nop
0x18012ebed  lea     rdx, [rbp+520h+var_578]
0x18012ebf1  lea     rcx, [rbp+520h+var_558]
0x18012ebf5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18012ebfa  nop
0x18012ebfb  lea     rcx, [rbp+520h+var_578]
0x18012ebff  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012ec04  lea     rdx, asc_1801EE8B0; ")"
0x18012ec0b  lea     rcx, [rbp+520h+var_558]
0x18012ec0f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18012ec14  lea     rcx, [rsp+620h+var_5E0]
0x18012ec19  call    ?clear@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x18012ec1e  lea     rdx, aEnrollmentType; "Enrollment Type"
0x18012ec25  lea     rcx, [rbp+520h+var_4C0]
0x18012ec29  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012ec2e  nop
0x18012ec2f  mov     rdx, qword ptr [rsp+620h+var_5E0+8]
0x18012ec34  lea     rcx, [rsp+620h+var_5E0]
0x18012ec39  cmp     rdx, [rsp+620h+var_5D0]
0x18012ec3e  jz      short loc_18012EC4B
0x18012ec40  lea     rdx, [rbp+520h+var_4C0]
0x18012ec44  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012ec49  jmp     short loc_18012EC55
0x18012ec4b  lea     r8, [rbp+520h+var_4C0]
0x18012ec4f  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012ec54  nop
0x18012ec55  lea     rcx, [rbp+520h+var_4C0]
0x18012ec59  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012ec5e  mov     rdx, qword ptr [rsp+620h+var_5E0+8]
0x18012ec63  lea     rcx, [rsp+620h+var_5E0]
0x18012ec68  cmp     rdx, [rsp+620h+var_5D0]
0x18012ec6d  jz      short loc_18012EC7A
0x18012ec6f  lea     rdx, [rbp+520h+var_558]
  ... truncated ...
```

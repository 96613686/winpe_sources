# WriteDeviceInfo(void)

- ea: `0x18012db44`
- end: `0x18012e789`
- name: `?WriteDeviceInfo@@YAJXZ`
- size: `3141`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180128138`

## callees

- `0x180019080`
- `0x1800e4408`
- `0x1800e4508`
- `0x1800e688c`
- `0x1800e68b0`
- `0x1800e69f4`
- `0x1800e8a44`
- `0x1800ed46c`
- `0x1800edd78`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f00e4`
- `0x1800f4b2c`
- `0x1800faa0c`
- `0x180105480`
- `0x180106b6c`
- `0x180106ee0`
- `0x1801093e8`
- `0x18011273c`
- `0x18012944c`
- `0x180129aac`
- `0x180129dc4`
- `0x180129ee0`
- `0x18012db44`
- `0x180132f50`
- `0x180134e3c`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z` at `0x18012e307`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z` at `0x18012e366`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z` at `0x18012e398`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z` at `0x18012e307`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z` at `0x18012e366`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z` at `0x18012e398`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18012dfe3`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18012dfe3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012dc03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012e2b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012dc03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012e2b0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012dd7e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012dece`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012e188`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012e5e9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012dd7e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012dece`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012e188`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012e5e9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18012e521`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18012e521`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18012dbf3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18012dbf3`
- `api-ms-win-core-sysinfo-l1-2-1!GetPhysicallyInstalledSystemMemory` at `0x18012e298`
- `api-ms-win-core-sysinfo-l1-2-1!GetPhysicallyInstalledSystemMemory` at `0x18012e298`

## string_xrefs

- `0x18012dba3`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012dd01`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012de58`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012dfa8`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012e112`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012e262`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012e4ad`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012e6f8`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012e2cb`: `GetPhysicallyInstalledSystemMemory failed`
- `0x18012e3c2`: `Installed RAM`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 WriteDeviceInfo(void)
{
  int v0; // eax
  unsigned int v1; // ebx
  signed int v3; // eax
  unsigned int v4; // ebx
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // eax
  unsigned int v14; // ebx
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v15; // rbx
  signed int LastError; // eax
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rax
  int v21; // eax
  unsigned int v22; // ebx
  const wchar_t *v23; // rdx
  __int64 v24; // rax
  int v25; // eax
  unsigned int v26; // ebx
  int pdwType; // [rsp+20h] [rbp-438h]
  int pdwTypea; // [rsp+20h] [rbp-438h]
  int pdwTypeb; // [rsp+20h] [rbp-438h]
  int pdwTypec; // [rsp+20h] [rbp-438h]
  int pdwTyped; // [rsp+20h] [rbp-438h]
  int pdwTypee; // [rsp+20h] [rbp-438h]
  _BYTE v33[8]; // [rsp+40h] [rbp-418h] BYREF
  __int64 v34; // [rsp+48h] [rbp-410h]
  __int64 v35; // [rsp+50h] [rbp-408h]
  DWORD nSize; // [rsp+58h] [rbp-400h] BYREF
  unsigned __int64 TotalMemoryInKilobytes; // [rsp+60h] [rbp-3F8h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+68h] [rbp-3F0h] BYREF
  _BYTE v39[16]; // [rsp+A0h] [rbp-3B8h] BYREF
  _BYTE v40[240]; // [rsp+B0h] [rbp-3A8h] BYREF
  _BYTE v41[32]; // [rsp+1A0h] [rbp-2B8h] BYREF
  _BYTE v42[32]; // [rsp+1C0h] [rbp-298h] BYREF
  _BYTE v43[80]; // [rsp+1E0h] [rbp-278h] BYREF
  WCHAR Buffer[264]; // [rsp+230h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+458h] [rbp+0h]

  Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::SimpleTable(
    (Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v43,
    L"Device Info",
    L"DeviceInfoTable");
  v0 = Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::WriteSectionHeaderForTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v43);
  v1 = v0;
  if ( v0 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x325,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)(unsigned int)v0,
      pdwType);
    Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v43);
    return v1;
  }
  nSize = 260;
  TotalMemoryInKilobytes = 0;
  std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(v33);
  if ( GetComputerNameW(Buffer, &nSize) )
  {
    std::wstring::wstring(v41, L"PC name");
    if ( v34 == v35 )
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v33, v34, v41);
    else
      std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v33, v41);
    std::wstring::_Tidy_deallocate(v41);
    std::wstring::wstring(v41, Buffer);
    if ( v34 == v35 )
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v33, v34, v41);
    else
      std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v33, v41);
    std::wstring::_Tidy_deallocate(v41);
    v5 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v43, v33);
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x335,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
        (const char *)(unsigned int)v5,
        pdwType);
      std::vector<std::wstring>::_Tidy(v33);
      Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v43);
      return v6;
    }
    nSize = 260;
    Buffer[0] = 0;
    RegGetValueW(
      HKEY_LOCAL_MACHINE,
      L"Software\\Microsoft\\Windows NT\\CurrentVersion",
      L"RegisteredOrganization",
      2u,
      0,
      Buffer,
      &nSize);
    std::vector<std::wstring>::clear(v33);
    std::wstring::wstring(v41, L"Organization");
    if ( v34 == v35 )
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v33, v34, v41);
    else
      std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v33, v41);
    std::wstring::_Tidy_deallocate(v41);
    std::wstring::wstring(v41, Buffer);
    if ( v34 == v35 )
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v33, v34, v41);
    else
      std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v33, v41);
    std::wstring::_Tidy_deallocate(v41);
    v7 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v43, v33);
    v8 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x341,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
        (const char *)(unsigned int)v7,
        pdwTypea);
      std::vector<std::wstring>::_Tidy(v33);
      Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v43);
      return v8;
    }
    nSize = 260;
    Buffer[0] = 0;
    RegGetValueW(
      HKEY_LOCAL_MACHINE,
      L"Software\\Microsoft\\Windows NT\\CurrentVersion",
      L"ProductName",
      2u,
      0,
      Buffer,
      &nSize);
    std::vector<std::wstring>::clear(v33);
    std::wstring::wstring(v41, L"Edition");
    if ( v34 == v35 )
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v33, v34, v41);
    else
      std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v33, v41);
    std::wstring::_Tidy_deallocate(v41);
    std::wstring::wstring(v41, Buffer);
    if ( v34 == v35 )
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v33, v34, v41);
    else
      std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v33, v41);
    std::wstring::_Tidy_deallocate(v41);
    v9 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v43, v33);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x34D,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
        (const char *)(unsigned int)v9,
        pdwTypeb);
      std::vector<std::wstring>::_Tidy(v33);
      Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v43);
      return v10;
    }
    RtlGetDeviceFamilyInfoEnum(&TotalMemoryInKilobytes, 0, 0);
    nSize = 260;
    Buffer[0] = 0;
    pdwTypec = WORD2(TotalMemoryInKilobytes);
    StringCchPrintfW(Buffer, 0x104u, L"%llu.%llu.%llu.%llu", HIWORD(TotalMemoryInKilobytes));
    std::vector<std::wstring>::clear(v33);
    std::wstring::wstring(v41, L"OS Build");
    if ( v34 == v35 )
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v33, v34, v41);
    else
      std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v33, v41);
    std::wstring::_Tidy_deallocate(v41);
    std::wstring::wstring(v41, Buffer);
    if ( v34 == v35 )
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v33, v34, v41);
    else
      std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v33, v41);
    std::wstring::_Tidy_deallocate(v41);
    v11 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v43, v33);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x35C,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
        (const char *)(unsigned int)v11,
        pdwTypec);
      std::vector<std::wstring>::_Tidy(v33);
      Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v43);
      return v12;
    }
    nSize = 260;
    Buffer[0] = 0;
    RegGetValueW(
      HKEY_LOCAL_MACHINE,
      L"HARDWARE\\DESCRIPTION\\System\\CentralProcessor\\0",
      L"ProcessorNameString",
      2u,
      0,
      Buffer,
      &nSize);
    std::vector<std::wstring>::clear(v33);
    std::wstring::wstring(v41, L"Processor");
    if ( v34 == v35 )
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v33, v34, v41);
    else
      std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v33, v41);
    std::wstring::_Tidy_deallocate(v41);
    std::wstring::wstring(v41, Buffer);
    if ( v34 == v35 )
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v33, v34, v41);
    else
      std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v33, v41);
    std::wstring::_Tidy_deallocate(v41);
    v13 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v43, v33);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x368,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
        (const char *)(unsigned int)v13,
        pdwTyped);
      std::vector<std::wstring>::_Tidy(v33);
      Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v43);
      return v14;
    }
    if ( GetPhysicallyInstalledSystemMemory(&TotalMemoryInKilobytes) )
    {
      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v39);
      TotalMemoryInKilobytes >>= 10;
      v17 = std::basic_ostream<unsigned short>::operator<<(v40, TotalMemoryInKilobytes >> 10);
      std::basic_ostream<unsigned short>::operator<<(v17, 46);
      v18 = ((TotalMemoryInKilobytes & 0x3FF) * (unsigned __int128)0x47AE147AE147AE15uLL) >> 64;
      TotalMemoryInKilobytes = (v18 + (((TotalMemoryInKilobytes & 0x3FF) - v18) >> 1)) >> 6;
      std::basic_ostream<unsigned short>::operator<<(v40, TotalMemoryInKilobytes / 0xA);
      if ( TotalMemoryInKilobytes != 10 * (TotalMemoryInKilobytes / 0xA) )
        std::basic_ostream<unsigned short>::operator<<(v40, TotalMemoryInKilobytes % 0xA);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v40, L" GB");
      std::vector<std::wstring>::clear(v33);
      std::wstring::wstring(v41, L"Installed RAM");
      if ( v34 == v35 )
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v33, v34, v41);
      else
        std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v33, v41);
      std::wstring::_Tidy_deallocate(v41);
      v19 = std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
              v39,
              v42);
      v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v19);
      std::wstring::wstring(v41, v20);
      if ( v34 == v35 )
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v33, v34, v41);
      else
        std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v33, v41);
      std::wstring::_Tidy_deallocate(v41);
      std::wstring::_Tidy_deallocate(v42);
      v21 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v43, v33);
      v22 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x383,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
          (const char *)(unsigned int)v21,
          pdwTyped);
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v39);
        std::vector<std::wstring>::_Tidy(v33);
        Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v43);
        return v22;
      }
      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v39);
    }
    else
    {
      v15 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(
        v15,
        L"GetPhysicallyInstalledSystemMemory failed",
        LastError);
    }
    std::wstring::wstring(v41);
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetSystemInfo(&SystemInfo);
    if ( SystemInfo.wProcessorArchitecture )
    {
      if ( SystemInfo.wProcessorArchitecture == 5 )
      {
        v23 = L"ARM";
      }
      else if ( SystemInfo.wProcessorArchitecture == 6 )
      {
        v23 = L"Intel Itanium-based";
      }
      else
      {
        v23 = L"Unknown";
        if ( SystemInfo.wProcessorArchitecture == 9 )
          v23 = L"64-bit";
      }
      std::wstring::assign(v41, v23);
    }
    else
    {
      std::wstring::assign(v41, L"32-bit");
    }
    std::wstring::append(v41, L" operating system ");
    nSize = 260;
    Buffer[0] = 0;
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Control\\Session Manager\\Environment",
            L"PROCESSOR_ARCHITECTURE",
            2u,
            0,
            Buffer,
            &nSize) )
    {
      std::wstring::append(v41, Buffer);
      std::wstring::append(v41, L"-based processor");
    }
    std::vector<std::wstring>::clear(v33);
    std::wstring::wstring(v42, L"System Type");
    if ( v34 == v35 )
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v33, v34, v42);
    else
      std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v33, v42);
    std::wstring::_Tidy_deallocate(v42);
    v24 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v41);
    std::wstring::wstring(v42, v24);
    if ( v34 == v35 )
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v33, v34, v42);
    else
      std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v33, v42);
    std::wstring::_Tidy_deallocate(v42);
    v25 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v43, v33);
    v26 = v25;
    if ( v25 >= 0 )
    {
      std::wstring::_Tidy_deallocate(v41);
      std::vector<std::wstring>::_Tidy(v33);
      Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v43);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3AB,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
        (const char *)(unsigned int)v25,
        pdwTypee);
      std::wstring::_Tidy_deallocate(v41);
      std::vector<std::wstring>::_Tidy(v33);
      Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v43);
      return v26;
    }
  }
  else
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    std::vector<std::wstring>::_Tidy(v33);
    Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v43);
    return v4;
  }
}

```

## disassembly

```asm
0x18012db44  mov     [rsp+arg_0], rbx
0x18012db49  mov     [rsp+arg_8], rsi
0x18012db4e  push    r15
0x18012db50  sub     rsp, 450h
0x18012db57  mov     rax, cs:__security_cookie
0x18012db5e  xor     rax, rsp
0x18012db61  mov     [rsp+458h+var_18], rax
0x18012db69  lea     r8, aDeviceinfotabl; "DeviceInfoTable"
0x18012db70  lea     rdx, aDeviceInfo; "Device Info"
0x18012db77  lea     rcx, [rsp+458h+var_278]; this
0x18012db7f  call    ??0SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@PEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::SimpleTable(ushort const *,ushort const *)
0x18012db84  nop
0x18012db85  lea     rcx, [rsp+458h+var_278]; this
0x18012db8d  call    ?WriteSectionHeaderForTable@SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJXZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::WriteSectionHeaderForTable(void)
0x18012db92  mov     ebx, eax
0x18012db94  test    eax, eax
0x18012db96  jns     short loc_18012DBC9
0x18012db98  mov     rcx, [rsp+458h]; this
0x18012dba0  mov     r9d, eax; char *
0x18012dba3  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012dbaa  mov     edx, 325h; void *
0x18012dbaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012dbb4  nop
0x18012dbb5  lea     rcx, [rsp+458h+var_278]; this
0x18012dbbd  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012dbc2  mov     eax, ebx
0x18012dbc4  jmp     loc_18012E762
0x18012dbc9  mov     esi, 104h
0x18012dbce  mov     [rsp+458h+nSize], esi
0x18012dbd2  mov     [rsp+458h+TotalMemoryInKilobytes], 0
0x18012dbdb  lea     rcx, [rsp+458h+var_418]
0x18012dbe0  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x18012dbe5  nop
0x18012dbe6  lea     rdx, [rsp+458h+nSize]; nSize
0x18012dbeb  lea     rcx, [rsp+458h+Buffer]; lpBuffer
0x18012dbf3  call    cs:__imp_GetComputerNameW
0x18012dbfa  nop     dword ptr [rax+rax+00h]
0x18012dbff  test    eax, eax
0x18012dc01  jnz     short loc_18012DC3D
0x18012dc03  call    cs:__imp_GetLastError
0x18012dc0a  nop     dword ptr [rax+rax+00h]
0x18012dc0f  mov     ebx, eax
0x18012dc11  test    eax, eax
0x18012dc13  jle     short loc_18012DC1E
0x18012dc15  movzx   ebx, ax
0x18012dc18  or      ebx, 80070000h
0x18012dc1e  lea     rcx, [rsp+458h+var_418]
0x18012dc23  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012dc28  nop
0x18012dc29  lea     rcx, [rsp+458h+var_278]; this
0x18012dc31  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012dc36  mov     eax, ebx
0x18012dc38  jmp     loc_18012E762
0x18012dc3d  lea     rdx, aPcName; "PC name"
0x18012dc44  lea     rcx, [rsp+458h+var_2B8]
0x18012dc4c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012dc51  nop
0x18012dc52  mov     rdx, [rsp+458h+var_410]
0x18012dc57  lea     rcx, [rsp+458h+var_418]
0x18012dc5c  cmp     rdx, [rsp+458h+var_408]
0x18012dc61  jz      short loc_18012DC72
0x18012dc63  lea     rdx, [rsp+458h+var_2B8]
0x18012dc6b  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012dc70  jmp     short loc_18012DC80
0x18012dc72  lea     r8, [rsp+458h+var_2B8]
0x18012dc7a  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012dc7f  nop
0x18012dc80  lea     rcx, [rsp+458h+var_2B8]
0x18012dc88  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012dc8d  lea     rdx, [rsp+458h+Buffer]
0x18012dc95  lea     rcx, [rsp+458h+var_2B8]
0x18012dc9d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012dca2  nop
0x18012dca3  mov     rdx, [rsp+458h+var_410]
0x18012dca8  lea     rcx, [rsp+458h+var_418]
0x18012dcad  cmp     rdx, [rsp+458h+var_408]
0x18012dcb2  jz      short loc_18012DCC3
0x18012dcb4  lea     rdx, [rsp+458h+var_2B8]
0x18012dcbc  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012dcc1  jmp     short loc_18012DCD1
0x18012dcc3  lea     r8, [rsp+458h+var_2B8]
0x18012dccb  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012dcd0  nop
0x18012dcd1  lea     rcx, [rsp+458h+var_2B8]
0x18012dcd9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012dcde  lea     rdx, [rsp+458h+var_418]
0x18012dce3  lea     rcx, [rsp+458h+var_278]
0x18012dceb  call    ?AddTableRow@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(std::vector<std::wstring> &)
0x18012dcf0  mov     ebx, eax
0x18012dcf2  test    eax, eax
0x18012dcf4  jns     short loc_18012DD32
0x18012dcf6  mov     rcx, [rsp+458h]; this
0x18012dcfe  mov     r9d, eax; char *
0x18012dd01  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012dd08  mov     edx, 335h; void *
0x18012dd0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012dd12  nop
0x18012dd13  lea     rcx, [rsp+458h+var_418]
0x18012dd18  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012dd1d  nop
0x18012dd1e  lea     rcx, [rsp+458h+var_278]; this
0x18012dd26  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012dd2b  mov     eax, ebx
0x18012dd2d  jmp     loc_18012E762
0x18012dd32  mov     [rsp+458h+nSize], esi
0x18012dd36  xor     eax, eax
0x18012dd38  mov     [rsp+458h+Buffer], ax
0x18012dd40  lea     rax, [rsp+458h+nSize]
0x18012dd45  mov     [rsp+458h+pcbData], rax; pcbData
0x18012dd4a  lea     rax, [rsp+458h+Buffer]
0x18012dd52  mov     [rsp+458h+pvData], rax; pvData
0x18012dd57  mov     [rsp+458h+pdwType], 0; int
0x18012dd60  mov     r9d, 2; dwFlags
0x18012dd66  lea     r8, aRegisteredorga; "RegisteredOrganization"
0x18012dd6d  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\Windows NT\\Curren"...
0x18012dd74  mov     r15, 0FFFFFFFF80000002h
0x18012dd7b  mov     rcx, r15; hkey
0x18012dd7e  call    cs:__imp_RegGetValueW
0x18012dd85  nop     dword ptr [rax+rax+00h]
0x18012dd8a  lea     rcx, [rsp+458h+var_418]
0x18012dd8f  call    ?clear@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x18012dd94  lea     rdx, aOrganization; "Organization"
0x18012dd9b  lea     rcx, [rsp+458h+var_2B8]
0x18012dda3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012dda8  nop
0x18012dda9  mov     rdx, [rsp+458h+var_410]
0x18012ddae  lea     rcx, [rsp+458h+var_418]
0x18012ddb3  cmp     rdx, [rsp+458h+var_408]
0x18012ddb8  jz      short loc_18012DDC9
0x18012ddba  lea     rdx, [rsp+458h+var_2B8]
0x18012ddc2  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012ddc7  jmp     short loc_18012DDD7
0x18012ddc9  lea     r8, [rsp+458h+var_2B8]
0x18012ddd1  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012ddd6  nop
0x18012ddd7  lea     rcx, [rsp+458h+var_2B8]
0x18012dddf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012dde4  lea     rdx, [rsp+458h+Buffer]
0x18012ddec  lea     rcx, [rsp+458h+var_2B8]
0x18012ddf4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012ddf9  nop
0x18012ddfa  mov     rdx, [rsp+458h+var_410]
0x18012ddff  lea     rcx, [rsp+458h+var_418]
0x18012de04  cmp     rdx, [rsp+458h+var_408]
0x18012de09  jz      short loc_18012DE1A
0x18012de0b  lea     rdx, [rsp+458h+var_2B8]
0x18012de13  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012de18  jmp     short loc_18012DE28
0x18012de1a  lea     r8, [rsp+458h+var_2B8]
0x18012de22  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012de27  nop
0x18012de28  lea     rcx, [rsp+458h+var_2B8]
0x18012de30  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012de35  lea     rdx, [rsp+458h+var_418]
0x18012de3a  lea     rcx, [rsp+458h+var_278]
0x18012de42  call    ?AddTableRow@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(std::vector<std::wstring> &)
0x18012de47  mov     ebx, eax
0x18012de49  test    eax, eax
0x18012de4b  jns     short loc_18012DE89
0x18012de4d  mov     rcx, [rsp+458h]; this
0x18012de55  mov     r9d, eax; char *
0x18012de58  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012de5f  mov     edx, 341h; void *
0x18012de64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012de69  nop
0x18012de6a  lea     rcx, [rsp+458h+var_418]
0x18012de6f  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012de74  nop
0x18012de75  lea     rcx, [rsp+458h+var_278]; this
0x18012de7d  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012de82  mov     eax, ebx
0x18012de84  jmp     loc_18012E762
0x18012de89  mov     [rsp+458h+nSize], esi
0x18012de8d  xor     eax, eax
0x18012de8f  mov     [rsp+458h+Buffer], ax
0x18012de97  lea     rax, [rsp+458h+nSize]
0x18012de9c  mov     [rsp+458h+pcbData], rax; pcbData
0x18012dea1  lea     rax, [rsp+458h+Buffer]
0x18012dea9  mov     [rsp+458h+pvData], rax; pvData
0x18012deae  mov     [rsp+458h+pdwType], 0; int
0x18012deb7  mov     r9d, 2; dwFlags
0x18012debd  lea     r8, aProductname; "ProductName"
0x18012dec4  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\Windows NT\\Curren"...
0x18012decb  mov     rcx, r15; hkey
0x18012dece  call    cs:__imp_RegGetValueW
0x18012ded5  nop     dword ptr [rax+rax+00h]
0x18012deda  lea     rcx, [rsp+458h+var_418]
0x18012dedf  call    ?clear@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x18012dee4  lea     rdx, aEdition; "Edition"
0x18012deeb  lea     rcx, [rsp+458h+var_2B8]
0x18012def3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012def8  nop
0x18012def9  mov     rdx, [rsp+458h+var_410]
0x18012defe  lea     rcx, [rsp+458h+var_418]
0x18012df03  cmp     rdx, [rsp+458h+var_408]
0x18012df08  jz      short loc_18012DF19
0x18012df0a  lea     rdx, [rsp+458h+var_2B8]
0x18012df12  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012df17  jmp     short loc_18012DF27
0x18012df19  lea     r8, [rsp+458h+var_2B8]
0x18012df21  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012df26  nop
0x18012df27  lea     rcx, [rsp+458h+var_2B8]
0x18012df2f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012df34  lea     rdx, [rsp+458h+Buffer]
0x18012df3c  lea     rcx, [rsp+458h+var_2B8]
0x18012df44  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012df49  nop
0x18012df4a  mov     rdx, [rsp+458h+var_410]
0x18012df4f  lea     rcx, [rsp+458h+var_418]
0x18012df54  cmp     rdx, [rsp+458h+var_408]
0x18012df59  jz      short loc_18012DF6A
0x18012df5b  lea     rdx, [rsp+458h+var_2B8]
0x18012df63  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012df68  jmp     short loc_18012DF78
0x18012df6a  lea     r8, [rsp+458h+var_2B8]
0x18012df72  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012df77  nop
0x18012df78  lea     rcx, [rsp+458h+var_2B8]
0x18012df80  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012df85  lea     rdx, [rsp+458h+var_418]
0x18012df8a  lea     rcx, [rsp+458h+var_278]
0x18012df92  call    ?AddTableRow@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(std::vector<std::wstring> &)
0x18012df97  mov     ebx, eax
0x18012df99  test    eax, eax
0x18012df9b  jns     short loc_18012DFD9
0x18012df9d  mov     rcx, [rsp+458h]; this
0x18012dfa5  mov     r9d, eax; char *
0x18012dfa8  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012dfaf  mov     edx, 34Dh; void *
0x18012dfb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012dfb9  nop
0x18012dfba  lea     rcx, [rsp+458h+var_418]
0x18012dfbf  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012dfc4  nop
0x18012dfc5  lea     rcx, [rsp+458h+var_278]; this
0x18012dfcd  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012dfd2  mov     eax, ebx
0x18012dfd4  jmp     loc_18012E762
0x18012dfd9  xor     r8d, r8d
0x18012dfdc  xor     edx, edx
0x18012dfde  lea     rcx, [rsp+458h+TotalMemoryInKilobytes]
0x18012dfe3  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18012dfea  nop     dword ptr [rax+rax+00h]
0x18012dfef  mov     [rsp+458h+nSize], esi
0x18012dff3  xor     eax, eax
0x18012dff5  mov     [rsp+458h+Buffer], ax
0x18012dffd  mov     r9, [rsp+458h+TotalMemoryInKilobytes]
0x18012e002  movzx   r8d, r9w
0x18012e006  mov     rax, r9
0x18012e009  shr     rax, 10h
0x18012e00d  movzx   edx, ax
0x18012e010  mov     rax, r9
0x18012e013  shr     rax, 20h
0x18012e017  movzx   ecx, ax
0x18012e01a  shr     r9, 30h
0x18012e01e  mov     [rsp+458h+pcbData], r8
0x18012e023  mov     [rsp+458h+pvData], rdx
0x18012e028  mov     [rsp+458h+pdwType], rcx; int
0x18012e02d  lea     r8, aLluLluLluLlu; "%llu.%llu.%llu.%llu"
0x18012e034  mov     rdx, rsi; unsigned __int64
0x18012e037  lea     rcx, [rsp+458h+Buffer]; unsigned __int16 *
0x18012e03f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18012e044  lea     rcx, [rsp+458h+var_418]
0x18012e049  call    ?clear@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x18012e04e  lea     rdx, aOsBuild; "OS Build"
0x18012e055  lea     rcx, [rsp+458h+var_2B8]
0x18012e05d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012e062  nop
0x18012e063  mov     rdx, [rsp+458h+var_410]
0x18012e068  lea     rcx, [rsp+458h+var_418]
0x18012e06d  cmp     rdx, [rsp+458h+var_408]
0x18012e072  jz      short loc_18012E083
0x18012e074  lea     rdx, [rsp+458h+var_2B8]
0x18012e07c  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012e081  jmp     short loc_18012E091
0x18012e083  lea     r8, [rsp+458h+var_2B8]
0x18012e08b  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012e090  nop
0x18012e091  lea     rcx, [rsp+458h+var_2B8]
0x18012e099  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012e09e  lea     rdx, [rsp+458h+Buffer]
0x18012e0a6  lea     rcx, [rsp+458h+var_2B8]
0x18012e0ae  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012e0b3  nop
0x18012e0b4  mov     rdx, [rsp+458h+var_410]
0x18012e0b9  lea     rcx, [rsp+458h+var_418]
0x18012e0be  cmp     rdx, [rsp+458h+var_408]
0x18012e0c3  jz      short loc_18012E0D4
0x18012e0c5  lea     rdx, [rsp+458h+var_2B8]
0x18012e0cd  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012e0d2  jmp     short loc_18012E0E2
0x18012e0d4  lea     r8, [rsp+458h+var_2B8]
0x18012e0dc  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012e0e1  nop
0x18012e0e2  lea     rcx, [rsp+458h+var_2B8]
0x18012e0ea  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012e0ef  lea     rdx, [rsp+458h+var_418]
0x18012e0f4  lea     rcx, [rsp+458h+var_278]
0x18012e0fc  call    ?AddTableRow@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(std::vector<std::wstring> &)
  ... truncated ...
```

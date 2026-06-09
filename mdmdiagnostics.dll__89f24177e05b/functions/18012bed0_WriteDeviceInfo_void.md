# WriteDeviceInfo(void)

- ea: `0x18012bed0`
- end: `0x18012cacc`
- name: `?WriteDeviceInfo@@YAJXZ`
- size: `3068`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801266fc`

## callees

- `0x180019000`
- `0x1800e4348`
- `0x1800e4444`
- `0x1800e66b8`
- `0x1800e66dc`
- `0x1800e680c`
- `0x1800e87e8`
- `0x1800ece5c`
- `0x1800ed730`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800ef900`
- `0x1800f3f8c`
- `0x1800f9a0c`
- `0x180104270`
- `0x1801058cc`
- `0x180105c40`
- `0x1801080f8`
- `0x18011129c`
- `0x180127960`
- `0x180127fa8`
- `0x1801282b0`
- `0x1801283b0`
- `0x18012bed0`
- `0x180131140`
- `0x180132f88`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z` at `0x18012c663`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z` at `0x18012c6bc`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z` at `0x18012c6e8`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z` at `0x18012c663`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z` at `0x18012c6bc`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z` at `0x18012c6e8`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18012c357`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18012c357`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bf89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012c612`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bf89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012c612`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012c0fe`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012c248`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012c4f6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012c932`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012c0fe`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012c248`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012c4f6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012c932`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18012c870`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18012c870`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18012bf7f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18012bf7f`
- `api-ms-win-core-sysinfo-l1-2-1!GetPhysicallyInstalledSystemMemory` at `0x18012c600`
- `api-ms-win-core-sysinfo-l1-2-1!GetPhysicallyInstalledSystemMemory` at `0x18012c600`

## string_xrefs

- `0x18012bf2f`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012c081`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012c1d2`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012c31c`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012c480`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012c5ca`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012c7fc`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012ca3b`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012c627`: `GetPhysicallyInstalledSystemMemory failed`
- `0x18012c70c`: `Installed RAM`

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
  int v20; // eax
  unsigned int v21; // ebx
  const wchar_t *v22; // rdx
  __int64 v23; // rax
  int v24; // eax
  unsigned int v25; // ebx
  int pdwType; // [rsp+20h] [rbp-438h]
  int pdwTypea; // [rsp+20h] [rbp-438h]
  int pdwTypeb; // [rsp+20h] [rbp-438h]
  int pdwTypec; // [rsp+20h] [rbp-438h]
  int pdwTyped; // [rsp+20h] [rbp-438h]
  int pdwTypee; // [rsp+20h] [rbp-438h]
  DWORD nSize; // [rsp+40h] [rbp-418h] BYREF
  _BYTE v33[8]; // [rsp+48h] [rbp-410h] BYREF
  __int64 v34; // [rsp+50h] [rbp-408h]
  __int64 v35; // [rsp+58h] [rbp-400h]
  unsigned __int64 TotalMemoryInKilobytes; // [rsp+60h] [rbp-3F8h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+68h] [rbp-3F0h] BYREF
  _BYTE v38[16]; // [rsp+A0h] [rbp-3B8h] BYREF
  _BYTE v39[8]; // [rsp+B0h] [rbp-3A8h] BYREF
  _BYTE v40[232]; // [rsp+B8h] [rbp-3A0h] BYREF
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
      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v38);
      TotalMemoryInKilobytes >>= 10;
      v17 = std::basic_ostream<unsigned short>::operator<<(v39, TotalMemoryInKilobytes >> 10);
      std::basic_ostream<unsigned short>::operator<<(v17, 46);
      v18 = ((TotalMemoryInKilobytes & 0x3FF) * (unsigned __int128)0x47AE147AE147AE15uLL) >> 64;
      TotalMemoryInKilobytes = (v18 + (((TotalMemoryInKilobytes & 0x3FF) - v18) >> 1)) >> 6;
      std::basic_ostream<unsigned short>::operator<<(v39, TotalMemoryInKilobytes / 0xA);
      if ( TotalMemoryInKilobytes != 10 * (TotalMemoryInKilobytes / 0xA) )
        std::basic_ostream<unsigned short>::operator<<(v39, TotalMemoryInKilobytes % 0xA);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v39, L" GB");
      std::vector<std::wstring>::clear(v33);
      std::wstring::wstring(v41, L"Installed RAM");
      if ( v34 == v35 )
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v33, v34, v41);
      else
        std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v33, v41);
      std::wstring::_Tidy_deallocate(v41);
      std::basic_stringbuf<unsigned short>::str(v40, v42);
      v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v42);
      std::wstring::wstring(v41, v19);
      if ( v34 == v35 )
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v33, v34, v41);
      else
        std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v33, v41);
      std::wstring::_Tidy_deallocate(v41);
      std::wstring::_Tidy_deallocate(v42);
      v20 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v43, v33);
      v21 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x383,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
          (const char *)(unsigned int)v20,
          pdwTyped);
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v38);
        std::vector<std::wstring>::_Tidy(v33);
        Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v43);
        return v21;
      }
      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v38);
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
        v22 = L"ARM";
      }
      else if ( SystemInfo.wProcessorArchitecture == 6 )
      {
        v22 = L"Intel Itanium-based";
      }
      else
      {
        v22 = L"Unknown";
        if ( SystemInfo.wProcessorArchitecture == 9 )
          v22 = L"64-bit";
      }
      std::wstring::assign(v41, v22);
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
    v23 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v41);
    std::wstring::wstring(v42, v23);
    if ( v34 == v35 )
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v33, v34, v42);
    else
      std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v33, v42);
    std::wstring::_Tidy_deallocate(v42);
    v24 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v43, v33);
    v25 = v24;
    if ( v24 >= 0 )
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
        (const char *)(unsigned int)v24,
        pdwTypee);
      std::wstring::_Tidy_deallocate(v41);
      std::vector<std::wstring>::_Tidy(v33);
      Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v43);
      return v25;
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
0x18012bed0  mov     [rsp+arg_0], rbx
0x18012bed5  mov     [rsp+arg_8], rsi
0x18012beda  push    r15
0x18012bedc  sub     rsp, 450h
0x18012bee3  mov     rax, cs:__security_cookie
0x18012beea  xor     rax, rsp
0x18012beed  mov     [rsp+458h+var_18], rax
0x18012bef5  lea     r8, aDeviceinfotabl; "DeviceInfoTable"
0x18012befc  lea     rdx, aDeviceInfo; "Device Info"
0x18012bf03  lea     rcx, [rsp+458h+var_278]; this
0x18012bf0b  call    ??0SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@PEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::SimpleTable(ushort const *,ushort const *)
0x18012bf10  nop
0x18012bf11  lea     rcx, [rsp+458h+var_278]; this
0x18012bf19  call    ?WriteSectionHeaderForTable@SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJXZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::WriteSectionHeaderForTable(void)
0x18012bf1e  mov     ebx, eax
0x18012bf20  test    eax, eax
0x18012bf22  jns     short loc_18012BF55
0x18012bf24  mov     rcx, [rsp+458h]; this
0x18012bf2c  mov     r9d, eax; char *
0x18012bf2f  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012bf36  mov     edx, 325h; void *
0x18012bf3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012bf40  nop
0x18012bf41  lea     rcx, [rsp+458h+var_278]; this
0x18012bf49  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012bf4e  mov     eax, ebx
0x18012bf50  jmp     loc_18012CAA5
0x18012bf55  mov     esi, 104h
0x18012bf5a  mov     [rsp+458h+nSize], esi
0x18012bf5e  mov     [rsp+458h+TotalMemoryInKilobytes], 0
0x18012bf67  lea     rcx, [rsp+458h+var_410]
0x18012bf6c  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x18012bf71  nop
0x18012bf72  lea     rdx, [rsp+458h+nSize]; nSize
0x18012bf77  lea     rcx, [rsp+458h+Buffer]; lpBuffer
0x18012bf7f  call    cs:__imp_GetComputerNameW
0x18012bf85  test    eax, eax
0x18012bf87  jnz     short loc_18012BFBD
0x18012bf89  call    cs:__imp_GetLastError
0x18012bf8f  mov     ebx, eax
0x18012bf91  test    eax, eax
0x18012bf93  jle     short loc_18012BF9E
0x18012bf95  movzx   ebx, ax
0x18012bf98  or      ebx, 80070000h
0x18012bf9e  lea     rcx, [rsp+458h+var_410]
0x18012bfa3  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012bfa8  nop
0x18012bfa9  lea     rcx, [rsp+458h+var_278]; this
0x18012bfb1  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012bfb6  mov     eax, ebx
0x18012bfb8  jmp     loc_18012CAA5
0x18012bfbd  lea     rdx, aPcName; "PC name"
0x18012bfc4  lea     rcx, [rsp+458h+var_2B8]
0x18012bfcc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012bfd1  nop
0x18012bfd2  mov     rdx, [rsp+458h+var_408]
0x18012bfd7  lea     rcx, [rsp+458h+var_410]
0x18012bfdc  cmp     rdx, [rsp+458h+var_400]
0x18012bfe1  jz      short loc_18012BFF2
0x18012bfe3  lea     rdx, [rsp+458h+var_2B8]
0x18012bfeb  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012bff0  jmp     short loc_18012C000
0x18012bff2  lea     r8, [rsp+458h+var_2B8]
0x18012bffa  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012bfff  nop
0x18012c000  lea     rcx, [rsp+458h+var_2B8]
0x18012c008  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012c00d  lea     rdx, [rsp+458h+Buffer]
0x18012c015  lea     rcx, [rsp+458h+var_2B8]
0x18012c01d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012c022  nop
0x18012c023  mov     rdx, [rsp+458h+var_408]
0x18012c028  lea     rcx, [rsp+458h+var_410]
0x18012c02d  cmp     rdx, [rsp+458h+var_400]
0x18012c032  jz      short loc_18012C043
0x18012c034  lea     rdx, [rsp+458h+var_2B8]
0x18012c03c  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012c041  jmp     short loc_18012C051
0x18012c043  lea     r8, [rsp+458h+var_2B8]
0x18012c04b  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012c050  nop
0x18012c051  lea     rcx, [rsp+458h+var_2B8]
0x18012c059  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012c05e  lea     rdx, [rsp+458h+var_410]
0x18012c063  lea     rcx, [rsp+458h+var_278]
0x18012c06b  call    ?AddTableRow@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(std::vector<std::wstring> &)
0x18012c070  mov     ebx, eax
0x18012c072  test    eax, eax
0x18012c074  jns     short loc_18012C0B2
0x18012c076  mov     rcx, [rsp+458h]; this
0x18012c07e  mov     r9d, eax; char *
0x18012c081  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012c088  mov     edx, 335h; void *
0x18012c08d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012c092  nop
0x18012c093  lea     rcx, [rsp+458h+var_410]
0x18012c098  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012c09d  nop
0x18012c09e  lea     rcx, [rsp+458h+var_278]; this
0x18012c0a6  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012c0ab  mov     eax, ebx
0x18012c0ad  jmp     loc_18012CAA5
0x18012c0b2  mov     [rsp+458h+nSize], esi
0x18012c0b6  xor     eax, eax
0x18012c0b8  mov     [rsp+458h+Buffer], ax
0x18012c0c0  lea     rax, [rsp+458h+nSize]
0x18012c0c5  mov     [rsp+458h+pcbData], rax; pcbData
0x18012c0ca  lea     rax, [rsp+458h+Buffer]
0x18012c0d2  mov     [rsp+458h+pvData], rax; pvData
0x18012c0d7  mov     [rsp+458h+pdwType], 0; int
0x18012c0e0  mov     r9d, 2; dwFlags
0x18012c0e6  lea     r8, aRegisteredorga; "RegisteredOrganization"
0x18012c0ed  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\Windows NT\\Curren"...
0x18012c0f4  mov     r15, 0FFFFFFFF80000002h
0x18012c0fb  mov     rcx, r15; hkey
0x18012c0fe  call    cs:__imp_RegGetValueW
0x18012c104  lea     rcx, [rsp+458h+var_410]
0x18012c109  call    ?clear@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x18012c10e  lea     rdx, aOrganization; "Organization"
0x18012c115  lea     rcx, [rsp+458h+var_2B8]
0x18012c11d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012c122  nop
0x18012c123  mov     rdx, [rsp+458h+var_408]
0x18012c128  lea     rcx, [rsp+458h+var_410]
0x18012c12d  cmp     rdx, [rsp+458h+var_400]
0x18012c132  jz      short loc_18012C143
0x18012c134  lea     rdx, [rsp+458h+var_2B8]
0x18012c13c  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012c141  jmp     short loc_18012C151
0x18012c143  lea     r8, [rsp+458h+var_2B8]
0x18012c14b  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012c150  nop
0x18012c151  lea     rcx, [rsp+458h+var_2B8]
0x18012c159  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012c15e  lea     rdx, [rsp+458h+Buffer]
0x18012c166  lea     rcx, [rsp+458h+var_2B8]
0x18012c16e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012c173  nop
0x18012c174  mov     rdx, [rsp+458h+var_408]
0x18012c179  lea     rcx, [rsp+458h+var_410]
0x18012c17e  cmp     rdx, [rsp+458h+var_400]
0x18012c183  jz      short loc_18012C194
0x18012c185  lea     rdx, [rsp+458h+var_2B8]
0x18012c18d  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012c192  jmp     short loc_18012C1A2
0x18012c194  lea     r8, [rsp+458h+var_2B8]
0x18012c19c  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012c1a1  nop
0x18012c1a2  lea     rcx, [rsp+458h+var_2B8]
0x18012c1aa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012c1af  lea     rdx, [rsp+458h+var_410]
0x18012c1b4  lea     rcx, [rsp+458h+var_278]
0x18012c1bc  call    ?AddTableRow@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(std::vector<std::wstring> &)
0x18012c1c1  mov     ebx, eax
0x18012c1c3  test    eax, eax
0x18012c1c5  jns     short loc_18012C203
0x18012c1c7  mov     rcx, [rsp+458h]; this
0x18012c1cf  mov     r9d, eax; char *
0x18012c1d2  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012c1d9  mov     edx, 341h; void *
0x18012c1de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012c1e3  nop
0x18012c1e4  lea     rcx, [rsp+458h+var_410]
0x18012c1e9  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012c1ee  nop
0x18012c1ef  lea     rcx, [rsp+458h+var_278]; this
0x18012c1f7  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012c1fc  mov     eax, ebx
0x18012c1fe  jmp     loc_18012CAA5
0x18012c203  mov     [rsp+458h+nSize], esi
0x18012c207  xor     eax, eax
0x18012c209  mov     [rsp+458h+Buffer], ax
0x18012c211  lea     rax, [rsp+458h+nSize]
0x18012c216  mov     [rsp+458h+pcbData], rax; pcbData
0x18012c21b  lea     rax, [rsp+458h+Buffer]
0x18012c223  mov     [rsp+458h+pvData], rax; pvData
0x18012c228  mov     [rsp+458h+pdwType], 0; int
0x18012c231  mov     r9d, 2; dwFlags
0x18012c237  lea     r8, aProductname; "ProductName"
0x18012c23e  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\Windows NT\\Curren"...
0x18012c245  mov     rcx, r15; hkey
0x18012c248  call    cs:__imp_RegGetValueW
0x18012c24e  lea     rcx, [rsp+458h+var_410]
0x18012c253  call    ?clear@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x18012c258  lea     rdx, aEdition; "Edition"
0x18012c25f  lea     rcx, [rsp+458h+var_2B8]
0x18012c267  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012c26c  nop
0x18012c26d  mov     rdx, [rsp+458h+var_408]
0x18012c272  lea     rcx, [rsp+458h+var_410]
0x18012c277  cmp     rdx, [rsp+458h+var_400]
0x18012c27c  jz      short loc_18012C28D
0x18012c27e  lea     rdx, [rsp+458h+var_2B8]
0x18012c286  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012c28b  jmp     short loc_18012C29B
0x18012c28d  lea     r8, [rsp+458h+var_2B8]
0x18012c295  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012c29a  nop
0x18012c29b  lea     rcx, [rsp+458h+var_2B8]
0x18012c2a3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012c2a8  lea     rdx, [rsp+458h+Buffer]
0x18012c2b0  lea     rcx, [rsp+458h+var_2B8]
0x18012c2b8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012c2bd  nop
0x18012c2be  mov     rdx, [rsp+458h+var_408]
0x18012c2c3  lea     rcx, [rsp+458h+var_410]
0x18012c2c8  cmp     rdx, [rsp+458h+var_400]
0x18012c2cd  jz      short loc_18012C2DE
0x18012c2cf  lea     rdx, [rsp+458h+var_2B8]
0x18012c2d7  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012c2dc  jmp     short loc_18012C2EC
0x18012c2de  lea     r8, [rsp+458h+var_2B8]
0x18012c2e6  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012c2eb  nop
0x18012c2ec  lea     rcx, [rsp+458h+var_2B8]
0x18012c2f4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012c2f9  lea     rdx, [rsp+458h+var_410]
0x18012c2fe  lea     rcx, [rsp+458h+var_278]
0x18012c306  call    ?AddTableRow@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(std::vector<std::wstring> &)
0x18012c30b  mov     ebx, eax
0x18012c30d  test    eax, eax
0x18012c30f  jns     short loc_18012C34D
0x18012c311  mov     rcx, [rsp+458h]; this
0x18012c319  mov     r9d, eax; char *
0x18012c31c  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012c323  mov     edx, 34Dh; void *
0x18012c328  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012c32d  nop
0x18012c32e  lea     rcx, [rsp+458h+var_410]
0x18012c333  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012c338  nop
0x18012c339  lea     rcx, [rsp+458h+var_278]; this
0x18012c341  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012c346  mov     eax, ebx
0x18012c348  jmp     loc_18012CAA5
0x18012c34d  xor     r8d, r8d
0x18012c350  xor     edx, edx
0x18012c352  lea     rcx, [rsp+458h+TotalMemoryInKilobytes]
0x18012c357  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18012c35d  mov     [rsp+458h+nSize], esi
0x18012c361  xor     eax, eax
0x18012c363  mov     [rsp+458h+Buffer], ax
0x18012c36b  mov     r9, [rsp+458h+TotalMemoryInKilobytes]
0x18012c370  movzx   r8d, r9w
0x18012c374  mov     rax, r9
0x18012c377  shr     rax, 10h
0x18012c37b  movzx   edx, ax
0x18012c37e  mov     rax, r9
0x18012c381  shr     rax, 20h
0x18012c385  movzx   ecx, ax
0x18012c388  shr     r9, 30h
0x18012c38c  mov     [rsp+458h+pcbData], r8
0x18012c391  mov     [rsp+458h+pvData], rdx
0x18012c396  mov     [rsp+458h+pdwType], rcx; int
0x18012c39b  lea     r8, aLluLluLluLlu; "%llu.%llu.%llu.%llu"
0x18012c3a2  mov     rdx, rsi; unsigned __int64
0x18012c3a5  lea     rcx, [rsp+458h+Buffer]; unsigned __int16 *
0x18012c3ad  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18012c3b2  lea     rcx, [rsp+458h+var_410]
0x18012c3b7  call    ?clear@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x18012c3bc  lea     rdx, aOsBuild; "OS Build"
0x18012c3c3  lea     rcx, [rsp+458h+var_2B8]
0x18012c3cb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012c3d0  nop
0x18012c3d1  mov     rdx, [rsp+458h+var_408]
0x18012c3d6  lea     rcx, [rsp+458h+var_410]
0x18012c3db  cmp     rdx, [rsp+458h+var_400]
0x18012c3e0  jz      short loc_18012C3F1
0x18012c3e2  lea     rdx, [rsp+458h+var_2B8]
0x18012c3ea  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012c3ef  jmp     short loc_18012C3FF
0x18012c3f1  lea     r8, [rsp+458h+var_2B8]
0x18012c3f9  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012c3fe  nop
0x18012c3ff  lea     rcx, [rsp+458h+var_2B8]
0x18012c407  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012c40c  lea     rdx, [rsp+458h+Buffer]
0x18012c414  lea     rcx, [rsp+458h+var_2B8]
0x18012c41c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012c421  nop
0x18012c422  mov     rdx, [rsp+458h+var_408]
0x18012c427  lea     rcx, [rsp+458h+var_410]
0x18012c42c  cmp     rdx, [rsp+458h+var_400]
0x18012c431  jz      short loc_18012C442
0x18012c433  lea     rdx, [rsp+458h+var_2B8]
0x18012c43b  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012c440  jmp     short loc_18012C450
0x18012c442  lea     r8, [rsp+458h+var_2B8]
0x18012c44a  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012c44f  nop
0x18012c450  lea     rcx, [rsp+458h+var_2B8]
0x18012c458  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012c45d  lea     rdx, [rsp+458h+var_410]
0x18012c462  lea     rcx, [rsp+458h+var_278]
0x18012c46a  call    ?AddTableRow@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(std::vector<std::wstring> &)
0x18012c46f  mov     ebx, eax
0x18012c471  test    eax, eax
0x18012c473  jns     short loc_18012C4B1
0x18012c475  mov     rcx, [rsp+458h]; this
0x18012c47d  mov     r9d, eax; char *
  ... truncated ...
```

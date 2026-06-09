# MdmLogCollector::CollectLog(ushort const *,MdmLogCollectorOutputOption)

- ea: `0x18010cb20`
- end: `0x18010d489`
- name: `?CollectLog@MdmLogCollector@@QEAAJPEBGW4MdmLogCollectorOutputOption@@@Z`
- size: `2409`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800fabb4`

## callees

- `0x180019080`
- `0x1800ed46c`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800fa50c`
- `0x1800fa538`
- `0x1800fa600`
- `0x180104be8`
- `0x180104cec`
- `0x18010562c`
- `0x180105744`
- `0x18010bd00`
- `0x18010cb20`
- `0x18010fc0c`
- `0x180111204`
- `0x180127a74`
- `0x180146f90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x18010cb88`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x18010cb88`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18010cf22`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18010cf22`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010cdb4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010cde8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010cdb4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010cde8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18010cb79`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18010cb79`
- `DMCmnUtils!DmGetUserSidFromToken` at `0x18010cc5a`
- `DMCmnUtils!DmGetUserSidFromToken` at `0x18010cf67`
- `DMCmnUtils!DmGetUserSidFromToken` at `0x18010cc5a`
- `DMCmnUtils!DmGetUserSidFromToken` at `0x18010cf67`
- `CabAPI!Cab_CreateCab` at `0x18010d274`
- `CabAPI!Cab_CreateCab` at `0x18010d274`

## string_xrefs

- `0x18010cbdb`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010cc77`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010cd47`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010ce2c`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010ceb1`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010cf84`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010d06e`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010d1c9`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010d291`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010d36a`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall MdmLogCollector::CollectLog(void **a1, const WCHAR *a2, int a3)
{
  ULONGLONG TickCount64; // rax
  int v7; // eax
  unsigned int v8; // edi
  int UserSidFromToken; // eax
  unsigned int v11; // edi
  int v12; // eax
  unsigned int v13; // edi
  const WCHAR *v14; // rax
  const WCHAR *v15; // rax
  int WorkingFolder; // eax
  unsigned int v17; // edi
  wil *v18; // rax
  const WCHAR *v19; // rax
  int v20; // eax
  unsigned int v21; // edi
  wil *v22; // rax
  int v23; // eax
  unsigned int v24; // ebx
  wil *v25; // rax
  wil *v26; // rax
  int v27; // eax
  unsigned int v28; // ebx
  wil *v29; // rax
  const unsigned __int16 *v30; // rax
  int v31; // ebx
  __int64 v32; // rax
  __int64 v33; // rcx
  wil *v34; // rax
  int v35; // eax
  unsigned int v36; // ebx
  wil *v37; // rax
  __int64 v38; // rdi
  __int64 v39; // rbx
  __int64 v40; // rax
  int Cab; // eax
  unsigned int v42; // ebx
  wil *v43; // rax
  wil *v44; // rax
  __int64 v45; // rbx
  __int64 v46; // rcx
  int ZipFromDirectory; // eax
  unsigned int v48; // ebx
  wil *v49; // rax
  wil *v50; // rax
  wil *v51; // rax
  int v52; // [rsp+20h] [rbp-C8h]
  __int64 v53; // [rsp+30h] [rbp-B8h] BYREF
  unsigned __int16 *v54; // [rsp+38h] [rbp-B0h] BYREF
  int v55; // [rsp+40h] [rbp-A8h] BYREF
  _BYTE v56[16]; // [rsp+48h] [rbp-A0h] BYREF
  _OWORD *v57; // [rsp+58h] [rbp-90h] BYREF
  char v58; // [rsp+60h] [rbp-88h]
  _OWORD v59[2]; // [rsp+68h] [rbp-80h] BYREF
  _OWORD v60[2]; // [rsp+88h] [rbp-60h] BYREF
  _OWORD v61[2]; // [rsp+A8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v59[0] = 0;
  v59[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v59[0]) = 0;
  v53 = -1;
  v56[0] = 0;
  v56[2] = 0;
  TickCount64 = GetTickCount64();
  _o_srand(TickCount64);
  v60[0] = 0;
  v60[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v60[0]) = 0;
  v7 = MdmLogCollector::ExpandEnvironmentVariable(a2);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
      (const char *)(unsigned int)v7,
      v52);
    std::wstring::_Tidy_deallocate(v60);
    AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v56);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v53);
    std::wstring::_Tidy_deallocate(v59);
    return v8;
  }
  if ( a1[28] == (void *)-1LL )
  {
    v15 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v60);
    DeleteFileW(v15);
  }
  else
  {
    LOBYTE(v57) = 0;
    BYTE2(v57) = 0;
    v54 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v54,
      0);
    UserSidFromToken = DmGetUserSidFromToken(a1[28], &v54);
    v11 = UserSidFromToken;
    if ( UserSidFromToken < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x139,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
        (const char *)(unsigned int)UserSidFromToken,
        v52);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v54);
      AutoImpersonate::~AutoImpersonate((AutoImpersonate *)&v57);
      std::wstring::_Tidy_deallocate(v60);
      AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v56);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v53);
      std::wstring::_Tidy_deallocate(v59);
      return v11;
    }
    if ( !v54 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v54);
      AutoImpersonate::~AutoImpersonate((AutoImpersonate *)&v57);
      std::wstring::_Tidy_deallocate(v60);
      AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v56);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v53);
      std::wstring::_Tidy_deallocate(v59);
      return 2147942487LL;
    }
    v12 = AutoImpersonate::ImpersonateSID((AutoImpersonate *)&v57, v54);
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x142,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
        (const char *)(unsigned int)v12,
        v52);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v54);
      AutoImpersonate::~AutoImpersonate((AutoImpersonate *)&v57);
      std::wstring::_Tidy_deallocate(v60);
      AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v56);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v53);
      std::wstring::_Tidy_deallocate(v59);
      return v13;
    }
    v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v60);
    DeleteFileW(v14);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v54);
    AutoImpersonate::~AutoImpersonate((AutoImpersonate *)&v57);
  }
  v57 = v59;
  v58 = 1;
  WorkingFolder = MdmLogCollector::GetWorkingFolder(L"MdmLogCollector_", v59, a1[28]);
  v17 = WorkingFolder;
  if ( WorkingFolder < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x150,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
      (const char *)(unsigned int)WorkingFolder,
      v52);
    v18 = (wil *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
    wil::RemoveDirectoryRecursiveNoThrow(v18, 0, (void *)0xFFFFFFFFFFFFFFFFLL);
    std::wstring::_Tidy_deallocate(v60);
    AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v56);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v53);
    std::wstring::_Tidy_deallocate(v59);
    return v17;
  }
  v19 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
  v20 = MdmLogCollector::CollectEntriesToFolder((MdmLogCollector *)a1, v19);
  v21 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x152,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
      (const char *)(unsigned int)v20,
      v52);
    v22 = (wil *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
    wil::RemoveDirectoryRecursiveNoThrow(v22, 0, (void *)0xFFFFFFFFFFFFFFFFLL);
    std::wstring::_Tidy_deallocate(v60);
    AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v56);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v53);
    std::wstring::_Tidy_deallocate(v59);
    return v21;
  }
  v55 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v55, 0);
  if ( a1[28] != (void *)-1LL && v55 != 10 )
  {
    v54 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v54,
      0);
    v23 = DmGetUserSidFromToken(a1[28], &v54);
    v24 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x160,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
        (const char *)(unsigned int)v23,
        v52);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v54);
      v25 = (wil *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
      wil::RemoveDirectoryRecursiveNoThrow(v25, 0, (void *)0xFFFFFFFFFFFFFFFFLL);
      std::wstring::_Tidy_deallocate(v60);
      AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v56);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v53);
      std::wstring::_Tidy_deallocate(v59);
      return v24;
    }
    if ( !v54 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v54);
      v26 = (wil *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
      wil::RemoveDirectoryRecursiveNoThrow(v26, 0, (void *)0xFFFFFFFFFFFFFFFFLL);
      std::wstring::_Tidy_deallocate(v60);
      AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v56);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v53);
      std::wstring::_Tidy_deallocate(v59);
      return 2147942487LL;
    }
    v27 = AutoImpersonate::ImpersonateSID((AutoImpersonate *)v56, v54);
    v28 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x169,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
        (const char *)(unsigned int)v27,
        v52);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v54);
      v29 = (wil *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
      wil::RemoveDirectoryRecursiveNoThrow(v29, 0, (void *)0xFFFFFFFFFFFFFFFFLL);
      std::wstring::_Tidy_deallocate(v60);
      AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v56);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v53);
      std::wstring::_Tidy_deallocate(v59);
      return v28;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v54);
  }
  v30 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v60);
  v31 = EnsureDirectoriesArePresent(v30);
  if ( v31 >= 0 )
  {
    if ( a3 )
    {
      if ( a3 != 1 )
      {
        v51 = (wil *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
        wil::RemoveDirectoryRecursiveNoThrow(v51, 0, (void *)0xFFFFFFFFFFFFFFFFLL);
        std::wstring::_Tidy_deallocate(v60);
        AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v56);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v53);
        std::wstring::_Tidy_deallocate(v59);
        return 2147942450LL;
      }
      v45 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
      v46 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v60);
      ZipFromDirectory = CreateZipFromDirectory(v46, v45);
      v48 = ZipFromDirectory;
      if ( ZipFromDirectory < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x181,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
          (const char *)(unsigned int)ZipFromDirectory,
          v52);
        v49 = (wil *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
        wil::RemoveDirectoryRecursiveNoThrow(v49, 0, (void *)0xFFFFFFFFFFFFFFFFLL);
        std::wstring::_Tidy_deallocate(v60);
        AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v56);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v53);
        std::wstring::_Tidy_deallocate(v59);
        return v48;
      }
    }
    else
    {
      v61[0] = 0;
      v61[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v61[0]) = 0;
      v35 = MdmLogCollector::GetWorkingFolder(L"MdmLogCollector_cab_", v61, -1);
      v36 = v35;
      if ( v35 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x179,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
          (const char *)(unsigned int)v35,
          v52);
        std::wstring::_Tidy_deallocate(v61);
        v37 = (wil *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
        wil::RemoveDirectoryRecursiveNoThrow(v37, 0, (void *)0xFFFFFFFFFFFFFFFFLL);
        std::wstring::_Tidy_deallocate(v60);
        AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v56);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v53);
        std::wstring::_Tidy_deallocate(v59);
        return v36;
      }
      v38 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v61);
      v39 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
      v40 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v60);
      Cab = Cab_CreateCab(v40, v39, v38, 0);
      v42 = Cab;
      if ( Cab < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x17B,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
          (const char *)(unsigned int)Cab,
          2);
        std::wstring::_Tidy_deallocate(v61);
        v43 = (wil *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
        wil::RemoveDirectoryRecursiveNoThrow(v43, 0, (void *)0xFFFFFFFFFFFFFFFFLL);
        std::wstring::_Tidy_deallocate(v60);
        AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v56);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v53);
        std::wstring::_Tidy_deallocate(v59);
        return v42;
      }
      v44 = (wil *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v61);
      wil::RemoveDirectoryRecursiveNoThrow(v44, 0, (void *)0xFFFFFFFFFFFFFFFFLL);
      std::wstring::_Tidy_deallocate(v61);
    }
    v50 = (wil *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
    wil::RemoveDirectoryRecursiveNoThrow(v50, 0, (void *)0xFFFFFFFFFFFFFFFFLL);
    std::wstring::_Tidy_deallocate(v60);
    AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v56);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v53);
    std::wstring::_Tidy_deallocate(v59);
    return 0;
  }
  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
  {
    v32 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v60);
    McTemplateU0zd_EventWriteTransfer(
      v33,
      EnterpriseDiagnosticsMdmDiagnosticsCreatingOrCheckingDirectoryFailure,
      v32,
      (unsigned int)v31);
  }
  v34 = (wil *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
  wil::RemoveDirectoryRecursiveNoThrow(v34, 0, (void *)0xFFFFFFFFFFFFFFFFLL);
  std::wstring::_Tidy_deallocate(v60);
  AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v56);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v53);
  std::wstring::_Tidy_deallocate(v59);
  return (unsigned int)v31;
}

```

## disassembly

```asm
0x18010cb20  mov     [rsp+arg_10], rbx
0x18010cb25  push    rsi
0x18010cb26  push    rdi
0x18010cb27  push    r15
0x18010cb29  sub     rsp, 0D0h
0x18010cb30  mov     rax, cs:__security_cookie
0x18010cb37  xor     rax, rsp
0x18010cb3a  mov     [rsp+0E8h+var_20], rax
0x18010cb42  mov     esi, r8d
0x18010cb45  mov     rdi, rdx
0x18010cb48  mov     rbx, rcx
0x18010cb4b  xorps   xmm0, xmm0
0x18010cb4e  movups  [rsp+0E8h+var_80], xmm0
0x18010cb53  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18010cb5b  movdqu  [rsp+0E8h+var_70], xmm1
0x18010cb61  xor     eax, eax
0x18010cb63  mov     word ptr [rsp+0E8h+var_80], ax
0x18010cb68  or      r15, 0FFFFFFFFFFFFFFFFh
0x18010cb6c  mov     [rsp+0E8h+var_B8], r15
0x18010cb71  mov     [rsp+0E8h+var_A0], al
0x18010cb75  mov     [rsp+0E8h+var_9E], al
0x18010cb79  call    cs:__imp_GetTickCount64
0x18010cb80  nop     dword ptr [rax+rax+00h]
0x18010cb85  mov     rcx, rax
0x18010cb88  call    cs:__imp__o_srand
0x18010cb8f  nop     dword ptr [rax+rax+00h]
0x18010cb94  xorps   xmm0, xmm0
0x18010cb97  movups  [rsp+0E8h+var_60], xmm0
0x18010cb9f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18010cba7  movdqu  [rsp+0E8h+var_50], xmm1
0x18010cbb0  xor     eax, eax
0x18010cbb2  mov     word ptr [rsp+0E8h+var_60], ax
0x18010cbba  lea     rdx, [rsp+0E8h+var_60]
0x18010cbc2  mov     rcx, rdi; lpSrc
0x18010cbc5  call    ?ExpandEnvironmentVariable@MdmLogCollector@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmLogCollector::ExpandEnvironmentVariable(ushort const *,std::wstring &)
0x18010cbca  mov     edi, eax
0x18010cbcc  test    eax, eax
0x18010cbce  jns     short loc_18010CC22
0x18010cbd0  mov     rcx, [rsp+0E8h]; this
0x18010cbd8  mov     r9d, eax; char *
0x18010cbdb  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010cbe2  mov     edx, 12Eh; void *
0x18010cbe7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010cbec  nop
0x18010cbed  lea     rcx, [rsp+0E8h+var_60]
0x18010cbf5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010cbfa  nop
0x18010cbfb  lea     rcx, [rsp+0E8h+var_A0]; this
0x18010cc00  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18010cc05  nop
0x18010cc06  lea     rcx, [rsp+0E8h+var_B8]
0x18010cc0b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18010cc10  nop
0x18010cc11  lea     rcx, [rsp+0E8h+var_80]
0x18010cc16  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010cc1b  mov     eax, edi
0x18010cc1d  jmp     loc_18010D464
0x18010cc22  cmp     [rbx+0E0h], r15
0x18010cc29  jz      loc_18010CDD8
0x18010cc2f  mov     byte ptr [rsp+0E8h+var_90], 0
0x18010cc34  mov     byte ptr [rsp+0E8h+var_90+2], 0
0x18010cc39  mov     [rsp+0E8h+var_B0], 0
0x18010cc42  xor     edx, edx
0x18010cc44  lea     rcx, [rsp+0E8h+var_B0]
0x18010cc49  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18010cc4e  lea     rdx, [rsp+0E8h+var_B0]
0x18010cc53  mov     rcx, [rbx+0E0h]
0x18010cc5a  call    cs:__imp_?DmGetUserSidFromToken@@YAJPEAXPEAPEAG@Z; DmGetUserSidFromToken(void *,ushort * *)
0x18010cc61  nop     dword ptr [rax+rax+00h]
0x18010cc66  mov     edi, eax
0x18010cc68  test    eax, eax
0x18010cc6a  jns     short loc_18010CCD4
0x18010cc6c  mov     rcx, [rsp+0E8h]; this
0x18010cc74  mov     r9d, eax; char *
0x18010cc77  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010cc7e  mov     edx, 139h; void *
0x18010cc83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010cc88  nop
0x18010cc89  lea     rcx, [rsp+0E8h+var_B0]
0x18010cc8e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010cc93  nop
0x18010cc94  lea     rcx, [rsp+0E8h+var_90]; this
0x18010cc99  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18010cc9e  nop
0x18010cc9f  lea     rcx, [rsp+0E8h+var_60]
0x18010cca7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010ccac  nop
0x18010ccad  lea     rcx, [rsp+0E8h+var_A0]; this
0x18010ccb2  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18010ccb7  nop
0x18010ccb8  lea     rcx, [rsp+0E8h+var_B8]
0x18010ccbd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18010ccc2  nop
0x18010ccc3  lea     rcx, [rsp+0E8h+var_80]
0x18010ccc8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010cccd  mov     eax, edi
0x18010cccf  jmp     loc_18010D464
0x18010ccd4  mov     rdx, [rsp+0E8h+var_B0]; unsigned __int16 *
0x18010ccd9  test    rdx, rdx
0x18010ccdc  jnz     short loc_18010CD2C
0x18010ccde  lea     rcx, [rsp+0E8h+var_B0]
0x18010cce3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010cce8  nop
0x18010cce9  lea     rcx, [rsp+0E8h+var_90]; this
0x18010ccee  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18010ccf3  nop
0x18010ccf4  lea     rcx, [rsp+0E8h+var_60]
0x18010ccfc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010cd01  nop
0x18010cd02  lea     rcx, [rsp+0E8h+var_A0]; this
0x18010cd07  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18010cd0c  nop
0x18010cd0d  lea     rcx, [rsp+0E8h+var_B8]
0x18010cd12  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18010cd17  nop
0x18010cd18  lea     rcx, [rsp+0E8h+var_80]
0x18010cd1d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010cd22  mov     eax, 80070057h
0x18010cd27  jmp     loc_18010D464
0x18010cd2c  lea     rcx, [rsp+0E8h+var_90]; this
0x18010cd31  call    ?ImpersonateSID@AutoImpersonate@@QEAAJPEBG@Z; AutoImpersonate::ImpersonateSID(ushort const *)
0x18010cd36  mov     edi, eax
0x18010cd38  test    eax, eax
0x18010cd3a  jns     short loc_18010CDA4
0x18010cd3c  mov     rcx, [rsp+0E8h]; this
0x18010cd44  mov     r9d, eax; char *
0x18010cd47  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010cd4e  mov     edx, 142h; void *
0x18010cd53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010cd58  nop
0x18010cd59  lea     rcx, [rsp+0E8h+var_B0]
0x18010cd5e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010cd63  nop
0x18010cd64  lea     rcx, [rsp+0E8h+var_90]; this
0x18010cd69  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18010cd6e  nop
0x18010cd6f  lea     rcx, [rsp+0E8h+var_60]
0x18010cd77  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010cd7c  nop
0x18010cd7d  lea     rcx, [rsp+0E8h+var_A0]; this
0x18010cd82  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18010cd87  nop
0x18010cd88  lea     rcx, [rsp+0E8h+var_B8]
0x18010cd8d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18010cd92  nop
0x18010cd93  lea     rcx, [rsp+0E8h+var_80]
0x18010cd98  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010cd9d  mov     eax, edi
0x18010cd9f  jmp     loc_18010D464
0x18010cda4  lea     rcx, [rsp+0E8h+var_60]
0x18010cdac  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010cdb1  mov     rcx, rax; lpFileName
0x18010cdb4  call    cs:__imp_DeleteFileW
0x18010cdbb  nop     dword ptr [rax+rax+00h]
0x18010cdc0  nop
0x18010cdc1  lea     rcx, [rsp+0E8h+var_B0]
0x18010cdc6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010cdcb  nop
0x18010cdcc  lea     rcx, [rsp+0E8h+var_90]; this
0x18010cdd1  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18010cdd6  jmp     short loc_18010CDF4
0x18010cdd8  lea     rcx, [rsp+0E8h+var_60]
0x18010cde0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010cde5  mov     rcx, rax; lpFileName
0x18010cde8  call    cs:__imp_DeleteFileW
0x18010cdef  nop     dword ptr [rax+rax+00h]
0x18010cdf4  lea     rax, [rsp+0E8h+var_80]
0x18010cdf9  mov     [rsp+0E8h+var_90], rax
0x18010cdfe  mov     [rsp+0E8h+var_88], 1
0x18010ce03  mov     r8, [rbx+0E0h]
0x18010ce0a  lea     rdx, [rsp+0E8h+var_80]
0x18010ce0f  lea     rcx, aMdmlogcollecto; "MdmLogCollector_"
0x18010ce16  call    ?GetWorkingFolder@MdmLogCollector@@CAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; MdmLogCollector::GetWorkingFolder(ushort const *,std::wstring &,void *)
0x18010ce1b  mov     edi, eax
0x18010ce1d  test    eax, eax
0x18010ce1f  jns     short loc_18010CE8B
0x18010ce21  mov     rcx, [rsp+0E8h]; this
0x18010ce29  mov     r9d, eax; char *
0x18010ce2c  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010ce33  mov     edx, 150h; void *
0x18010ce38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010ce3d  nop
0x18010ce3e  lea     rcx, [rsp+0E8h+var_80]
0x18010ce43  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010ce48  mov     r8, r15
0x18010ce4b  xor     edx, edx
0x18010ce4d  mov     rcx, rax
0x18010ce50  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x18010ce55  nop
0x18010ce56  lea     rcx, [rsp+0E8h+var_60]
0x18010ce5e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010ce63  nop
0x18010ce64  lea     rcx, [rsp+0E8h+var_A0]; this
0x18010ce69  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18010ce6e  nop
0x18010ce6f  lea     rcx, [rsp+0E8h+var_B8]
0x18010ce74  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18010ce79  nop
0x18010ce7a  lea     rcx, [rsp+0E8h+var_80]
0x18010ce7f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010ce84  mov     eax, edi
0x18010ce86  jmp     loc_18010D464
0x18010ce8b  lea     rcx, [rsp+0E8h+var_80]
0x18010ce90  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010ce95  mov     rdx, rax; lpPathName
0x18010ce98  mov     rcx, rbx; this
0x18010ce9b  call    ?CollectEntriesToFolder@MdmLogCollector@@AEAAJPEBG@Z; MdmLogCollector::CollectEntriesToFolder(ushort const *)
0x18010cea0  mov     edi, eax
0x18010cea2  test    eax, eax
0x18010cea4  jns     short loc_18010CF10
0x18010cea6  mov     rcx, [rsp+0E8h]; this
0x18010ceae  mov     r9d, eax; char *
0x18010ceb1  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010ceb8  mov     edx, 152h; void *
0x18010cebd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010cec2  nop
0x18010cec3  lea     rcx, [rsp+0E8h+var_80]
0x18010cec8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010cecd  mov     r8, r15
0x18010ced0  xor     edx, edx
0x18010ced2  mov     rcx, rax
0x18010ced5  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x18010ceda  nop
0x18010cedb  lea     rcx, [rsp+0E8h+var_60]
0x18010cee3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010cee8  nop
0x18010cee9  lea     rcx, [rsp+0E8h+var_A0]; this
0x18010ceee  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18010cef3  nop
0x18010cef4  lea     rcx, [rsp+0E8h+var_B8]
0x18010cef9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18010cefe  nop
0x18010ceff  lea     rcx, [rsp+0E8h+var_80]
0x18010cf04  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010cf09  mov     eax, edi
0x18010cf0b  jmp     loc_18010D464
0x18010cf10  mov     [rsp+0E8h+var_A8], 0
0x18010cf18  xor     r8d, r8d
0x18010cf1b  lea     rdx, [rsp+0E8h+var_A8]
0x18010cf20  xor     ecx, ecx
0x18010cf22  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18010cf29  nop     dword ptr [rax+rax+00h]
0x18010cf2e  cmp     [rbx+0E0h], r15
0x18010cf35  jz      loc_18010D0E2
0x18010cf3b  cmp     [rsp+0E8h+var_A8], 0Ah
0x18010cf40  jz      loc_18010D0E2
0x18010cf46  mov     [rsp+0E8h+var_B0], 0
0x18010cf4f  xor     edx, edx
0x18010cf51  lea     rcx, [rsp+0E8h+var_B0]
0x18010cf56  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18010cf5b  lea     rdx, [rsp+0E8h+var_B0]
0x18010cf60  mov     rcx, [rbx+0E0h]
0x18010cf67  call    cs:__imp_?DmGetUserSidFromToken@@YAJPEAXPEAPEAG@Z; DmGetUserSidFromToken(void *,ushort * *)
0x18010cf6e  nop     dword ptr [rax+rax+00h]
0x18010cf73  mov     ebx, eax
0x18010cf75  test    eax, eax
0x18010cf77  jns     short loc_18010CFEE
0x18010cf79  mov     rcx, [rsp+0E8h]; this
0x18010cf81  mov     r9d, eax; char *
0x18010cf84  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010cf8b  mov     edx, 160h; void *
0x18010cf90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010cf95  nop
0x18010cf96  lea     rcx, [rsp+0E8h+var_B0]
0x18010cf9b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010cfa0  nop
0x18010cfa1  lea     rcx, [rsp+0E8h+var_80]
0x18010cfa6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010cfab  mov     r8, r15
0x18010cfae  xor     edx, edx
0x18010cfb0  mov     rcx, rax
0x18010cfb3  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x18010cfb8  nop
0x18010cfb9  lea     rcx, [rsp+0E8h+var_60]
0x18010cfc1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010cfc6  nop
0x18010cfc7  lea     rcx, [rsp+0E8h+var_A0]; this
0x18010cfcc  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18010cfd1  nop
0x18010cfd2  lea     rcx, [rsp+0E8h+var_B8]
0x18010cfd7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18010cfdc  nop
0x18010cfdd  lea     rcx, [rsp+0E8h+var_80]
0x18010cfe2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010cfe7  mov     eax, ebx
0x18010cfe9  jmp     loc_18010D464
0x18010cfee  mov     rdx, [rsp+0E8h+var_B0]; unsigned __int16 *
0x18010cff3  test    rdx, rdx
0x18010cff6  jnz     short loc_18010D053
0x18010cff8  lea     rcx, [rsp+0E8h+var_B0]
0x18010cffd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010d002  nop
0x18010d003  lea     rcx, [rsp+0E8h+var_80]
0x18010d008  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010d00d  mov     r8, r15
0x18010d010  xor     edx, edx
0x18010d012  mov     rcx, rax
0x18010d015  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x18010d01a  nop
0x18010d01b  lea     rcx, [rsp+0E8h+var_60]
  ... truncated ...
```

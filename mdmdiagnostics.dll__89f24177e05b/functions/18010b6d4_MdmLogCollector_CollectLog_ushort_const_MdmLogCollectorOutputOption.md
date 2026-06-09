# MdmLogCollector::CollectLog(ushort const *,MdmLogCollectorOutputOption)

- ea: `0x18010b6d4`
- end: `0x18010c00d`
- name: `?CollectLog@MdmLogCollector@@QEAAJPEBGW4MdmLogCollectorOutputOption@@@Z`
- size: `2361`
- prototype: `__int64 __fastcall(void **, const WCHAR *, int)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f9bb4`

## callees

- `0x180019000`
- `0x1800ece5c`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800f9534`
- `0x1800f9558`
- `0x1800f9614`
- `0x180103ae0`
- `0x180103bc4`
- `0x18010440c`
- `0x18010450c`
- `0x18010a908`
- `0x18010b6d4`
- `0x18010e684`
- `0x18010fd74`
- `0x18012605c`
- `0x1801447ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x18010b736`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x18010b736`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18010bab8`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18010bab8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010b956`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010b984`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010b956`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010b984`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18010b72d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18010b72d`
- `DMCmnUtils!DmGetUserSidFromToken` at `0x18010b802`
- `DMCmnUtils!DmGetUserSidFromToken` at `0x18010baf7`
- `DMCmnUtils!DmGetUserSidFromToken` at `0x18010b802`
- `DMCmnUtils!DmGetUserSidFromToken` at `0x18010baf7`
- `CabAPI!Cab_CreateCab` at `0x18010bdfe`
- `CabAPI!Cab_CreateCab` at `0x18010bdfe`

## string_xrefs

- `0x18010b783`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010b819`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010b8e9`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010b9c2`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010ba47`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010bb0e`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010bbf8`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010bd53`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010be15`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010beee`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
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
  __int64 v18; // rax
  const WCHAR *v19; // rax
  int v20; // eax
  unsigned int v21; // edi
  __int64 v22; // rax
  int v23; // eax
  unsigned int v24; // ebx
  __int64 v25; // rax
  __int64 v26; // rax
  int v27; // eax
  unsigned int v28; // ebx
  __int64 v29; // rax
  const unsigned __int16 *v30; // rax
  int v31; // ebx
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  unsigned int v36; // ebx
  __int64 v37; // rax
  __int64 v38; // rdi
  __int64 v39; // rbx
  __int64 v40; // rax
  int Cab; // eax
  unsigned int v42; // ebx
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rbx
  __int64 v46; // rcx
  int ZipFromDirectory; // eax
  unsigned int v48; // ebx
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
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
      (void *)0x12F,
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
        (void *)0x13A,
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
        (void *)0x143,
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
      (void *)0x151,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
      (const char *)(unsigned int)WorkingFolder,
      v52);
    v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
    wil::RemoveDirectoryRecursiveNoThrow(v18, 0, -1);
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
      (void *)0x153,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
      (const char *)(unsigned int)v20,
      v52);
    v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
    wil::RemoveDirectoryRecursiveNoThrow(v22, 0, -1);
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
        (void *)0x161,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
        (const char *)(unsigned int)v23,
        v52);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v54);
      v25 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
      wil::RemoveDirectoryRecursiveNoThrow(v25, 0, -1);
      std::wstring::_Tidy_deallocate(v60);
      AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v56);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v53);
      std::wstring::_Tidy_deallocate(v59);
      return v24;
    }
    if ( !v54 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v54);
      v26 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
      wil::RemoveDirectoryRecursiveNoThrow(v26, 0, -1);
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
        (void *)0x16A,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
        (const char *)(unsigned int)v27,
        v52);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v54);
      v29 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
      wil::RemoveDirectoryRecursiveNoThrow(v29, 0, -1);
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
        v51 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
        wil::RemoveDirectoryRecursiveNoThrow(v51, 0, -1);
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
          (void *)0x182,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
          (const char *)(unsigned int)ZipFromDirectory,
          v52);
        v49 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
        wil::RemoveDirectoryRecursiveNoThrow(v49, 0, -1);
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
          (void *)0x17A,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
          (const char *)(unsigned int)v35,
          v52);
        std::wstring::_Tidy_deallocate(v61);
        v37 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
        wil::RemoveDirectoryRecursiveNoThrow(v37, 0, -1);
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
          (void *)0x17C,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
          (const char *)(unsigned int)Cab,
          2);
        std::wstring::_Tidy_deallocate(v61);
        v43 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
        wil::RemoveDirectoryRecursiveNoThrow(v43, 0, -1);
        std::wstring::_Tidy_deallocate(v60);
        AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v56);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v53);
        std::wstring::_Tidy_deallocate(v59);
        return v42;
      }
      v44 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v61);
      wil::RemoveDirectoryRecursiveNoThrow(v44, 0, -1);
      std::wstring::_Tidy_deallocate(v61);
    }
    v50 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
    wil::RemoveDirectoryRecursiveNoThrow(v50, 0, -1);
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
  v34 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
  wil::RemoveDirectoryRecursiveNoThrow(v34, 0, -1);
  std::wstring::_Tidy_deallocate(v60);
  AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v56);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v53);
  std::wstring::_Tidy_deallocate(v59);
  return (unsigned int)v31;
}

```

## disassembly

```asm
0x18010b6d4  mov     [rsp+arg_10], rbx
0x18010b6d9  push    rsi
0x18010b6da  push    rdi
0x18010b6db  push    r15
0x18010b6dd  sub     rsp, 0D0h
0x18010b6e4  mov     rax, cs:__security_cookie
0x18010b6eb  xor     rax, rsp
0x18010b6ee  mov     [rsp+0E8h+var_20], rax
0x18010b6f6  mov     esi, r8d
0x18010b6f9  mov     rdi, rdx
0x18010b6fc  mov     rbx, rcx
0x18010b6ff  xorps   xmm0, xmm0
0x18010b702  movups  [rsp+0E8h+var_80], xmm0
0x18010b707  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18010b70f  movdqu  [rsp+0E8h+var_70], xmm1
0x18010b715  xor     eax, eax
0x18010b717  mov     word ptr [rsp+0E8h+var_80], ax
0x18010b71c  or      r15, 0FFFFFFFFFFFFFFFFh
0x18010b720  mov     [rsp+0E8h+var_B8], r15
0x18010b725  mov     [rsp+0E8h+var_A0], al
0x18010b729  mov     [rsp+0E8h+var_9E], al
0x18010b72d  call    cs:__imp_GetTickCount64
0x18010b733  mov     rcx, rax
0x18010b736  call    cs:__imp__o_srand
0x18010b73c  xorps   xmm0, xmm0
0x18010b73f  movups  [rsp+0E8h+var_60], xmm0
0x18010b747  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18010b74f  movdqu  [rsp+0E8h+var_50], xmm1
0x18010b758  xor     eax, eax
0x18010b75a  mov     word ptr [rsp+0E8h+var_60], ax
0x18010b762  lea     rdx, [rsp+0E8h+var_60]
0x18010b76a  mov     rcx, rdi; lpSrc
0x18010b76d  call    ?ExpandEnvironmentVariable@MdmLogCollector@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmLogCollector::ExpandEnvironmentVariable(ushort const *,std::wstring &)
0x18010b772  mov     edi, eax
0x18010b774  test    eax, eax
0x18010b776  jns     short loc_18010B7CA
0x18010b778  mov     rcx, [rsp+0E8h]; this
0x18010b780  mov     r9d, eax; char *
0x18010b783  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010b78a  mov     edx, 12Fh; void *
0x18010b78f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010b794  nop
0x18010b795  lea     rcx, [rsp+0E8h+var_60]
0x18010b79d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010b7a2  nop
0x18010b7a3  lea     rcx, [rsp+0E8h+var_A0]; this
0x18010b7a8  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18010b7ad  nop
0x18010b7ae  lea     rcx, [rsp+0E8h+var_B8]
0x18010b7b3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18010b7b8  nop
0x18010b7b9  lea     rcx, [rsp+0E8h+var_80]
0x18010b7be  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010b7c3  mov     eax, edi
0x18010b7c5  jmp     loc_18010BFE8
0x18010b7ca  cmp     [rbx+0E0h], r15
0x18010b7d1  jz      loc_18010B974
0x18010b7d7  mov     byte ptr [rsp+0E8h+var_90], 0
0x18010b7dc  mov     byte ptr [rsp+0E8h+var_90+2], 0
0x18010b7e1  mov     [rsp+0E8h+var_B0], 0
0x18010b7ea  xor     edx, edx
0x18010b7ec  lea     rcx, [rsp+0E8h+var_B0]
0x18010b7f1  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18010b7f6  lea     rdx, [rsp+0E8h+var_B0]
0x18010b7fb  mov     rcx, [rbx+0E0h]
0x18010b802  call    cs:__imp_?DmGetUserSidFromToken@@YAJPEAXPEAPEAG@Z; DmGetUserSidFromToken(void *,ushort * *)
0x18010b808  mov     edi, eax
0x18010b80a  test    eax, eax
0x18010b80c  jns     short loc_18010B876
0x18010b80e  mov     rcx, [rsp+0E8h]; this
0x18010b816  mov     r9d, eax; char *
0x18010b819  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010b820  mov     edx, 13Ah; void *
0x18010b825  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010b82a  nop
0x18010b82b  lea     rcx, [rsp+0E8h+var_B0]
0x18010b830  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010b835  nop
0x18010b836  lea     rcx, [rsp+0E8h+var_90]; this
0x18010b83b  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18010b840  nop
0x18010b841  lea     rcx, [rsp+0E8h+var_60]
0x18010b849  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010b84e  nop
0x18010b84f  lea     rcx, [rsp+0E8h+var_A0]; this
0x18010b854  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18010b859  nop
0x18010b85a  lea     rcx, [rsp+0E8h+var_B8]
0x18010b85f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18010b864  nop
0x18010b865  lea     rcx, [rsp+0E8h+var_80]
0x18010b86a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010b86f  mov     eax, edi
0x18010b871  jmp     loc_18010BFE8
0x18010b876  mov     rdx, [rsp+0E8h+var_B0]; unsigned __int16 *
0x18010b87b  test    rdx, rdx
0x18010b87e  jnz     short loc_18010B8CE
0x18010b880  lea     rcx, [rsp+0E8h+var_B0]
0x18010b885  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010b88a  nop
0x18010b88b  lea     rcx, [rsp+0E8h+var_90]; this
0x18010b890  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18010b895  nop
0x18010b896  lea     rcx, [rsp+0E8h+var_60]
0x18010b89e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010b8a3  nop
0x18010b8a4  lea     rcx, [rsp+0E8h+var_A0]; this
0x18010b8a9  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18010b8ae  nop
0x18010b8af  lea     rcx, [rsp+0E8h+var_B8]
0x18010b8b4  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18010b8b9  nop
0x18010b8ba  lea     rcx, [rsp+0E8h+var_80]
0x18010b8bf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010b8c4  mov     eax, 80070057h
0x18010b8c9  jmp     loc_18010BFE8
0x18010b8ce  lea     rcx, [rsp+0E8h+var_90]; this
0x18010b8d3  call    ?ImpersonateSID@AutoImpersonate@@QEAAJPEBG@Z; AutoImpersonate::ImpersonateSID(ushort const *)
0x18010b8d8  mov     edi, eax
0x18010b8da  test    eax, eax
0x18010b8dc  jns     short loc_18010B946
0x18010b8de  mov     rcx, [rsp+0E8h]; this
0x18010b8e6  mov     r9d, eax; char *
0x18010b8e9  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010b8f0  mov     edx, 143h; void *
0x18010b8f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010b8fa  nop
0x18010b8fb  lea     rcx, [rsp+0E8h+var_B0]
0x18010b900  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010b905  nop
0x18010b906  lea     rcx, [rsp+0E8h+var_90]; this
0x18010b90b  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18010b910  nop
0x18010b911  lea     rcx, [rsp+0E8h+var_60]
0x18010b919  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010b91e  nop
0x18010b91f  lea     rcx, [rsp+0E8h+var_A0]; this
0x18010b924  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18010b929  nop
0x18010b92a  lea     rcx, [rsp+0E8h+var_B8]
0x18010b92f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18010b934  nop
0x18010b935  lea     rcx, [rsp+0E8h+var_80]
0x18010b93a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010b93f  mov     eax, edi
0x18010b941  jmp     loc_18010BFE8
0x18010b946  lea     rcx, [rsp+0E8h+var_60]
0x18010b94e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010b953  mov     rcx, rax; lpFileName
0x18010b956  call    cs:__imp_DeleteFileW
0x18010b95c  nop
0x18010b95d  lea     rcx, [rsp+0E8h+var_B0]
0x18010b962  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010b967  nop
0x18010b968  lea     rcx, [rsp+0E8h+var_90]; this
0x18010b96d  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18010b972  jmp     short loc_18010B98A
0x18010b974  lea     rcx, [rsp+0E8h+var_60]
0x18010b97c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010b981  mov     rcx, rax; lpFileName
0x18010b984  call    cs:__imp_DeleteFileW
0x18010b98a  lea     rax, [rsp+0E8h+var_80]
0x18010b98f  mov     [rsp+0E8h+var_90], rax
0x18010b994  mov     [rsp+0E8h+var_88], 1
0x18010b999  mov     r8, [rbx+0E0h]
0x18010b9a0  lea     rdx, [rsp+0E8h+var_80]
0x18010b9a5  lea     rcx, aMdmlogcollecto; "MdmLogCollector_"
0x18010b9ac  call    ?GetWorkingFolder@MdmLogCollector@@CAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; MdmLogCollector::GetWorkingFolder(ushort const *,std::wstring &,void *)
0x18010b9b1  mov     edi, eax
0x18010b9b3  test    eax, eax
0x18010b9b5  jns     short loc_18010BA21
0x18010b9b7  mov     rcx, [rsp+0E8h]; this
0x18010b9bf  mov     r9d, eax; char *
0x18010b9c2  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010b9c9  mov     edx, 151h; void *
0x18010b9ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010b9d3  nop
0x18010b9d4  lea     rcx, [rsp+0E8h+var_80]
0x18010b9d9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010b9de  mov     r8, r15
0x18010b9e1  xor     edx, edx
0x18010b9e3  mov     rcx, rax
0x18010b9e6  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x18010b9eb  nop
0x18010b9ec  lea     rcx, [rsp+0E8h+var_60]
0x18010b9f4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010b9f9  nop
0x18010b9fa  lea     rcx, [rsp+0E8h+var_A0]; this
0x18010b9ff  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18010ba04  nop
0x18010ba05  lea     rcx, [rsp+0E8h+var_B8]
0x18010ba0a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18010ba0f  nop
0x18010ba10  lea     rcx, [rsp+0E8h+var_80]
0x18010ba15  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010ba1a  mov     eax, edi
0x18010ba1c  jmp     loc_18010BFE8
0x18010ba21  lea     rcx, [rsp+0E8h+var_80]
0x18010ba26  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010ba2b  mov     rdx, rax; lpPathName
0x18010ba2e  mov     rcx, rbx; this
0x18010ba31  call    ?CollectEntriesToFolder@MdmLogCollector@@AEAAJPEBG@Z; MdmLogCollector::CollectEntriesToFolder(ushort const *)
0x18010ba36  mov     edi, eax
0x18010ba38  test    eax, eax
0x18010ba3a  jns     short loc_18010BAA6
0x18010ba3c  mov     rcx, [rsp+0E8h]; this
0x18010ba44  mov     r9d, eax; char *
0x18010ba47  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010ba4e  mov     edx, 153h; void *
0x18010ba53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010ba58  nop
0x18010ba59  lea     rcx, [rsp+0E8h+var_80]
0x18010ba5e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010ba63  mov     r8, r15
0x18010ba66  xor     edx, edx
0x18010ba68  mov     rcx, rax
0x18010ba6b  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x18010ba70  nop
0x18010ba71  lea     rcx, [rsp+0E8h+var_60]
0x18010ba79  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010ba7e  nop
0x18010ba7f  lea     rcx, [rsp+0E8h+var_A0]; this
0x18010ba84  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18010ba89  nop
0x18010ba8a  lea     rcx, [rsp+0E8h+var_B8]
0x18010ba8f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18010ba94  nop
0x18010ba95  lea     rcx, [rsp+0E8h+var_80]
0x18010ba9a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010ba9f  mov     eax, edi
0x18010baa1  jmp     loc_18010BFE8
0x18010baa6  mov     [rsp+0E8h+var_A8], 0
0x18010baae  xor     r8d, r8d
0x18010bab1  lea     rdx, [rsp+0E8h+var_A8]
0x18010bab6  xor     ecx, ecx
0x18010bab8  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18010babe  cmp     [rbx+0E0h], r15
0x18010bac5  jz      loc_18010BC6C
0x18010bacb  cmp     [rsp+0E8h+var_A8], 0Ah
0x18010bad0  jz      loc_18010BC6C
0x18010bad6  mov     [rsp+0E8h+var_B0], 0
0x18010badf  xor     edx, edx
0x18010bae1  lea     rcx, [rsp+0E8h+var_B0]
0x18010bae6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18010baeb  lea     rdx, [rsp+0E8h+var_B0]
0x18010baf0  mov     rcx, [rbx+0E0h]
0x18010baf7  call    cs:__imp_?DmGetUserSidFromToken@@YAJPEAXPEAPEAG@Z; DmGetUserSidFromToken(void *,ushort * *)
0x18010bafd  mov     ebx, eax
0x18010baff  test    eax, eax
0x18010bb01  jns     short loc_18010BB78
0x18010bb03  mov     rcx, [rsp+0E8h]; this
0x18010bb0b  mov     r9d, eax; char *
0x18010bb0e  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010bb15  mov     edx, 161h; void *
0x18010bb1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010bb1f  nop
0x18010bb20  lea     rcx, [rsp+0E8h+var_B0]
0x18010bb25  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010bb2a  nop
0x18010bb2b  lea     rcx, [rsp+0E8h+var_80]
0x18010bb30  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010bb35  mov     r8, r15
0x18010bb38  xor     edx, edx
0x18010bb3a  mov     rcx, rax
0x18010bb3d  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x18010bb42  nop
0x18010bb43  lea     rcx, [rsp+0E8h+var_60]
0x18010bb4b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010bb50  nop
0x18010bb51  lea     rcx, [rsp+0E8h+var_A0]; this
0x18010bb56  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18010bb5b  nop
0x18010bb5c  lea     rcx, [rsp+0E8h+var_B8]
0x18010bb61  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18010bb66  nop
0x18010bb67  lea     rcx, [rsp+0E8h+var_80]
0x18010bb6c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010bb71  mov     eax, ebx
0x18010bb73  jmp     loc_18010BFE8
0x18010bb78  mov     rdx, [rsp+0E8h+var_B0]; unsigned __int16 *
0x18010bb7d  test    rdx, rdx
0x18010bb80  jnz     short loc_18010BBDD
0x18010bb82  lea     rcx, [rsp+0E8h+var_B0]
0x18010bb87  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010bb8c  nop
0x18010bb8d  lea     rcx, [rsp+0E8h+var_80]
0x18010bb92  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010bb97  mov     r8, r15
0x18010bb9a  xor     edx, edx
0x18010bb9c  mov     rcx, rax
0x18010bb9f  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x18010bba4  nop
0x18010bba5  lea     rcx, [rsp+0E8h+var_60]
0x18010bbad  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010bbb2  nop
0x18010bbb3  lea     rcx, [rsp+0E8h+var_A0]; this
0x18010bbb8  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18010bbbd  nop
0x18010bbbe  lea     rcx, [rsp+0E8h+var_B8]
0x18010bbc3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
  ... truncated ...
```

# CreateDirectoryJunction(ushort const *,ushort const *,ushort const *,CAACLApplicator const &,int,_GUID const &)

- ea: `0x18000ad78`
- end: `0x18000b7d9`
- name: `?CreateDirectoryJunction@@YAJPEBG00AEBVCAACLApplicator@@HAEBU_GUID@@@Z`
- size: `2657`
- prototype: `__int64 __fastcall(char *, const unsigned __int16 *, const unsigned __int16 *, const struct CAACLApplicator *, int, struct _GUID *rfid)`
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000ab70`
- `0x18000feb0`

## callees

- `0x180001854`
- `0x180004030`
- `0x1800044e0`
- `0x180004594`
- `0x180006400`
- `0x18000aacc`
- `0x18000ad78`
- `0x18000c6c0`
- `0x18000c7d4`
- `0x18000c95c`
- `0x18000f114`
- `0x18000f71c`
- `0x18000f864`
- `0x180010d5c`
- `0x180011118`
- `0x1800227f2`
- `0x1800227fe`
- `0x180022830`
- `0x180024010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000b0f8`
- `msvcrt!_wcsnicmp` at `0x18000b0f8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000b741`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000b782`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000b741`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000b782`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000adc2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000adc2`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000b0ac`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000b0ac`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b07c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b402`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b07c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b402`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000b6e9`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000b6e9`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000b1b5`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000b1b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000add5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000add5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aedf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aedf`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18000b124`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18000b124`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000b600`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000b600`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18000afe6`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18000b16e`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18000afe6`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18000b16e`

## string_xrefs

- `0x18000ae06`: `onecore\ds\security\gina\profile\profext\DirJuncHelper.h`
- `0x18000af22`: `onecore\ds\security\gina\profile\profext\DirJuncHelper.h`
- `0x18000af9b`: `onecore\ds\security\gina\profile\profext\DirJuncHelper.h`
- `0x18000b002`: `onecore\ds\security\gina\profile\profext\DirJuncHelper.h`
- `0x18000b244`: `onecore\ds\security\gina\profile\profext\DirJuncHelper.h`
- `0x18000b29a`: `onecore\ds\security\gina\profile\profext\DirJuncHelper.h`
- `0x18000b331`: `onecore\ds\security\gina\profile\profext\DirJuncHelper.h`
- `0x18000b389`: `onecore\ds\security\gina\profile\profext\DirJuncHelper.h`
- `0x18000b422`: `onecore\ds\security\gina\profile\profext\DirJuncHelper.h`
- `0x18000b4b0`: `onecore\ds\security\gina\profile\profext\DirJuncHelper.h`
- `0x18000b53e`: `onecore\ds\security\gina\profile\profext\DirJuncHelper.h`
- `0x18000b617`: `onecore\ds\security\gina\profile\profext\DirJuncHelper.h`
- `0x18000b68d`: `onecore\ds\security\gina\profile\profext\DirJuncHelper.h`
- `0x18000b700`: `onecore\ds\security\gina\profile\profext\DirJuncHelper.h`
- `0x18000b7a1`: `onecore\ds\security\gina\profile\profext\DirJuncHelper.h`
- `0x18000af8c`: `Path %ws, size %u.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CreateDirectoryJunction(
        char *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct CAACLApplicator *a4,
        int a5,
        struct _GUID *rfid)
{
  const unsigned __int16 *v6; // r15
  DWORD FileAttributesW; // eax
  signed int LastError; // eax
  struct _SECURITY_ATTRIBUTES *v11; // rdx
  unsigned int v12; // ecx
  int NestedDirectory; // ebx
  __int64 v14; // rdx
  HANDLE *v16; // rax
  HANDLE *v17; // rsi
  __int64 v18; // r14
  __int64 v19; // r15
  unsigned __int64 v20; // r15
  HLOCAL v21; // rax
  WCHAR *v22; // rbx
  unsigned int LastErrorFailHr; // edi
  HANDLE *v24; // rbx
  HANDLE *v25; // rbx
  HRESULT v26; // eax
  HANDLE *v27; // rbx
  HANDLE FileW; // rax
  const char *v29; // r9
  void *v30; // rdi
  const char *v31; // r9
  int v32; // eax
  WCHAR *p_szFilePath; // rcx
  const char *v34; // r9
  DWORD v35; // ecx
  HRESULT v36; // eax
  wil::details *v37; // rcx
  HANDLE *v38; // rbx
  HANDLE *v39; // rbx
  HANDLE *v40; // rbx
  HANDLE *v41; // rbx
  HANDLE *v42; // rbx
  HANDLE *v43; // rbx
  HANDLE *v44; // rbx
  WCHAR *v45; // rbx
  const char *v46; // r9
  HANDLE *v47; // rbx
  int v48; // eax
  HANDLE *v49; // rbx
  __int64 v50; // rax
  int v51; // eax
  __int16 v52; // r10
  __int64 v53; // r11
  HANDLE *v54; // rbx
  const char *v55; // r9
  HANDLE *v56; // rbx
  int v57; // eax
  HANDLE *v58; // rbx
  const char *v59; // r9
  HANDLE *v60; // rbx
  HANDLE *v61; // rbx
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositionc; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  PWSTR pszPath; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v68; // [rsp+48h] [rbp-B8h] BYREF
  DWORD BytesReturned; // [rsp+50h] [rbp-B0h] BYREF
  __int64 FileInformation; // [rsp+58h] [rbp-A8h] BYREF
  const unsigned __int16 *v71; // [rsp+60h] [rbp-A0h]
  const struct CAACLApplicator *v72; // [rsp+68h] [rbp-98h]
  HANDLE *v73; // [rsp+70h] [rbp-90h]
  __int64 v74; // [rsp+78h] [rbp-88h]
  __int128 InBuffer; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v76[528]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR szFilePath; // [rsp+4B0h] [rbp+3B0h] BYREF
  wchar_t String1; // [rsp+4B8h] [rbp+3B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+718h] [rbp+618h]

  v72 = a4;
  v6 = a3;
  v71 = a3;
  FileAttributesW = GetFileAttributesW(a2);
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( !a5 || (unsigned int)(LastError - 2) > 1 )
    {
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
      return v12;
    }
    NestedDirectory = CreateNestedDirectory(a2, v11);
    if ( NestedDirectory < 0 )
    {
      v14 = 295;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\DirJuncHelper.h",
        (const char *)(unsigned int)NestedDirectory,
        dwCreationDisposition);
      return (unsigned int)NestedDirectory;
    }
  }
  else if ( (FileAttributesW & 0x10) == 0 )
  {
    NestedDirectory = -2147024816;
    v14 = 299;
    goto LABEL_6;
  }
  v16 = (HANDLE *)operator new[](0xA0u);
  v17 = v16;
  if ( v16 )
    memset_0(v16, 0, 0xA0u);
  else
    v17 = 0;
  v73 = v17;
  v74 = 20;
  if ( !v17 )
  {
    LastErrorFailHr = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\DirJuncHelper.h",
      (const char *)0x8007000ELL,
      dwCreationDisposition);
    return LastErrorFailHr;
  }
  v18 = -1;
  if ( *(_QWORD *)&rfid->Data1 == *(_QWORD *)&FOLDERID_UserProfiles.Data1
    && *(_QWORD *)rfid->Data4 == *(_QWORD *)FOLDERID_UserProfiles.Data4
    || *(_QWORD *)&rfid->Data1 == *(_QWORD *)&FOLDERID_ProgramData.Data1
    && *(_QWORD *)rfid->Data4 == *(_QWORD *)FOLDERID_ProgramData.Data4 )
  {
    pszPath = 0;
    v19 = -1;
    do
      ++v19;
    while ( *(_WORD *)&a1[2 * v19] );
    v20 = v19 + 1;
    v21 = LocalAlloc(0, 2 * v20);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &pszPath,
      v21);
    v22 = pszPath;
    if ( pszPath )
    {
      LastErrorFailHr = StringCchCopyW(pszPath, v20, (const unsigned __int16 *)a1);
      if ( (LastErrorFailHr & 0x80000000) == 0 )
      {
        v26 = PathCchRemoveFileSpec(v22, v20);
        LastErrorFailHr = v26;
        if ( v26 >= 0 )
        {
          BytesReturned = 0;
          while ( 1 )
          {
            if ( !(unsigned int)IsPathUnderKnownFolder(v22, rfid) )
            {
              wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&pszPath);
              v6 = v71;
              goto LABEL_49;
            }
            FileW = CreateFileW(v22, 0x80000000, 1u, 0, 3u, 0x2200000u, 0);
            v30 = FileW;
            v68 = (__int64)FileW;
            if ( FileW == (HANDLE)-1LL )
              break;
            if ( GetFinalPathNameByHandleW(FileW, &szFilePath, 0x104u, 0) - 1 > 0x103 )
            {
              LastErrorFailHr = wil::details::in1diag3::Return_GetLastError(
                                  retaddr,
                                  (void *)0x14C,
                                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\DirJuncHelper.h",
                                  v31);
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v68);
              wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&pszPath);
              v43 = v17;
              do
                wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*v43++);
              while ( v43 != v17 + 20 );
              goto LABEL_97;
            }
            v32 = wcsncmp_0(&szFilePath, L"\\\\?\\", 4u);
            p_szFilePath = &szFilePath;
            if ( !v32 )
              p_szFilePath = &String1;
            if ( _wcsnicmp(p_szFilePath, v22, v20) )
            {
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v68);
              wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&pszPath);
              v42 = v17;
              do
                wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*v42++);
              while ( v42 != v17 + 20 );
              goto LABEL_64;
            }
            FileInformation = 0;
            if ( !GetFileInformationByHandleEx(v30, FileAttributeTagInfo, &FileInformation, 8u) )
            {
              LastErrorFailHr = wil::details::in1diag3::Return_GetLastError(
                                  retaddr,
                                  (void *)0x15B,
                                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\DirJuncHelper.h",
                                  v34);
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v68);
              wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&pszPath);
              v41 = v17;
              do
                wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*v41++);
              while ( v41 != v17 + 20 );
              goto LABEL_97;
            }
            if ( (FileInformation & 0x400) != 0 && (FileInformation & 0xA000000F00000000uLL) != 0 )
            {
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v68);
              wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&pszPath);
              v39 = v17;
              do
                wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*v39++);
              while ( v39 != v17 + 20 );
LABEL_64:
              LastErrorFailHr = -2147023504;
              goto LABEL_97;
            }
            v35 = BytesReturned;
            if ( BytesReturned < 0x14 )
            {
              v68 = -1;
              v17[BytesReturned] = v30;
              BytesReturned = v35 + 1;
            }
            v36 = PathCchRemoveFileSpec(v22, v20);
            LastErrorFailHr = v36;
            if ( v36 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x16A,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\DirJuncHelper.h",
                (const char *)(unsigned int)v36,
                dwCreationDispositiona);
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v68);
              wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&pszPath);
              v40 = v17;
              do
                wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*v40++);
              while ( v40 != v17 + 20 );
              goto LABEL_97;
            }
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v68);
          }
          LastErrorFailHr = wil::details::in1diag3::Return_GetLastError(
                              retaddr,
                              (void *)0x147,
                              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\DirJuncHelper.h",
                              v29);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v68);
          wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&pszPath);
          v44 = v17;
          do
            wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*v44++);
          while ( v44 != v17 + 20 );
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x13E,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\DirJuncHelper.h",
            (const char *)(unsigned int)v26,
            dwCreationDisposition);
          wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&pszPath);
          v27 = v17;
          do
            wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*v27++);
          while ( v27 != v17 + 20 );
        }
      }
      else
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x13B,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\DirJuncHelper.h",
          (const char *)LastErrorFailHr,
          (int)"Path %ws, size %u.",
          a1,
          v20);
        wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&pszPath);
        v25 = v17;
        do
          wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*v25++);
        while ( v25 != v17 + 20 );
      }
    }
    else
    {
      LODWORD(dwFlagsAndAttributes) = v20;
      LastErrorFailHr = -2147024882;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x139,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\DirJuncHelper.h",
        (const char *)0x8007000ELL,
        (int)"Size %u.",
        dwFlagsAndAttributes);
      wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&pszPath);
      v24 = v17;
      do
        wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*v24++);
      while ( v24 != v17 + 20 );
    }
    goto LABEL_97;
  }
LABEL_49:
  if ( !CreateDirectoryW((LPCWSTR)a1, 0) )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v37);
    v38 = v17;
    do
      wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*v38++);
    while ( v38 != v17 + 20 );
LABEL_97:
    operator delete[](v17);
    return LastErrorFailHr;
  }
  v68 = (__int64)a1;
  v45 = (WCHAR *)CreateFileW((LPCWSTR)a1, 0x40040000u, 0, 0, 3u, 0x2200000u, 0);
  pszPath = v45;
  if ( v45 == (WCHAR *)-1LL )
  {
    LastErrorFailHr = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x17E,
                        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\DirJuncHelper.h",
                        v46);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&pszPath);
    CDirectoryRemover::~CDirectoryRemover((CDirectoryRemover *)&v68);
    v47 = v17;
    do
      wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*v47++);
    while ( v47 != v17 + 20 );
    goto LABEL_97;
  }
  InBuffer = 0;
  *(_QWORD *)v76 = 0;
  LODWORD(InBuffer) = -1610612733;
  v48 = StringCchPrintfW(v76, 0x104u, L"\\??\\%s", v6);
  LastErrorFailHr = v48;
  if ( v48 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x187,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\DirJuncHelper.h",
      (const char *)(unsigned int)v48,
      dwCreationDispositionb);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&pszPath);
    CDirectoryRemover::~CDirectoryRemover((CDirectoryRemover *)&v68);
    v49 = v17;
    do
      wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*v49++);
    while ( v49 != v17 + 20 );
    goto LABEL_97;
  }
  v50 = -1;
  do
    ++v50;
  while ( v76[v50] );
  v51 = StringCchCopyW(&v76[(unsigned __int16)v50 + 1], 0x104u, v6);
  LastErrorFailHr = v51;
  if ( v51 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\DirJuncHelper.h",
      (const char *)(unsigned int)v51,
      dwCreationDispositionb);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&pszPath);
    CDirectoryRemover::~CDirectoryRemover((CDirectoryRemover *)&v68);
    v54 = v17;
    do
      wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*v54++);
    while ( v54 != v17 + 20 );
    goto LABEL_97;
  }
  do
    ++v18;
  while ( *(_WORD *)(v53 + 2 * v18) );
  WORD4(InBuffer) = 0;
  WORD5(InBuffer) = 2 * v52;
  WORD6(InBuffer) = 2 * v52 + 2;
  HIWORD(InBuffer) = 2 * v18;
  WORD2(InBuffer) = 2 * (v18 + v52 + 6);
  BytesReturned = 0;
  if ( !DeviceIoControl(v45, 0x900A4u, &InBuffer, WORD2(InBuffer) + 8, 0, 0, &BytesReturned, 0) )
  {
    LastErrorFailHr = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x1A5,
                        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\DirJuncHelper.h",
                        v55);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&pszPath);
    CDirectoryRemover::~CDirectoryRemover((CDirectoryRemover *)&v68);
    v56 = v17;
    do
      wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*v56++);
    while ( v56 != v17 + 20 );
    goto LABEL_97;
  }
  v57 = (*(__int64 (__fastcall **)(const struct CAACLApplicator *, WCHAR *))(*(_QWORD *)v72 + 8LL))(v72, v45);
  LastErrorFailHr = v57;
  if ( v57 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A7,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\DirJuncHelper.h",
      (const char *)(unsigned int)v57,
      dwCreationDispositionc);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&pszPath);
    CDirectoryRemover::~CDirectoryRemover((CDirectoryRemover *)&v68);
    v58 = v17;
    do
      wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*v58++);
    while ( v58 != v17 + 20 );
    goto LABEL_97;
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&pszPath);
  if ( !SetFileAttributesW((LPCWSTR)a1, 0x2006u) )
  {
    LastErrorFailHr = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x1AF,
                        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\DirJuncHelper.h",
                        v59);
    CDirectoryRemover::~CDirectoryRemover((CDirectoryRemover *)&v68);
    v60 = v17;
    do
      wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*v60++);
    while ( v60 != v17 + 20 );
    goto LABEL_97;
  }
  v68 = 0;
  CDirectoryRemover::~CDirectoryRemover((CDirectoryRemover *)&v68);
  v61 = v17;
  do
    wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*v61++);
  while ( v61 != v17 + 20 );
  operator delete[](v17);
  return 0;
}

```

## disassembly

```asm
0x18000ad78  push    rbp
0x18000ad7a  push    rbx
0x18000ad7b  push    rsi
0x18000ad7c  push    rdi
0x18000ad7d  push    r12
0x18000ad7f  push    r13
0x18000ad81  push    r14
0x18000ad83  push    r15
0x18000ad85  lea     rbp, [rsp-5D8h]
0x18000ad8d  sub     rsp, 6D8h
0x18000ad94  mov     rax, cs:__security_cookie
0x18000ad9b  xor     rax, rsp
0x18000ad9e  mov     [rbp+610h+var_50], rax
0x18000ada5  mov     [rsp+710h+var_6A8], r9
0x18000adaa  mov     r15, r8
0x18000adad  mov     [rsp+710h+var_6B0], r8
0x18000adb2  mov     rbx, rdx
0x18000adb5  mov     r12, rcx
0x18000adb8  mov     r13, [rbp+610h+rfid]
0x18000adbf  mov     rcx, rdx; lpFileName
0x18000adc2  call    cs:__imp_GetFileAttributesW
0x18000adc9  nop     dword ptr [rax+rax+00h]
0x18000adce  xor     edi, edi
0x18000add0  cmp     eax, 0FFFFFFFFh
0x18000add3  jnz     short loc_18000AE37
0x18000add5  call    cs:__imp_GetLastError
0x18000addc  nop     dword ptr [rax+rax+00h]
0x18000ade1  mov     ecx, eax
0x18000ade3  cmp     [rbp+610h+arg_20], edi
0x18000ade9  jz      short loc_18000AE23
0x18000adeb  add     eax, 0FFFFFFFEh
0x18000adee  cmp     eax, 1
0x18000adf1  ja      short loc_18000AE23
0x18000adf3  mov     rcx, rbx; unsigned __int16 *
0x18000adf6  call    ?CreateNestedDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CreateNestedDirectory(ushort const *,_SECURITY_ATTRIBUTES *)
0x18000adfb  mov     ebx, eax
0x18000adfd  test    eax, eax
0x18000adff  jns     short loc_18000AE47
0x18000ae01  mov     edx, 127h; void *
0x18000ae06  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000ae0d  mov     r9d, ebx; char *
0x18000ae10  mov     rcx, [rbp+618h]; this
0x18000ae17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ae1c  mov     eax, ebx
0x18000ae1e  jmp     loc_18000B7B5
0x18000ae23  test    ecx, ecx
0x18000ae25  jle     short loc_18000AE30
0x18000ae27  movzx   ecx, cx
0x18000ae2a  or      ecx, 80070000h
0x18000ae30  mov     eax, ecx
0x18000ae32  jmp     loc_18000B7B5
0x18000ae37  test    al, 10h
0x18000ae39  jnz     short loc_18000AE47
0x18000ae3b  mov     ebx, 80070050h
0x18000ae40  mov     edx, 12Bh
0x18000ae45  jmp     short loc_18000AE06
0x18000ae47  mov     ebx, 0A0h
0x18000ae4c  mov     ecx, ebx; unsigned __int64
0x18000ae4e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000ae53  mov     rsi, rax
0x18000ae56  test    rax, rax
0x18000ae59  jz      short loc_18000AE6A
0x18000ae5b  mov     r8d, ebx; Size
0x18000ae5e  xor     edx, edx; Val
0x18000ae60  mov     rcx, rax; void *
0x18000ae63  call    memset_0
0x18000ae68  jmp     short loc_18000AE6D
0x18000ae6a  mov     rsi, rdi
0x18000ae6d  mov     [rsp+710h+var_6A0], rsi
0x18000ae72  mov     [rsp+710h+var_698], 14h
0x18000ae7b  test    rsi, rsi
0x18000ae7e  jz      loc_18000B792
0x18000ae84  mov     rax, [r13+0]
0x18000ae88  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000ae8c  cmp     rax, qword ptr cs:FOLDERID_UserProfiles.Data1
0x18000ae93  jnz     short loc_18000AEA2
0x18000ae95  mov     rax, [r13+8]
0x18000ae99  cmp     rax, qword ptr cs:FOLDERID_UserProfiles.Data4
0x18000aea0  jz      short loc_18000AEC4
0x18000aea2  mov     rax, [r13+0]
0x18000aea6  cmp     rax, qword ptr cs:FOLDERID_ProgramData.Data1
0x18000aead  jnz     loc_18000B1B0
0x18000aeb3  mov     rax, [r13+8]
0x18000aeb7  cmp     rax, qword ptr cs:FOLDERID_ProgramData.Data4
0x18000aebe  jnz     loc_18000B1B0
0x18000aec4  mov     [rsp+710h+pszPath], rdi
0x18000aec9  mov     r15, r14
0x18000aecc  inc     r15
0x18000aecf  cmp     [r12+r15*2], di
0x18000aed4  jnz     short loc_18000AECC
0x18000aed6  inc     r15
0x18000aed9  lea     rdx, [r15+r15]; uBytes
0x18000aedd  xor     ecx, ecx; uFlags
0x18000aedf  call    cs:__imp_LocalAlloc
0x18000aee6  nop     dword ptr [rax+rax+00h]
0x18000aeeb  mov     rdx, rax
0x18000aeee  lea     rcx, [rsp+710h+pszPath]
0x18000aef3  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000aef8  mov     rbx, [rsp+710h+pszPath]
0x18000aefd  test    rbx, rbx
0x18000af00  jnz     short loc_18000AF67
0x18000af02  mov     rcx, [rbp+618h]; this
0x18000af09  mov     [rsp+710h+dwFlagsAndAttributes], r15d; char *
0x18000af0e  lea     rax, aSizeU; "Size %u."
0x18000af15  mov     qword ptr [rsp+710h+dwCreationDisposition], rax; int
0x18000af1a  mov     edi, 8007000Eh
0x18000af1f  mov     r9d, edi; char *
0x18000af22  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000af29  mov     edx, 139h; void *
0x18000af2e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000af33  lea     rcx, [rsp+710h+pszPath]
0x18000af38  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18000af3d  nop
0x18000af3e  mov     rbx, rsi
0x18000af41  lea     r14, [rsi+0A0h]
0x18000af48  cmp     rsi, r14
0x18000af4b  jz      loc_18000B73E
0x18000af51  mov     rcx, [rbx]; hObject
0x18000af54  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18000af59  add     rbx, 8
0x18000af5d  cmp     rbx, r14
0x18000af60  jnz     short loc_18000AF51
0x18000af62  jmp     loc_18000B73E
0x18000af67  mov     r8, r12; unsigned __int16 *
0x18000af6a  mov     rdx, r15; unsigned __int64
0x18000af6d  mov     rcx, rbx; unsigned __int16 *
0x18000af70  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000af75  mov     edi, eax
0x18000af77  test    eax, eax
0x18000af79  jns     short loc_18000AFE0
0x18000af7b  mov     rcx, [rbp+618h]; this
0x18000af82  mov     dword ptr [rsp+710h+hTemplateFile], r15d
0x18000af87  mov     qword ptr [rsp+710h+dwFlagsAndAttributes], r12; char *
0x18000af8c  lea     rax, aPathWsSizeU; "Path %ws, size %u."
0x18000af93  mov     qword ptr [rsp+710h+dwCreationDisposition], rax; int
0x18000af98  mov     r9d, edi; char *
0x18000af9b  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000afa2  mov     edx, 13Bh; void *
0x18000afa7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000afac  lea     rcx, [rsp+710h+pszPath]
0x18000afb1  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18000afb6  nop
0x18000afb7  mov     rbx, rsi
0x18000afba  lea     r14, [rsi+0A0h]
0x18000afc1  cmp     rsi, r14
0x18000afc4  jz      loc_18000B73E
0x18000afca  mov     rcx, [rbx]; hObject
0x18000afcd  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18000afd2  add     rbx, 8
0x18000afd6  cmp     rbx, r14
0x18000afd9  jnz     short loc_18000AFCA
0x18000afdb  jmp     loc_18000B73E
0x18000afe0  mov     rdx, r15; cchPath
0x18000afe3  mov     rcx, rbx; pszPath
0x18000afe6  call    cs:__imp_PathCchRemoveFileSpec
0x18000afed  nop     dword ptr [rax+rax+00h]
0x18000aff2  mov     edi, eax
0x18000aff4  test    eax, eax
0x18000aff6  jns     short loc_18000B047
0x18000aff8  mov     rcx, [rbp+618h]; this
0x18000afff  mov     r9d, eax; char *
0x18000b002  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000b009  mov     edx, 13Eh; void *
0x18000b00e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b013  lea     rcx, [rsp+710h+pszPath]
0x18000b018  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18000b01d  nop
0x18000b01e  mov     rbx, rsi
0x18000b021  lea     r14, [rsi+0A0h]
0x18000b028  cmp     rsi, r14
0x18000b02b  jz      loc_18000B73E
0x18000b031  mov     rcx, [rbx]; hObject
0x18000b034  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18000b039  add     rbx, 8
0x18000b03d  cmp     rbx, r14
0x18000b040  jnz     short loc_18000B031
0x18000b042  jmp     loc_18000B73E
0x18000b047  mov     [rsp+710h+BytesReturned], 0
0x18000b04f  jmp     loc_18000B18E
0x18000b054  mov     [rsp+710h+hTemplateFile], 0; hTemplateFile
0x18000b05d  mov     [rsp+710h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18000b065  mov     [rsp+710h+dwCreationDisposition], 3; int
0x18000b06d  xor     r9d, r9d; lpSecurityAttributes
0x18000b070  mov     edx, 80000000h; dwDesiredAccess
0x18000b075  lea     r8d, [r9+1]; dwShareMode
0x18000b079  mov     rcx, rbx; lpFileName
0x18000b07c  call    cs:__imp_CreateFileW
0x18000b083  nop     dword ptr [rax+rax+00h]
0x18000b088  mov     rdi, rax
0x18000b08b  mov     [rsp+710h+var_6C8], rax
0x18000b090  cmp     rax, r14
0x18000b093  jz      loc_18000B382
0x18000b099  xor     r9d, r9d; dwFlags
0x18000b09c  mov     r8d, 104h; cchFilePath
0x18000b0a2  lea     rdx, [rbp+610h+szFilePath]; lpszFilePath
0x18000b0a9  mov     rcx, rax; hFile
0x18000b0ac  call    cs:__imp_GetFinalPathNameByHandleW
0x18000b0b3  nop     dword ptr [rax+rax+00h]
0x18000b0b8  dec     eax
0x18000b0ba  cmp     eax, 103h
0x18000b0bf  ja      loc_18000B32A
0x18000b0c5  mov     r8d, 4; MaxCount
0x18000b0cb  lea     rdx, String2; "\\\\?\\"
0x18000b0d2  lea     rcx, [rbp+610h+szFilePath]; String1
0x18000b0d9  call    wcsncmp_0
0x18000b0de  lea     rcx, [rbp+610h+szFilePath]
0x18000b0e5  lea     rdx, [rbp+610h+String1]
0x18000b0ec  test    eax, eax
0x18000b0ee  cmovz   rcx, rdx; String1
0x18000b0f2  mov     r8, r15; MaxCount
0x18000b0f5  mov     rdx, rbx; String2
0x18000b0f8  call    cs:__imp__wcsnicmp
0x18000b0ff  nop     dword ptr [rax+rax+00h]
0x18000b104  test    eax, eax
0x18000b106  jnz     loc_18000B2EB
0x18000b10c  mov     [rsp+710h+FileInformation], 0
0x18000b115  lea     r9d, [rax+8]; dwBufferSize
0x18000b119  lea     r8, [rsp+710h+FileInformation]; lpFileInformation
0x18000b11e  lea     edx, [rax+9]; FileInformationClass
0x18000b121  mov     rcx, rdi; hFile
0x18000b124  call    cs:__imp_GetFileInformationByHandleEx
0x18000b12b  nop     dword ptr [rax+rax+00h]
0x18000b130  test    eax, eax
0x18000b132  jz      loc_18000B293
0x18000b138  test    dword ptr [rsp+710h+FileInformation], 400h
0x18000b140  jz      short loc_18000B150
0x18000b142  test    dword ptr [rsp+710h+FileInformation+4], 0A000000Fh
0x18000b14a  jnz     loc_18000B1FC
0x18000b150  mov     ecx, [rsp+710h+BytesReturned]
0x18000b154  cmp     ecx, 14h
0x18000b157  jnb     short loc_18000B168
0x18000b159  mov     [rsp+710h+var_6C8], r14
0x18000b15e  mov     [rsi+rcx*8], rdi
0x18000b162  inc     ecx
0x18000b164  mov     [rsp+710h+BytesReturned], ecx
0x18000b168  mov     rdx, r15; cchPath
0x18000b16b  mov     rcx, rbx; pszPath
0x18000b16e  call    cs:__imp_PathCchRemoveFileSpec
0x18000b175  nop     dword ptr [rax+rax+00h]
0x18000b17a  mov     edi, eax
0x18000b17c  test    eax, eax
0x18000b17e  js      loc_18000B23A
0x18000b184  lea     rcx, [rsp+710h+var_6C8]
0x18000b189  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000b18e  mov     rdx, r13; rfid
0x18000b191  mov     rcx, rbx; unsigned __int16 *
0x18000b194  call    ?IsPathUnderKnownFolder@@YAHPEBGAEBU_GUID@@@Z; IsPathUnderKnownFolder(ushort const *,_GUID const &)
0x18000b199  test    eax, eax
0x18000b19b  jnz     loc_18000B054
0x18000b1a1  lea     rcx, [rsp+710h+pszPath]
0x18000b1a6  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18000b1ab  mov     r15, [rsp+710h+var_6B0]
0x18000b1b0  xor     edx, edx; lpSecurityAttributes
0x18000b1b2  mov     rcx, r12; lpPathName
0x18000b1b5  call    cs:__imp_CreateDirectoryW
0x18000b1bc  nop     dword ptr [rax+rax+00h]
0x18000b1c1  xor     r13d, r13d
0x18000b1c4  test    eax, eax
0x18000b1c6  jnz     loc_18000B3DA
0x18000b1cc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000b1d1  mov     edi, eax
0x18000b1d3  mov     rbx, rsi
0x18000b1d6  lea     r14, [rsi+0A0h]
0x18000b1dd  cmp     rsi, r14
0x18000b1e0  jz      loc_18000B73E
0x18000b1e6  mov     rcx, [rbx]; hObject
0x18000b1e9  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18000b1ee  add     rbx, 8
0x18000b1f2  cmp     rbx, r14
0x18000b1f5  jnz     short loc_18000B1E6
0x18000b1f7  jmp     loc_18000B73E
0x18000b1fc  lea     rcx, [rsp+710h+var_6C8]
0x18000b201  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000b206  lea     rcx, [rsp+710h+pszPath]
0x18000b20b  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18000b210  nop
0x18000b211  mov     rbx, rsi
0x18000b214  lea     rdi, [rsi+0A0h]
0x18000b21b  cmp     rsi, rdi
0x18000b21e  jz      loc_18000B320
0x18000b224  mov     rcx, [rbx]; hObject
0x18000b227  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18000b22c  add     rbx, 8
0x18000b230  cmp     rbx, rdi
0x18000b233  jnz     short loc_18000B224
0x18000b235  jmp     loc_18000B320
0x18000b23a  mov     rcx, [rbp+618h]; this
0x18000b241  mov     r9d, eax; char *
0x18000b244  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000b24b  mov     edx, 16Ah; void *
0x18000b250  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b255  lea     rcx, [rsp+710h+var_6C8]
0x18000b25a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000b25f  lea     rcx, [rsp+710h+pszPath]
0x18000b264  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18000b269  nop
0x18000b26a  mov     rbx, rsi
0x18000b26d  lea     r14, [rsi+0A0h]
0x18000b274  cmp     rsi, r14
0x18000b277  jz      loc_18000B73E
  ... truncated ...
```

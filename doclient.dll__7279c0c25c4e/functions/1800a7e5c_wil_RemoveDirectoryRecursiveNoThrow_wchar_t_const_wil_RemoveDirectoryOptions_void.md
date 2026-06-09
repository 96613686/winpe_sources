# wil::RemoveDirectoryRecursiveNoThrow(wchar_t const *,wil::RemoveDirectoryOptions,void *)

- ea: `0x1800a7e5c`
- end: `0x1800a8403`
- name: `?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEB_WW4RemoveDirectoryOptions@1@PEAX@Z`
- size: `1447`
- prototype: `__int64 __fastcall(void *, int, void *)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18009d324`
- `0x1800a5f14`
- `0x1800a7e5c`

## callees

- `0x180008618`
- `0x180008b1c`
- `0x18000933c`
- `0x1800a7868`
- `0x1800a79e4`
- `0x1800a7d60`
- `0x1800a7e5c`
- `0x1800f82f0`
- `0x180108ed0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a80a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8114`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a829b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a80a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8114`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a829b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a81a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a81e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8267`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a81a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a81e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8267`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a7f4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a7fa3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a7fb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a80b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a80cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a80da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a8187`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a82aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a82c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a82d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a8304`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a83c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a83d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a7f4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a7fa3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a7fb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a80b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a80cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a80da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a8187`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a82aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a82c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a82d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a8304`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a83c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a83d1`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800a7f73`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800a802d`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800a7f73`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800a802d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800a7fd7`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800a7fd7`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800a80bd`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800a82b3`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800a83b4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800a80bd`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800a82b3`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800a83b4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a8147`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a8147`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a8166`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a8166`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800a8194`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800a8194`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a8120`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a8170`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a8120`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a8170`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800a81da`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800a820c`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800a81da`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800a820c`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800a80f9`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800a8343`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800a80f9`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800a8343`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x1800a7ea7`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x1800a7ea7`

## string_xrefs

- `0x1800a7ed1`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\filesystem.h`
- `0x1800a7f32`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\filesystem.h`
- `0x1800a7f86`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\filesystem.h`
- `0x1800a808e`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\filesystem.h`
- `0x1800a8226`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\filesystem.h`
- `0x1800a8240`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\filesystem.h`
- `0x1800a8278`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\filesystem.h`
- `0x1800a82e9`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\filesystem.h`
- `0x1800a832f`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\filesystem.h`
- `0x1800a8374`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\filesystem.h`
- `0x1800a8394`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\filesystem.h`

## pseudocode

```c
__int64 __fastcall wil::RemoveDirectoryRecursiveNoThrow(void *a1, int a2, void *a3)
{
  WCHAR *v6; // rbx
  unsigned int v7; // ebx
  ULONG v9; // r8d
  int v10; // eax
  HRESULT v11; // eax
  unsigned int v12; // edi
  char *FirstFileW; // rdi
  const char *v14; // r9
  HRESULT v15; // eax
  unsigned int LastError; // esi
  char *v17; // rsi
  int v18; // eax
  unsigned int v19; // r14d
  const char *v20; // r9
  const char *v21; // r9
  DWORD FileAttributesW; // eax
  DWORD v23; // eax
  DWORD v24; // eax
  const char *v25; // r9
  __int64 v26; // rdx
  int v27; // eax
  int v28; // eax
  DWORD v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r9
  __int64 v32; // rdx
  int v33; // [rsp+20h] [rbp-E0h]
  _BYTE v34[8]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v35[14]; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE hObject; // [rsp+A8h] [rbp-58h] BYREF
  HLOCAL hMem; // [rsp+B0h] [rbp-50h] BYREF
  PWSTR ppszPathOut; // [rsp+B8h] [rbp-48h] BYREF
  char FileInformation[16]; // [rsp+C0h] [rbp-40h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+268h]

  hMem = 0;
  if ( !wcsncmp((const wchar_t *)a1, L"\\\\?\\", 4u) )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
      &hMem,
      a1,
      -1);
    v6 = (WCHAR *)hMem;
    if ( !hMem )
    {
      v7 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x104,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\filesystem.h",
        (const char *)0x8007000ELL,
        v33);
      return v7;
    }
    v9 = 16;
  }
  else
  {
    hObject = a1;
    v35[0] = ___7____func_V_lambda_1___1____GetFullPathNameW_V__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6APEAXPEAX_Z_1_LocalFree__YAPEAX0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil___0BAA__wil__YAJPEB_WAEAV__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6APEAXPEAX_Z_1_LocalFree__YAPEAX0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___2_PEAPEB_W_Z___A6AJPEA_W_KPEA_K_Z___function_wistd__6B_;
    v35[1] = &hObject;
    v35[13] = v35;
    v10 = wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
            &hMem,
            v34);
    v7 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10C,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\filesystem.h",
        (const char *)(unsigned int)v10,
        v33);
      if ( hMem )
        LocalFree(hMem);
      return v7;
    }
    v6 = (WCHAR *)hMem;
    v9 = 1;
  }
  ppszPathOut = 0;
  v11 = PathAllocCombine(v6, L"*", v9, &ppszPathOut);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x111,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\filesystem.h",
      (const char *)(unsigned int)v11,
      v33);
    if ( ppszPathOut )
      LocalFree(ppszPathOut);
    if ( v6 )
      LocalFree(v6);
    return v12;
  }
  memset(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (char *)FindFirstFileW(ppszPathOut, &FindFileData);
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x115,
                  (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\filesystem.h",
                  v14);
LABEL_87:
    if ( ppszPathOut )
      LocalFree(ppszPathOut);
    if ( v6 )
      LocalFree(v6);
    return LastError;
  }
  do
  {
    if ( (FindFileData.dwFileAttributes & 0x10) != 0
      && FindFileData.cFileName[0] == 46
      && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2]) )
    {
      continue;
    }
    hMem = 0;
    v15 = PathAllocCombine(v6, FindFileData.cFileName, 0x18u, (PWSTR *)&hMem);
    LastError = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x120,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\filesystem.h",
        (const char *)(unsigned int)v15,
        v33);
      goto LABEL_74;
    }
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
    {
      if ( !DeleteFileW((LPCWSTR)hMem) )
      {
        if ( (a2 & 2) == 0 || GetLastError() != 5 )
        {
          v30 = 321;
LABEL_73:
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)v30,
                        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensour"
                                      "ce\\wil\\filesystem.h",
                        v21);
LABEL_74:
          if ( hMem )
            LocalFree(hMem);
LABEL_86:
          FindClose(FirstFileW);
          goto LABEL_87;
        }
        FileAttributesW = GetFileAttributesW((LPCWSTR)hMem);
        if ( (FileAttributesW & 1) == 0 )
        {
          v30 = 325;
          goto LABEL_73;
        }
        v23 = FileAttributesW & 0xFFFFFFFE;
        if ( !v23 )
          v23 = 128;
        SetFileAttributesW((LPCWSTR)hMem, v23);
        if ( !DeleteFileW((LPCWSTR)hMem) )
        {
          v30 = 336;
          goto LABEL_73;
        }
      }
      goto LABEL_46;
    }
    hObject = 0;
    wil::TryCreateFileCanRecurseIntoDirectory(&hObject, hMem, &FindFileData);
    v17 = (char *)hObject;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v18 = wil::RemoveDirectoryRecursiveNoThrow(hMem, a2 & 0xFFFFFFFE, hObject);
      v19 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12C,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\filesystem.h",
          (const char *)(unsigned int)v18,
          v33);
LABEL_27:
        CloseHandle(v17);
LABEL_28:
        if ( hMem )
          LocalFree(hMem);
        FindClose(FirstFileW);
        if ( ppszPathOut )
          LocalFree(ppszPathOut);
        if ( v6 )
          LocalFree(v6);
        return v19;
      }
      goto LABEL_37;
    }
    if ( (FindFileData.dwFileAttributes & 0x400) == 0 )
    {
      v29 = GetLastError();
      if ( !v29 )
      {
        if ( (unsigned __int64)(v17 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v17);
        if ( hMem )
          LocalFree(hMem);
        goto LABEL_67;
      }
      v28 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x136,
              (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\filesystem.h",
              (const char *)v29,
              v33);
LABEL_59:
      v19 = v28;
      if ( (unsigned __int64)(v17 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
        goto LABEL_28;
      goto LABEL_27;
    }
    if ( !RemoveDirectoryW((LPCWSTR)hMem) )
    {
      v28 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x131,
              (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\filesystem.h",
              v20);
      goto LABEL_59;
    }
LABEL_37:
    if ( (unsigned __int64)(v17 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v17);
LABEL_46:
    if ( hMem )
      LocalFree(hMem);
  }
  while ( FindNextFileW(FirstFileW, &FindFileData) );
  v24 = GetLastError();
  if ( v24 != 18 )
  {
    if ( !v24 )
      goto LABEL_67;
    v31 = v24;
    v32 = 348;
    goto LABEL_79;
  }
  if ( (a2 & 1) != 0 )
    goto LABEL_67;
  if ( a3 == (void *)-1LL )
  {
    if ( RemoveDirectoryW(v6) )
      goto LABEL_67;
    v26 = 381;
LABEL_56:
    v27 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v26,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\filesystem.h",
            v25);
LABEL_57:
    LastError = v27;
    goto LABEL_86;
  }
  LODWORD(hObject) = 3;
  if ( SetFileInformationByHandle(a3, FileRenameInfoEx|FileDispositionInfo, &hObject, 4u) )
    goto LABEL_67;
  if ( GetLastError() == 5 )
  {
    v31 = 5;
    v32 = 374;
LABEL_79:
    v27 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v32,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\filesystem.h",
            (const char *)v31,
            v33);
    goto LABEL_57;
  }
  FileInformation[0] = 1;
  if ( !SetFileInformationByHandle(a3, FileDispositionInfo, FileInformation, 1u) )
  {
    v26 = 369;
    goto LABEL_56;
  }
LABEL_67:
  FindClose(FirstFileW);
  if ( ppszPathOut )
    LocalFree(ppszPathOut);
  if ( v6 )
    LocalFree(v6);
  return 0;
}

```

## disassembly

```asm
0x1800a7e5c  mov     [rsp-8+arg_18], rbx
0x1800a7e61  push    rbp
0x1800a7e62  push    rsi
0x1800a7e63  push    rdi
0x1800a7e64  push    r12
0x1800a7e66  push    r13
0x1800a7e68  push    r14
0x1800a7e6a  push    r15
0x1800a7e6c  lea     rbp, [rsp-230h]
0x1800a7e74  sub     rsp, 330h
0x1800a7e7b  mov     rax, cs:__security_cookie
0x1800a7e82  xor     rax, rsp
0x1800a7e85  mov     [rbp+260h+var_40], rax
0x1800a7e8c  xor     r13d, r13d
0x1800a7e8f  mov     r15, r8
0x1800a7e92  mov     r12d, edx
0x1800a7e95  mov     [rbp+260h+hMem], r13
0x1800a7e99  lea     rdx, String2
0x1800a7ea0  mov     rbx, rcx
0x1800a7ea3  lea     r8d, [r13+4]; MaxCount
0x1800a7ea7  call    cs:__imp_wcsncmp
0x1800a7ead  lea     rcx, [rbp+260h+hMem]
0x1800a7eb1  test    eax, eax
0x1800a7eb3  jnz     short loc_1800A7EF9
0x1800a7eb5  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800a7eb9  mov     rdx, rbx
0x1800a7ebc  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z
0x1800a7ec1  mov     rbx, [rbp+260h+hMem]
0x1800a7ec5  test    rbx, rbx
0x1800a7ec8  jnz     short loc_1800A7EF1
0x1800a7eca  mov     rcx, [rbp+268h]; this
0x1800a7ed1  lea     r8, aCW1SPackagesMi_1
0x1800a7ed8  mov     ebx, 8007000Eh
0x1800a7edd  mov     edx, 104h; void *
0x1800a7ee2  mov     r9d, ebx; char *
0x1800a7ee5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x1800a7eea  mov     eax, ebx
0x1800a7eec  jmp     loc_1800A83D9
0x1800a7ef1  mov     r8d, 10h
0x1800a7ef7  jmp     short loc_1800A7F61
0x1800a7ef9  lea     rax, ??_7?$__func@V_lambda_1_@?1???$GetFullPathNameW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEB_WAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@2@PEAPEB_W@Z@$$A6AJPEA_W_KPEA_K@Z@__function@wistd@@6B@
0x1800a7f00  mov     [rbp+260h+hObject], rbx
0x1800a7f04  mov     [rsp+360h+var_328], rax
0x1800a7f09  lea     rdx, [rsp+360h+var_330]
0x1800a7f0e  lea     rax, [rbp+260h+hObject]
0x1800a7f12  mov     [rsp+360h+var_320], rax
0x1800a7f17  lea     rax, [rsp+360h+var_328]
0x1800a7f1c  mov     [rbp+260h+var_2C0], rax
0x1800a7f20  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z
0x1800a7f25  mov     ebx, eax
0x1800a7f27  test    eax, eax
0x1800a7f29  jns     short loc_1800A7F57
0x1800a7f2b  mov     rcx, [rbp+268h]; this
0x1800a7f32  lea     r8, aCW1SPackagesMi_1
0x1800a7f39  mov     r9d, eax; char *
0x1800a7f3c  mov     edx, 10Ch; void *
0x1800a7f41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x1800a7f46  mov     rcx, [rbp+260h+hMem]; hMem
0x1800a7f4a  test    rcx, rcx
0x1800a7f4d  jz      short loc_1800A7EEA
0x1800a7f4f  call    cs:__imp_LocalFree
0x1800a7f55  jmp     short loc_1800A7EEA
0x1800a7f57  mov     rbx, [rbp+260h+hMem]
0x1800a7f5b  mov     r8d, 1; dwFlags
0x1800a7f61  lea     r9, [rbp+260h+ppszPathOut]; ppszPathOut
0x1800a7f65  mov     [rbp+260h+ppszPathOut], r13
0x1800a7f69  lea     rdx, asc_180138A58
0x1800a7f70  mov     rcx, rbx; pszPathIn
0x1800a7f73  call    cs:__imp_PathAllocCombine
0x1800a7f79  mov     edi, eax
0x1800a7f7b  test    eax, eax
0x1800a7f7d  jns     short loc_1800A7FBE
0x1800a7f7f  mov     rcx, [rbp+268h]; this
0x1800a7f86  lea     r8, aCW1SPackagesMi_1
0x1800a7f8d  mov     r9d, eax; char *
0x1800a7f90  mov     edx, 111h; void *
0x1800a7f95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x1800a7f9a  mov     rcx, [rbp+260h+ppszPathOut]; hMem
0x1800a7f9e  test    rcx, rcx
0x1800a7fa1  jz      short loc_1800A7FA9
0x1800a7fa3  call    cs:__imp_LocalFree
0x1800a7fa9  test    rbx, rbx
0x1800a7fac  jz      short loc_1800A7FB7
0x1800a7fae  mov     rcx, rbx; hMem
0x1800a7fb1  call    cs:__imp_LocalFree
0x1800a7fb7  mov     eax, edi
0x1800a7fb9  jmp     loc_1800A83D9
0x1800a7fbe  xor     edx, edx; Val
0x1800a7fc0  lea     rcx, [rbp+260h+FindFileData]; void *
0x1800a7fc4  mov     r8d, 250h; Size
0x1800a7fca  call    memset
0x1800a7fcf  mov     rcx, [rbp+260h+ppszPathOut]; lpFileName
0x1800a7fd3  lea     rdx, [rbp+260h+FindFileData]; lpFindFileData
0x1800a7fd7  call    cs:__imp_FindFirstFileW
0x1800a7fdd  mov     rdi, rax
0x1800a7fe0  dec     rax
0x1800a7fe3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a7fe7  ja      loc_1800A838D
0x1800a7fed  test    byte ptr [rbp+260h+FindFileData.dwFileAttributes], 10h
0x1800a7ff1  jz      short loc_1800A8018
0x1800a7ff3  cmp     [rbp+260h+FindFileData.cFileName], 2Eh ; '.'
0x1800a7ff8  jnz     short loc_1800A8018
0x1800a7ffa  movzx   eax, [rbp+260h+FindFileData.cFileName+2]
0x1800a7ffe  test    ax, ax
0x1800a8001  jz      loc_1800A818D
0x1800a8007  cmp     ax, 2Eh ; '.'
0x1800a800b  jnz     short loc_1800A8018
0x1800a800d  cmp     [rbp+260h+FindFileData.cFileName+4], r13w
0x1800a8012  jz      loc_1800A818D
0x1800a8018  lea     r9, [rbp+260h+hMem]; ppszPathOut
0x1800a801c  mov     [rbp+260h+hMem], r13
0x1800a8020  mov     r8d, 18h; dwFlags
0x1800a8026  lea     rdx, [rbp+260h+FindFileData.cFileName]; pszMore
0x1800a802a  mov     rcx, rbx; pszPathIn
0x1800a802d  call    cs:__imp_PathAllocCombine
0x1800a8033  mov     esi, eax
0x1800a8035  test    eax, eax
0x1800a8037  js      loc_1800A836D
0x1800a803d  test    byte ptr [rbp+260h+FindFileData.dwFileAttributes], 10h
0x1800a8041  jz      loc_1800A811C
0x1800a8047  mov     rdx, [rbp+260h+hMem]
0x1800a804b  lea     r8, [rbp+260h+FindFileData]
0x1800a804f  lea     rcx, [rbp+260h+hObject]
0x1800a8053  mov     [rbp+260h+hObject], r13
0x1800a8057  call    ?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEB_WPEAU_WIN32_FIND_DATAW@@KK@Z
0x1800a805c  mov     rsi, [rbp+260h+hObject]
0x1800a8060  lea     rax, [rsi-1]
0x1800a8064  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a8068  ja      short loc_1800A80E8
0x1800a806a  mov     rcx, [rbp+260h+hMem]
0x1800a806e  mov     edx, r12d
0x1800a8071  and     edx, 0FFFFFFFEh
0x1800a8074  mov     r8, rsi
0x1800a8077  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEB_WW4RemoveDirectoryOptions@1@PEAX@Z
0x1800a807c  mov     r14d, eax
0x1800a807f  test    eax, eax
0x1800a8081  jns     loc_1800A8107
0x1800a8087  mov     rcx, [rbp+268h]; this
0x1800a808e  lea     r8, aCW1SPackagesMi_1
0x1800a8095  mov     r9d, eax; char *
0x1800a8098  mov     edx, 12Ch; void *
0x1800a809d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x1800a80a2  mov     rcx, rsi; hObject
0x1800a80a5  call    cs:__imp_CloseHandle
0x1800a80ab  mov     rcx, [rbp+260h+hMem]; hMem
0x1800a80af  test    rcx, rcx
0x1800a80b2  jz      short loc_1800A80BA
0x1800a80b4  call    cs:__imp_LocalFree
0x1800a80ba  mov     rcx, rdi; hFindFile
0x1800a80bd  call    cs:__imp_FindClose
0x1800a80c3  mov     rcx, [rbp+260h+ppszPathOut]; hMem
0x1800a80c7  test    rcx, rcx
0x1800a80ca  jz      short loc_1800A80D2
0x1800a80cc  call    cs:__imp_LocalFree
0x1800a80d2  test    rbx, rbx
0x1800a80d5  jz      short loc_1800A80E0
0x1800a80d7  mov     rcx, rbx; hMem
0x1800a80da  call    cs:__imp_LocalFree
0x1800a80e0  mov     eax, r14d
0x1800a80e3  jmp     loc_1800A83D9
0x1800a80e8  test    [rbp+260h+FindFileData.dwFileAttributes], 400h
0x1800a80ef  jz      loc_1800A8267
0x1800a80f5  mov     rcx, [rbp+260h+hMem]; lpPathName
0x1800a80f9  call    cs:__imp_RemoveDirectoryW
0x1800a80ff  test    eax, eax
0x1800a8101  jz      loc_1800A8239
0x1800a8107  lea     rax, [rsi-1]
0x1800a810b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a810f  ja      short loc_1800A817E
0x1800a8111  mov     rcx, rsi; hObject
0x1800a8114  call    cs:__imp_CloseHandle
0x1800a811a  jmp     short loc_1800A817E
0x1800a811c  mov     rcx, [rbp+260h+hMem]; lpFileName
0x1800a8120  call    cs:__imp_DeleteFileW
0x1800a8126  test    eax, eax
0x1800a8128  jnz     short loc_1800A817E
0x1800a812a  test    r12b, 2
0x1800a812e  jz      loc_1800A8316
0x1800a8134  call    cs:__imp_GetLastError
0x1800a813a  cmp     eax, 5
0x1800a813d  jnz     loc_1800A8316
0x1800a8143  mov     rcx, [rbp+260h+hMem]; lpFileName
0x1800a8147  call    cs:__imp_GetFileAttributesW
0x1800a814d  test    al, 1
0x1800a814f  jz      loc_1800A830F
0x1800a8155  and     eax, 0FFFFFFFEh
0x1800a8158  mov     ecx, 80h
0x1800a815d  cmovz   eax, ecx
0x1800a8160  mov     rcx, [rbp+260h+hMem]; lpFileName
0x1800a8164  mov     edx, eax; dwFileAttributes
0x1800a8166  call    cs:__imp_SetFileAttributesW
0x1800a816c  mov     rcx, [rbp+260h+hMem]; lpFileName
0x1800a8170  call    cs:__imp_DeleteFileW
0x1800a8176  test    eax, eax
0x1800a8178  jz      loc_1800A82DD
0x1800a817e  mov     rcx, [rbp+260h+hMem]; hMem
0x1800a8182  test    rcx, rcx
0x1800a8185  jz      short loc_1800A818D
0x1800a8187  call    cs:__imp_LocalFree
0x1800a818d  lea     rdx, [rbp+260h+FindFileData]; lpFindFileData
0x1800a8191  mov     rcx, rdi; hFindFile
0x1800a8194  call    cs:__imp_FindNextFileW
0x1800a819a  test    eax, eax
0x1800a819c  jnz     loc_1800A7FED
0x1800a81a2  call    cs:__imp_GetLastError
0x1800a81a8  cmp     eax, 12h
0x1800a81ab  jnz     loc_1800A835B
0x1800a81b1  test    r12b, 1
0x1800a81b5  jnz     loc_1800A82B0
0x1800a81bb  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x1800a81bf  jz      loc_1800A8340
0x1800a81c5  lea     r9d, [rax-0Eh]; dwBufferSize
0x1800a81c9  mov     dword ptr [rbp+260h+hObject], 3
0x1800a81d0  lea     r8, [rbp+260h+hObject]; lpFileInformation
0x1800a81d4  mov     rcx, r15; hFile
0x1800a81d7  lea     edx, [rax+3]; FileInformationClass
0x1800a81da  call    cs:__imp_SetFileInformationByHandle
0x1800a81e0  test    eax, eax
0x1800a81e2  jnz     loc_1800A82B0
0x1800a81e8  call    cs:__imp_GetLastError
0x1800a81ee  cmp     eax, 5
0x1800a81f1  jz      loc_1800A831D
0x1800a81f7  mov     r9d, 1; dwBufferSize
0x1800a81fd  mov     [rbp+260h+FileInformation], 1
0x1800a8201  lea     r8, [rbp+260h+FileInformation]; lpFileInformation
0x1800a8205  mov     rcx, r15; hFile
0x1800a8208  lea     edx, [r9+3]; FileInformationClass
0x1800a820c  call    cs:__imp_SetFileInformationByHandle
0x1800a8212  test    eax, eax
0x1800a8214  jnz     loc_1800A82B0
0x1800a821a  mov     edx, 171h; void *
0x1800a821f  mov     rcx, [rbp+268h]; this
0x1800a8226  lea     r8, aCW1SPackagesMi_1
0x1800a822d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z
0x1800a8232  mov     esi, eax
0x1800a8234  jmp     loc_1800A83B1
0x1800a8239  mov     rcx, [rbp+268h]; this
0x1800a8240  lea     r8, aCW1SPackagesMi_1
0x1800a8247  mov     edx, 131h; void *
0x1800a824c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z
0x1800a8251  lea     rcx, [rsi-1]
0x1800a8255  mov     r14d, eax
0x1800a8258  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800a825c  ja      loc_1800A80AB
0x1800a8262  jmp     loc_1800A80A2
0x1800a8267  call    cs:__imp_GetLastError
0x1800a826d  test    eax, eax
0x1800a826f  jz      short loc_1800A828E
0x1800a8271  mov     rcx, [rbp+268h]; this
0x1800a8278  lea     r8, aCW1SPackagesMi_1
0x1800a827f  mov     r9d, eax; char *
0x1800a8282  mov     edx, 136h; void *
0x1800a8287  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z
0x1800a828c  jmp     short loc_1800A8251
0x1800a828e  lea     rax, [rsi-1]
0x1800a8292  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a8296  ja      short loc_1800A82A1
0x1800a8298  mov     rcx, rsi; hObject
0x1800a829b  call    cs:__imp_CloseHandle
0x1800a82a1  mov     rcx, [rbp+260h+hMem]; hMem
0x1800a82a5  test    rcx, rcx
0x1800a82a8  jz      short loc_1800A82B0
0x1800a82aa  call    cs:__imp_LocalFree
0x1800a82b0  mov     rcx, rdi; hFindFile
0x1800a82b3  call    cs:__imp_FindClose
0x1800a82b9  mov     rcx, [rbp+260h+ppszPathOut]; hMem
0x1800a82bd  test    rcx, rcx
0x1800a82c0  jz      short loc_1800A82C8
0x1800a82c2  call    cs:__imp_LocalFree
0x1800a82c8  test    rbx, rbx
0x1800a82cb  jz      short loc_1800A82D6
0x1800a82cd  mov     rcx, rbx; hMem
0x1800a82d0  call    cs:__imp_LocalFree
0x1800a82d6  xor     eax, eax
0x1800a82d8  jmp     loc_1800A83D9
0x1800a82dd  mov     edx, 150h; void *
0x1800a82e2  mov     rcx, [rbp+268h]; this
0x1800a82e9  lea     r8, aCW1SPackagesMi_1
0x1800a82f0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z
0x1800a82f5  mov     esi, eax
0x1800a82f7  mov     rcx, [rbp+260h+hMem]; hMem
0x1800a82fb  test    rcx, rcx
0x1800a82fe  jz      loc_1800A83B1
0x1800a8304  call    cs:__imp_LocalFree
0x1800a830a  jmp     loc_1800A83B1
0x1800a830f  mov     edx, 145h
0x1800a8314  jmp     short loc_1800A82E2
0x1800a8316  mov     edx, 141h
0x1800a831b  jmp     short loc_1800A82E2
0x1800a831d  mov     r9d, 5; char *
0x1800a8323  mov     edx, 176h; void *
0x1800a8328  mov     rcx, [rbp+268h]; this
0x1800a832f  lea     r8, aCW1SPackagesMi_1
0x1800a8336  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z
0x1800a833b  jmp     loc_1800A8232
0x1800a8340  mov     rcx, rbx; lpPathName
0x1800a8343  call    cs:__imp_RemoveDirectoryW
0x1800a8349  test    eax, eax
0x1800a834b  jnz     loc_1800A82B0
0x1800a8351  mov     edx, 17Dh
  ... truncated ...
```

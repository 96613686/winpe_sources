# wil::RemoveDirectoryRecursiveNoThrow(wchar_t const *,wil::RemoveDirectoryOptions,void *)

- ea: `0x1800f9674`
- end: `0x1800f9c34`
- name: `?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEB_WW4RemoveDirectoryOptions@1@PEAX@Z`
- size: `1472`
- prototype: `__int64 __fastcall(wil *, const wchar_t *, void *)`
- caller_count: `3`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f9674`
- `0x180140a5c`
- `0x1802bbe08`

## callees

- `0x180064e6c`
- `0x180064e8c`
- `0x18008abf4`
- `0x18009c78c`
- `0x1800bc658`
- `0x1800f9674`
- `0x1800f9c3c`
- `0x1800f9c5c`
- `0x1800f9c78`
- `0x1800f9ca0`
- `0x1800f9e40`
- `0x1801bbc78`
- `0x18020aac0`
- `0x18020bab8`
- `0x18023bd5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f98bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9a64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9b04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9b64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f98bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9a64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9b04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9b64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f99f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f99f9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800f9722`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800f9722`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800f9beb`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800f9beb`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800f9a98`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800f9a98`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f988c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f9aa3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f988c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f9aa3`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800f98b2`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800f98b2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800f9a78`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800f9a78`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800f98f4`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800f9b84`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800f98f4`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800f9b84`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800f999d`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800f9bd8`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800f999d`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800f9bd8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f98a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f991a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f9928`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f98a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f991a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f9928`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f97d2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f97d2`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800f96f6`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800f986c`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800f96f6`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800f986c`

## string_xrefs

- `0x1800f9a1b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800f9744`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1800f9822`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1800f99ae`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1800f9a41`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1800f9ac2`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1800f9adf`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1800f9b4a`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1800f9ba5`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1800f9bc5`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1800f9bfd`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall wil::RemoveDirectoryRecursiveNoThrow(wil *a1, const wchar_t *a2, void *a3)
{
  int v4; // r15d
  const char *v6; // r9
  int v7; // eax
  unsigned int v8; // edi
  WCHAR *v9; // rbx
  ULONG v10; // r8d
  HRESULT v11; // eax
  char *FirstFileW; // rsi
  const char *v13; // r9
  unsigned int LastError; // ebx
  __int64 v16; // rcx
  char *v17; // rax
  rsize_t v18; // rsi
  char *v19; // rax
  char *v20; // rdi
  __int64 v21; // rdx
  __int64 v22; // r9
  HRESULT v23; // eax
  const char *v24; // r9
  DWORD v25; // eax
  char *v26; // r14
  const char *v27; // r9
  int v28; // eax
  __int64 v29; // r9
  __int64 v30; // rdx
  int v31; // eax
  DWORD FileAttributesW; // eax
  DWORD v33; // eax
  __int64 v34; // rdx
  DWORD v35; // eax
  const char *v36; // r9
  __int64 v37; // rdx
  int v38; // eax
  unsigned int v39; // [rsp+20h] [rbp-E0h]
  PWSTR ppszPathOut; // [rsp+30h] [rbp-D0h] BYREF
  void *Source; // [rsp+38h] [rbp-C8h] BYREF
  char FileInformation[8]; // [rsp+40h] [rbp-C0h] BYREF
  char *v43; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hFile; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR pszPathIn; // [rsp+58h] [rbp-A8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  pszPathIn = 0;
  v4 = (int)a2;
  if ( !wil::is_extended_length_path(a1, a2) )
  {
    v7 = wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
           a1,
           &pszPathIn);
    v8 = v7;
    if ( v7 >= 0 )
    {
      v9 = (WCHAR *)pszPathIn;
      v10 = 1;
      goto LABEL_4;
    }
    v22 = (unsigned int)v7;
    v21 = 268;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
      (const char *)v22,
      v39);
LABEL_16:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&pszPathIn);
    return v8;
  }
  if ( !a1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v6);
  v16 = 0x7FFFFFFF;
  v17 = (char *)a1;
  do
  {
    if ( !*(_WORD *)v17 )
      break;
    v17 += 2;
    --v16;
  }
  while ( v16 );
  v18 = 2 * ((v17 - (char *)a1) >> 1);
  v19 = (char *)LocalAlloc(0, v18 + 2);
  v20 = v19;
  if ( v19 )
  {
    memcpy_s_0(v19, v18 + 2, a1, v18);
    *(_WORD *)&v20[v18] = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
    &pszPathIn,
    v20);
  v9 = (WCHAR *)pszPathIn;
  if ( !pszPathIn )
  {
    v8 = -2147024882;
    v21 = 260;
    v22 = 2147942414LL;
    goto LABEL_15;
  }
  v10 = 16;
LABEL_4:
  ppszPathOut = 0;
  v11 = PathAllocCombine(v9, L"*", v10, &ppszPathOut);
  v8 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x111,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
      (const char *)(unsigned int)v11,
      v39);
LABEL_82:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&ppszPathOut);
    goto LABEL_16;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (char *)FindFirstFileW(ppszPathOut, &FindFileData);
  v43 = FirstFileW;
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x115,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                  v13);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v43);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&ppszPathOut);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&pszPathIn);
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
    Source = 0;
    v23 = PathAllocCombine(v9, FindFileData.cFileName, 0x18u, (PWSTR *)&Source);
    v8 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x120,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
        (const char *)(unsigned int)v23,
        v39);
      goto LABEL_80;
    }
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
    {
      wil::TryCreateFileCanRecurseIntoDirectory(&hFile, Source, &FindFileData);
      v26 = (char *)hFile;
      if ( (char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        v31 = wil::RemoveDirectoryRecursiveNoThrow(Source, v4 & 0xFFFFFFFE);
        v8 = v31;
        if ( v31 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x12C,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
            (const char *)(unsigned int)v31,
            v39);
LABEL_64:
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
          goto LABEL_80;
        }
      }
      else
      {
        if ( (FindFileData.dwFileAttributes & 0x400) == 0 )
        {
          v35 = GetLastError();
          if ( !v35 )
          {
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&Source);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v43);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&ppszPathOut);
            v8 = 0;
            goto LABEL_16;
          }
          v28 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x136,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                  (const char *)v35,
                  v39);
          goto LABEL_63;
        }
        if ( !RemoveDirectoryW((LPCWSTR)Source) )
        {
          v28 = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x131,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                  v27);
LABEL_63:
          v8 = v28;
          goto LABEL_64;
        }
        if ( (unsigned __int64)(v26 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
          goto LABEL_22;
      }
      CloseHandle(v26);
    }
    else if ( !DeleteFileW((LPCWSTR)Source) )
    {
      if ( (v4 & 2) == 0 || GetLastError() != 5 )
      {
        v34 = 321;
        goto LABEL_68;
      }
      FileAttributesW = GetFileAttributesW((LPCWSTR)Source);
      if ( (FileAttributesW & 1) == 0 )
      {
        v34 = 325;
LABEL_68:
        v8 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v34,
               (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
               v24);
LABEL_80:
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&Source);
LABEL_81:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v43);
        goto LABEL_82;
      }
      v33 = FileAttributesW & 0xFFFFFFFE;
      if ( !v33 )
        v33 = 128;
      SetFileAttributesW((LPCWSTR)Source, v33);
      if ( !DeleteFileW((LPCWSTR)Source) )
      {
        v34 = 336;
        goto LABEL_68;
      }
    }
LABEL_22:
    if ( Source )
      LocalFree(Source);
  }
  while ( FindNextFileW(FirstFileW, &FindFileData) );
  v25 = GetLastError();
  if ( v25 != 18 )
  {
    if ( !v25 )
      goto LABEL_29;
    v29 = v25;
    v30 = 348;
    goto LABEL_75;
  }
  if ( (v4 & 1) != 0 )
    goto LABEL_29;
  if ( a3 == (void *)-1LL )
  {
    if ( RemoveDirectoryW(v9) )
      goto LABEL_29;
    v37 = 381;
LABEL_73:
    v38 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v37,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
            v36);
LABEL_76:
    v8 = v38;
    goto LABEL_81;
  }
  LODWORD(hFile) = 3;
  if ( SetFileInformationByHandle(a3, FileRenameInfoEx|FileDispositionInfo, &hFile, 4u) )
    goto LABEL_29;
  if ( GetLastError() == 5 )
  {
    v29 = 5;
    v30 = 374;
LABEL_75:
    v38 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v30,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
            (const char *)v29,
            v39);
    goto LABEL_76;
  }
  FileInformation[0] = 1;
  if ( !SetFileInformationByHandle(a3, FileDispositionInfo, FileInformation, 1u) )
  {
    v37 = 369;
    goto LABEL_73;
  }
LABEL_29:
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose(FirstFileW);
  if ( ppszPathOut )
    LocalFree(ppszPathOut);
  if ( v9 )
    LocalFree(v9);
  return 0;
}

```

## disassembly

```asm
0x1800f9674  mov     [rsp-8+arg_18], rbx
0x1800f9679  push    rbp
0x1800f967a  push    rsi
0x1800f967b  push    rdi
0x1800f967c  push    r12
0x1800f967e  push    r13
0x1800f9680  push    r14
0x1800f9682  push    r15
0x1800f9684  lea     rbp, [rsp-1C0h]
0x1800f968c  sub     rsp, 2C0h
0x1800f9693  mov     rax, cs:__security_cookie
0x1800f969a  xor     rax, rsp
0x1800f969d  mov     [rbp+1F0h+var_40], rax
0x1800f96a4  xor     r13d, r13d
0x1800f96a7  mov     r12, r8
0x1800f96aa  mov     [rsp+2F0h+pszPathIn], r13
0x1800f96af  mov     r15d, edx
0x1800f96b2  mov     rbx, rcx
0x1800f96b5  call    ?is_extended_length_path@wil@@YA_NPEB_W@Z; wil::is_extended_length_path(wchar_t const *)
0x1800f96ba  test    al, al
0x1800f96bc  jnz     loc_1800F97A1
0x1800f96c2  lea     rdx, [rsp+2F0h+pszPathIn]
0x1800f96c7  mov     rcx, rbx
0x1800f96ca  call    ??$GetFullPathNameW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEB_WAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEAPEB_W@Z; wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wchar_t const * *)
0x1800f96cf  mov     edi, eax
0x1800f96d1  test    eax, eax
0x1800f96d3  js      loc_1800F9A2D
0x1800f96d9  mov     rbx, [rsp+2F0h+pszPathIn]
0x1800f96de  lea     r8d, [r13+1]; dwFlags
0x1800f96e2  lea     r9, [rsp+2F0h+ppszPathOut]; ppszPathOut
0x1800f96e7  mov     [rsp+2F0h+ppszPathOut], r13
0x1800f96ec  lea     rdx, pszMore; "*"
0x1800f96f3  mov     rcx, rbx; pszPathIn
0x1800f96f6  call    cs:__imp_PathAllocCombine
0x1800f96fc  mov     edi, eax
0x1800f96fe  test    eax, eax
0x1800f9700  js      loc_1800F9A3A
0x1800f9706  xor     edx, edx; Val
0x1800f9708  lea     rcx, [rsp+2F0h+FindFileData]; void *
0x1800f970d  mov     r8d, 250h; Size
0x1800f9713  call    memset_0
0x1800f9718  mov     rcx, [rsp+2F0h+ppszPathOut]; lpFileName
0x1800f971d  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x1800f9722  call    cs:__imp_FindFirstFileW
0x1800f9728  mov     rsi, rax
0x1800f972b  mov     [rsp+2F0h+var_2A8], rax
0x1800f9730  dec     rax
0x1800f9733  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800f9737  jbe     loc_1800F984A
0x1800f973d  mov     rcx, [rbp+1F8h]; this
0x1800f9744  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800f974b  mov     edx, 115h; void *
0x1800f9750  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800f9755  lea     rcx, [rsp+2F0h+var_2A8]
0x1800f975a  mov     ebx, eax
0x1800f975c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800f9761  lea     rcx, [rsp+2F0h+ppszPathOut]
0x1800f9766  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x1800f976b  lea     rcx, [rsp+2F0h+pszPathIn]
0x1800f9770  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x1800f9775  mov     eax, ebx
0x1800f9777  mov     rcx, [rbp+1F0h+var_40]
0x1800f977e  xor     rcx, rsp; StackCookie
0x1800f9781  call    __security_check_cookie
0x1800f9786  mov     rbx, [rsp+2F0h+arg_18]
0x1800f978e  add     rsp, 2C0h
0x1800f9795  pop     r15
0x1800f9797  pop     r14
0x1800f9799  pop     r13
0x1800f979b  pop     r12
0x1800f979d  pop     rdi
0x1800f979e  pop     rsi
0x1800f979f  pop     rbp
0x1800f97a0  retn
0x1800f97a1  test    rbx, rbx
0x1800f97a4  jz      loc_1800F9A14
0x1800f97aa  mov     ecx, 7FFFFFFFh
0x1800f97af  mov     rax, rbx
0x1800f97b2  cmp     [rax], r13w
0x1800f97b6  jz      short loc_1800F97C2
0x1800f97b8  add     rax, 2
0x1800f97bc  sub     rcx, 1
0x1800f97c0  jnz     short loc_1800F97B2
0x1800f97c2  sub     rax, rbx
0x1800f97c5  xor     ecx, ecx; uFlags
0x1800f97c7  sar     rax, 1
0x1800f97ca  lea     rsi, [rax+rax]
0x1800f97ce  lea     rdx, [rsi+2]; uBytes
0x1800f97d2  call    cs:__imp_LocalAlloc
0x1800f97d8  mov     rdi, rax
0x1800f97db  test    rax, rax
0x1800f97de  jz      short loc_1800F97F7
0x1800f97e0  mov     r9, rsi; SourceSize
0x1800f97e3  lea     rdx, [rsi+2]; DestinationSize
0x1800f97e7  mov     r8, rbx; Source
0x1800f97ea  mov     rcx, rax; Destination
0x1800f97ed  call    memcpy_s_0
0x1800f97f2  mov     [rdi+rsi], r13w
0x1800f97f7  mov     rdx, rdi
0x1800f97fa  lea     rcx, [rsp+2F0h+pszPathIn]
0x1800f97ff  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x1800f9804  mov     rbx, [rsp+2F0h+pszPathIn]
0x1800f9809  test    rbx, rbx
0x1800f980c  jnz     short loc_1800F983F
0x1800f980e  mov     edi, 8007000Eh
0x1800f9813  mov     edx, 104h; void *
0x1800f9818  mov     r9d, edi; char *
0x1800f981b  mov     rcx, [rbp+1F8h]; this
0x1800f9822  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800f9829  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f982e  lea     rcx, [rsp+2F0h+pszPathIn]
0x1800f9833  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x1800f9838  mov     eax, edi
0x1800f983a  jmp     loc_1800F9777
0x1800f983f  mov     r8d, 10h
0x1800f9845  jmp     loc_1800F96E2
0x1800f984a  test    byte ptr [rsp+2F0h+FindFileData.dwFileAttributes], 10h
0x1800f984f  jnz     loc_1800F9935
0x1800f9855  lea     r9, [rsp+2F0h+Source]; ppszPathOut
0x1800f985a  mov     [rsp+2F0h+Source], r13
0x1800f985f  mov     r8d, 18h; dwFlags
0x1800f9865  lea     rdx, [rbp+1F0h+FindFileData.cFileName]; pszMore
0x1800f9869  mov     rcx, rbx; pszPathIn
0x1800f986c  call    cs:__imp_PathAllocCombine
0x1800f9872  mov     edi, eax
0x1800f9874  test    eax, eax
0x1800f9876  js      loc_1800F9BF6
0x1800f987c  test    byte ptr [rsp+2F0h+FindFileData.dwFileAttributes], 10h
0x1800f9881  jnz     loc_1800F9967
0x1800f9887  mov     rcx, [rsp+2F0h+Source]; lpFileName
0x1800f988c  call    cs:__imp_DeleteFileW
0x1800f9892  test    eax, eax
0x1800f9894  jz      loc_1800F9A5A
0x1800f989a  mov     rcx, [rsp+2F0h+Source]; hMem
0x1800f989f  test    rcx, rcx
0x1800f98a2  jz      short loc_1800F98AA
0x1800f98a4  call    cs:__imp_LocalFree
0x1800f98aa  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x1800f98af  mov     rcx, rsi; hFindFile
0x1800f98b2  call    cs:__imp_FindNextFileW
0x1800f98b8  test    eax, eax
0x1800f98ba  jnz     short loc_1800F984A
0x1800f98bc  call    cs:__imp_GetLastError
0x1800f98c2  cmp     eax, 12h
0x1800f98c5  jnz     loc_1800F99C4
0x1800f98cb  test    r15b, 1
0x1800f98cf  jnz     short loc_1800F9902
0x1800f98d1  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x1800f98d5  jz      loc_1800F9BD5
0x1800f98db  lea     edi, [rax-0Eh]
0x1800f98de  mov     dword ptr [rsp+2F0h+hFile], 3
0x1800f98e6  mov     r9d, edi; dwBufferSize
0x1800f98e9  lea     r8, [rsp+2F0h+hFile]; lpFileInformation
0x1800f98ee  lea     edx, [rax+3]; FileInformationClass
0x1800f98f1  mov     rcx, r12; hFile
0x1800f98f4  call    cs:__imp_SetFileInformationByHandle
0x1800f98fa  test    eax, eax
0x1800f98fc  jz      loc_1800F9B64
0x1800f9902  lea     rax, [rsi-1]
0x1800f9906  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800f990a  jbe     loc_1800F9BE8
0x1800f9910  mov     rcx, [rsp+2F0h+ppszPathOut]; hMem
0x1800f9915  test    rcx, rcx
0x1800f9918  jz      short loc_1800F9920
0x1800f991a  call    cs:__imp_LocalFree
0x1800f9920  test    rbx, rbx
0x1800f9923  jz      short loc_1800F992E
0x1800f9925  mov     rcx, rbx; hMem
0x1800f9928  call    cs:__imp_LocalFree
0x1800f992e  xor     eax, eax
0x1800f9930  jmp     loc_1800F9777
0x1800f9935  cmp     [rbp+1F0h+FindFileData.cFileName], 2Eh ; '.'
0x1800f993a  jnz     loc_1800F9855
0x1800f9940  movzx   eax, [rbp+1F0h+FindFileData.cFileName+2]
0x1800f9944  test    ax, ax
0x1800f9947  jz      loc_1800F98AA
0x1800f994d  cmp     ax, 2Eh ; '.'
0x1800f9951  jnz     loc_1800F9855
0x1800f9957  cmp     [rbp+1F0h+FindFileData.cFileName+4], r13w
0x1800f995c  jz      loc_1800F98AA
0x1800f9962  jmp     loc_1800F9855
0x1800f9967  mov     rdx, [rsp+2F0h+Source]
0x1800f996c  lea     r8, [rsp+2F0h+FindFileData]
0x1800f9971  lea     rcx, [rsp+2F0h+hFile]
0x1800f9976  call    ?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEB_WPEAU_WIN32_FIND_DATAW@@KK@Z; wil::TryCreateFileCanRecurseIntoDirectory(wchar_t const *,_WIN32_FIND_DATAW *,ulong,ulong)
0x1800f997b  mov     r14, [rsp+2F0h+hFile]
0x1800f9980  lea     rax, [r14-1]
0x1800f9984  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800f9988  jbe     short loc_1800F99D9
0x1800f998a  test    [rsp+2F0h+FindFileData.dwFileAttributes], 400h
0x1800f9992  jz      loc_1800F9B04
0x1800f9998  mov     rcx, [rsp+2F0h+Source]; lpPathName
0x1800f999d  call    cs:__imp_RemoveDirectoryW
0x1800f99a3  test    eax, eax
0x1800f99a5  jnz     short loc_1800F9A04
0x1800f99a7  mov     rcx, [rbp+1F8h]; this
0x1800f99ae  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800f99b5  mov     edx, 131h; void *
0x1800f99ba  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800f99bf  jmp     loc_1800F9AF3
0x1800f99c4  test    eax, eax
0x1800f99c6  jz      loc_1800F9902
0x1800f99cc  mov     r9d, eax
0x1800f99cf  mov     edx, 15Ch
0x1800f99d4  jmp     loc_1800F9BBE
0x1800f99d9  mov     rcx, [rsp+2F0h+Source]
0x1800f99de  mov     edx, r15d
0x1800f99e1  and     edx, 0FFFFFFFEh
0x1800f99e4  mov     r8, r14
0x1800f99e7  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEB_WW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(wchar_t const *,wil::RemoveDirectoryOptions,void *)
0x1800f99ec  mov     edi, eax
0x1800f99ee  test    eax, eax
0x1800f99f0  js      loc_1800F9ABB
0x1800f99f6  mov     rcx, r14; hObject
0x1800f99f9  call    cs:__imp_CloseHandle
0x1800f99ff  jmp     loc_1800F989A
0x1800f9a04  lea     rax, [r14-1]
0x1800f9a08  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800f9a0c  ja      loc_1800F989A
0x1800f9a12  jmp     short loc_1800F99F6
0x1800f9a14  mov     rcx, [rbp+1F8h]; this
0x1800f9a1b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800f9a22  mov     edx, 0F89h; void *
0x1800f9a27  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800f9a2d  mov     r9d, eax
0x1800f9a30  mov     edx, 10Ch
0x1800f9a35  jmp     loc_1800F981B
0x1800f9a3a  mov     rcx, [rbp+1F8h]; this
0x1800f9a41  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800f9a48  mov     r9d, eax; char *
0x1800f9a4b  mov     edx, 111h; void *
0x1800f9a50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f9a55  jmp     loc_1800F9C25
0x1800f9a5a  test    r15b, 2
0x1800f9a5e  jz      loc_1800F9B3E
0x1800f9a64  call    cs:__imp_GetLastError
0x1800f9a6a  cmp     eax, 5
0x1800f9a6d  jnz     loc_1800F9B3E
0x1800f9a73  mov     rcx, [rsp+2F0h+Source]; lpFileName
0x1800f9a78  call    cs:__imp_GetFileAttributesW
0x1800f9a7e  test    al, 1
0x1800f9a80  jz      loc_1800F9B5D
0x1800f9a86  and     eax, 0FFFFFFFEh
0x1800f9a89  mov     ecx, 80h
0x1800f9a8e  cmovz   eax, ecx
0x1800f9a91  mov     rcx, [rsp+2F0h+Source]; lpFileName
0x1800f9a96  mov     edx, eax; dwFileAttributes
0x1800f9a98  call    cs:__imp_SetFileAttributesW
0x1800f9a9e  mov     rcx, [rsp+2F0h+Source]; lpFileName
0x1800f9aa3  call    cs:__imp_DeleteFileW
0x1800f9aa9  test    eax, eax
0x1800f9aab  jnz     loc_1800F989A
0x1800f9ab1  mov     edx, 150h
0x1800f9ab6  jmp     loc_1800F9B43
0x1800f9abb  mov     rcx, [rbp+1F8h]; this
0x1800f9ac2  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800f9ac9  mov     r9d, eax; char *
0x1800f9acc  mov     edx, 12Ch; void *
0x1800f9ad1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f9ad6  jmp     short loc_1800F9AF5
0x1800f9ad8  mov     rcx, [rbp+1F8h]; this
0x1800f9adf  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800f9ae6  mov     r9d, eax; char *
0x1800f9ae9  mov     edx, 136h; void *
0x1800f9aee  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800f9af3  mov     edi, eax
0x1800f9af5  lea     rcx, [rsp+2F0h+hFile]
0x1800f9afa  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800f9aff  jmp     loc_1800F9C11
0x1800f9b04  call    cs:__imp_GetLastError
0x1800f9b0a  test    eax, eax
0x1800f9b0c  jnz     short loc_1800F9AD8
0x1800f9b0e  lea     rcx, [rsp+2F0h+hFile]
0x1800f9b13  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800f9b18  lea     rcx, [rsp+2F0h+Source]
0x1800f9b1d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x1800f9b22  lea     rcx, [rsp+2F0h+var_2A8]
0x1800f9b27  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800f9b2c  lea     rcx, [rsp+2F0h+ppszPathOut]
0x1800f9b31  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x1800f9b36  mov     edi, r13d
0x1800f9b39  jmp     loc_1800F982E
0x1800f9b3e  mov     edx, 141h; void *
0x1800f9b43  mov     rcx, [rbp+1F8h]; this
0x1800f9b4a  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800f9b51  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800f9b56  mov     edi, eax
0x1800f9b58  jmp     loc_1800F9C11
0x1800f9b5d  mov     edx, 145h
0x1800f9b62  jmp     short loc_1800F9B43
0x1800f9b64  call    cs:__imp_GetLastError
0x1800f9b6a  cmp     eax, 5
0x1800f9b6d  jz      short loc_1800F9BB3
0x1800f9b6f  mov     r9d, 1; dwBufferSize
0x1800f9b75  mov     [rsp+2F0h+FileInformation], 1
0x1800f9b7a  lea     r8, [rsp+2F0h+FileInformation]; lpFileInformation
0x1800f9b7f  mov     edx, edi; FileInformationClass
0x1800f9b81  mov     rcx, r12; hFile
0x1800f9b84  call    cs:__imp_SetFileInformationByHandle
0x1800f9b8a  test    eax, eax
  ... truncated ...
```

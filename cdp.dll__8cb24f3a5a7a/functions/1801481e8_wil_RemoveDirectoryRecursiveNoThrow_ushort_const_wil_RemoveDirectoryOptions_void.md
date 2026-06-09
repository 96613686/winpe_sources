# wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)

- ea: `0x1801481e8`
- end: `0x180148737`
- name: `?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z`
- size: `1359`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180148190`
- `0x1801481e8`

## callees

- `0x1800a29a0`
- `0x1800da1f0`
- `0x1801481e8`
- `0x18014874c`
- `0x18014876c`
- `0x180148864`
- `0x180149448`
- `0x18014946c`
- `0x1801497c0`
- `0x18017b4a8`
- `0x1801f6fb0`
- `0x1801f7974`
- `0x18023a2c0`
- `0x18023a81c`
- `0x18023ac94`
- `0x180312fd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180148480`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801484ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180148536`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801485a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180148480`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801484ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180148536`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801485a4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18014846c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801484bf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18014846c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801484bf`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180148494`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180148494`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180148528`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180148558`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180148528`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180148558`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1801484b4`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1801484b4`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18014844d`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18014864e`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18014844d`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18014864e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180148356`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180148356`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1801484de`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1801484de`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180148310`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1801483bf`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180148310`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1801483bf`

## string_xrefs

- `0x1801482cf`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x180148323`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x180148418`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x180148572`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18014858c`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1801485b5`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x180148607`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18014863a`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18014869c`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1801486e3`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`

## pseudocode

```c
__int64 __fastcall wil::RemoveDirectoryRecursiveNoThrow(const wchar_t *a1, int a2, void *a3)
{
  const WCHAR *v6; // rbx
  int v7; // esi
  __int64 v8; // rdx
  ULONG v9; // edi
  HRESULT v10; // eax
  wchar_t *FirstFileW; // rdi
  const char *v12; // r9
  HRESULT v13; // eax
  int v14; // eax
  const char *v15; // r9
  const char *v16; // r9
  DWORD FileAttributesW; // eax
  DWORD v18; // eax
  DWORD v19; // eax
  const char *v20; // r9
  __int64 v21; // rdx
  int v22; // eax
  int v23; // eax
  DWORD v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r9
  __int64 v27; // rdx
  unsigned int LastError; // ebx
  unsigned int v30; // [rsp+20h] [rbp-E0h]
  const wchar_t *v31; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR v32; // [rsp+38h] [rbp-C8h] BYREF
  PWSTR ppszPathOut; // [rsp+40h] [rbp-C0h] BYREF
  char FileInformation[8]; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hFile; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR pszPathIn; // [rsp+58h] [rbp-A8h] BYREF
  char v37[8]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v38[15]; // [rsp+68h] [rbp-98h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+378h] [rbp+278h]

  pszPathIn = 0;
  if ( !wcsncmp_0(a1, L"\\\\?\\", 4u) )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v31,
      a1,
      -1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &pszPathIn,
      &v31);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v31);
    v6 = pszPathIn;
    if ( !pszPathIn )
    {
      v7 = -2147024882;
      v8 = 260;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
        (const char *)(unsigned int)v7,
        v30);
      goto LABEL_64;
    }
    v9 = 16;
  }
  else
  {
    v31 = a1;
    v38[0] = &wistd::__function::__func<_lambda_8b91c585b7835484d8ed00982d386965_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
    v38[1] = &v31;
    v38[13] = v38;
    v7 = wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
           &pszPathIn,
           v37);
    wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::~function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>(v37);
    if ( v7 < 0 )
    {
      v8 = 268;
      goto LABEL_7;
    }
    v6 = pszPathIn;
    v9 = 1;
  }
  ppszPathOut = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPathOut,
    0);
  v10 = PathAllocCombine(v6, L"*", v9, &ppszPathOut);
  v7 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x111,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
      (const char *)(unsigned int)v10,
      v30);
    goto LABEL_63;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (wchar_t *)FindFirstFileW(ppszPathOut, &FindFileData);
  v31 = FirstFileW;
  if ( (unsigned __int64)FirstFileW - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x115,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                  v12);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v31);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
    return LastError;
  }
  while ( 1 )
  {
    if ( (FindFileData.dwFileAttributes & 0x10) != 0
      && FindFileData.cFileName[0] == 46
      && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2]) )
    {
      goto LABEL_34;
    }
    v32 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v32,
      0);
    v13 = PathAllocCombine(v6, FindFileData.cFileName, 0x18u, &v32);
    v7 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x120,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
        (const char *)(unsigned int)v13,
        v30);
      goto LABEL_61;
    }
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      break;
    wil::TryCreateFileCanRecurseIntoDirectory(&hFile, v32, &FindFileData);
    if ( (char *)hFile - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( (FindFileData.dwFileAttributes & 0x400) == 0 )
      {
        v24 = GetLastError();
        if ( !v24 )
        {
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v32);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v31);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
          v7 = 0;
          goto LABEL_64;
        }
        v23 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x136,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                (const char *)v24,
                v30);
        goto LABEL_45;
      }
      if ( !RemoveDirectoryW(v32) )
      {
        v23 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x131,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                v15);
LABEL_45:
        v7 = v23;
        goto LABEL_22;
      }
    }
    else
    {
      v14 = wil::RemoveDirectoryRecursiveNoThrow(v32, a2 & 0xFFFFFFFE, hFile);
      v7 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12C,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
          (const char *)(unsigned int)v14,
          v30);
LABEL_22:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
        goto LABEL_61;
      }
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
LABEL_33:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v32);
LABEL_34:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
    {
      v19 = GetLastError();
      if ( v19 == 18 )
      {
        if ( (a2 & 1) != 0 )
          goto LABEL_59;
        if ( a3 == (void *)-1LL )
        {
          if ( !RemoveDirectoryW(v6) )
          {
            v21 = 381;
            goto LABEL_42;
          }
LABEL_59:
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v31);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
          return 0;
        }
        LODWORD(hFile) = 3;
        if ( SetFileInformationByHandle(a3, FileRenameInfoEx|FileDispositionInfo, &hFile, 4u) )
          goto LABEL_59;
        if ( GetLastError() != 5 )
        {
          FileInformation[0] = 1;
          if ( !SetFileInformationByHandle(a3, FileDispositionInfo, FileInformation, 1u) )
          {
            v21 = 369;
LABEL_42:
            v22 = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v21,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                    v20);
LABEL_43:
            v7 = v22;
            goto LABEL_62;
          }
          goto LABEL_59;
        }
        v26 = 5;
        v27 = 374;
      }
      else
      {
        if ( !v19 )
          goto LABEL_59;
        v26 = v19;
        v27 = 348;
      }
      v22 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v27,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
              (const char *)v26,
              v30);
      goto LABEL_43;
    }
  }
  if ( DeleteFileW(v32) )
    goto LABEL_33;
  if ( (a2 & 2) != 0 && GetLastError() == 5 )
  {
    FileAttributesW = GetFileAttributesW(v32);
    if ( (FileAttributesW & 1) == 0 )
    {
      v25 = 325;
      goto LABEL_50;
    }
    v18 = FileAttributesW & 0xFFFFFFFE;
    if ( !v18 )
      v18 = 128;
    SetFileAttributesW(v32, v18);
    if ( !DeleteFileW(v32) )
    {
      v25 = 336;
      goto LABEL_50;
    }
    goto LABEL_33;
  }
  v25 = 321;
LABEL_50:
  v7 = wil::details::in1diag3::Return_GetLastError(
         retaddr,
         (void *)v25,
         (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
         v16);
LABEL_61:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v32);
LABEL_62:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v31);
LABEL_63:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
LABEL_64:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1801481e8  push    rbp
0x1801481ea  push    rbx
0x1801481eb  push    rsi
0x1801481ec  push    rdi
0x1801481ed  push    r12
0x1801481ef  push    r14
0x1801481f1  push    r15
0x1801481f3  lea     rbp, [rsp-240h]
0x1801481fb  sub     rsp, 340h
0x180148202  mov     rax, cs:__security_cookie
0x180148209  xor     rax, rsp
0x18014820c  mov     [rbp+270h+var_40], rax
0x180148213  xor     r12d, r12d
0x180148216  mov     r14, r8
0x180148219  mov     r15d, edx
0x18014821c  mov     [rsp+370h+pszPathIn], r12
0x180148221  lea     rdx, asc_1803CA010; "\\\\?\\"
0x180148228  mov     rbx, rcx
0x18014822b  lea     r8d, [r12+4]; MaxCount
0x180148230  call    wcsncmp_0
0x180148235  test    eax, eax
0x180148237  jnz     short loc_180148280
0x180148239  or      r8, 0FFFFFFFFFFFFFFFFh
0x18014823d  lea     rcx, [rsp+370h+var_340]
0x180148242  mov     rdx, rbx
0x180148245  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18014824a  lea     rdx, [rsp+370h+var_340]
0x18014824f  lea     rcx, [rsp+370h+pszPathIn]
0x180148254  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180148259  lea     rcx, [rsp+370h+var_340]
0x18014825e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180148263  mov     rbx, [rsp+370h+pszPathIn]
0x180148268  test    rbx, rbx
0x18014826b  jnz     short loc_180148279
0x18014826d  mov     esi, 8007000Eh
0x180148272  mov     edx, 104h
0x180148277  jmp     short loc_1801482C8
0x180148279  mov     edi, 10h
0x18014827e  jmp     short loc_1801482ED
0x180148280  lea     rax, ??_7?$__func@V_lambda_8b91c585b7835484d8ed00982d386965_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8b91c585b7835484d8ed00982d386965_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x180148287  mov     [rsp+370h+var_340], rbx
0x18014828c  mov     [rsp+370h+var_308], rax
0x180148291  lea     rdx, [rsp+370h+var_310]
0x180148296  lea     rax, [rsp+370h+var_340]
0x18014829b  mov     [rsp+370h+var_300], rax
0x1801482a0  lea     rcx, [rsp+370h+pszPathIn]
0x1801482a5  lea     rax, [rsp+370h+var_308]
0x1801482aa  mov     [rbp+270h+var_2A0], rax
0x1801482ae  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)
0x1801482b3  lea     rcx, [rsp+370h+var_310]
0x1801482b8  mov     esi, eax
0x1801482ba  call    ??1?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEAA@XZ; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::~function<long (ushort *,unsigned __int64,unsigned __int64 *)>(void)
0x1801482bf  test    esi, esi
0x1801482c1  jns     short loc_1801482E3
0x1801482c3  mov     edx, 10Ch; void *
0x1801482c8  mov     rcx, [rbp+278h]; this
0x1801482cf  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1801482d6  mov     r9d, esi; char *
0x1801482d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801482de  jmp     loc_1801486CE
0x1801482e3  mov     rbx, [rsp+370h+pszPathIn]
0x1801482e8  mov     edi, 1
0x1801482ed  xor     edx, edx
0x1801482ef  mov     [rsp+370h+ppszPathOut], r12
0x1801482f4  lea     rcx, [rsp+370h+ppszPathOut]
0x1801482f9  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1801482fe  lea     r9, [rsp+370h+ppszPathOut]; ppszPathOut
0x180148303  mov     r8d, edi; dwFlags
0x180148306  lea     rdx, pszMore; "*"
0x18014830d  mov     rcx, rbx; pszPathIn
0x180148310  call    cs:__imp_PathAllocCombine
0x180148316  mov     esi, eax
0x180148318  test    eax, eax
0x18014831a  jns     short loc_18014833C
0x18014831c  mov     rcx, [rbp+278h]; this
0x180148323  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18014832a  mov     r9d, eax; char *
0x18014832d  mov     edx, 111h; void *
0x180148332  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180148337  jmp     loc_1801486C4
0x18014833c  xor     edx, edx; Val
0x18014833e  lea     rcx, [rbp+270h+FindFileData]; void *
0x180148342  mov     r8d, 250h; Size
0x180148348  call    memset_0
0x18014834d  mov     rcx, [rsp+370h+ppszPathOut]; lpFileName
0x180148352  lea     rdx, [rbp+270h+FindFileData]; lpFindFileData
0x180148356  call    cs:__imp_FindFirstFileW
0x18014835c  mov     rdi, rax
0x18014835f  mov     [rsp+370h+var_340], rax
0x180148364  dec     rax
0x180148367  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18014836b  ja      loc_1801486DC
0x180148371  test    byte ptr [rbp+270h+FindFileData.dwFileAttributes], 10h
0x180148375  jz      short loc_18014839C
0x180148377  cmp     [rbp+270h+FindFileData.cFileName], 2Eh ; '.'
0x18014837c  jnz     short loc_18014839C
0x18014837e  movzx   eax, [rbp+270h+FindFileData.cFileName+2]
0x180148382  test    ax, ax
0x180148385  jz      loc_1801484D7
0x18014838b  cmp     ax, 2Eh ; '.'
0x18014838f  jnz     short loc_18014839C
0x180148391  cmp     [rbp+270h+FindFileData.cFileName+4], r12w
0x180148396  jz      loc_1801484D7
0x18014839c  xor     edx, edx
0x18014839e  mov     [rsp+370h+var_338], r12
0x1801483a3  lea     rcx, [rsp+370h+var_338]
0x1801483a8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1801483ad  lea     r9, [rsp+370h+var_338]; ppszPathOut
0x1801483b2  mov     r8d, 18h; dwFlags
0x1801483b8  lea     rdx, [rbp+270h+FindFileData.cFileName]; pszMore
0x1801483bc  mov     rcx, rbx; pszPathIn
0x1801483bf  call    cs:__imp_PathAllocCombine
0x1801483c5  mov     esi, eax
0x1801483c7  test    eax, eax
0x1801483c9  js      loc_180148695
0x1801483cf  test    byte ptr [rbp+270h+FindFileData.dwFileAttributes], 10h
0x1801483d3  jz      loc_180148467
0x1801483d9  mov     rdx, [rsp+370h+var_338]
0x1801483de  lea     r8, [rbp+270h+FindFileData]
0x1801483e2  lea     rcx, [rsp+370h+hFile]
0x1801483e7  call    ?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z; wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)
0x1801483ec  mov     r8, [rsp+370h+hFile]
0x1801483f1  lea     rax, [r8-1]
0x1801483f5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801483f9  ja      short loc_18014843B
0x1801483fb  mov     rcx, [rsp+370h+var_338]
0x180148400  mov     edx, r15d
0x180148403  and     edx, 0FFFFFFFEh
0x180148406  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x18014840b  mov     esi, eax
0x18014840d  test    eax, eax
0x18014840f  jns     short loc_18014845B
0x180148411  mov     rcx, [rbp+278h]; this
0x180148418  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18014841f  mov     r9d, eax; char *
0x180148422  mov     edx, 12Ch; void *
0x180148427  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014842c  lea     rcx, [rsp+370h+hFile]
0x180148431  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180148436  jmp     loc_1801486B0
0x18014843b  test    [rbp+270h+FindFileData.dwFileAttributes], 400h
0x180148442  jz      loc_1801485A4
0x180148448  mov     rcx, [rsp+370h+var_338]; lpPathName
0x18014844d  call    cs:__imp_RemoveDirectoryW
0x180148453  test    eax, eax
0x180148455  jz      loc_180148585
0x18014845b  lea     rcx, [rsp+370h+hFile]
0x180148460  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180148465  jmp     short loc_1801484CD
0x180148467  mov     rcx, [rsp+370h+var_338]; lpFileName
0x18014846c  call    cs:__imp_DeleteFileW
0x180148472  test    eax, eax
0x180148474  jnz     short loc_1801484CD
0x180148476  test    r15b, 2
0x18014847a  jz      loc_180148621
0x180148480  call    cs:__imp_GetLastError
0x180148486  cmp     eax, 5
0x180148489  jnz     loc_180148621
0x18014848f  mov     rcx, [rsp+370h+var_338]; lpFileName
0x180148494  call    cs:__imp_GetFileAttributesW
0x18014849a  test    al, 1
0x18014849c  jz      loc_18014861A
0x1801484a2  and     eax, 0FFFFFFFEh
0x1801484a5  mov     ecx, 80h
0x1801484aa  cmovz   eax, ecx
0x1801484ad  mov     rcx, [rsp+370h+var_338]; lpFileName
0x1801484b2  mov     edx, eax; dwFileAttributes
0x1801484b4  call    cs:__imp_SetFileAttributesW
0x1801484ba  mov     rcx, [rsp+370h+var_338]; lpFileName
0x1801484bf  call    cs:__imp_DeleteFileW
0x1801484c5  test    eax, eax
0x1801484c7  jz      loc_1801485FB
0x1801484cd  lea     rcx, [rsp+370h+var_338]
0x1801484d2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801484d7  lea     rdx, [rbp+270h+FindFileData]; lpFindFileData
0x1801484db  mov     rcx, rdi; hFindFile
0x1801484de  call    cs:__imp_FindNextFileW
0x1801484e4  test    eax, eax
0x1801484e6  jnz     loc_180148371
0x1801484ec  call    cs:__imp_GetLastError
0x1801484f2  cmp     eax, 12h
0x1801484f5  jnz     loc_180148662
0x1801484fb  test    r15b, 1
0x1801484ff  jnz     loc_180148670
0x180148505  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180148509  jz      loc_18014864B
0x18014850f  lea     ebx, [rax-0Eh]
0x180148512  mov     dword ptr [rsp+370h+hFile], 3
0x18014851a  mov     r9d, ebx; dwBufferSize
0x18014851d  lea     r8, [rsp+370h+hFile]; lpFileInformation
0x180148522  lea     edx, [rax+3]; FileInformationClass
0x180148525  mov     rcx, r14; hFile
0x180148528  call    cs:__imp_SetFileInformationByHandle
0x18014852e  test    eax, eax
0x180148530  jnz     loc_180148670
0x180148536  call    cs:__imp_GetLastError
0x18014853c  cmp     eax, 5
0x18014853f  jz      loc_180148628
0x180148545  lea     r9d, [rbx-3]; dwBufferSize
0x180148549  mov     [rsp+370h+FileInformation], 1
0x18014854e  lea     r8, [rsp+370h+FileInformation]; lpFileInformation
0x180148553  mov     edx, ebx; FileInformationClass
0x180148555  mov     rcx, r14; hFile
0x180148558  call    cs:__imp_SetFileInformationByHandle
0x18014855e  test    eax, eax
0x180148560  jnz     loc_180148670
0x180148566  mov     edx, 171h; void *
0x18014856b  mov     rcx, [rbp+278h]; this
0x180148572  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180148579  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18014857e  mov     esi, eax
0x180148580  jmp     loc_1801486BA
0x180148585  mov     rcx, [rbp+278h]; this
0x18014858c  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180148593  mov     edx, 131h; void *
0x180148598  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18014859d  mov     esi, eax
0x18014859f  jmp     loc_18014842C
0x1801485a4  call    cs:__imp_GetLastError
0x1801485aa  test    eax, eax
0x1801485ac  jz      short loc_1801485CB
0x1801485ae  mov     rcx, [rbp+278h]; this
0x1801485b5  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1801485bc  mov     r9d, eax; char *
0x1801485bf  mov     edx, 136h; void *
0x1801485c4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801485c9  jmp     short loc_18014859D
0x1801485cb  lea     rcx, [rsp+370h+hFile]
0x1801485d0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801485d5  lea     rcx, [rsp+370h+var_338]
0x1801485da  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801485df  lea     rcx, [rsp+370h+var_340]
0x1801485e4  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1801485e9  lea     rcx, [rsp+370h+ppszPathOut]
0x1801485ee  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801485f3  mov     esi, r12d
0x1801485f6  jmp     loc_1801486CE
0x1801485fb  mov     edx, 150h; void *
0x180148600  mov     rcx, [rbp+278h]; this
0x180148607  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18014860e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180148613  mov     esi, eax
0x180148615  jmp     loc_1801486B0
0x18014861a  mov     edx, 145h
0x18014861f  jmp     short loc_180148600
0x180148621  mov     edx, 141h
0x180148626  jmp     short loc_180148600
0x180148628  mov     r9d, 5; char *
0x18014862e  mov     edx, 176h; void *
0x180148633  mov     rcx, [rbp+278h]; this
0x18014863a  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180148641  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180148646  jmp     loc_18014857E
0x18014864b  mov     rcx, rbx; lpPathName
0x18014864e  call    cs:__imp_RemoveDirectoryW
0x180148654  test    eax, eax
0x180148656  jnz     short loc_180148670
0x180148658  mov     edx, 17Dh
0x18014865d  jmp     loc_18014856B
0x180148662  test    eax, eax
0x180148664  jz      short loc_180148670
0x180148666  mov     r9d, eax
0x180148669  mov     edx, 15Ch
0x18014866e  jmp     short loc_180148633
0x180148670  lea     rcx, [rsp+370h+var_340]
0x180148675  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18014867a  lea     rcx, [rsp+370h+ppszPathOut]
0x18014867f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180148684  lea     rcx, [rsp+370h+pszPathIn]
0x180148689  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18014868e  xor     eax, eax
0x180148690  jmp     loc_180148716
0x180148695  mov     rcx, [rbp+278h]; this
0x18014869c  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1801486a3  mov     r9d, eax; char *
0x1801486a6  mov     edx, 120h; void *
0x1801486ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801486b0  lea     rcx, [rsp+370h+var_338]
0x1801486b5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801486ba  lea     rcx, [rsp+370h+var_340]
0x1801486bf  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1801486c4  lea     rcx, [rsp+370h+ppszPathOut]
0x1801486c9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801486ce  lea     rcx, [rsp+370h+pszPathIn]
0x1801486d3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801486d8  mov     eax, esi
0x1801486da  jmp     short loc_180148716
0x1801486dc  mov     rcx, [rbp+278h]; this
0x1801486e3  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1801486ea  mov     edx, 115h; void *
0x1801486ef  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801486f4  lea     rcx, [rsp+370h+var_340]
0x1801486f9  mov     ebx, eax
0x1801486fb  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180148700  lea     rcx, [rsp+370h+ppszPathOut]
0x180148705  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18014870a  lea     rcx, [rsp+370h+pszPathIn]
0x18014870f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180148714  mov     eax, ebx
0x180148716  mov     rcx, [rbp+270h+var_40]
  ... truncated ...
```

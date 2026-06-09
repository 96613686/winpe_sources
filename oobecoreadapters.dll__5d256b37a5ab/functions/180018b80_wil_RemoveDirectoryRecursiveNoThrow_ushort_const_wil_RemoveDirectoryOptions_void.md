# wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)

- ea: `0x180018b80`
- end: `0x1800190cf`
- name: `?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z`
- size: `1359`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800179d0`
- `0x180018b80`

## callees

- `0x180002b60`
- `0x1800036e4`
- `0x1800076b4`
- `0x1800076d4`
- `0x1800097f4`
- `0x18000b1ac`
- `0x180015d84`
- `0x180016b4c`
- `0x180017598`
- `0x1800175bc`
- `0x1800175e0`
- `0x180017604`
- `0x180018b80`
- `0x1800190d8`
- `0x1800193ac`
- `0x18006ab94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018ece`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018ece`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f3c`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180018ca8`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180018d57`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180018ca8`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180018d57`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180018cee`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180018cee`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180018de5`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180018fe6`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180018de5`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180018fe6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180018e04`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180018e57`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180018e04`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180018e57`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180018e2c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180018e2c`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180018e76`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180018e76`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180018ec0`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180018ef0`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180018ec0`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180018ef0`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180018e4c`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180018e4c`

## string_xrefs

- `0x180018c67`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180018cbb`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180018db0`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180018f0a`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180018f24`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180018f4d`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180018f9f`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180018fd2`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180019034`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18001907b`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

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
  _WIN32_FIND_DATAW FindFileData; // [rsp+E0h] [rbp-20h] BYREF
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
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
        (const char *)(unsigned int)v7,
        v30);
      goto LABEL_64;
    }
    v9 = 16;
  }
  else
  {
    v31 = a1;
    v38[0] = &wistd::__function::__func<_lambda_dfced21692aadc2a556e46caeccd40ea_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
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
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
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
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
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
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
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
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                (const char *)v24,
                v30);
        goto LABEL_45;
      }
      if ( !RemoveDirectoryW(v32) )
      {
        v23 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x131,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
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
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
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
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
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
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
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
         (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
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
0x180018b80  push    rbp
0x180018b82  push    rbx
0x180018b83  push    rsi
0x180018b84  push    rdi
0x180018b85  push    r12
0x180018b87  push    r14
0x180018b89  push    r15
0x180018b8b  lea     rbp, [rsp-240h]
0x180018b93  sub     rsp, 340h
0x180018b9a  mov     rax, cs:__security_cookie
0x180018ba1  xor     rax, rsp
0x180018ba4  mov     [rbp+270h+var_40], rax
0x180018bab  xor     r12d, r12d
0x180018bae  mov     r14, r8
0x180018bb1  mov     r15d, edx
0x180018bb4  mov     [rsp+370h+pszPathIn], r12
0x180018bb9  lea     rdx, String2; "\\\\?\\"
0x180018bc0  mov     rbx, rcx
0x180018bc3  lea     r8d, [r12+4]; MaxCount
0x180018bc8  call    wcsncmp_0
0x180018bcd  test    eax, eax
0x180018bcf  jnz     short loc_180018C18
0x180018bd1  or      r8, 0FFFFFFFFFFFFFFFFh
0x180018bd5  lea     rcx, [rsp+370h+var_340]
0x180018bda  mov     rdx, rbx
0x180018bdd  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180018be2  lea     rdx, [rsp+370h+var_340]
0x180018be7  lea     rcx, [rsp+370h+pszPathIn]
0x180018bec  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180018bf1  lea     rcx, [rsp+370h+var_340]
0x180018bf6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180018bfb  mov     rbx, [rsp+370h+pszPathIn]
0x180018c00  test    rbx, rbx
0x180018c03  jnz     short loc_180018C11
0x180018c05  mov     esi, 8007000Eh
0x180018c0a  mov     edx, 104h
0x180018c0f  jmp     short loc_180018C60
0x180018c11  mov     edi, 10h
0x180018c16  jmp     short loc_180018C85
0x180018c18  lea     rax, ??_7?$__func@V_lambda_dfced21692aadc2a556e46caeccd40ea_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_dfced21692aadc2a556e46caeccd40ea_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x180018c1f  mov     [rsp+370h+var_340], rbx
0x180018c24  mov     [rsp+370h+var_308], rax
0x180018c29  lea     rdx, [rsp+370h+var_310]
0x180018c2e  lea     rax, [rsp+370h+var_340]
0x180018c33  mov     [rsp+370h+var_300], rax
0x180018c38  lea     rcx, [rsp+370h+pszPathIn]
0x180018c3d  lea     rax, [rsp+370h+var_308]
0x180018c42  mov     [rbp+270h+var_2A0], rax
0x180018c46  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)
0x180018c4b  lea     rcx, [rsp+370h+var_310]
0x180018c50  mov     esi, eax
0x180018c52  call    ??1?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEAA@XZ; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::~function<long (ushort *,unsigned __int64,unsigned __int64 *)>(void)
0x180018c57  test    esi, esi
0x180018c59  jns     short loc_180018C7B
0x180018c5b  mov     edx, 10Ch; void *
0x180018c60  mov     rcx, [rbp+278h]; this
0x180018c67  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180018c6e  mov     r9d, esi; char *
0x180018c71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018c76  jmp     loc_180019066
0x180018c7b  mov     rbx, [rsp+370h+pszPathIn]
0x180018c80  mov     edi, 1
0x180018c85  xor     edx, edx
0x180018c87  mov     [rsp+370h+ppszPathOut], r12
0x180018c8c  lea     rcx, [rsp+370h+ppszPathOut]
0x180018c91  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180018c96  lea     r9, [rsp+370h+ppszPathOut]; ppszPathOut
0x180018c9b  mov     r8d, edi; dwFlags
0x180018c9e  lea     rdx, pszMore; "*"
0x180018ca5  mov     rcx, rbx; pszPathIn
0x180018ca8  call    cs:__imp_PathAllocCombine
0x180018cae  mov     esi, eax
0x180018cb0  test    eax, eax
0x180018cb2  jns     short loc_180018CD4
0x180018cb4  mov     rcx, [rbp+278h]; this
0x180018cbb  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180018cc2  mov     r9d, eax; char *
0x180018cc5  mov     edx, 111h; void *
0x180018cca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018ccf  jmp     loc_18001905C
0x180018cd4  xor     edx, edx; Val
0x180018cd6  lea     rcx, [rbp+270h+FindFileData]; void *
0x180018cda  mov     r8d, 250h; Size
0x180018ce0  call    memset_0
0x180018ce5  mov     rcx, [rsp+370h+ppszPathOut]; lpFileName
0x180018cea  lea     rdx, [rbp+270h+FindFileData]; lpFindFileData
0x180018cee  call    cs:__imp_FindFirstFileW
0x180018cf4  mov     rdi, rax
0x180018cf7  mov     [rsp+370h+var_340], rax
0x180018cfc  dec     rax
0x180018cff  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180018d03  ja      loc_180019074
0x180018d09  test    byte ptr [rbp+270h+FindFileData.dwFileAttributes], 10h
0x180018d0d  jz      short loc_180018D34
0x180018d0f  cmp     [rbp+270h+FindFileData.cFileName], 2Eh ; '.'
0x180018d14  jnz     short loc_180018D34
0x180018d16  movzx   eax, [rbp+270h+FindFileData.cFileName+2]
0x180018d1a  test    ax, ax
0x180018d1d  jz      loc_180018E6F
0x180018d23  cmp     ax, 2Eh ; '.'
0x180018d27  jnz     short loc_180018D34
0x180018d29  cmp     [rbp+270h+FindFileData.cFileName+4], r12w
0x180018d2e  jz      loc_180018E6F
0x180018d34  xor     edx, edx
0x180018d36  mov     [rsp+370h+var_338], r12
0x180018d3b  lea     rcx, [rsp+370h+var_338]
0x180018d40  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180018d45  lea     r9, [rsp+370h+var_338]; ppszPathOut
0x180018d4a  mov     r8d, 18h; dwFlags
0x180018d50  lea     rdx, [rbp+270h+FindFileData.cFileName]; pszMore
0x180018d54  mov     rcx, rbx; pszPathIn
0x180018d57  call    cs:__imp_PathAllocCombine
0x180018d5d  mov     esi, eax
0x180018d5f  test    eax, eax
0x180018d61  js      loc_18001902D
0x180018d67  test    byte ptr [rbp+270h+FindFileData.dwFileAttributes], 10h
0x180018d6b  jz      loc_180018DFF
0x180018d71  mov     rdx, [rsp+370h+var_338]
0x180018d76  lea     r8, [rbp+270h+FindFileData]
0x180018d7a  lea     rcx, [rsp+370h+hFile]
0x180018d7f  call    ?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z; wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)
0x180018d84  mov     r8, [rsp+370h+hFile]
0x180018d89  lea     rax, [r8-1]
0x180018d8d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180018d91  ja      short loc_180018DD3
0x180018d93  mov     rcx, [rsp+370h+var_338]
0x180018d98  mov     edx, r15d
0x180018d9b  and     edx, 0FFFFFFFEh
0x180018d9e  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x180018da3  mov     esi, eax
0x180018da5  test    eax, eax
0x180018da7  jns     short loc_180018DF3
0x180018da9  mov     rcx, [rbp+278h]; this
0x180018db0  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180018db7  mov     r9d, eax; char *
0x180018dba  mov     edx, 12Ch; void *
0x180018dbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018dc4  lea     rcx, [rsp+370h+hFile]
0x180018dc9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180018dce  jmp     loc_180019048
0x180018dd3  test    [rbp+270h+FindFileData.dwFileAttributes], 400h
0x180018dda  jz      loc_180018F3C
0x180018de0  mov     rcx, [rsp+370h+var_338]; lpPathName
0x180018de5  call    cs:__imp_RemoveDirectoryW
0x180018deb  test    eax, eax
0x180018ded  jz      loc_180018F1D
0x180018df3  lea     rcx, [rsp+370h+hFile]
0x180018df8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180018dfd  jmp     short loc_180018E65
0x180018dff  mov     rcx, [rsp+370h+var_338]; lpFileName
0x180018e04  call    cs:__imp_DeleteFileW
0x180018e0a  test    eax, eax
0x180018e0c  jnz     short loc_180018E65
0x180018e0e  test    r15b, 2
0x180018e12  jz      loc_180018FB9
0x180018e18  call    cs:__imp_GetLastError
0x180018e1e  cmp     eax, 5
0x180018e21  jnz     loc_180018FB9
0x180018e27  mov     rcx, [rsp+370h+var_338]; lpFileName
0x180018e2c  call    cs:__imp_GetFileAttributesW
0x180018e32  test    al, 1
0x180018e34  jz      loc_180018FB2
0x180018e3a  and     eax, 0FFFFFFFEh
0x180018e3d  mov     ecx, 80h
0x180018e42  cmovz   eax, ecx
0x180018e45  mov     rcx, [rsp+370h+var_338]; lpFileName
0x180018e4a  mov     edx, eax; dwFileAttributes
0x180018e4c  call    cs:__imp_SetFileAttributesW
0x180018e52  mov     rcx, [rsp+370h+var_338]; lpFileName
0x180018e57  call    cs:__imp_DeleteFileW
0x180018e5d  test    eax, eax
0x180018e5f  jz      loc_180018F93
0x180018e65  lea     rcx, [rsp+370h+var_338]
0x180018e6a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180018e6f  lea     rdx, [rbp+270h+FindFileData]; lpFindFileData
0x180018e73  mov     rcx, rdi; hFindFile
0x180018e76  call    cs:__imp_FindNextFileW
0x180018e7c  test    eax, eax
0x180018e7e  jnz     loc_180018D09
0x180018e84  call    cs:__imp_GetLastError
0x180018e8a  cmp     eax, 12h
0x180018e8d  jnz     loc_180018FFA
0x180018e93  test    r15b, 1
0x180018e97  jnz     loc_180019008
0x180018e9d  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180018ea1  jz      loc_180018FE3
0x180018ea7  lea     ebx, [rax-0Eh]
0x180018eaa  mov     dword ptr [rsp+370h+hFile], 3
0x180018eb2  mov     r9d, ebx; dwBufferSize
0x180018eb5  lea     r8, [rsp+370h+hFile]; lpFileInformation
0x180018eba  lea     edx, [rax+3]; FileInformationClass
0x180018ebd  mov     rcx, r14; hFile
0x180018ec0  call    cs:__imp_SetFileInformationByHandle
0x180018ec6  test    eax, eax
0x180018ec8  jnz     loc_180019008
0x180018ece  call    cs:__imp_GetLastError
0x180018ed4  cmp     eax, 5
0x180018ed7  jz      loc_180018FC0
0x180018edd  lea     r9d, [rbx-3]; dwBufferSize
0x180018ee1  mov     [rsp+370h+FileInformation], 1
0x180018ee6  lea     r8, [rsp+370h+FileInformation]; lpFileInformation
0x180018eeb  mov     edx, ebx; FileInformationClass
0x180018eed  mov     rcx, r14; hFile
0x180018ef0  call    cs:__imp_SetFileInformationByHandle
0x180018ef6  test    eax, eax
0x180018ef8  jnz     loc_180019008
0x180018efe  mov     edx, 171h; void *
0x180018f03  mov     rcx, [rbp+278h]; this
0x180018f0a  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180018f11  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180018f16  mov     esi, eax
0x180018f18  jmp     loc_180019052
0x180018f1d  mov     rcx, [rbp+278h]; this
0x180018f24  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180018f2b  mov     edx, 131h; void *
0x180018f30  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180018f35  mov     esi, eax
0x180018f37  jmp     loc_180018DC4
0x180018f3c  call    cs:__imp_GetLastError
0x180018f42  test    eax, eax
0x180018f44  jz      short loc_180018F63
0x180018f46  mov     rcx, [rbp+278h]; this
0x180018f4d  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180018f54  mov     r9d, eax; char *
0x180018f57  mov     edx, 136h; void *
0x180018f5c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180018f61  jmp     short loc_180018F35
0x180018f63  lea     rcx, [rsp+370h+hFile]
0x180018f68  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180018f6d  lea     rcx, [rsp+370h+var_338]
0x180018f72  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180018f77  lea     rcx, [rsp+370h+var_340]
0x180018f7c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180018f81  lea     rcx, [rsp+370h+ppszPathOut]
0x180018f86  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180018f8b  mov     esi, r12d
0x180018f8e  jmp     loc_180019066
0x180018f93  mov     edx, 150h; void *
0x180018f98  mov     rcx, [rbp+278h]; this
0x180018f9f  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180018fa6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180018fab  mov     esi, eax
0x180018fad  jmp     loc_180019048
0x180018fb2  mov     edx, 145h
0x180018fb7  jmp     short loc_180018F98
0x180018fb9  mov     edx, 141h
0x180018fbe  jmp     short loc_180018F98
0x180018fc0  mov     r9d, 5; char *
0x180018fc6  mov     edx, 176h; void *
0x180018fcb  mov     rcx, [rbp+278h]; this
0x180018fd2  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180018fd9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180018fde  jmp     loc_180018F16
0x180018fe3  mov     rcx, rbx; lpPathName
0x180018fe6  call    cs:__imp_RemoveDirectoryW
0x180018fec  test    eax, eax
0x180018fee  jnz     short loc_180019008
0x180018ff0  mov     edx, 17Dh
0x180018ff5  jmp     loc_180018F03
0x180018ffa  test    eax, eax
0x180018ffc  jz      short loc_180019008
0x180018ffe  mov     r9d, eax
0x180019001  mov     edx, 15Ch
0x180019006  jmp     short loc_180018FCB
0x180019008  lea     rcx, [rsp+370h+var_340]
0x18001900d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180019012  lea     rcx, [rsp+370h+ppszPathOut]
0x180019017  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001901c  lea     rcx, [rsp+370h+pszPathIn]
0x180019021  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180019026  xor     eax, eax
0x180019028  jmp     loc_1800190AE
0x18001902d  mov     rcx, [rbp+278h]; this
0x180019034  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001903b  mov     r9d, eax; char *
0x18001903e  mov     edx, 120h; void *
0x180019043  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019048  lea     rcx, [rsp+370h+var_338]
0x18001904d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180019052  lea     rcx, [rsp+370h+var_340]
0x180019057  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18001905c  lea     rcx, [rsp+370h+ppszPathOut]
0x180019061  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180019066  lea     rcx, [rsp+370h+pszPathIn]
0x18001906b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180019070  mov     eax, esi
0x180019072  jmp     short loc_1800190AE
0x180019074  mov     rcx, [rbp+278h]; this
0x18001907b  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180019082  mov     edx, 115h; void *
0x180019087  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001908c  lea     rcx, [rsp+370h+var_340]
0x180019091  mov     ebx, eax
0x180019093  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180019098  lea     rcx, [rsp+370h+ppszPathOut]
0x18001909d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800190a2  lea     rcx, [rsp+370h+pszPathIn]
0x1800190a7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800190ac  mov     eax, ebx
0x1800190ae  mov     rcx, [rbp+270h+var_40]
  ... truncated ...
```

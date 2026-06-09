# wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)

- ea: `0x18002c680`
- end: `0x18002cbcf`
- name: `?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z`
- size: `1359`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002c680`
- `0x180067c90`

## callees

- `0x180010fcc`
- `0x1800118f8`
- `0x180011938`
- `0x180017de4`
- `0x18001ac7c`
- `0x18002c680`
- `0x18002cbd8`
- `0x18002e1a0`
- `0x18002ec8c`
- `0x180032a04`
- `0x180035988`
- `0x18005f41c`
- `0x1800678b0`
- `0x180067ae8`
- `0x180067b0c`
- `0x180078040`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c918`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c9ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ca3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c918`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c9ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ca3c`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18002c9c0`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18002c9f0`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18002c9c0`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18002c9f0`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002c94c`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002c94c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002c92c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002c92c`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18002c8e5`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18002cae6`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18002c8e5`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18002cae6`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002c976`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002c976`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002c7ee`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002c7ee`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002c904`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002c957`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002c904`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002c957`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18002c7a8`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18002c857`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18002c7a8`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18002c857`

## string_xrefs

- `0x18002c767`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18002c7bb`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18002c8b0`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18002ca0a`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18002ca24`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18002ca4d`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18002ca9f`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18002cad2`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18002cb34`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18002cb7b`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

## pseudocode

```c
__int64 __fastcall wil::RemoveDirectoryRecursiveNoThrow(char *a1, int a2, void *a3)
{
  const char *v6; // r9
  const WCHAR *v7; // rbx
  int v8; // esi
  __int64 v9; // rdx
  ULONG v10; // edi
  HRESULT v11; // eax
  char *FirstFileW; // rdi
  const char *v13; // r9
  HRESULT v14; // eax
  int v15; // eax
  const char *v16; // r9
  const char *v17; // r9
  DWORD FileAttributesW; // eax
  DWORD v19; // eax
  DWORD v20; // eax
  const char *v21; // r9
  __int64 v22; // rdx
  int v23; // eax
  int v24; // eax
  DWORD v25; // eax
  __int64 v26; // rdx
  __int64 v27; // r9
  __int64 v28; // rdx
  unsigned int LastError; // ebx
  unsigned int v31; // [rsp+20h] [rbp-E0h]
  char *v32; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR v33; // [rsp+38h] [rbp-C8h] BYREF
  PWSTR ppszPathOut; // [rsp+40h] [rbp-C0h] BYREF
  char FileInformation[8]; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hFile; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR pszPathIn; // [rsp+58h] [rbp-A8h] BYREF
  char v38[8]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v39[15]; // [rsp+68h] [rbp-98h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+378h] [rbp+278h]

  pszPathIn = 0;
  if ( !wcsncmp_0((const wchar_t *)a1, L"\\\\?\\", 4u) )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v32,
      a1,
      0xFFFFFFFFFFFFFFFFuLL,
      v6);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &pszPathIn,
      &v32);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v32);
    v7 = pszPathIn;
    if ( !pszPathIn )
    {
      v8 = -2147024882;
      v9 = 260;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
        (const char *)(unsigned int)v8,
        v31);
      goto LABEL_64;
    }
    v10 = 16;
  }
  else
  {
    v32 = a1;
    v39[0] = &wistd::__function::__func<_lambda_dfced21692aadc2a556e46caeccd40ea_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
    v39[1] = &v32;
    v39[13] = v39;
    v8 = wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
           (__int64)&pszPathIn,
           (__int64)v38);
    wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::~function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>(v38);
    if ( v8 < 0 )
    {
      v9 = 268;
      goto LABEL_7;
    }
    v7 = pszPathIn;
    v10 = 1;
  }
  ppszPathOut = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPathOut,
    0);
  v11 = PathAllocCombine(v7, L"*", v10, &ppszPathOut);
  v8 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x111,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
      (const char *)(unsigned int)v11,
      v31);
    goto LABEL_63;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (char *)FindFirstFileW(ppszPathOut, &FindFileData);
  v32 = FirstFileW;
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x115,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                  v13);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v32);
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
    v33 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v33,
      0);
    v14 = PathAllocCombine(v7, FindFileData.cFileName, 0x18u, &v33);
    v8 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x120,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
        (const char *)(unsigned int)v14,
        v31);
      goto LABEL_61;
    }
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      break;
    wil::TryCreateFileCanRecurseIntoDirectory(&hFile, v33, &FindFileData);
    if ( (char *)hFile - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( (FindFileData.dwFileAttributes & 0x400) == 0 )
      {
        v25 = GetLastError();
        if ( !v25 )
        {
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v32);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
          v8 = 0;
          goto LABEL_64;
        }
        v24 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x136,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                (const char *)v25,
                v31);
        goto LABEL_45;
      }
      if ( !RemoveDirectoryW(v33) )
      {
        v24 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x131,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                v16);
LABEL_45:
        v8 = v24;
        goto LABEL_22;
      }
    }
    else
    {
      v15 = wil::RemoveDirectoryRecursiveNoThrow(v33, a2 & 0xFFFFFFFE, hFile);
      v8 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12C,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
          (const char *)(unsigned int)v15,
          v31);
LABEL_22:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
        goto LABEL_61;
      }
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
LABEL_33:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
LABEL_34:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
    {
      v20 = GetLastError();
      if ( v20 == 18 )
      {
        if ( (a2 & 1) != 0 )
          goto LABEL_59;
        if ( a3 == (void *)-1LL )
        {
          if ( !RemoveDirectoryW(v7) )
          {
            v22 = 381;
            goto LABEL_42;
          }
LABEL_59:
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v32);
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
            v22 = 369;
LABEL_42:
            v23 = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v22,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                    v21);
LABEL_43:
            v8 = v23;
            goto LABEL_62;
          }
          goto LABEL_59;
        }
        v27 = 5;
        v28 = 374;
      }
      else
      {
        if ( !v20 )
          goto LABEL_59;
        v27 = v20;
        v28 = 348;
      }
      v23 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v28,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
              (const char *)v27,
              v31);
      goto LABEL_43;
    }
  }
  if ( DeleteFileW(v33) )
    goto LABEL_33;
  if ( (a2 & 2) != 0 && GetLastError() == 5 )
  {
    FileAttributesW = GetFileAttributesW(v33);
    if ( (FileAttributesW & 1) == 0 )
    {
      v26 = 325;
      goto LABEL_50;
    }
    v19 = FileAttributesW & 0xFFFFFFFE;
    if ( !v19 )
      v19 = 128;
    SetFileAttributesW(v33, v19);
    if ( !DeleteFileW(v33) )
    {
      v26 = 336;
      goto LABEL_50;
    }
    goto LABEL_33;
  }
  v26 = 321;
LABEL_50:
  v8 = wil::details::in1diag3::Return_GetLastError(
         retaddr,
         (void *)v26,
         (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
         v17);
LABEL_61:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
LABEL_62:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v32);
LABEL_63:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
LABEL_64:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002c680  push    rbp
0x18002c682  push    rbx
0x18002c683  push    rsi
0x18002c684  push    rdi
0x18002c685  push    r12
0x18002c687  push    r14
0x18002c689  push    r15
0x18002c68b  lea     rbp, [rsp-240h]
0x18002c693  sub     rsp, 340h
0x18002c69a  mov     rax, cs:__security_cookie
0x18002c6a1  xor     rax, rsp
0x18002c6a4  mov     [rbp+270h+var_40], rax
0x18002c6ab  xor     r12d, r12d
0x18002c6ae  mov     r14, r8
0x18002c6b1  mov     r15d, edx
0x18002c6b4  mov     [rsp+370h+pszPathIn], r12
0x18002c6b9  lea     rdx, asc_18009BEF0; "\\\\?\\"
0x18002c6c0  mov     rbx, rcx
0x18002c6c3  lea     r8d, [r12+4]; MaxCount
0x18002c6c8  call    wcsncmp_0
0x18002c6cd  test    eax, eax
0x18002c6cf  jnz     short loc_18002C718
0x18002c6d1  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002c6d5  lea     rcx, [rsp+370h+var_340]
0x18002c6da  mov     rdx, rbx
0x18002c6dd  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002c6e2  lea     rdx, [rsp+370h+var_340]
0x18002c6e7  lea     rcx, [rsp+370h+pszPathIn]
0x18002c6ec  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18002c6f1  lea     rcx, [rsp+370h+var_340]
0x18002c6f6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c6fb  mov     rbx, [rsp+370h+pszPathIn]
0x18002c700  test    rbx, rbx
0x18002c703  jnz     short loc_18002C711
0x18002c705  mov     esi, 8007000Eh
0x18002c70a  mov     edx, 104h
0x18002c70f  jmp     short loc_18002C760
0x18002c711  mov     edi, 10h
0x18002c716  jmp     short loc_18002C785
0x18002c718  lea     rax, ??_7?$__func@V_lambda_dfced21692aadc2a556e46caeccd40ea_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_dfced21692aadc2a556e46caeccd40ea_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x18002c71f  mov     [rsp+370h+var_340], rbx
0x18002c724  mov     [rsp+370h+var_308], rax
0x18002c729  lea     rdx, [rsp+370h+var_310]
0x18002c72e  lea     rax, [rsp+370h+var_340]
0x18002c733  mov     [rsp+370h+var_300], rax
0x18002c738  lea     rcx, [rsp+370h+pszPathIn]
0x18002c73d  lea     rax, [rsp+370h+var_308]
0x18002c742  mov     [rbp+270h+var_2A0], rax
0x18002c746  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)
0x18002c74b  lea     rcx, [rsp+370h+var_310]
0x18002c750  mov     esi, eax
0x18002c752  call    ??1?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEAA@XZ; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::~function<long (ushort *,unsigned __int64,unsigned __int64 *)>(void)
0x18002c757  test    esi, esi
0x18002c759  jns     short loc_18002C77B
0x18002c75b  mov     edx, 10Ch; void *
0x18002c760  mov     rcx, [rbp+278h]; this
0x18002c767  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002c76e  mov     r9d, esi; char *
0x18002c771  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c776  jmp     loc_18002CB66
0x18002c77b  mov     rbx, [rsp+370h+pszPathIn]
0x18002c780  mov     edi, 1
0x18002c785  xor     edx, edx
0x18002c787  mov     [rsp+370h+ppszPathOut], r12
0x18002c78c  lea     rcx, [rsp+370h+ppszPathOut]
0x18002c791  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002c796  lea     r9, [rsp+370h+ppszPathOut]; ppszPathOut
0x18002c79b  mov     r8d, edi; dwFlags
0x18002c79e  lea     rdx, pszMore; "*"
0x18002c7a5  mov     rcx, rbx; pszPathIn
0x18002c7a8  call    cs:__imp_PathAllocCombine
0x18002c7ae  mov     esi, eax
0x18002c7b0  test    eax, eax
0x18002c7b2  jns     short loc_18002C7D4
0x18002c7b4  mov     rcx, [rbp+278h]; this
0x18002c7bb  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002c7c2  mov     r9d, eax; char *
0x18002c7c5  mov     edx, 111h; void *
0x18002c7ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c7cf  jmp     loc_18002CB5C
0x18002c7d4  xor     edx, edx; Val
0x18002c7d6  lea     rcx, [rbp+270h+FindFileData]; void *
0x18002c7da  mov     r8d, 250h; Size
0x18002c7e0  call    memset_0
0x18002c7e5  mov     rcx, [rsp+370h+ppszPathOut]; lpFileName
0x18002c7ea  lea     rdx, [rbp+270h+FindFileData]; lpFindFileData
0x18002c7ee  call    cs:__imp_FindFirstFileW
0x18002c7f4  mov     rdi, rax
0x18002c7f7  mov     [rsp+370h+var_340], rax
0x18002c7fc  dec     rax
0x18002c7ff  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002c803  ja      loc_18002CB74
0x18002c809  test    byte ptr [rbp+270h+FindFileData.dwFileAttributes], 10h
0x18002c80d  jz      short loc_18002C834
0x18002c80f  cmp     [rbp+270h+FindFileData.cFileName], 2Eh ; '.'
0x18002c814  jnz     short loc_18002C834
0x18002c816  movzx   eax, [rbp+270h+FindFileData.cFileName+2]
0x18002c81a  test    ax, ax
0x18002c81d  jz      loc_18002C96F
0x18002c823  cmp     ax, 2Eh ; '.'
0x18002c827  jnz     short loc_18002C834
0x18002c829  cmp     [rbp+270h+FindFileData.cFileName+4], r12w
0x18002c82e  jz      loc_18002C96F
0x18002c834  xor     edx, edx
0x18002c836  mov     [rsp+370h+var_338], r12
0x18002c83b  lea     rcx, [rsp+370h+var_338]
0x18002c840  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002c845  lea     r9, [rsp+370h+var_338]; ppszPathOut
0x18002c84a  mov     r8d, 18h; dwFlags
0x18002c850  lea     rdx, [rbp+270h+FindFileData.cFileName]; pszMore
0x18002c854  mov     rcx, rbx; pszPathIn
0x18002c857  call    cs:__imp_PathAllocCombine
0x18002c85d  mov     esi, eax
0x18002c85f  test    eax, eax
0x18002c861  js      loc_18002CB2D
0x18002c867  test    byte ptr [rbp+270h+FindFileData.dwFileAttributes], 10h
0x18002c86b  jz      loc_18002C8FF
0x18002c871  mov     rdx, [rsp+370h+var_338]
0x18002c876  lea     r8, [rbp+270h+FindFileData]
0x18002c87a  lea     rcx, [rsp+370h+hFile]
0x18002c87f  call    ?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z; wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)
0x18002c884  mov     r8, [rsp+370h+hFile]
0x18002c889  lea     rax, [r8-1]
0x18002c88d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002c891  ja      short loc_18002C8D3
0x18002c893  mov     rcx, [rsp+370h+var_338]
0x18002c898  mov     edx, r15d
0x18002c89b  and     edx, 0FFFFFFFEh
0x18002c89e  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x18002c8a3  mov     esi, eax
0x18002c8a5  test    eax, eax
0x18002c8a7  jns     short loc_18002C8F3
0x18002c8a9  mov     rcx, [rbp+278h]; this
0x18002c8b0  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002c8b7  mov     r9d, eax; char *
0x18002c8ba  mov     edx, 12Ch; void *
0x18002c8bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c8c4  lea     rcx, [rsp+370h+hFile]
0x18002c8c9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002c8ce  jmp     loc_18002CB48
0x18002c8d3  test    [rbp+270h+FindFileData.dwFileAttributes], 400h
0x18002c8da  jz      loc_18002CA3C
0x18002c8e0  mov     rcx, [rsp+370h+var_338]; lpPathName
0x18002c8e5  call    cs:__imp_RemoveDirectoryW
0x18002c8eb  test    eax, eax
0x18002c8ed  jz      loc_18002CA1D
0x18002c8f3  lea     rcx, [rsp+370h+hFile]
0x18002c8f8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002c8fd  jmp     short loc_18002C965
0x18002c8ff  mov     rcx, [rsp+370h+var_338]; lpFileName
0x18002c904  call    cs:__imp_DeleteFileW
0x18002c90a  test    eax, eax
0x18002c90c  jnz     short loc_18002C965
0x18002c90e  test    r15b, 2
0x18002c912  jz      loc_18002CAB9
0x18002c918  call    cs:__imp_GetLastError
0x18002c91e  cmp     eax, 5
0x18002c921  jnz     loc_18002CAB9
0x18002c927  mov     rcx, [rsp+370h+var_338]; lpFileName
0x18002c92c  call    cs:__imp_GetFileAttributesW
0x18002c932  test    al, 1
0x18002c934  jz      loc_18002CAB2
0x18002c93a  and     eax, 0FFFFFFFEh
0x18002c93d  mov     ecx, 80h
0x18002c942  cmovz   eax, ecx
0x18002c945  mov     rcx, [rsp+370h+var_338]; lpFileName
0x18002c94a  mov     edx, eax; dwFileAttributes
0x18002c94c  call    cs:__imp_SetFileAttributesW
0x18002c952  mov     rcx, [rsp+370h+var_338]; lpFileName
0x18002c957  call    cs:__imp_DeleteFileW
0x18002c95d  test    eax, eax
0x18002c95f  jz      loc_18002CA93
0x18002c965  lea     rcx, [rsp+370h+var_338]
0x18002c96a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c96f  lea     rdx, [rbp+270h+FindFileData]; lpFindFileData
0x18002c973  mov     rcx, rdi; hFindFile
0x18002c976  call    cs:__imp_FindNextFileW
0x18002c97c  test    eax, eax
0x18002c97e  jnz     loc_18002C809
0x18002c984  call    cs:__imp_GetLastError
0x18002c98a  cmp     eax, 12h
0x18002c98d  jnz     loc_18002CAFA
0x18002c993  test    r15b, 1
0x18002c997  jnz     loc_18002CB08
0x18002c99d  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18002c9a1  jz      loc_18002CAE3
0x18002c9a7  lea     ebx, [rax-0Eh]
0x18002c9aa  mov     dword ptr [rsp+370h+hFile], 3
0x18002c9b2  mov     r9d, ebx; dwBufferSize
0x18002c9b5  lea     r8, [rsp+370h+hFile]; lpFileInformation
0x18002c9ba  lea     edx, [rax+3]; FileInformationClass
0x18002c9bd  mov     rcx, r14; hFile
0x18002c9c0  call    cs:__imp_SetFileInformationByHandle
0x18002c9c6  test    eax, eax
0x18002c9c8  jnz     loc_18002CB08
0x18002c9ce  call    cs:__imp_GetLastError
0x18002c9d4  cmp     eax, 5
0x18002c9d7  jz      loc_18002CAC0
0x18002c9dd  lea     r9d, [rbx-3]; dwBufferSize
0x18002c9e1  mov     [rsp+370h+FileInformation], 1
0x18002c9e6  lea     r8, [rsp+370h+FileInformation]; lpFileInformation
0x18002c9eb  mov     edx, ebx; FileInformationClass
0x18002c9ed  mov     rcx, r14; hFile
0x18002c9f0  call    cs:__imp_SetFileInformationByHandle
0x18002c9f6  test    eax, eax
0x18002c9f8  jnz     loc_18002CB08
0x18002c9fe  mov     edx, 171h; void *
0x18002ca03  mov     rcx, [rbp+278h]; this
0x18002ca0a  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002ca11  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002ca16  mov     esi, eax
0x18002ca18  jmp     loc_18002CB52
0x18002ca1d  mov     rcx, [rbp+278h]; this
0x18002ca24  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002ca2b  mov     edx, 131h; void *
0x18002ca30  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002ca35  mov     esi, eax
0x18002ca37  jmp     loc_18002C8C4
0x18002ca3c  call    cs:__imp_GetLastError
0x18002ca42  test    eax, eax
0x18002ca44  jz      short loc_18002CA63
0x18002ca46  mov     rcx, [rbp+278h]; this
0x18002ca4d  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002ca54  mov     r9d, eax; char *
0x18002ca57  mov     edx, 136h; void *
0x18002ca5c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002ca61  jmp     short loc_18002CA35
0x18002ca63  lea     rcx, [rsp+370h+hFile]
0x18002ca68  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002ca6d  lea     rcx, [rsp+370h+var_338]
0x18002ca72  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002ca77  lea     rcx, [rsp+370h+var_340]
0x18002ca7c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18002ca81  lea     rcx, [rsp+370h+ppszPathOut]
0x18002ca86  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002ca8b  mov     esi, r12d
0x18002ca8e  jmp     loc_18002CB66
0x18002ca93  mov     edx, 150h; void *
0x18002ca98  mov     rcx, [rbp+278h]; this
0x18002ca9f  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002caa6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002caab  mov     esi, eax
0x18002caad  jmp     loc_18002CB48
0x18002cab2  mov     edx, 145h
0x18002cab7  jmp     short loc_18002CA98
0x18002cab9  mov     edx, 141h
0x18002cabe  jmp     short loc_18002CA98
0x18002cac0  mov     r9d, 5; char *
0x18002cac6  mov     edx, 176h; void *
0x18002cacb  mov     rcx, [rbp+278h]; this
0x18002cad2  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002cad9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002cade  jmp     loc_18002CA16
0x18002cae3  mov     rcx, rbx; lpPathName
0x18002cae6  call    cs:__imp_RemoveDirectoryW
0x18002caec  test    eax, eax
0x18002caee  jnz     short loc_18002CB08
0x18002caf0  mov     edx, 17Dh
0x18002caf5  jmp     loc_18002CA03
0x18002cafa  test    eax, eax
0x18002cafc  jz      short loc_18002CB08
0x18002cafe  mov     r9d, eax
0x18002cb01  mov     edx, 15Ch
0x18002cb06  jmp     short loc_18002CACB
0x18002cb08  lea     rcx, [rsp+370h+var_340]
0x18002cb0d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18002cb12  lea     rcx, [rsp+370h+ppszPathOut]
0x18002cb17  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002cb1c  lea     rcx, [rsp+370h+pszPathIn]
0x18002cb21  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002cb26  xor     eax, eax
0x18002cb28  jmp     loc_18002CBAE
0x18002cb2d  mov     rcx, [rbp+278h]; this
0x18002cb34  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002cb3b  mov     r9d, eax; char *
0x18002cb3e  mov     edx, 120h; void *
0x18002cb43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cb48  lea     rcx, [rsp+370h+var_338]
0x18002cb4d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002cb52  lea     rcx, [rsp+370h+var_340]
0x18002cb57  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18002cb5c  lea     rcx, [rsp+370h+ppszPathOut]
0x18002cb61  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002cb66  lea     rcx, [rsp+370h+pszPathIn]
0x18002cb6b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002cb70  mov     eax, esi
0x18002cb72  jmp     short loc_18002CBAE
0x18002cb74  mov     rcx, [rbp+278h]; this
0x18002cb7b  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002cb82  mov     edx, 115h; void *
0x18002cb87  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002cb8c  lea     rcx, [rsp+370h+var_340]
0x18002cb91  mov     ebx, eax
0x18002cb93  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18002cb98  lea     rcx, [rsp+370h+ppszPathOut]
0x18002cb9d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002cba2  lea     rcx, [rsp+370h+pszPathIn]
0x18002cba7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002cbac  mov     eax, ebx
0x18002cbae  mov     rcx, [rbp+270h+var_40]
  ... truncated ...
```

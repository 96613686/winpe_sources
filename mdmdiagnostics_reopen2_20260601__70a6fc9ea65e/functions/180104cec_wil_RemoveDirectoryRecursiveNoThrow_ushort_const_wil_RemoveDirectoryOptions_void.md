# wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)

- ea: `0x180104cec`
- end: `0x180105267`
- name: `?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z`
- size: `1403`
- prototype: ``
- caller_count: `5`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180104cec`
- `0x180105270`
- `0x180108d94`
- `0x18010cb20`
- `0x180111204`

## callees

- `0x180019080`
- `0x18001a054`
- `0x1800ed44c`
- `0x1800ed46c`
- `0x1800f809c`
- `0x1800f9c9c`
- `0x1800fa09c`
- `0x1800fa50c`
- `0x1800fa538`
- `0x1800fa854`
- `0x180104cec`
- `0x180105294`
- `0x180105308`
- `0x180105538`
- `0x1801055a4`
- `0x18010562c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180105035`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180105071`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180105035`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180105071`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180104f82`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180104f82`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180104f4e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180104fb9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180104f4e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180104fb9`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180104fa8`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180104fa8`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180104fdf`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180104fdf`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180104f26`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180105172`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180104f26`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180105172`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180104e2f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180104e2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180104f68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180104ff3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180105049`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801050c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180104f68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180104ff3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180105049`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801050c3`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180104de1`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180104e8f`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180104de1`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180104e8f`

## string_xrefs

- `0x180104d9f`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180104dfa`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180104ef0`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180105091`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1801050ab`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1801050da`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18010512b`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18010515e`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1801051c6`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18010520d`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

## pseudocode

```c
__int64 __fastcall wil::RemoveDirectoryRecursiveNoThrow(wil *a1, const unsigned __int16 *a2, void *a3)
{
  int v4; // r15d
  const WCHAR *v6; // rbx
  ULONG v7; // edi
  unsigned int v8; // esi
  __int64 v9; // rdx
  __int64 v10; // r9
  int v11; // eax
  HRESULT v12; // eax
  const unsigned __int16 *v13; // rdx
  char *FirstFileW; // rdi
  const char *v15; // r9
  HRESULT v16; // eax
  int v17; // eax
  const char *v18; // r9
  const char *v19; // r9
  DWORD FileAttributesW; // eax
  DWORD v21; // eax
  DWORD v22; // eax
  const char *v23; // r9
  __int64 v24; // rdx
  int v25; // eax
  int v26; // eax
  DWORD v27; // eax
  __int64 v28; // rdx
  __int64 v29; // r9
  __int64 v30; // rdx
  unsigned int LastError; // ebx
  unsigned int v33; // [rsp+20h] [rbp-E0h]
  PWSTR v34; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR ppszPathOut; // [rsp+38h] [rbp-C8h] BYREF
  char *v36; // [rsp+40h] [rbp-C0h] BYREF
  char FileInformation[8]; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hFile; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR pszPathIn; // [rsp+58h] [rbp-A8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  pszPathIn = 0;
  v4 = (int)a2;
  if ( wil::is_extended_length_path(a1, a2) )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v36,
      a1,
      -1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &pszPathIn,
      &v36);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v36);
    v6 = pszPathIn;
    if ( pszPathIn )
    {
      v7 = 16;
      goto LABEL_9;
    }
    v8 = -2147024882;
    v9 = 260;
    v10 = 2147942414LL;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
      (const char *)v10,
      v33);
    goto LABEL_61;
  }
  v11 = wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
          a1,
          &pszPathIn);
  v8 = v11;
  if ( v11 < 0 )
  {
    v10 = (unsigned int)v11;
    v9 = 268;
    goto LABEL_7;
  }
  v6 = pszPathIn;
  v7 = 1;
LABEL_9:
  ppszPathOut = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPathOut,
    0);
  v12 = PathAllocCombine(v6, L"*", v7, &ppszPathOut);
  v8 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x111,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
      (const char *)(unsigned int)v12,
      v33);
    goto LABEL_60;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (char *)FindFirstFileW(ppszPathOut, &FindFileData);
  v36 = FirstFileW;
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x115,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                  v15);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v36);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
    return LastError;
  }
  while ( 1 )
  {
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 && wil::path_is_dot_or_dotdot((wil *)FindFileData.cFileName, v13) )
      goto LABEL_31;
    v34 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v34,
      0);
    v16 = PathAllocCombine(v6, FindFileData.cFileName, 0x18u, &v34);
    v8 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x120,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
        (const char *)(unsigned int)v16,
        v33);
      goto LABEL_58;
    }
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      break;
    wil::TryCreateFileCanRecurseIntoDirectory(&hFile, v34, &FindFileData);
    if ( (char *)hFile - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( (FindFileData.dwFileAttributes & 0x400) == 0 )
      {
        v27 = GetLastError();
        if ( !v27 )
        {
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v34);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v36);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
          v8 = 0;
          goto LABEL_61;
        }
        v26 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x136,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                (const char *)v27,
                v33);
        goto LABEL_42;
      }
      if ( !RemoveDirectoryW(v34) )
      {
        v26 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x131,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                v18);
LABEL_42:
        v8 = v26;
        goto LABEL_19;
      }
    }
    else
    {
      v17 = wil::RemoveDirectoryRecursiveNoThrow(v34, v4 & 0xFFFFFFFE);
      v8 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12C,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
          (const char *)(unsigned int)v17,
          v33);
LABEL_19:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
        goto LABEL_58;
      }
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
LABEL_30:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v34);
LABEL_31:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
    {
      v22 = GetLastError();
      if ( v22 == 18 )
      {
        if ( (v4 & 1) != 0 )
          goto LABEL_56;
        if ( a3 == (void *)-1LL )
        {
          if ( !RemoveDirectoryW(v6) )
          {
            v24 = 381;
            goto LABEL_39;
          }
LABEL_56:
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v36);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
          return 0;
        }
        LODWORD(hFile) = 3;
        if ( SetFileInformationByHandle(a3, FileRenameInfoEx|FileDispositionInfo, &hFile, 4u) )
          goto LABEL_56;
        if ( GetLastError() != 5 )
        {
          FileInformation[0] = 1;
          if ( !SetFileInformationByHandle(a3, FileDispositionInfo, FileInformation, 1u) )
          {
            v24 = 369;
LABEL_39:
            v25 = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v24,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                    v23);
LABEL_40:
            v8 = v25;
            goto LABEL_59;
          }
          goto LABEL_56;
        }
        v29 = 5;
        v30 = 374;
      }
      else
      {
        if ( !v22 )
          goto LABEL_56;
        v29 = v22;
        v30 = 348;
      }
      v25 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v30,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
              (const char *)v29,
              v33);
      goto LABEL_40;
    }
  }
  if ( DeleteFileW(v34) )
    goto LABEL_30;
  if ( (v4 & 2) != 0 && GetLastError() == 5 )
  {
    FileAttributesW = GetFileAttributesW(v34);
    if ( (FileAttributesW & 1) == 0 )
    {
      v28 = 325;
      goto LABEL_47;
    }
    v21 = FileAttributesW & 0xFFFFFFFE;
    if ( !v21 )
      v21 = 128;
    SetFileAttributesW(v34, v21);
    if ( !DeleteFileW(v34) )
    {
      v28 = 336;
      goto LABEL_47;
    }
    goto LABEL_30;
  }
  v28 = 321;
LABEL_47:
  v8 = wil::details::in1diag3::Return_GetLastError(
         retaddr,
         (void *)v28,
         (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
         v19);
LABEL_58:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v34);
LABEL_59:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v36);
LABEL_60:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
LABEL_61:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
  return v8;
}

```

## disassembly

```asm
0x180104cec  mov     [rsp-8+arg_18], rbx
0x180104cf1  push    rbp
0x180104cf2  push    rsi
0x180104cf3  push    rdi
0x180104cf4  push    r14
0x180104cf6  push    r15
0x180104cf8  lea     rbp, [rsp-1C0h]
0x180104d00  sub     rsp, 2C0h
0x180104d07  mov     rax, cs:__security_cookie
0x180104d0e  xor     rax, rsp
0x180104d11  mov     [rbp+1E0h+var_30], rax
0x180104d18  mov     r14, r8
0x180104d1b  mov     [rsp+2E0h+pszPathIn], 0
0x180104d24  mov     r15d, edx
0x180104d27  mov     rbx, rcx
0x180104d2a  call    ?is_extended_length_path@wil@@YA_NPEBG@Z; wil::is_extended_length_path(ushort const *)
0x180104d2f  test    al, al
0x180104d31  jz      short loc_180104D7D
0x180104d33  or      r8, 0FFFFFFFFFFFFFFFFh
0x180104d37  lea     rcx, [rsp+2E0h+var_2A0]
0x180104d3c  mov     rdx, rbx
0x180104d3f  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180104d44  lea     rdx, [rsp+2E0h+var_2A0]
0x180104d49  lea     rcx, [rsp+2E0h+pszPathIn]
0x180104d4e  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180104d53  lea     rcx, [rsp+2E0h+var_2A0]
0x180104d58  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180104d5d  mov     rbx, [rsp+2E0h+pszPathIn]
0x180104d62  test    rbx, rbx
0x180104d65  jz      short loc_180104D6E
0x180104d67  mov     edi, 10h
0x180104d6c  jmp     short loc_180104DBA
0x180104d6e  mov     esi, 8007000Eh
0x180104d73  mov     edx, 104h
0x180104d78  mov     r9d, esi
0x180104d7b  jmp     short loc_180104D98
0x180104d7d  lea     rdx, [rsp+2E0h+pszPathIn]
0x180104d82  mov     rcx, rbx
0x180104d85  call    ??$GetFullPathNameW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEAPEBG@Z; wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const * *)
0x180104d8a  mov     esi, eax
0x180104d8c  test    eax, eax
0x180104d8e  jns     short loc_180104DB0
0x180104d90  mov     r9d, eax; char *
0x180104d93  mov     edx, 10Ch; void *
0x180104d98  mov     rcx, [rbp+1E8h]; this
0x180104d9f  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180104da6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180104dab  jmp     loc_1801051F8
0x180104db0  mov     rbx, [rsp+2E0h+pszPathIn]
0x180104db5  mov     edi, 1
0x180104dba  xor     edx, edx
0x180104dbc  mov     [rsp+2E0h+ppszPathOut], 0
0x180104dc5  lea     rcx, [rsp+2E0h+ppszPathOut]
0x180104dca  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180104dcf  lea     r9, [rsp+2E0h+ppszPathOut]; ppszPathOut
0x180104dd4  mov     r8d, edi; dwFlags
0x180104dd7  lea     rdx, Delimiter; "*"
0x180104dde  mov     rcx, rbx; pszPathIn
0x180104de1  call    cs:__imp_PathAllocCombine
0x180104de8  nop     dword ptr [rax+rax+00h]
0x180104ded  mov     esi, eax
0x180104def  test    eax, eax
0x180104df1  jns     short loc_180104E13
0x180104df3  mov     rcx, [rbp+1E8h]; this
0x180104dfa  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180104e01  mov     r9d, eax; char *
0x180104e04  mov     edx, 111h; void *
0x180104e09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180104e0e  jmp     loc_1801051EE
0x180104e13  xor     edx, edx; Val
0x180104e15  lea     rcx, [rsp+2E0h+FindFileData]; void *
0x180104e1a  mov     r8d, 250h; Size
0x180104e20  call    memset_0
0x180104e25  mov     rcx, [rsp+2E0h+ppszPathOut]; lpFileName
0x180104e2a  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x180104e2f  call    cs:__imp_FindFirstFileW
0x180104e36  nop     dword ptr [rax+rax+00h]
0x180104e3b  mov     rdi, rax
0x180104e3e  mov     [rsp+2E0h+var_2A0], rax
0x180104e43  dec     rax
0x180104e46  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180104e4a  ja      loc_180105206
0x180104e50  test    byte ptr [rsp+2E0h+FindFileData.dwFileAttributes], 10h
0x180104e55  jz      short loc_180104E68
0x180104e57  lea     rcx, [rbp+1E0h+FindFileData.cFileName]; this
0x180104e5b  call    ?path_is_dot_or_dotdot@wil@@YA_NPEBG@Z; wil::path_is_dot_or_dotdot(ushort const *)
0x180104e60  test    al, al
0x180104e62  jnz     loc_180104FD7
0x180104e68  xor     edx, edx
0x180104e6a  mov     [rsp+2E0h+var_2B0], 0
0x180104e73  lea     rcx, [rsp+2E0h+var_2B0]
0x180104e78  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180104e7d  lea     r9, [rsp+2E0h+var_2B0]; ppszPathOut
0x180104e82  mov     r8d, 18h; dwFlags
0x180104e88  lea     rdx, [rbp+1E0h+FindFileData.cFileName]; pszMore
0x180104e8c  mov     rcx, rbx; pszPathIn
0x180104e8f  call    cs:__imp_PathAllocCombine
0x180104e96  nop     dword ptr [rax+rax+00h]
0x180104e9b  mov     esi, eax
0x180104e9d  test    eax, eax
0x180104e9f  js      loc_1801051BF
0x180104ea5  test    byte ptr [rsp+2E0h+FindFileData.dwFileAttributes], 10h
0x180104eaa  jz      loc_180104F49
0x180104eb0  mov     rdx, [rsp+2E0h+var_2B0]
0x180104eb5  lea     r8, [rsp+2E0h+FindFileData]
0x180104eba  lea     rcx, [rsp+2E0h+hFile]
0x180104ebf  call    ?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z; wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)
0x180104ec4  mov     r8, [rsp+2E0h+hFile]
0x180104ec9  lea     rax, [r8-1]
0x180104ecd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180104ed1  ja      short loc_180104F13
0x180104ed3  mov     rcx, [rsp+2E0h+var_2B0]
0x180104ed8  mov     edx, r15d
0x180104edb  and     edx, 0FFFFFFFEh
0x180104ede  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x180104ee3  mov     esi, eax
0x180104ee5  test    eax, eax
0x180104ee7  jns     short loc_180104F3A
0x180104ee9  mov     rcx, [rbp+1E8h]; this
0x180104ef0  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180104ef7  mov     r9d, eax; char *
0x180104efa  mov     edx, 12Ch; void *
0x180104eff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180104f04  lea     rcx, [rsp+2E0h+hFile]
0x180104f09  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180104f0e  jmp     loc_1801051DA
0x180104f13  test    [rsp+2E0h+FindFileData.dwFileAttributes], 400h
0x180104f1b  jz      loc_1801050C3
0x180104f21  mov     rcx, [rsp+2E0h+var_2B0]; lpPathName
0x180104f26  call    cs:__imp_RemoveDirectoryW
0x180104f2d  nop     dword ptr [rax+rax+00h]
0x180104f32  test    eax, eax
0x180104f34  jz      loc_1801050A4
0x180104f3a  lea     rcx, [rsp+2E0h+hFile]
0x180104f3f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180104f44  jmp     loc_180104FCD
0x180104f49  mov     rcx, [rsp+2E0h+var_2B0]; lpFileName
0x180104f4e  call    cs:__imp_DeleteFileW
0x180104f55  nop     dword ptr [rax+rax+00h]
0x180104f5a  test    eax, eax
0x180104f5c  jnz     short loc_180104FCD
0x180104f5e  test    r15b, 2
0x180104f62  jz      loc_180105145
0x180104f68  call    cs:__imp_GetLastError
0x180104f6f  nop     dword ptr [rax+rax+00h]
0x180104f74  cmp     eax, 5
0x180104f77  jnz     loc_180105145
0x180104f7d  mov     rcx, [rsp+2E0h+var_2B0]; lpFileName
0x180104f82  call    cs:__imp_GetFileAttributesW
0x180104f89  nop     dword ptr [rax+rax+00h]
0x180104f8e  test    al, 1
0x180104f90  jz      loc_18010513E
0x180104f96  and     eax, 0FFFFFFFEh
0x180104f99  mov     ecx, 80h
0x180104f9e  cmovz   eax, ecx
0x180104fa1  mov     rcx, [rsp+2E0h+var_2B0]; lpFileName
0x180104fa6  mov     edx, eax; dwFileAttributes
0x180104fa8  call    cs:__imp_SetFileAttributesW
0x180104faf  nop     dword ptr [rax+rax+00h]
0x180104fb4  mov     rcx, [rsp+2E0h+var_2B0]; lpFileName
0x180104fb9  call    cs:__imp_DeleteFileW
0x180104fc0  nop     dword ptr [rax+rax+00h]
0x180104fc5  test    eax, eax
0x180104fc7  jz      loc_18010511F
0x180104fcd  lea     rcx, [rsp+2E0h+var_2B0]
0x180104fd2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180104fd7  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x180104fdc  mov     rcx, rdi; hFindFile
0x180104fdf  call    cs:__imp_FindNextFileW
0x180104fe6  nop     dword ptr [rax+rax+00h]
0x180104feb  test    eax, eax
0x180104fed  jnz     loc_180104E50
0x180104ff3  call    cs:__imp_GetLastError
0x180104ffa  nop     dword ptr [rax+rax+00h]
0x180104fff  cmp     eax, 12h
0x180105002  jnz     loc_18010518C
0x180105008  test    r15b, 1
0x18010500c  jnz     loc_18010519A
0x180105012  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180105016  jz      loc_18010516F
0x18010501c  lea     ebx, [rax-0Eh]
0x18010501f  mov     dword ptr [rsp+2E0h+hFile], 3
0x180105027  mov     r9d, ebx; dwBufferSize
0x18010502a  lea     r8, [rsp+2E0h+hFile]; lpFileInformation
0x18010502f  lea     edx, [rax+3]; FileInformationClass
0x180105032  mov     rcx, r14; hFile
0x180105035  call    cs:__imp_SetFileInformationByHandle
0x18010503c  nop     dword ptr [rax+rax+00h]
0x180105041  test    eax, eax
0x180105043  jnz     loc_18010519A
0x180105049  call    cs:__imp_GetLastError
0x180105050  nop     dword ptr [rax+rax+00h]
0x180105055  cmp     eax, 5
0x180105058  jz      loc_18010514C
0x18010505e  lea     r9d, [rbx-3]; dwBufferSize
0x180105062  mov     [rsp+2E0h+FileInformation], 1
0x180105067  lea     r8, [rsp+2E0h+FileInformation]; lpFileInformation
0x18010506c  mov     edx, ebx; FileInformationClass
0x18010506e  mov     rcx, r14; hFile
0x180105071  call    cs:__imp_SetFileInformationByHandle
0x180105078  nop     dword ptr [rax+rax+00h]
0x18010507d  test    eax, eax
0x18010507f  jnz     loc_18010519A
0x180105085  mov     edx, 171h; void *
0x18010508a  mov     rcx, [rbp+1E8h]; this
0x180105091  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180105098  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18010509d  mov     esi, eax
0x18010509f  jmp     loc_1801051E4
0x1801050a4  mov     rcx, [rbp+1E8h]; this
0x1801050ab  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1801050b2  mov     edx, 131h; void *
0x1801050b7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801050bc  mov     esi, eax
0x1801050be  jmp     loc_180104F04
0x1801050c3  call    cs:__imp_GetLastError
0x1801050ca  nop     dword ptr [rax+rax+00h]
0x1801050cf  test    eax, eax
0x1801050d1  jz      short loc_1801050F0
0x1801050d3  mov     rcx, [rbp+1E8h]; this
0x1801050da  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1801050e1  mov     r9d, eax; char *
0x1801050e4  mov     edx, 136h; void *
0x1801050e9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801050ee  jmp     short loc_1801050BC
0x1801050f0  lea     rcx, [rsp+2E0h+hFile]
0x1801050f5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801050fa  lea     rcx, [rsp+2E0h+var_2B0]
0x1801050ff  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180105104  lea     rcx, [rsp+2E0h+var_2A0]
0x180105109  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18010510e  lea     rcx, [rsp+2E0h+ppszPathOut]
0x180105113  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180105118  xor     esi, esi
0x18010511a  jmp     loc_1801051F8
0x18010511f  mov     edx, 150h; void *
0x180105124  mov     rcx, [rbp+1E8h]; this
0x18010512b  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180105132  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180105137  mov     esi, eax
0x180105139  jmp     loc_1801051DA
0x18010513e  mov     edx, 145h
0x180105143  jmp     short loc_180105124
0x180105145  mov     edx, 141h
0x18010514a  jmp     short loc_180105124
0x18010514c  mov     r9d, 5; char *
0x180105152  mov     edx, 176h; void *
0x180105157  mov     rcx, [rbp+1E8h]; this
0x18010515e  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180105165  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010516a  jmp     loc_18010509D
0x18010516f  mov     rcx, rbx; lpPathName
0x180105172  call    cs:__imp_RemoveDirectoryW
0x180105179  nop     dword ptr [rax+rax+00h]
0x18010517e  test    eax, eax
0x180105180  jnz     short loc_18010519A
0x180105182  mov     edx, 17Dh
0x180105187  jmp     loc_18010508A
0x18010518c  test    eax, eax
0x18010518e  jz      short loc_18010519A
0x180105190  mov     r9d, eax
0x180105193  mov     edx, 15Ch
0x180105198  jmp     short loc_180105157
0x18010519a  lea     rcx, [rsp+2E0h+var_2A0]
0x18010519f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1801051a4  lea     rcx, [rsp+2E0h+ppszPathOut]
0x1801051a9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801051ae  lea     rcx, [rsp+2E0h+pszPathIn]
0x1801051b3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801051b8  xor     eax, eax
0x1801051ba  jmp     loc_180105240
0x1801051bf  mov     rcx, [rbp+1E8h]; this
0x1801051c6  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1801051cd  mov     r9d, eax; char *
0x1801051d0  mov     edx, 120h; void *
0x1801051d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801051da  lea     rcx, [rsp+2E0h+var_2B0]
0x1801051df  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801051e4  lea     rcx, [rsp+2E0h+var_2A0]
0x1801051e9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1801051ee  lea     rcx, [rsp+2E0h+ppszPathOut]
0x1801051f3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801051f8  lea     rcx, [rsp+2E0h+pszPathIn]
0x1801051fd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180105202  mov     eax, esi
0x180105204  jmp     short loc_180105240
0x180105206  mov     rcx, [rbp+1E8h]; this
0x18010520d  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180105214  mov     edx, 115h; void *
0x180105219  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18010521e  lea     rcx, [rsp+2E0h+var_2A0]
0x180105223  mov     ebx, eax
0x180105225  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18010522a  lea     rcx, [rsp+2E0h+ppszPathOut]
0x18010522f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180105234  lea     rcx, [rsp+2E0h+pszPathIn]
0x180105239  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010523e  mov     eax, ebx
0x180105240  mov     rcx, [rbp+1E0h+var_30]
0x180105247  xor     rcx, rsp; StackCookie
  ... truncated ...
```

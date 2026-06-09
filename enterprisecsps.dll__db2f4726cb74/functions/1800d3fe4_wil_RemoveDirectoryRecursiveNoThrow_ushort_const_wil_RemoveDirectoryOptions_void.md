# wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)

- ea: `0x1800d3fe4`
- end: `0x1800d4565`
- name: `?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z`
- size: `1409`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d3fe4`
- `0x1800f9b94`

## callees

- `0x180008de0`
- `0x180009cc4`
- `0x18000d4b4`
- `0x18000d4d4`
- `0x180025a78`
- `0x18002aed0`
- `0x18002dc38`
- `0x18004568c`
- `0x18005bd10`
- `0x180084334`
- `0x1800d2d60`
- `0x1800d3344`
- `0x1800d3fe4`
- `0x1800d4b20`
- `0x1800d54d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d426a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d42f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d434b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d43c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d426a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d42f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d434b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d43c5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800d4284`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800d4284`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800d4228`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800d4475`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800d4228`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800d4475`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800d4121`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800d4121`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800d42e1`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800d42e1`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800d42aa`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800d42aa`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800d4337`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800d4373`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800d4337`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800d4373`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800d4250`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800d42bb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800d4250`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800d42bb`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800d40d3`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800d4191`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800d40d3`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800d4191`

## string_xrefs

- `0x1800d4095`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1800d40ec`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1800d41f2`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1800d4393`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1800d43ad`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1800d43dc`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1800d442e`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1800d4461`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1800d44c9`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1800d4510`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

## pseudocode

```c
__int64 __fastcall wil::RemoveDirectoryRecursiveNoThrow(wil *a1, const unsigned __int16 *a2, void *a3)
{
  int v4; // r15d
  const WCHAR *v6; // rbx
  unsigned int v7; // esi
  __int64 v8; // rdx
  __int64 v9; // r9
  ULONG v10; // edi
  int v11; // eax
  HRESULT v12; // eax
  char *FirstFileW; // rdi
  const char *v14; // r9
  HRESULT v15; // eax
  int v16; // eax
  const char *v17; // r9
  const char *v18; // r9
  DWORD FileAttributesW; // eax
  DWORD v20; // eax
  DWORD v21; // eax
  const char *v22; // r9
  __int64 v23; // rdx
  int v24; // eax
  int v25; // eax
  DWORD v26; // eax
  __int64 v27; // rdx
  __int64 v28; // r9
  __int64 v29; // rdx
  unsigned int LastError; // ebx
  unsigned int v32; // [rsp+20h] [rbp-E0h]
  PWSTR v33; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR ppszPathOut; // [rsp+38h] [rbp-C8h] BYREF
  char *v35; // [rsp+40h] [rbp-C0h] BYREF
  char FileInformation[8]; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hFile; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR pszPathIn; // [rsp+58h] [rbp-A8h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  pszPathIn = 0;
  v4 = (int)a2;
  if ( wil::is_extended_length_path(a1, a2) )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v35,
      a1,
      -1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &pszPathIn,
      &v35);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
    v6 = pszPathIn;
    if ( !pszPathIn )
    {
      v7 = -2147024882;
      v8 = 260;
      v9 = 2147942414LL;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
        (const char *)v9,
        v32);
      goto LABEL_64;
    }
    v10 = 16;
  }
  else
  {
    v11 = wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
            a1,
            &pszPathIn);
    v7 = v11;
    if ( v11 < 0 )
    {
      v9 = (unsigned int)v11;
      v8 = 268;
      goto LABEL_7;
    }
    v6 = pszPathIn;
    v10 = 1;
  }
  ppszPathOut = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPathOut,
    0);
  v12 = PathAllocCombine(v6, L"*", v10, &ppszPathOut);
  v7 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x111,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
      (const char *)(unsigned int)v12,
      v32);
    goto LABEL_63;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (char *)FindFirstFileW(ppszPathOut, &FindFileData);
  v35 = FirstFileW;
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x115,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                  v14);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v35);
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
    v15 = PathAllocCombine(v6, FindFileData.cFileName, 0x18u, &v33);
    v7 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x120,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
        (const char *)(unsigned int)v15,
        v32);
      goto LABEL_61;
    }
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      break;
    wil::TryCreateFileCanRecurseIntoDirectory(&hFile, v33, &FindFileData);
    if ( (char *)hFile - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( (FindFileData.dwFileAttributes & 0x400) == 0 )
      {
        v26 = GetLastError();
        if ( !v26 )
        {
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v35);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
          v7 = 0;
          goto LABEL_64;
        }
        v25 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x136,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                (const char *)v26,
                v32);
        goto LABEL_45;
      }
      if ( !RemoveDirectoryW(v33) )
      {
        v25 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x131,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                v17);
LABEL_45:
        v7 = v25;
        goto LABEL_22;
      }
    }
    else
    {
      v16 = wil::RemoveDirectoryRecursiveNoThrow(v33, v4 & 0xFFFFFFFE);
      v7 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12C,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
          (const char *)(unsigned int)v16,
          v32);
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
      v21 = GetLastError();
      if ( v21 == 18 )
      {
        if ( (v4 & 1) != 0 )
          goto LABEL_59;
        if ( a3 == (void *)-1LL )
        {
          if ( !RemoveDirectoryW(v6) )
          {
            v23 = 381;
            goto LABEL_42;
          }
LABEL_59:
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v35);
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
            v23 = 369;
LABEL_42:
            v24 = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v23,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                    v22);
LABEL_43:
            v7 = v24;
            goto LABEL_62;
          }
          goto LABEL_59;
        }
        v28 = 5;
        v29 = 374;
      }
      else
      {
        if ( !v21 )
          goto LABEL_59;
        v28 = v21;
        v29 = 348;
      }
      v24 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v29,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
              (const char *)v28,
              v32);
      goto LABEL_43;
    }
  }
  if ( DeleteFileW(v33) )
    goto LABEL_33;
  if ( (v4 & 2) != 0 && GetLastError() == 5 )
  {
    FileAttributesW = GetFileAttributesW(v33);
    if ( (FileAttributesW & 1) == 0 )
    {
      v27 = 325;
      goto LABEL_50;
    }
    v20 = FileAttributesW & 0xFFFFFFFE;
    if ( !v20 )
      v20 = 128;
    SetFileAttributesW(v33, v20);
    if ( !DeleteFileW(v33) )
    {
      v27 = 336;
      goto LABEL_50;
    }
    goto LABEL_33;
  }
  v27 = 321;
LABEL_50:
  v7 = wil::details::in1diag3::Return_GetLastError(
         retaddr,
         (void *)v27,
         (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
         v18);
LABEL_61:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
LABEL_62:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v35);
LABEL_63:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
LABEL_64:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
  return v7;
}

```

## disassembly

```asm
0x1800d3fe4  push    rbp
0x1800d3fe6  push    rbx
0x1800d3fe7  push    rsi
0x1800d3fe8  push    rdi
0x1800d3fe9  push    r12
0x1800d3feb  push    r14
0x1800d3fed  push    r15
0x1800d3fef  lea     rbp, [rsp-1C0h]
0x1800d3ff7  sub     rsp, 2C0h
0x1800d3ffe  mov     rax, cs:__security_cookie
0x1800d4005  xor     rax, rsp
0x1800d4008  mov     [rbp+1F0h+var_40], rax
0x1800d400f  xor     r12d, r12d
0x1800d4012  mov     r14, r8
0x1800d4015  mov     [rsp+2F0h+pszPathIn], r12
0x1800d401a  mov     r15d, edx
0x1800d401d  mov     rbx, rcx
0x1800d4020  call    ?is_extended_length_path@wil@@YA_NPEBG@Z; wil::is_extended_length_path(ushort const *)
0x1800d4025  test    al, al
0x1800d4027  jz      short loc_1800D4073
0x1800d4029  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800d402d  lea     rcx, [rsp+2F0h+var_2B0]
0x1800d4032  mov     rdx, rbx
0x1800d4035  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800d403a  lea     rdx, [rsp+2F0h+var_2B0]
0x1800d403f  lea     rcx, [rsp+2F0h+pszPathIn]
0x1800d4044  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800d4049  lea     rcx, [rsp+2F0h+var_2B0]
0x1800d404e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800d4053  mov     rbx, [rsp+2F0h+pszPathIn]
0x1800d4058  test    rbx, rbx
0x1800d405b  jnz     short loc_1800D406C
0x1800d405d  mov     esi, 8007000Eh
0x1800d4062  mov     edx, 104h
0x1800d4067  mov     r9d, esi
0x1800d406a  jmp     short loc_1800D408E
0x1800d406c  mov     edi, 10h
0x1800d4071  jmp     short loc_1800D40B0
0x1800d4073  lea     rdx, [rsp+2F0h+pszPathIn]
0x1800d4078  mov     rcx, rbx
0x1800d407b  call    ??$GetFullPathNameW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEAPEBG@Z; wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const * *)
0x1800d4080  mov     esi, eax
0x1800d4082  test    eax, eax
0x1800d4084  jns     short loc_1800D40A6
0x1800d4086  mov     r9d, eax; char *
0x1800d4089  mov     edx, 10Ch; void *
0x1800d408e  mov     rcx, [rbp+1F8h]; this
0x1800d4095  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800d409c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d40a1  jmp     loc_1800D44FB
0x1800d40a6  mov     rbx, [rsp+2F0h+pszPathIn]
0x1800d40ab  mov     edi, 1
0x1800d40b0  xor     edx, edx
0x1800d40b2  mov     [rsp+2F0h+ppszPathOut], r12
0x1800d40b7  lea     rcx, [rsp+2F0h+ppszPathOut]
0x1800d40bc  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800d40c1  lea     r9, [rsp+2F0h+ppszPathOut]; ppszPathOut
0x1800d40c6  mov     r8d, edi; dwFlags
0x1800d40c9  lea     rdx, asc_18012A2BC; "*"
0x1800d40d0  mov     rcx, rbx; pszPathIn
0x1800d40d3  call    cs:__imp_PathAllocCombine
0x1800d40da  nop     dword ptr [rax+rax+00h]
0x1800d40df  mov     esi, eax
0x1800d40e1  test    eax, eax
0x1800d40e3  jns     short loc_1800D4105
0x1800d40e5  mov     rcx, [rbp+1F8h]; this
0x1800d40ec  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800d40f3  mov     r9d, eax; char *
0x1800d40f6  mov     edx, 111h; void *
0x1800d40fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4100  jmp     loc_1800D44F1
0x1800d4105  xor     edx, edx; Val
0x1800d4107  lea     rcx, [rsp+2F0h+FindFileData]; void *
0x1800d410c  mov     r8d, 250h; Size
0x1800d4112  call    memset_0
0x1800d4117  mov     rcx, [rsp+2F0h+ppszPathOut]; lpFileName
0x1800d411c  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x1800d4121  call    cs:__imp_FindFirstFileW
0x1800d4128  nop     dword ptr [rax+rax+00h]
0x1800d412d  mov     rdi, rax
0x1800d4130  mov     [rsp+2F0h+var_2B0], rax
0x1800d4135  dec     rax
0x1800d4138  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800d413c  ja      loc_1800D4509
0x1800d4142  test    byte ptr [rsp+2F0h+FindFileData.dwFileAttributes], 10h
0x1800d4147  jz      short loc_1800D416E
0x1800d4149  cmp     [rbp+1F0h+FindFileData.cFileName], 2Eh ; '.'
0x1800d414e  jnz     short loc_1800D416E
0x1800d4150  movzx   eax, [rbp+1F0h+FindFileData.cFileName+2]
0x1800d4154  test    ax, ax
0x1800d4157  jz      loc_1800D42D9
0x1800d415d  cmp     ax, 2Eh ; '.'
0x1800d4161  jnz     short loc_1800D416E
0x1800d4163  cmp     [rbp+1F0h+FindFileData.cFileName+4], r12w
0x1800d4168  jz      loc_1800D42D9
0x1800d416e  xor     edx, edx
0x1800d4170  mov     [rsp+2F0h+var_2C0], r12
0x1800d4175  lea     rcx, [rsp+2F0h+var_2C0]
0x1800d417a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800d417f  lea     r9, [rsp+2F0h+var_2C0]; ppszPathOut
0x1800d4184  mov     r8d, 18h; dwFlags
0x1800d418a  lea     rdx, [rbp+1F0h+FindFileData.cFileName]; pszMore
0x1800d418e  mov     rcx, rbx; pszPathIn
0x1800d4191  call    cs:__imp_PathAllocCombine
0x1800d4198  nop     dword ptr [rax+rax+00h]
0x1800d419d  mov     esi, eax
0x1800d419f  test    eax, eax
0x1800d41a1  js      loc_1800D44C2
0x1800d41a7  test    byte ptr [rsp+2F0h+FindFileData.dwFileAttributes], 10h
0x1800d41ac  jz      loc_1800D424B
0x1800d41b2  mov     rdx, [rsp+2F0h+var_2C0]
0x1800d41b7  lea     r8, [rsp+2F0h+FindFileData]
0x1800d41bc  lea     rcx, [rsp+2F0h+hFile]
0x1800d41c1  call    ?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z; wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)
0x1800d41c6  mov     r8, [rsp+2F0h+hFile]
0x1800d41cb  lea     rax, [r8-1]
0x1800d41cf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800d41d3  ja      short loc_1800D4215
0x1800d41d5  mov     rcx, [rsp+2F0h+var_2C0]
0x1800d41da  mov     edx, r15d
0x1800d41dd  and     edx, 0FFFFFFFEh
0x1800d41e0  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x1800d41e5  mov     esi, eax
0x1800d41e7  test    eax, eax
0x1800d41e9  jns     short loc_1800D423C
0x1800d41eb  mov     rcx, [rbp+1F8h]; this
0x1800d41f2  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800d41f9  mov     r9d, eax; char *
0x1800d41fc  mov     edx, 12Ch; void *
0x1800d4201  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4206  lea     rcx, [rsp+2F0h+hFile]
0x1800d420b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800d4210  jmp     loc_1800D44DD
0x1800d4215  test    [rsp+2F0h+FindFileData.dwFileAttributes], 400h
0x1800d421d  jz      loc_1800D43C5
0x1800d4223  mov     rcx, [rsp+2F0h+var_2C0]; lpPathName
0x1800d4228  call    cs:__imp_RemoveDirectoryW
0x1800d422f  nop     dword ptr [rax+rax+00h]
0x1800d4234  test    eax, eax
0x1800d4236  jz      loc_1800D43A6
0x1800d423c  lea     rcx, [rsp+2F0h+hFile]
0x1800d4241  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800d4246  jmp     loc_1800D42CF
0x1800d424b  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x1800d4250  call    cs:__imp_DeleteFileW
0x1800d4257  nop     dword ptr [rax+rax+00h]
0x1800d425c  test    eax, eax
0x1800d425e  jnz     short loc_1800D42CF
0x1800d4260  test    r15b, 2
0x1800d4264  jz      loc_1800D4448
0x1800d426a  call    cs:__imp_GetLastError
0x1800d4271  nop     dword ptr [rax+rax+00h]
0x1800d4276  cmp     eax, 5
0x1800d4279  jnz     loc_1800D4448
0x1800d427f  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x1800d4284  call    cs:__imp_GetFileAttributesW
0x1800d428b  nop     dword ptr [rax+rax+00h]
0x1800d4290  test    al, 1
0x1800d4292  jz      loc_1800D4441
0x1800d4298  and     eax, 0FFFFFFFEh
0x1800d429b  mov     ecx, 80h
0x1800d42a0  cmovz   eax, ecx
0x1800d42a3  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x1800d42a8  mov     edx, eax; dwFileAttributes
0x1800d42aa  call    cs:__imp_SetFileAttributesW
0x1800d42b1  nop     dword ptr [rax+rax+00h]
0x1800d42b6  mov     rcx, [rsp+2F0h+var_2C0]; lpFileName
0x1800d42bb  call    cs:__imp_DeleteFileW
0x1800d42c2  nop     dword ptr [rax+rax+00h]
0x1800d42c7  test    eax, eax
0x1800d42c9  jz      loc_1800D4422
0x1800d42cf  lea     rcx, [rsp+2F0h+var_2C0]
0x1800d42d4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800d42d9  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x1800d42de  mov     rcx, rdi; hFindFile
0x1800d42e1  call    cs:__imp_FindNextFileW
0x1800d42e8  nop     dword ptr [rax+rax+00h]
0x1800d42ed  test    eax, eax
0x1800d42ef  jnz     loc_1800D4142
0x1800d42f5  call    cs:__imp_GetLastError
0x1800d42fc  nop     dword ptr [rax+rax+00h]
0x1800d4301  cmp     eax, 12h
0x1800d4304  jnz     loc_1800D448F
0x1800d430a  test    r15b, 1
0x1800d430e  jnz     loc_1800D449D
0x1800d4314  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1800d4318  jz      loc_1800D4472
0x1800d431e  lea     ebx, [rax-0Eh]
0x1800d4321  mov     dword ptr [rsp+2F0h+hFile], 3
0x1800d4329  mov     r9d, ebx; dwBufferSize
0x1800d432c  lea     r8, [rsp+2F0h+hFile]; lpFileInformation
0x1800d4331  lea     edx, [rax+3]; FileInformationClass
0x1800d4334  mov     rcx, r14; hFile
0x1800d4337  call    cs:__imp_SetFileInformationByHandle
0x1800d433e  nop     dword ptr [rax+rax+00h]
0x1800d4343  test    eax, eax
0x1800d4345  jnz     loc_1800D449D
0x1800d434b  call    cs:__imp_GetLastError
0x1800d4352  nop     dword ptr [rax+rax+00h]
0x1800d4357  cmp     eax, 5
0x1800d435a  jz      loc_1800D444F
0x1800d4360  lea     r9d, [rbx-3]; dwBufferSize
0x1800d4364  mov     [rsp+2F0h+FileInformation], 1
0x1800d4369  lea     r8, [rsp+2F0h+FileInformation]; lpFileInformation
0x1800d436e  mov     edx, ebx; FileInformationClass
0x1800d4370  mov     rcx, r14; hFile
0x1800d4373  call    cs:__imp_SetFileInformationByHandle
0x1800d437a  nop     dword ptr [rax+rax+00h]
0x1800d437f  test    eax, eax
0x1800d4381  jnz     loc_1800D449D
0x1800d4387  mov     edx, 171h; void *
0x1800d438c  mov     rcx, [rbp+1F8h]; this
0x1800d4393  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800d439a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d439f  mov     esi, eax
0x1800d43a1  jmp     loc_1800D44E7
0x1800d43a6  mov     rcx, [rbp+1F8h]; this
0x1800d43ad  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800d43b4  mov     edx, 131h; void *
0x1800d43b9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d43be  mov     esi, eax
0x1800d43c0  jmp     loc_1800D4206
0x1800d43c5  call    cs:__imp_GetLastError
0x1800d43cc  nop     dword ptr [rax+rax+00h]
0x1800d43d1  test    eax, eax
0x1800d43d3  jz      short loc_1800D43F2
0x1800d43d5  mov     rcx, [rbp+1F8h]; this
0x1800d43dc  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800d43e3  mov     r9d, eax; char *
0x1800d43e6  mov     edx, 136h; void *
0x1800d43eb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800d43f0  jmp     short loc_1800D43BE
0x1800d43f2  lea     rcx, [rsp+2F0h+hFile]
0x1800d43f7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800d43fc  lea     rcx, [rsp+2F0h+var_2C0]
0x1800d4401  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800d4406  lea     rcx, [rsp+2F0h+var_2B0]
0x1800d440b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800d4410  lea     rcx, [rsp+2F0h+ppszPathOut]
0x1800d4415  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800d441a  mov     esi, r12d
0x1800d441d  jmp     loc_1800D44FB
0x1800d4422  mov     edx, 150h; void *
0x1800d4427  mov     rcx, [rbp+1F8h]; this
0x1800d442e  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800d4435  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d443a  mov     esi, eax
0x1800d443c  jmp     loc_1800D44DD
0x1800d4441  mov     edx, 145h
0x1800d4446  jmp     short loc_1800D4427
0x1800d4448  mov     edx, 141h
0x1800d444d  jmp     short loc_1800D4427
0x1800d444f  mov     r9d, 5; char *
0x1800d4455  mov     edx, 176h; void *
0x1800d445a  mov     rcx, [rbp+1F8h]; this
0x1800d4461  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800d4468  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800d446d  jmp     loc_1800D439F
0x1800d4472  mov     rcx, rbx; lpPathName
0x1800d4475  call    cs:__imp_RemoveDirectoryW
0x1800d447c  nop     dword ptr [rax+rax+00h]
0x1800d4481  test    eax, eax
0x1800d4483  jnz     short loc_1800D449D
0x1800d4485  mov     edx, 17Dh
0x1800d448a  jmp     loc_1800D438C
0x1800d448f  test    eax, eax
0x1800d4491  jz      short loc_1800D449D
0x1800d4493  mov     r9d, eax
0x1800d4496  mov     edx, 15Ch
0x1800d449b  jmp     short loc_1800D445A
0x1800d449d  lea     rcx, [rsp+2F0h+var_2B0]
0x1800d44a2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800d44a7  lea     rcx, [rsp+2F0h+ppszPathOut]
0x1800d44ac  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800d44b1  lea     rcx, [rsp+2F0h+pszPathIn]
0x1800d44b6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800d44bb  xor     eax, eax
0x1800d44bd  jmp     loc_1800D4543
0x1800d44c2  mov     rcx, [rbp+1F8h]; this
0x1800d44c9  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800d44d0  mov     r9d, eax; char *
0x1800d44d3  mov     edx, 120h; void *
0x1800d44d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d44dd  lea     rcx, [rsp+2F0h+var_2C0]
0x1800d44e2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800d44e7  lea     rcx, [rsp+2F0h+var_2B0]
0x1800d44ec  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800d44f1  lea     rcx, [rsp+2F0h+ppszPathOut]
0x1800d44f6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800d44fb  lea     rcx, [rsp+2F0h+pszPathIn]
0x1800d4500  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800d4505  mov     eax, esi
0x1800d4507  jmp     short loc_1800D4543
0x1800d4509  mov     rcx, [rbp+1F8h]; this
0x1800d4510  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800d4517  mov     edx, 115h; void *
0x1800d451c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d4521  lea     rcx, [rsp+2F0h+var_2B0]
0x1800d4526  mov     ebx, eax
0x1800d4528  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
  ... truncated ...
```

# wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)

- ea: `0x180103bc4`
- end: `0x1801040db`
- name: `?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z`
- size: `1303`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180103bc4`
- `0x1801040e4`
- `0x180107abc`
- `0x18010b6d4`
- `0x18010fd74`

## callees

- `0x180019000`
- `0x180019fc4`
- `0x1800ece3c`
- `0x1800ece5c`
- `0x1800f7240`
- `0x1800f8cb0`
- `0x1800f90ec`
- `0x1800f9534`
- `0x1800f9558`
- `0x1800f9850`
- `0x180103bc4`
- `0x180104108`
- `0x18010416c`
- `0x180104320`
- `0x18010438c`
- `0x18010440c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180103ec8`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180103ef8`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180103ec8`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180103ef8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180103e33`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180103e33`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180103e0b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180103e5e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180103e0b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180103e5e`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180103e53`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180103e53`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180103e7e`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180103e7e`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180103dec`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180103fed`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180103dec`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180103fed`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180103d01`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180103d01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103e1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103e8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103ed6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103f44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103e1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103e8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103ed6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103f44`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180103cb9`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180103d5b`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180103cb9`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180103d5b`

## string_xrefs

- `0x180103c77`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180103ccc`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180103db6`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180103f12`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180103f2c`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180103f55`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180103fa6`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180103fd9`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18010403b`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180104082`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

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
      v17 = wil::RemoveDirectoryRecursiveNoThrow(v34, v4 & 0xFFFFFFFE, hFile);
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
0x180103bc4  mov     [rsp-8+arg_18], rbx
0x180103bc9  push    rbp
0x180103bca  push    rsi
0x180103bcb  push    rdi
0x180103bcc  push    r14
0x180103bce  push    r15
0x180103bd0  lea     rbp, [rsp-1C0h]
0x180103bd8  sub     rsp, 2C0h
0x180103bdf  mov     rax, cs:__security_cookie
0x180103be6  xor     rax, rsp
0x180103be9  mov     [rbp+1E0h+var_30], rax
0x180103bf0  mov     r14, r8
0x180103bf3  mov     [rsp+2E0h+pszPathIn], 0
0x180103bfc  mov     r15d, edx
0x180103bff  mov     rbx, rcx
0x180103c02  call    ?is_extended_length_path@wil@@YA_NPEBG@Z; wil::is_extended_length_path(ushort const *)
0x180103c07  test    al, al
0x180103c09  jz      short loc_180103C55
0x180103c0b  or      r8, 0FFFFFFFFFFFFFFFFh
0x180103c0f  lea     rcx, [rsp+2E0h+var_2A0]
0x180103c14  mov     rdx, rbx
0x180103c17  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180103c1c  lea     rdx, [rsp+2E0h+var_2A0]
0x180103c21  lea     rcx, [rsp+2E0h+pszPathIn]
0x180103c26  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180103c2b  lea     rcx, [rsp+2E0h+var_2A0]
0x180103c30  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180103c35  mov     rbx, [rsp+2E0h+pszPathIn]
0x180103c3a  test    rbx, rbx
0x180103c3d  jz      short loc_180103C46
0x180103c3f  mov     edi, 10h
0x180103c44  jmp     short loc_180103C92
0x180103c46  mov     esi, 8007000Eh
0x180103c4b  mov     edx, 104h
0x180103c50  mov     r9d, esi
0x180103c53  jmp     short loc_180103C70
0x180103c55  lea     rdx, [rsp+2E0h+pszPathIn]
0x180103c5a  mov     rcx, rbx
0x180103c5d  call    ??$GetFullPathNameW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEAPEBG@Z; wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const * *)
0x180103c62  mov     esi, eax
0x180103c64  test    eax, eax
0x180103c66  jns     short loc_180103C88
0x180103c68  mov     r9d, eax; char *
0x180103c6b  mov     edx, 10Ch; void *
0x180103c70  mov     rcx, [rbp+1E8h]; this
0x180103c77  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180103c7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180103c83  jmp     loc_18010406D
0x180103c88  mov     rbx, [rsp+2E0h+pszPathIn]
0x180103c8d  mov     edi, 1
0x180103c92  xor     edx, edx
0x180103c94  mov     [rsp+2E0h+ppszPathOut], 0
0x180103c9d  lea     rcx, [rsp+2E0h+ppszPathOut]
0x180103ca2  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180103ca7  lea     r9, [rsp+2E0h+ppszPathOut]; ppszPathOut
0x180103cac  mov     r8d, edi; dwFlags
0x180103caf  lea     rdx, Delimiter; "*"
0x180103cb6  mov     rcx, rbx; pszPathIn
0x180103cb9  call    cs:__imp_PathAllocCombine
0x180103cbf  mov     esi, eax
0x180103cc1  test    eax, eax
0x180103cc3  jns     short loc_180103CE5
0x180103cc5  mov     rcx, [rbp+1E8h]; this
0x180103ccc  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180103cd3  mov     r9d, eax; char *
0x180103cd6  mov     edx, 111h; void *
0x180103cdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180103ce0  jmp     loc_180104063
0x180103ce5  xor     edx, edx; Val
0x180103ce7  lea     rcx, [rsp+2E0h+FindFileData]; void *
0x180103cec  mov     r8d, 250h; Size
0x180103cf2  call    memset_0
0x180103cf7  mov     rcx, [rsp+2E0h+ppszPathOut]; lpFileName
0x180103cfc  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x180103d01  call    cs:__imp_FindFirstFileW
0x180103d07  mov     rdi, rax
0x180103d0a  mov     [rsp+2E0h+var_2A0], rax
0x180103d0f  dec     rax
0x180103d12  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180103d16  ja      loc_18010407B
0x180103d1c  test    byte ptr [rsp+2E0h+FindFileData.dwFileAttributes], 10h
0x180103d21  jz      short loc_180103D34
0x180103d23  lea     rcx, [rbp+1E0h+FindFileData.cFileName]; this
0x180103d27  call    ?path_is_dot_or_dotdot@wil@@YA_NPEBG@Z; wil::path_is_dot_or_dotdot(ushort const *)
0x180103d2c  test    al, al
0x180103d2e  jnz     loc_180103E76
0x180103d34  xor     edx, edx
0x180103d36  mov     [rsp+2E0h+var_2B0], 0
0x180103d3f  lea     rcx, [rsp+2E0h+var_2B0]
0x180103d44  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180103d49  lea     r9, [rsp+2E0h+var_2B0]; ppszPathOut
0x180103d4e  mov     r8d, 18h; dwFlags
0x180103d54  lea     rdx, [rbp+1E0h+FindFileData.cFileName]; pszMore
0x180103d58  mov     rcx, rbx; pszPathIn
0x180103d5b  call    cs:__imp_PathAllocCombine
0x180103d61  mov     esi, eax
0x180103d63  test    eax, eax
0x180103d65  js      loc_180104034
0x180103d6b  test    byte ptr [rsp+2E0h+FindFileData.dwFileAttributes], 10h
0x180103d70  jz      loc_180103E06
0x180103d76  mov     rdx, [rsp+2E0h+var_2B0]
0x180103d7b  lea     r8, [rsp+2E0h+FindFileData]
0x180103d80  lea     rcx, [rsp+2E0h+hFile]
0x180103d85  call    ?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z; wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)
0x180103d8a  mov     r8, [rsp+2E0h+hFile]
0x180103d8f  lea     rax, [r8-1]
0x180103d93  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180103d97  ja      short loc_180103DD9
0x180103d99  mov     rcx, [rsp+2E0h+var_2B0]
0x180103d9e  mov     edx, r15d
0x180103da1  and     edx, 0FFFFFFFEh
0x180103da4  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x180103da9  mov     esi, eax
0x180103dab  test    eax, eax
0x180103dad  jns     short loc_180103DFA
0x180103daf  mov     rcx, [rbp+1E8h]; this
0x180103db6  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180103dbd  mov     r9d, eax; char *
0x180103dc0  mov     edx, 12Ch; void *
0x180103dc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180103dca  lea     rcx, [rsp+2E0h+hFile]
0x180103dcf  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180103dd4  jmp     loc_18010404F
0x180103dd9  test    [rsp+2E0h+FindFileData.dwFileAttributes], 400h
0x180103de1  jz      loc_180103F44
0x180103de7  mov     rcx, [rsp+2E0h+var_2B0]; lpPathName
0x180103dec  call    cs:__imp_RemoveDirectoryW
0x180103df2  test    eax, eax
0x180103df4  jz      loc_180103F25
0x180103dfa  lea     rcx, [rsp+2E0h+hFile]
0x180103dff  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180103e04  jmp     short loc_180103E6C
0x180103e06  mov     rcx, [rsp+2E0h+var_2B0]; lpFileName
0x180103e0b  call    cs:__imp_DeleteFileW
0x180103e11  test    eax, eax
0x180103e13  jnz     short loc_180103E6C
0x180103e15  test    r15b, 2
0x180103e19  jz      loc_180103FC0
0x180103e1f  call    cs:__imp_GetLastError
0x180103e25  cmp     eax, 5
0x180103e28  jnz     loc_180103FC0
0x180103e2e  mov     rcx, [rsp+2E0h+var_2B0]; lpFileName
0x180103e33  call    cs:__imp_GetFileAttributesW
0x180103e39  test    al, 1
0x180103e3b  jz      loc_180103FB9
0x180103e41  and     eax, 0FFFFFFFEh
0x180103e44  mov     ecx, 80h
0x180103e49  cmovz   eax, ecx
0x180103e4c  mov     rcx, [rsp+2E0h+var_2B0]; lpFileName
0x180103e51  mov     edx, eax; dwFileAttributes
0x180103e53  call    cs:__imp_SetFileAttributesW
0x180103e59  mov     rcx, [rsp+2E0h+var_2B0]; lpFileName
0x180103e5e  call    cs:__imp_DeleteFileW
0x180103e64  test    eax, eax
0x180103e66  jz      loc_180103F9A
0x180103e6c  lea     rcx, [rsp+2E0h+var_2B0]
0x180103e71  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180103e76  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x180103e7b  mov     rcx, rdi; hFindFile
0x180103e7e  call    cs:__imp_FindNextFileW
0x180103e84  test    eax, eax
0x180103e86  jnz     loc_180103D1C
0x180103e8c  call    cs:__imp_GetLastError
0x180103e92  cmp     eax, 12h
0x180103e95  jnz     loc_180104001
0x180103e9b  test    r15b, 1
0x180103e9f  jnz     loc_18010400F
0x180103ea5  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180103ea9  jz      loc_180103FEA
0x180103eaf  lea     ebx, [rax-0Eh]
0x180103eb2  mov     dword ptr [rsp+2E0h+hFile], 3
0x180103eba  mov     r9d, ebx; dwBufferSize
0x180103ebd  lea     r8, [rsp+2E0h+hFile]; lpFileInformation
0x180103ec2  lea     edx, [rax+3]; FileInformationClass
0x180103ec5  mov     rcx, r14; hFile
0x180103ec8  call    cs:__imp_SetFileInformationByHandle
0x180103ece  test    eax, eax
0x180103ed0  jnz     loc_18010400F
0x180103ed6  call    cs:__imp_GetLastError
0x180103edc  cmp     eax, 5
0x180103edf  jz      loc_180103FC7
0x180103ee5  lea     r9d, [rbx-3]; dwBufferSize
0x180103ee9  mov     [rsp+2E0h+FileInformation], 1
0x180103eee  lea     r8, [rsp+2E0h+FileInformation]; lpFileInformation
0x180103ef3  mov     edx, ebx; FileInformationClass
0x180103ef5  mov     rcx, r14; hFile
0x180103ef8  call    cs:__imp_SetFileInformationByHandle
0x180103efe  test    eax, eax
0x180103f00  jnz     loc_18010400F
0x180103f06  mov     edx, 171h; void *
0x180103f0b  mov     rcx, [rbp+1E8h]; this
0x180103f12  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180103f19  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180103f1e  mov     esi, eax
0x180103f20  jmp     loc_180104059
0x180103f25  mov     rcx, [rbp+1E8h]; this
0x180103f2c  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180103f33  mov     edx, 131h; void *
0x180103f38  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180103f3d  mov     esi, eax
0x180103f3f  jmp     loc_180103DCA
0x180103f44  call    cs:__imp_GetLastError
0x180103f4a  test    eax, eax
0x180103f4c  jz      short loc_180103F6B
0x180103f4e  mov     rcx, [rbp+1E8h]; this
0x180103f55  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180103f5c  mov     r9d, eax; char *
0x180103f5f  mov     edx, 136h; void *
0x180103f64  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180103f69  jmp     short loc_180103F3D
0x180103f6b  lea     rcx, [rsp+2E0h+hFile]
0x180103f70  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180103f75  lea     rcx, [rsp+2E0h+var_2B0]
0x180103f7a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180103f7f  lea     rcx, [rsp+2E0h+var_2A0]
0x180103f84  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180103f89  lea     rcx, [rsp+2E0h+ppszPathOut]
0x180103f8e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180103f93  xor     esi, esi
0x180103f95  jmp     loc_18010406D
0x180103f9a  mov     edx, 150h; void *
0x180103f9f  mov     rcx, [rbp+1E8h]; this
0x180103fa6  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180103fad  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180103fb2  mov     esi, eax
0x180103fb4  jmp     loc_18010404F
0x180103fb9  mov     edx, 145h
0x180103fbe  jmp     short loc_180103F9F
0x180103fc0  mov     edx, 141h
0x180103fc5  jmp     short loc_180103F9F
0x180103fc7  mov     r9d, 5; char *
0x180103fcd  mov     edx, 176h; void *
0x180103fd2  mov     rcx, [rbp+1E8h]; this
0x180103fd9  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180103fe0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180103fe5  jmp     loc_180103F1E
0x180103fea  mov     rcx, rbx; lpPathName
0x180103fed  call    cs:__imp_RemoveDirectoryW
0x180103ff3  test    eax, eax
0x180103ff5  jnz     short loc_18010400F
0x180103ff7  mov     edx, 17Dh
0x180103ffc  jmp     loc_180103F0B
0x180104001  test    eax, eax
0x180104003  jz      short loc_18010400F
0x180104005  mov     r9d, eax
0x180104008  mov     edx, 15Ch
0x18010400d  jmp     short loc_180103FD2
0x18010400f  lea     rcx, [rsp+2E0h+var_2A0]
0x180104014  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180104019  lea     rcx, [rsp+2E0h+ppszPathOut]
0x18010401e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180104023  lea     rcx, [rsp+2E0h+pszPathIn]
0x180104028  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010402d  xor     eax, eax
0x18010402f  jmp     loc_1801040B5
0x180104034  mov     rcx, [rbp+1E8h]; this
0x18010403b  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180104042  mov     r9d, eax; char *
0x180104045  mov     edx, 120h; void *
0x18010404a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010404f  lea     rcx, [rsp+2E0h+var_2B0]
0x180104054  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180104059  lea     rcx, [rsp+2E0h+var_2A0]
0x18010405e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180104063  lea     rcx, [rsp+2E0h+ppszPathOut]
0x180104068  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010406d  lea     rcx, [rsp+2E0h+pszPathIn]
0x180104072  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180104077  mov     eax, esi
0x180104079  jmp     short loc_1801040B5
0x18010407b  mov     rcx, [rbp+1E8h]; this
0x180104082  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180104089  mov     edx, 115h; void *
0x18010408e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180104093  lea     rcx, [rsp+2E0h+var_2A0]
0x180104098  mov     ebx, eax
0x18010409a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18010409f  lea     rcx, [rsp+2E0h+ppszPathOut]
0x1801040a4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801040a9  lea     rcx, [rsp+2E0h+pszPathIn]
0x1801040ae  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801040b3  mov     eax, ebx
0x1801040b5  mov     rcx, [rbp+1E0h+var_30]
0x1801040bc  xor     rcx, rsp; StackCookie
0x1801040bf  call    __security_check_cookie
0x1801040c4  mov     rbx, [rsp+2E0h+arg_18]
0x1801040cc  add     rsp, 2C0h
0x1801040d3  pop     r15
0x1801040d5  pop     r14
0x1801040d7  pop     rdi
0x1801040d8  pop     rsi
0x1801040d9  pop     rbp
0x1801040da  retn
```

# wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)

- ea: `0x1800161e4`
- end: `0x180016838`
- name: `?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z`
- size: `1620`
- prototype: `__int64 __fastcall(char *, int, void *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800161e4`
- `0x180017020`

## callees

- `0x180007654`
- `0x180007674`
- `0x180009a8c`
- `0x18000c538`
- `0x1800161e4`
- `0x180017914`
- `0x180033e9a`
- `0x180033ea6`
- `0x180033ed0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800164f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001655f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800165d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001661b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016698`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800164f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001655f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800165d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001661b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016698`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001650b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001650b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800164b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016502`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016543`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800166cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800164b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016502`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016543`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800166cc`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180016438`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180016438`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180016573`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180016573`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180016593`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180016593`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800165c3`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800165c3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180016405`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180016405`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18001660d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18001663d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18001660d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18001663d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001654b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001659e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001654b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001659e`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180016527`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180016777`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180016527`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180016777`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800164ca`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800166e5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800167e8`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800164ca`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800166e5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800167e8`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001636d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001636d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800162fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800164c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800164da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800164e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800165b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800166dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800166f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016703`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016738`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800167f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016806`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800162fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800164c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800164da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800164e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800165b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800166dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800166f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016703`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016738`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800167f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016806`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180016327`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800163c5`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180016327`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800163c5`

## string_xrefs

- `0x18001625b`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1800162db`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18001633a`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18001649a`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180016657`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180016671`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1800166a9`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x18001671c`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180016763`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1800167a8`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1800167c8`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

## pseudocode

```c
__int64 __fastcall wil::RemoveDirectoryRecursiveNoThrow(char *a1, int a2, void *a3)
{
  const char *v6; // r9
  WCHAR *v7; // rbx
  unsigned int v8; // ebx
  ULONG v10; // r8d
  HRESULT v11; // eax
  unsigned int LastError; // edi
  char *FirstFileW; // rsi
  const char *v14; // r9
  HRESULT v15; // eax
  HANDLE FileW; // rax
  __int64 v17; // rdi
  int v18; // eax
  unsigned int v19; // r14d
  DWORD v20; // r14d
  const char *v21; // r9
  const char *v22; // r9
  DWORD FileAttributesW; // eax
  DWORD v24; // eax
  DWORD v25; // eax
  const char *v26; // r9
  __int64 v27; // rdx
  int v28; // eax
  int v29; // eax
  DWORD v30; // eax
  __int64 v31; // rdx
  __int64 v32; // r9
  __int64 v33; // rdx
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  PWSTR ppszPathOut; // [rsp+48h] [rbp-B8h] BYREF
  char FileInformation[8]; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR pszPathIn; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v39[8]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v40[13]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v41; // [rsp+D0h] [rbp-30h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+378h] [rbp+278h]

  hMem = 0;
  if ( !wcsncmp_0((const wchar_t *)a1, L"\\\\?\\", 4u) )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &pszPathIn,
      a1,
      0xFFFFFFFFFFFFFFFFuLL,
      v6);
    v7 = (WCHAR *)pszPathIn;
    if ( !pszPathIn )
    {
      v8 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x104,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
        (const char *)0x8007000ELL,
        dwCreationDisposition);
      return v8;
    }
    v10 = 16;
  }
  else
  {
    pszPathIn = (PCWSTR)a1;
    v40[0] = &wistd::__function::__func<_lambda_dfced21692aadc2a556e46caeccd40ea_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
    v40[1] = &pszPathIn;
    v41 = v40;
    v8 = wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
           (char *)&hMem,
           (__int64)v39);
    if ( v41 )
      (*(void (__fastcall **)(_QWORD *))(*v41 + 24LL))(v41);
    if ( (v8 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10C,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
        (const char *)v8,
        dwCreationDisposition);
      if ( hMem )
        LocalFree(hMem);
      return v8;
    }
    v7 = (WCHAR *)hMem;
    v10 = 1;
  }
  ppszPathOut = 0;
  v11 = PathAllocCombine(v7, L"*", v10, &ppszPathOut);
  LastError = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x111,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
      (const char *)(unsigned int)v11,
      dwCreationDisposition);
LABEL_93:
    if ( ppszPathOut )
      LocalFree(ppszPathOut);
    if ( v7 )
      LocalFree(v7);
    return LastError;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (char *)FindFirstFileW(ppszPathOut, &FindFileData);
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x115,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                  v14);
    goto LABEL_93;
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
    v15 = PathAllocCombine(v7, FindFileData.cFileName, 0x18u, (PWSTR *)&hMem);
    LastError = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x120,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
        (const char *)(unsigned int)v15,
        dwCreationDisposition);
      goto LABEL_80;
    }
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
    {
      if ( !DeleteFileW((LPCWSTR)hMem) )
      {
        if ( (a2 & 2) == 0 || GetLastError() != 5 )
        {
          v31 = 321;
LABEL_79:
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)v31,
                        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                        v22);
LABEL_80:
          if ( hMem )
            LocalFree(hMem);
LABEL_92:
          FindClose(FirstFileW);
          goto LABEL_93;
        }
        FileAttributesW = GetFileAttributesW((LPCWSTR)hMem);
        if ( (FileAttributesW & 1) == 0 )
        {
          v31 = 325;
          goto LABEL_79;
        }
        v24 = FileAttributesW & 0xFFFFFFFE;
        if ( !v24 )
          v24 = 128;
        SetFileAttributesW((LPCWSTR)hMem, v24);
        if ( !DeleteFileW((LPCWSTR)hMem) )
        {
          v31 = 336;
          goto LABEL_79;
        }
      }
      goto LABEL_52;
    }
    FileW = CreateFileW((LPCWSTR)hMem, 0x80010000, 1u, 0, 3u, 0x2200000u, 0);
    v17 = (__int64)FileW;
    if ( FileW != (HANDLE)-1LL && FileW )
    {
      pszPathIn = 0;
      if ( GetFileInformationByHandleEx(FileW, FileAttributeTagInfo, &pszPathIn, 8u)
        && ((unsigned __int8)pszPathIn & 0x10) != 0
        && (((unsigned __int16)pszPathIn & 0x400) == 0
         || (HIDWORD(pszPathIn) & 0x10000000) != 0
         || HIDWORD(pszPathIn) == -2147483624) )
      {
        FindFileData.dwReserved0 = HIDWORD(pszPathIn);
        FindFileData.dwFileAttributes = (unsigned int)pszPathIn;
        v18 = wil::RemoveDirectoryRecursiveNoThrow(hMem, a2 & 0xFFFFFFFE, v17);
        v19 = v18;
        if ( v18 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x12C,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
            (const char *)(unsigned int)v18,
            dwCreationDisposition);
LABEL_31:
          CloseHandle((HANDLE)v17);
LABEL_32:
          if ( hMem )
            LocalFree(hMem);
          FindClose(FirstFileW);
          if ( ppszPathOut )
            LocalFree(ppszPathOut);
          if ( v7 )
            LocalFree(v7);
          return v19;
        }
LABEL_43:
        if ( v17 )
          CloseHandle((HANDLE)v17);
        goto LABEL_52;
      }
      v20 = GetLastError();
      CloseHandle((HANDLE)v17);
      SetLastError(v20);
      v17 = -1;
    }
    if ( (FindFileData.dwFileAttributes & 0x400) == 0 )
    {
      v30 = GetLastError();
      if ( !v30 )
      {
        if ( (unsigned __int64)(v17 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle((HANDLE)v17);
        if ( hMem )
          LocalFree(hMem);
        goto LABEL_73;
      }
      v29 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x136,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
              (const char *)v30,
              dwCreationDisposition);
LABEL_65:
      v19 = v29;
      if ( (unsigned __int64)(v17 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
        goto LABEL_32;
      goto LABEL_31;
    }
    if ( !RemoveDirectoryW((LPCWSTR)hMem) )
    {
      v29 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x131,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
              v21);
      goto LABEL_65;
    }
    if ( v17 != -1 )
      goto LABEL_43;
LABEL_52:
    if ( hMem )
      LocalFree(hMem);
  }
  while ( FindNextFileW(FirstFileW, &FindFileData) );
  v25 = GetLastError();
  if ( v25 != 18 )
  {
    if ( !v25 )
      goto LABEL_73;
    v32 = v25;
    v33 = 348;
    goto LABEL_85;
  }
  if ( (a2 & 1) != 0 )
    goto LABEL_73;
  if ( a3 == (void *)-1LL )
  {
    if ( RemoveDirectoryW(v7) )
      goto LABEL_73;
    v27 = 381;
LABEL_62:
    v28 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v27,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
            v26);
LABEL_63:
    LastError = v28;
    goto LABEL_92;
  }
  LODWORD(hMem) = 3;
  if ( SetFileInformationByHandle(a3, FileRenameInfoEx|FileDispositionInfo, &hMem, 4u) )
    goto LABEL_73;
  if ( GetLastError() == 5 )
  {
    v32 = 5;
    v33 = 374;
LABEL_85:
    v28 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v33,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
            (const char *)v32,
            dwCreationDisposition);
    goto LABEL_63;
  }
  FileInformation[0] = 1;
  if ( !SetFileInformationByHandle(a3, FileDispositionInfo, FileInformation, 1u) )
  {
    v27 = 369;
    goto LABEL_62;
  }
LABEL_73:
  FindClose(FirstFileW);
  if ( ppszPathOut )
    LocalFree(ppszPathOut);
  if ( v7 )
    LocalFree(v7);
  return 0;
}

```

## disassembly

```asm
0x1800161e4  mov     [rsp-8+arg_18], rbx
0x1800161e9  push    rbp
0x1800161ea  push    rsi
0x1800161eb  push    rdi
0x1800161ec  push    r12
0x1800161ee  push    r13
0x1800161f0  push    r14
0x1800161f2  push    r15
0x1800161f4  lea     rbp, [rsp-240h]
0x1800161fc  sub     rsp, 340h
0x180016203  mov     rax, cs:__security_cookie
0x18001620a  xor     rax, rsp
0x18001620d  mov     [rbp+270h+var_40], rax
0x180016214  xor     r13d, r13d
0x180016217  mov     r15, r8
0x18001621a  mov     r12d, edx
0x18001621d  mov     [rsp+370h+hMem], r13
0x180016222  lea     rdx, String2; "\\\\?\\"
0x180016229  mov     rbx, rcx
0x18001622c  lea     r8d, [r13+4]; MaxCount
0x180016230  call    wcsncmp_0
0x180016235  test    eax, eax
0x180016237  jnz     short loc_180016286
0x180016239  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001623d  lea     rcx, [rsp+370h+pszPathIn]
0x180016242  mov     rdx, rbx
0x180016245  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001624a  mov     rbx, [rsp+370h+pszPathIn]
0x18001624f  test    rbx, rbx
0x180016252  jnz     short loc_18001627B
0x180016254  mov     rcx, [rbp+278h]; this
0x18001625b  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180016262  mov     ebx, 8007000Eh
0x180016267  mov     edx, 104h; void *
0x18001626c  mov     r9d, ebx; char *
0x18001626f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016274  mov     eax, ebx
0x180016276  jmp     loc_18001680E
0x18001627b  mov     r8d, 10h
0x180016281  jmp     loc_180016313
0x180016286  lea     rax, ??_7?$__func@V_lambda_dfced21692aadc2a556e46caeccd40ea_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_dfced21692aadc2a556e46caeccd40ea_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x18001628d  mov     [rsp+370h+pszPathIn], rbx
0x180016292  mov     [rsp+370h+var_308], rax
0x180016297  lea     rdx, [rsp+370h+var_310]
0x18001629c  lea     rax, [rsp+370h+pszPathIn]
0x1800162a1  mov     [rsp+370h+var_300], rax
0x1800162a6  lea     rcx, [rsp+370h+hMem]
0x1800162ab  lea     rax, [rsp+370h+var_308]
0x1800162b0  mov     [rbp+270h+var_2A0], rax
0x1800162b4  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)
0x1800162b9  mov     rcx, [rbp+270h+var_2A0]
0x1800162bd  mov     ebx, eax
0x1800162bf  test    rcx, rcx
0x1800162c2  jz      short loc_1800162D0
0x1800162c4  mov     rdx, [rcx]
0x1800162c7  mov     rax, [rdx+18h]
0x1800162cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162d0  test    ebx, ebx
0x1800162d2  jns     short loc_180016308
0x1800162d4  mov     rcx, [rbp+278h]; this
0x1800162db  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800162e2  mov     r9d, ebx; char *
0x1800162e5  mov     edx, 10Ch; void *
0x1800162ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800162ef  mov     rcx, [rsp+370h+hMem]; hMem
0x1800162f4  test    rcx, rcx
0x1800162f7  jz      loc_180016274
0x1800162fd  call    cs:__imp_LocalFree
0x180016303  jmp     loc_180016274
0x180016308  mov     rbx, [rsp+370h+hMem]
0x18001630d  mov     r8d, 1; dwFlags
0x180016313  lea     r9, [rsp+370h+ppszPathOut]; ppszPathOut
0x180016318  mov     [rsp+370h+ppszPathOut], r13
0x18001631d  lea     rdx, pszMore; "*"
0x180016324  mov     rcx, rbx; pszPathIn
0x180016327  call    cs:__imp_PathAllocCombine
0x18001632d  mov     edi, eax
0x18001632f  test    eax, eax
0x180016331  jns     short loc_180016353
0x180016333  mov     rcx, [rbp+278h]; this
0x18001633a  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180016341  mov     r9d, eax; char *
0x180016344  mov     edx, 111h; void *
0x180016349  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001634e  jmp     loc_1800167EE
0x180016353  xor     edx, edx; Val
0x180016355  lea     rcx, [rbp+270h+FindFileData]; void *
0x180016359  mov     r8d, 250h; Size
0x18001635f  call    memset_0
0x180016364  mov     rcx, [rsp+370h+ppszPathOut]; lpFileName
0x180016369  lea     rdx, [rbp+270h+FindFileData]; lpFindFileData
0x18001636d  call    cs:__imp_FindFirstFileW
0x180016373  mov     rsi, rax
0x180016376  dec     rax
0x180016379  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001637d  ja      loc_1800167C1
0x180016383  test    byte ptr [rbp+270h+FindFileData.dwFileAttributes], 10h
0x180016387  jz      short loc_1800163AE
0x180016389  cmp     [rbp+270h+FindFileData.cFileName], 2Eh ; '.'
0x18001638e  jnz     short loc_1800163AE
0x180016390  movzx   eax, [rbp+270h+FindFileData.cFileName+2]
0x180016394  test    ax, ax
0x180016397  jz      loc_1800165BC
0x18001639d  cmp     ax, 2Eh ; '.'
0x1800163a1  jnz     short loc_1800163AE
0x1800163a3  cmp     [rbp+270h+FindFileData.cFileName+4], r13w
0x1800163a8  jz      loc_1800165BC
0x1800163ae  lea     r9, [rsp+370h+hMem]; ppszPathOut
0x1800163b3  mov     [rsp+370h+hMem], r13
0x1800163b8  mov     r8d, 18h; dwFlags
0x1800163be  lea     rdx, [rbp+270h+FindFileData.cFileName]; pszMore
0x1800163c2  mov     rcx, rbx; pszPathIn
0x1800163c5  call    cs:__imp_PathAllocCombine
0x1800163cb  mov     edi, eax
0x1800163cd  test    eax, eax
0x1800163cf  js      loc_1800167A1
0x1800163d5  test    byte ptr [rbp+270h+FindFileData.dwFileAttributes], 10h
0x1800163d9  mov     rcx, [rsp+370h+hMem]; lpFileName
0x1800163de  jz      loc_18001654B
0x1800163e4  xor     r9d, r9d; lpSecurityAttributes
0x1800163e7  mov     [rsp+370h+hTemplateFile], r13; hTemplateFile
0x1800163ec  mov     [rsp+370h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1800163f4  mov     edx, 80010000h; dwDesiredAccess
0x1800163f9  mov     [rsp+370h+dwCreationDisposition], 3; int
0x180016401  lea     r8d, [r9+1]; dwShareMode
0x180016405  call    cs:__imp_CreateFileW
0x18001640b  mov     rdi, rax
0x18001640e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180016412  jz      loc_180016515
0x180016418  test    rax, rax
0x18001641b  jz      loc_180016515
0x180016421  mov     r9d, 8; dwBufferSize
0x180016427  mov     [rsp+370h+pszPathIn], r13
0x18001642c  lea     r8, [rsp+370h+pszPathIn]; lpFileInformation
0x180016431  mov     rcx, rax; hFile
0x180016434  lea     edx, [r9+1]; FileInformationClass
0x180016438  call    cs:__imp_GetFileInformationByHandleEx
0x18001643e  test    eax, eax
0x180016440  jz      loc_1800164F6
0x180016446  mov     rax, [rsp+370h+pszPathIn]
0x18001644b  test    al, 10h
0x18001644d  jz      loc_1800164F6
0x180016453  mov     ecx, dword ptr [rsp+370h+pszPathIn+4]
0x180016457  bt      eax, 0Ah
0x18001645b  jnb     short loc_18001646F
0x18001645d  bt      ecx, 1Ch
0x180016461  jb      short loc_18001646F
0x180016463  cmp     ecx, 80000018h
0x180016469  jnz     loc_1800164F6
0x18001646f  mov     edx, r12d
0x180016472  mov     [rbp+270h+FindFileData.dwReserved0], ecx
0x180016475  mov     rcx, [rsp+370h+hMem]
0x18001647a  and     edx, 0FFFFFFFEh
0x18001647d  mov     r8, rdi
0x180016480  mov     [rbp+270h+FindFileData.dwFileAttributes], eax
0x180016483  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x180016488  mov     r14d, eax
0x18001648b  test    eax, eax
0x18001648d  jns     loc_18001653B
0x180016493  mov     rcx, [rbp+278h]; this
0x18001649a  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800164a1  mov     r9d, eax; char *
0x1800164a4  mov     edx, 12Ch; void *
0x1800164a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800164ae  mov     rcx, rdi; hObject
0x1800164b1  call    cs:__imp_CloseHandle
0x1800164b7  mov     rcx, [rsp+370h+hMem]; hMem
0x1800164bc  test    rcx, rcx
0x1800164bf  jz      short loc_1800164C7
0x1800164c1  call    cs:__imp_LocalFree
0x1800164c7  mov     rcx, rsi; hFindFile
0x1800164ca  call    cs:__imp_FindClose
0x1800164d0  mov     rcx, [rsp+370h+ppszPathOut]; hMem
0x1800164d5  test    rcx, rcx
0x1800164d8  jz      short loc_1800164E0
0x1800164da  call    cs:__imp_LocalFree
0x1800164e0  test    rbx, rbx
0x1800164e3  jz      short loc_1800164EE
0x1800164e5  mov     rcx, rbx; hMem
0x1800164e8  call    cs:__imp_LocalFree
0x1800164ee  mov     eax, r14d
0x1800164f1  jmp     loc_18001680E
0x1800164f6  call    cs:__imp_GetLastError
0x1800164fc  mov     rcx, rdi; hObject
0x1800164ff  mov     r14d, eax
0x180016502  call    cs:__imp_CloseHandle
0x180016508  mov     ecx, r14d; dwErrCode
0x18001650b  call    cs:__imp_SetLastError
0x180016511  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180016515  test    [rbp+270h+FindFileData.dwFileAttributes], 400h
0x18001651c  jz      loc_180016698
0x180016522  mov     rcx, [rsp+370h+hMem]; lpPathName
0x180016527  call    cs:__imp_RemoveDirectoryW
0x18001652d  test    eax, eax
0x18001652f  jz      loc_18001666A
0x180016535  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180016539  jz      short loc_1800165AC
0x18001653b  test    rdi, rdi
0x18001653e  jz      short loc_1800165AC
0x180016540  mov     rcx, rdi; hObject
0x180016543  call    cs:__imp_CloseHandle
0x180016549  jmp     short loc_1800165AC
0x18001654b  call    cs:__imp_DeleteFileW
0x180016551  test    eax, eax
0x180016553  jnz     short loc_1800165AC
0x180016555  test    r12b, 2
0x180016559  jz      loc_18001674A
0x18001655f  call    cs:__imp_GetLastError
0x180016565  cmp     eax, 5
0x180016568  jnz     loc_18001674A
0x18001656e  mov     rcx, [rsp+370h+hMem]; lpFileName
0x180016573  call    cs:__imp_GetFileAttributesW
0x180016579  test    al, 1
0x18001657b  jz      loc_180016743
0x180016581  and     eax, 0FFFFFFFEh
0x180016584  mov     ecx, 80h
0x180016589  cmovz   eax, ecx
0x18001658c  mov     rcx, [rsp+370h+hMem]; lpFileName
0x180016591  mov     edx, eax; dwFileAttributes
0x180016593  call    cs:__imp_SetFileAttributesW
0x180016599  mov     rcx, [rsp+370h+hMem]; lpFileName
0x18001659e  call    cs:__imp_DeleteFileW
0x1800165a4  test    eax, eax
0x1800165a6  jz      loc_180016710
0x1800165ac  mov     rcx, [rsp+370h+hMem]; hMem
0x1800165b1  test    rcx, rcx
0x1800165b4  jz      short loc_1800165BC
0x1800165b6  call    cs:__imp_LocalFree
0x1800165bc  lea     rdx, [rbp+270h+FindFileData]; lpFindFileData
0x1800165c0  mov     rcx, rsi; hFindFile
0x1800165c3  call    cs:__imp_FindNextFileW
0x1800165c9  test    eax, eax
0x1800165cb  jnz     loc_180016383
0x1800165d1  call    cs:__imp_GetLastError
0x1800165d7  cmp     eax, 12h
0x1800165da  jnz     loc_18001678F
0x1800165e0  test    r12b, 1
0x1800165e4  jnz     loc_1800166E2
0x1800165ea  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x1800165ee  jz      loc_180016774
0x1800165f4  lea     edi, [rax-0Eh]
0x1800165f7  mov     dword ptr [rsp+370h+hMem], 3
0x1800165ff  mov     r9d, edi; dwBufferSize
0x180016602  lea     r8, [rsp+370h+hMem]; lpFileInformation
0x180016607  lea     edx, [rax+3]; FileInformationClass
0x18001660a  mov     rcx, r15; hFile
0x18001660d  call    cs:__imp_SetFileInformationByHandle
0x180016613  test    eax, eax
0x180016615  jnz     loc_1800166E2
0x18001661b  call    cs:__imp_GetLastError
0x180016621  cmp     eax, 5
0x180016624  jz      loc_180016751
0x18001662a  lea     r9d, [rdi-3]; dwBufferSize
0x18001662e  mov     [rsp+370h+FileInformation], 1
0x180016633  lea     r8, [rsp+370h+FileInformation]; lpFileInformation
0x180016638  mov     edx, edi; FileInformationClass
0x18001663a  mov     rcx, r15; hFile
0x18001663d  call    cs:__imp_SetFileInformationByHandle
0x180016643  test    eax, eax
0x180016645  jnz     loc_1800166E2
0x18001664b  mov     edx, 171h; void *
0x180016650  mov     rcx, [rbp+278h]; this
0x180016657  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001665e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180016663  mov     edi, eax
0x180016665  jmp     loc_1800167E5
0x18001666a  mov     rcx, [rbp+278h]; this
0x180016671  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180016678  mov     edx, 131h; void *
0x18001667d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180016682  lea     rcx, [rdi-1]
0x180016686  mov     r14d, eax
0x180016689  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001668d  ja      loc_1800164B7
0x180016693  jmp     loc_1800164AE
0x180016698  call    cs:__imp_GetLastError
0x18001669e  test    eax, eax
0x1800166a0  jz      short loc_1800166BF
0x1800166a2  mov     rcx, [rbp+278h]; this
0x1800166a9  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800166b0  mov     r9d, eax; char *
0x1800166b3  mov     edx, 136h; void *
0x1800166b8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800166bd  jmp     short loc_180016682
0x1800166bf  lea     rax, [rdi-1]
0x1800166c3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800166c7  ja      short loc_1800166D2
0x1800166c9  mov     rcx, rdi; hObject
0x1800166cc  call    cs:__imp_CloseHandle
0x1800166d2  mov     rcx, [rsp+370h+hMem]; hMem
0x1800166d7  test    rcx, rcx
0x1800166da  jz      short loc_1800166E2
0x1800166dc  call    cs:__imp_LocalFree
0x1800166e2  mov     rcx, rsi; hFindFile
0x1800166e5  call    cs:__imp_FindClose
0x1800166eb  mov     rcx, [rsp+370h+ppszPathOut]; hMem
0x1800166f0  test    rcx, rcx
0x1800166f3  jz      short loc_1800166FB
0x1800166f5  call    cs:__imp_LocalFree
0x1800166fb  test    rbx, rbx
  ... truncated ...
```

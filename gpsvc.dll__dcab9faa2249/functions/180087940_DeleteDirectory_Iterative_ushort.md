# DeleteDirectory_Iterative(ushort *)

- ea: `0x180087940`
- end: `0x18008856d`
- name: `?DeleteDirectory_Iterative@@YAHPEAG@Z`
- size: `3117`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1800877e4`

## callees

- `0x18000a504`
- `0x18001ee6c`
- `0x180053510`
- `0x180075ec0`
- `0x18007d320`
- `0x18007d72c`
- `0x180086174`
- `0x180086324`
- `0x180086364`
- `0x18008639c`
- `0x180086ee4`
- `0x180087054`
- `0x18008708c`
- `0x1800870d0`
- `0x18008710c`
- `0x180087180`
- `0x180087940`
- `0x180088ca0`
- `0x180088ef8`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087da0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800881de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088215`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008829a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088445`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087da0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800881de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088215`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008829a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088445`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800879e1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180087a58`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180087ac2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180087b25`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800879e1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180087a58`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180087ac2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180087b25`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x180087d2a`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x180087f59`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x180088150`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x180087d2a`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x180087f59`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x180088150`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800881bf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800881bf`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180087d8d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180087d8d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180088249`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180088249`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180088014`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800881b6`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180088014`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800881b6`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180088238`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180088238`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800883d9`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800883d9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180087e6a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180087ee0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180087e6a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180087ee0`

## string_xrefs

- `0x1800879a4`: `DeleteDirectory_Iterative: Entering, lpDir = <%s>`
- `0x1800879c7`: `DeleteDirectory_Iterative: Entering, lpDir = <%s>`
- `0x180087a18`: `DeleteDirectory_Iterative:  Failed to allocate memory for WIN32_FIND_DATA (size = %Iu).`
- `0x180087a41`: `DeleteDirectory_Iterative:  Failed to allocate memory for WIN32_FIND_DATA (size = %Iu).`
- `0x180087a8b`: `DeleteDirectory_Iterative:  Failed to allocate memory for tszSearchPath (size = %Iu).`
- `0x180087ab1`: `DeleteDirectory_Iterative:  Failed to allocate memory for tszSearchPath (size = %Iu).`
- `0x180087af8`: `DeleteDirectory_Iterative:  Failed to allocate memory for tszAbsoluteDirPath (size = %Iu).`
- `0x180087b17`: `DeleteDirectory_Iterative:  Failed to allocate memory for tszAbsoluteDirPath (size = %Iu).`
- `0x180087b59`: `DeleteDirectory_Iterative:  Failed to allocate memory for tszAbsoluteFilePath (size = %Iu).`
- `0x180087b81`: `DeleteDirectory_Iterative:  Failed to allocate memory for tszAbsoluteFilePath (size = %Iu).`
- `0x180087d4a`: `DeleteDirectory_Iterative: After PathCchCombine tszSearchPath: <%s>`
- `0x180087d74`: `DeleteDirectory_Iterative: After PathCchCombine tszSearchPath: <%s>`
- `0x180087dc4`: `DeleteDirectory_Iterative: hFile == INVALID_HANDLE_VALUE AND ERROR_FILE_NOT_FOUND `
- `0x180087de9`: `DeleteDirectory_Iterative: hFile == INVALID_HANDLE_VALUE AND ERROR_FILE_NOT_FOUND `
- `0x180088272`: `DeleteDirectory_Iterative: FindFirstFile failed.  Error = %d`
- `0x1800882a3`: `DeleteDirectory_Iterative: FindFirstFile failed.  Error = %d`
- `0x180087e22`: `DeleteDirectory_Iterative: FindFirstFile found:  <%s>`
- `0x180087e4b`: `DeleteDirectory_Iterative: FindFirstFile found:  <%s>`
- `0x180087e90`: `DeleteDirectory_Iterative: Found ., continuing`
- `0x180087ec0`: `DeleteDirectory_Iterative: Found ., continuing`
- `0x180087f06`: `DeleteDirectory_Iterative: Found .., continuing`
- `0x180087f29`: `DeleteDirectory_Iterative: Found .., continuing`
- `0x180087f7a`: `DeleteDirectory_Iterative: After PathCchCombine tszAbsoluteDirPath:  <%s>`
- `0x180087fa1`: `DeleteDirectory_Iterative: After PathCchCombine tszAbsoluteDirPath:  <%s>`
- `0x180087fd6`: `DeleteDirectory_Iterative: Removing FILE_ATTRIBUTE_READONLY from:  <%s>`
- `0x180087ffe`: `DeleteDirectory_Iterative: Removing FILE_ATTRIBUTE_READONLY from:  <%s>`
- `0x180088032`: `DeleteDirectory_Iterative: Adding to directoriesToSearch and directoriesToRemove:  <%s>`
- `0x18008805a`: `DeleteDirectory_Iterative: Adding to directoriesToSearch and directoriesToRemove:  <%s>`
- `0x180088171`: `DeleteDirectory_Iterative: After PathCchCombine tszAbsoluteFilePath:  <%s>`
- `0x180088198`: `DeleteDirectory_Iterative: After PathCchCombine tszAbsoluteFilePath:  <%s>`
- `0x1800881ea`: `DeleteDirectory_Iterative: Failed to delete file <%s>.  Error = %d`
- `0x180088221`: `DeleteDirectory_Iterative: Failed to delete file <%s>.  Error = %d`
- `0x180088381`: `DeleteDirectory_Iterative: Calling RemoveDirectory on  <%s>`
- `0x1800883ba`: `DeleteDirectory_Iterative: Calling RemoveDirectory on  <%s>`
- `0x18008841d`: `DeleteDirectory_Iterative: RemoveDirectory failed for <%s>.  Error = %d`
- `0x180088462`: `DeleteDirectory_Iterative: RemoveDirectory failed for <%s>.  Error = %d`
- `0x18008849b`: `DeleteDirectory_Iterative: Leaving <%s>`
- `0x1800884c4`: `DeleteDirectory_Iterative: Leaving <%s>`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeleteDirectory_Iterative(unsigned __int16 *a1)
{
  HLOCAL v2; // rax
  LPWIN32_FIND_DATAW v3; // rbx
  void (*v4)(unsigned int, const unsigned __int16 *, ...); // rax
  __int64 v5; // r8
  const wchar_t *v6; // rdx
  HLOCAL v7; // rax
  HLOCAL v8; // rax
  WCHAR *v9; // rdi
  HLOCAL v10; // rax
  WCHAR *v11; // rsi
  _QWORD *v13; // rax
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r12
  __int64 v17; // r15
  __int64 v18; // rax
  unsigned int v19; // r13d
  __int64 v20; // r9
  const WCHAR *v21; // r8
  HANDLE FirstFileW; // r12
  void (*v23)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v24; // rdx
  const WCHAR *v25; // r8
  const WCHAR *cFileName; // r9
  void (*v27)(unsigned int, const unsigned __int16 *, ...); // rax
  __int64 v28; // r8
  __int64 v29; // rdx
  __int64 v30; // r12
  __int64 v31; // r15
  __int64 v32; // rax
  void (*v33)(unsigned int, const unsigned __int16 *, ...); // r15
  DWORD v34; // eax
  DWORD v35; // eax
  void (*v36)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v37; // eax
  DWORD v38; // eax
  const WCHAR *v39; // rcx
  void (*v40)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD LastError; // eax
  DWORD v42; // eax
  PWSTR pszPathOut; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v44; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v45; // [rsp+48h] [rbp-B8h]
  __int64 v46; // [rsp+58h] [rbp-A8h]
  __int128 v47; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v48; // [rsp+70h] [rbp-90h]
  PWSTR v49; // [rsp+78h] [rbp-88h] BYREF
  PWSTR v50; // [rsp+80h] [rbp-80h] BYREF
  LPWIN32_FIND_DATAW lpFindFileData; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v52; // [rsp+90h] [rbp-70h]
  HANDLE v53; // [rsp+98h] [rbp-68h]
  __int128 v54; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v55; // [rsp+B0h] [rbp-50h]
  LPCWSTR lpPathName[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v57; // [rsp+D0h] [rbp-30h]
  PCWSTR pszPathIn[3]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v59; // [rsp+F8h] [rbp-8h]

  v52 = a1;
  lpFindFileData = 0;
  pszPathOut = 0;
  v50 = 0;
  v49 = 0;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"DeleteDirectory_Iterative: Entering, lpDir = <%s>", a1);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"DeleteDirectory_Iterative: Entering, lpDir = <%s>", a1);
    }
  }
  v2 = LocalAlloc(0x40u, 0x250u);
  XPtrLF<_SECURITY_DESCRIPTOR>::operator=(&lpFindFileData, v2);
  v3 = lpFindFileData;
  if ( !lpFindFileData )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v4 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance )
        {
          if ( g_lpDebugMsgContext )
            RedirectDebugMsg(
              2u,
              L"DeleteDirectory_Iterative:  Failed to allocate memory for WIN32_FIND_DATA (size = %Iu).",
              592);
        }
        goto LABEL_37;
      }
      v5 = 592;
      v6 = L"DeleteDirectory_Iterative:  Failed to allocate memory for WIN32_FIND_DATA (size = %Iu).";
      goto LABEL_33;
    }
LABEL_37:
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&v49);
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&v50);
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&pszPathOut);
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&lpFindFileData);
    return 0;
  }
  v7 = LocalAlloc(0x40u, 0x800u);
  XPtrLF<unsigned short>::operator=(&pszPathOut, v7);
  if ( !pszPathOut )
  {
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_37;
    v4 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(
          2u,
          L"DeleteDirectory_Iterative:  Failed to allocate memory for tszSearchPath (size = %Iu).",
          2048);
      goto LABEL_37;
    }
    v6 = L"DeleteDirectory_Iterative:  Failed to allocate memory for tszSearchPath (size = %Iu).";
LABEL_32:
    v5 = 2048;
LABEL_33:
    v4(2u, v6, v5);
    goto LABEL_37;
  }
  v8 = LocalAlloc(0x40u, 0x800u);
  XPtrLF<unsigned short>::operator=(&v49, v8);
  v9 = v49;
  if ( !v49 )
  {
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_37;
    v4 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(
          2u,
          L"DeleteDirectory_Iterative:  Failed to allocate memory for tszAbsoluteDirPath (size = %Iu).",
          2048);
      goto LABEL_37;
    }
    v6 = L"DeleteDirectory_Iterative:  Failed to allocate memory for tszAbsoluteDirPath (size = %Iu).";
    goto LABEL_32;
  }
  v10 = LocalAlloc(0x40u, 0x800u);
  XPtrLF<unsigned short>::operator=(&v50, v10);
  v11 = v50;
  if ( !v50 )
  {
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_37;
    v4 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(
          2u,
          L"DeleteDirectory_Iterative:  Failed to allocate memory for tszAbsoluteFilePath (size = %Iu).",
          2048);
      goto LABEL_37;
    }
    v6 = L"DeleteDirectory_Iterative:  Failed to allocate memory for tszAbsoluteFilePath (size = %Iu).";
    goto LABEL_32;
  }
  std::vector<std::wstring>::vector<std::wstring>(&v47);
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v13 = operator new(0x10u);
  v13[1] = 0;
  *(_QWORD *)&v44 = v13;
  *v13 = &v44;
  std::wstring::wstring(lpPathName, a1);
  v14 = v46;
  v15 = v45;
  if ( (unsigned __int64)v45 <= v46 + 1 )
  {
    std::deque<std::wstring>::_Growmap(&v44);
    v14 = v46;
    v15 = v45;
  }
  *((_QWORD *)&v45 + 1) &= v15 - 1;
  v16 = v14 + *((_QWORD *)&v45 + 1);
  v17 = (v15 - 1) & (v14 + *((_QWORD *)&v45 + 1));
  v18 = *((_QWORD *)&v44 + 1);
  if ( !*(_QWORD *)(*((_QWORD *)&v44 + 1) + 8 * v17) )
  {
    *(_QWORD *)(*((_QWORD *)&v44 + 1) + 8 * v17) = std::_Allocate<16,std::_Default_allocate_traits>(32);
    v15 = v45;
    v18 = *((_QWORD *)&v44 + 1);
  }
  std::wstring::wstring(*(_QWORD *)(v18 + 8 * (v16 & (v15 - 1))), lpPathName);
  v19 = 1;
  ++v46;
  std::wstring::_Tidy_deallocate(lpPathName);
  while ( 1 )
  {
    if ( !v46 )
    {
      LOBYTE(v20) = 0;
      std::_Sort_unchecked<std::wstring *,std::less<void>>(
        v47,
        *((_QWORD *)&v47 + 1),
        (__int64)(*((_QWORD *)&v47 + 1) - v47) >> 5,
        v20);
      while ( (_QWORD)v47 != *((_QWORD *)&v47 + 1) )
      {
        std::wstring::wstring(lpPathName, *((_QWORD *)&v47 + 1) - 32LL);
        std::wstring::_Tidy_deallocate(*((_QWORD *)&v47 + 1) - 32LL);
        *((_QWORD *)&v47 + 1) -= 32LL;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            v54 = *(_OWORD *)lpPathName;
            v55 = v57;
            g_lpDebugMsg(4u, L"DeleteDirectory_Iterative: Calling RemoveDirectory on  <%s>", &v54);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            v54 = *(_OWORD *)lpPathName;
            v55 = v57;
            RedirectDebugMsg(4u, L"DeleteDirectory_Iterative: Calling RemoveDirectory on  <%s>", &v54);
          }
        }
        v39 = (const WCHAR *)lpPathName;
        if ( *((_QWORD *)&v57 + 1) > 7u )
          v39 = lpPathName[0];
        if ( !RemoveDirectoryW(v39) && *(_DWORD *)&g_dwDebugLevel )
        {
          v40 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            LastError = GetLastError();
            v54 = *(_OWORD *)lpPathName;
            v55 = v57;
            v40(2u, L"DeleteDirectory_Iterative: RemoveDirectory failed for <%s>.  Error = %d", &v54, LastError);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            v42 = GetLastError();
            v54 = *(_OWORD *)lpPathName;
            v55 = v57;
            RedirectDebugMsg(2u, L"DeleteDirectory_Iterative: RemoveDirectory failed for <%s>.  Error = %d", &v54, v42);
          }
        }
        std::wstring::_Tidy_deallocate(lpPathName);
      }
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"DeleteDirectory_Iterative: Leaving <%s>", v52);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"DeleteDirectory_Iterative: Leaving <%s>", v52);
        }
      }
      std::deque<std::wstring>::~deque<std::wstring>(&v44);
      if ( (_QWORD)v47 )
      {
        std::_Destroy_range<std::allocator<std::wstring>>(v47, *((_QWORD *)&v47 + 1));
        std::_Deallocate<16>(v47, (v48 - v47) & 0xFFFFFFFFFFFFFFE0uLL);
        v47 = 0;
        v48 = 0;
      }
      goto LABEL_171;
    }
    std::wstring::wstring(pszPathIn, *(_QWORD *)(*((_QWORD *)&v44 + 1) + 8 * (*((_QWORD *)&v45 + 1) & (v45 - 1))));
    std::wstring::_Tidy_deallocate(*(_QWORD *)(*((_QWORD *)&v44 + 1) + 8 * (*((_QWORD *)&v45 + 1) & (v45 - 1))));
    if ( --v46 )
      ++*((_QWORD *)&v45 + 1);
    else
      *((_QWORD *)&v45 + 1) = 0;
    v21 = (const WCHAR *)pszPathIn;
    if ( v59 > 7 )
      v21 = pszPathIn[0];
    PathCchCombineEx(pszPathOut, 0x800u, v21, L"*.*", 1u);
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"DeleteDirectory_Iterative: After PathCchCombine tszSearchPath: <%s>", pszPathOut);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"DeleteDirectory_Iterative: After PathCchCombine tszSearchPath: <%s>", pszPathOut);
      }
    }
    FirstFileW = FindFirstFileW(pszPathOut, v3);
    v53 = FirstFileW;
    if ( FirstFileW != (HANDLE)-1LL )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"DeleteDirectory_Iterative: FindFirstFile found:  <%s>", v3->cFileName);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"DeleteDirectory_Iterative: FindFirstFile found:  <%s>", v3->cFileName);
        }
      }
      while ( 1 )
      {
        if ( lstrcmpiW(v3->cFileName, L".") )
        {
          if ( lstrcmpiW(v3->cFileName, L"..") )
          {
            v25 = (const WCHAR *)pszPathIn;
            cFileName = v3->cFileName;
            if ( (v3->dwFileAttributes & 0x10) == 0 )
            {
              if ( v59 > 7 )
                v25 = pszPathIn[0];
              PathCchCombineEx(v11, 0x800u, v25, cFileName, 1u);
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                if ( g_lpDebugMsg )
                {
                  g_lpDebugMsg(4u, L"DeleteDirectory_Iterative: After PathCchCombine tszAbsoluteFilePath:  <%s>", v11);
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  RedirectDebugMsg(
                    4u,
                    L"DeleteDirectory_Iterative: After PathCchCombine tszAbsoluteFilePath:  <%s>",
                    v11);
                }
              }
              if ( (v3->dwFileAttributes & 5) != 0 )
                SetFileAttributesW(v11, 0x80u);
              if ( !DeleteFileW(v11) && *(_DWORD *)&g_dwDebugLevel )
              {
                v33 = g_lpDebugMsg;
                if ( g_lpDebugMsg )
                {
                  v34 = GetLastError();
                  v33(2u, L"DeleteDirectory_Iterative: Failed to delete file <%s>.  Error = %d", v11, v34);
                }
                else if ( g_lpDebugMsgContextInstance && (char *)g_lpDebugMsgContext != (char *)g_lpDebugMsg )
                {
                  v35 = GetLastError();
                  RedirectDebugMsg(2u, L"DeleteDirectory_Iterative: Failed to delete file <%s>.  Error = %d", v11, v35);
                }
              }
              goto LABEL_134;
            }
            if ( v59 > 7 )
              v25 = pszPathIn[0];
            PathCchCombineEx(v9, 0x800u, v25, cFileName, 1u);
            v27 = g_lpDebugMsg;
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(4u, L"DeleteDirectory_Iterative: After PathCchCombine tszAbsoluteDirPath:  <%s>", v9);
                goto LABEL_94;
              }
              if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(4u, L"DeleteDirectory_Iterative: After PathCchCombine tszAbsoluteDirPath:  <%s>", v9);
LABEL_94:
                v27 = g_lpDebugMsg;
              }
            }
            if ( (v3->dwFileAttributes & 1) != 0 )
            {
              v3->dwFileAttributes &= ~1u;
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                if ( v27 )
                {
                  v27(4u, L"DeleteDirectory_Iterative: Removing FILE_ATTRIBUTE_READONLY from:  <%s>", v9);
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  RedirectDebugMsg(4u, L"DeleteDirectory_Iterative: Removing FILE_ATTRIBUTE_READONLY from:  <%s>", v9);
                }
              }
              SetFileAttributesW(v9, v3->dwFileAttributes);
              v27 = g_lpDebugMsg;
            }
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( v27 )
              {
                v27(4u, L"DeleteDirectory_Iterative: Adding to directoriesToSearch and directoriesToRemove:  <%s>", v9);
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(
                  4u,
                  L"DeleteDirectory_Iterative: Adding to directoriesToSearch and directoriesToRemove:  <%s>",
                  v9);
              }
            }
            std::wstring::wstring(lpPathName, v9);
            v28 = v46;
            v29 = v45;
            if ( (unsigned __int64)v45 <= v46 + 1 )
            {
              std::deque<std::wstring>::_Growmap(&v44);
              v28 = v46;
              v29 = v45;
            }
            *((_QWORD *)&v45 + 1) &= v29 - 1;
            v30 = v28 + *((_QWORD *)&v45 + 1);
            v31 = (v29 - 1) & (v28 + *((_QWORD *)&v45 + 1));
            v32 = *((_QWORD *)&v44 + 1);
            if ( !*(_QWORD *)(*((_QWORD *)&v44 + 1) + 8 * v31) )
            {
              *(_QWORD *)(*((_QWORD *)&v44 + 1) + 8 * v31) = std::_Allocate<16,std::_Default_allocate_traits>(32);
              v29 = v45;
              v32 = *((_QWORD *)&v44 + 1);
            }
            std::wstring::wstring(*(_QWORD *)(v32 + 8 * (v30 & (v29 - 1))), lpPathName);
            ++v46;
            if ( *((_QWORD *)&v47 + 1) == v48 )
            {
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(
                &v47,
                *((_QWORD *)&v47 + 1),
                lpPathName);
            }
            else
            {
              std::wstring::wstring(*((_QWORD *)&v47 + 1), lpPathName);
              *((_QWORD *)&v47 + 1) += 32LL;
            }
            std::wstring::_Tidy_deallocate(lpPathName);
            FirstFileW = v53;
            goto LABEL_134;
          }
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            v23 = g_lpDebugMsg;
            if ( !g_lpDebugMsg )
            {
              if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                RedirectDebugMsg(4u, L"DeleteDirectory_Iterative: Found .., continuing");
              goto LABEL_134;
            }
            v24 = L"DeleteDirectory_Iterative: Found .., continuing";
LABEL_74:
            v23(4u, v24);
          }
        }
        else if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v23 = g_lpDebugMsg;
          if ( !g_lpDebugMsg )
          {
            if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              RedirectDebugMsg(4u, L"DeleteDirectory_Iterative: Found ., continuing");
            goto LABEL_134;
          }
          v24 = L"DeleteDirectory_Iterative: Found ., continuing";
          goto LABEL_74;
        }
LABEL_134:
        if ( !FindNextFileW(FirstFileW, v3) )
        {
          FindClose(FirstFileW);
          goto LABEL_63;
        }
      }
    }
    if ( GetLastError() != 2 )
      break;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"DeleteDirectory_Iterative: hFile == INVALID_HANDLE_VALUE AND ERROR_FILE_NOT_FOUND ");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"DeleteDirectory_Iterative: hFile == INVALID_HANDLE_VALUE AND ERROR_FILE_NOT_FOUND ");
      }
    }
LABEL_63:
    std::wstring::_Tidy_deallocate(pszPathIn);
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    v36 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      v37 = GetLastError();
      v36(2u, L"DeleteDirectory_Iterative: FindFirstFile failed.  Error = %d", v37);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      v38 = GetLastError();
      RedirectDebugMsg(2u, L"DeleteDirectory_Iterative: FindFirstFile failed.  Error = %d", v38);
    }
  }
  std::wstring::_Tidy_deallocate(pszPathIn);
  std::deque<std::wstring>::~deque<std::wstring>(&v44);
  if ( (_QWORD)v47 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v47, *((_QWORD *)&v47 + 1));
    std::_Deallocate<16>(v47, (v48 - v47) & 0xFFFFFFFFFFFFFFE0uLL);
    v47 = 0;
    v48 = 0;
  }
  v19 = 0;
LABEL_171:
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&v49);
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&v50);
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&pszPathOut);
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&lpFindFileData);
  return v19;
}

```

## disassembly

```asm
0x180087940  mov     [rsp-8+arg_8], rbx
0x180087945  mov     [rsp-8+arg_10], rsi
0x18008794a  push    rbp
0x18008794b  push    rdi
0x18008794c  push    r12
0x18008794e  push    r13
0x180087950  push    r15
0x180087952  lea     rbp, [rsp-10h]
0x180087957  sub     rsp, 110h
0x18008795e  mov     rax, cs:__security_cookie
0x180087965  xor     rax, rsp
0x180087968  mov     [rbp+30h+var_30], rax
0x18008796c  mov     r15, rcx
0x18008796f  mov     [rbp+30h+var_A0], rcx
0x180087973  xor     r13d, r13d
0x180087976  mov     [rbp+30h+lpFindFileData], r13
0x18008797a  mov     [rsp+130h+pszPathOut], r13
0x18008797f  mov     [rbp+30h+var_B0], r13
0x180087983  mov     [rsp+130h+var_B8], r13
0x180087988  lea     ecx, [r13+4]; unsigned int
0x18008798c  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180087993  jz      short loc_1800879D3
0x180087995  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18008799c  test    rax, rax
0x18008799f  jz      short loc_1800879B2
0x1800879a1  mov     r8, r15
0x1800879a4  lea     rdx, aDeletedirector_1; "DeleteDirectory_Iterative: Entering, lp"...
0x1800879ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800879b0  jmp     short loc_1800879D3
0x1800879b2  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x1800879b9  jz      short loc_1800879D3
0x1800879bb  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800879c2  jz      short loc_1800879D3
0x1800879c4  mov     r8, r15
0x1800879c7  lea     rdx, aDeletedirector_1; "DeleteDirectory_Iterative: Entering, lp"...
0x1800879ce  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800879d3  mov     edi, 250h
0x1800879d8  mov     edx, edi; uBytes
0x1800879da  mov     esi, 40h ; '@'
0x1800879df  mov     ecx, esi; uFlags
0x1800879e1  call    cs:__imp_LocalAlloc
0x1800879e7  mov     rdx, rax
0x1800879ea  lea     rcx, [rbp+30h+lpFindFileData]
0x1800879ee  call    ??4?$XPtrLF@U_SECURITY_DESCRIPTOR@@@@QEAAPEAU_SECURITY_DESCRIPTOR@@PEAU1@@Z; XPtrLF<_SECURITY_DESCRIPTOR>::operator=(_SECURITY_DESCRIPTOR *)
0x1800879f3  mov     rbx, [rbp+30h+lpFindFileData]
0x1800879f7  test    rbx, rbx
0x1800879fa  jnz     short loc_180087A4D
0x1800879fc  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180087a03  jz      loc_180087B96
0x180087a09  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180087a10  test    rax, rax
0x180087a13  jz      short loc_180087A24
0x180087a15  mov     r8d, edi
0x180087a18  lea     rdx, aDeletedirector_8; "DeleteDirectory_Iterative:  Failed to a"...
0x180087a1f  jmp     loc_180087B63
0x180087a24  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x180087a2b  jz      loc_180087B96
0x180087a31  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180087a38  jz      loc_180087B96
0x180087a3e  mov     r8, rdi
0x180087a41  lea     rdx, aDeletedirector_8; "DeleteDirectory_Iterative:  Failed to a"...
0x180087a48  jmp     loc_180087B8B
0x180087a4d  mov     r12d, 800h
0x180087a53  mov     edx, r12d; uBytes
0x180087a56  mov     ecx, esi; uFlags
0x180087a58  call    cs:__imp_LocalAlloc
0x180087a5e  mov     rdx, rax
0x180087a61  lea     rcx, [rsp+130h+pszPathOut]
0x180087a66  call    ??4?$XPtrLF@G@@QEAAPEAGPEAG@Z; XPtrLF<ushort>::operator=(ushort *)
0x180087a6b  cmp     [rsp+130h+pszPathOut], r13
0x180087a70  jnz     short loc_180087ABD
0x180087a72  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180087a79  jz      loc_180087B96
0x180087a7f  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180087a86  test    rax, rax
0x180087a89  jz      short loc_180087A97
0x180087a8b  lea     rdx, aDeletedirector_16; "DeleteDirectory_Iterative:  Failed to a"...
0x180087a92  jmp     loc_180087B60
0x180087a97  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x180087a9e  jz      loc_180087B96
0x180087aa4  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180087aab  jz      loc_180087B96
0x180087ab1  lea     rdx, aDeletedirector_16; "DeleteDirectory_Iterative:  Failed to a"...
0x180087ab8  jmp     loc_180087B88
0x180087abd  mov     rdx, r12; uBytes
0x180087ac0  mov     ecx, esi; uFlags
0x180087ac2  call    cs:__imp_LocalAlloc
0x180087ac8  mov     rdx, rax
0x180087acb  lea     rcx, [rsp+130h+var_B8]
0x180087ad0  call    ??4?$XPtrLF@G@@QEAAPEAGPEAG@Z; XPtrLF<ushort>::operator=(ushort *)
0x180087ad5  mov     rdi, [rsp+130h+var_B8]
0x180087ada  test    rdi, rdi
0x180087add  jnz     short loc_180087B20
0x180087adf  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180087ae6  jz      loc_180087B96
0x180087aec  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180087af3  test    rax, rax
0x180087af6  jz      short loc_180087B01
0x180087af8  lea     rdx, aDeletedirector_10; "DeleteDirectory_Iterative:  Failed to a"...
0x180087aff  jmp     short loc_180087B60
0x180087b01  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x180087b08  jz      loc_180087B96
0x180087b0e  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180087b15  jz      short loc_180087B96
0x180087b17  lea     rdx, aDeletedirector_10; "DeleteDirectory_Iterative:  Failed to a"...
0x180087b1e  jmp     short loc_180087B88
0x180087b20  mov     rdx, r12; uBytes
0x180087b23  mov     ecx, esi; uFlags
0x180087b25  call    cs:__imp_LocalAlloc
0x180087b2b  mov     rdx, rax
0x180087b2e  lea     rcx, [rbp+30h+var_B0]
0x180087b32  call    ??4?$XPtrLF@G@@QEAAPEAGPEAG@Z; XPtrLF<ushort>::operator=(ushort *)
0x180087b37  mov     rsi, [rbp+30h+var_B0]
0x180087b3b  test    rsi, rsi
0x180087b3e  jnz     loc_180087BC6
0x180087b44  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180087b4b  jz      short loc_180087B96
0x180087b4d  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180087b54  test    rax, rax
0x180087b57  jz      short loc_180087B6F
0x180087b59  lea     rdx, aDeletedirector_9; "DeleteDirectory_Iterative:  Failed to a"...
0x180087b60  mov     r8, r12
0x180087b63  mov     ecx, 2
0x180087b68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087b6d  jmp     short loc_180087B96
0x180087b6f  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x180087b76  jz      short loc_180087B96
0x180087b78  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180087b7f  jz      short loc_180087B96
0x180087b81  lea     rdx, aDeletedirector_9; "DeleteDirectory_Iterative:  Failed to a"...
0x180087b88  mov     r8, r12
0x180087b8b  mov     ecx, 2; unsigned int
0x180087b90  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180087b95  nop
0x180087b96  lea     rcx, [rsp+130h+var_B8]
0x180087b9b  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x180087ba0  nop
0x180087ba1  lea     rcx, [rbp+30h+var_B0]
0x180087ba5  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x180087baa  nop
0x180087bab  lea     rcx, [rsp+130h+pszPathOut]
0x180087bb0  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x180087bb5  nop
0x180087bb6  lea     rcx, [rbp+30h+lpFindFileData]
0x180087bba  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x180087bbf  xor     eax, eax
0x180087bc1  jmp     loc_180088545
0x180087bc6  lea     rcx, [rsp+130h+var_D0]
0x180087bcb  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::vector<std::wstring>(void)
0x180087bd0  nop
0x180087bd1  xorps   xmm0, xmm0
0x180087bd4  movdqu  [rsp+130h+var_F8], xmm0
0x180087bda  xorps   xmm1, xmm1
0x180087bdd  movdqu  [rsp+130h+var_E8], xmm1
0x180087be3  mov     [rsp+130h+var_D8], r13
0x180087be8  mov     ecx, 10h; Size
0x180087bed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180087bf2  mov     [rax+8], r13
0x180087bf6  mov     qword ptr [rsp+130h+var_F8], rax
0x180087bfb  lea     rcx, [rsp+130h+var_F8]
0x180087c00  mov     [rax], rcx
0x180087c03  mov     rdx, r15
0x180087c06  lea     rcx, [rbp+30h+lpPathName]
0x180087c0a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180087c0f  nop
0x180087c10  mov     r8, [rsp+130h+var_D8]
0x180087c15  lea     rax, [r8+1]
0x180087c19  mov     rdx, qword ptr [rsp+130h+var_E8]
0x180087c1e  cmp     rdx, rax
0x180087c21  ja      short loc_180087C37
0x180087c23  lea     rcx, [rsp+130h+var_F8]
0x180087c28  call    ?_Growmap@?$deque@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAX_K@Z; std::deque<std::wstring>::_Growmap(unsigned __int64)
0x180087c2d  mov     r8, [rsp+130h+var_D8]
0x180087c32  mov     rdx, qword ptr [rsp+130h+var_E8]
0x180087c37  lea     rcx, [rdx-1]
0x180087c3b  mov     rax, qword ptr [rsp+130h+var_E8+8]
0x180087c40  and     rax, rcx
0x180087c43  mov     qword ptr [rsp+130h+var_E8+8], rax
0x180087c48  lea     r12, [r8+rax]
0x180087c4c  mov     r15, r12
0x180087c4f  and     r15, rcx
0x180087c52  mov     rax, qword ptr [rsp+130h+var_F8+8]
0x180087c57  cmp     [rax+r15*8], r13
0x180087c5b  jnz     short loc_180087C7A
0x180087c5d  mov     ecx, 20h ; ' '
0x180087c62  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180087c67  mov     rcx, qword ptr [rsp+130h+var_F8+8]
0x180087c6c  mov     [rcx+r15*8], rax
0x180087c70  mov     rdx, qword ptr [rsp+130h+var_E8]
0x180087c75  mov     rax, qword ptr [rsp+130h+var_F8+8]
0x180087c7a  lea     rcx, [rdx-1]
0x180087c7e  and     rcx, r12
0x180087c81  lea     rdx, [rbp+30h+lpPathName]
0x180087c85  mov     rcx, [rax+rcx*8]
0x180087c89  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180087c8e  mov     r13d, 1
0x180087c94  add     [rsp+130h+var_D8], r13
0x180087c99  lea     rcx, [rbp+30h+lpPathName]
0x180087c9d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180087ca2  xor     r15d, r15d
0x180087ca5  cmp     [rsp+130h+var_D8], r15
0x180087caa  jz      loc_18008830A
0x180087cb0  mov     rax, qword ptr [rsp+130h+var_E8]
0x180087cb5  dec     rax
0x180087cb8  and     rax, qword ptr [rsp+130h+var_E8+8]
0x180087cbd  mov     rdx, qword ptr [rsp+130h+var_F8+8]
0x180087cc2  mov     rdx, [rdx+rax*8]
0x180087cc6  lea     rcx, [rbp+30h+pszPathIn]
0x180087cca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180087ccf  nop
0x180087cd0  mov     rax, qword ptr [rsp+130h+var_E8]
0x180087cd5  dec     rax
0x180087cd8  and     rax, qword ptr [rsp+130h+var_E8+8]
0x180087cdd  mov     rcx, qword ptr [rsp+130h+var_F8+8]
0x180087ce2  mov     rcx, [rcx+rax*8]
0x180087ce6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180087ceb  mov     rax, [rsp+130h+var_D8]
0x180087cf0  sub     rax, r13
0x180087cf3  mov     [rsp+130h+var_D8], rax
0x180087cf8  jnz     short loc_180087D01
0x180087cfa  mov     qword ptr [rsp+130h+var_E8+8], r15
0x180087cff  jmp     short loc_180087D06
0x180087d01  add     qword ptr [rsp+130h+var_E8+8], r13
0x180087d06  lea     r8, [rbp+30h+pszPathIn]
0x180087d0a  cmp     [rbp+30h+var_38], 7
0x180087d0f  cmova   r8, [rbp+30h+pszPathIn]; pszPathIn
0x180087d14  mov     [rsp+130h+dwFlags], r13d; dwFlags
0x180087d19  lea     r9, pszMore; "*.*"
0x180087d20  mov     edx, 800h; cchPathOut
0x180087d25  mov     rcx, [rsp+130h+pszPathOut]; pszPathOut
0x180087d2a  call    cs:__imp_PathCchCombineEx
0x180087d30  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180087d37  jz      short loc_180087D85
0x180087d39  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180087d40  test    rax, rax
0x180087d43  jz      short loc_180087D5D
0x180087d45  mov     r8, [rsp+130h+pszPathOut]
0x180087d4a  lea     rdx, aDeletedirector_4; "DeleteDirectory_Iterative: After PathCc"...
0x180087d51  mov     ecx, 4
0x180087d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087d5b  jmp     short loc_180087D85
0x180087d5d  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180087d64  jz      short loc_180087D85
0x180087d66  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180087d6d  jz      short loc_180087D85
0x180087d6f  mov     r8, [rsp+130h+pszPathOut]
0x180087d74  lea     rdx, aDeletedirector_4; "DeleteDirectory_Iterative: After PathCc"...
0x180087d7b  mov     ecx, 4; unsigned int
0x180087d80  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180087d85  mov     rdx, rbx; lpFindFileData
0x180087d88  mov     rcx, [rsp+130h+pszPathOut]; lpFileName
0x180087d8d  call    cs:__imp_FindFirstFileW
0x180087d93  mov     r12, rax
0x180087d96  mov     [rbp+30h+var_98], rax
0x180087d9a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180087d9e  jnz     short loc_180087E09
0x180087da0  call    cs:__imp_GetLastError
0x180087da6  cmp     eax, 2
0x180087da9  jnz     loc_180088254
0x180087daf  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180087db6  jz      short loc_180087DFB
0x180087db8  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180087dbf  test    rax, rax
0x180087dc2  jz      short loc_180087DD7
0x180087dc4  lea     rdx, aDeletedirector_7; "DeleteDirectory_Iterative: hFile == INV"...
0x180087dcb  lea     ecx, [r12+5]
0x180087dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087dd5  jmp     short loc_180087DFB
0x180087dd7  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180087dde  jz      short loc_180087DFB
0x180087de0  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180087de7  jz      short loc_180087DFB
0x180087de9  lea     rdx, aDeletedirector_7; "DeleteDirectory_Iterative: hFile == INV"...
0x180087df0  mov     ecx, 4; unsigned int
0x180087df5  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180087dfa  nop
0x180087dfb  lea     rcx, [rbp+30h+pszPathIn]
0x180087dff  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180087e04  jmp     loc_180087CA5
0x180087e09  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180087e10  jz      short loc_180087E5C
0x180087e12  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180087e19  test    rax, rax
0x180087e1c  jz      short loc_180087E35
0x180087e1e  lea     r8, [rbx+2Ch]
0x180087e22  lea     rdx, aDeletedirector_15; "DeleteDirectory_Iterative: FindFirstFil"...
0x180087e29  mov     ecx, 4
0x180087e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087e33  jmp     short loc_180087E5C
0x180087e35  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180087e3c  jz      short loc_180087E5C
0x180087e3e  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180087e45  jz      short loc_180087E5C
0x180087e47  lea     r8, [rbx+2Ch]
0x180087e4b  lea     rdx, aDeletedirector_15; "DeleteDirectory_Iterative: FindFirstFil"...
0x180087e52  mov     ecx, 4; unsigned int
0x180087e57  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180087e5c  lea     r15, [rbx+2Ch]
0x180087e60  lea     rdx, asc_1800C3A80; "."
0x180087e67  mov     rcx, r15; lpString1
  ... truncated ...
```

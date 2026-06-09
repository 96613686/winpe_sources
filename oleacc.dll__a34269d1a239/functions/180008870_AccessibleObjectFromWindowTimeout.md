# AccessibleObjectFromWindowTimeout

- ea: `0x180008870`
- end: `0x1800093b0`
- name: `AccessibleObjectFromWindowTimeout`
- size: `2880`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, HWND, LONG, IID *, void **ppvObject)`
- caller_count: `31`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002c20`
- `0x180005910`
- `0x180005e10`
- `0x180007750`
- `0x180007820`
- `0x180008478`
- `0x1800084e0`
- `0x180008560`
- `0x1800097e0`
- `0x180014b30`
- `0x180016650`
- `0x180017bb4`
- `0x1800180f0`
- `0x1800196e0`
- `0x18001c7b0`
- `0x180029210`
- `0x18002b0f0`
- `0x18002b230`
- `0x18002b9ec`
- `0x18002bff0`
- `0x18002e6d0`
- `0x18002eb10`
- `0x18003abd0`
- `0x180041900`
- `0x180044140`
- `0x180045154`
- `0x1800455a0`
- `0x1800456f0`
- `0x1800457e0`
- `0x1800458d0`
- `0x180045a20`

## callees

- `0x180007700`
- `0x180008870`
- `0x180009634`
- `0x1800096a0`
- `0x1800097e0`
- `0x18000baa0`
- `0x18001e4c0`
- `0x18001e610`
- `0x180046880`
- `0x180047fec`
- `0x180047ff8`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008a6b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008a7d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008a98`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008ab3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800092a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800092b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008a6b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008a7d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008a98`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008ab3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800092a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800092b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000924a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000924a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800091c2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800091c2`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180008f89`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000900a`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180008f89`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000900a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180008fa3`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000902e`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180008fa3`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000902e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800090d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009205`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800090d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009205`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800091fa`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800091fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800091d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800091d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000898c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008f5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008fba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800090f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000898c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008f5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008fba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800090f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008909`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008909`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800090c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800090c5`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000903c`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000903c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008c61`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008fdf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008c61`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008fdf`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180009388`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000939b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180009388`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000939b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180008acf`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180008acf`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180009071`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180009071`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180009051`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180009051`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x1800089c2`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x1800089c2`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x180008afd`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x180008afd`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180008f56`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180008f56`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x1800090a9`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x1800090a9`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000908d`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000908d`
- `USER32!EnumWindows` at `0x180009358`
- `USER32!EnumWindows` at `0x180009358`
- `USER32!SendMessageTimeoutW` at `0x180008952`
- `USER32!SendMessageTimeoutW` at `0x180009195`
- `USER32!SendMessageTimeoutW` at `0x180008952`
- `USER32!SendMessageTimeoutW` at `0x180009195`
- `USER32!GetWindowThreadProcessId` at `0x180008901`
- `USER32!GetWindowThreadProcessId` at `0x180008901`
- `USER32!IsWindow` at `0x1800088ed`
- `USER32!IsWindow` at `0x1800088ed`

## string_xrefs

- `0x180008aac`: `NTDLL.DLL`
- `0x180008ac8`: `OLEAUT32.DLL`
- `0x180008a5a`: `USER32.DLL`
- `0x180008a91`: `api-ms-win-core-memory-l1-1-2.DLL`
- `0x180008a71`: `api-ms-win-core-libraryloader-l1-2-0.DLL`
- `0x1800092f3`: `OleAcc: Unexpected timeout of zero supplied to AccessibleObjectFromWindowTimeout().`
- `0x18000929a`: `KERNEL32.DLL`
- `0x1800092b1`: `KERNEL32.DLL`

## pseudocode

```c
__int64 __fastcall AccessibleObjectFromWindowTimeout(
        unsigned int a1,
        unsigned int a2,
        HWND a3,
        LONG a4,
        IID *a5,
        void **ppvObject)
{
  unsigned int v6; // edi
  IID *v7; // r14
  HWND v8; // r15
  WPARAM CurrentProcessId; // r14
  DWORD WindowThreadProcessId; // ebx
  ULONG_PTR v13; // rsi
  bool v14; // zf
  DWORD v15; // r15d
  DWORD v16; // edi
  char *v17; // r8
  int v18; // ecx
  int v19; // edx
  int v20; // edi
  int v21; // edi
  const struct ImportInfo *v22; // rdx
  int v23; // r8d
  unsigned int i; // ebx
  const WCHAR *v25; // rcx
  unsigned __int64 v26; // rdi
  ATOM v27; // ax
  HANDLE ProcessHandleFromHwnd; // rsi
  unsigned int (__fastcall ***v29)(LPVOID, GUID *, HWND *); // rdi
  unsigned int (__fastcall **v30)(LPVOID, GUID *, HWND *); // rax
  int v31; // ebx
  _DWORD *v32; // rax
  _DWORD *v33; // rbx
  int v34; // r14d
  HANDLE v36; // rbx
  char *v37; // r8
  int v38; // ecx
  int v39; // edx
  int v40; // ebx
  int v41; // ebx
  __int16 *v42; // r8
  int j; // ecx
  __int16 v44; // dx
  __int16 *v45; // rdx
  int k; // ecx
  __int16 v47; // r8
  int (__fastcall ***v48)(LPVOID, GUID *, ULONG_PTR *); // rdi
  int v49; // ebx
  int (__fastcall **v50)(LPVOID, GUID *, ULONG_PTR *); // rax
  unsigned int v51; // ebx
  int *v52; // rax
  int v53; // ebx
  int v54; // esi
  SIZE_T v55; // rdi
  size_t v56; // rbx
  HLOCAL v57; // rdi
  char *v58; // rax
  const void *v59; // rsi
  HGLOBAL v60; // rax
  void *v61; // rsi
  void *v62; // rax
  HRESULT v63; // ebx
  UINT uTimeout; // eax
  HANDLE CurrentProcess; // rax
  BOOL v66; // ebx
  signed int LastError; // eax
  ULONG_PTR dwResult; // [rsp+40h] [rbp-C0h] BYREF
  LONG idObject; // [rsp+48h] [rbp-B8h]
  HWND hwnd; // [rsp+50h] [rbp-B0h] BYREF
  LPSTREAM ppstm; // [rsp+58h] [rbp-A8h] BYREF
  HMODULE ModuleHandleW; // [rsp+60h] [rbp-A0h]
  HMODULE v73; // [rsp+68h] [rbp-98h]
  HMODULE v74; // [rsp+70h] [rbp-90h]
  HANDLE hFileMappingObject; // [rsp+78h] [rbp-88h] BYREF
  IID *riid; // [rsp+80h] [rbp-80h]
  unsigned int v77; // [rsp+88h] [rbp-78h]
  WCHAR Buffer[5]; // [rsp+90h] [rbp-70h] BYREF
  char v79; // [rsp+9Ah] [rbp-66h] BYREF
  __int16 v80; // [rsp+AAh] [rbp-56h]
  char v81; // [rsp+ACh] [rbp-54h] BYREF
  __int16 v82; // [rsp+BCh] [rbp-44h]
  char v83; // [rsp+BEh] [rbp-42h] BYREF
  __int16 v84; // [rsp+CEh] [rbp-32h]
  char v85; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v86; // [rsp+E0h] [rbp-20h]
  __int16 v87; // [rsp+E2h] [rbp-1Eh]

  v6 = a4;
  v7 = a5;
  v8 = a3;
  riid = a5;
  idObject = a4;
  hwnd = a3;
  v77 = a2;
  if ( !g_fInitedOleacc )
  {
    g_fInitedOleacc = 1;
    ppstm = (LPSTREAM)GetModuleHandleW(L"USER32.DLL");
    ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-libraryloader-l1-2-0.DLL");
    if ( !ModuleHandleW )
      ModuleHandleW = GetModuleHandleW(L"KERNEL32.DLL");
    v73 = GetModuleHandleW(L"api-ms-win-core-memory-l1-1-2.DLL");
    if ( !v73 )
      v73 = GetModuleHandleW(L"KERNEL32.DLL");
    v74 = GetModuleHandleW(L"NTDLL.DLL");
    ImportFromModule((HINSTANCE *)&ppstm, v22, v23);
    LoadLibraryW(L"OLEAUT32.DLL");
    for ( i = 0; i < 0x20; ++i )
    {
      v25 = off_180052380[i];
      v26 = 2LL * (int)i;
      if ( v25 )
      {
        v27 = GlobalAddAtomW(v25);
      }
      else
      {
        if ( v26 >= 0x40 )
          _report_rangecheckfailure();
        v27 = 0;
      }
      *(_WORD *)((char *)&rgAtomClasses + v26) = v27;
    }
    if ( !(unsigned int)IsProxyRegistrationCorrect(&_ImageBase) )
      Oleacc_DllRegisterServer();
    v6 = idObject;
  }
  if ( a1 >= 0x80000 )
  {
    if ( a2 )
    {
      if ( a2 >= 0x32 )
        goto LABEL_3;
    }
    else
    {
      Error::IAccessibleError(
        0,
        L"OleAcc: Unexpected timeout of zero supplied to AccessibleObjectFromWindowTimeout().",
        0,
        v8,
        5002);
    }
    LODWORD(v13) = -2147024809;
    return (unsigned int)v13;
  }
LABEL_3:
  if ( !ppvObject )
  {
    LODWORD(v13) = -2147024809;
    goto LABEL_49;
  }
  CurrentProcessId = 0;
  *ppvObject = 0;
  dwResult = 0;
  if ( !IsWindow(v8) )
    goto LABEL_9;
  WindowThreadProcessId = GetWindowThreadProcessId(v8, 0);
  if ( WindowThreadProcessId == GetCurrentThreadId() )
  {
    CurrentProcessId = 0xFFFFFFFFLL;
  }
  else
  {
    CurrentProcessId = GetCurrentProcessId();
    if ( CurrentProcessId == 0xFFFFFFFF )
      CurrentProcessId = 0;
  }
  if ( a1 <= 0x70000 )
  {
    SendMessageTimeoutW(v8, 0x3Du, CurrentProcessId, v6, 2u, 0x2710u, &dwResult);
LABEL_9:
    v13 = dwResult;
    goto LABEL_10;
  }
  uTimeout = 20000;
  ppstm = 0;
  if ( a2 >= 0x32 )
    uTimeout = a2;
  if ( !SendMessageTimeoutW(v8, 0x3Du, CurrentProcessId, v6, 2u, uTimeout, (PDWORD_PTR)&ppstm) )
  {
    LastError = GetLastError();
    LODWORD(v13) = LastError;
    if ( LastError == 1460 )
    {
      LODWORD(v13) = -2146233083;
    }
    else if ( LastError > 0 )
    {
      LODWORD(v13) = (unsigned __int16)LastError | 0x80070000;
    }
    Error::IAccessibleError(0, L"SendMessageTimeoutHelper", v13, v8, 5002);
    if ( (v13 & 0x80000000) != 0LL )
      goto LABEL_134;
  }
  v13 = (ULONG_PTR)ppstm;
  dwResult = (ULONG_PTR)ppstm;
LABEL_10:
  v14 = (_DWORD)v13 == 0;
  if ( (v13 & 0x80000000) != 0LL )
    goto LABEL_47;
  if ( !v13 )
    goto LABEL_106;
  *ppvObject = 0;
  if ( (v13 & 0x80000000) != 0LL )
  {
    LODWORD(v13) = -2147024809;
LABEL_45:
    if ( CurrentProcessId == 0xFFFFFFFF )
      goto LABEL_46;
LABEL_106:
    LODWORD(v13) = 0;
    goto LABEL_48;
  }
  if ( CurrentProcessId == 0xFFFFFFFF )
    v15 = GetCurrentProcessId();
  else
    v15 = CurrentProcessId;
  hFileMappingObject = 0;
  if ( WORD1(v13)
    || !(_WORD)v13
    || GlobalGetAtomNameW(v13, Buffer, 42) != 41
    || memcmp_0(Buffer, L"MSAA:", 0xAu)
    || v80 != 58
    || v82 != 58
    || v84 != 58
    || v86 != 58
    || v87 )
  {
    goto LABEL_44;
  }
  v16 = 0;
  v17 = &v79;
  v18 = 0;
  while ( v18 < 8 )
  {
    v19 = *(unsigned __int16 *)v17;
    v20 = 16 * v16;
    if ( (unsigned __int16)(v19 - 48) <= 9u )
    {
      v21 = v20 - 48;
      goto LABEL_28;
    }
    if ( (unsigned __int16)(v19 - 65) > 5u )
    {
      if ( (unsigned __int16)(v19 - 97) > 5u )
        goto LABEL_44;
      v21 = v20 - 87;
LABEL_28:
      v16 = v19 + v21;
      ++v18;
      v17 += 2;
    }
    else
    {
      ++v18;
      v16 = v19 + v20 - 55;
      v17 += 2;
    }
  }
  LODWORD(v36) = 0;
  v37 = &v81;
  v38 = 0;
  while ( v38 < 8 )
  {
    v39 = *(unsigned __int16 *)v37;
    v40 = 16 * (_DWORD)v36;
    if ( (unsigned __int16)(v39 - 48) <= 9u )
    {
      v41 = v40 - 48;
      goto LABEL_66;
    }
    if ( (unsigned __int16)(v39 - 65) > 5u )
    {
      if ( (unsigned __int16)(v39 - 97) > 5u )
        goto LABEL_44;
      v41 = v40 - 87;
LABEL_66:
      LODWORD(v36) = v39 + v41;
      ++v38;
      v37 += 2;
    }
    else
    {
      ++v38;
      LODWORD(v36) = v39 + v40 - 55;
      v37 += 2;
    }
  }
  v42 = (__int16 *)&v83;
  for ( j = 0; j < 8; ++j )
  {
    v44 = *v42;
    if ( (unsigned __int16)(*v42 - 48) > 9u && (unsigned __int16)(v44 - 65) > 5u && (unsigned __int16)(v44 - 97) > 5u )
      goto LABEL_44;
    ++v42;
  }
  v45 = (__int16 *)&v85;
  for ( k = 0; k < 8; ++k )
  {
    v47 = *v45;
    if ( (unsigned __int16)(*v45 - 48) > 9u && (unsigned __int16)(v47 - 65) > 5u && (unsigned __int16)(v47 - 97) > 5u )
      goto LABEL_44;
    ++v45;
  }
  GlobalDeleteAtom(v13);
  v36 = (HANDLE)(int)v36;
  if ( v16 == GetCurrentProcessId() )
  {
    hFileMappingObject = (HANDLE)(int)v36;
    goto LABEL_92;
  }
  ProcessHandleFromHwnd = OpenProcess(0x40u, 0, v16);
  if ( !ProcessHandleFromHwnd )
  {
    ppstm = (LPSTREAM)v16;
    ModuleHandleW = 0;
    EnumWindows(FindWindowFromProcessEnumWindowsProc, (LPARAM)&ppstm);
    if ( !ModuleHandleW )
      goto LABEL_44;
    ProcessHandleFromHwnd = (HANDLE)GetProcessHandleFromHwnd(ModuleHandleW);
    if ( !ProcessHandleFromHwnd )
      goto LABEL_44;
  }
  CurrentProcess = GetCurrentProcess();
  v66 = DuplicateHandle(ProcessHandleFromHwnd, (HANDLE)(int)v36, CurrentProcess, &hFileMappingObject, 0, 0, 3u);
  CloseHandle(ProcessHandleFromHwnd);
  if ( !v66 || (v36 = hFileMappingObject) == 0 )
  {
LABEL_44:
    LODWORD(v13) = -2147467259;
    goto LABEL_45;
  }
LABEL_92:
  v52 = (int *)MapViewOfFile(v36, 0xF001Fu, 0, 0, 0x10u);
  if ( !v52 )
    goto LABEL_44;
  v53 = *v52;
  v54 = v52[2];
  v55 = (unsigned int)v52[3];
  UnmapViewOfFile(v52);
  if ( v53 != -1440944115 || v15 && v54 != GetCurrentProcessId() )
    goto LABEL_44;
  if ( (unsigned int)v55 > 0x100000 )
  {
    v63 = -2147467259;
  }
  else
  {
    v56 = v55;
    v57 = LocalAlloc(0x40u, v55);
    if ( v57 )
    {
      v58 = (char *)MapViewOfFile(hFileMappingObject, 0xF001Fu, 0, 0, v56 + 16);
      v59 = v58;
      if ( v58 )
      {
        memcpy_0(v57, v58 + 16, v56);
        UnmapViewOfFile(v59);
        v60 = GlobalAlloc(2u, v56);
        v61 = v60;
        if ( v60 )
        {
          v62 = GlobalLock(v60);
          if ( v62 )
          {
            memcpy_0(v62, v57, v56);
            GlobalUnlock(v61);
            ppstm = 0;
            v63 = CreateStreamOnHGlobal(v61, 1, &ppstm);
            if ( v63 < 0 )
            {
              GlobalFree(v61);
            }
            else
            {
              v63 = CoUnmarshalInterface(ppstm, riid, ppvObject);
              (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
            }
          }
          else
          {
            GlobalFree(v61);
            v63 = -2147467259;
          }
        }
        else
        {
          v63 = -2147024882;
        }
      }
      else
      {
        v63 = -2147467259;
      }
      LocalFree(v57);
    }
    else
    {
      v63 = -2147024882;
    }
  }
  CloseHandle(hFileMappingObject);
  LODWORD(v13) = v63;
  if ( v63 < 0 )
    goto LABEL_45;
LABEL_46:
  v14 = (_DWORD)v13 == 0;
LABEL_47:
  if ( !v14 )
  {
    v8 = hwnd;
LABEL_134:
    v7 = riid;
    goto LABEL_49;
  }
LABEL_48:
  v7 = riid;
  v8 = hwnd;
  if ( !*ppvObject )
  {
    LODWORD(v13) = CreateStdAccessibleObject_0(hwnd, idObject, riid, ppvObject);
    if ( (v13 & 0x80000000) == 0LL )
    {
      v48 = (int (__fastcall ***)(LPVOID, GUID *, ULONG_PTR *))*ppvObject;
      ppstm = 0;
      if ( (**v48)(v48, &GUID_55f9c234_79cd_4699_89e7_5518fd88bcde, (ULONG_PTR *)&ppstm) >= 0 )
      {
        v49 = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD))(*(_QWORD *)ppstm + 32LL))(ppstm, a1);
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
        if ( v49 >= 0 )
        {
          v50 = *v48;
          dwResult = 0;
          if ( (*v50)(v48, &GUID_f660d979_a938_423f_b5b9_12e4028c50b0, &dwResult) >= 0 )
          {
            v51 = v77;
            if ( (*(int (__fastcall **)(ULONG_PTR, _QWORD))(*(_QWORD *)dwResult + 32LL))(dwResult, v77) >= 0 )
              (*(void (__fastcall **)(ULONG_PTR, _QWORD))(*(_QWORD *)dwResult + 48LL))(dwResult, v51);
            (*(void (__fastcall **)(ULONG_PTR))(*(_QWORD *)dwResult + 16LL))(dwResult);
          }
        }
      }
    }
  }
LABEL_49:
  if ( (_DWORD)v13 )
    return (unsigned int)v13;
  if ( !ppvObject )
    return (unsigned int)v13;
  v29 = (unsigned int (__fastcall ***)(LPVOID, GUID *, HWND *))*ppvObject;
  if ( !*ppvObject )
    return (unsigned int)v13;
  ppstm = 0;
  if ( !(**v29)(v29, &IID_IAccessible, (HWND *)&ppstm) && ppstm )
  {
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    v30 = *v29;
    hwnd = 0;
    if ( (*v30)(v29, &IID_IServiceProvider, &hwnd)
      || !hwnd
      || (dwResult = 0,
          v31 = (*(__int64 (__fastcall **)(HWND, GUID *, GUID *, ULONG_PTR *))(*(_QWORD *)hwnd + 24LL))(
                  hwnd,
                  &IIS_AccWrapBase_GetIUnknown,
                  &IID_IUnknown,
                  &dwResult),
          (*(void (__fastcall **)(HWND))(*(_QWORD *)hwnd + 16LL))(hwnd),
          v31)
      || !dwResult )
    {
      v32 = LocalAlloc(0x40u, 0xA8u);
      v33 = v32;
      if ( v32 )
      {
        v32[10] = 1;
        *(_QWORD *)v32 = &AccWrap_Base::`vftable'{for `IAccessible'};
        *((_QWORD *)v32 + 6) = v29;
        *((_QWORD *)v32 + 1) = &AccWrap_Base::`vftable'{for `IOleWindow'};
        *((_QWORD *)v32 + 2) = &AccWrap_Base::`vftable'{for `IEnumVARIANT'};
        *((_QWORD *)v32 + 3) = &AccWrap_Base::`vftable'{for `IAccIdentity'};
        *((_QWORD *)v32 + 4) = &AccWrap_Base::`vftable'{for `IServiceProvider'};
        *((_QWORD *)v32 + 8) = 0;
        *((_QWORD *)v32 + 9) = 0;
        *((_QWORD *)v32 + 10) = 0;
        *((_QWORD *)v32 + 11) = 0;
        *((_QWORD *)v32 + 12) = 0;
        v32[26] = 0;
        *((_QWORD *)v32 + 14) = 0;
        *((_QWORD *)v32 + 7) = *v29;
        ((void (__fastcall *)(unsigned int (__fastcall ***)(LPVOID, GUID *, HWND *)))(*v29)[1])(v29);
        *((_QWORD *)v33 + 15) = 0;
        *(_QWORD *)v33 = &AccWrap_LocationEtcFix::`vftable'{for `IAccessible'};
        v33[32] = 0;
        *((_QWORD *)v33 + 1) = &AccWrap_LocationEtcFix::`vftable'{for `IOleWindow'};
        v33[34] = 0;
        *((_QWORD *)v33 + 2) = &AccWrap_LocationEtcFix::`vftable'{for `IEnumVARIANT'};
        *((_QWORD *)v33 + 18) = 0;
        *((_QWORD *)v33 + 3) = &AccWrap_LocationEtcFix::`vftable'{for `IAccIdentity'};
        *((_QWORD *)v33 + 4) = &AccWrap_LocationEtcFix::`vftable'{for `IServiceProvider'};
        *((_QWORD *)v33 + 19) = 0;
        *((_QWORD *)v33 + 20) = v8;
        v34 = ((__int64 (__fastcall *)(_DWORD *, IID *, void **))AccWrap_LocationEtcFix::`vftable'{for `IAccessible'})(
                v33,
                v7,
                ppvObject);
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v33 + 16LL))(v33);
        goto LABEL_59;
      }
      LODWORD(v13) = -2147024882;
    }
    else
    {
      (*(void (__fastcall **)(ULONG_PTR))(*(_QWORD *)dwResult + 16LL))(dwResult);
      v34 = (**v29)(v29, v7, (HWND *)ppvObject);
LABEL_59:
      LODWORD(v13) = v34;
      if ( v34 >= 0 )
      {
LABEL_60:
        ((void (__fastcall *)(unsigned int (__fastcall ***)(LPVOID, GUID *, HWND *)))(*v29)[2])(v29);
        return (unsigned int)v13;
      }
    }
    *ppvObject = 0;
    goto LABEL_60;
  }
  return 0;
}

```

## disassembly

```asm
0x180008870  push    rbp
0x180008872  push    rbx
0x180008873  push    rsi
0x180008874  push    rdi
0x180008875  push    r12
0x180008877  push    r13
0x180008879  push    r14
0x18000887b  push    r15
0x18000887d  lea     rbp, [rsp-8]
0x180008882  sub     rsp, 108h
0x180008889  mov     rax, cs:__security_cookie
0x180008890  xor     rax, rsp
0x180008893  mov     [rbp+40h+var_50], rax
0x180008897  cmp     cs:?g_fInitedOleacc@@3HA, 0; int g_fInitedOleacc
0x18000889e  mov     edi, r9d
0x1800088a1  mov     r14, [rbp+40h+arg_20]
0x1800088a5  mov     r15, r8
0x1800088a8  mov     r12, [rbp+40h+ppvObject]
0x1800088ac  mov     esi, edx
0x1800088ae  mov     [rbp+40h+riid], r14
0x1800088b2  mov     r13d, ecx
0x1800088b5  mov     [rsp+140h+idObject], r9d
0x1800088ba  mov     [rsp+140h+hwnd], r8
0x1800088bf  mov     [rbp+40h+var_B8], edx
0x1800088c2  jz      loc_180008A5A
0x1800088c8  cmp     r13d, 80000h
0x1800088cf  jnb     loc_180009226
0x1800088d5  test    r12, r12
0x1800088d8  jz      loc_18000930B
0x1800088de  xor     r14d, r14d
0x1800088e1  mov     rcx, r15; hWnd
0x1800088e4  mov     [r12], r14
0x1800088e8  mov     [rsp+140h+dwResult], r14
0x1800088ed  call    cs:__imp_IsWindow
0x1800088f3  mov     ecx, 0FFFFFFFFh
0x1800088f8  test    eax, eax
0x1800088fa  jz      short loc_18000895D
0x1800088fc  xor     edx, edx; lpdwProcessId
0x1800088fe  mov     rcx, r15; hWnd
0x180008901  call    cs:__imp_GetWindowThreadProcessId
0x180008907  mov     ebx, eax
0x180008909  call    cs:__imp_GetCurrentThreadId
0x18000890f  cmp     ebx, eax
0x180008911  jnz     loc_1800090F3
0x180008917  mov     r14d, 0FFFFFFFFh
0x18000891d  mov     r9d, edi; lParam
0x180008920  mov     r8, r14; wParam
0x180008923  mov     edx, 3Dh ; '='; Msg
0x180008928  cmp     r13d, 70000h
0x18000892f  ja      loc_180009168
0x180008935  lea     rax, [rsp+140h+dwResult]
0x18000893a  mov     rcx, r15; hWnd
0x18000893d  mov     [rsp+140h+lpdwResult], rax; lpdwResult
0x180008942  mov     [rsp+140h+uTimeout], 2710h; uTimeout
0x18000894a  mov     [rsp+140h+fuFlags], 2; fuFlags
0x180008952  call    cs:__imp_SendMessageTimeoutW
0x180008958  mov     ecx, 0FFFFFFFFh
0x18000895d  mov     rsi, [rsp+140h+dwResult]
0x180008962  test    esi, esi
0x180008964  js      loc_180008B6F
0x18000896a  test    rsi, rsi
0x18000896d  jz      loc_1800090E5
0x180008973  mov     qword ptr [r12], 0
0x18000897b  test    esi, esi
0x18000897d  js      loc_180009154
0x180008983  cmp     r14, rcx
0x180008986  jnz     loc_18000910F
0x18000898c  call    cs:__imp_GetCurrentProcessId
0x180008992  mov     r15d, eax
0x180008995  mov     eax, esi
0x180008997  mov     [rsp+140h+hFileMappingObject], 0
0x1800089a0  shr     eax, 10h
0x1800089a3  test    ax, ax
0x1800089a6  jnz     loc_180008B5A
0x1800089ac  test    si, si
0x1800089af  jz      loc_180008B5A
0x1800089b5  mov     r8d, 2Ah ; '*'; nSize
0x1800089bb  lea     rdx, [rbp+40h+Buffer]; lpBuffer
0x1800089bf  movzx   ecx, si; nAtom
0x1800089c2  call    cs:__imp_GlobalGetAtomNameW
0x1800089c8  cmp     eax, 29h ; ')'
0x1800089cb  jnz     loc_180008B5A
0x1800089d1  mov     r8d, 0Ah; Size
0x1800089d7  lea     rdx, aMsaa_0; "MSAA:"
0x1800089de  lea     rcx, [rbp+40h+Buffer]; Buf1
0x1800089e2  call    memcmp_0
0x1800089e7  test    eax, eax
0x1800089e9  jnz     loc_180008B5A
0x1800089ef  cmp     [rbp+40h+var_96], 3Ah ; ':'
0x1800089f4  jnz     loc_180008B5A
0x1800089fa  cmp     [rbp+40h+var_84], 3Ah ; ':'
0x1800089ff  jnz     loc_180008B5A
0x180008a05  cmp     [rbp+40h+var_72], 3Ah ; ':'
0x180008a0a  jnz     loc_180008B5A
0x180008a10  cmp     [rbp+40h+var_60], 3Ah ; ':'
0x180008a15  jnz     loc_180008B5A
0x180008a1b  cmp     [rbp+40h+var_5E], ax
0x180008a1f  jnz     loc_180008B5A
0x180008a25  xor     edi, edi
0x180008a27  lea     r8, [rbp+40h+var_A6]
0x180008a2b  xor     ecx, ecx
0x180008a2d  nop     dword ptr [rax]
0x180008a30  cmp     ecx, 8
0x180008a33  jge     loc_180008DA7
0x180008a39  movzx   edx, word ptr [r8]
0x180008a3d  shl     edi, 4
0x180008a40  lea     eax, [rdx-30h]
0x180008a43  cmp     ax, 9
0x180008a47  ja      loc_180008B2C
0x180008a4d  add     edi, 0FFFFFFD0h
0x180008a50  add     edi, edx
0x180008a52  inc     ecx
0x180008a54  add     r8, 2
0x180008a58  jmp     short loc_180008A30
0x180008a5a  lea     rcx, aUser32Dll_0; "USER32.DLL"
0x180008a61  mov     cs:?g_fInitedOleacc@@3HA, 1; int g_fInitedOleacc
0x180008a6b  call    cs:__imp_GetModuleHandleW
0x180008a71  lea     rcx, aApiMsWinCoreLi_1; "api-ms-win-core-libraryloader-l1-2-0.DL"...
0x180008a78  mov     [rsp+140h+ppstm], rax
0x180008a7d  call    cs:__imp_GetModuleHandleW
0x180008a83  mov     [rsp+140h+var_E0], rax
0x180008a88  test    rax, rax
0x180008a8b  jz      loc_18000929A
0x180008a91  lea     rcx, aApiMsWinCoreMe_0; "api-ms-win-core-memory-l1-1-2.DLL"
0x180008a98  call    cs:__imp_GetModuleHandleW
0x180008a9e  mov     [rsp+140h+var_D8], rax
0x180008aa3  test    rax, rax
0x180008aa6  jz      loc_1800092B1
0x180008aac  lea     rcx, aNtdllDll_0; "NTDLL.DLL"
0x180008ab3  call    cs:__imp_GetModuleHandleW
0x180008ab9  lea     rcx, [rsp+140h+ppstm]; HINSTANCE *
0x180008abe  mov     [rsp+140h+var_D0], rax
0x180008ac3  call    ?ImportFromModule@@YAXPEAPEAUHINSTANCE__@@PEBUImportInfo@@H@Z; ImportFromModule(HINSTANCE__ * *,ImportInfo const *,int)
0x180008ac8  lea     rcx, LibFileName; "OLEAUT32.DLL"
0x180008acf  call    cs:__imp_LoadLibraryW
0x180008ad5  xor     ebx, ebx
0x180008ad7  lea     rcx, __ImageBase
0x180008ade  xchg    ax, ax
0x180008ae0  cmp     ebx, 20h ; ' '
0x180008ae3  jnb     short loc_180008B16
0x180008ae5  movsxd  rax, ebx
0x180008ae8  mov     rcx, ds:rva off_180052380[rcx+rax*8]; lpString
0x180008af0  lea     rdi, [rax+rax]
0x180008af4  test    rcx, rcx
0x180008af7  jz      loc_1800092C8
0x180008afd  call    cs:__imp_GlobalAddAtomW
0x180008b03  lea     rcx, __ImageBase
0x180008b0a  inc     ebx
0x180008b0c  mov     [rdi+rcx+61C60h], ax
0x180008b14  jmp     short loc_180008AE0
0x180008b16  call    IsProxyRegistrationCorrect
0x180008b1b  test    eax, eax
0x180008b1d  jz      loc_1800092DB
0x180008b23  mov     edi, [rsp+140h+idObject]
0x180008b27  jmp     loc_1800088C8
0x180008b2c  lea     eax, [rdx-41h]
0x180008b2f  cmp     ax, 5
0x180008b33  ja      loc_180009315
0x180008b39  add     edi, 0FFFFFFC9h
0x180008b3c  inc     ecx
0x180008b3e  add     edi, edx
0x180008b40  add     r8, 2
0x180008b44  jmp     loc_180008A30
0x180008b49  call    GetProcessHandleFromHwnd
0x180008b4e  mov     rsi, rax
0x180008b51  test    rax, rax
0x180008b54  jnz     loc_1800091D4
0x180008b5a  mov     esi, 80004005h
0x180008b5f  mov     ecx, 0FFFFFFFFh
0x180008b64  cmp     r14, rcx
0x180008b67  jnz     loc_1800090E5
0x180008b6d  test    esi, esi
0x180008b6f  jnz     loc_1800093A6
0x180008b75  cmp     qword ptr [r12], 0
0x180008b7a  mov     r14, [rbp+40h+riid]
0x180008b7e  mov     r15, [rsp+140h+hwnd]
0x180008b83  jz      loc_180008E6B
0x180008b89  test    esi, esi
0x180008b8b  jnz     loc_180008D85
0x180008b91  test    r12, r12
0x180008b94  jz      loc_180008D85
0x180008b9a  mov     rdi, [r12]
0x180008b9e  test    rdi, rdi
0x180008ba1  jz      loc_180008D85
0x180008ba7  xor     r13d, r13d
0x180008baa  lea     r8, [rsp+140h+ppstm]
0x180008baf  mov     [rsp+140h+ppstm], r13
0x180008bb4  lea     rdx, IID_IAccessible
0x180008bbb  mov     rax, [rdi]
0x180008bbe  mov     rcx, rdi
0x180008bc1  mov     rax, [rax]
0x180008bc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bc9  test    eax, eax
0x180008bcb  jnz     loc_1800090EC
0x180008bd1  mov     rcx, [rsp+140h+ppstm]
0x180008bd6  test    rcx, rcx
0x180008bd9  jz      loc_1800090EC
0x180008bdf  mov     rax, [rcx]
0x180008be2  mov     rax, [rax+10h]
0x180008be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008beb  mov     rax, [rdi]
0x180008bee  lea     r8, [rsp+140h+hwnd]
0x180008bf3  lea     rdx, IID_IServiceProvider
0x180008bfa  mov     [rsp+140h+hwnd], r13
0x180008bff  mov     rcx, rdi
0x180008c02  mov     rax, [rax]
0x180008c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c0a  test    eax, eax
0x180008c0c  jnz     short loc_180008C57
0x180008c0e  mov     rcx, [rsp+140h+hwnd]
0x180008c13  test    rcx, rcx
0x180008c16  jz      short loc_180008C57
0x180008c18  mov     [rsp+140h+dwResult], r13
0x180008c1d  lea     r9, [rsp+140h+dwResult]
0x180008c22  mov     rax, [rcx]
0x180008c25  lea     r8, IID_IUnknown
0x180008c2c  lea     rdx, ?IIS_AccWrapBase_GetIUnknown@@3U_GUID@@A; _GUID IIS_AccWrapBase_GetIUnknown
0x180008c33  mov     rax, [rax+18h]
0x180008c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c3c  mov     rcx, [rsp+140h+hwnd]
0x180008c41  mov     ebx, eax
0x180008c43  mov     rdx, [rcx]
0x180008c46  mov     rax, [rdx+10h]
0x180008c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c4f  test    ebx, ebx
0x180008c51  jz      loc_18000911E
0x180008c57  mov     edx, 0A8h; uBytes
0x180008c5c  mov     ecx, 40h ; '@'; uFlags
0x180008c61  call    cs:__imp_LocalAlloc
0x180008c67  mov     rbx, rax
0x180008c6a  test    rax, rax
0x180008c6d  jz      loc_18000923C
0x180008c73  mov     dword ptr [rbx+28h], 1
0x180008c7a  lea     rax, ??_7AccWrap_Base@@6BIAccessible@@@; const AccWrap_Base::`vftable'{for `IAccessible'}
0x180008c81  mov     [rbx], rax
0x180008c84  mov     rcx, rdi
0x180008c87  mov     [rbx+30h], rdi
0x180008c8b  lea     rax, ??_7AccWrap_Base@@6BIOleWindow@@@; const AccWrap_Base::`vftable'{for `IOleWindow'}
0x180008c92  mov     [rbx+8], rax
0x180008c96  lea     rax, ??_7AccWrap_Base@@6BIEnumVARIANT@@@; const AccWrap_Base::`vftable'{for `IEnumVARIANT'}
0x180008c9d  mov     [rbx+10h], rax
0x180008ca1  lea     rax, ??_7AccWrap_Base@@6BIAccIdentity@@@; const AccWrap_Base::`vftable'{for `IAccIdentity'}
0x180008ca8  mov     [rbx+18h], rax
0x180008cac  lea     rax, ??_7AccWrap_Base@@6BIServiceProvider@@@; const AccWrap_Base::`vftable'{for `IServiceProvider'}
0x180008cb3  mov     [rbx+20h], rax
0x180008cb7  mov     [rbx+40h], r13
0x180008cbb  mov     [rbx+48h], r13
0x180008cbf  mov     [rbx+50h], r13
0x180008cc3  mov     [rbx+58h], r13
0x180008cc7  mov     [rbx+60h], r13
0x180008ccb  mov     [rbx+68h], r13d
0x180008ccf  mov     [rbx+70h], r13
0x180008cd3  mov     rax, [rdi]
0x180008cd6  mov     [rbx+38h], rax
0x180008cda  mov     rax, [rdi]
0x180008cdd  mov     rax, [rax+8]
0x180008ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ce6  lea     rax, ??_7AccWrap_LocationEtcFix@@6BIAccessible@@@; const AccWrap_LocationEtcFix::`vftable'{for `IAccessible'}
0x180008ced  mov     [rbx+78h], r13
0x180008cf1  mov     [rbx], rax
0x180008cf4  mov     r8, r12
0x180008cf7  lea     rax, ??_7AccWrap_LocationEtcFix@@6BIOleWindow@@@; const AccWrap_LocationEtcFix::`vftable'{for `IOleWindow'}
0x180008cfe  mov     [rbx+80h], r13d
0x180008d05  mov     [rbx+8], rax
0x180008d09  mov     rdx, r14
0x180008d0c  lea     rax, ??_7AccWrap_LocationEtcFix@@6BIEnumVARIANT@@@; const AccWrap_LocationEtcFix::`vftable'{for `IEnumVARIANT'}
0x180008d13  mov     [rbx+88h], r13d
0x180008d1a  mov     [rbx+10h], rax
0x180008d1e  mov     rcx, rbx
0x180008d21  lea     rax, ??_7AccWrap_LocationEtcFix@@6BIAccIdentity@@@; const AccWrap_LocationEtcFix::`vftable'{for `IAccIdentity'}
0x180008d28  mov     [rbx+90h], r13
0x180008d2f  mov     [rbx+18h], rax
0x180008d33  lea     rax, ??_7AccWrap_LocationEtcFix@@6BIServiceProvider@@@; const AccWrap_LocationEtcFix::`vftable'{for `IServiceProvider'}
0x180008d3a  mov     [rbx+20h], rax
0x180008d3e  mov     [rbx+98h], r13
0x180008d45  mov     [rbx+0A0h], r15
0x180008d4c  mov     rax, cs:??_7AccWrap_LocationEtcFix@@6BIAccessible@@@; const AccWrap_LocationEtcFix::`vftable'{for `IAccessible'}
0x180008d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d58  mov     r14d, eax
0x180008d5b  mov     rcx, rbx
0x180008d5e  mov     rax, [rbx]
0x180008d61  mov     rax, [rax+10h]
0x180008d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d6a  mov     esi, r14d
0x180008d6d  test    r14d, r14d
0x180008d70  js      loc_180009241
0x180008d76  mov     rax, [rdi]
0x180008d79  mov     rcx, rdi
0x180008d7c  mov     rax, [rax+10h]
0x180008d80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d85  mov     eax, esi
0x180008d87  mov     rcx, [rbp+40h+var_50]
0x180008d8b  xor     rcx, rsp; StackCookie
0x180008d8e  call    __security_check_cookie
0x180008d93  add     rsp, 108h
0x180008d9a  pop     r15
0x180008d9c  pop     r14
0x180008d9e  pop     r13
0x180008da0  pop     r12
0x180008da2  pop     rdi
  ... truncated ...
```

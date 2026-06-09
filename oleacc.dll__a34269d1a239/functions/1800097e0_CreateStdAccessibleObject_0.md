# CreateStdAccessibleObject_0

- ea: `0x1800097e0`
- end: `0x18000a5d8`
- name: `CreateStdAccessibleObject_0`
- size: `3576`
- prototype: `HRESULT __stdcall(HWND hwnd, LONG idObject, const IID *const riid, void **ppvObject)`
- caller_count: `5`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180007b90`
- `0x180008870`
- `0x18000aa10`
- `0x18000b360`
- `0x18001b020`

## callees

- `0x180002804`
- `0x180002910`
- `0x180008870`
- `0x1800097e0`
- `0x18000a5e0`
- `0x18000b48c`
- `0x18000baa0`
- `0x18000c594`
- `0x180016820`
- `0x180016d6c`
- `0x18001bb6c`
- `0x18001e4c0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ec3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a31d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a33e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ec3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a31d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a33e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180009d1b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000a12e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180009d1b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000a12e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a17e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a395`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a58c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a17e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a395`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a58c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009c33`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009cc8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009e6c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009c33`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009cc8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009e6c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180009e0a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180009e26`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180009e0a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180009e26`
- `api-ms-win-core-atoms-l1-1-0!GlobalFindAtomW` at `0x1800098bd`
- `api-ms-win-core-atoms-l1-1-0!GlobalFindAtomW` at `0x18000992c`
- `api-ms-win-core-atoms-l1-1-0!GlobalFindAtomW` at `0x180009b32`
- `api-ms-win-core-atoms-l1-1-0!GlobalFindAtomW` at `0x180009fb6`
- `api-ms-win-core-atoms-l1-1-0!GlobalFindAtomW` at `0x18000a1d1`
- `api-ms-win-core-atoms-l1-1-0!GlobalFindAtomW` at `0x18000a227`
- `api-ms-win-core-atoms-l1-1-0!GlobalFindAtomW` at `0x1800098bd`
- `api-ms-win-core-atoms-l1-1-0!GlobalFindAtomW` at `0x18000992c`
- `api-ms-win-core-atoms-l1-1-0!GlobalFindAtomW` at `0x180009b32`
- `api-ms-win-core-atoms-l1-1-0!GlobalFindAtomW` at `0x180009fb6`
- `api-ms-win-core-atoms-l1-1-0!GlobalFindAtomW` at `0x18000a1d1`
- `api-ms-win-core-atoms-l1-1-0!GlobalFindAtomW` at `0x18000a227`
- `USER32!SendMessageTimeoutW` at `0x1800099a4`
- `USER32!SendMessageTimeoutW` at `0x180009a83`
- `USER32!SendMessageTimeoutW` at `0x180009b9d`
- `USER32!SendMessageTimeoutW` at `0x1800099a4`
- `USER32!SendMessageTimeoutW` at `0x180009a83`
- `USER32!SendMessageTimeoutW` at `0x180009b9d`
- `USER32!GetWindowThreadProcessId` at `0x180009d01`
- `USER32!GetWindowThreadProcessId` at `0x18000a114`
- `USER32!GetWindowThreadProcessId` at `0x180009d01`
- `USER32!GetWindowThreadProcessId` at `0x18000a114`
- `USER32!IsWindow` at `0x18000987a`
- `USER32!IsWindow` at `0x1800099db`
- `USER32!IsWindow` at `0x180009aef`
- `USER32!IsWindow` at `0x180009c59`
- `USER32!IsWindow` at `0x180009e37`
- `USER32!IsWindow` at `0x180009e96`
- `USER32!IsWindow` at `0x18000a070`
- `USER32!IsWindow` at `0x18000987a`
- `USER32!IsWindow` at `0x1800099db`
- `USER32!IsWindow` at `0x180009aef`
- `USER32!IsWindow` at `0x180009c59`
- `USER32!IsWindow` at `0x180009e37`
- `USER32!IsWindow` at `0x180009e96`
- `USER32!IsWindow` at `0x18000a070`
- `USER32!GetDesktopWindow` at `0x18000a30e`
- `USER32!GetDesktopWindow` at `0x18000a32f`
- `USER32!GetDesktopWindow` at `0x18000a30e`
- `USER32!GetDesktopWindow` at `0x18000a32f`
- `USER32!FindWindowExW` at `0x18000a3ea`
- `USER32!FindWindowExW` at `0x18000a40b`
- `USER32!FindWindowExW` at `0x18000a42c`
- `USER32!FindWindowExW` at `0x18000a44d`
- `USER32!FindWindowExW` at `0x18000a3ea`
- `USER32!FindWindowExW` at `0x18000a40b`
- `USER32!FindWindowExW` at `0x18000a42c`
- `USER32!FindWindowExW` at `0x18000a44d`
- `USER32!LoadCursorW` at `0x18000a556`
- `USER32!LoadCursorW` at `0x18000a556`
- `USER32!GetClassNameW` at `0x180009df2`
- `USER32!GetClassNameW` at `0x18000a4ef`
- `USER32!GetClassNameW` at `0x18000a4fa`
- `USER32!GetClassNameW` at `0x18000a572`
- `USER32!GetClassNameW` at `0x180009df2`
- `USER32!GetClassNameW` at `0x18000a4ef`
- `USER32!GetClassNameW` at `0x18000a4fa`
- `USER32!GetClassNameW` at `0x18000a572`

## pseudocode

```c
HRESULT __stdcall CreateStdAccessibleObject_0(HWND hwnd, LONG idObject, const IID *const riid, void **ppvObject)
{
  __int64 v4; // r15
  __int64 v9; // rbx
  int v10; // r12d
  int v11; // eax
  int ClassNameW; // eax
  int v13; // r14d
  ATOM AtomW; // ax
  int v15; // ecx
  int v16; // eax
  ATOM v17; // ax
  int v18; // ecx
  signed int v19; // eax
  HRESULT RemoteProxy6432; // ebx
  __int64 v23; // rbx
  int v24; // eax
  int v25; // r14d
  ATOM v26; // ax
  int v27; // ecx
  CScrollBar *v28; // rax
  CScrollBar *v29; // r15
  CTitleBar *v30; // rax
  HANDLE v31; // r15
  int v32; // ebx
  int v33; // eax
  CSizeGrip *v34; // rax
  CSizeGrip *v35; // rax
  CTitleBar *v36; // r14
  BOOL v37; // eax
  __int64 v38; // r9
  signed int v39; // eax
  signed int LastError; // eax
  signed int v41; // eax
  const WCHAR *v42; // rcx
  ATOM v43; // dx
  __int64 v44; // rax
  int v45; // eax
  __int64 (__fastcall **v46)(CTitleBar *, const IID *const, void **); // rax
  __int64 v47; // rax
  bool v48; // zf
  HANDLE v49; // rax
  int v50; // ebx
  const WCHAR *v51; // rcx
  ATOM v52; // dx
  int i; // eax
  const WCHAR *v54; // rcx
  ATOM v55; // dx
  int j; // eax
  _BOOL8 v57; // rax
  _BOOL8 v58; // rax
  HWND v59; // r14
  HWND Window; // rax
  HWND v61; // r12
  HWND v62; // r15
  HWND v63; // rax
  HWND v64; // rax
  __int64 *v65; // rcx
  __int64 v66; // rax
  DWORD dwProcessId[2]; // [rsp+48h] [rbp-C0h] BYREF
  ULONG_PTR dwResult; // [rsp+50h] [rbp-B8h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-B0h]
  __int64 v70; // [rsp+60h] [rbp-A8h]
  __int128 v71; // [rsp+68h] [rbp-A0h]
  __int64 v72; // [rsp+78h] [rbp-90h]
  __int128 v73; // [rsp+80h] [rbp-88h] BYREF
  __int64 v74; // [rsp+90h] [rbp-78h]
  __int128 v75; // [rsp+98h] [rbp-70h] BYREF
  __int64 v76; // [rsp+A8h] [rbp-60h]
  WCHAR String[128]; // [rsp+B8h] [rbp-50h] BYREF
  WCHAR ClassName[128]; // [rsp+1B8h] [rbp+B0h] BYREF
  __int64 v79; // [rsp+2E0h] [rbp+1D8h]

  if ( !ppvObject )
    return -2147024809;
  v9 = 0;
  v79 = v4;
  *ppvObject = 0;
  if ( !hwnd )
  {
    if ( idObject == -9 )
    {
      v11 = 0;
      v10 = 1;
LABEL_5:
      switch ( v11 )
      {
        case 0:
          if ( !_InterlockedExchange(&fCursorDataInit, 1) )
          {
            do
            {
              (&rghcurSystem)[v9] = (HICON near *)LoadCursorW(0, (LPCWSTR)(&rghcurSystem)[v9]);
              ++v9;
            }
            while ( v9 != 15 );
          }
          return CreateCursorThing(riid, ppvObject);
        case 1:
          return CreateCaretThing(hwnd, riid, ppvObject);
        case 2:
          *ppvObject = 0;
          v34 = (CSizeGrip *)LocalAlloc(0x40u, 0x78u);
          if ( !v34 )
            return -2147024882;
          v35 = CSizeGrip::CSizeGrip(v34);
          v36 = v35;
          if ( !v35 )
            return -2147024882;
          *((_QWORD *)v35 + 10) = hwnd;
          v37 = IsWindow(hwnd);
          v38 = *(_QWORD *)v36;
          if ( !v37 )
          {
            (*(void (__fastcall **)(CTitleBar *, __int64))(v38 + 224))(v36, 1);
            return -2147467259;
          }
          v45 = (*(__int64 (__fastcall **)(CTitleBar *, const IID *const, void **))v38)(v36, riid, ppvObject);
          goto LABEL_114;
        case 3:
        case 4:
          *ppvObject = 0;
          v28 = (CScrollBar *)LocalAlloc(0x40u, 0x88u);
          if ( !v28 )
            return -2147024882;
          v29 = CScrollBar::CScrollBar(v28);
          if ( !v29 )
            return -2147024882;
          if ( !IsWindow(hwnd) )
          {
            (*(void (__fastcall **)(CScrollBar *, __int64))(*(_QWORD *)v29 + 224LL))(v29, 1);
            return -2147467259;
          }
          *((_QWORD *)v29 + 10) = hwnd;
          *(_QWORD *)((char *)v29 + 92) = 5;
          *((_DWORD *)v29 + 32) = idObject == -5;
          RemoteProxy6432 = (**(__int64 (__fastcall ***)(CScrollBar *, const IID *const, void **))v29)(
                              v29,
                              riid,
                              ppvObject);
          if ( RemoteProxy6432 < 0 )
            (*(void (__fastcall **)(CScrollBar *, __int64))(*(_QWORD *)v29 + 224LL))(v29, 1);
          return RemoteProxy6432;
        case 5:
          *ppvObject = 0;
          if ( !IsWindow(hwnd) )
            return -2147467259;
          String[0] = 0;
          if ( lpfnRealGetWindowClass )
            ClassNameW = ((__int64 (__fastcall *)(HWND, WCHAR *, __int64))lpfnRealGetWindowClass)(hwnd, String, 128);
          else
            ClassNameW = GetClassNameW(hwnd, String, 128);
          if ( !ClassNameW )
            goto LABEL_37;
          v13 = 0;
          AtomW = GlobalFindAtomW(String);
          if ( !AtomW )
            goto LABEL_34;
          v15 = 0;
          while ( 2 )
          {
            if ( v15 < 32 )
            {
              if ( *((_WORD *)&rgAtomClasses + v15) != AtomW )
              {
                ++v15;
                continue;
              }
              _mm_lfence();
              v13 = dword_180054260[v15];
              if ( v13 != -1 )
                goto LABEL_38;
            }
            break;
          }
LABEL_34:
          dwResult = 0;
          if ( !SendMessageTimeoutW(hwnd, 0x3Du, 0, -12, 2u, 0x4E20u, &dwResult) )
          {
            LastError = GetLastError();
            LODWORD(v9) = LastError;
            if ( LastError == 1460 )
            {
              LODWORD(v9) = -2146233083;
            }
            else if ( LastError > 0 )
            {
              LODWORD(v9) = (unsigned __int16)LastError | 0x80070000;
            }
            Error::IAccessibleError(0, L"SendMessageTimeoutHelper", v9, hwnd, 5002);
          }
          if ( (int)v9 < 0 )
          {
            Error::IAccessibleError(0, L"OleAcc: LookupWindowClass", v9, hwnd, 5002);
            goto LABEL_37;
          }
          if ( dwResult < 0x10000 )
            goto LABEL_37;
          if ( dwResult - 0x10000 > 0x1F )
            goto LABEL_37;
          v51 = off_180052380[dwResult - 0x10000];
          if ( !v51 )
            goto LABEL_37;
          v52 = GlobalFindAtomW(v51);
          if ( v52 )
          {
            for ( i = 0; i < 32; ++i )
            {
              if ( *((_WORD *)&rgAtomClasses + i) == v52 )
              {
                _mm_lfence();
                v13 = dword_180054260[i];
                v57 = v13 != -1;
                goto LABEL_152;
              }
            }
            LODWORD(v57) = 0;
          }
          else
          {
            LODWORD(v57) = 0;
          }
LABEL_152:
          if ( !v57 )
LABEL_37:
            v13 = 1;
LABEL_38:
          v23 = 40LL * v13;
          if ( *(_DWORD *)&algn_18004A398[v23] )
            return (*(__int64 (__fastcall **)(HWND, _QWORD, const IID *const, void **))((char *)&g_ClassInfo + v23))(
                     hwnd,
                     0,
                     riid,
                     ppvObject);
          dwProcessId[0] = 0;
          if ( (int)SameBitness(hwnd, (int *)dwProcessId) < 0 )
            return -2147467259;
          if ( dwProcessId[0] )
            return (*(__int64 (__fastcall **)(HWND, _QWORD, const IID *const, void **))((char *)&g_ClassInfo + v23))(
                     hwnd,
                     0,
                     riid,
                     ppvObject);
          return CreateRemoteProxy6432(hwnd, 0xFFFFFFFC, riid, ppvObject);
        case 6:
          if ( !GetClassNameW(hwnd, ClassName, 128)
            || lstrcmpW(ClassName, L"IEFrame") && lstrcmpW(ClassName, L"CabinetWClass") )
          {
            goto LABEL_82;
          }
          v72 = 0;
          v59 = 0;
          v71 = 0;
          v74 = 0;
          v73 = 0;
          while ( 1 )
          {
            Window = FindWindowExW(hwnd, v59, L"Worker", 0);
            v59 = Window;
            if ( !Window )
              break;
            v61 = FindWindowExW(Window, 0, L"RebarWindow32", 0);
            if ( v61 )
            {
              v62 = 0;
              while ( 1 )
              {
                v63 = FindWindowExW(v61, v62, L"SysPager", 0);
                v62 = v63;
                if ( !v63 )
                  break;
                v64 = FindWindowExW(v63, 0, L"ToolbarWindow32", 0);
                RemoteProxy6432 = AccessibleObjectFromWindowTimeout(
                                    0x80000u,
                                    0x4E20u,
                                    v64,
                                    -3,
                                    &IID_IAccessible,
                                    ppvObject);
                if ( RemoteProxy6432 >= 0 )
                {
                  v65 = (__int64 *)*ppvObject;
                  DWORD2(v71) = 0;
                  LOWORD(v71) = 3;
                  v66 = *v65;
                  v76 = 0;
                  v75 = v71;
                  if ( (*(int (__fastcall **)(__int64 *, __int128 *, __int128 *))(v66 + 112))(v65, &v75, &v73) >= 0
                    && (WORD4(v73) & 0x8000) == 0 )
                  {
                    return RemoteProxy6432;
                  }
                }
                if ( *ppvObject )
                  (*(void (__fastcall **)(void *))(*(_QWORD *)*ppvObject + 16LL))(*ppvObject);
              }
            }
          }
LABEL_82:
          if ( !IsWindow(hwnd) )
            return -2147467259;
          return CreateMenuBar(hwnd, 0, 0, riid, ppvObject);
        case 7:
          *ppvObject = 0;
          v30 = (CTitleBar *)LocalAlloc(0x40u, 0x78u);
          if ( !v30 )
            return -2147024882;
          v36 = CTitleBar::CTitleBar(v30);
          if ( !v36 )
            return -2147024882;
          if ( !IsWindow(hwnd) )
          {
            (*(void (__fastcall **)(CTitleBar *, __int64))(*(_QWORD *)v36 + 224LL))(v36, 1);
            return -2147467259;
          }
          v46 = *(__int64 (__fastcall ***)(CTitleBar *, const IID *const, void **))v36;
          *((_QWORD *)v36 + 10) = hwnd;
          *(_QWORD *)((char *)v36 + 92) = 5;
          v45 = (*v46)(v36, riid, ppvObject);
LABEL_114:
          RemoteProxy6432 = v45;
          if ( v45 < 0 )
            (*(void (__fastcall **)(CTitleBar *, __int64))(*(_QWORD *)v36 + 224LL))(v36, 1);
          return RemoteProxy6432;
        case 9:
          *ppvObject = 0;
          if ( !IsWindow(hwnd) )
            return -2147467259;
          String[0] = 0;
          if ( lpfnRealGetWindowClass )
            v24 = ((__int64 (__fastcall *)(HWND, WCHAR *, __int64))lpfnRealGetWindowClass)(hwnd, String, 128);
          else
            v24 = GetClassNameW(hwnd, String, 128);
          if ( !v24 )
            goto LABEL_53;
          v25 = 0;
          v26 = GlobalFindAtomW(String);
          if ( !v26 )
            goto LABEL_50;
          v27 = 0;
          while ( 2 )
          {
            if ( v27 < 2 )
            {
              if ( *((_WORD *)&rgAtomClasses + v27) != v26 )
              {
                ++v27;
                continue;
              }
              _mm_lfence();
              v25 = *(_DWORD *)&g_WindowClassMap[4 * v27];
              if ( v25 != -1 )
                goto LABEL_54;
            }
            break;
          }
LABEL_50:
          dwResult = 0;
          if ( !SendMessageTimeoutW(hwnd, 0x3Du, 0, -12, 2u, 0x4E20u, &dwResult) )
          {
            v41 = GetLastError();
            LODWORD(v9) = v41;
            if ( v41 == 1460 )
            {
              LODWORD(v9) = -2146233083;
            }
            else if ( v41 > 0 )
            {
              LODWORD(v9) = (unsigned __int16)v41 | 0x80070000;
            }
            Error::IAccessibleError(0, L"SendMessageTimeoutHelper", v9, hwnd, 5002);
          }
          if ( (int)v9 < 0 )
          {
            Error::IAccessibleError(0, L"OleAcc: LookupWindowClass", v9, hwnd, 5002);
            goto LABEL_53;
          }
          if ( dwResult < 0x10000 )
            goto LABEL_53;
          if ( dwResult - 0x10000 > 0x1F )
            goto LABEL_53;
          v54 = off_180052380[dwResult - 0x10000];
          if ( !v54 )
            goto LABEL_53;
          v55 = GlobalFindAtomW(v54);
          if ( v55 )
          {
            for ( j = 0; j < 2; ++j )
            {
              if ( *((_WORD *)&rgAtomClasses + j) == v55 )
              {
                _mm_lfence();
                v25 = *(_DWORD *)&g_WindowClassMap[4 * j];
                v58 = v25 != -1;
                goto LABEL_155;
              }
            }
            LODWORD(v58) = 0;
          }
          else
          {
            LODWORD(v58) = 0;
          }
LABEL_155:
          if ( !v58 )
LABEL_53:
            v25 = 8;
LABEL_54:
          v23 = 40LL * v25;
          if ( *(_DWORD *)&algn_18004A398[v23] )
            return (*(__int64 (__fastcall **)(HWND, _QWORD, const IID *const, void **))((char *)&g_ClassInfo + v23))(
                     hwnd,
                     0,
                     riid,
                     ppvObject);
          dwProcessId[0] = 0;
          if ( (int)SameBitness(hwnd, (int *)dwProcessId) < 0 )
            return -2147467259;
          if ( dwProcessId[0] )
            return (*(__int64 (__fastcall **)(HWND, _QWORD, const IID *const, void **))((char *)&g_ClassInfo + v23))(
                     hwnd,
                     0,
                     riid,
                     ppvObject);
          else
            return CreateRemoteProxy6432(hwnd, 0, riid, ppvObject);
        default:
          String[0] = 0;
          if ( lpfnRealGetWindowClass )
            v16 = ((__int64 (__fastcall *)(HWND, WCHAR *, __int64))lpfnRealGetWindowClass)(hwnd, String, 128);
          else
            v16 = GetClassNameW(hwnd, String, 128);
          if ( !v16 )
            goto LABEL_27;
          dwProcessId[0] = 0;
          v17 = GlobalFindAtomW(String);
          if ( !v17 )
            goto LABEL_24;
          v18 = 0;
          while ( 2 )
          {
            if ( v18 < 2 )
            {
              if ( *((_WORD *)&rgAtomClasses + v18) != v17 )
              {
                ++v18;
                continue;
              }
              _mm_lfence();
              v19 = *(_DWORD *)&g_WindowClassMap[4 * v18];
              dwProcessId[0] = v19;
              if ( v19 != -1 )
                goto LABEL_122;
            }
            break;
          }
LABEL_24:
          dwResult = 0;
          if ( !SendMessageTimeoutW(hwnd, 0x3Du, 0, -12, 2u, 0x4E20u, &dwResult) )
          {
            v39 = GetLastError();
            LODWORD(v9) = v39;
            if ( v39 == 1460 )
            {
              LODWORD(v9) = -2146233083;
            }
            else if ( v39 > 0 )
            {
              LODWORD(v9) = (unsigned __int16)v39 | 0x80070000;
            }
            Error::IAccessibleError(0, L"SendMessageTimeoutHelper", v9, hwnd, 5002);
          }
          if ( (int)v9 < 0 )
          {
            Error::IAccessibleError(0, L"OleAcc: LookupWindowClass", v9, hwnd, 5002);
            *ppvObject = 0;
            return -2147467259;
          }
          if ( dwResult < 0x10000 )
            goto LABEL_27;
          if ( dwResult - 0x10000 > 0x1F )
            goto LABEL_27;
          v42 = off_180052380[dwResult - 0x10000];
          if ( !v42 )
            goto LABEL_27;
          v43 = GlobalFindAtomW(v42);
          LODWORD(v44) = 0;
          if ( v43 )
          {
            while ( (int)v44 < 2 )
            {
              if ( *((_WORD *)&rgAtomClasses + (int)v44) == v43 )
              {
                _mm_lfence();
                dwProcessId[0] = *(_DWORD *)&g_WindowClassMap[4 * (int)v44];
                v44 = dwProcessId[0] != -1;
                goto LABEL_120;
              }
              LODWORD(v44) = v44 + 1;
            }
            LODWORD(v44) = 0;
          }
LABEL_120:
          if ( !(_DWORD)v44 )
          {
LABEL_27:
            *ppvObject = 0;
            return -2147467259;
          }
          v19 = dwProcessId[0];
LABEL_122:
          v47 = 40LL * v19;
          v48 = *(_DWORD *)&algn_18004A398[v47] == 0;
          v70 = v47;
          if ( !v48 )
            return (*(__int64 (__fastcall **)(HWND, _QWORD, const IID *const, void **))((char *)&g_ClassInfo + v47))(
                     hwnd,
                     0,
                     riid,
                     ppvObject);
          if ( dword_180061968 )
          {
            if ( dword_180061968 == 1 )
              return (*(__int64 (__fastcall **)(HWND, _QWORD, const IID *const, void **))((char *)&g_ClassInfo + v47))(
                       hwnd,
                       0,
                       riid,
                       ppvObject);
          }
          else
          {
            dword_180061968 = 2;
          }
          dwProcessId[0] = 0;
          if ( !GetWindowThreadProcessId(hwnd, dwProcessId) )
            return -2147467259;
          v49 = OpenProcess(0x400u, 0, dwProcessId[0]);
          hObject = v49;
          if ( v49 )
          {
            dwResult = 0;
            if ( lpfnNtQueryInformationProcess )
            {
              v50 = ((__int64 (__fastcall *)(HANDLE, __int64, ULONG_PTR *, __int64, _QWORD))lpfnNtQueryInformationProcess)(
                      v49,
                      26,
                      &dwResult,
                      8,
                      0);
              CloseHandle(hObject);
              if ( (v50 & 0xC0000000) != 0xC0000000 && dwResult )
                v10 = 0;
            }
            else
            {
              CloseHandle(v49);
            }
          }
          else if ( hwnd != GetDesktopWindow() )
          {
            GetLastError();
            return -2147467259;
          }
          if ( v10 )
          {
            v47 = v70;
            return (*(__int64 (__fastcall **)(HWND, _QWORD, const IID *const, void **))((char *)&g_ClassInfo + v47))(
                     hwnd,
                     0,
                     riid,
                     ppvObject);
          }
          RemoteProxy6432 = CreateRemoteProxy6432(hwnd, idObject, riid, ppvObject);
          break;
      }
      return RemoteProxy6432;
    }
    return -2147467259;
  }
  v10 = 1;
  if ( ((idObject + 3) & 0xFFFFFFFD) != 0 )
  {
LABEL_4:
    v11 = idObject + 9;
    goto LABEL_5;
  }
  if ( dword_180061968 )
  {
    if ( dword_180061968 == 1 )
      goto LABEL_74;
  }
  else
  {
    dword_180061968 = 2;
  }
  dwProcessId[0] = 0;
  if ( !GetWindowThreadProcessId(hwnd, dwProcessId) )
    return -2147467259;
  v31 = OpenProcess(0x400u, 0, dwProcessId[0]);
  if ( !v31 )
  {
    if ( hwnd == GetDesktopWindow() )
      goto LABEL_94;
    GetLastError();
    return -2147467259;
  }
  dwResult = 0;
  if ( !lpfnNtQueryInformationProcess )
  {
    CloseHandle(v31);
    goto LABEL_93;
  }
  v32 = lpfnNtQueryInformationProcess(v31, 26, &dwResult, 8u, 0);
  CloseHandle(v31);
  if ( (v32 & 0xC0000000) == 0xC0000000 )
  {
    v9 = 0;
LABEL_93:
    dwResult = 0;
    goto LABEL_94;
  }
  v9 = 0;
  if ( !dwResult )
  {
LABEL_94:
    v33 = 1;
    goto LABEL_73;
  }
  v33 = 0;
LABEL_73:
  if ( v33 )
  {
LABEL_74:
    if ( idObject == -1 )
    {
      if ( !IsWindow(hwnd) )
        return -2147467259;
      return CreateMenuBar(hwnd, 1, 0, riid, ppvObject);
    }
    goto LABEL_4;
  }
  return CreateRemoteProxy6432(hwnd, idObject, riid, ppvObject);
}

```

## disassembly

```asm
0x1800097e0  mov     r11, rsp
0x1800097e3  push    rbp
0x1800097e4  push    rsi
0x1800097e5  push    rdi
0x1800097e6  push    r13
0x1800097e8  push    r14
0x1800097ea  lea     rbp, [r11-218h]
0x1800097f1  sub     rsp, 2F0h
0x1800097f8  mov     rax, cs:__security_cookie
0x1800097ff  xor     rax, rsp
0x180009802  mov     [rbp+210h+var_60], rax
0x180009809  mov     rdi, r9
0x18000980c  mov     r13, r8
0x18000980f  mov     r14d, edx
0x180009812  mov     rsi, rcx
0x180009815  test    r9, r9
0x180009818  jz      loc_18000A37C
0x18000981e  mov     [r11-30h], rbx
0x180009822  xor     ebx, ebx
0x180009824  mov     [r11-38h], r12
0x180009828  mov     [r11-40h], r15
0x18000982c  movaps  xmmword ptr [r11-58h], xmm6
0x180009831  mov     [r9], rbx
0x180009834  test    rcx, rcx
0x180009837  jz      loc_180009FEF
0x18000983d  lea     eax, [rdx+3]
0x180009840  mov     r12d, 1
0x180009846  test    eax, 0FFFFFFFDh
0x18000984b  jz      loc_180009CE1
0x180009851  lea     eax, [r14+9]; switch 10 cases
0x180009855  cmp     eax, 9
0x180009858  ja      def_180009872; jumptable 0000000180009872 default case
0x18000985e  cdqe
0x180009860  lea     r15, __ImageBase
0x180009867  mov     eax, ds:(jpt_180009872 - 180000000h)[r15+rax*4]
0x18000986f  add     rax, r15
0x180009872  jmp     rax; switch jump
0x180009874  mov     rcx, rsi; jumptable 0000000180009872 case -4
0x180009877  mov     [rdi], rbx
0x18000987a  call    cs:__imp_IsWindow
0x180009880  test    eax, eax
0x180009882  jz      loc_1800099D1
0x180009888  mov     rax, cs:?lpfnRealGetWindowClass@@3P6AIPEAUHWND__@@PEAGI@ZEA; uint (*lpfnRealGetWindowClass)(HWND__ *,ushort *,uint)
0x18000988f  lea     rdx, [rbp+210h+String]; lpClassName
0x180009893  mov     [rbp+210h+String], bx
0x180009897  mov     r8d, 80h; nMaxCount
0x18000989d  mov     rcx, rsi; hWnd
0x1800098a0  test    rax, rax
0x1800098a3  jz      loc_18000A4EF
0x1800098a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098ae  test    eax, eax
0x1800098b0  jz      loc_180009AAB
0x1800098b6  lea     rcx, [rbp+210h+String]; lpString
0x1800098ba  mov     r14d, ebx
0x1800098bd  call    cs:__imp_GlobalFindAtomW
0x1800098c3  test    ax, ax
0x1800098c6  jz      loc_180009A4E
0x1800098cc  mov     ecx, ebx
0x1800098ce  xchg    ax, ax
0x1800098d0  cmp     ecx, 20h ; ' '
0x1800098d3  jge     loc_180009A4E
0x1800098d9  movsxd  rdx, ecx
0x1800098dc  cmp     rva ?rgAtomClasses@@3PAGA[r15+rdx*2], ax; ushort near * rgAtomClasses ...
0x1800098e5  jz      loc_180009A3D
0x1800098eb  inc     ecx
0x1800098ed  jmp     short loc_1800098D0
0x1800098ef  lea     r15, __ImageBase; jumptable 0000000180009872 default case
0x1800098f6  mov     rax, cs:?lpfnRealGetWindowClass@@3P6AIPEAUHWND__@@PEAGI@ZEA; jumptable 0000000180009872 case -1
0x1800098fd  lea     rdx, [rbp+210h+String]; lpClassName
0x180009901  mov     [rbp+210h+String], bx
0x180009905  mov     r8d, 80h; nMaxCount
0x18000990b  mov     rcx, rsi; hWnd
0x18000990e  test    rax, rax
0x180009911  jz      loc_18000A572
0x180009917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000991c  test    eax, eax
0x18000991e  jz      loc_1800099CE
0x180009924  lea     rcx, [rbp+210h+String]; lpString
0x180009928  mov     [rsp+310h+dwProcessId], ebx
0x18000992c  call    cs:__imp_GlobalFindAtomW
0x180009932  test    ax, ax
0x180009935  jz      short loc_18000996F
0x180009937  mov     ecx, ebx
0x180009939  nop     dword ptr [rax+00000000h]
0x180009940  cmp     ecx, 2
0x180009943  jge     short loc_18000996F
0x180009945  movsxd  rdx, ecx
0x180009948  cmp     rva ?rgAtomClasses@@3PAGA[r15+rdx*2], ax; ushort near * rgAtomClasses ...
0x180009951  jz      short loc_180009957
0x180009953  inc     ecx
0x180009955  jmp     short loc_180009940
0x180009957  lfence
0x18000995a  mov     eax, dword ptr ds:rva ?g_WindowClassMap@@3PAW4CLASS_ENUM@@A[r15+rdx*4]; "#" ...
0x180009962  mov     [rsp+310h+dwProcessId], eax
0x180009966  cmp     eax, 0FFFFFFFFh
0x180009969  jnz     loc_18000A0B8
0x18000996f  lea     rax, [rsp+310h+dwResult]
0x180009974  mov     [rsp+310h+dwResult], 0
0x18000997d  mov     [rsp+30h], rax; lpdwResult
0x180009982  mov     r9, 0FFFFFFFFFFFFFFF4h; lParam
0x180009989  mov     [rsp+310h+uTimeout], 4E20h; uTimeout
0x180009991  xor     r8d, r8d; wParam
0x180009994  mov     edx, 3Dh ; '='; Msg
0x180009999  mov     [rsp+310h+fuFlags], 2; fuFlags
0x1800099a1  mov     rcx, rsi; hWnd
0x1800099a4  call    cs:__imp_SendMessageTimeoutW
0x1800099aa  test    rax, rax
0x1800099ad  jz      loc_180009EC3
0x1800099b3  test    ebx, ebx
0x1800099b5  js      loc_18000A25F
0x1800099bb  mov     rax, [rsp+310h+dwResult]
0x1800099c0  cmp     rax, 10000h
0x1800099c6  jnb     loc_180009F95
0x1800099cc  xor     ebx, ebx
0x1800099ce  mov     [rdi], rbx
0x1800099d1  mov     ebx, 80004005h
0x1800099d6  jmp     short loc_1800099FD
0x1800099d8  mov     rcx, rsi; hWnd
0x1800099db  call    cs:__imp_IsWindow
0x1800099e1  test    eax, eax
0x1800099e3  jz      short loc_1800099D1
0x1800099e5  mov     r9, r13; struct _GUID *
0x1800099e8  mov     qword ptr [rsp+310h+fuFlags], rdi; void **
0x1800099ed  xor     r8d, r8d; int
0x1800099f0  mov     edx, r12d; int
0x1800099f3  mov     rcx, rsi; HWND
0x1800099f6  call    ?CreateMenuBar@@YAJPEAUHWND__@@HJAEBU_GUID@@PEAPEAX@Z; CreateMenuBar(HWND__ *,int,long,_GUID const &,void * *)
0x1800099fb  mov     ebx, eax
0x1800099fd  mov     eax, ebx
0x1800099ff  mov     r15, [rsp+310h+var_38]
0x180009a07  mov     r12, [rsp+310h+var_30]
0x180009a0f  mov     rbx, [rsp+2E8h]
0x180009a17  movaps  xmm6, [rsp+310h+var_58+8]
0x180009a1f  mov     rcx, [rbp+210h+var_60]
0x180009a26  xor     rcx, rsp; StackCookie
0x180009a29  call    __security_check_cookie
0x180009a2e  add     rsp, 2F0h
0x180009a35  pop     r14
0x180009a37  pop     r13
0x180009a39  pop     rdi
0x180009a3a  pop     rsi
0x180009a3b  pop     rbp
0x180009a3c  retn
0x180009a3d  lfence
0x180009a40  mov     r14d, ds:rva dword_180054260[r15+rdx*4]
0x180009a48  cmp     r14d, 0FFFFFFFFh
0x180009a4c  jnz     short loc_180009AAE
0x180009a4e  lea     rax, [rsp+310h+dwResult]
0x180009a53  mov     [rsp+310h+dwResult], 0
0x180009a5c  mov     [rsp+30h], rax; lpdwResult
0x180009a61  mov     r9, 0FFFFFFFFFFFFFFF4h; lParam
0x180009a68  mov     [rsp+310h+uTimeout], 4E20h; uTimeout
0x180009a70  xor     r8d, r8d; wParam
0x180009a73  mov     edx, 3Dh ; '='; Msg
0x180009a78  mov     [rsp+310h+fuFlags], 2; fuFlags
0x180009a80  mov     rcx, rsi; hWnd
0x180009a83  call    cs:__imp_SendMessageTimeoutW
0x180009a89  test    rax, rax
0x180009a8c  jz      loc_180009F13
0x180009a92  test    ebx, ebx
0x180009a94  js      loc_18000A28A
0x180009a9a  mov     rax, [rsp+310h+dwResult]
0x180009a9f  cmp     rax, 10000h
0x180009aa5  jnb     loc_18000A1B0
0x180009aab  mov     r14d, r12d
0x180009aae  movsxd  rax, r14d
0x180009ab1  lea     rcx, [rax+rax*4]
0x180009ab5  lea     rbx, ds:0[rcx*8]
0x180009abd  cmp     dword ptr [rbx+r15+4A398h], 0
0x180009ac6  jz      loc_180009DA2
0x180009acc  mov     rax, [rbx+r15+4A390h]
0x180009ad4  mov     r9, rdi
0x180009ad7  mov     r8, r13
0x180009ada  xor     edx, edx
0x180009adc  mov     rcx, rsi
0x180009adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ae4  jmp     loc_1800099FB
0x180009ae9  mov     rcx, rsi; jumptable 0000000180009872 case 0
0x180009aec  mov     [rdi], rbx
0x180009aef  call    cs:__imp_IsWindow
0x180009af5  test    eax, eax
0x180009af7  jz      loc_1800099D1
0x180009afd  mov     rax, cs:?lpfnRealGetWindowClass@@3P6AIPEAUHWND__@@PEAGI@ZEA; uint (*lpfnRealGetWindowClass)(HWND__ *,ushort *,uint)
0x180009b04  lea     rdx, [rbp+210h+String]; lpClassName
0x180009b08  mov     [rbp+210h+String], bx
0x180009b0c  mov     r8d, 80h; nMaxCount
0x180009b12  mov     rcx, rsi; hWnd
0x180009b15  test    rax, rax
0x180009b18  jz      loc_18000A4FA
0x180009b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b23  test    eax, eax
0x180009b25  jz      loc_180009BC5
0x180009b2b  lea     rcx, [rbp+210h+String]; lpString
0x180009b2f  mov     r14d, ebx
0x180009b32  call    cs:__imp_GlobalFindAtomW
0x180009b38  test    ax, ax
0x180009b3b  jz      short loc_180009B68
0x180009b3d  mov     ecx, ebx
0x180009b3f  nop
0x180009b40  cmp     ecx, 2
0x180009b43  jge     short loc_180009B68
0x180009b45  movsxd  rdx, ecx
0x180009b48  cmp     rva ?rgAtomClasses@@3PAGA[r15+rdx*2], ax; ushort near * rgAtomClasses ...
0x180009b51  jz      short loc_180009B57
0x180009b53  inc     ecx
0x180009b55  jmp     short loc_180009B40
0x180009b57  lfence
0x180009b5a  mov     r14d, dword ptr ds:rva ?g_WindowClassMap@@3PAW4CLASS_ENUM@@A[r15+rdx*4]; "#" ...
0x180009b62  cmp     r14d, 0FFFFFFFFh
0x180009b66  jnz     short loc_180009BCB
0x180009b68  lea     rax, [rsp+310h+dwResult]
0x180009b6d  mov     [rsp+310h+dwResult], 0
0x180009b76  mov     [rsp+30h], rax; lpdwResult
0x180009b7b  mov     r9, 0FFFFFFFFFFFFFFF4h; lParam
0x180009b82  mov     [rsp+310h+uTimeout], 4E20h; uTimeout
0x180009b8a  xor     r8d, r8d; wParam
0x180009b8d  mov     edx, 3Dh ; '='; Msg
0x180009b92  mov     [rsp+310h+fuFlags], 2; fuFlags
0x180009b9a  mov     rcx, rsi; hWnd
0x180009b9d  call    cs:__imp_SendMessageTimeoutW
0x180009ba3  test    rax, rax
0x180009ba6  jz      loc_180009F54
0x180009bac  test    ebx, ebx
0x180009bae  js      loc_18000A2AB
0x180009bb4  mov     rax, [rsp+310h+dwResult]
0x180009bb9  cmp     rax, 10000h
0x180009bbf  jnb     loc_18000A206
0x180009bc5  mov     r14d, 8
0x180009bcb  movsxd  rax, r14d
0x180009bce  lea     rcx, [rax+rax*4]
0x180009bd2  lea     rbx, ds:0[rcx*8]
0x180009bda  cmp     dword ptr [rbx+r15+4A398h], 0
0x180009be3  jnz     loc_180009ACC
0x180009be9  lea     rdx, [rsp+310h+dwProcessId]; int *
0x180009bee  mov     [rsp+310h+dwProcessId], 0
0x180009bf6  mov     rcx, rsi; HWND
0x180009bf9  call    ?SameBitness@@YAJPEAUHWND__@@PEAH@Z; SameBitness(HWND__ *,int *)
0x180009bfe  test    eax, eax
0x180009c00  js      loc_1800099D1
0x180009c06  cmp     [rsp+310h+dwProcessId], 0
0x180009c0b  jnz     loc_180009ACC
0x180009c11  mov     r9, rdi; void **
0x180009c14  mov     r8, r13; struct _GUID *
0x180009c17  xor     edx, edx; int
0x180009c19  mov     rcx, rsi; HWND
0x180009c1c  call    ?CreateRemoteProxy6432@@YAJPEAUHWND__@@JAEBU_GUID@@PEAPEAX@Z; CreateRemoteProxy6432(HWND__ *,long,_GUID const &,void * *)
0x180009c21  jmp     loc_1800099FB
0x180009c26  mov     edx, 88h; jumptable 0000000180009872 cases -6,-5
0x180009c2b  mov     [rdi], rbx
0x180009c2e  mov     ecx, 40h ; '@'; uFlags
0x180009c33  call    cs:__imp_LocalAlloc
0x180009c39  test    rax, rax
0x180009c3c  jz      loc_180009CD7
0x180009c42  mov     rcx, rax; this
0x180009c45  call    ??0CScrollBar@@QEAA@XZ; CScrollBar::CScrollBar(void)
0x180009c4a  mov     r15, rax
0x180009c4d  test    rax, rax
0x180009c50  jz      loc_180009CD7
0x180009c56  mov     rcx, rsi; hWnd
0x180009c59  call    cs:__imp_IsWindow
0x180009c5f  test    eax, eax
0x180009c61  jz      loc_18000A505
0x180009c67  mov     eax, ebx
0x180009c69  mov     [r15+50h], rsi
0x180009c6d  cmp     r14d, 0FFFFFFFBh
0x180009c71  mov     qword ptr [r15+5Ch], 5
0x180009c79  mov     r8, rdi
0x180009c7c  mov     rdx, r13
0x180009c7f  setz    al
0x180009c82  mov     rcx, r15
0x180009c85  mov     [r15+80h], eax
0x180009c8c  mov     rax, [r15]
0x180009c8f  mov     rax, [rax]
0x180009c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c97  mov     ebx, eax
0x180009c99  test    eax, eax
0x180009c9b  jns     loc_1800099FD
0x180009ca1  mov     rax, [r15]
0x180009ca4  mov     edx, r12d
0x180009ca7  mov     rcx, r15
0x180009caa  mov     rax, [rax+0E0h]
0x180009cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cb6  jmp     loc_1800099FD
0x180009cbb  mov     edx, 78h ; 'x'; jumptable 0000000180009872 case -2
0x180009cc0  mov     [rdi], rbx
0x180009cc3  mov     ecx, 40h ; '@'; uFlags
0x180009cc8  call    cs:__imp_LocalAlloc
0x180009cce  test    rax, rax
0x180009cd1  jnz     loc_18000A059
0x180009cd7  mov     ebx, 8007000Eh
0x180009cdc  jmp     loc_1800099FD
0x180009ce1  mov     eax, cs:dword_180061968
0x180009ce7  test    eax, eax
0x180009ce9  jz      loc_18000A386
0x180009cef  cmp     eax, r12d
0x180009cf2  jz      loc_180009D93
0x180009cf8  lea     rdx, [rsp+310h+dwProcessId]; lpdwProcessId
0x180009cfd  mov     [rsp+310h+dwProcessId], ebx
0x180009d01  call    cs:__imp_GetWindowThreadProcessId
0x180009d07  test    eax, eax
  ... truncated ...
```

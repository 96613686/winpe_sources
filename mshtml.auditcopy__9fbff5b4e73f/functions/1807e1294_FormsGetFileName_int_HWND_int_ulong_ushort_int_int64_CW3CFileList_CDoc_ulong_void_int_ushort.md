# FormsGetFileName(int,HWND__ *,int,ulong,ushort *,int,__int64,CW3CFileList *,CDoc *,ulong *,void * *,int,ushort *)

- ea: `0x1807e1294`
- end: `0x1807e1b9e`
- name: `?FormsGetFileName@@YAJHPEAUHWND__@@HKPEAGH_JPEAVCW3CFileList@@PEAVCDoc@@PEAKPEAPEAXH1@Z`
- size: `2314`
- prototype: `__int64 __fastcall(int, HWND, UINT, unsigned int, unsigned __int16 *, int, LPARAM, struct CW3CFileList *, struct CDoc *, unsigned int *, void **, int, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1808cc020`
- `0x1808cc4d0`
- `0x180a62728`

## callees

- `0x18024bed4`
- `0x18040ac58`
- `0x18059fd60`
- `0x180745a1c`
- `0x1807e1294`
- `0x1807e1ba4`
- `0x180845718`
- `0x1808458a8`
- `0x180866aa4`
- `0x180b524cc`
- `0x180b66dfc`
- `0x18108bec4`
- `0x18108c1b0`
- `0x18108e8dc`
- `0x1810c6ad4`
- `0x1810c6bfc`
- `0x1810f6516`
- `0x1810f65c0`
- `0x181100f20`
- `0x181104010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1807e1a3b`
- `msvcrt!wcsrchr` at `0x1807e1a3b`
- `msvcrt!wcsstr` at `0x1807e1594`
- `msvcrt!wcsstr` at `0x1807e1594`
- `KERNEL32!GetTempPath2W` at `0x1807e1ae9`
- `KERNEL32!GetTempPath2W` at `0x1807e1ae9`
- `KERNEL32!GetTempFileNameW` at `0x1807e1b11`
- `KERNEL32!GetTempFileNameW` at `0x1807e1b11`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1807e1477`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1807e1477`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1807e133f`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1807e133f`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1807e13ad`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1807e13ad`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1807e1830`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1807e1830`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1807e17cf`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1807e1905`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1807e1926`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1807e193b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1807e194c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1807e17cf`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1807e1905`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1807e1926`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1807e193b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1807e194c`
- `COMDLG32!CommDlgExtendedError` at `0x1807e1a98`
- `COMDLG32!CommDlgExtendedError` at `0x1807e1a98`
- `COMDLG32!GetOpenFileNameW` at `0x1807e199d`
- `COMDLG32!GetOpenFileNameW` at `0x1807e199d`
- `COMDLG32!GetSaveFileNameW` at `0x1807e1973`
- `COMDLG32!GetSaveFileNameW` at `0x1807e1973`

## string_xrefs

- `0x1807e1b03`: `lrietemp`

## pseudocode

```c
__int64 __fastcall FormsGetFileName(
        int a1,
        HWND a2,
        UINT a3,
        unsigned int a4,
        unsigned __int16 *a5,
        int a6,
        LPARAM a7,
        struct CW3CFileList *a8,
        struct CDoc *a9,
        unsigned int *a10,
        void **a11,
        int a12,
        unsigned __int16 *a13)
{
  unsigned __int16 **v13; // r12
  int v15; // ebx
  int v16; // eax
  bool v17; // zf
  DWORD Flags; // eax
  unsigned __int16 *v19; // rdi
  void *v20; // rdx
  HINSTANCE MUIHInst; // rax
  int StringW; // eax
  __int64 v23; // r12
  void *lpstrTitle; // r8
  WCHAR *v25; // rcx
  WCHAR v26; // dx
  WCHAR v27; // ax
  int v28; // eax
  WCHAR v29; // ax
  WCHAR *v30; // rcx
  const wchar_t *lpstrFilter; // rbx
  int v32; // esi
  __int64 v33; // rax
  unsigned __int16 *v34; // rbx
  unsigned __int16 *v35; // r11
  unsigned __int16 *v36; // rdi
  _WORD *v37; // rsi
  bool IsEdpFileAccessPolicyEnforced; // si
  const struct IE80TabWindowExports *v39; // rax
  int v40; // r14d
  int v41; // edi
  __int64 v42; // rax
  WCHAR *i; // rax
  __int64 v44; // rcx
  BOOL SaveFileNameW; // eax
  struct IEUserBroker **v46; // r15
  struct CW3CFileList *v47; // r14
  __int64 v48; // rax
  WCHAR *j; // rax
  __int64 v50; // rcx
  int v51; // eax
  LPVOID *v52; // rcx
  unsigned int v53; // r14d
  __int64 k; // rsi
  unsigned __int16 *v55; // r11
  wchar_t *v56; // rax
  signed int v57; // eax
  signed int LastWin32Error; // eax
  struct CDoc *v60; // [rsp+30h] [rbp-D8h]
  void **v61; // [rsp+50h] [rbp-B8h]
  __int64 v62; // [rsp+58h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-A8h] BYREF
  unsigned __int16 **v64; // [rsp+68h] [rbp-A0h]
  struct CW3CFileList *v65; // [rsp+70h] [rbp-98h]
  unsigned int *v66; // [rsp+78h] [rbp-90h]
  tagOFNW v67; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int64 v68; // [rsp+128h] [rbp+20h]
  HWND v69; // [rsp+130h] [rbp+28h]
  CDoc *v70; // [rsp+138h] [rbp+30h]
  unsigned __int16 v71[264]; // [rsp+148h] [rbp+40h] BYREF
  WCHAR PathName[264]; // [rsp+358h] [rbp+250h] BYREF
  WCHAR TempFileName[264]; // [rsp+568h] [rbp+460h] BYREF
  WCHAR Buffer[4096]; // [rsp+778h] [rbp+670h] BYREF

  v13 = (unsigned __int16 **)a11;
  v69 = a2;
  v65 = a8;
  v66 = a10;
  v70 = a9;
  v15 = 0;
  v64 = (unsigned __int16 **)a11;
  memset_0(&v67, 0, sizeof(v67));
  v16 = IsProtectedModeProcess();
  LODWORD(pv) = v16;
  if ( !a1 || v16 || (HIDWORD(v62) = 1, !a11) )
    HIDWORD(v62) = 0;
  v68 = a6;
  a5[a6 - 1] = 0;
  memset_0(&v67, 0, sizeof(v67));
  v67.nMaxFile = a6;
  v67.lpfnHook = 0;
  v67.lCustData = a7;
  v67.lStructSize = 152;
  v67.Flags = 530446;
  v67.lpstrFile = a5;
  v17 = !LCIEIsCurrentProcessInPrivate();
  Flags = v67.Flags;
  if ( !v17 )
  {
    Flags = v67.Flags | 0x2000000;
    v67.Flags |= 0x2000000u;
  }
  if ( a12 )
  {
    Flags |= 0x200u;
    v67.Flags = Flags;
  }
  if ( a1 && a7 )
  {
    v67.Flags = Flags | 0x60;
    v67.lpfnHook = (LPOFNHOOKPROC)SaveOFNHookProc;
    v67.lpTemplateName = L"IDD_ADDTOSAVE_DIALOG_MSHTML";
    v67.hInstance = GetMUIHInst();
  }
  v19 = a5;
  if ( *a5 )
  {
    do
      ++v19;
    while ( *v19 );
    if ( v19 < a5 )
      goto LABEL_18;
  }
  do
  {
    if ( *v19 == 46 )
      break;
    --v19;
  }
  while ( v19 >= a5 );
  if ( v19 < a5 )
  {
LABEL_18:
    v19 = 0;
LABEL_21:
    MUIHInst = GetMUIHInst();
    StringW = LoadStringW(MUIHInst, a3, Buffer, 4096);
    v23 = StringW;
    if ( !StringW )
      goto LABEL_44;
    lpstrTitle = Buffer;
    v67.lpstrTitle = Buffer;
    v25 = Buffer;
    do
    {
      v26 = *v25;
      if ( !*v25 )
        break;
      ++v25;
    }
    while ( v26 != 124 );
    if ( *v25 )
    {
      v67.nFilterIndex = v66 ? *v66 : 1;
      v67.lpstrDefExt = v25;
      do
      {
        v27 = *v25;
        if ( !*v25 )
          break;
        ++v25;
      }
      while ( v27 != 124 );
      if ( *v25 )
      {
        v67.lpstrFilter = v25;
        if ( a13 )
        {
          v28 = StringCchCatW(Buffer, 4096, a13);
          lpstrTitle = (void *)v67.lpstrTitle;
          v15 = v28;
        }
        v29 = Buffer[0];
        if ( Buffer[0] )
        {
          v30 = Buffer;
          do
          {
            if ( v29 == 124 )
              *v30 = 0;
            v29 = *++v30;
          }
          while ( *v30 );
        }
      }
    }
    if ( !lpstrTitle || !v67.lpstrDefExt || !v67.lpstrFilter || v15 < 0 )
    {
LABEL_44:
      v67.lpstrTitle = 0;
      v67.lpstrDefExt = 0;
      v67.lpstrFilter = 0;
      v67.nFilterIndex = 0;
    }
    if ( v19 )
    {
      lpstrFilter = v67.lpstrFilter;
      v32 = 0;
      while ( lpstrFilter )
      {
        if ( wcsstr(lpstrFilter, v19) )
        {
          *v19 = 0;
          v67.nFilterIndex = v32 / 2 + 1;
          v67.lpstrDefExt = v19 + 1;
          break;
        }
        v33 = -1;
        do
          ++v33;
        while ( lpstrFilter[v33] );
        lpstrFilter += v33 + 1;
        if ( !*lpstrFilter )
        {
          v67.lpstrDefExt = 0;
          break;
        }
        ++v32;
      }
    }
    StringCchCopyW(v71, 0x105u, a5);
    v34 = v71;
    for ( v71[260] = 0; *v34; ++v34 )
      ;
    v35 = v34;
    do
    {
      if ( *v35 == 92 )
        break;
      if ( *v35 == 58 )
        break;
      --v35;
    }
    while ( v35 >= v71 );
    if ( v35 < v71 )
    {
      CLockg_achSavePath::CLockg_achSavePath((CLockg_achSavePath *)&v62, 0);
      StringCchCopyW(v71, 0x105u, &g_achSavePath);
      CLockg_achSavePath::~CLockg_achSavePath((CLockg_achSavePath *)&v62);
      goto LABEL_75;
    }
    v36 = 0;
    if ( (char *)v35 - (char *)v71 < 0
      || (((char *)v35 - (char *)v71) & 0xFFFFFFFFFFFFFFFEuLL) == 0
      || (v36 = v35 - 1, *(v35 - 1) != 92) )
    {
      if ( v35 != v34 )
      {
        v37 = v35 + 1;
        StringCchCopyW(a5, v68, v35 + 1);
        goto LABEL_65;
      }
    }
    else
    {
      v35 = v34;
    }
    *a5 = 0;
    v37 = v35 + 1;
LABEL_65:
    if ( *v35 == 58 || v36 && *v36 == 58 )
    {
      if ( v35 != v34 )
        *v37 = 0;
    }
    else
    {
      *v35 = 0;
    }
LABEL_75:
    v67.lpstrInitialDir = (LPCWSTR)((unsigned __int64)v71 & -(__int64)(v71[0] != 0));
    IsEdpFileAccessPolicyEnforced = BrowserUtilEdp::IsEdpFileAccessPolicyEnforced((BrowserUtilEdp *)v67.lpstrInitialDir);
    v39 = IEProcessHelper::TabWindow();
    v15 = ((__int64 (__fastcall *)(_QWORD, HWND, HWND *))v39->WaitForTabWindow)(0, v69, &v67.hwndOwner);
    if ( v15 < 0 )
    {
      v15 = -2147024891;
LABEL_144:
      v13 = v64;
      goto LABEL_146;
    }
    v40 = HIDWORD(v62);
    v41 = 0;
    if ( HIDWORD(v62) )
    {
      pv = 0;
      v42 = -1;
      do
        ++v42;
      while ( v67.lpstrFilter[v42] );
      for ( i = (WCHAR *)&v67.lpstrFilter[v42]; i < &Buffer[v23] && i[1]; i += v44 )
      {
        *i = 124;
        v44 = -1;
        do
          ++v44;
        while ( i[v44] );
      }
      *i = 124;
      LODWORD(v60) = v67.nFilterIndex;
      v15 = IEFrameHelper::IEShowSaveFileDialog(
              (IEFrameHelper *)v67.hwndOwner,
              (HWND)v67.lpstrFile,
              v67.lpstrInitialDir,
              v67.lpstrFilter,
              v67.lpstrDefExt,
              (const unsigned __int16 *)v60,
              v67.Flags,
              (unsigned int)&pv,
              v64,
              v61);
      if ( pv )
        CoTaskMemFree(pv);
      SaveFileNameW = v15 == 0;
LABEL_113:
      if ( !SaveFileNameW )
      {
        if ( v40 )
        {
LABEL_138:
          if ( !v15 )
          {
            if ( (unsigned int)GetTempPath2W(260, PathName) && GetTempFileNameW(PathName, L"lrietemp", 0, TempFileName) )
            {
              v15 = StringCchCopyW(v67.lpstrFile, v67.nMaxFile, TempFileName);
            }
            else
            {
              LastWin32Error = GetLastWin32Error();
              v15 = LastWin32Error;
              if ( LastWin32Error > 0 )
                v15 = (unsigned __int16)LastWin32Error | 0x80070000;
            }
          }
          goto LABEL_144;
        }
        goto LABEL_131;
      }
LABEL_121:
      CLockg_achSavePath::CLockg_achSavePath((CLockg_achSavePath *)&v62, 1);
      v15 = StringCchCopyW(&g_achSavePath, 0x104u, v67.lpstrFile);
      if ( !v15 )
      {
        if ( v41 )
        {
          v15 = StringCchCatW(v55, 260, L"\\");
        }
        else
        {
          v56 = wcsrchr(v55, 0x5Cu);
          if ( v56 )
            v56[1] = 0;
          else
            g_achSavePath = 0;
        }
      }
      if ( v66 )
        *v66 = v67.nFilterIndex;
      CLockg_achSavePath::~CLockg_achSavePath((CLockg_achSavePath *)&v62);
      v40 = HIDWORD(v62);
LABEL_137:
      if ( !v40 )
        return (unsigned int)v15;
      goto LABEL_138;
    }
    v46 = (struct IEUserBroker **)v70;
    v47 = v65;
    if ( v70 && v65 )
    {
      if ( !a1 )
      {
        if ( !(_DWORD)pv
          && (unsigned int)IsABrowserApp()
          && !(unsigned __int8)IEConfiguration_GetBool(268435481)
          && IsOs_Win8OrGreater() )
        {
          v48 = -1;
          pv = 0;
          do
            ++v48;
          while ( v67.lpstrFilter[v48] );
          for ( j = (WCHAR *)&v67.lpstrFilter[v48]; ; j += v50 )
          {
            *j = 124;
            if ( !j[1] )
              break;
            v50 = -1;
            do
              ++v50;
            while ( j[v50] );
          }
          v15 = CDoc::ShowOpenFileDialog(v46, &v67, (struct _OPEN_FILE_RESULT **)&pv);
          if ( v15 >= 0 )
          {
            v51 = AppendToFileList(
                    *((unsigned __int16 **)pv + 2),
                    v47,
                    a12,
                    IsEdpFileAccessPolicyEnforced,
                    (unsigned int *)pv,
                    (struct CDoc *)v46,
                    *((struct _FILE_TOKEN **)pv + 1));
            v52 = (LPVOID *)pv;
            v15 = v51;
            if ( !v51 && *(_DWORD *)pv > 1u )
              v41 = 1;
            v53 = 0;
            for ( k = *((_QWORD *)pv + 1); v53 < *(_DWORD *)pv; ++v53 )
            {
              CoTaskMemFree(*(LPVOID *)(k + 8));
              v52 = (LPVOID *)pv;
              k += 16;
            }
            CoTaskMemFree(v52[1]);
            CoTaskMemFree(*((LPVOID *)pv + 2));
            CoTaskMemFree(pv);
          }
          SaveFileNameW = v15 >= 0;
          goto LABEL_112;
        }
LABEL_116:
        if ( GetOpenFileNameW(&v67) )
        {
          if ( !v47 )
            goto LABEL_121;
          LODWORD(pv) = 0;
          v15 = AppendToFileList(
                  v67.lpstrFile,
                  v47,
                  a12,
                  IsEdpFileAccessPolicyEnforced,
                  (unsigned int *)&pv,
                  (struct CDoc *)v46,
                  0);
          if ( v15 >= 0 )
          {
            if ( (unsigned int)pv > 1 )
              v41 = 1;
            goto LABEL_121;
          }
        }
        v40 = HIDWORD(v62);
LABEL_131:
        v57 = CommDlgExtendedError();
        if ( v57 )
        {
          if ( v57 > 0 )
            return (unsigned __int16)v57 | 0x80070000;
          else
            return (unsigned int)v57;
        }
        if ( v15 == -2147018894 )
          return (unsigned int)v15;
        v15 = 1;
        goto LABEL_137;
      }
    }
    else if ( !a1 )
    {
      goto LABEL_116;
    }
    SaveFileNameW = GetSaveFileNameW(&v67);
LABEL_112:
    v40 = HIDWORD(v62);
    goto LABEL_113;
  }
  if ( !a4 )
    goto LABEL_21;
  v15 = CheckPerceivedFileType(a5, v19, a4);
  if ( v15 >= 0 )
    goto LABEL_21;
LABEL_146:
  if ( HIDWORD(v62) && v15 && *v13 )
  {
    IEFrameHelper::IECancelSaveFile((IEFrameHelper *)*v13, v20);
    *v13 = 0;
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1807e1294  mov     rax, rsp
0x1807e1297  mov     [rax+20h], r9d
0x1807e129b  mov     [rax+18h], r8d
0x1807e129f  mov     [rax+10h], rdx
0x1807e12a3  mov     [rax+8], ecx
0x1807e12a6  push    rbp
0x1807e12a7  push    rbx
0x1807e12a8  push    rsi
0x1807e12a9  push    rdi
0x1807e12aa  push    r12
0x1807e12ac  push    r14
0x1807e12ae  push    r15
0x1807e12b0  lea     rbp, [rax-26B8h]
0x1807e12b7  mov     eax, 2780h
0x1807e12bc  call    _alloca_probe
0x1807e12c1  sub     rsp, rax
0x1807e12c4  mov     rax, cs:__security_cookie
0x1807e12cb  xor     rax, rsp
0x1807e12ce  mov     [rbp+26B0h+var_40], rax
0x1807e12d5  mov     rax, [rbp+26B0h+arg_8]
0x1807e12dc  xor     edx, edx; Val
0x1807e12de  mov     rcx, [rbp+26B0h+arg_40]
0x1807e12e5  mov     r8d, 98h; Size
0x1807e12eb  mov     r12, [rbp+26B0h+arg_50]
0x1807e12f2  movsxd  rdi, [rbp+26B0h+arg_28]
0x1807e12f9  mov     esi, [rbp+26B0h+uID]
0x1807e12ff  mov     r14, [rbp+26B0h+arg_20]
0x1807e1306  mov     r15, [rbp+26B0h+arg_60]
0x1807e130d  mov     [rbp+26B0h+var_2688], rax
0x1807e1311  mov     rax, [rbp+26B0h+arg_38]
0x1807e1318  mov     [rsp+27B0h+var_2748], rax
0x1807e131d  mov     rax, [rbp+26B0h+arg_48]
0x1807e1324  mov     [rsp+27B0h+var_2740], rax
0x1807e1329  xor     eax, eax
0x1807e132b  mov     [rbp+26B0h+var_2680], rcx
0x1807e132f  mov     ebx, eax
0x1807e1331  lea     rcx, [rbp+26B0h+var_2730]; void *
0x1807e1335  mov     [rsp+27B0h+var_2750], r12
0x1807e133a  call    memset_0
0x1807e133f  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x1807e1346  nop     dword ptr [rax+rax+00h]
0x1807e134b  xor     edx, edx; Val
0x1807e134d  mov     dword ptr [rsp+27B0h+pv], eax
0x1807e1351  cmp     [rbp+26B0h+arg_0], edx
0x1807e1357  jz      short loc_1807E136A
0x1807e1359  test    eax, eax
0x1807e135b  jnz     short loc_1807E136A
0x1807e135d  mov     dword ptr [rsp+27B0h+var_2760+4], 1
0x1807e1365  test    r12, r12
0x1807e1368  jnz     short loc_1807E136E
0x1807e136a  mov     dword ptr [rsp+27B0h+var_2760+4], edx
0x1807e136e  mov     r8d, 98h; Size
0x1807e1374  mov     [rbp+26B0h+var_2690], rdi
0x1807e1378  lea     rcx, [rbp+26B0h+var_2730]; void *
0x1807e137c  mov     [r14+rdi*2-2], dx
0x1807e1382  call    memset_0
0x1807e1387  mov     [rbp+26B0h+var_2730.nMaxFile], edi
0x1807e138a  xor     eax, eax
0x1807e138c  mov     rdi, [rbp+26B0h+arg_30]
0x1807e1393  mov     [rbp+26B0h+var_2730.lpfnHook], rax
0x1807e1397  mov     [rbp+26B0h+var_2730.lCustData], rdi
0x1807e139b  mov     [rbp+26B0h+var_2730.lStructSize], 98h
0x1807e13a2  mov     [rbp+26B0h+var_2730.Flags], 8180Eh
0x1807e13a9  mov     [rbp+26B0h+var_2730.lpstrFile], r14
0x1807e13ad  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x1807e13b4  nop     dword ptr [rax+rax+00h]
0x1807e13b9  xor     ecx, ecx
0x1807e13bb  test    al, al
0x1807e13bd  mov     eax, [rbp+26B0h+var_2730.Flags]
0x1807e13c0  jz      short loc_1807E13C9
0x1807e13c2  bts     eax, 19h
0x1807e13c6  mov     [rbp+26B0h+var_2730.Flags], eax
0x1807e13c9  cmp     [rbp+26B0h+arg_58], ecx
0x1807e13cf  jz      short loc_1807E13D8
0x1807e13d1  bts     eax, 9
0x1807e13d5  mov     [rbp+26B0h+var_2730.Flags], eax
0x1807e13d8  cmp     [rbp+26B0h+arg_0], ecx
0x1807e13de  jz      short loc_1807E140C
0x1807e13e0  test    rdi, rdi
0x1807e13e3  jz      short loc_1807E140C
0x1807e13e5  or      eax, 60h
0x1807e13e8  mov     [rbp+26B0h+var_2730.Flags], eax
0x1807e13eb  lea     rax, ?SaveOFNHookProc@@YA_KPEAUHWND__@@I_K_J@Z; SaveOFNHookProc(HWND__ *,uint,unsigned __int64,__int64)
0x1807e13f2  mov     [rbp+26B0h+var_2730.lpfnHook], rax
0x1807e13f6  lea     rax, aIddAddtosaveDi; "IDD_ADDTOSAVE_DIALOG_MSHTML"
0x1807e13fd  mov     [rbp+26B0h+var_2730.lpTemplateName], rax
0x1807e1401  call    ?GetMUIHInst@@YAPEAUHINSTANCE__@@XZ; GetMUIHInst(void)
0x1807e1406  mov     [rbp+26B0h+var_2730.hInstance], rax
0x1807e140a  xor     ecx, ecx
0x1807e140c  mov     rdi, r14
0x1807e140f  mov     eax, 2
0x1807e1414  cmp     [r14], cx
0x1807e1418  jz      short loc_1807E1427
0x1807e141a  add     rdi, rax
0x1807e141d  cmp     [rdi], cx
0x1807e1420  jnz     short loc_1807E141A
0x1807e1422  cmp     rdi, r14
0x1807e1425  jb      short loc_1807E143A
0x1807e1427  cmp     word ptr [rdi], 2Eh ; '.'
0x1807e142b  jz      short loc_1807E1435
0x1807e142d  sub     rdi, rax
0x1807e1430  cmp     rdi, r14
0x1807e1433  jnb     short loc_1807E1427
0x1807e1435  cmp     rdi, r14
0x1807e1438  jnb     short loc_1807E143F
0x1807e143a  mov     rdi, rcx
0x1807e143d  jmp     short loc_1807E1460
0x1807e143f  mov     r8d, [rbp+26B0h+arg_18]; unsigned int
0x1807e1446  test    r8d, r8d
0x1807e1449  jz      short loc_1807E1460
0x1807e144b  mov     rdx, rdi; unsigned __int16 *
0x1807e144e  mov     rcx, r14; unsigned __int16 *
0x1807e1451  call    ?CheckPerceivedFileType@@YAJPEBG0K@Z; CheckPerceivedFileType(ushort const *,ushort const *,ulong)
0x1807e1456  mov     ebx, eax
0x1807e1458  test    eax, eax
0x1807e145a  js      loc_1807E1B5A
0x1807e1460  call    ?GetMUIHInst@@YAPEAUHINSTANCE__@@XZ; GetMUIHInst(void)
0x1807e1465  mov     rcx, rax; hInstance
0x1807e1468  lea     r8, [rbp+26B0h+Buffer]; lpBuffer
0x1807e146f  mov     r9d, 1000h; cchBufferMax
0x1807e1475  mov     edx, esi; uID
0x1807e1477  call    cs:__imp_LoadStringW
0x1807e147e  nop     dword ptr [rax+rax+00h]
0x1807e1483  xor     r9d, r9d
0x1807e1486  movsxd  r12, eax
0x1807e1489  mov     r10d, 7Ch ; '|'
0x1807e148f  test    eax, eax
0x1807e1491  jz      loc_1807E156A
0x1807e1497  lea     r8, [rbp+26B0h+Buffer]
0x1807e149e  mov     [rbp+26B0h+var_2730.lpstrTitle], r8
0x1807e14a2  lea     rcx, [rbp+26B0h+Buffer]
0x1807e14a9  movzx   edx, word ptr [rcx]
0x1807e14ac  test    dx, dx
0x1807e14af  jz      short loc_1807E14BB
0x1807e14b1  add     rcx, 2
0x1807e14b5  cmp     dx, r10w
0x1807e14b9  jnz     short loc_1807E14A9
0x1807e14bb  cmp     [rcx], r9w
0x1807e14bf  jz      loc_1807E1550
0x1807e14c5  mov     rax, [rsp+27B0h+var_2740]
0x1807e14ca  test    rax, rax
0x1807e14cd  jz      short loc_1807E14D6
0x1807e14cf  mov     eax, [rax]
0x1807e14d1  mov     [rbp+26B0h+var_2730.nFilterIndex], eax
0x1807e14d4  jmp     short loc_1807E14DD
0x1807e14d6  mov     [rbp+26B0h+var_2730.nFilterIndex], 1
0x1807e14dd  mov     [rbp+26B0h+var_2730.lpstrDefExt], rcx
0x1807e14e1  movzx   eax, word ptr [rcx]
0x1807e14e4  test    ax, ax
0x1807e14e7  jz      short loc_1807E14F3
0x1807e14e9  add     rcx, 2
0x1807e14ed  cmp     ax, r10w
0x1807e14f1  jnz     short loc_1807E14E1
0x1807e14f3  cmp     [rcx], r9w
0x1807e14f7  jz      short loc_1807E1550
0x1807e14f9  mov     [rbp+26B0h+var_2730.lpstrFilter], rcx
0x1807e14fd  test    r15, r15
0x1807e1500  jz      short loc_1807E1522
0x1807e1502  mov     r8, r15; unsigned __int16 *
0x1807e1505  lea     rcx, [rbp+26B0h+Buffer]; unsigned __int16 *
0x1807e150c  mov     edx, 1000h; unsigned __int64
0x1807e1511  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1807e1516  mov     r8, [rbp+26B0h+var_2730.lpstrTitle]
0x1807e151a  mov     ebx, eax
0x1807e151c  mov     r10d, 7Ch ; '|'
0x1807e1522  movzx   eax, [rbp+26B0h+Buffer]
0x1807e1529  xor     r15d, r15d
0x1807e152c  test    ax, ax
0x1807e152f  jz      short loc_1807E1553
0x1807e1531  lea     rcx, [rbp+26B0h+Buffer]
0x1807e1538  cmp     ax, r10w
0x1807e153c  jnz     short loc_1807E1542
0x1807e153e  mov     [rcx], r15w
0x1807e1542  add     rcx, 2
0x1807e1546  movzx   eax, word ptr [rcx]
0x1807e1549  test    ax, ax
0x1807e154c  jnz     short loc_1807E1538
0x1807e154e  jmp     short loc_1807E1553
0x1807e1550  xor     r15d, r15d
0x1807e1553  test    r8, r8
0x1807e1556  jz      short loc_1807E156D
0x1807e1558  cmp     [rbp+26B0h+var_2730.lpstrDefExt], r15
0x1807e155c  jz      short loc_1807E156D
0x1807e155e  cmp     [rbp+26B0h+var_2730.lpstrFilter], r15
0x1807e1562  jz      short loc_1807E156D
0x1807e1564  test    ebx, ebx
0x1807e1566  jns     short loc_1807E157D
0x1807e1568  jmp     short loc_1807E156D
0x1807e156a  xor     r15d, r15d
0x1807e156d  mov     [rbp+26B0h+var_2730.lpstrTitle], r15
0x1807e1571  mov     [rbp+26B0h+var_2730.lpstrDefExt], r15
0x1807e1575  mov     [rbp+26B0h+var_2730.lpstrFilter], r15
0x1807e1579  mov     [rbp+26B0h+var_2730.nFilterIndex], r15d
0x1807e157d  test    rdi, rdi
0x1807e1580  jz      short loc_1807E15CD
0x1807e1582  mov     rbx, [rbp+26B0h+var_2730.lpstrFilter]
0x1807e1586  mov     esi, r15d
0x1807e1589  test    rbx, rbx
0x1807e158c  jz      short loc_1807E15CD
0x1807e158e  mov     rdx, rdi; SubStr
0x1807e1591  mov     rcx, rbx; Str
0x1807e1594  call    cs:__imp_wcsstr
0x1807e159b  nop     dword ptr [rax+rax+00h]
0x1807e15a0  test    rax, rax
0x1807e15a3  jnz     loc_1807E1670
0x1807e15a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1807e15ad  inc     rax
0x1807e15b0  cmp     [rbx+rax*2], r15w
0x1807e15b5  jnz     short loc_1807E15AD
0x1807e15b7  lea     rbx, [rbx+rax*2]
0x1807e15bb  add     rbx, 2
0x1807e15bf  cmp     [rbx], r15w
0x1807e15c3  jz      short loc_1807E15C9
0x1807e15c5  inc     esi
0x1807e15c7  jmp     short loc_1807E1589
0x1807e15c9  mov     [rbp+26B0h+var_2730.lpstrDefExt], r15
0x1807e15cd  mov     esi, 2
0x1807e15d2  mov     edi, 105h
0x1807e15d7  lea     rcx, [rbp+26B0h+var_2670]; unsigned __int16 *
0x1807e15db  mov     edx, edi; unsigned __int64
0x1807e15dd  mov     r8, r14; unsigned __int16 *
0x1807e15e0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1807e15e5  lea     rbx, [rbp+26B0h+var_2670]
0x1807e15e9  mov     [rbp+26B0h+var_2468], r15w
0x1807e15f1  cmp     [rbp+26B0h+var_2670], r15w
0x1807e15f6  jz      short loc_1807E1601
0x1807e15f8  add     rbx, rsi
0x1807e15fb  cmp     [rbx], r15w
0x1807e15ff  jnz     short loc_1807E15F8
0x1807e1601  mov     r11, rbx
0x1807e1604  mov     edx, 5Ch ; '\'
0x1807e1609  cmp     [r11], dx
0x1807e160d  jz      short loc_1807E1622
0x1807e160f  cmp     word ptr [r11], 3Ah ; ':'
0x1807e1614  jz      short loc_1807E1622
0x1807e1616  sub     r11, rsi
0x1807e1619  lea     rax, [rbp+26B0h+var_2670]
0x1807e161d  cmp     r11, rax
0x1807e1620  jnb     short loc_1807E1609
0x1807e1622  lea     rax, [rbp+26B0h+var_2670]
0x1807e1626  cmp     r11, rax
0x1807e1629  jb      loc_1807E16B5
0x1807e162f  lea     rcx, [rbp+26B0h+var_2670]
0x1807e1633  mov     rax, r11
0x1807e1636  sub     rax, rcx
0x1807e1639  mov     rdi, r15
0x1807e163c  test    rax, 0FFFFFFFFFFFFFFFEh
0x1807e1642  jle     short loc_1807E1690
0x1807e1644  lea     rdi, [r11-2]
0x1807e1648  cmp     [rdi], dx
0x1807e164b  jnz     short loc_1807E1690
0x1807e164d  mov     r11, rbx
0x1807e1650  mov     [r14], r15w
0x1807e1654  lea     rsi, [r11+2]
0x1807e1658  cmp     word ptr [r11], 3Ah ; ':'
0x1807e165d  jz      short loc_1807E16AA
0x1807e165f  test    rdi, rdi
0x1807e1662  jz      short loc_1807E166A
0x1807e1664  cmp     word ptr [rdi], 3Ah ; ':'
0x1807e1668  jz      short loc_1807E16AA
0x1807e166a  mov     [r11], r15w
0x1807e166e  jmp     short loc_1807E16DE
0x1807e1670  mov     eax, esi
0x1807e1672  mov     [rdi], r15w
0x1807e1676  cdq
0x1807e1677  mov     esi, 2
0x1807e167c  idiv    esi
0x1807e167e  inc     eax
0x1807e1680  mov     [rbp+26B0h+var_2730.nFilterIndex], eax
0x1807e1683  lea     rax, [rdi+2]
0x1807e1687  mov     [rbp+26B0h+var_2730.lpstrDefExt], rax
0x1807e168b  jmp     loc_1807E15D2
0x1807e1690  cmp     r11, rbx
0x1807e1693  jz      short loc_1807E1650
0x1807e1695  mov     rdx, [rbp+26B0h+var_2690]; unsigned __int64
0x1807e1699  lea     rsi, [r11+2]
0x1807e169d  mov     r8, rsi; unsigned __int16 *
0x1807e16a0  mov     rcx, r14; unsigned __int16 *
0x1807e16a3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1807e16a8  jmp     short loc_1807E1658
0x1807e16aa  cmp     r11, rbx
0x1807e16ad  jz      short loc_1807E16DE
0x1807e16af  mov     [rsi], r15w
0x1807e16b3  jmp     short loc_1807E16DE
0x1807e16b5  xor     edx, edx; bool
0x1807e16b7  lea     rcx, [rsp+27B0h+var_2760]; this
0x1807e16bc  call    ??0CLockg_achSavePath@@QEAA@_N@Z; CLockg_achSavePath::CLockg_achSavePath(bool)
0x1807e16c1  lea     r8, ?g_achSavePath@@3PAGA; unsigned __int16 *
0x1807e16c8  mov     rdx, rdi; unsigned __int64
0x1807e16cb  lea     rcx, [rbp+26B0h+var_2670]; unsigned __int16 *
0x1807e16cf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1807e16d4  lea     rcx, [rsp+27B0h+var_2760]; this
0x1807e16d9  call    ??1CLockg_achSavePath@@QEAA@XZ; CLockg_achSavePath::~CLockg_achSavePath(void)
0x1807e16de  movzx   eax, [rbp+26B0h+var_2670]
0x1807e16e2  neg     ax
0x1807e16e5  lea     rax, [rbp+26B0h+var_2670]
0x1807e16e9  sbb     rcx, rcx
0x1807e16ec  and     rcx, rax; this
0x1807e16ef  mov     [rbp+26B0h+var_2730.lpstrInitialDir], rcx
0x1807e16f3  call    ?IsEdpFileAccessPolicyEnforced@BrowserUtilEdp@@YA_NXZ; BrowserUtilEdp::IsEdpFileAccessPolicyEnforced(void)
  ... truncated ...
```

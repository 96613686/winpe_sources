# FormsGetFileName(int,HWND__ *,int,ulong,ushort *,int,__int64,CW3CFileList *,CDoc *,ulong *,void * *,int,ushort *)

- ea: `0x1807d5cec`
- end: `0x1807d6595`
- name: `?FormsGetFileName@@YAJHPEAUHWND__@@HKPEAGH_JPEAVCW3CFileList@@PEAVCDoc@@PEAKPEAPEAXH1@Z`
- size: `2217`
- prototype: `__int64 __fastcall(int, HWND, int, unsigned int, unsigned __int16 *, int, __int64, struct CW3CFileList *, struct CDoc *, unsigned int *, void **, int, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1808c2d18`
- `0x1808c3188`
- `0x180a4e7b0`

## callees

- `0x180282eac`
- `0x1802e5024`
- `0x1805b9418`
- `0x18073d694`
- `0x1807d5cec`
- `0x1807d659c`
- `0x180842a70`
- `0x180842bc4`
- `0x180861980`
- `0x180b3a818`
- `0x180b4df48`
- `0x18105c078`
- `0x18105c304`
- `0x18105e80c`
- `0x181094584`
- `0x1810946a8`
- `0x1810c2cb6`
- `0x1810c2d60`
- `0x1810cd6c0`
- `0x1810d1010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1807d644b`
- `msvcrt!wcsrchr` at `0x1807d644b`
- `msvcrt!wcsstr` at `0x1807d5fda`
- `msvcrt!wcsstr` at `0x1807d5fda`
- `KERNEL32!GetTempPath2W` at `0x1807d64ed`
- `KERNEL32!GetTempPath2W` at `0x1807d64ed`
- `KERNEL32!GetTempFileNameW` at `0x1807d650f`
- `KERNEL32!GetTempFileNameW` at `0x1807d650f`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1807d5ec3`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1807d5ec3`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1807d5d97`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1807d5d97`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1807d5dff`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1807d5dff`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1807d626a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1807d626a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1807d620f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1807d6339`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1807d6354`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1807d6363`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1807d636e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1807d620f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1807d6339`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1807d6354`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1807d6363`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1807d636e`
- `COMDLG32!CommDlgExtendedError` at `0x1807d64a2`
- `COMDLG32!CommDlgExtendedError` at `0x1807d64a2`
- `COMDLG32!GetOpenFileNameW` at `0x1807d63b3`
- `COMDLG32!GetOpenFileNameW` at `0x1807d63b3`
- `COMDLG32!GetSaveFileNameW` at `0x1807d638f`
- `COMDLG32!GetSaveFileNameW` at `0x1807d638f`

## string_xrefs

- `0x1807d6501`: `lrietemp`

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
  signed int v15; // ebx
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
  unsigned __int64 v35; // r11
  _WORD *v36; // rdi
  _WORD *v37; // rsi
  bool IsEdpFileAccessPolicyEnforced; // si
  const struct IE80TabWindowExports *v39; // rax
  int v40; // r14d
  int v41; // edi
  __int64 v42; // rax
  WCHAR *i; // rax
  __int64 v44; // rcx
  BOOL SaveFileNameW; // eax
  CDoc *v46; // r15
  struct CW3CFileList *v47; // r14
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // r9
  __int64 v51; // rax
  WCHAR *j; // rax
  __int64 v53; // rcx
  signed int v54; // eax
  LPVOID *v55; // rcx
  unsigned int v56; // r14d
  __int64 k; // rsi
  unsigned __int16 *v58; // r11
  wchar_t *v59; // rax
  signed int v60; // eax
  int LastWin32Error; // eax
  struct CDoc *v63; // [rsp+30h] [rbp-D8h]
  void **v64; // [rsp+50h] [rbp-B8h]
  __int64 v65; // [rsp+58h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-A8h] BYREF
  unsigned __int16 **v67; // [rsp+68h] [rbp-A0h]
  struct CW3CFileList *v68; // [rsp+70h] [rbp-98h]
  unsigned int *v69; // [rsp+78h] [rbp-90h]
  tagOFNW v70; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int64 v71; // [rsp+128h] [rbp+20h]
  HWND v72; // [rsp+130h] [rbp+28h]
  CDoc *v73; // [rsp+138h] [rbp+30h]
  unsigned __int16 v74[264]; // [rsp+148h] [rbp+40h] BYREF
  WCHAR PathName[264]; // [rsp+358h] [rbp+250h] BYREF
  WCHAR TempFileName[264]; // [rsp+568h] [rbp+460h] BYREF
  WCHAR Buffer[4096]; // [rsp+778h] [rbp+670h] BYREF

  v13 = (unsigned __int16 **)a11;
  v72 = a2;
  v68 = a8;
  v69 = a10;
  v73 = a9;
  v15 = 0;
  v67 = (unsigned __int16 **)a11;
  memset_0(&v70, 0, sizeof(v70));
  v16 = IsProtectedModeProcess();
  LODWORD(pv) = v16;
  if ( !a1 || v16 || (HIDWORD(v65) = 1, !a11) )
    HIDWORD(v65) = 0;
  v71 = a6;
  a5[a6 - 1] = 0;
  memset_0(&v70, 0, sizeof(v70));
  v70.nMaxFile = a6;
  v70.lpfnHook = 0;
  v70.lCustData = a7;
  v70.lStructSize = 152;
  v70.Flags = 530446;
  v70.lpstrFile = a5;
  v17 = !LCIEIsCurrentProcessInPrivate();
  Flags = v70.Flags;
  if ( !v17 )
  {
    Flags = v70.Flags | 0x2000000;
    v70.Flags |= 0x2000000u;
  }
  if ( a12 )
  {
    Flags |= 0x200u;
    v70.Flags = Flags;
  }
  if ( a1 && a7 )
  {
    v70.Flags = Flags | 0x60;
    v70.lpfnHook = (LPOFNHOOKPROC)SaveOFNHookProc;
    v70.lpTemplateName = L"IDD_ADDTOSAVE_DIALOG_MSHTML";
    v70.hInstance = GetMUIHInst();
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
    v70.lpstrTitle = Buffer;
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
      v70.nFilterIndex = v69 ? *v69 : 1;
      v70.lpstrDefExt = v25;
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
        v70.lpstrFilter = v25;
        if ( a13 )
        {
          v28 = StringCchCatW(Buffer, 0x1000u, a13);
          lpstrTitle = (void *)v70.lpstrTitle;
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
    if ( !lpstrTitle || !v70.lpstrDefExt || !v70.lpstrFilter || v15 < 0 )
    {
LABEL_44:
      v70.lpstrTitle = 0;
      v70.lpstrDefExt = 0;
      v70.lpstrFilter = 0;
      v70.nFilterIndex = 0;
    }
    if ( v19 )
    {
      lpstrFilter = v70.lpstrFilter;
      v32 = 0;
      while ( lpstrFilter )
      {
        if ( wcsstr(lpstrFilter, v19) )
        {
          *v19 = 0;
          v70.nFilterIndex = v32 / 2 + 1;
          v70.lpstrDefExt = v19 + 1;
          break;
        }
        v33 = -1;
        do
          ++v33;
        while ( lpstrFilter[v33] );
        lpstrFilter += v33 + 1;
        if ( !*lpstrFilter )
        {
          v70.lpstrDefExt = 0;
          break;
        }
        ++v32;
      }
    }
    StringCchCopyW(v74, 0x105u, a5);
    v34 = v74;
    for ( v74[260] = 0; *v34; ++v34 )
      ;
    v35 = (unsigned __int64)v34;
    do
    {
      if ( *(_WORD *)v35 == 92 )
        break;
      if ( *(_WORD *)v35 == 58 )
        break;
      v35 -= 2LL;
    }
    while ( v35 >= (unsigned __int64)v74 );
    if ( v35 < (unsigned __int64)v74 )
    {
      CLockg_achSavePath::CLockg_achSavePath((CLockg_achSavePath *)&v65, 0);
      StringCchCopyW(v74, 0x105u, g_achSavePath);
      CLockg_achSavePath::~CLockg_achSavePath((CLockg_achSavePath *)&v65);
      goto LABEL_75;
    }
    v36 = 0;
    if ( (__int64)(v35 - (_QWORD)v74) < 0
      || ((v35 - (_QWORD)v74) & 0xFFFFFFFFFFFFFFFEuLL) == 0
      || (v36 = (_WORD *)(v35 - 2), *(_WORD *)(v35 - 2) != 92) )
    {
      if ( (unsigned __int16 *)v35 != v34 )
      {
        v37 = (_WORD *)(v35 + 2);
        StringCchCopyW(a5, v71, (const unsigned __int16 *)(v35 + 2));
        goto LABEL_65;
      }
    }
    else
    {
      v35 = (unsigned __int64)v34;
    }
    *a5 = 0;
    v37 = (_WORD *)(v35 + 2);
LABEL_65:
    if ( *(_WORD *)v35 == 58 || v36 && *v36 == 58 )
    {
      if ( (unsigned __int16 *)v35 != v34 )
        *v37 = 0;
    }
    else
    {
      *(_WORD *)v35 = 0;
    }
LABEL_75:
    v70.lpstrInitialDir = (LPCWSTR)((unsigned __int64)v74 & -(__int64)(v74[0] != 0));
    IsEdpFileAccessPolicyEnforced = BrowserUtilEdp::IsEdpFileAccessPolicyEnforced((BrowserUtilEdp *)v70.lpstrInitialDir);
    v39 = IEProcessHelper::TabWindow();
    v15 = ((__int64 (__fastcall *)(_QWORD, HWND, HWND *))v39->WaitForTabWindow)(0, v72, &v70.hwndOwner);
    if ( v15 < 0 )
    {
      v15 = -2147024891;
LABEL_144:
      v13 = v67;
      goto LABEL_146;
    }
    v40 = HIDWORD(v65);
    v41 = 0;
    if ( HIDWORD(v65) )
    {
      pv = 0;
      v42 = -1;
      do
        ++v42;
      while ( v70.lpstrFilter[v42] );
      for ( i = (WCHAR *)&v70.lpstrFilter[v42]; i < &Buffer[v23] && i[1]; i += v44 )
      {
        *i = 124;
        v44 = -1;
        do
          ++v44;
        while ( i[v44] );
      }
      *i = 124;
      LODWORD(v63) = v70.nFilterIndex;
      v15 = IEFrameHelper::IEShowSaveFileDialog(
              (IEFrameHelper *)v70.hwndOwner,
              (HWND)v70.lpstrFile,
              v70.lpstrInitialDir,
              v70.lpstrFilter,
              v70.lpstrDefExt,
              (const unsigned __int16 *)v63,
              v70.Flags,
              (unsigned int)&pv,
              v67,
              v64);
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
              v15 = StringCchCopyW(v70.lpstrFile, v70.nMaxFile, TempFileName);
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
      CLockg_achSavePath::CLockg_achSavePath((CLockg_achSavePath *)&v65, 1);
      v15 = StringCchCopyW(g_achSavePath, 0x104u, v70.lpstrFile);
      if ( !v15 )
      {
        if ( v41 )
        {
          v15 = StringCchCatW(v58, 0x104u, L"\\");
        }
        else
        {
          v59 = wcsrchr(v58, 0x5Cu);
          if ( v59 )
            v59[1] = 0;
          else
            g_achSavePath[0] = 0;
        }
      }
      if ( v69 )
        *v69 = v70.nFilterIndex;
      CLockg_achSavePath::~CLockg_achSavePath((CLockg_achSavePath *)&v65);
      v40 = HIDWORD(v65);
LABEL_137:
      if ( !v40 )
        return (unsigned int)v15;
      goto LABEL_138;
    }
    v46 = v73;
    v47 = v68;
    if ( v73 && v68 )
    {
      if ( !a1 )
      {
        if ( !(_DWORD)pv
          && (unsigned int)IsABrowserApp()
          && !(unsigned __int8)IEConfiguration_GetBool(268435481, v48, v49, v50)
          && IsOs_Win8OrGreater() )
        {
          v51 = -1;
          pv = 0;
          do
            ++v51;
          while ( v70.lpstrFilter[v51] );
          for ( j = (WCHAR *)&v70.lpstrFilter[v51]; ; j += v53 )
          {
            *j = 124;
            if ( !j[1] )
              break;
            v53 = -1;
            do
              ++v53;
            while ( j[v53] );
          }
          v15 = CDoc::ShowOpenFileDialog(v46, &v70, (struct _OPEN_FILE_RESULT **)&pv);
          if ( v15 >= 0 )
          {
            v54 = AppendToFileList(
                    *((unsigned __int16 **)pv + 2),
                    v47,
                    a12,
                    IsEdpFileAccessPolicyEnforced,
                    (unsigned int *)pv,
                    v46,
                    *((struct _FILE_TOKEN **)pv + 1));
            v55 = (LPVOID *)pv;
            v15 = v54;
            if ( !v54 && *(_DWORD *)pv > 1u )
              v41 = 1;
            v56 = 0;
            for ( k = *((_QWORD *)pv + 1); v56 < *(_DWORD *)pv; ++v56 )
            {
              CoTaskMemFree(*(LPVOID *)(k + 8));
              v55 = (LPVOID *)pv;
              k += 16;
            }
            CoTaskMemFree(v55[1]);
            CoTaskMemFree(*((LPVOID *)pv + 2));
            CoTaskMemFree(pv);
          }
          SaveFileNameW = v15 >= 0;
          goto LABEL_112;
        }
LABEL_116:
        if ( GetOpenFileNameW(&v70) )
        {
          if ( !v47 )
            goto LABEL_121;
          LODWORD(pv) = 0;
          v15 = AppendToFileList(v70.lpstrFile, v47, a12, IsEdpFileAccessPolicyEnforced, (unsigned int *)&pv, v46, 0);
          if ( v15 >= 0 )
          {
            if ( (unsigned int)pv > 1 )
              v41 = 1;
            goto LABEL_121;
          }
        }
        v40 = HIDWORD(v65);
LABEL_131:
        v60 = CommDlgExtendedError();
        if ( v60 )
        {
          if ( v60 > 0 )
            return (unsigned __int16)v60 | 0x80070000;
          else
            return (unsigned int)v60;
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
    SaveFileNameW = GetSaveFileNameW(&v70);
LABEL_112:
    v40 = HIDWORD(v65);
    goto LABEL_113;
  }
  if ( !a4 )
    goto LABEL_21;
  v15 = CheckPerceivedFileType(a5, v19, a4);
  if ( v15 >= 0 )
    goto LABEL_21;
LABEL_146:
  if ( HIDWORD(v65) && v15 && *v13 )
  {
    IEFrameHelper::IECancelSaveFile((IEFrameHelper *)*v13, v20);
    *v13 = 0;
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1807d5cec  mov     rax, rsp
0x1807d5cef  mov     [rax+20h], r9d
0x1807d5cf3  mov     [rax+18h], r8d
0x1807d5cf7  mov     [rax+10h], rdx
0x1807d5cfb  mov     [rax+8], ecx
0x1807d5cfe  push    rbp
0x1807d5cff  push    rbx
0x1807d5d00  push    rsi
0x1807d5d01  push    rdi
0x1807d5d02  push    r12
0x1807d5d04  push    r14
0x1807d5d06  push    r15
0x1807d5d08  lea     rbp, [rax-26B8h]
0x1807d5d0f  mov     eax, 2780h
0x1807d5d14  call    _alloca_probe
0x1807d5d19  sub     rsp, rax
0x1807d5d1c  mov     rax, cs:__security_cookie
0x1807d5d23  xor     rax, rsp
0x1807d5d26  mov     [rbp+26B0h+var_40], rax
0x1807d5d2d  mov     rax, [rbp+26B0h+arg_8]
0x1807d5d34  xor     edx, edx; Val
0x1807d5d36  mov     rcx, [rbp+26B0h+arg_40]
0x1807d5d3d  mov     r8d, 98h; Size
0x1807d5d43  mov     r12, [rbp+26B0h+arg_50]
0x1807d5d4a  movsxd  rdi, [rbp+26B0h+arg_28]
0x1807d5d51  mov     esi, [rbp+26B0h+uID]
0x1807d5d57  mov     r14, [rbp+26B0h+arg_20]
0x1807d5d5e  mov     r15, [rbp+26B0h+arg_60]
0x1807d5d65  mov     [rbp+26B0h+var_2688], rax
0x1807d5d69  mov     rax, [rbp+26B0h+arg_38]
0x1807d5d70  mov     [rsp+27B0h+var_2748], rax
0x1807d5d75  mov     rax, [rbp+26B0h+arg_48]
0x1807d5d7c  mov     [rsp+27B0h+var_2740], rax
0x1807d5d81  xor     eax, eax
0x1807d5d83  mov     [rbp+26B0h+var_2680], rcx
0x1807d5d87  mov     ebx, eax
0x1807d5d89  lea     rcx, [rbp+26B0h+var_2730]; void *
0x1807d5d8d  mov     [rsp+27B0h+var_2750], r12
0x1807d5d92  call    memset_0
0x1807d5d97  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x1807d5d9d  xor     edx, edx; Val
0x1807d5d9f  mov     dword ptr [rsp+27B0h+pv], eax
0x1807d5da3  cmp     [rbp+26B0h+arg_0], edx
0x1807d5da9  jz      short loc_1807D5DBC
0x1807d5dab  test    eax, eax
0x1807d5dad  jnz     short loc_1807D5DBC
0x1807d5daf  mov     dword ptr [rsp+27B0h+var_2760+4], 1
0x1807d5db7  test    r12, r12
0x1807d5dba  jnz     short loc_1807D5DC0
0x1807d5dbc  mov     dword ptr [rsp+27B0h+var_2760+4], edx
0x1807d5dc0  mov     r8d, 98h; Size
0x1807d5dc6  mov     [rbp+26B0h+var_2690], rdi
0x1807d5dca  lea     rcx, [rbp+26B0h+var_2730]; void *
0x1807d5dce  mov     [r14+rdi*2-2], dx
0x1807d5dd4  call    memset_0
0x1807d5dd9  mov     [rbp+26B0h+var_2730.nMaxFile], edi
0x1807d5ddc  xor     eax, eax
0x1807d5dde  mov     rdi, [rbp+26B0h+arg_30]
0x1807d5de5  mov     [rbp+26B0h+var_2730.lpfnHook], rax
0x1807d5de9  mov     [rbp+26B0h+var_2730.lCustData], rdi
0x1807d5ded  mov     [rbp+26B0h+var_2730.lStructSize], 98h
0x1807d5df4  mov     [rbp+26B0h+var_2730.Flags], 8180Eh
0x1807d5dfb  mov     [rbp+26B0h+var_2730.lpstrFile], r14
0x1807d5dff  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x1807d5e05  xor     ecx, ecx
0x1807d5e07  test    al, al
0x1807d5e09  mov     eax, [rbp+26B0h+var_2730.Flags]
0x1807d5e0c  jz      short loc_1807D5E15
0x1807d5e0e  bts     eax, 19h
0x1807d5e12  mov     [rbp+26B0h+var_2730.Flags], eax
0x1807d5e15  cmp     [rbp+26B0h+arg_58], ecx
0x1807d5e1b  jz      short loc_1807D5E24
0x1807d5e1d  bts     eax, 9
0x1807d5e21  mov     [rbp+26B0h+var_2730.Flags], eax
0x1807d5e24  cmp     [rbp+26B0h+arg_0], ecx
0x1807d5e2a  jz      short loc_1807D5E58
0x1807d5e2c  test    rdi, rdi
0x1807d5e2f  jz      short loc_1807D5E58
0x1807d5e31  or      eax, 60h
0x1807d5e34  mov     [rbp+26B0h+var_2730.Flags], eax
0x1807d5e37  lea     rax, ?SaveOFNHookProc@@YA_KPEAUHWND__@@I_K_J@Z; SaveOFNHookProc(HWND__ *,uint,unsigned __int64,__int64)
0x1807d5e3e  mov     [rbp+26B0h+var_2730.lpfnHook], rax
0x1807d5e42  lea     rax, aIddAddtosaveDi; "IDD_ADDTOSAVE_DIALOG_MSHTML"
0x1807d5e49  mov     [rbp+26B0h+var_2730.lpTemplateName], rax
0x1807d5e4d  call    ?GetMUIHInst@@YAPEAUHINSTANCE__@@XZ; GetMUIHInst(void)
0x1807d5e52  mov     [rbp+26B0h+var_2730.hInstance], rax
0x1807d5e56  xor     ecx, ecx
0x1807d5e58  mov     rdi, r14
0x1807d5e5b  mov     eax, 2
0x1807d5e60  cmp     [r14], cx
0x1807d5e64  jz      short loc_1807D5E73
0x1807d5e66  add     rdi, rax
0x1807d5e69  cmp     [rdi], cx
0x1807d5e6c  jnz     short loc_1807D5E66
0x1807d5e6e  cmp     rdi, r14
0x1807d5e71  jb      short loc_1807D5E86
0x1807d5e73  cmp     word ptr [rdi], 2Eh ; '.'
0x1807d5e77  jz      short loc_1807D5E81
0x1807d5e79  sub     rdi, rax
0x1807d5e7c  cmp     rdi, r14
0x1807d5e7f  jnb     short loc_1807D5E73
0x1807d5e81  cmp     rdi, r14
0x1807d5e84  jnb     short loc_1807D5E8B
0x1807d5e86  mov     rdi, rcx
0x1807d5e89  jmp     short loc_1807D5EAC
0x1807d5e8b  mov     r8d, [rbp+26B0h+arg_18]; unsigned int
0x1807d5e92  test    r8d, r8d
0x1807d5e95  jz      short loc_1807D5EAC
0x1807d5e97  mov     rdx, rdi; unsigned __int16 *
0x1807d5e9a  mov     rcx, r14; unsigned __int16 *
0x1807d5e9d  call    ?CheckPerceivedFileType@@YAJPEBG0K@Z; CheckPerceivedFileType(ushort const *,ushort const *,ulong)
0x1807d5ea2  mov     ebx, eax
0x1807d5ea4  test    eax, eax
0x1807d5ea6  js      loc_1807D6552
0x1807d5eac  call    ?GetMUIHInst@@YAPEAUHINSTANCE__@@XZ; GetMUIHInst(void)
0x1807d5eb1  mov     rcx, rax; hInstance
0x1807d5eb4  lea     r8, [rbp+26B0h+Buffer]; lpBuffer
0x1807d5ebb  mov     r9d, 1000h; cchBufferMax
0x1807d5ec1  mov     edx, esi; uID
0x1807d5ec3  call    cs:__imp_LoadStringW
0x1807d5ec9  xor     r9d, r9d
0x1807d5ecc  movsxd  r12, eax
0x1807d5ecf  mov     r10d, 7Ch ; '|'
0x1807d5ed5  test    eax, eax
0x1807d5ed7  jz      loc_1807D5FB0
0x1807d5edd  lea     r8, [rbp+26B0h+Buffer]
0x1807d5ee4  mov     [rbp+26B0h+var_2730.lpstrTitle], r8
0x1807d5ee8  lea     rcx, [rbp+26B0h+Buffer]
0x1807d5eef  movzx   edx, word ptr [rcx]
0x1807d5ef2  test    dx, dx
0x1807d5ef5  jz      short loc_1807D5F01
0x1807d5ef7  add     rcx, 2
0x1807d5efb  cmp     dx, r10w
0x1807d5eff  jnz     short loc_1807D5EEF
0x1807d5f01  cmp     [rcx], r9w
0x1807d5f05  jz      loc_1807D5F96
0x1807d5f0b  mov     rax, [rsp+27B0h+var_2740]
0x1807d5f10  test    rax, rax
0x1807d5f13  jz      short loc_1807D5F1C
0x1807d5f15  mov     eax, [rax]
0x1807d5f17  mov     [rbp+26B0h+var_2730.nFilterIndex], eax
0x1807d5f1a  jmp     short loc_1807D5F23
0x1807d5f1c  mov     [rbp+26B0h+var_2730.nFilterIndex], 1
0x1807d5f23  mov     [rbp+26B0h+var_2730.lpstrDefExt], rcx
0x1807d5f27  movzx   eax, word ptr [rcx]
0x1807d5f2a  test    ax, ax
0x1807d5f2d  jz      short loc_1807D5F39
0x1807d5f2f  add     rcx, 2
0x1807d5f33  cmp     ax, r10w
0x1807d5f37  jnz     short loc_1807D5F27
0x1807d5f39  cmp     [rcx], r9w
0x1807d5f3d  jz      short loc_1807D5F96
0x1807d5f3f  mov     [rbp+26B0h+var_2730.lpstrFilter], rcx
0x1807d5f43  test    r15, r15
0x1807d5f46  jz      short loc_1807D5F68
0x1807d5f48  mov     r8, r15; unsigned __int16 *
0x1807d5f4b  lea     rcx, [rbp+26B0h+Buffer]; unsigned __int16 *
0x1807d5f52  mov     edx, 1000h; unsigned __int64
0x1807d5f57  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1807d5f5c  mov     r8, [rbp+26B0h+var_2730.lpstrTitle]
0x1807d5f60  mov     ebx, eax
0x1807d5f62  mov     r10d, 7Ch ; '|'
0x1807d5f68  movzx   eax, [rbp+26B0h+Buffer]
0x1807d5f6f  xor     r15d, r15d
0x1807d5f72  test    ax, ax
0x1807d5f75  jz      short loc_1807D5F99
0x1807d5f77  lea     rcx, [rbp+26B0h+Buffer]
0x1807d5f7e  cmp     ax, r10w
0x1807d5f82  jnz     short loc_1807D5F88
0x1807d5f84  mov     [rcx], r15w
0x1807d5f88  add     rcx, 2
0x1807d5f8c  movzx   eax, word ptr [rcx]
0x1807d5f8f  test    ax, ax
0x1807d5f92  jnz     short loc_1807D5F7E
0x1807d5f94  jmp     short loc_1807D5F99
0x1807d5f96  xor     r15d, r15d
0x1807d5f99  test    r8, r8
0x1807d5f9c  jz      short loc_1807D5FB3
0x1807d5f9e  cmp     [rbp+26B0h+var_2730.lpstrDefExt], r15
0x1807d5fa2  jz      short loc_1807D5FB3
0x1807d5fa4  cmp     [rbp+26B0h+var_2730.lpstrFilter], r15
0x1807d5fa8  jz      short loc_1807D5FB3
0x1807d5faa  test    ebx, ebx
0x1807d5fac  jns     short loc_1807D5FC3
0x1807d5fae  jmp     short loc_1807D5FB3
0x1807d5fb0  xor     r15d, r15d
0x1807d5fb3  mov     [rbp+26B0h+var_2730.lpstrTitle], r15
0x1807d5fb7  mov     [rbp+26B0h+var_2730.lpstrDefExt], r15
0x1807d5fbb  mov     [rbp+26B0h+var_2730.lpstrFilter], r15
0x1807d5fbf  mov     [rbp+26B0h+var_2730.nFilterIndex], r15d
0x1807d5fc3  test    rdi, rdi
0x1807d5fc6  jz      short loc_1807D600D
0x1807d5fc8  mov     rbx, [rbp+26B0h+var_2730.lpstrFilter]
0x1807d5fcc  mov     esi, r15d
0x1807d5fcf  test    rbx, rbx
0x1807d5fd2  jz      short loc_1807D600D
0x1807d5fd4  mov     rdx, rdi; SubStr
0x1807d5fd7  mov     rcx, rbx; Str
0x1807d5fda  call    cs:__imp_wcsstr
0x1807d5fe0  test    rax, rax
0x1807d5fe3  jnz     loc_1807D60B0
0x1807d5fe9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1807d5fed  inc     rax
0x1807d5ff0  cmp     [rbx+rax*2], r15w
0x1807d5ff5  jnz     short loc_1807D5FED
0x1807d5ff7  lea     rbx, [rbx+rax*2]
0x1807d5ffb  add     rbx, 2
0x1807d5fff  cmp     [rbx], r15w
0x1807d6003  jz      short loc_1807D6009
0x1807d6005  inc     esi
0x1807d6007  jmp     short loc_1807D5FCF
0x1807d6009  mov     [rbp+26B0h+var_2730.lpstrDefExt], r15
0x1807d600d  mov     esi, 2
0x1807d6012  mov     edi, 105h
0x1807d6017  lea     rcx, [rbp+26B0h+var_2670]; unsigned __int16 *
0x1807d601b  mov     edx, edi; unsigned __int64
0x1807d601d  mov     r8, r14; unsigned __int16 *
0x1807d6020  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1807d6025  lea     rbx, [rbp+26B0h+var_2670]
0x1807d6029  mov     [rbp+26B0h+var_2468], r15w
0x1807d6031  cmp     [rbp+26B0h+var_2670], r15w
0x1807d6036  jz      short loc_1807D6041
0x1807d6038  add     rbx, rsi
0x1807d603b  cmp     [rbx], r15w
0x1807d603f  jnz     short loc_1807D6038
0x1807d6041  mov     r11, rbx
0x1807d6044  mov     edx, 5Ch ; '\'
0x1807d6049  cmp     [r11], dx
0x1807d604d  jz      short loc_1807D6062
0x1807d604f  cmp     word ptr [r11], 3Ah ; ':'
0x1807d6054  jz      short loc_1807D6062
0x1807d6056  sub     r11, rsi
0x1807d6059  lea     rax, [rbp+26B0h+var_2670]
0x1807d605d  cmp     r11, rax
0x1807d6060  jnb     short loc_1807D6049
0x1807d6062  lea     rax, [rbp+26B0h+var_2670]
0x1807d6066  cmp     r11, rax
0x1807d6069  jb      loc_1807D60F5
0x1807d606f  lea     rcx, [rbp+26B0h+var_2670]
0x1807d6073  mov     rax, r11
0x1807d6076  sub     rax, rcx
0x1807d6079  mov     rdi, r15
0x1807d607c  test    rax, 0FFFFFFFFFFFFFFFEh
0x1807d6082  jle     short loc_1807D60D0
0x1807d6084  lea     rdi, [r11-2]
0x1807d6088  cmp     [rdi], dx
0x1807d608b  jnz     short loc_1807D60D0
0x1807d608d  mov     r11, rbx
0x1807d6090  mov     [r14], r15w
0x1807d6094  lea     rsi, [r11+2]
0x1807d6098  cmp     word ptr [r11], 3Ah ; ':'
0x1807d609d  jz      short loc_1807D60EA
0x1807d609f  test    rdi, rdi
0x1807d60a2  jz      short loc_1807D60AA
0x1807d60a4  cmp     word ptr [rdi], 3Ah ; ':'
0x1807d60a8  jz      short loc_1807D60EA
0x1807d60aa  mov     [r11], r15w
0x1807d60ae  jmp     short loc_1807D611E
0x1807d60b0  mov     eax, esi
0x1807d60b2  mov     [rdi], r15w
0x1807d60b6  cdq
0x1807d60b7  mov     esi, 2
0x1807d60bc  idiv    esi
0x1807d60be  inc     eax
0x1807d60c0  mov     [rbp+26B0h+var_2730.nFilterIndex], eax
0x1807d60c3  lea     rax, [rdi+2]
0x1807d60c7  mov     [rbp+26B0h+var_2730.lpstrDefExt], rax
0x1807d60cb  jmp     loc_1807D6012
0x1807d60d0  cmp     r11, rbx
0x1807d60d3  jz      short loc_1807D6090
0x1807d60d5  mov     rdx, [rbp+26B0h+var_2690]; unsigned __int64
0x1807d60d9  lea     rsi, [r11+2]
0x1807d60dd  mov     r8, rsi; unsigned __int16 *
0x1807d60e0  mov     rcx, r14; unsigned __int16 *
0x1807d60e3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1807d60e8  jmp     short loc_1807D6098
0x1807d60ea  cmp     r11, rbx
0x1807d60ed  jz      short loc_1807D611E
0x1807d60ef  mov     [rsi], r15w
0x1807d60f3  jmp     short loc_1807D611E
0x1807d60f5  xor     edx, edx; bool
0x1807d60f7  lea     rcx, [rsp+27B0h+var_2760]; this
0x1807d60fc  call    ??0CLockg_achSavePath@@QEAA@_N@Z; CLockg_achSavePath::CLockg_achSavePath(bool)
0x1807d6101  lea     r8, ?g_achSavePath@@3PAGA; unsigned __int16 *
0x1807d6108  mov     rdx, rdi; unsigned __int64
0x1807d610b  lea     rcx, [rbp+26B0h+var_2670]; unsigned __int16 *
0x1807d610f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1807d6114  lea     rcx, [rsp+27B0h+var_2760]; this
0x1807d6119  call    ??1CLockg_achSavePath@@QEAA@XZ; CLockg_achSavePath::~CLockg_achSavePath(void)
0x1807d611e  movzx   eax, [rbp+26B0h+var_2670]
0x1807d6122  neg     ax
0x1807d6125  lea     rax, [rbp+26B0h+var_2670]
0x1807d6129  sbb     rcx, rcx
0x1807d612c  and     rcx, rax; this
0x1807d612f  mov     [rbp+26B0h+var_2730.lpstrInitialDir], rcx
0x1807d6133  call    ?IsEdpFileAccessPolicyEnforced@BrowserUtilEdp@@YA_NXZ; BrowserUtilEdp::IsEdpFileAccessPolicyEnforced(void)
0x1807d6138  mov     sil, al
0x1807d613b  call    ?TabWindow@IEProcessHelper@@SAPEBUIE80TabWindowExports@@XZ; IEProcessHelper::TabWindow(void)
0x1807d6140  mov     rdx, [rbp+26B0h+var_2688]
0x1807d6144  lea     r8, [rbp+26B0h+var_2730.hwndOwner]
  ... truncated ...
```

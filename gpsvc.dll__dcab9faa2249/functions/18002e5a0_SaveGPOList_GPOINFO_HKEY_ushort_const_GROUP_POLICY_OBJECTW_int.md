# SaveGPOList(_GPOINFO *,HKEY__ *,ushort const *,_GROUP_POLICY_OBJECTW *,int)

- ea: `0x18002e5a0`
- end: `0x18002f6d2`
- name: `?SaveGPOList@@YAHPEAU_GPOINFO@@PEAUHKEY__@@PEBGPEAU_GROUP_POLICY_OBJECTW@@H@Z`
- size: `4402`
- prototype: `__int64 __fastcall(struct _GPOINFO *, HKEY, const unsigned __int16 *, BYTE *lpData, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002e088`
- `0x180075064`

## callees

- `0x180003770`
- `0x18000a504`
- `0x18001dcf0`
- `0x18001ef14`
- `0x18002e5a0`
- `0x18002f6e0`
- `0x180030bcc`
- `0x1800336a0`
- `0x180063ce4`
- `0x1800672b0`
- `0x180073984`
- `0x180073a5c`
- `0x180075ec0`
- `0x18007d320`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ea5e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eaf5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eb38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eb4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ec88`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ea5e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eaf5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eb38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eb4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ec88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e5f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e9b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ea30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ea8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002efba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f16c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f4e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e5f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e9b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ea30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ea8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002efba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f16c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f4e2`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18002ec22`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18002ec22`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002eae2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002eae2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e75c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e75c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e731`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f6c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e731`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f6c6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e6a0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e6d7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e70e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e7f9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e82d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e8a6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e905`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e96e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002eb1b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ed94`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002eebb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e6a0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e6d7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e70e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e7f9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e82d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e8a6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e905`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e96e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002eb1b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ed94`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002eebb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002e7c9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002e7c9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002ed4a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002ed4a`

## string_xrefs

- `0x18002ed88`: `DSPath`
- `0x18002e89a`: `FileSysPath`
- `0x18002e962`: `Extensions`
- `0x18002e6cb`: `GPOLink`
- `0x18002f660`: `SaveGPOList: Failed to create reg key with %d.`
- `0x18002f698`: `SaveGPOList: Failed to create reg key with %d.`
- `0x18002f507`: `SizeTToDWord() Failed to convert lpGPOList->lpFileSysPath length to DWORD`
- `0x18002f539`: `SizeTToDWord() Failed to convert lpGPOList->lpFileSysPath length to DWORD`
- `0x18002f0a0`: `SaveGPOList: Failed to get file active path.`
- `0x18002f0c7`: `SaveGPOList: Failed to get file active path.`
- `0x18002f03f`: `SaveGPOList: Failed to set file sys path reg value with %d.`
- `0x18002f06f`: `SaveGPOList: Failed to set file sys path reg value with %d.`
- `0x18002f494`: `SaveGPOList: Failed to set file sys path reg value with %d.`
- `0x18002f4cc`: `SaveGPOList: Failed to set file sys path reg value with %d.`
- `0x18002efdf`: `SizeTToDWord() Failed to convert xszLocalFilePath length to DWORD`
- `0x18002f011`: `SizeTToDWord() Failed to convert xszLocalFilePath length to DWORD`
- `0x18002f12c`: `SaveGPOList: Failed to set extension names reg value with %d.`
- `0x18002f159`: `SaveGPOList: Failed to set extension names reg value with %d.`
- `0x18002f2d7`: `SaveGPOList: Failed to set GPOLink reg value with %d.`
- `0x18002f30f`: `SaveGPOList: Failed to set GPOLink reg value with %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SaveGPOList(struct _GPOINFO *a1, HKEY a2, const unsigned __int16 *a3, BYTE *lpData, int a5)
{
  const unsigned __int16 *v6; // rbx
  HKEY v7; // rdi
  struct _GPOINFO *v8; // r15
  DWORD LastError; // esi
  void *v10; // rcx
  int v11; // eax
  int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  __int64 v16; // r15
  int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  const BYTE *v21; // rax
  const BYTE *v22; // rcx
  unsigned __int64 v23; // rax
  DWORD v24; // edx
  unsigned __int16 *v25; // rdi
  DWORD v26; // eax
  unsigned int v27; // eax
  const BYTE *v28; // rdx
  unsigned __int64 v29; // rcx
  int v30; // eax
  unsigned int v31; // eax
  const BYTE *v32; // rcx
  __int64 v33; // rax
  unsigned __int64 v34; // rax
  unsigned int v35; // eax
  __int64 v36; // r9
  BYTE *v37; // r14
  unsigned __int64 v38; // rcx
  void (*v39)(unsigned int, const unsigned __int16 *, ...); // rax
  __int64 v40; // rcx
  unsigned __int64 v41; // rcx
  unsigned int v42; // r14d
  DWORD v44; // ebx
  const WCHAR *v45; // rcx
  __int64 v46; // rax
  __int64 v47; // r9
  DWORD v48; // ecx
  unsigned int v49; // eax
  __int64 v50; // r14
  const BYTE *v51; // rcx
  __int64 v52; // rax
  unsigned __int64 v53; // rax
  unsigned int i; // ebx
  unsigned int v55; // r12d
  int *v56; // r8
  int v57; // ebx
  DWORD v58; // r14d
  int v59; // r15d
  unsigned int v60; // eax
  unsigned int v61; // eax
  unsigned __int64 v62; // rcx
  __int64 v63; // rcx
  const BYTE *v64; // r9
  unsigned int v65; // eax
  const unsigned __int16 *v66; // rdx
  BYTE *lpDataa; // [rsp+20h] [rbp-E0h]
  __int64 cbData; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v69; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v71; // [rsp+68h] [rbp-98h] BYREF
  int v72; // [rsp+6Ch] [rbp-94h]
  unsigned __int16 *v73; // [rsp+70h] [rbp-90h] BYREF
  const unsigned __int16 *v74; // [rsp+78h] [rbp-88h]
  DWORD dwDisposition; // [rsp+80h] [rbp-80h] BYREF
  struct _GPOINFO *v76; // [rsp+88h] [rbp-78h]
  HKEY v77; // [rsp+90h] [rbp-70h]
  int v78; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v79[96]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR SubKey[400]; // [rsp+100h] [rbp+0h] BYREF

  v6 = a3;
  v74 = a3;
  v7 = a2;
  v77 = a2;
  v8 = a1;
  v76 = a1;
  hKey = 0;
  dwDisposition = 0;
  LastError = GetLastError();
  if ( !v8 || !v7 || !v6 )
  {
    SetLastError(0x57u);
    return 0;
  }
  if ( GPRegDelnode(v7, v6) && *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"SaveGPOList: GPRegDelnode failed.");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"SaveGPOList: GPRegDelnode failed.");
    }
  }
  v10 = 0;
  if ( (*(_BYTE *)v8 & 1) == 0 )
    v10 = (void *)*((_QWORD *)v8 + 1);
  if ( !(unsigned int)MakeRegKeySecure(v10, v7, v6, 0, 0, 0) )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"SaveGpoList: Failed to secure reg key.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"SaveGpoList: Failed to secure reg key.");
      }
    }
    v57 = *((_DWORD *)v8 + 64);
    v58 = GetTickCount() - v57;
    v59 = *((_DWORD *)v8 + 70);
    for ( i = 0; i < 6; ++i )
    {
      if ( FindNLSString(
             0x7Fu,
             0x200001u,
             L"ds\\grouppolicy\\client\\gpsvc\\engine\\gpstate.cpp",
             -1,
             (LPCWSTR)*(&GPSourceFileNameIdTable + 2 * i),
             -1,
             0) != -1 )
      {
        v55 = *((_DWORD *)&GPSourceFileNameIdTable + 4 * i + 2);
        goto LABEL_88;
      }
    }
    v55 = -1;
LABEL_88:
    LODWORD(cbData) = v58;
    LODWORD(lpDataa) = v59;
    CGPAdminEventInitFailure::CGPAdminEventInitFailure(
      (CGPAdminEventInitFailure *)v79,
      (__int64)&gpEvent_INTERNAL_SYSTEM_ERROR,
      v55,
      753,
      (__int64)lpDataa,
      cbData,
      5u);
    CGPPolicyEventReporting::Report(*((CGPPolicyEventReporting **)v76 + 34), (struct CGPEventInfo *)v79, v56);
    CGPAdminEventInitFailure::~CGPAdminEventInitFailure((CGPAdminEventInitFailure *)v79);
    SetLastError(LastError);
    return 0;
  }
  v11 = 0;
  v72 = 0;
  while ( 1 )
  {
    if ( !lpData )
    {
      v42 = 1;
      goto LABEL_57;
    }
    LODWORD(lpDataa) = v11;
    v17 = StringCchPrintfW(SubKey, 0x190u, L"%ws\\%d", v6, lpDataa);
    if ( v17 < 0 )
    {
      LastError = (unsigned __int16)v17;
      goto LABEL_56;
    }
    v18 = RegCreateKeyExW(v7, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, &dwDisposition);
    if ( v18 )
    {
      LastError = v18;
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_56;
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"SaveGPOList: Failed to create reg key with %d.", v18);
        goto LABEL_56;
      }
      if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
        goto LABEL_56;
      RedirectDebugMsg(2u, L"SaveGPOList: Failed to create reg key with %d.", v18);
      v42 = 0;
      goto LABEL_57;
    }
    v19 = RegSetValueExW(hKey, L"Options", 0, 4u, lpData, 4u);
    if ( v19 )
    {
      LastError = v19;
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_56;
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"SaveGPOList: Failed to set options reg value with %d.", v19);
        goto LABEL_56;
      }
      if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
        goto LABEL_56;
      RedirectDebugMsg(2u, L"SaveGPOList: Failed to set options reg value with %d.", v19);
      v42 = 0;
      goto LABEL_57;
    }
    v20 = RegSetValueExW(hKey, L"Version", 0, 4u, lpData + 4, 4u);
    if ( v20 )
    {
      LastError = v20;
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_56;
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"SaveGPOList: Failed to set Version reg value with %d.", v20);
        goto LABEL_56;
      }
      if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
        goto LABEL_56;
      RedirectDebugMsg(2u, L"SaveGPOList: Failed to set Version reg value with %d.", v20);
      v42 = 0;
      goto LABEL_57;
    }
    v21 = (const BYTE *)*((_QWORD *)lpData + 1);
    if ( !v21 )
      goto LABEL_24;
    v40 = -1;
    do
      ++v40;
    while ( *(_WORD *)&v21[2 * v40] );
    v41 = 2 * v40 + 2;
    if ( v41 > 0xFFFFFFFF )
      break;
    v60 = RegSetValueExW(hKey, L"DSPath", 0, 1u, v21, v41);
    if ( v60 )
    {
      LastError = v60;
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_56;
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"SaveGPOList: Failed to set DS reg value with %d.", v60);
        goto LABEL_56;
      }
      if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
        goto LABEL_56;
      RedirectDebugMsg(2u, L"SaveGPOList: Failed to set DS reg value with %d.", v60);
      v42 = 0;
      goto LABEL_57;
    }
LABEL_24:
    v22 = (const BYTE *)*((_QWORD *)lpData + 2);
    v23 = -1;
    do
      ++v23;
    while ( *(_WORD *)&v22[2 * v23] );
    if ( v23 > 0xFFFFFFFF )
    {
      LastError = GetLastError();
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_56;
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"SizeTToDWord() Failed to convert lpGPOList->lpFileSysPath length to DWORD");
        goto LABEL_56;
      }
      if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
        goto LABEL_56;
      RedirectDebugMsg(2u, L"SizeTToDWord() Failed to convert lpGPOList->lpFileSysPath length to DWORD");
      v42 = 0;
      goto LABEL_57;
    }
    v24 = 0;
    if ( v22 )
      v24 = v23;
    v71 = v24;
    v25 = 0;
    v69 = 0;
    if ( !v22 || !a5 )
    {
      v26 = 2 * v24 + 2;
      goto LABEL_31;
    }
    v73 = 0;
    if ( !(unsigned int)GetFileActivePath(v8, v24, &v73) )
    {
      LastError = 4317;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"SaveGPOList: Failed to get file active path.");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"SaveGPOList: Failed to get file active path.");
        }
      }
      goto LABEL_148;
    }
    v61 = MapRemotePathToLocalPath(*((const unsigned __int16 **)lpData + 2), v73, &v69, &v78);
    if ( v61 )
    {
      LastError = v61;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"SaveGPOList: Failed to set file sys path reg value with %d.", v61);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"SaveGPOList: Failed to set file sys path reg value with %d.", v61);
        }
      }
      goto LABEL_148;
    }
    v25 = v69;
    v62 = -1;
    do
      ++v62;
    while ( v69[v62] );
    if ( (int)ULongLongToULong(v62, &v71) < 0 )
    {
      LastError = GetLastError();
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"SizeTToDWord() Failed to convert xszLocalFilePath length to DWORD");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"SizeTToDWord() Failed to convert xszLocalFilePath length to DWORD");
        }
      }
LABEL_148:
      XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v73);
      goto LABEL_149;
    }
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v73);
    v22 = (const BYTE *)v25;
    v26 = 2 * v71 + 2;
LABEL_31:
    v27 = RegSetValueExW(hKey, L"FileSysPath", 0, 1u, v22, v26);
    if ( v27 )
    {
      LastError = v27;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"SaveGPOList: Failed to set file sys path reg value with %d.", v27);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"SaveGPOList: Failed to set file sys path reg value with %d.", v27);
        }
      }
      goto LABEL_149;
    }
    v28 = (const BYTE *)*((_QWORD *)lpData + 3);
    v29 = -1;
    do
      ++v29;
    while ( *(_WORD *)&v28[2 * v29] );
    if ( v29 > 0xFFFFFFFF )
    {
      LastError = GetLastError();
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"SizeTToDWord() Failed to convert lpGPOList->lpDisplayName length to DWORD");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"SizeTToDWord() Failed to convert lpGPOList->lpDisplayName length to DWORD");
        }
      }
LABEL_149:
      XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v69);
      v42 = 0;
      goto LABEL_57;
    }
    v30 = 0;
    if ( v28 )
      v30 = v29;
    v71 = 2 * v30 + 2;
    v31 = RegSetValueExW(hKey, L"DisplayName", 0, 1u, v28, v71);
    if ( v31 )
    {
      LastError = v31;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"SaveGPOList: Failed to set display name reg value with %d.", v31);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"SaveGPOList: Failed to set display name reg value with %d.", v31);
        }
      }
      goto LABEL_149;
    }
    v32 = (const BYTE *)*((_QWORD *)lpData + 20);
    if ( v32 )
    {
      v33 = -1;
      do
        ++v33;
      while ( *(_WORD *)&v32[2 * v33] );
      v34 = 2 * v33 + 2;
      if ( v34 > 0xFFFFFFFF )
      {
        LastError = GetLastError();
        if ( !*(_DWORD *)&g_dwDebugLevel )
          goto LABEL_149;
        v39 = g_lpDebugMsg;
        if ( !g_lpDebugMsg )
          goto LABEL_81;
        goto LABEL_158;
      }
      v71 = v34;
      v35 = RegSetValueExW(hKey, L"Extensions", 0, 1u, v32, v34);
      if ( v35 )
      {
        LastError = v35;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"SaveGPOList: Failed to set extension names reg value with %d.", v35);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"SaveGPOList: Failed to set extension names reg value with %d.", v35);
          }
        }
        goto LABEL_149;
      }
    }
    v36 = *((_QWORD *)lpData + 22);
    if ( v36 )
    {
      v63 = -1;
      do
        ++v63;
      while ( *(_WORD *)(v36 + 2 * v63) );
      if ( (int)ULongLongToULong(2 * v63 + 2, &v71) < 0 )
        goto LABEL_79;
      v65 = RegSetValueExW(hKey, L"Link", 0, 1u, v64, v71);
      if ( v65 )
      {
        LastError = v65;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"SaveGPOList: Failed to set DSObject reg value with %d.", v65);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"SaveGPOList: Failed to set DSObject reg value with %d.", v65);
          }
        }
        goto LABEL_149;
      }
    }
    v37 = lpData + 32;
    v38 = -1;
    do
      ++v38;
    while ( *(_WORD *)&v37[2 * v38] );
    if ( v38 > 0xFFFFFFFF )
    {
      LastError = GetLastError();
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_149;
      v39 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && (char *)g_lpDebugMsgContext != (char *)g_lpDebugMsg )
          RedirectDebugMsg(2u, L"SizeTToDWord() Failed to convert lpGPOList->szGPOName length to DWORD");
        goto LABEL_149;
      }
      v66 = L"SizeTToDWord() Failed to convert lpGPOList->szGPOName length to DWORD";
LABEL_160:
      v39(2u, v66);
      goto LABEL_149;
    }
    v12 = 0;
    if ( lpData != (BYTE *)-32LL )
      v12 = v38;
    v13 = RegSetValueExW(hKey, L"GPOName", 0, 1u, lpData + 32, 2 * v12 + 2);
    if ( v13 )
    {
      LastError = v13;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"SaveGPOList: Failed to set GPO name reg value with %d.", v13);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"SaveGPOList: Failed to set GPO name reg value with %d.", v13);
        }
      }
      goto LABEL_149;
    }
    v14 = RegSetValueExW(hKey, L"GPOLink", 0, 4u, lpData + 132, 4u);
    if ( v14 )
    {
      LastError = v14;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"SaveGPOList: Failed to set GPOLink reg value with %d.", v14);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"SaveGPOList: Failed to set GPOLink reg value with %d.", v14);
        }
      }
      goto LABEL_149;
    }
    v15 = RegSetValueExW(hKey, L"lParam", 0, 4u, lpData + 136, 8u);
    if ( v15 )
    {
      LastError = v15;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"SaveGPOList: Failed to set lParam reg value with %d.", v15);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"SaveGPOList: Failed to set lParam reg value with %d.", v15);
        }
      }
      goto LABEL_149;
    }
    v16 = *((_QWORD *)v8 + 38);
    if ( v16 )
    {
      v44 = GetLastError();
      if ( lpData == (BYTE *)-32LL )
      {
        v48 = 87;
LABEL_69:
        SetLastError(v48);
      }
      else
      {
        while ( 1 )
        {
          if ( !v16 )
          {
            v48 = v44;
            goto LABEL_69;
          }
          v45 = *(const WCHAR **)v16;
          v46 = -1;
          do
            ++v46;
          while ( v45[v46] );
          v47 = -1;
          do
            ++v47;
          while ( *(_WORD *)&v37[2 * v47] );
          if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)lpData + 16, v47, v45, v46) == 2 )
            break;
          v16 = *(_QWORD *)(v16 + 32);
        }
        v50 = *(_QWORD *)(v16 + 24);
        SetLastError(v44);
        if ( v50 )
        {
          if ( !*(_QWORD *)(v50 + 8) )
            StringClone(L"1;3;10;4;WQL;root\\CIMv2;NULL;", (unsigned __int16 **)(v50 + 8));
          v51 = *(const BYTE **)(v50 + 8);
          v52 = -1;
          do
            ++v52;
          while ( *(_WORD *)&v51[2 * v52] );
          v53 = 2 * v52 + 2;
          if ( v53 > 0xFFFFFFFF )
          {
LABEL_79:
            LastError = GetLastError();
            if ( !*(_DWORD *)&g_dwDebugLevel )
              goto LABEL_149;
            v39 = g_lpDebugMsg;
            if ( !g_lpDebugMsg )
            {
LABEL_81:
              if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                RedirectDebugMsg(2u, L"SizeTToDWord() Failed to convert to DWORD");
              goto LABEL_149;
            }
LABEL_158:
            v66 = L"SizeTToDWord() Failed to convert to DWORD";
            goto LABEL_160;
          }
          v49 = RegSetValueExW(hKey, L"WMIRules", 0, 1u, v51, v53);
          if ( v49 )
          {
            LastError = v49;
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(2u, L"SaveGPOList: Failed to set WMIRules reg value with %d.", v49);
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(2u, L"SaveGPOList: Failed to set WMIRules reg value with %d.", v49);
              }
            }
            goto LABEL_149;
          }
        }
      }
      v6 = v74;
    }
    RegCloseKey(hKey);
    hKey = 0;
    v11 = ++v72;
    lpData = (BYTE *)*((_QWORD *)lpData + 18);
    v8 = v76;
    if ( v25 )
    {
      LocalFree(v25);
      v11 = v72;
    }
    v7 = v77;
  }
  LastError = GetLastError();
  if ( !*(_DWORD *)&g_dwDebugLevel )
  {
LABEL_56:
    v42 = 0;
    goto LABEL_57;
  }
  if ( g_lpDebugMsg )
  {
    g_lpDebugMsg(2u, L"SizeTToDWord() Failed to convert to DWORD");
    goto LABEL_56;
  }
  if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
    goto LABEL_56;
  RedirectDebugMsg(2u, L"SizeTToDWord() Failed to convert to DWORD");
  v42 = 0;
LABEL_57:
  if ( hKey )
    RegCloseKey(hKey);
  SetLastError(LastError);
  return v42;
}

```

## disassembly

```asm
0x18002e5a0  push    rbp
0x18002e5a2  push    rbx
0x18002e5a3  push    rsi
0x18002e5a4  push    rdi
0x18002e5a5  push    r12
0x18002e5a7  push    r13
0x18002e5a9  push    r14
0x18002e5ab  push    r15
0x18002e5ad  lea     rbp, [rsp-338h]
0x18002e5b5  sub     rsp, 438h
0x18002e5bc  mov     rax, cs:__security_cookie
0x18002e5c3  xor     rax, rsp
0x18002e5c6  mov     [rbp+370h+var_50], rax
0x18002e5cd  mov     r13, r9
0x18002e5d0  mov     rbx, r8
0x18002e5d3  mov     [rsp+470h+var_3F8], rbx
0x18002e5d8  mov     rdi, rdx
0x18002e5db  mov     [rbp+370h+var_3E0], rdx
0x18002e5df  mov     r15, rcx
0x18002e5e2  mov     [rbp+370h+var_3E8], rcx
0x18002e5e6  xor     r12d, r12d
0x18002e5e9  mov     [rsp+470h+hKey], r12
0x18002e5ee  mov     [rbp+370h+dwDisposition], r12d
0x18002e5f2  call    cs:__imp_GetLastError
0x18002e5f8  mov     esi, eax
0x18002e5fa  mov     [rsp+470h+var_41C], eax
0x18002e5fe  test    r15, r15
0x18002e601  jz      loc_18002EB33
0x18002e607  test    rdi, rdi
0x18002e60a  jz      loc_18002EB33
0x18002e610  test    rbx, rbx
0x18002e613  jz      loc_18002EB33
0x18002e619  mov     rdx, rbx; unsigned __int16 *
0x18002e61c  mov     rcx, rdi; HKEY
0x18002e61f  call    ?GPRegDelnode@@YAKPEAUHKEY__@@PEBG@Z; GPRegDelnode(HKEY__ *,ushort const *)
0x18002e624  test    eax, eax
0x18002e626  jnz     loc_18002EC95
0x18002e62c  test    byte ptr [r15], 1
0x18002e630  mov     rcx, r12
0x18002e633  jnz     short loc_18002E639
0x18002e635  mov     rcx, [r15+8]; void *
0x18002e639  mov     dword ptr [rsp+470h+cbData], r12d; int
0x18002e63e  mov     dword ptr [rsp+470h+lpData], r12d; int
0x18002e643  xor     r9d, r9d; int
0x18002e646  mov     r8, rbx; unsigned __int16 *
0x18002e649  mov     rdx, rdi; HKEY
0x18002e64c  call    ?MakeRegKeySecure@@YAHPEAXPEAUHKEY__@@PEBGHHH@Z; MakeRegKeySecure(void *,HKEY__ *,ushort const *,int,int,int)
0x18002e651  test    eax, eax
0x18002e653  jz      loc_18002ECF6
0x18002e659  mov     eax, r12d
0x18002e65c  mov     [rsp+470h+var_404], eax
0x18002e660  mov     [rsp+470h+var_420], r12d
0x18002e665  mov     r12d, 0FFFFFFFFh
0x18002e66b  xor     r14d, r14d
0x18002e66e  jmp     loc_18002E76A
0x18002e673  xor     eax, eax
0x18002e675  test    r14, r14
0x18002e678  cmovnz  eax, ecx
0x18002e67b  lea     eax, ds:2[rax*2]
0x18002e682  mov     dword ptr [rsp+470h+cbData], eax; cbData
0x18002e686  mov     [rsp+470h+lpData], r14; lpData
0x18002e68b  mov     r9d, 1; dwType
0x18002e691  xor     r8d, r8d; Reserved
0x18002e694  lea     rdx, aGponame; "GPOName"
0x18002e69b  mov     rcx, [rsp+470h+hKey]; hKey
0x18002e6a0  call    cs:__imp_RegSetValueExW
0x18002e6a6  test    eax, eax
0x18002e6a8  jnz     loc_18002F325
0x18002e6ae  lea     rax, [r13+84h]
0x18002e6b5  mov     dword ptr [rsp+470h+cbData], 4; cbData
0x18002e6bd  mov     [rsp+470h+lpData], rax; lpData
0x18002e6c2  mov     r9d, 4; dwType
0x18002e6c8  xor     r8d, r8d; Reserved
0x18002e6cb  lea     rdx, aGpolink; "GPOLink"
0x18002e6d2  mov     rcx, [rsp+470h+hKey]; hKey
0x18002e6d7  call    cs:__imp_RegSetValueExW
0x18002e6dd  test    eax, eax
0x18002e6df  jnz     loc_18002F2B5
0x18002e6e5  lea     rax, [r13+88h]
0x18002e6ec  mov     dword ptr [rsp+470h+cbData], 8; cbData
0x18002e6f4  mov     [rsp+470h+lpData], rax; lpData
0x18002e6f9  mov     r9d, 4; dwType
0x18002e6ff  xor     r8d, r8d; Reserved
0x18002e702  lea     rdx, aLparam; "lParam"
0x18002e709  mov     rcx, [rsp+470h+hKey]; hKey
0x18002e70e  call    cs:__imp_RegSetValueExW
0x18002e714  test    eax, eax
0x18002e716  jnz     loc_18002F245
0x18002e71c  mov     r15, [r15+130h]
0x18002e723  test    r15, r15
0x18002e726  jnz     loc_18002EA8A
0x18002e72c  mov     rcx, [rsp+470h+hKey]; hKey
0x18002e731  call    cs:__imp_RegCloseKey
0x18002e737  xor     r14d, r14d
0x18002e73a  mov     [rsp+470h+hKey], r14
0x18002e73f  mov     eax, [rsp+470h+var_404]
0x18002e743  inc     eax
0x18002e745  mov     [rsp+470h+var_404], eax
0x18002e749  mov     r13, [r13+90h]
0x18002e750  test    rdi, rdi
0x18002e753  mov     r15, [rbp+370h+var_3E8]
0x18002e757  jz      short loc_18002E766
0x18002e759  mov     rcx, rdi; hMem
0x18002e75c  call    cs:__imp_LocalFree
0x18002e762  mov     eax, [rsp+470h+var_404]
0x18002e766  mov     rdi, [rbp+370h+var_3E0]
0x18002e76a  test    r13, r13
0x18002e76d  jz      loc_18002F6BB
0x18002e773  mov     dword ptr [rsp+470h+lpData], eax
0x18002e777  mov     r9, rbx
0x18002e77a  lea     r8, aWsD; "%ws\\%d"
0x18002e781  mov     edx, 190h; unsigned __int64
0x18002e786  lea     rcx, [rbp+370h+SubKey]; unsigned __int16 *
0x18002e78a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e78f  test    eax, eax
0x18002e791  js      loc_18002F6B3
0x18002e797  lea     rax, [rbp+370h+dwDisposition]
0x18002e79b  mov     [rsp+470h+lpdwDisposition], rax; lpdwDisposition
0x18002e7a0  lea     rax, [rsp+470h+hKey]
0x18002e7a5  mov     [rsp+470h+phkResult], rax; phkResult
0x18002e7aa  mov     [rsp+470h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18002e7af  mov     dword ptr [rsp+470h+cbData], 20006h; samDesired
0x18002e7b7  mov     dword ptr [rsp+470h+lpData], r14d; dwOptions
0x18002e7bc  xor     r9d, r9d; lpClass
0x18002e7bf  xor     r8d, r8d; Reserved
0x18002e7c2  lea     rdx, [rbp+370h+SubKey]; lpSubKey
0x18002e7c6  mov     rcx, rdi; hKey
0x18002e7c9  call    cs:__imp_RegCreateKeyExW
0x18002e7cf  test    eax, eax
0x18002e7d1  jnz     loc_18002F63E
0x18002e7d7  mov     dword ptr [rsp+470h+cbData], 4; cbData
0x18002e7df  mov     [rsp+470h+lpData], r13; lpData
0x18002e7e4  mov     r9d, 4; dwType
0x18002e7ea  xor     r8d, r8d; Reserved
0x18002e7ed  lea     rdx, aOptions; "Options"
0x18002e7f4  mov     rcx, [rsp+470h+hKey]; hKey
0x18002e7f9  call    cs:__imp_RegSetValueExW
0x18002e7ff  test    eax, eax
0x18002e801  jnz     loc_18002F5C9
0x18002e807  lea     rax, [r13+4]
0x18002e80b  mov     dword ptr [rsp+470h+cbData], 4; cbData
0x18002e813  mov     [rsp+470h+lpData], rax; lpData
0x18002e818  mov     r9d, 4; dwType
0x18002e81e  xor     r8d, r8d; Reserved
0x18002e821  lea     rdx, aVersion_1; "Version"
0x18002e828  mov     rcx, [rsp+470h+hKey]; hKey
0x18002e82d  call    cs:__imp_RegSetValueExW
0x18002e833  test    eax, eax
0x18002e835  jnz     loc_18002F554
0x18002e83b  mov     rax, [r13+8]
0x18002e83f  test    rax, rax
0x18002e842  jnz     loc_18002EA0D
0x18002e848  mov     rcx, [r13+10h]
0x18002e84c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002e853  inc     rax
0x18002e856  cmp     word ptr [rcx+rax*2], 0
0x18002e85b  jnz     short loc_18002E853
0x18002e85d  cmp     rax, r12
0x18002e860  ja      loc_18002F4E2
0x18002e866  mov     edx, r14d
0x18002e869  test    rcx, rcx
0x18002e86c  cmovnz  edx, eax; int
0x18002e86f  mov     [rsp+470h+var_408], edx
0x18002e873  mov     rdi, r14
0x18002e876  mov     [rsp+470h+var_418], r14
0x18002e87b  jnz     loc_18002EDE1
0x18002e881  lea     eax, ds:2[rdx*2]
0x18002e888  mov     dword ptr [rsp+470h+cbData], eax; cbData
0x18002e88c  mov     [rsp+470h+lpData], rcx; lpData
0x18002e891  mov     r9d, 1; dwType
0x18002e897  xor     r8d, r8d; Reserved
0x18002e89a  lea     rdx, aFilesyspath; "FileSysPath"
0x18002e8a1  mov     rcx, [rsp+470h+hKey]; hKey
0x18002e8a6  call    cs:__imp_RegSetValueExW
0x18002e8ac  test    eax, eax
0x18002e8ae  jnz     loc_18002F472
0x18002e8b4  mov     rdx, [r13+18h]
0x18002e8b8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002e8bf  nop
0x18002e8c0  inc     rcx
0x18002e8c3  cmp     word ptr [rdx+rcx*2], 0
0x18002e8c8  jnz     short loc_18002E8C0
0x18002e8ca  cmp     rcx, r12
0x18002e8cd  ja      loc_18002F405
0x18002e8d3  mov     eax, r14d
0x18002e8d6  test    rdx, rdx
0x18002e8d9  cmovnz  eax, ecx
0x18002e8dc  lea     eax, ds:2[rax*2]
0x18002e8e3  mov     [rsp+470h+var_408], eax
0x18002e8e7  mov     dword ptr [rsp+470h+cbData], eax; cbData
0x18002e8eb  mov     [rsp+470h+lpData], rdx; lpData
0x18002e8f0  mov     r9d, 1; dwType
0x18002e8f6  xor     r8d, r8d; Reserved
0x18002e8f9  lea     rdx, aDisplayname; "DisplayName"
0x18002e900  mov     rcx, [rsp+470h+hKey]; hKey
0x18002e905  call    cs:__imp_RegSetValueExW
0x18002e90b  test    eax, eax
0x18002e90d  jnz     loc_18002F395
0x18002e913  mov     rcx, [r13+0A0h]
0x18002e91a  test    rcx, rcx
0x18002e91d  jz      short loc_18002E97C
0x18002e91f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002e926  nop     word ptr [rax+rax+00000000h]
0x18002e930  lea     rax, [rax+1]
0x18002e934  cmp     word ptr [rcx+rax*2], 0
0x18002e939  jnz     short loc_18002E930
0x18002e93b  lea     rax, ds:2[rax*2]
0x18002e943  cmp     rax, r12
0x18002e946  ja      loc_18002F16C
0x18002e94c  mov     [rsp+470h+var_408], eax
0x18002e950  mov     dword ptr [rsp+470h+cbData], eax; cbData
0x18002e954  mov     [rsp+470h+lpData], rcx; lpData
0x18002e959  mov     r9d, 1; dwType
0x18002e95f  xor     r8d, r8d; Reserved
0x18002e962  lea     rdx, aExtensions; "Extensions"
0x18002e969  mov     rcx, [rsp+470h+hKey]; hKey
0x18002e96e  call    cs:__imp_RegSetValueExW
0x18002e974  test    eax, eax
0x18002e976  jnz     loc_18002F10E
0x18002e97c  mov     r9, [r13+0B0h]
0x18002e983  test    r9, r9
0x18002e986  jnz     loc_18002EE6C
0x18002e98c  lea     r14, [r13+20h]
0x18002e990  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002e997  nop     word ptr [rax+rax+00000000h]
0x18002e9a0  inc     rcx
0x18002e9a3  cmp     word ptr [r14+rcx*2], 0
0x18002e9a9  jnz     short loc_18002E9A0
0x18002e9ab  cmp     rcx, r12
0x18002e9ae  jbe     loc_18002E673
0x18002e9b4  call    cs:__imp_GetLastError
0x18002e9ba  mov     esi, eax
0x18002e9bc  mov     [rsp+470h+var_41C], eax
0x18002e9c0  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18002e9c7  jz      loc_18002F0FA
0x18002e9cd  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18002e9d4  test    rax, rax
0x18002e9d7  jnz     loc_18002F19E
0x18002e9dd  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rax; void * g_lpDebugMsgContextInstance
0x18002e9e4  jz      loc_18002F0FA
0x18002e9ea  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rax; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18002e9f1  jz      loc_18002F0FA
0x18002e9f7  lea     rdx, aSizettodwordFa_6; "SizeTToDWord() Failed to convert lpGPOL"...
0x18002e9fe  mov     ecx, 2; unsigned int
0x18002ea03  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18002ea08  jmp     loc_18002F0FA
0x18002ea0d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002ea14  lea     rcx, [rcx+1]
0x18002ea18  cmp     word ptr [rax+rcx*2], 0
0x18002ea1d  jnz     short loc_18002EA14
0x18002ea1f  lea     rcx, ds:2[rcx*2]
0x18002ea27  cmp     rcx, r12
0x18002ea2a  jbe     loc_18002ED76
0x18002ea30  call    cs:__imp_GetLastError
0x18002ea36  mov     esi, eax
0x18002ea38  mov     [rsp+470h+var_41C], eax
0x18002ea3c  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18002ea43  jnz     loc_18002EF61
0x18002ea49  mov     r14d, [rsp+470h+var_420]
0x18002ea4e  mov     rcx, [rsp+470h+hKey]; hKey
0x18002ea53  test    rcx, rcx
0x18002ea56  jnz     loc_18002F6C6
0x18002ea5c  mov     ecx, esi; dwErrCode
0x18002ea5e  call    cs:__imp_SetLastError
0x18002ea64  mov     eax, r14d
0x18002ea67  mov     rcx, [rbp+370h+var_50]
0x18002ea6e  xor     rcx, rsp; StackCookie
0x18002ea71  call    __security_check_cookie
0x18002ea76  add     rsp, 438h
0x18002ea7d  pop     r15
0x18002ea7f  pop     r14
0x18002ea81  pop     r13
0x18002ea83  pop     r12
0x18002ea85  pop     rdi
0x18002ea86  pop     rsi
0x18002ea87  pop     rbx
0x18002ea88  pop     rbp
0x18002ea89  retn
0x18002ea8a  call    cs:__imp_GetLastError
0x18002ea90  nop
0x18002ea91  mov     ebx, eax
0x18002ea93  test    r14, r14
0x18002ea96  jz      loc_18002EF1D
0x18002ea9c  nop     dword ptr [rax+00h]
0x18002eaa0  test    r15, r15
0x18002eaa3  jz      short loc_18002EAF3
0x18002eaa5  mov     rcx, [r15]
0x18002eaa8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002eaaf  nop
0x18002eab0  inc     rax
0x18002eab3  cmp     word ptr [rcx+rax*2], 0
0x18002eab8  jnz     short loc_18002EAB0
0x18002eaba  mov     r9, 0FFFFFFFFFFFFFFFFh
0x18002eac1  inc     r9; cchCount1
0x18002eac4  cmp     word ptr [r14+r9*2], 0
0x18002eaca  jnz     short loc_18002EAC1
0x18002eacc  mov     dword ptr [rsp+470h+cbData], eax; cchCount2
0x18002ead0  mov     [rsp+470h+lpData], rcx; lpString2
0x18002ead5  mov     r8, r14; lpString1
0x18002ead8  mov     edx, 1; dwCmpFlags
  ... truncated ...
```

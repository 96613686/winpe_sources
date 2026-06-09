# CMsiEngine::ClearEngineData(void)

- ea: `0x1800b3a04`
- end: `0x1800b4541`
- name: `?ClearEngineData@CMsiEngine@@IEAAXXZ`
- size: `2877`
- prototype: `void __fastcall(CMsiEngine *__hidden this)`
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x1800b4680`
- `0x18017ac60`

## callees

- `0x18001e5d0`
- `0x180025904`
- `0x180025a18`
- `0x1800620e4`
- `0x180068680`
- `0x1800b3a04`
- `0x1800d6f44`
- `0x1801158ec`
- `0x180115954`
- `0x18011678c`
- `0x180117804`
- `0x18011786c`
- `0x1801727fc`
- `0x18017284c`
- `0x180172878`
- `0x1801728a0`
- `0x1801728c8`
- `0x18017ef00`
- `0x1801fff20`
- `0x180200e04`
- `0x18025c010`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x1800b3d91`
- `KERNEL32!DeleteFileW` at `0x1800b3dbc`
- `KERNEL32!DeleteFileW` at `0x1800b4346`
- `KERNEL32!DeleteFileW` at `0x1800b4411`
- `KERNEL32!DeleteFileW` at `0x1800b3d91`
- `KERNEL32!DeleteFileW` at `0x1800b3dbc`
- `KERNEL32!DeleteFileW` at `0x1800b4346`
- `KERNEL32!DeleteFileW` at `0x1800b4411`
- `KERNEL32!GetLastError` at `0x1800b4358`
- `KERNEL32!GetLastError` at `0x1800b442b`
- `KERNEL32!GetLastError` at `0x1800b4358`
- `KERNEL32!GetLastError` at `0x1800b442b`

## string_xrefs

- `0x1800b42fe`: `Attempting to delete file %s`
- `0x1800b43c9`: `Attempting to delete file %s`
- `0x1800b4363`: `Unable to delete the file. LastError = %d`
- `0x1800b4436`: `Unable to delete the file. LastError = %d`

## pseudocode

```c
void __fastcall CMsiEngine::ClearEngineData(CMsiEngine *this, unsigned int a2)
{
  LPCWSTR v3; // rcx
  __int64 v4; // rdx
  CMsiEmbeddedUIManager *v5; // rcx
  __int64 v6; // r8
  CMsiBaselineManager *v7; // rcx
  CMsiSecureRepairManager *v8; // rcx
  CMsiPatchManager *v9; // rcx
  __int64 i; // rbx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  CScriptGenerate *v27; // rcx
  bool v28; // zf
  const WCHAR *v29; // rax
  const WCHAR *v30; // rax
  CScriptGenerate *v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rcx
  __int64 v55; // rcx
  unsigned int j; // ebx
  __int64 v57; // rcx
  unsigned int k; // ebx
  __int64 v59; // rcx
  MSIHANDLE v60; // ecx
  __int64 v61; // rcx
  void (__fastcall ***v62)(_QWORD, __int64); // rcx
  _QWORD *v63; // rsi
  __int64 v64; // rbx
  const unsigned __int16 *v65; // rax
  const WCHAR *v66; // rax
  DWORD LastError; // eax
  const unsigned __int16 *v68; // rax
  const WCHAR *v69; // rax
  DWORD v70; // eax
  CWin64DualFolders *v71; // rcx
  char v72; // [rsp+A0h] [rbp+8h] BYREF

  if ( g_scServerContext || *((_QWORD *)this + 22) )
  {
LABEL_5:
    v3 = g_pEmbeddedUI;
    if ( !g_pEmbeddedUI )
      goto LABEL_13;
    goto LABEL_6;
  }
  (*(void (__fastcall **)(CMsiEngine *))(*(_QWORD *)this + 456LL))(this);
  v3 = g_pEmbeddedUI;
  if ( !g_pEmbeddedUI )
  {
    (*(void (__fastcall **)(CMsiEngine *))(*(_QWORD *)this + 464LL))(this);
    goto LABEL_5;
  }
LABEL_6:
  if ( !*((_BYTE *)v3 + 1092) )
  {
    *((_DWORD *)v3 + 272) = 0;
    MsiMessageHandler::ShutdownHandler((MsiMessageHandler *)(v3 + 268));
    if ( !g_scServerContext && !*((_QWORD *)this + 22) )
      (*(void (__fastcall **)(CMsiEngine *))(*(_QWORD *)this + 464LL))(this);
    CMsiEmbeddedUIManager::CleanupTempDirectory(v5, v4, v6);
    if ( g_pEmbeddedUI )
      CMsiEmbeddedUIManager::`scalar deleting destructor'((CMsiEmbeddedUIManager *)g_pEmbeddedUI, a2);
    g_pEmbeddedUI = 0;
  }
LABEL_13:
  v7 = (CMsiBaselineManager *)*((_QWORD *)this + 116);
  if ( v7 )
  {
    CMsiBaselineManager::`scalar deleting destructor'(v7, a2);
    *((_QWORD *)this + 116) = 0;
  }
  v8 = (CMsiSecureRepairManager *)*((_QWORD *)this + 276);
  if ( v8 )
  {
    CMsiSecureRepairManager::`scalar deleting destructor'(v8, a2);
    *((_QWORD *)this + 276) = 0;
  }
  v9 = (CMsiPatchManager *)*((_QWORD *)this + 117);
  if ( v9 )
  {
    CMsiPatchManager::`scalar deleting destructor'(v9, a2);
    *((_QWORD *)this + 117) = 0;
  }
  for ( i = 0; i != 16; ++i )
  {
    v11 = *((_QWORD *)this + i + 26);
    if ( v11 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      *((_QWORD *)this + i + 26) = 0;
    }
  }
  v12 = *((_QWORD *)this + 52);
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    *((_QWORD *)this + 52) = 0;
  }
  v13 = *((_QWORD *)this + 53);
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    *((_QWORD *)this + 53) = 0;
  }
  v14 = *((_QWORD *)this + 23);
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    *((_QWORD *)this + 23) = 0;
  }
  v15 = *((_QWORD *)this + 24);
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    *((_QWORD *)this + 24) = 0;
  }
  v16 = *((_QWORD *)this + 25);
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    *((_QWORD *)this + 25) = 0;
  }
  v17 = *((_QWORD *)this + 112);
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    *((_QWORD *)this + 112) = 0;
  }
  v18 = *((_QWORD *)this + 113);
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    *((_QWORD *)this + 113) = 0;
  }
  v19 = *((_QWORD *)this + 84);
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    *((_QWORD *)this + 84) = 0;
  }
  v20 = *((_QWORD *)this + 85);
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    *((_QWORD *)this + 85) = 0;
  }
  v21 = *((_QWORD *)this + 42);
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    *((_QWORD *)this + 42) = 0;
  }
  v22 = *((_QWORD *)this + 43);
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    *((_QWORD *)this + 43) = 0;
  }
  if ( *((_DWORD *)this + 89) )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 45) + 16LL))(*((_QWORD *)this + 45));
    v23 = *((_QWORD *)this + 46);
    *((_QWORD *)this + 45) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v24 = *((_QWORD *)this + 47);
    *((_QWORD *)this + 46) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v25 = *((_QWORD *)this + 48);
    *((_QWORD *)this + 47) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v26 = *((_QWORD *)this + 49);
    *((_QWORD *)this + 48) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    *((_QWORD *)this + 49) = 0;
    *((_DWORD *)this + 89) = 0;
  }
  *(_QWORD *)((char *)this + 68) = 0;
  *((_DWORD *)this + 24) = 0;
  *((_DWORD *)this + 9) = 0;
  *((_WORD *)this + 810) = 0;
  *((_DWORD *)this + 452) = 0;
  *((_DWORD *)this + 406) = 0;
  *(_WORD *)((char *)this + 601) = 0;
  v27 = (CScriptGenerate *)*((_QWORD *)this + 13);
  *((_BYTE *)this + 588) = 0;
  *((_DWORD *)this + 127) = 0;
  *((_BYTE *)this + 953) = 0;
  if ( v27 )
  {
    CScriptGenerate::`scalar deleting destructor'(v27, a2);
    v28 = g_scServerContext == 2;
    *((_QWORD *)this + 13) = 0;
    if ( v28 )
    {
      CElevate::CElevate((CElevate *)&v72, 1);
      v29 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 54) + 80LL))(*((_QWORD *)this + 54));
      DeleteFileW(v29);
      CElevate::~CElevate((CElevate *)&v72);
    }
    else
    {
      v30 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 54) + 80LL))(*((_QWORD *)this + 54));
      DeleteFileW(v30);
    }
  }
  v31 = (CScriptGenerate *)*((_QWORD *)this + 14);
  if ( v31 )
  {
    CScriptGenerate::`scalar deleting destructor'(v31, a2);
    *((_QWORD *)this + 14) = 0;
  }
  v32 = *((_QWORD *)this + 54);
  *((_DWORD *)this + 120) = 0;
  if ( v32 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    *((_QWORD *)this + 54) = 0;
  }
  v33 = *((_QWORD *)this + 55);
  if ( v33 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    *((_QWORD *)this + 55) = 0;
  }
  v34 = *((_QWORD *)this + 271);
  if ( v34 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    *((_QWORD *)this + 271) = 0;
  }
  v35 = *((_QWORD *)this + 272);
  if ( v35 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    *((_QWORD *)this + 272) = 0;
  }
  v36 = *((_QWORD *)this + 100);
  if ( v36 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    *((_QWORD *)this + 100) = 0;
  }
  v37 = *((_QWORD *)this + 101);
  if ( v37 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    *((_QWORD *)this + 101) = 0;
  }
  v38 = *((_QWORD *)this + 106);
  if ( v38 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    *((_QWORD *)this + 106) = 0;
  }
  v39 = *((_QWORD *)this + 107);
  if ( v39 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    *((_QWORD *)this + 107) = 0;
  }
  v40 = *((_QWORD *)this + 122);
  if ( v40 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    *((_QWORD *)this + 122) = 0;
  }
  v41 = *((_QWORD *)this + 123);
  if ( v41 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    *((_QWORD *)this + 123) = 0;
  }
  v42 = *((_QWORD *)this + 126);
  if ( v42 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    *((_QWORD *)this + 126) = 0;
  }
  v43 = *((_QWORD *)this + 127);
  if ( v43 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    *((_QWORD *)this + 127) = 0;
  }
  v44 = *((_QWORD *)this + 130);
  if ( v44 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    *((_QWORD *)this + 130) = 0;
  }
  v45 = *((_QWORD *)this + 131);
  if ( v45 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    *((_QWORD *)this + 131) = 0;
  }
  v46 = *((_QWORD *)this + 141);
  if ( v46 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    *((_QWORD *)this + 141) = 0;
  }
  v47 = *((_QWORD *)this + 142);
  if ( v47 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    *((_QWORD *)this + 142) = 0;
  }
  v48 = *((_QWORD *)this + 145);
  if ( v48 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    *((_QWORD *)this + 145) = 0;
  }
  v49 = *((_QWORD *)this + 146);
  if ( v49 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    *((_QWORD *)this + 146) = 0;
  }
  v50 = *((_QWORD *)this + 149);
  if ( v50 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    *((_QWORD *)this + 149) = 0;
  }
  v51 = *((_QWORD *)this + 150);
  if ( v51 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    *((_QWORD *)this + 150) = 0;
  }
  v52 = *((_QWORD *)this + 154);
  if ( v52 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    *((_QWORD *)this + 154) = 0;
  }
  v53 = *((_QWORD *)this + 155);
  if ( v53 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    *((_QWORD *)this + 155) = 0;
  }
  v54 = *((_QWORD *)this + 134);
  if ( v54 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    *((_QWORD *)this + 134) = 0;
  }
  v55 = *((_QWORD *)this + 135);
  if ( v55 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    *((_QWORD *)this + 135) = 0;
  }
  if ( *((_QWORD *)this + 158) )
  {
    for ( j = 0; j < *((_DWORD *)this + 318); ++j )
    {
      v57 = *(_QWORD *)(*((_QWORD *)this + 158) + 8LL * j);
      if ( v57 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
        *(_QWORD *)(*((_QWORD *)this + 158) + 8LL * j) = 0;
      }
    }
    operator delete(*((void **)this + 158));
    *((_QWORD *)this + 158) = 0;
  }
  if ( *((_QWORD *)this + 157) )
  {
    for ( k = 0; k < *((_DWORD *)this + 318); ++k )
    {
      v59 = *(_QWORD *)(*((_QWORD *)this + 157) + 8LL * k);
      if ( v59 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
        *(_QWORD *)(*((_QWORD *)this + 157) + 8LL * k) = 0;
      }
    }
    operator delete(*((void **)this + 157));
    *((_QWORD *)this + 157) = 0;
  }
  if ( g_scServerContext == 2 )
  {
    v60 = *((_DWORD *)this + 25);
    if ( v60 )
    {
      MsiCloseHandle(v60);
      *((_DWORD *)this + 25) = 0;
    }
  }
  CMsiEngine::DestroyPatchUninstallCustomActionData(this);
  *((_BYTE *)this + 944) = 0;
  *((_BYTE *)this + 954) = 0;
  CMsiEngine::SetPatchingRunFromSourceFeatures(this, 0);
  CMsiEngine::SetPatchingDownRevFiles(this, 0);
  CMsiEngine::SetActiveMajorUpgradePatch(this, 0);
  CMsiEngine::SetForceRepair(this, 0);
  v61 = *((_QWORD *)this + 19);
  *((_DWORD *)this + 10) = 0;
  *((_WORD *)this + 744) = 0;
  if ( v61 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
    *((_QWORD *)this + 19) = 0;
  }
  v62 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 269);
  *((_DWORD *)this + 146) = 0;
  *((_DWORD *)this + 148) = -1;
  if ( v62 )
  {
    (**v62)(v62, 1);
    *((_QWORD *)this + 269) = 0;
  }
  *(_OWORD *)((char *)this + 780) = 0;
  *((_BYTE *)this + 2024) = 0;
  *(_OWORD *)((char *)this + 2028) = 0;
  *(_OWORD *)((char *)this + 2044) = 0;
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 120) + 16LL))(*((_QWORD *)this + 120));
  *((_QWORD *)this + 120) = &g_MsiStringNull;
  v63 = (_QWORD *)((char *)this + 1928);
  while ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v63 + 56LL))(*v63) )
  {
    v64 = MsiString::ExtractAndRemove((char *)this + 1928, 2, 59);
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v64 + 56LL))(v64) )
    {
      if ( g_scServerContext == 2 )
      {
        CElevate::CElevate((CElevate *)&v72, 1);
        if ( g_dmDiagnosticMode )
        {
          v65 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v64 + 80LL))(v64);
          DebugString(
            10,
            0,
            0,
            L"Attempting to delete file %s",
            v65,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        }
        v66 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v64 + 80LL))(v64);
        if ( !DeleteFileW(v66) )
        {
          if ( g_dmDiagnosticMode )
          {
            LastError = GetLastError();
            DebugString(
              10,
              0,
              0,
              L"Unable to delete the file. LastError = %d",
              (const unsigned __int16 *)LastError,
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
          }
        }
        CElevate::~CElevate((CElevate *)&v72);
      }
      else
      {
        if ( g_dmDiagnosticMode )
        {
          v68 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v64 + 80LL))(v64);
          DebugString(
            10,
            0,
            0,
            L"Attempting to delete file %s",
            v68,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        }
        v69 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v64 + 80LL))(v64);
        if ( !DeleteFileW(v69) && g_dmDiagnosticMode )
        {
          v70 = GetLastError();
          DebugString(
            10,
            0,
            0,
            L"Unable to delete the file. LastError = %d",
            (const unsigned __int16 *)v70,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        }
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
  }
  *((_QWORD *)this + 86) = 0;
  *((_QWORD *)this + 87) = 0;
  *((_QWORD *)this + 88) = 0;
  *((_QWORD *)this + 89) = 0;
  *((_QWORD *)this + 90) = 0;
  *((_QWORD *)this + 91) = 0;
  *((_QWORD *)this + 92) = 0;
  *((_QWORD *)this + 93) = 0;
  *((_QWORD *)this + 94) = 0;
  *((_QWORD *)this + 95) = 0;
  *((_QWORD *)this + 96) = 0;
  *((_DWORD *)this + 194) = 0;
  *((_QWORD *)this + 143) = 0;
  *((_QWORD *)this + 144) = 0;
  *((_QWORD *)this + 147) = 0;
  *((_QWORD *)this + 148) = 0;
  *((_QWORD *)this + 151) = 0;
  *((_QWORD *)this + 152) = 0;
  *((_QWORD *)this + 153) = 0;
  *((_DWORD *)this + 312) = 0;
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v63 + 16LL))(*v63);
  v28 = g_scServerContext == 2;
  *v63 = &g_MsiStringNull;
  *((_BYTE *)this + 2192) = 1;
  *((_BYTE *)this + 664) = 0;
  if ( !v28 && qword_180308938 )
    CWin64DualFolders::Release(v71);
}

```

## disassembly

```asm
0x1800b3a04  push    rbx
0x1800b3a06  push    rbp
0x1800b3a07  push    rsi
0x1800b3a08  push    rdi
0x1800b3a09  push    r13
0x1800b3a0b  push    r14
0x1800b3a0d  sub     rsp, 68h
0x1800b3a11  xor     ebp, ebp
0x1800b3a13  mov     rdi, rcx
0x1800b3a16  cmp     cs:?g_scServerContext@@3W4scEnum@@A, ebp; scEnum g_scServerContext
0x1800b3a1c  jnz     short loc_1800B3A54
0x1800b3a1e  cmp     [rcx+0B0h], rbp
0x1800b3a25  jnz     short loc_1800B3A54
0x1800b3a27  mov     rax, [rcx]
0x1800b3a2a  mov     rax, [rax+1C8h]
0x1800b3a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3a36  mov     rcx, cs:?g_pEmbeddedUI@@3PEAVCMsiEmbeddedUIManager@@EA; CMsiEmbeddedUIManager * g_pEmbeddedUI
0x1800b3a3d  test    rcx, rcx
0x1800b3a40  jnz     short loc_1800B3A60
0x1800b3a42  mov     rax, [rdi]
0x1800b3a45  mov     rcx, rdi
0x1800b3a48  mov     rax, [rax+1D0h]
0x1800b3a4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3a54  mov     rcx, cs:?g_pEmbeddedUI@@3PEAVCMsiEmbeddedUIManager@@EA; CMsiEmbeddedUIManager * g_pEmbeddedUI
0x1800b3a5b  test    rcx, rcx
0x1800b3a5e  jz      short loc_1800B3ABB
0x1800b3a60  cmp     [rcx+444h], bpl
0x1800b3a67  jnz     short loc_1800B3ABB
0x1800b3a69  mov     [rcx+440h], ebp
0x1800b3a6f  add     rcx, 218h; this
0x1800b3a76  call    ?ShutdownHandler@MsiMessageHandler@@QEAAKXZ; MsiMessageHandler::ShutdownHandler(void)
0x1800b3a7b  cmp     cs:?g_scServerContext@@3W4scEnum@@A, ebp; scEnum g_scServerContext
0x1800b3a81  jnz     short loc_1800B3A9E
0x1800b3a83  cmp     [rdi+0B0h], rbp
0x1800b3a8a  jnz     short loc_1800B3A9E
0x1800b3a8c  mov     rax, [rdi]
0x1800b3a8f  mov     rcx, rdi
0x1800b3a92  mov     rax, [rax+1D0h]
0x1800b3a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3a9e  call    ?CleanupTempDirectory@CMsiEmbeddedUIManager@@QEAAPEAGXZ; CMsiEmbeddedUIManager::CleanupTempDirectory(void)
0x1800b3aa3  mov     rcx, cs:?g_pEmbeddedUI@@3PEAVCMsiEmbeddedUIManager@@EA; this
0x1800b3aaa  test    rcx, rcx
0x1800b3aad  jz      short loc_1800B3AB4
0x1800b3aaf  call    ??_GCMsiEmbeddedUIManager@@QEAAPEAXI@Z; CMsiEmbeddedUIManager::`scalar deleting destructor'(uint)
0x1800b3ab4  mov     cs:?g_pEmbeddedUI@@3PEAVCMsiEmbeddedUIManager@@EA, rbp; CMsiEmbeddedUIManager * g_pEmbeddedUI
0x1800b3abb  mov     rcx, [rdi+3A0h]; this
0x1800b3ac2  test    rcx, rcx
0x1800b3ac5  jz      short loc_1800B3AD3
0x1800b3ac7  call    ??_GCMsiBaselineManager@@QEAAPEAXI@Z; CMsiBaselineManager::`scalar deleting destructor'(uint)
0x1800b3acc  mov     [rdi+3A0h], rbp
0x1800b3ad3  mov     rcx, [rdi+8A0h]; this
0x1800b3ada  test    rcx, rcx
0x1800b3add  jz      short loc_1800B3AEB
0x1800b3adf  call    ??_GCMsiSecureRepairManager@@QEAAPEAXI@Z; CMsiSecureRepairManager::`scalar deleting destructor'(uint)
0x1800b3ae4  mov     [rdi+8A0h], rbp
0x1800b3aeb  mov     rcx, [rdi+3A8h]; this
0x1800b3af2  test    rcx, rcx
0x1800b3af5  jz      short loc_1800B3B03
0x1800b3af7  call    ??_GCMsiPatchManager@@QEAAPEAXI@Z; CMsiPatchManager::`scalar deleting destructor'(uint)
0x1800b3afc  mov     [rdi+3A8h], rbp
0x1800b3b03  mov     rbx, rbp
0x1800b3b06  mov     rcx, [rdi+rbx*8+0D0h]
0x1800b3b0e  test    rcx, rcx
0x1800b3b11  jz      short loc_1800B3B27
0x1800b3b13  mov     rax, [rcx]
0x1800b3b16  mov     rax, [rax+10h]
0x1800b3b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3b1f  mov     [rdi+rbx*8+0D0h], rbp
0x1800b3b27  inc     rbx
0x1800b3b2a  cmp     rbx, 10h
0x1800b3b2e  jnz     short loc_1800B3B06
0x1800b3b30  mov     rcx, [rdi+1A0h]
0x1800b3b37  test    rcx, rcx
0x1800b3b3a  jz      short loc_1800B3B4F
0x1800b3b3c  mov     rax, [rcx]
0x1800b3b3f  mov     rax, [rax+10h]
0x1800b3b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3b48  mov     [rdi+1A0h], rbp
0x1800b3b4f  mov     rcx, [rdi+1A8h]
0x1800b3b56  test    rcx, rcx
0x1800b3b59  jz      short loc_1800B3B6E
0x1800b3b5b  mov     rax, [rcx]
0x1800b3b5e  mov     rax, [rax+10h]
0x1800b3b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3b67  mov     [rdi+1A8h], rbp
0x1800b3b6e  mov     rcx, [rdi+0B8h]
0x1800b3b75  test    rcx, rcx
0x1800b3b78  jz      short loc_1800B3B8D
0x1800b3b7a  mov     rax, [rcx]
0x1800b3b7d  mov     rax, [rax+10h]
0x1800b3b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3b86  mov     [rdi+0B8h], rbp
0x1800b3b8d  mov     rcx, [rdi+0C0h]
0x1800b3b94  test    rcx, rcx
0x1800b3b97  jz      short loc_1800B3BAC
0x1800b3b99  mov     rax, [rcx]
0x1800b3b9c  mov     rax, [rax+10h]
0x1800b3ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3ba5  mov     [rdi+0C0h], rbp
0x1800b3bac  mov     rcx, [rdi+0C8h]
0x1800b3bb3  test    rcx, rcx
0x1800b3bb6  jz      short loc_1800B3BCB
0x1800b3bb8  mov     rax, [rcx]
0x1800b3bbb  mov     rax, [rax+10h]
0x1800b3bbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3bc4  mov     [rdi+0C8h], rbp
0x1800b3bcb  mov     rcx, [rdi+380h]
0x1800b3bd2  test    rcx, rcx
0x1800b3bd5  jz      short loc_1800B3BEA
0x1800b3bd7  mov     rax, [rcx]
0x1800b3bda  mov     rax, [rax+10h]
0x1800b3bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3be3  mov     [rdi+380h], rbp
0x1800b3bea  mov     rcx, [rdi+388h]
0x1800b3bf1  test    rcx, rcx
0x1800b3bf4  jz      short loc_1800B3C09
0x1800b3bf6  mov     rax, [rcx]
0x1800b3bf9  mov     rax, [rax+10h]
0x1800b3bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3c02  mov     [rdi+388h], rbp
0x1800b3c09  mov     rcx, [rdi+2A0h]
0x1800b3c10  test    rcx, rcx
0x1800b3c13  jz      short loc_1800B3C28
0x1800b3c15  mov     rax, [rcx]
0x1800b3c18  mov     rax, [rax+10h]
0x1800b3c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3c21  mov     [rdi+2A0h], rbp
0x1800b3c28  mov     rcx, [rdi+2A8h]
0x1800b3c2f  test    rcx, rcx
0x1800b3c32  jz      short loc_1800B3C47
0x1800b3c34  mov     rax, [rcx]
0x1800b3c37  mov     rax, [rax+10h]
0x1800b3c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3c40  mov     [rdi+2A8h], rbp
0x1800b3c47  mov     rcx, [rdi+150h]
0x1800b3c4e  test    rcx, rcx
0x1800b3c51  jz      short loc_1800B3C66
0x1800b3c53  mov     rax, [rcx]
0x1800b3c56  mov     rax, [rax+10h]
0x1800b3c5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3c5f  mov     [rdi+150h], rbp
0x1800b3c66  mov     rcx, [rdi+158h]
0x1800b3c6d  test    rcx, rcx
0x1800b3c70  jz      short loc_1800B3C85
0x1800b3c72  mov     rax, [rcx]
0x1800b3c75  mov     rax, [rax+10h]
0x1800b3c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3c7e  mov     [rdi+158h], rbp
0x1800b3c85  cmp     [rdi+164h], ebp
0x1800b3c8b  jz      loc_1800B3D19
0x1800b3c91  mov     rcx, [rdi+168h]
0x1800b3c98  mov     rax, [rcx]
0x1800b3c9b  mov     rax, [rax+10h]
0x1800b3c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3ca4  mov     rcx, [rdi+170h]
0x1800b3cab  mov     [rdi+168h], rbp
0x1800b3cb2  mov     rax, [rcx]
0x1800b3cb5  mov     rax, [rax+10h]
0x1800b3cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3cbe  mov     rcx, [rdi+178h]
0x1800b3cc5  mov     [rdi+170h], rbp
0x1800b3ccc  mov     rax, [rcx]
0x1800b3ccf  mov     rax, [rax+10h]
0x1800b3cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3cd8  mov     rcx, [rdi+180h]
0x1800b3cdf  mov     [rdi+178h], rbp
0x1800b3ce6  mov     rax, [rcx]
0x1800b3ce9  mov     rax, [rax+10h]
0x1800b3ced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3cf2  mov     rcx, [rdi+188h]
0x1800b3cf9  mov     [rdi+180h], rbp
0x1800b3d00  mov     rax, [rcx]
0x1800b3d03  mov     rax, [rax+10h]
0x1800b3d07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3d0c  mov     [rdi+188h], rbp
0x1800b3d13  mov     [rdi+164h], ebp
0x1800b3d19  mov     [rdi+44h], rbp
0x1800b3d1d  mov     [rdi+60h], ebp
0x1800b3d20  mov     [rdi+24h], ebp
0x1800b3d23  mov     [rdi+654h], bp
0x1800b3d2a  mov     [rdi+710h], ebp
0x1800b3d30  mov     [rdi+658h], ebp
0x1800b3d36  mov     [rdi+259h], bp
0x1800b3d3d  mov     rcx, [rdi+68h]; this
0x1800b3d41  mov     [rdi+24Ch], bpl
0x1800b3d48  mov     [rdi+1FCh], ebp
0x1800b3d4e  mov     [rdi+3B9h], bpl
0x1800b3d55  test    rcx, rcx
0x1800b3d58  jz      short loc_1800B3DC2
0x1800b3d5a  call    ??_GCScriptGenerate@@QEAAPEAXI@Z; CScriptGenerate::`scalar deleting destructor'(uint)
0x1800b3d5f  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x1800b3d66  mov     [rdi+68h], rbp
0x1800b3d6a  jnz     short loc_1800B3DA6
0x1800b3d6c  mov     dl, 1; bool
0x1800b3d6e  lea     rcx, [rsp+98h+arg_0]; this
0x1800b3d76  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x1800b3d7b  mov     rcx, [rdi+1B0h]
0x1800b3d82  mov     rax, [rcx]
0x1800b3d85  mov     rax, [rax+50h]
0x1800b3d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3d8e  mov     rcx, rax; lpFileName
0x1800b3d91  call    cs:__imp_DeleteFileW
0x1800b3d97  lea     rcx, [rsp+98h+arg_0]; this
0x1800b3d9f  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x1800b3da4  jmp     short loc_1800B3DC2
0x1800b3da6  mov     rcx, [rdi+1B0h]
0x1800b3dad  mov     rax, [rcx]
0x1800b3db0  mov     rax, [rax+50h]
0x1800b3db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3db9  mov     rcx, rax; lpFileName
0x1800b3dbc  call    cs:__imp_DeleteFileW
0x1800b3dc2  mov     rcx, [rdi+70h]; this
0x1800b3dc6  test    rcx, rcx
0x1800b3dc9  jz      short loc_1800B3DD4
0x1800b3dcb  call    ??_GCScriptGenerate@@QEAAPEAXI@Z; CScriptGenerate::`scalar deleting destructor'(uint)
0x1800b3dd0  mov     [rdi+70h], rbp
0x1800b3dd4  mov     rcx, [rdi+1B0h]
0x1800b3ddb  mov     [rdi+1E0h], ebp
0x1800b3de1  test    rcx, rcx
0x1800b3de4  jz      short loc_1800B3DF9
0x1800b3de6  mov     rax, [rcx]
0x1800b3de9  mov     rax, [rax+10h]
0x1800b3ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3df2  mov     [rdi+1B0h], rbp
0x1800b3df9  mov     rcx, [rdi+1B8h]
0x1800b3e00  test    rcx, rcx
0x1800b3e03  jz      short loc_1800B3E18
0x1800b3e05  mov     rax, [rcx]
0x1800b3e08  mov     rax, [rax+10h]
0x1800b3e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3e11  mov     [rdi+1B8h], rbp
0x1800b3e18  mov     rcx, [rdi+878h]
0x1800b3e1f  test    rcx, rcx
0x1800b3e22  jz      short loc_1800B3E37
0x1800b3e24  mov     rax, [rcx]
0x1800b3e27  mov     rax, [rax+10h]
0x1800b3e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3e30  mov     [rdi+878h], rbp
0x1800b3e37  mov     rcx, [rdi+880h]
0x1800b3e3e  test    rcx, rcx
0x1800b3e41  jz      short loc_1800B3E56
0x1800b3e43  mov     rax, [rcx]
0x1800b3e46  mov     rax, [rax+10h]
0x1800b3e4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3e4f  mov     [rdi+880h], rbp
0x1800b3e56  mov     rcx, [rdi+320h]
0x1800b3e5d  test    rcx, rcx
0x1800b3e60  jz      short loc_1800B3E75
0x1800b3e62  mov     rax, [rcx]
0x1800b3e65  mov     rax, [rax+10h]
0x1800b3e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3e6e  mov     [rdi+320h], rbp
0x1800b3e75  mov     rcx, [rdi+328h]
0x1800b3e7c  test    rcx, rcx
0x1800b3e7f  jz      short loc_1800B3E94
0x1800b3e81  mov     rax, [rcx]
0x1800b3e84  mov     rax, [rax+10h]
0x1800b3e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3e8d  mov     [rdi+328h], rbp
0x1800b3e94  mov     rcx, [rdi+350h]
0x1800b3e9b  test    rcx, rcx
0x1800b3e9e  jz      short loc_1800B3EB3
0x1800b3ea0  mov     rax, [rcx]
0x1800b3ea3  mov     rax, [rax+10h]
0x1800b3ea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3eac  mov     [rdi+350h], rbp
0x1800b3eb3  mov     rcx, [rdi+358h]
0x1800b3eba  test    rcx, rcx
0x1800b3ebd  jz      short loc_1800B3ED2
0x1800b3ebf  mov     rax, [rcx]
0x1800b3ec2  mov     rax, [rax+10h]
0x1800b3ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3ecb  mov     [rdi+358h], rbp
0x1800b3ed2  mov     rcx, [rdi+3D0h]
0x1800b3ed9  test    rcx, rcx
0x1800b3edc  jz      short loc_1800B3EF1
0x1800b3ede  mov     rax, [rcx]
0x1800b3ee1  mov     rax, [rax+10h]
0x1800b3ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3eea  mov     [rdi+3D0h], rbp
0x1800b3ef1  mov     rcx, [rdi+3D8h]
0x1800b3ef8  test    rcx, rcx
0x1800b3efb  jz      short loc_1800B3F10
0x1800b3efd  mov     rax, [rcx]
0x1800b3f00  mov     rax, [rax+10h]
0x1800b3f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3f09  mov     [rdi+3D8h], rbp
0x1800b3f10  mov     rcx, [rdi+3F0h]
0x1800b3f17  test    rcx, rcx
0x1800b3f1a  jz      short loc_1800B3F2F
0x1800b3f1c  mov     rax, [rcx]
0x1800b3f1f  mov     rax, [rax+10h]
0x1800b3f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3f28  mov     [rdi+3F0h], rbp
0x1800b3f2f  mov     rcx, [rdi+3F8h]
0x1800b3f36  test    rcx, rcx
0x1800b3f39  jz      short loc_1800B3F4E
0x1800b3f3b  mov     rax, [rcx]
0x1800b3f3e  mov     rax, [rax+10h]
0x1800b3f42  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```

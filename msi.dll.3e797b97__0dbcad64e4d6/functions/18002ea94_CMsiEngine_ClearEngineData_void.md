# CMsiEngine::ClearEngineData(void)

- ea: `0x18002ea94`
- end: `0x18002f5f6`
- name: `?ClearEngineData@CMsiEngine@@IEAAXXZ`
- size: `2914`
- prototype: `void __fastcall(CMsiEngine *__hidden this)`
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18002f750`
- `0x180181170`

## callees

- `0x18000c4bc`
- `0x18000d270`
- `0x180014528`
- `0x180019cc0`
- `0x18002ea94`
- `0x180067fec`
- `0x1800d92c4`
- `0x18011c610`
- `0x18011c870`
- `0x18011ccc4`
- `0x18011cefc`
- `0x18011cf64`
- `0x180178a80`
- `0x180178ad0`
- `0x180178afc`
- `0x180178b24`
- `0x180178b4c`
- `0x1801854e0`
- `0x180209120`
- `0x18020a054`
- `0x180266010`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x18002ee21`
- `KERNEL32!DeleteFileW` at `0x18002ee52`
- `KERNEL32!DeleteFileW` at `0x18002f3e2`
- `KERNEL32!DeleteFileW` at `0x18002f4b9`
- `KERNEL32!DeleteFileW` at `0x18002ee21`
- `KERNEL32!DeleteFileW` at `0x18002ee52`
- `KERNEL32!DeleteFileW` at `0x18002f3e2`
- `KERNEL32!DeleteFileW` at `0x18002f4b9`
- `KERNEL32!GetLastError` at `0x18002f3fa`
- `KERNEL32!GetLastError` at `0x18002f4d9`
- `KERNEL32!GetLastError` at `0x18002f3fa`
- `KERNEL32!GetLastError` at `0x18002f4d9`

## string_xrefs

- `0x18002f39a`: `Attempting to delete file %s`
- `0x18002f471`: `Attempting to delete file %s`
- `0x18002f40b`: `Unable to delete the file. LastError = %d`
- `0x18002f4ea`: `Unable to delete the file. LastError = %d`

## pseudocode

```c
void __fastcall CMsiEngine::ClearEngineData(CMsiEngine *this, unsigned int a2)
{
  LPCWSTR v3; // rcx
  CMsiEmbeddedUIManager *v4; // rcx
  CMsiBaselineManager *v5; // rcx
  CMsiSecureRepairManager *v6; // rcx
  CMsiPatchManager *v7; // rcx
  __int64 i; // rbx
  __int64 v9; // rcx
  __int64 v10; // rcx
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
  CScriptGenerate *v25; // rcx
  bool v26; // zf
  const WCHAR *v27; // rax
  const WCHAR *v28; // rax
  CScriptGenerate *v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
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
  unsigned int j; // ebx
  __int64 v55; // rcx
  unsigned int k; // ebx
  __int64 v57; // rcx
  MSIHANDLE v58; // ecx
  __int64 v59; // rcx
  void (__fastcall ***v60)(_QWORD, __int64); // rcx
  _QWORD *v61; // rsi
  __int64 v62; // rbx
  const unsigned __int16 *v63; // rax
  const WCHAR *v64; // rax
  DWORD LastError; // eax
  const unsigned __int16 *v66; // rax
  const WCHAR *v67; // rax
  DWORD v68; // eax
  CWin64DualFolders *v69; // rcx
  char v70; // [rsp+A0h] [rbp+8h] BYREF

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
    CMsiEmbeddedUIManager::CleanupTempDirectory(v4);
    if ( g_pEmbeddedUI )
      CMsiEmbeddedUIManager::`scalar deleting destructor'((CMsiEmbeddedUIManager *)g_pEmbeddedUI, a2);
    g_pEmbeddedUI = 0;
  }
LABEL_13:
  v5 = (CMsiBaselineManager *)*((_QWORD *)this + 116);
  if ( v5 )
  {
    CMsiBaselineManager::`scalar deleting destructor'(v5, a2);
    *((_QWORD *)this + 116) = 0;
  }
  v6 = (CMsiSecureRepairManager *)*((_QWORD *)this + 276);
  if ( v6 )
  {
    CMsiSecureRepairManager::`scalar deleting destructor'(v6, a2);
    *((_QWORD *)this + 276) = 0;
  }
  v7 = (CMsiPatchManager *)*((_QWORD *)this + 117);
  if ( v7 )
  {
    CMsiPatchManager::`scalar deleting destructor'(v7, a2);
    *((_QWORD *)this + 117) = 0;
  }
  for ( i = 0; i != 16; ++i )
  {
    v9 = *((_QWORD *)this + i + 26);
    if ( v9 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      *((_QWORD *)this + i + 26) = 0;
    }
  }
  v10 = *((_QWORD *)this + 52);
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    *((_QWORD *)this + 52) = 0;
  }
  v11 = *((_QWORD *)this + 53);
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    *((_QWORD *)this + 53) = 0;
  }
  v12 = *((_QWORD *)this + 23);
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    *((_QWORD *)this + 23) = 0;
  }
  v13 = *((_QWORD *)this + 24);
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    *((_QWORD *)this + 24) = 0;
  }
  v14 = *((_QWORD *)this + 25);
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    *((_QWORD *)this + 25) = 0;
  }
  v15 = *((_QWORD *)this + 112);
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    *((_QWORD *)this + 112) = 0;
  }
  v16 = *((_QWORD *)this + 113);
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    *((_QWORD *)this + 113) = 0;
  }
  v17 = *((_QWORD *)this + 84);
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    *((_QWORD *)this + 84) = 0;
  }
  v18 = *((_QWORD *)this + 85);
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    *((_QWORD *)this + 85) = 0;
  }
  v19 = *((_QWORD *)this + 42);
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    *((_QWORD *)this + 42) = 0;
  }
  v20 = *((_QWORD *)this + 43);
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    *((_QWORD *)this + 43) = 0;
  }
  if ( *((_DWORD *)this + 89) )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 45) + 16LL))(*((_QWORD *)this + 45));
    v21 = *((_QWORD *)this + 46);
    *((_QWORD *)this + 45) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v22 = *((_QWORD *)this + 47);
    *((_QWORD *)this + 46) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v23 = *((_QWORD *)this + 48);
    *((_QWORD *)this + 47) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v24 = *((_QWORD *)this + 49);
    *((_QWORD *)this + 48) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
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
  v25 = (CScriptGenerate *)*((_QWORD *)this + 13);
  *((_BYTE *)this + 588) = 0;
  *((_DWORD *)this + 127) = 0;
  *((_BYTE *)this + 953) = 0;
  if ( v25 )
  {
    CScriptGenerate::`scalar deleting destructor'(v25, a2);
    v26 = g_scServerContext == 2;
    *((_QWORD *)this + 13) = 0;
    if ( v26 )
    {
      CElevate::CElevate((CElevate *)&v70, 1);
      v27 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 54) + 80LL))(*((_QWORD *)this + 54));
      DeleteFileW(v27);
      CElevate::~CElevate((CElevate *)&v70);
    }
    else
    {
      v28 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 54) + 80LL))(*((_QWORD *)this + 54));
      DeleteFileW(v28);
    }
  }
  v29 = (CScriptGenerate *)*((_QWORD *)this + 14);
  if ( v29 )
  {
    CScriptGenerate::`scalar deleting destructor'(v29, a2);
    *((_QWORD *)this + 14) = 0;
  }
  v30 = *((_QWORD *)this + 54);
  *((_DWORD *)this + 120) = 0;
  if ( v30 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    *((_QWORD *)this + 54) = 0;
  }
  v31 = *((_QWORD *)this + 55);
  if ( v31 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    *((_QWORD *)this + 55) = 0;
  }
  v32 = *((_QWORD *)this + 271);
  if ( v32 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    *((_QWORD *)this + 271) = 0;
  }
  v33 = *((_QWORD *)this + 272);
  if ( v33 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    *((_QWORD *)this + 272) = 0;
  }
  v34 = *((_QWORD *)this + 100);
  if ( v34 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    *((_QWORD *)this + 100) = 0;
  }
  v35 = *((_QWORD *)this + 101);
  if ( v35 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    *((_QWORD *)this + 101) = 0;
  }
  v36 = *((_QWORD *)this + 106);
  if ( v36 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    *((_QWORD *)this + 106) = 0;
  }
  v37 = *((_QWORD *)this + 107);
  if ( v37 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    *((_QWORD *)this + 107) = 0;
  }
  v38 = *((_QWORD *)this + 122);
  if ( v38 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    *((_QWORD *)this + 122) = 0;
  }
  v39 = *((_QWORD *)this + 123);
  if ( v39 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    *((_QWORD *)this + 123) = 0;
  }
  v40 = *((_QWORD *)this + 126);
  if ( v40 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    *((_QWORD *)this + 126) = 0;
  }
  v41 = *((_QWORD *)this + 127);
  if ( v41 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    *((_QWORD *)this + 127) = 0;
  }
  v42 = *((_QWORD *)this + 130);
  if ( v42 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    *((_QWORD *)this + 130) = 0;
  }
  v43 = *((_QWORD *)this + 131);
  if ( v43 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    *((_QWORD *)this + 131) = 0;
  }
  v44 = *((_QWORD *)this + 141);
  if ( v44 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    *((_QWORD *)this + 141) = 0;
  }
  v45 = *((_QWORD *)this + 142);
  if ( v45 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    *((_QWORD *)this + 142) = 0;
  }
  v46 = *((_QWORD *)this + 145);
  if ( v46 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    *((_QWORD *)this + 145) = 0;
  }
  v47 = *((_QWORD *)this + 146);
  if ( v47 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    *((_QWORD *)this + 146) = 0;
  }
  v48 = *((_QWORD *)this + 149);
  if ( v48 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    *((_QWORD *)this + 149) = 0;
  }
  v49 = *((_QWORD *)this + 150);
  if ( v49 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    *((_QWORD *)this + 150) = 0;
  }
  v50 = *((_QWORD *)this + 154);
  if ( v50 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    *((_QWORD *)this + 154) = 0;
  }
  v51 = *((_QWORD *)this + 155);
  if ( v51 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    *((_QWORD *)this + 155) = 0;
  }
  v52 = *((_QWORD *)this + 134);
  if ( v52 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    *((_QWORD *)this + 134) = 0;
  }
  v53 = *((_QWORD *)this + 135);
  if ( v53 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    *((_QWORD *)this + 135) = 0;
  }
  if ( *((_QWORD *)this + 158) )
  {
    for ( j = 0; j < *((_DWORD *)this + 318); ++j )
    {
      v55 = *(_QWORD *)(*((_QWORD *)this + 158) + 8LL * j);
      if ( v55 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
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
      v57 = *(_QWORD *)(*((_QWORD *)this + 157) + 8LL * k);
      if ( v57 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
        *(_QWORD *)(*((_QWORD *)this + 157) + 8LL * k) = 0;
      }
    }
    operator delete(*((void **)this + 157));
    *((_QWORD *)this + 157) = 0;
  }
  if ( g_scServerContext == 2 )
  {
    v58 = *((_DWORD *)this + 25);
    if ( v58 )
    {
      MsiCloseHandle(v58);
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
  v59 = *((_QWORD *)this + 19);
  *((_DWORD *)this + 10) = 0;
  *((_WORD *)this + 744) = 0;
  if ( v59 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
    *((_QWORD *)this + 19) = 0;
  }
  v60 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 269);
  *((_DWORD *)this + 146) = 0;
  *((_DWORD *)this + 148) = -1;
  if ( v60 )
  {
    (**v60)(v60, 1);
    *((_QWORD *)this + 269) = 0;
  }
  *(_OWORD *)((char *)this + 780) = 0;
  *((_BYTE *)this + 2024) = 0;
  *(_OWORD *)((char *)this + 2028) = 0;
  *(_OWORD *)((char *)this + 2044) = 0;
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 120) + 16LL))(*((_QWORD *)this + 120));
  *((_QWORD *)this + 120) = &g_MsiStringNull;
  v61 = (_QWORD *)((char *)this + 1928);
  while ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v61 + 56LL))(*v61) )
  {
    v62 = MsiString::ExtractAndRemove((char *)this + 1928, 2, 59);
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v62 + 56LL))(v62) )
    {
      if ( g_scServerContext == 2 )
      {
        CElevate::CElevate((CElevate *)&v70, 1);
        if ( g_dmDiagnosticMode )
        {
          v63 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v62 + 80LL))(v62);
          DebugString(
            10,
            0,
            0,
            L"Attempting to delete file %s",
            v63,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        }
        v64 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v62 + 80LL))(v62);
        if ( !DeleteFileW(v64) )
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
        CElevate::~CElevate((CElevate *)&v70);
      }
      else
      {
        if ( g_dmDiagnosticMode )
        {
          v66 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v62 + 80LL))(v62);
          DebugString(
            10,
            0,
            0,
            L"Attempting to delete file %s",
            v66,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        }
        v67 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v62 + 80LL))(v62);
        if ( !DeleteFileW(v67) && g_dmDiagnosticMode )
        {
          v68 = GetLastError();
          DebugString(
            10,
            0,
            0,
            L"Unable to delete the file. LastError = %d",
            (const unsigned __int16 *)v68,
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
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
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
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v61 + 16LL))(*v61);
  v26 = g_scServerContext == 2;
  *v61 = &g_MsiStringNull;
  *((_BYTE *)this + 2192) = 1;
  *((_BYTE *)this + 664) = 0;
  if ( !v26 && qword_1803128F0 )
    CWin64DualFolders::Release(v69);
}

```

## disassembly

```asm
0x18002ea94  push    rbx
0x18002ea96  push    rbp
0x18002ea97  push    rsi
0x18002ea98  push    rdi
0x18002ea99  push    r13
0x18002ea9b  push    r14
0x18002ea9d  sub     rsp, 68h
0x18002eaa1  xor     ebp, ebp
0x18002eaa3  mov     rdi, rcx
0x18002eaa6  cmp     cs:?g_scServerContext@@3W4scEnum@@A, ebp; scEnum g_scServerContext
0x18002eaac  jnz     short loc_18002EAE4
0x18002eaae  cmp     [rcx+0B0h], rbp
0x18002eab5  jnz     short loc_18002EAE4
0x18002eab7  mov     rax, [rcx]
0x18002eaba  mov     rax, [rax+1C8h]
0x18002eac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eac6  mov     rcx, cs:?g_pEmbeddedUI@@3PEAVCMsiEmbeddedUIManager@@EA; CMsiEmbeddedUIManager * g_pEmbeddedUI
0x18002eacd  test    rcx, rcx
0x18002ead0  jnz     short loc_18002EAF0
0x18002ead2  mov     rax, [rdi]
0x18002ead5  mov     rcx, rdi
0x18002ead8  mov     rax, [rax+1D0h]
0x18002eadf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eae4  mov     rcx, cs:?g_pEmbeddedUI@@3PEAVCMsiEmbeddedUIManager@@EA; CMsiEmbeddedUIManager * g_pEmbeddedUI
0x18002eaeb  test    rcx, rcx
0x18002eaee  jz      short loc_18002EB4B
0x18002eaf0  cmp     [rcx+444h], bpl
0x18002eaf7  jnz     short loc_18002EB4B
0x18002eaf9  mov     [rcx+440h], ebp
0x18002eaff  add     rcx, 218h; this
0x18002eb06  call    ?ShutdownHandler@MsiMessageHandler@@QEAAKXZ; MsiMessageHandler::ShutdownHandler(void)
0x18002eb0b  cmp     cs:?g_scServerContext@@3W4scEnum@@A, ebp; scEnum g_scServerContext
0x18002eb11  jnz     short loc_18002EB2E
0x18002eb13  cmp     [rdi+0B0h], rbp
0x18002eb1a  jnz     short loc_18002EB2E
0x18002eb1c  mov     rax, [rdi]
0x18002eb1f  mov     rcx, rdi
0x18002eb22  mov     rax, [rax+1D0h]
0x18002eb29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb2e  call    ?CleanupTempDirectory@CMsiEmbeddedUIManager@@QEAAPEAGXZ; CMsiEmbeddedUIManager::CleanupTempDirectory(void)
0x18002eb33  mov     rcx, cs:?g_pEmbeddedUI@@3PEAVCMsiEmbeddedUIManager@@EA; this
0x18002eb3a  test    rcx, rcx
0x18002eb3d  jz      short loc_18002EB44
0x18002eb3f  call    ??_GCMsiEmbeddedUIManager@@QEAAPEAXI@Z; CMsiEmbeddedUIManager::`scalar deleting destructor'(uint)
0x18002eb44  mov     cs:?g_pEmbeddedUI@@3PEAVCMsiEmbeddedUIManager@@EA, rbp; CMsiEmbeddedUIManager * g_pEmbeddedUI
0x18002eb4b  mov     rcx, [rdi+3A0h]; this
0x18002eb52  test    rcx, rcx
0x18002eb55  jz      short loc_18002EB63
0x18002eb57  call    ??_GCMsiBaselineManager@@QEAAPEAXI@Z; CMsiBaselineManager::`scalar deleting destructor'(uint)
0x18002eb5c  mov     [rdi+3A0h], rbp
0x18002eb63  mov     rcx, [rdi+8A0h]; this
0x18002eb6a  test    rcx, rcx
0x18002eb6d  jz      short loc_18002EB7B
0x18002eb6f  call    ??_GCMsiSecureRepairManager@@QEAAPEAXI@Z; CMsiSecureRepairManager::`scalar deleting destructor'(uint)
0x18002eb74  mov     [rdi+8A0h], rbp
0x18002eb7b  mov     rcx, [rdi+3A8h]; this
0x18002eb82  test    rcx, rcx
0x18002eb85  jz      short loc_18002EB93
0x18002eb87  call    ??_GCMsiPatchManager@@QEAAPEAXI@Z; CMsiPatchManager::`scalar deleting destructor'(uint)
0x18002eb8c  mov     [rdi+3A8h], rbp
0x18002eb93  mov     rbx, rbp
0x18002eb96  mov     rcx, [rdi+rbx*8+0D0h]
0x18002eb9e  test    rcx, rcx
0x18002eba1  jz      short loc_18002EBB7
0x18002eba3  mov     rax, [rcx]
0x18002eba6  mov     rax, [rax+10h]
0x18002ebaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebaf  mov     [rdi+rbx*8+0D0h], rbp
0x18002ebb7  inc     rbx
0x18002ebba  cmp     rbx, 10h
0x18002ebbe  jnz     short loc_18002EB96
0x18002ebc0  mov     rcx, [rdi+1A0h]
0x18002ebc7  test    rcx, rcx
0x18002ebca  jz      short loc_18002EBDF
0x18002ebcc  mov     rax, [rcx]
0x18002ebcf  mov     rax, [rax+10h]
0x18002ebd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebd8  mov     [rdi+1A0h], rbp
0x18002ebdf  mov     rcx, [rdi+1A8h]
0x18002ebe6  test    rcx, rcx
0x18002ebe9  jz      short loc_18002EBFE
0x18002ebeb  mov     rax, [rcx]
0x18002ebee  mov     rax, [rax+10h]
0x18002ebf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebf7  mov     [rdi+1A8h], rbp
0x18002ebfe  mov     rcx, [rdi+0B8h]
0x18002ec05  test    rcx, rcx
0x18002ec08  jz      short loc_18002EC1D
0x18002ec0a  mov     rax, [rcx]
0x18002ec0d  mov     rax, [rax+10h]
0x18002ec11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec16  mov     [rdi+0B8h], rbp
0x18002ec1d  mov     rcx, [rdi+0C0h]
0x18002ec24  test    rcx, rcx
0x18002ec27  jz      short loc_18002EC3C
0x18002ec29  mov     rax, [rcx]
0x18002ec2c  mov     rax, [rax+10h]
0x18002ec30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec35  mov     [rdi+0C0h], rbp
0x18002ec3c  mov     rcx, [rdi+0C8h]
0x18002ec43  test    rcx, rcx
0x18002ec46  jz      short loc_18002EC5B
0x18002ec48  mov     rax, [rcx]
0x18002ec4b  mov     rax, [rax+10h]
0x18002ec4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec54  mov     [rdi+0C8h], rbp
0x18002ec5b  mov     rcx, [rdi+380h]
0x18002ec62  test    rcx, rcx
0x18002ec65  jz      short loc_18002EC7A
0x18002ec67  mov     rax, [rcx]
0x18002ec6a  mov     rax, [rax+10h]
0x18002ec6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec73  mov     [rdi+380h], rbp
0x18002ec7a  mov     rcx, [rdi+388h]
0x18002ec81  test    rcx, rcx
0x18002ec84  jz      short loc_18002EC99
0x18002ec86  mov     rax, [rcx]
0x18002ec89  mov     rax, [rax+10h]
0x18002ec8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec92  mov     [rdi+388h], rbp
0x18002ec99  mov     rcx, [rdi+2A0h]
0x18002eca0  test    rcx, rcx
0x18002eca3  jz      short loc_18002ECB8
0x18002eca5  mov     rax, [rcx]
0x18002eca8  mov     rax, [rax+10h]
0x18002ecac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ecb1  mov     [rdi+2A0h], rbp
0x18002ecb8  mov     rcx, [rdi+2A8h]
0x18002ecbf  test    rcx, rcx
0x18002ecc2  jz      short loc_18002ECD7
0x18002ecc4  mov     rax, [rcx]
0x18002ecc7  mov     rax, [rax+10h]
0x18002eccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ecd0  mov     [rdi+2A8h], rbp
0x18002ecd7  mov     rcx, [rdi+150h]
0x18002ecde  test    rcx, rcx
0x18002ece1  jz      short loc_18002ECF6
0x18002ece3  mov     rax, [rcx]
0x18002ece6  mov     rax, [rax+10h]
0x18002ecea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ecef  mov     [rdi+150h], rbp
0x18002ecf6  mov     rcx, [rdi+158h]
0x18002ecfd  test    rcx, rcx
0x18002ed00  jz      short loc_18002ED15
0x18002ed02  mov     rax, [rcx]
0x18002ed05  mov     rax, [rax+10h]
0x18002ed09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed0e  mov     [rdi+158h], rbp
0x18002ed15  cmp     [rdi+164h], ebp
0x18002ed1b  jz      loc_18002EDA9
0x18002ed21  mov     rcx, [rdi+168h]
0x18002ed28  mov     rax, [rcx]
0x18002ed2b  mov     rax, [rax+10h]
0x18002ed2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed34  mov     rcx, [rdi+170h]
0x18002ed3b  mov     [rdi+168h], rbp
0x18002ed42  mov     rax, [rcx]
0x18002ed45  mov     rax, [rax+10h]
0x18002ed49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed4e  mov     rcx, [rdi+178h]
0x18002ed55  mov     [rdi+170h], rbp
0x18002ed5c  mov     rax, [rcx]
0x18002ed5f  mov     rax, [rax+10h]
0x18002ed63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed68  mov     rcx, [rdi+180h]
0x18002ed6f  mov     [rdi+178h], rbp
0x18002ed76  mov     rax, [rcx]
0x18002ed79  mov     rax, [rax+10h]
0x18002ed7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed82  mov     rcx, [rdi+188h]
0x18002ed89  mov     [rdi+180h], rbp
0x18002ed90  mov     rax, [rcx]
0x18002ed93  mov     rax, [rax+10h]
0x18002ed97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed9c  mov     [rdi+188h], rbp
0x18002eda3  mov     [rdi+164h], ebp
0x18002eda9  mov     [rdi+44h], rbp
0x18002edad  mov     [rdi+60h], ebp
0x18002edb0  mov     [rdi+24h], ebp
0x18002edb3  mov     [rdi+654h], bp
0x18002edba  mov     [rdi+710h], ebp
0x18002edc0  mov     [rdi+658h], ebp
0x18002edc6  mov     [rdi+259h], bp
0x18002edcd  mov     rcx, [rdi+68h]; this
0x18002edd1  mov     [rdi+24Ch], bpl
0x18002edd8  mov     [rdi+1FCh], ebp
0x18002edde  mov     [rdi+3B9h], bpl
0x18002ede5  test    rcx, rcx
0x18002ede8  jz      short loc_18002EE5E
0x18002edea  call    ??_GCScriptGenerate@@QEAAPEAXI@Z; CScriptGenerate::`scalar deleting destructor'(uint)
0x18002edef  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x18002edf6  mov     [rdi+68h], rbp
0x18002edfa  jnz     short loc_18002EE3C
0x18002edfc  mov     dl, 1; bool
0x18002edfe  lea     rcx, [rsp+98h+arg_0]; this
0x18002ee06  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x18002ee0b  mov     rcx, [rdi+1B0h]
0x18002ee12  mov     rax, [rcx]
0x18002ee15  mov     rax, [rax+50h]
0x18002ee19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ee1e  mov     rcx, rax; lpFileName
0x18002ee21  call    cs:__imp_DeleteFileW
0x18002ee28  nop     dword ptr [rax+rax+00h]
0x18002ee2d  lea     rcx, [rsp+98h+arg_0]; this
0x18002ee35  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x18002ee3a  jmp     short loc_18002EE5E
0x18002ee3c  mov     rcx, [rdi+1B0h]
0x18002ee43  mov     rax, [rcx]
0x18002ee46  mov     rax, [rax+50h]
0x18002ee4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ee4f  mov     rcx, rax; lpFileName
0x18002ee52  call    cs:__imp_DeleteFileW
0x18002ee59  nop     dword ptr [rax+rax+00h]
0x18002ee5e  mov     rcx, [rdi+70h]; this
0x18002ee62  test    rcx, rcx
0x18002ee65  jz      short loc_18002EE70
0x18002ee67  call    ??_GCScriptGenerate@@QEAAPEAXI@Z; CScriptGenerate::`scalar deleting destructor'(uint)
0x18002ee6c  mov     [rdi+70h], rbp
0x18002ee70  mov     rcx, [rdi+1B0h]
0x18002ee77  mov     [rdi+1E0h], ebp
0x18002ee7d  test    rcx, rcx
0x18002ee80  jz      short loc_18002EE95
0x18002ee82  mov     rax, [rcx]
0x18002ee85  mov     rax, [rax+10h]
0x18002ee89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ee8e  mov     [rdi+1B0h], rbp
0x18002ee95  mov     rcx, [rdi+1B8h]
0x18002ee9c  test    rcx, rcx
0x18002ee9f  jz      short loc_18002EEB4
0x18002eea1  mov     rax, [rcx]
0x18002eea4  mov     rax, [rax+10h]
0x18002eea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eead  mov     [rdi+1B8h], rbp
0x18002eeb4  mov     rcx, [rdi+878h]
0x18002eebb  test    rcx, rcx
0x18002eebe  jz      short loc_18002EED3
0x18002eec0  mov     rax, [rcx]
0x18002eec3  mov     rax, [rax+10h]
0x18002eec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eecc  mov     [rdi+878h], rbp
0x18002eed3  mov     rcx, [rdi+880h]
0x18002eeda  test    rcx, rcx
0x18002eedd  jz      short loc_18002EEF2
0x18002eedf  mov     rax, [rcx]
0x18002eee2  mov     rax, [rax+10h]
0x18002eee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eeeb  mov     [rdi+880h], rbp
0x18002eef2  mov     rcx, [rdi+320h]
0x18002eef9  test    rcx, rcx
0x18002eefc  jz      short loc_18002EF11
0x18002eefe  mov     rax, [rcx]
0x18002ef01  mov     rax, [rax+10h]
0x18002ef05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef0a  mov     [rdi+320h], rbp
0x18002ef11  mov     rcx, [rdi+328h]
0x18002ef18  test    rcx, rcx
0x18002ef1b  jz      short loc_18002EF30
0x18002ef1d  mov     rax, [rcx]
0x18002ef20  mov     rax, [rax+10h]
0x18002ef24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef29  mov     [rdi+328h], rbp
0x18002ef30  mov     rcx, [rdi+350h]
0x18002ef37  test    rcx, rcx
0x18002ef3a  jz      short loc_18002EF4F
0x18002ef3c  mov     rax, [rcx]
0x18002ef3f  mov     rax, [rax+10h]
0x18002ef43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef48  mov     [rdi+350h], rbp
0x18002ef4f  mov     rcx, [rdi+358h]
0x18002ef56  test    rcx, rcx
0x18002ef59  jz      short loc_18002EF6E
0x18002ef5b  mov     rax, [rcx]
0x18002ef5e  mov     rax, [rax+10h]
0x18002ef62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef67  mov     [rdi+358h], rbp
0x18002ef6e  mov     rcx, [rdi+3D0h]
0x18002ef75  test    rcx, rcx
0x18002ef78  jz      short loc_18002EF8D
0x18002ef7a  mov     rax, [rcx]
0x18002ef7d  mov     rax, [rax+10h]
0x18002ef81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef86  mov     [rdi+3D0h], rbp
0x18002ef8d  mov     rcx, [rdi+3D8h]
0x18002ef94  test    rcx, rcx
0x18002ef97  jz      short loc_18002EFAC
0x18002ef99  mov     rax, [rcx]
0x18002ef9c  mov     rax, [rax+10h]
0x18002efa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efa5  mov     [rdi+3D8h], rbp
0x18002efac  mov     rcx, [rdi+3F0h]
0x18002efb3  test    rcx, rcx
0x18002efb6  jz      short loc_18002EFCB
0x18002efb8  mov     rax, [rcx]
0x18002efbb  mov     rax, [rax+10h]
0x18002efbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efc4  mov     [rdi+3F0h], rbp
0x18002efcb  mov     rcx, [rdi+3F8h]
0x18002efd2  test    rcx, rcx
0x18002efd5  jz      short loc_18002EFEA
0x18002efd7  mov     rax, [rcx]
  ... truncated ...
```

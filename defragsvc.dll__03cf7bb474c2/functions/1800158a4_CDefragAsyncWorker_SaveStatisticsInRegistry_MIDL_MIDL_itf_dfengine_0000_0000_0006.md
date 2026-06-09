# CDefragAsyncWorker::_SaveStatisticsInRegistry(__MIDL___MIDL_itf_dfengine_0000_0000_0006)

- ea: `0x1800158a4`
- end: `0x1800164a5`
- name: `?_SaveStatisticsInRegistry@CDefragAsyncWorker@@AEAAJU__MIDL___MIDL_itf_dfengine_0000_0000_0006@@@Z`
- size: `3073`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180027e00`
- `0x180041d18`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x1800149f8`
- `0x1800156a0`
- `0x180015728`
- `0x1800158a4`
- `0x180017e34`
- `0x1800192b4`
- `0x18001a630`
- `0x180067af2`
- `0x180067afe`
- `0x180067b0a`
- `0x180067b30`
- `0x18006a010`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x180015af5`
- `ntdll!RtlGetPersistedStateLocation` at `0x180015af5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015b3b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015cbf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015b3b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015cbf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800160b5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016135`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800160b5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016135`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015cfc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015cfc`

## string_xrefs

- `0x180015ea3`: `DirectoryCount`
- `0x180015ee5`: `FragmentedDirectoryExtents`
- `0x1800158e6`: `CDefragAsyncWorker::_SaveStatisticsInRegistry`
- `0x180015d4c`: `SoRegWriteLCN`
- `0x180016196`: `SoRegWriteLCN`
- `0x180016071`: `SxRegWriteBinary`
- `0x1800160f1`: `SxRegWriteBinary`

## pseudocode

```c
__int64 __fastcall CDefragAsyncWorker::_SaveStatisticsInRegistry(__int64 a1, __int64 a2)
{
  unsigned __int16 *v4; // rbx
  int LastFailureAsHRESULT; // esi
  __int16 v6; // ax
  void *v7; // rax
  __int64 v8; // r12
  __int64 v9; // r13
  int v10; // r15d
  unsigned __int16 *v11; // rdi
  unsigned int v12; // r15d
  __int64 v13; // rdi
  _WORD *v14; // r13
  unsigned int PersistedStateLocation; // eax
  __int64 v17; // r15
  WCHAR *v18; // rdi
  int v19; // eax
  __int64 v20; // r8
  LPCWSTR v21; // rcx
  int v22; // r8d
  WCHAR *v23; // rdi
  LSTATUS v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  HKEY v29; // rbx
  HKEY v30; // rbx
  HKEY v31; // rbx
  HKEY v32; // rbx
  HKEY v33; // rbx
  HKEY v34; // rbx
  HKEY v35; // rbx
  HKEY v36; // rbx
  int v37; // eax
  HKEY v38; // rbx
  int v39; // eax
  HKEY v40; // rbx
  HKEY v41; // rbx
  HKEY v42; // rbx
  HKEY v43; // rbx
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  void *v45; // [rsp+58h] [rbp-A8h]
  int v46; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v47; // [rsp+64h] [rbp-9Ch]
  __int16 v48; // [rsp+66h] [rbp-9Ah]
  LPCWSTR lpSubKey; // [rsp+98h] [rbp-68h] BYREF
  __int64 v50; // [rsp+A0h] [rbp-60h]
  int v51; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v52; // [rsp+ACh] [rbp-54h]
  __int16 v53; // [rsp+AEh] [rbp-52h]
  unsigned int v54; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v55; // [rsp+E4h] [rbp-1Ch] BYREF
  unsigned __int16 *v56; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v57; // [rsp+F0h] [rbp-10h]
  void *Src; // [rsp+F8h] [rbp-8h]
  BYTE Data[16]; // [rsp+100h] [rbp+0h] BYREF
  BYTE v60[16]; // [rsp+110h] [rbp+10h] BYREF
  _WORD v61[264]; // [rsp+120h] [rbp+20h] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v51,
    "CDefragAsyncWorker::_SaveStatisticsInRegistry",
    2073,
    1);
  hKey = 0;
  v4 = (unsigned __int16 *)&qword_18006F470;
  v45 = (void *)&qword_18006F470;
  lpSubKey = &qword_18006F470;
  v50 = 0;
  v56 = (unsigned __int16 *)&qword_18006F470;
  v57 = 0;
  v54 = 0;
  *(_OWORD *)Data = 0;
  *(_OWORD *)v60 = 0;
  v55 = 0;
  memset_0(v61, 0, 0x208u);
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(_QWORD, BYTE *))(**(_QWORD **)(a1 + 200) + 72LL))(
                           *(_QWORD *)(a1 + 200),
                           Data);
  v51 = LastFailureAsHRESULT;
  v6 = 2084;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_19;
  v52 = 2084;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(_QWORD, BYTE *))(**(_QWORD **)(a1 + 200) + 88LL))(
                           *(_QWORD *)(a1 + 200),
                           v60);
  v51 = LastFailureAsHRESULT;
  v6 = 2085;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_19;
  v52 = 2085;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(a1 + 200) + 104LL))(
                           *(_QWORD *)(a1 + 200),
                           &v54);
  v51 = LastFailureAsHRESULT;
  v6 = 2086;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_19;
  v52 = 2086;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(a1 + 200) + 120LL))(
                           *(_QWORD *)(a1 + 200),
                           &v55);
  v51 = LastFailureAsHRESULT;
  v6 = 2087;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_19;
  v52 = 2087;
  v7 = *(void **)(a1 + 208);
  Src = v7;
  if ( !v7 )
  {
    LastFailureAsHRESULT = -2147024809;
    v51 = -2147024809;
    goto LABEL_78;
  }
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( *((_WORD *)v7 + v9) );
  LastFailureAsHRESULT = 0;
  if ( (_DWORD)v9 )
  {
    LastFailureAsHRESULT = CBsString::ExtendBuffer((CBsString *)&v56, (int)v9 + 1);
    v4 = v56;
    v45 = v56;
    if ( LastFailureAsHRESULT >= 0 )
    {
      v10 = v57;
      v11 = &v56[(unsigned int)v57];
      memcpy_0(v11, Src, 2LL * (unsigned int)v9);
      v11[(unsigned int)v9] = 0;
      v12 = v9 + v10;
      v51 = LastFailureAsHRESULT;
      goto LABEL_13;
    }
  }
  v51 = LastFailureAsHRESULT;
  if ( LastFailureAsHRESULT < 0 )
  {
LABEL_78:
    v6 = 2090;
    goto LABEL_19;
  }
  v12 = v57;
LABEL_13:
  v52 = 2090;
  v13 = v12 - 4;
  v14 = v45;
  if ( v12 < 4 )
  {
    LODWORD(v13) = v12;
  }
  else
  {
    memmove_0(v45, (char *)v45 + 2 * (v12 - (unsigned __int64)(unsigned int)v13), 2 * v13);
    *((_WORD *)v45 + v13) = 0;
  }
  if ( (_DWORD)v13 )
    v14[(unsigned int)(v13 - 1)] = 0;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"DfrgStatistics",
                             0,
                             L"SOFTWARE\\Microsoft\\Dfrg\\Statistics",
                             0,
                             v61,
                             260,
                             0);
  LastFailureAsHRESULT = HRESULTFromNTSTATUS(PersistedStateLocation);
  v51 = LastFailureAsHRESULT;
  v6 = 2104;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_18;
  v52 = 2104;
  v17 = -1;
  do
    ++v17;
  while ( v61[v17] );
  LastFailureAsHRESULT = 0;
  if ( (_DWORD)v17 )
  {
    LastFailureAsHRESULT = CBsString::ExtendBuffer((CBsString *)&lpSubKey, (int)v17 + 1);
    if ( LastFailureAsHRESULT >= 0 )
    {
      v18 = (WCHAR *)&lpSubKey[(unsigned int)v50];
      memcpy_0(v18, v61, 2LL * (unsigned int)v17);
      v18[(unsigned int)v17] = 0;
      v19 = v17 + v50;
      LODWORD(v50) = v17 + v50;
      v51 = LastFailureAsHRESULT;
      goto LABEL_30;
    }
  }
  v51 = LastFailureAsHRESULT;
  if ( LastFailureAsHRESULT >= 0 )
  {
    v19 = v50;
LABEL_30:
    v52 = 2106;
    LastFailureAsHRESULT = CBsString::ExtendBuffer((CBsString *)&lpSubKey, v19 + 2);
    if ( LastFailureAsHRESULT < 0 )
    {
      v51 = LastFailureAsHRESULT;
      v6 = 2107;
      goto LABEL_18;
    }
    v20 = (unsigned int)v50;
    v21 = lpSubKey;
    lpSubKey[(unsigned int)v50] = asc_180070370[0];
    v21[v20 + 1] = 0;
    v22 = v20 + 1;
    LODWORD(v50) = v22;
    v51 = LastFailureAsHRESULT;
    v52 = 2107;
    if ( v14 )
    {
      do
        ++v8;
      while ( v14[v8] );
      LastFailureAsHRESULT = 0;
      if ( (_DWORD)v8 )
      {
        LastFailureAsHRESULT = CBsString::ExtendBuffer((CBsString *)&lpSubKey, (int)v8 + v22 + 1);
        if ( LastFailureAsHRESULT >= 0 )
        {
          v23 = (WCHAR *)&lpSubKey[(unsigned int)v50];
          memcpy_0(v23, v14, 2LL * (unsigned int)v8);
          v23[(unsigned int)v8] = 0;
          v51 = LastFailureAsHRESULT;
          goto LABEL_37;
        }
      }
      v51 = LastFailureAsHRESULT;
      if ( LastFailureAsHRESULT >= 0 )
      {
LABEL_37:
        v52 = 2108;
        if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          RegCloseKey(hKey);
          hKey = 0;
        }
        v24 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
        LastFailureAsHRESULT = v24;
        if ( v24 > 0 )
          LastFailureAsHRESULT = (unsigned __int16)v24 | 0x80070000;
        v51 = LastFailureAsHRESULT;
        v6 = 2118;
        if ( LastFailureAsHRESULT >= 0 )
        {
          v52 = 2118;
          v29 = hKey;
          if ( hKey )
          {
            v51 = 0;
            v52 = 2120;
            CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v46, "SoRegWriteLCN", 43, 1);
            v46 = SxRegWriteULONGLONG(v29, L"TotalUsedClusters", *(_QWORD *)(a2 + 80));
            if ( v46 < 0 )
              v48 = 51;
            else
              v47 = 51;
            CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v46);
            v30 = hKey;
            CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v46, "SoRegWriteLCN", 43, 1);
            v46 = SxRegWriteULONGLONG(v30, L"TotalClusters", *(_QWORD *)(a2 + 88));
            if ( v46 < 0 )
              v48 = 51;
            else
              v47 = 51;
            CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v46);
            SxRegWriteDWORD(hKey, L"BytesPerCluster", *(_DWORD *)(a2 + 96));
            SxRegWriteDWORD(hKey, L"FragmentedSpace", *(_DWORD *)a2);
            SxRegWriteDWORD(hKey, L"AvgFragmentsPerFile", *(_DWORD *)(a2 + 28));
            SxRegWriteDWORD(hKey, L"MovableFiles", *(_DWORD *)(a2 + 8));
            SxRegWriteDWORD(hKey, L"UnmovableFiles", *(_DWORD *)(a2 + 4));
            SxRegWriteDWORD(hKey, L"FragmentedFiles", *(_DWORD *)(a2 + 24));
            v31 = hKey;
            CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v46, "SoRegWriteLCN", 43, 1);
            v46 = SxRegWriteULONGLONG(v31, L"FragmentedExtents", *(_QWORD *)(a2 + 16));
            if ( v46 < 0 )
              v48 = 51;
            else
              v47 = 51;
            CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v46);
            SxRegWriteDWORD(hKey, L"DirectoryCount", *(_DWORD *)(a2 + 32));
            SxRegWriteDWORD(hKey, L"FragmentedDirectories", *(_DWORD *)(a2 + 48));
            v32 = hKey;
            CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v46, "SoRegWriteLCN", 43, 1);
            v46 = SxRegWriteULONGLONG(v32, L"FragmentedDirectoryExtents", *(_QWORD *)(a2 + 40));
            if ( v46 < 0 )
              v48 = 51;
            else
              v47 = 51;
            CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v46);
            v33 = hKey;
            CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v46, "SoRegWriteLCN", 43, 1);
            v46 = SxRegWriteULONGLONG(v33, L"FreeSpaceCount", *(_QWORD *)(a2 + 152));
            if ( v46 < 0 )
              v48 = 51;
            else
              v47 = 51;
            CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v46);
            v34 = hKey;
            CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v46, "SoRegWriteLCN", 43, 1);
            v46 = SxRegWriteULONGLONG(v34, L"AvgFreeSpaceSize", *(_QWORD *)(a2 + 160));
            if ( v46 < 0 )
              v48 = 51;
            else
              v47 = 51;
            CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v46);
            v35 = hKey;
            CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v46, "SoRegWriteLCN", 43, 1);
            v46 = SxRegWriteULONGLONG(v35, L"LargestFreeSpaceSize", *(_QWORD *)(a2 + 168));
            if ( v46 < 0 )
              v48 = 51;
            else
              v47 = 51;
            CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v46);
            SxRegWriteULONGLONG(hKey, L"MFTSize", *(_QWORD *)(a2 + 184));
            SxRegWriteDWORD(hKey, L"TotalMFTRecords", *(_DWORD *)(a2 + 196));
            SxRegWriteDWORD(hKey, L"InUseMFTRecords", *(_DWORD *)(a2 + 192));
            SxRegWriteDWORD(hKey, L"MFTFragmentCount", *(_DWORD *)(a2 + 200));
            SxRegWriteDWORD(hKey, L"LastRunPercentFragmentation", v54);
            v36 = hKey;
            CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v46, "SxRegWriteBinary", 548, 1);
            v46 = 0;
            v47 = 551;
            v37 = RegSetValueExW(v36, L"LastRunTime", 0, 3u, Data, 0x10u);
            if ( v37 > 0 )
              v37 = (unsigned __int16)v37 | 0x80070000;
            v46 = v37;
            if ( v37 < 0 )
              v48 = 553;
            else
              v47 = 553;
            CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v46);
            v38 = hKey;
            CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v46, "SxRegWriteBinary", 548, 1);
            v46 = 0;
            v47 = 551;
            v39 = RegSetValueExW(v38, L"LastRunFullDefragTime", 0, 3u, v60, 0x10u);
            if ( v39 > 0 )
              v39 = (unsigned __int16)v39 | 0x80070000;
            v46 = v39;
            if ( v39 < 0 )
              v48 = 553;
            else
              v47 = 553;
            CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v46);
            SxRegWriteDWORD(hKey, L"HardwareIssue", v55);
            SxRegWriteDWORD(hKey, L"TotalSlabs", *(_DWORD *)(a2 + 248));
            v40 = hKey;
            CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v46, "SoRegWriteLCN", 43, 1);
            v46 = SxRegWriteULONGLONG(v40, L"ClustersPerSlab", *(_QWORD *)(a2 + 256));
            if ( v46 < 0 )
              v48 = 51;
            else
              v47 = 51;
            CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v46);
            v41 = hKey;
            CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v46, "SoRegWriteLCN", 43, 1);
            v46 = SxRegWriteULONGLONG(v41, L"AlignmentClusters", *(_QWORD *)(a2 + 264));
            if ( v46 < 0 )
              v48 = 51;
            else
              v47 = 51;
            CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v46);
            SxRegWriteDWORD(hKey, L"InUseSlabs", *(_DWORD *)(a2 + 272));
            SxRegWriteDWORD(hKey, L"LastRunPotentialPurgeSlabs", *(_DWORD *)(a2 + 276));
            SxRegWriteDWORD(hKey, L"LastRunActualPurgeSlabs", *(_DWORD *)(a2 + 280));
            v42 = hKey;
            CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v46, "SoRegWriteLCN", 43, 1);
            v46 = SxRegWriteULONGLONG(v42, L"LastRunActualPurgeClusters", *(_QWORD *)(a2 + 288));
            if ( v46 < 0 )
              v48 = 51;
            else
              v47 = 51;
            CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v46);
            SxRegWriteDWORD(hKey, L"LastRunPinnedSlabs", *(_DWORD *)(a2 + 296));
            SxRegWriteDWORD(hKey, L"LastRunVolsnapPinnedSlabs", *(_DWORD *)(a2 + 300));
            SxRegWriteDWORD(hKey, L"LastRunInitialBackedSlabs", *(_DWORD *)(a2 + 304));
            SxRegWriteDWORD(hKey, L"LastRunTrimmedSlabs", *(_DWORD *)(a2 + 308));
            SxRegWriteDWORD(hKey, L"LastRunUnknownEvictFailSlabs", *(_DWORD *)(a2 + 312));
            SxRegWriteDWORD(hKey, L"LastRunSpaceInefficientSlabs", *(_DWORD *)(a2 + 316));
            v43 = hKey;
            CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v46, "SoRegWriteLCN", 43, 1);
            v46 = SxRegWriteULONGLONG(v43, L"LastRunClustersTrimmed", *(_QWORD *)(a2 + 320));
            if ( v46 < 0 )
              v48 = 51;
            else
              v47 = 51;
            CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v46);
            LastFailureAsHRESULT = v51;
            goto LABEL_74;
          }
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v26, v25, v27, v28);
          v51 = LastFailureAsHRESULT;
          v6 = 2120;
        }
LABEL_18:
        v4 = (unsigned __int16 *)v45;
LABEL_19:
        v53 = v6;
        goto LABEL_20;
      }
    }
    else
    {
      LastFailureAsHRESULT = -2147024809;
      v51 = -2147024809;
    }
    v6 = 2108;
    goto LABEL_18;
  }
  v53 = 2106;
LABEL_74:
  v4 = (unsigned __int16 *)v45;
LABEL_20:
  CBsString::_FreeData(v4);
  CBsString::_FreeData((unsigned __int16 *)lpSubKey);
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v51);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x1800158a4  mov     [rsp-8+arg_10], rbx
0x1800158a9  push    rbp
0x1800158aa  push    rsi
0x1800158ab  push    rdi
0x1800158ac  push    r12
0x1800158ae  push    r13
0x1800158b0  push    r14
0x1800158b2  push    r15
0x1800158b4  lea     rbp, [rsp-240h]
0x1800158bc  sub     rsp, 340h
0x1800158c3  mov     rax, cs:__security_cookie
0x1800158ca  xor     rax, rsp
0x1800158cd  mov     [rbp+270h+var_40], rax
0x1800158d4  mov     r14, rdx
0x1800158d7  mov     rdi, rcx
0x1800158da  mov     r9d, 1; unsigned __int16
0x1800158e0  mov     r8d, 819h; unsigned __int16
0x1800158e6  lea     rdx, aCdefragasyncwo_4; "CDefragAsyncWorker::_SaveStatisticsInRe"...
0x1800158ed  lea     rcx, [rbp+270h+var_2C8]; this
0x1800158f1  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800158f6  nop
0x1800158f7  xor     r15d, r15d
0x1800158fa  mov     [rsp+370h+hKey], r15
0x1800158ff  lea     rbx, qword_18006F470
0x180015906  mov     [rsp+370h+var_318], rbx
0x18001590b  mov     [rbp+270h+lpSubKey], rbx
0x18001590f  mov     [rbp+270h+var_2D0], r15
0x180015913  mov     [rbp+270h+var_288], rbx
0x180015917  mov     [rbp+270h+var_280], r15
0x18001591b  mov     [rbp+270h+var_290], r15d
0x18001591f  xorps   xmm0, xmm0
0x180015922  movups  xmmword ptr [rbp+270h+Data], xmm0
0x180015926  xorps   xmm1, xmm1
0x180015929  movups  xmmword ptr [rbp+270h+var_260], xmm1
0x18001592d  mov     [rbp+270h+var_28C], r15d
0x180015931  xor     edx, edx; Val
0x180015933  mov     r8d, 208h; Size
0x180015939  lea     rcx, [rbp+270h+var_250]; void *
0x18001593d  call    memset_0
0x180015942  mov     rcx, [rdi+0C8h]
0x180015949  mov     rax, [rcx]
0x18001594c  lea     rdx, [rbp+270h+Data]
0x180015950  mov     rax, [rax+48h]
0x180015954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015959  mov     esi, eax
0x18001595b  mov     [rbp+270h+var_2C8], eax
0x18001595e  test    eax, eax
0x180015960  mov     eax, 824h
0x180015965  js      loc_180015B15
0x18001596b  mov     [rbp+270h+var_2C4], ax
0x18001596f  mov     rcx, [rdi+0C8h]
0x180015976  mov     rax, [rcx]
0x180015979  lea     rdx, [rbp+270h+var_260]
0x18001597d  mov     rax, [rax+58h]
0x180015981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015986  mov     esi, eax
0x180015988  mov     [rbp+270h+var_2C8], eax
0x18001598b  test    eax, eax
0x18001598d  mov     eax, 825h
0x180015992  js      loc_180015B15
0x180015998  mov     [rbp+270h+var_2C4], ax
0x18001599c  mov     rcx, [rdi+0C8h]
0x1800159a3  mov     rax, [rcx]
0x1800159a6  lea     rdx, [rbp+270h+var_290]
0x1800159aa  mov     rax, [rax+68h]
0x1800159ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159b3  mov     esi, eax
0x1800159b5  mov     [rbp+270h+var_2C8], eax
0x1800159b8  test    eax, eax
0x1800159ba  mov     eax, 826h
0x1800159bf  js      loc_180015B15
0x1800159c5  mov     [rbp+270h+var_2C4], ax
0x1800159c9  mov     rcx, [rdi+0C8h]
0x1800159d0  mov     rax, [rcx]
0x1800159d3  lea     rdx, [rbp+270h+var_28C]
0x1800159d7  mov     rax, [rax+78h]
0x1800159db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159e0  mov     esi, eax
0x1800159e2  mov     [rbp+270h+var_2C8], eax
0x1800159e5  test    eax, eax
0x1800159e7  mov     eax, 827h
0x1800159ec  js      loc_180015B15
0x1800159f2  mov     [rbp+270h+var_2C4], ax
0x1800159f6  mov     rax, [rdi+0D0h]
0x1800159fd  mov     [rbp+270h+Src], rax
0x180015a01  test    rax, rax
0x180015a04  jz      loc_1800163E6
0x180015a0a  or      r12, 0FFFFFFFFFFFFFFFFh
0x180015a0e  mov     r13, r12
0x180015a11  inc     r13
0x180015a14  cmp     [rax+r13*2], r15w
0x180015a19  jnz     short loc_180015A11
0x180015a1b  mov     esi, r15d
0x180015a1e  test    r13d, r13d
0x180015a21  jz      short loc_180015A6B
0x180015a23  lea     edx, [r13+1]; unsigned int
0x180015a27  lea     rcx, [rbp+270h+var_288]; this
0x180015a2b  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x180015a30  mov     esi, eax
0x180015a32  mov     rbx, [rbp+270h+var_288]
0x180015a36  mov     [rsp+370h+var_318], rbx
0x180015a3b  test    eax, eax
0x180015a3d  js      short loc_180015A6B
0x180015a3f  mov     r15d, dword ptr [rbp+270h+var_280]
0x180015a43  lea     rdi, [rbx+r15*2]
0x180015a47  mov     eax, r13d
0x180015a4a  lea     rbx, [rax+rax]
0x180015a4e  mov     r8, rbx; Size
0x180015a51  mov     rdx, [rbp+270h+Src]; Src
0x180015a55  mov     rcx, rdi; void *
0x180015a58  call    memcpy_0
0x180015a5d  xor     eax, eax
0x180015a5f  mov     [rbx+rdi], ax
0x180015a63  add     r15d, r13d
0x180015a66  mov     [rbp+270h+var_2C8], esi
0x180015a69  jmp     short loc_180015A7A
0x180015a6b  mov     [rbp+270h+var_2C8], esi
0x180015a6e  test    esi, esi
0x180015a70  js      loc_1800163EE
0x180015a76  mov     r15d, dword ptr [rbp+270h+var_280]
0x180015a7a  mov     eax, 82Ah
0x180015a7f  mov     [rbp+270h+var_2C4], ax
0x180015a83  lea     edi, [r15-4]
0x180015a87  mov     r13, [rsp+370h+var_318]
0x180015a8c  cmp     edi, r15d
0x180015a8f  jnb     loc_1800163B3
0x180015a95  mov     ecx, edi
0x180015a97  lea     rbx, [rdi+rdi]
0x180015a9b  mov     eax, r15d
0x180015a9e  sub     rax, rcx
0x180015aa1  lea     rdx, ds:0[rax*2]
0x180015aa9  add     rdx, r13; Src
0x180015aac  mov     r8, rbx; Size
0x180015aaf  mov     rcx, r13; void *
0x180015ab2  call    memmove_0
0x180015ab7  xor     r15d, r15d
0x180015aba  mov     [rbx+r13], r15w
0x180015abf  lea     eax, [rdi-1]
0x180015ac2  cmp     eax, edi
0x180015ac4  jnb     short loc_180015ACC
0x180015ac6  mov     [r13+rax*2+0], r15w
0x180015acc  mov     [rsp+370h+lpSecurityAttributes], r15
0x180015ad1  mov     [rsp+370h+samDesired], 104h
0x180015ad9  lea     rax, [rbp+270h+var_250]
0x180015add  mov     qword ptr [rsp+370h+dwOptions], rax
0x180015ae2  xor     r9d, r9d
0x180015ae5  lea     r8, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Dfrg\\Statistics"
0x180015aec  xor     edx, edx
0x180015aee  lea     rcx, aDfrgstatistics; "DfrgStatistics"
0x180015af5  call    cs:__imp_RtlGetPersistedStateLocation
0x180015afb  mov     ecx, eax
0x180015afd  call    HRESULTFromNTSTATUS
0x180015b02  mov     esi, eax
0x180015b04  mov     [rbp+270h+var_2C8], eax
0x180015b07  test    eax, eax
0x180015b09  mov     eax, 838h
0x180015b0e  jns     short loc_180015B7B
0x180015b10  mov     rbx, [rsp+370h+var_318]
0x180015b15  mov     [rbp+270h+var_2C2], ax
0x180015b19  mov     rcx, rbx; unsigned __int16 *
0x180015b1c  call    ?_FreeData@CBsString@@CAXPEAGK@Z; CBsString::_FreeData(ushort *,ulong)
0x180015b21  nop
0x180015b22  mov     rcx, [rbp+270h+lpSubKey]; unsigned __int16 *
0x180015b26  call    ?_FreeData@CBsString@@CAXPEAGK@Z; CBsString::_FreeData(ushort *,ulong)
0x180015b2b  nop
0x180015b2c  mov     rcx, [rsp+370h+hKey]; hKey
0x180015b31  lea     rdx, [rcx-1]
0x180015b35  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180015b39  ja      short loc_180015B46
0x180015b3b  call    cs:__imp_RegCloseKey
0x180015b41  mov     [rsp+370h+hKey], r15
0x180015b46  lea     rcx, [rbp+270h+var_2C8]; this
0x180015b4a  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180015b4f  mov     eax, esi
0x180015b51  mov     rcx, [rbp+270h+var_40]
0x180015b58  xor     rcx, rsp; StackCookie
0x180015b5b  call    __security_check_cookie
0x180015b60  mov     rbx, [rsp+370h+arg_10]
0x180015b68  add     rsp, 340h
0x180015b6f  pop     r15
0x180015b71  pop     r14
0x180015b73  pop     r13
0x180015b75  pop     r12
0x180015b77  pop     rdi
0x180015b78  pop     rsi
0x180015b79  pop     rbp
0x180015b7a  retn
0x180015b7b  mov     [rbp+270h+var_2C4], ax
0x180015b7f  lea     rax, [rbp+270h+var_250]
0x180015b83  mov     r15, r12
0x180015b86  xor     ebx, ebx
0x180015b88  inc     r15
0x180015b8b  cmp     [rax+r15*2], bx
0x180015b90  jnz     short loc_180015B88
0x180015b92  mov     esi, ebx
0x180015b94  test    r15d, r15d
0x180015b97  jz      short loc_180015BE4
0x180015b99  lea     edx, [r15+1]; unsigned int
0x180015b9d  lea     rcx, [rbp+270h+lpSubKey]; this
0x180015ba1  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x180015ba6  mov     esi, eax
0x180015ba8  test    eax, eax
0x180015baa  js      short loc_180015BE4
0x180015bac  mov     ecx, dword ptr [rbp+270h+var_2D0]
0x180015baf  mov     rax, [rbp+270h+lpSubKey]
0x180015bb3  lea     rdi, [rax+rcx*2]
0x180015bb7  mov     eax, r15d
0x180015bba  lea     rbx, [rax+rax]
0x180015bbe  mov     r8, rbx; Size
0x180015bc1  lea     rdx, [rbp+270h+var_250]; Src
0x180015bc5  mov     rcx, rdi; void *
0x180015bc8  call    memcpy_0
0x180015bcd  xor     eax, eax
0x180015bcf  mov     [rbx+rdi], ax
0x180015bd3  mov     eax, dword ptr [rbp+270h+var_2D0]
0x180015bd6  add     eax, r15d
0x180015bd9  mov     dword ptr [rbp+270h+var_2D0], eax
0x180015bdc  mov     [rbp+270h+var_2C8], esi
0x180015bdf  xor     r15d, r15d
0x180015be2  jmp     short loc_180015BF5
0x180015be4  mov     [rbp+270h+var_2C8], esi
0x180015be7  xor     r15d, r15d
0x180015bea  test    esi, esi
0x180015bec  js      loc_1800163F8
0x180015bf2  mov     eax, dword ptr [rbp+270h+var_2D0]
0x180015bf5  mov     ecx, 83Ah
0x180015bfa  mov     [rbp+270h+var_2C4], cx
0x180015bfe  lea     edx, [rax+2]; unsigned int
0x180015c01  lea     rcx, [rbp+270h+lpSubKey]; this
0x180015c05  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x180015c0a  mov     esi, eax
0x180015c0c  test    eax, eax
0x180015c0e  js      loc_180016497
0x180015c14  mov     r8d, dword ptr [rbp+270h+var_2D0]
0x180015c18  mov     rcx, [rbp+270h+lpSubKey]
0x180015c1c  mov     eax, dword ptr cs:asc_180070370; "\\"
0x180015c22  mov     [rcx+r8*2], ax
0x180015c27  mov     [rcx+r8*2+2], r15w
0x180015c2d  inc     r8d
0x180015c30  mov     dword ptr [rbp+270h+var_2D0], r8d
0x180015c34  mov     [rbp+270h+var_2C8], esi
0x180015c37  mov     eax, 83Bh
0x180015c3c  mov     [rbp+270h+var_2C4], ax
0x180015c40  test    r13, r13
0x180015c43  jz      loc_180016403
0x180015c49  inc     r12
0x180015c4c  cmp     [r13+r12*2+0], r15w
0x180015c52  jnz     short loc_180015C49
0x180015c54  mov     esi, r15d
0x180015c57  test    r12d, r12d
0x180015c5a  jz      short loc_180015C9C
0x180015c5c  lea     edx, [r8+1]
0x180015c60  add     edx, r12d; unsigned int
0x180015c63  lea     rcx, [rbp+270h+lpSubKey]; this
0x180015c67  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x180015c6c  mov     esi, eax
0x180015c6e  test    eax, eax
0x180015c70  js      short loc_180015C9C
0x180015c72  mov     ecx, dword ptr [rbp+270h+var_2D0]
0x180015c75  mov     rax, [rbp+270h+lpSubKey]
0x180015c79  lea     rdi, [rax+rcx*2]
0x180015c7d  mov     eax, r12d
0x180015c80  lea     rbx, [rax+rax]
0x180015c84  mov     r8, rbx; Size
0x180015c87  mov     rdx, r13; Src
0x180015c8a  mov     rcx, rdi; void *
0x180015c8d  call    memcpy_0
0x180015c92  mov     [rbx+rdi], r15w
0x180015c97  mov     [rbp+270h+var_2C8], esi
0x180015c9a  jmp     short loc_180015CA7
0x180015c9c  mov     [rbp+270h+var_2C8], esi
0x180015c9f  test    esi, esi
0x180015ca1  js      loc_18001640B
0x180015ca7  mov     eax, 83Ch
0x180015cac  mov     [rbp+270h+var_2C4], ax
0x180015cb0  mov     rcx, [rsp+370h+hKey]; hKey
0x180015cb5  lea     rax, [rcx-1]
0x180015cb9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180015cbd  ja      short loc_180015CCA
0x180015cbf  call    cs:__imp_RegCloseKey
0x180015cc5  mov     [rsp+370h+hKey], r15
0x180015cca  mov     [rsp+370h+lpdwDisposition], r15; lpdwDisposition
0x180015ccf  lea     rax, [rsp+370h+hKey]
0x180015cd4  mov     [rsp+370h+phkResult], rax; phkResult
0x180015cd9  mov     [rsp+370h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180015cde  mov     [rsp+370h+samDesired], 2001Fh; samDesired
0x180015ce6  mov     [rsp+370h+dwOptions], r15d; dwOptions
0x180015ceb  xor     r9d, r9d; lpClass
0x180015cee  xor     r8d, r8d; Reserved
0x180015cf1  mov     rdx, [rbp+270h+lpSubKey]; lpSubKey
0x180015cf5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015cfc  call    cs:__imp_RegCreateKeyExW
0x180015d02  mov     esi, eax
0x180015d04  test    eax, eax
0x180015d06  jg      loc_1800163BE
0x180015d0c  mov     [rbp+270h+var_2C8], esi
0x180015d0f  mov     eax, 846h
0x180015d14  test    esi, esi
0x180015d16  js      loc_180015B10
0x180015d1c  mov     [rbp+270h+var_2C4], ax
  ... truncated ...
```

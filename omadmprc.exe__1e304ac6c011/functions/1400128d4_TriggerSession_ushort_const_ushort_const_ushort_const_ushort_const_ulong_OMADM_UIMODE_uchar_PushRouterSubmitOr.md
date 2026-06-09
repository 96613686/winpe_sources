# TriggerSession(ushort const *,ushort const *,ushort const *,ushort const *,ulong,OMADM_UIMODE,uchar,PushRouterSubmitOrigin,long *)

- ea: `0x1400128d4`
- end: `0x14001334a`
- name: `?TriggerSession@@YAJPEBG000KW4OMADM_UIMODE@@EW4PushRouterSubmitOrigin@@PEAJ@Z`
- size: `2678`
- prototype: ``
- caller_count: `3`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14000fff0`
- `0x1400112f4`
- `0x140011468`

## callees

- `0x140001090`
- `0x140002aa0`
- `0x14000812c`
- `0x14000b708`
- `0x14000c328`
- `0x14000f250`
- `0x14000f964`
- `0x140010f44`
- `0x140012388`
- `0x1400124a8`
- `0x140012604`
- `0x1400128d4`
- `0x1400141a0`
- `0x140014620`
- `0x1400147f0`
- `0x140015690`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x140013170`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x140013170`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400129cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012bba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012c59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012cfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012dcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012f9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400130da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013180`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400129cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012bba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012c59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012cfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012dcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012f9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400130da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013180`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400129ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140012bd9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140012c78`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140012d1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140012dec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140012fbe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400129ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140012bd9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140012c78`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140012d1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140012dec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140012fbe`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400130ca`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400130ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012fb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400132f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012fb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400132f0`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1400131b5`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1400131b5`
- `DMCmnUtils!DmRunTask` at `0x140012ff7`
- `DMCmnUtils!DmRunTask` at `0x140012ff7`
- `DMCmnUtils!OmaDmRegistrySetString` at `0x140012ada`
- `DMCmnUtils!OmaDmRegistrySetString` at `0x140012ada`
- `DMCmnUtils!IsWvdFeatureAllowed` at `0x140012af3`
- `DMCmnUtils!IsWvdFeatureAllowed` at `0x140012af3`
- `DMCmnUtils!BigStrcat` at `0x140012967`
- `DMCmnUtils!BigStrcat` at `0x140012967`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x140012a6e`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x140012a98`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x140012ac2`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x140012a6e`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x140012a98`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x140012ac2`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14001293a`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14001293a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140012a2f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140012a2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400129e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001331b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400129e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001331b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012bcb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012c04`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012c24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012c6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012c9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012d10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012d4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012d6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012dde`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012e18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012e34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140013305`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012bcb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012c04`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012c24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012c6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012c9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012d10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012d4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012d6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012dde`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012e18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012e34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140013305`
- `omadmapi!__imp_?OmaDmGetNextSessionIDToUse@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@PEAK@Z` at `0x140012b2b`
- `omadmapi!__imp_?OmaDmGetNextSessionIDToUse@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@PEAK@Z` at `0x140012b2b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall TriggerSession(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        unsigned int a6,
        char a7,
        unsigned int a8,
        int *a9)
{
  unsigned __int16 *v9; // rsi
  const unsigned __int16 *v10; // r15
  const unsigned __int16 *v11; // r12
  const unsigned __int16 *v12; // r14
  int *v13; // r13
  char IsStateSeparationEnabled; // al
  const wchar_t *v15; // rdx
  unsigned __int16 *v16; // rbx
  signed int NextSessionIDToUse; // edi
  LSTATUS v18; // eax
  int v19; // eax
  __int64 v20; // rcx
  HLOCAL *v21; // rax
  unsigned __int64 v22; // r8
  HLOCAL *v23; // rsi
  HLOCAL *hlocal_string_nothrow; // r14
  char v25; // r15
  HLOCAL v26; // rcx
  HLOCAL v27; // r13
  HLOCAL v28; // r12
  DWORD LastError; // edi
  HLOCAL *v30; // rax
  unsigned __int64 v31; // r8
  HLOCAL *v32; // r14
  void **v33; // r12
  HLOCAL v34; // rax
  void *v35; // r13
  DWORD v36; // edi
  HLOCAL *v37; // r12
  char v38; // r14
  HLOCAL v39; // rcx
  char v40; // r14
  HLOCAL *v41; // r15
  DWORD v42; // edi
  HLOCAL *v43; // r12
  char v44; // r15
  HLOCAL v45; // rcx
  char v46; // r15
  HLOCAL *v47; // r14
  DWORD v48; // edi
  unsigned int v49; // edx
  char v50; // cl
  __int64 v51; // rdx
  int v52; // eax
  unsigned int v53; // r8d
  HANDLE v54; // rsi
  DWORD v55; // edi
  const unsigned __int16 *v56; // r8
  __int64 v57; // rcx
  unsigned int v58; // r8d
  __int64 v59; // rcx
  signed int v60; // eax
  unsigned int v61; // r8d
  signed int v62; // eax
  DWORD v63; // eax
  COmaDmPrcLogger *Logger; // rax
  struct _PROCESS_INFORMATION *v65; // rdx
  HLOCAL v67; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v68; // [rsp+58h] [rbp-A8h]
  HLOCAL v69; // [rsp+60h] [rbp-A0h] BYREF
  DWORD ExitCode; // [rsp+68h] [rbp-98h] BYREF
  int v71; // [rsp+6Ch] [rbp-94h] BYREF
  int *v72; // [rsp+70h] [rbp-90h]
  const unsigned __int16 *v73; // [rsp+78h] [rbp-88h]
  HANDLE v74; // [rsp+80h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  HANDLE hObject; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v77; // [rsp+98h] [rbp-68h]
  HLOCAL v78; // [rsp+A0h] [rbp-60h] BYREF
  const unsigned __int16 *v79; // [rsp+A8h] [rbp-58h]
  HLOCAL hMem; // [rsp+B0h] [rbp-50h] BYREF
  HLOCAL v81; // [rsp+B8h] [rbp-48h] BYREF
  HLOCAL v82[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v83; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v84; // [rsp+E0h] [rbp-20h]
  _BYTE v85[32]; // [rsp+E8h] [rbp-18h] BYREF
  HLOCAL *v86; // [rsp+108h] [rbp+8h]
  __int64 v87; // [rsp+110h] [rbp+10h]

  v9 = a4;
  v68 = a4;
  v10 = a3;
  v74 = a3;
  v11 = a2;
  v79 = a2;
  v12 = a1;
  v73 = a1;
  v13 = a9;
  v72 = a9;
  LODWORD(v67) = 0;
  ExitCode = 0;
  v71 = 0;
  v77 = 0;
  hKey = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v15 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
  if ( !IsStateSeparationEnabled )
    v15 = L"Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
  v16 = BigStrcat(3u, v15, L"\\", v11);
  v82[1] = v16;
  hObject = 0;
  v83 = 0;
  v84 = 0;
  if ( !(unsigned int)ShouldDisableOnRoaming(v11) )
  {
    if ( (unsigned int)ShouldDisableAsDeletePending(v11) )
    {
      NextSessionIDToUse = -2102657018;
      goto LABEL_113;
    }
    if ( !v16 )
    {
      NextSessionIDToUse = -2147024882;
      goto LABEL_113;
    }
    hKey = 0;
    v18 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v16, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
    NextSessionIDToUse = v18;
    if ( v18 )
    {
      if ( v18 > 0 )
        NextSessionIDToUse = (unsigned __int16)v18 | 0x80070000;
      goto LABEL_112;
    }
    if ( v10 )
    {
      v19 = OmaDmRegistrySetString(hKey, 0, L"InitiationId", v10);
    }
    else
    {
      NextSessionIDToUse = OmaDmRegistrySetDWORD(hKey, 0, L"SessionId", a5);
      if ( NextSessionIDToUse < 0 )
        goto LABEL_112;
      NextSessionIDToUse = OmaDmRegistrySetDWORD(hKey, 0, L"UIMode", a6);
      if ( NextSessionIDToUse < 0 )
        goto LABEL_112;
      v19 = OmaDmRegistrySetDWORD(hKey, 0, L"Origin", a8);
    }
    NextSessionIDToUse = v19;
    if ( v19 < 0 )
    {
LABEL_112:
      v9 = v68;
      goto LABEL_113;
    }
    if ( IsWvdFeatureAllowed(v11) && qword_140024308 )
    {
      if ( !a5 )
      {
        NextSessionIDToUse = OmaDmGetNextSessionIDToUse(v11, 1, &a5);
        if ( NextSessionIDToUse < 0 )
          goto LABEL_112;
      }
      v21 = (HLOCAL *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
      v23 = v21;
      if ( v21 )
      {
        v21[4] = 0;
        v21[5] = 0;
        *v21 = 0;
        v21[1] = 0;
        v21[2] = 0;
        v21[3] = 0;
      }
      else
      {
        v23 = 0;
      }
      if ( v12 )
      {
        hlocal_string_nothrow = (HLOCAL *)wil::make_hlocal_string_nothrow((wil *)&v67, v12, v22);
        v25 = 1;
        v26 = hMem;
      }
      else
      {
        v26 = 0;
        hMem = 0;
        hlocal_string_nothrow = &hMem;
        v25 = 2;
      }
      if ( v23 != hlocal_string_nothrow )
      {
        v27 = *hlocal_string_nothrow;
        v28 = *v23;
        if ( *v23 )
        {
          LastError = GetLastError();
          LocalFree(v28);
          SetLastError(LastError);
        }
        *v23 = v27;
        *hlocal_string_nothrow = 0;
        v26 = hMem;
        v11 = v79;
      }
      if ( (v25 & 2) != 0 )
      {
        v25 &= ~2u;
        if ( v26 )
          LocalFree(v26);
      }
      if ( (v25 & 1) != 0 )
      {
        v25 &= ~1u;
        if ( v67 )
          LocalFree(v67);
      }
      v30 = (HLOCAL *)wil::make_hlocal_string_nothrow((wil *)&v78, v11, v22);
      v32 = v30;
      v33 = v23 + 1;
      if ( v23 + 1 != v30 )
      {
        v34 = *v30;
        v67 = v34;
        v35 = *v33;
        if ( *v33 )
        {
          v36 = GetLastError();
          LocalFree(v35);
          SetLastError(v36);
          v34 = v67;
        }
        *v33 = v34;
        *v32 = 0;
      }
      if ( v78 )
        LocalFree(v78);
      if ( v74 )
      {
        v37 = (HLOCAL *)wil::make_hlocal_string_nothrow((wil *)&v69, (const unsigned __int16 *)v74, v31);
        v38 = 4;
        v39 = v81;
      }
      else
      {
        v39 = 0;
        v81 = 0;
        v37 = &v81;
        v38 = 8;
      }
      v40 = v25 | v38;
      v41 = v23 + 2;
      if ( v23 + 2 != v37 )
      {
        v67 = *v37;
        v78 = *v41;
        if ( v78 )
        {
          v42 = GetLastError();
          LocalFree(v78);
          SetLastError(v42);
        }
        *v41 = v67;
        *v37 = 0;
        v39 = v81;
      }
      if ( (v40 & 8) != 0 )
      {
        v40 &= ~8u;
        if ( v39 )
          LocalFree(v39);
      }
      if ( (v40 & 4) != 0 )
      {
        v40 &= ~4u;
        if ( v69 )
          LocalFree(v69);
      }
      if ( v68 )
      {
        v43 = (HLOCAL *)wil::make_hlocal_string_nothrow((wil *)&v67, v68, v31);
        v44 = 16;
        v45 = v82[0];
      }
      else
      {
        v45 = 0;
        v82[0] = 0;
        v43 = v82;
        v44 = 32;
      }
      v46 = v40 | v44;
      v47 = v23 + 3;
      if ( v23 + 3 != v43 )
      {
        v78 = *v43;
        v69 = *v47;
        if ( v69 )
        {
          v48 = GetLastError();
          LocalFree(v69);
          SetLastError(v48);
        }
        *v47 = v78;
        *v43 = 0;
        v45 = v82[0];
      }
      if ( (v46 & 0x20) != 0 )
      {
        v46 &= ~0x20u;
        if ( v45 )
          LocalFree(v45);
      }
      if ( (v46 & 0x10) != 0 && v67 )
        LocalFree(v67);
      v49 = a8;
      *((_DWORD *)v23 + 9) = a8;
      v50 = a7;
      *((_BYTE *)v23 + 32) = a7;
      *((_DWORD *)v23 + 10) = a5;
      *((_DWORD *)v23 + 11) = 0;
      if ( v50 )
      {
        v52 = ThreadpoolManager::QueueThreadpoolWork(qword_140024308, 1, v31, v23);
        v12 = v73;
      }
      else
      {
        v12 = v73;
        if ( v73 )
        {
          if ( v49 == 42 )
            v51 = 3;
          else
            v51 = 2;
        }
        else
        {
          v51 = 1;
        }
        v52 = ThreadpoolManager::QueueThreadpoolWork(qword_140024308, v51, v31, v23);
      }
      NextSessionIDToUse = v52;
      if ( v52 >= 0 )
      {
        v77 = _InterlockedCompareExchange(&ThreadpoolManager::m_numberOfWorkQueued, 0, 0);
      }
      else if ( (unsigned int)dword_140023000 > 5 )
      {
        LODWORD(v67) = v52;
        v86 = &v67;
        v87 = 4;
        tlgWriteTransfer_EventWriteTransfer(&dword_140023000, byte_14001E37B, 0, 0, 3, v85);
      }
      v10 = (const unsigned __int16 *)v74;
      v11 = v79;
      goto LABEL_111;
    }
    v74 = 0;
    v53 = *(_DWORD *)Feature_ConfigRefresh__descriptor;
    if ( (*(_DWORD *)Feature_ConfigRefresh__descriptor & 4) == 0 )
    {
      v69 = *(HLOCAL *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigRefresh>::GetCachedFeatureEnabledState(
                         v20,
                         &v69);
      v53 = (unsigned int)v69;
    }
    LODWORD(v67) = 0;
    WORD2(v67) = 3;
    wil::details::ReportUsageToService(&qword_140024350, 43467477, (v53 >> 10) & 1, (v53 >> 11) & 1, &v67, 1);
    NextSessionIDToUse = SignalConfigRefreshSemaphore(&v74);
    if ( NextSessionIDToUse >= 0 )
    {
      v54 = hObject;
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        v55 = GetLastError();
        CloseHandle(v54);
        SetLastError(v55);
      }
      hObject = 0;
      v56 = L"Schedule to run OMADMClient by client";
      if ( a7 )
        v56 = L"Schedule to run OMADMClient by server";
      NextSessionIDToUse = DmRunTask(L"\\Microsoft\\Windows\\EnterpriseMgmt", v11, v56, &hObject);
      if ( NextSessionIDToUse >= 0 )
      {
        if ( !WaitForSingleObject(hObject, 0x5265C0u) )
        {
          v61 = *(_DWORD *)Feature_ConfigRefresh__descriptor;
          if ( (*(_DWORD *)Feature_ConfigRefresh__descriptor & 4) == 0 )
          {
            v69 = *(HLOCAL *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigRefresh>::GetCachedFeatureEnabledState(
                               v59,
                               &v69);
            v61 = (unsigned int)v69;
          }
          LODWORD(v67) = 0;
          WORD2(v67) = 3;
          wil::details::ReportUsageToService(&qword_140024350, 43467477, (v61 >> 10) & 1, (v61 >> 11) & 1, &v67, 1);
          WaitForConfigRefreshSemaphore(v74);
          if ( GetExitCodeProcess(hObject, &ExitCode) )
            goto LABEL_106;
          v62 = GetLastError();
          NextSessionIDToUse = v62;
          if ( v62 > 0 )
            NextSessionIDToUse = (unsigned __int16)v62 | 0x80070000;
          if ( NextSessionIDToUse >= 0 )
          {
LABEL_106:
            if ( (int)OmaDmRegistryGetDWORD(HKEY_LOCAL_MACHINE, v10, L"SessionHRESULT", (unsigned int *)&v71) >= 0
              && v71 >= 0 )
            {
              v63 = ExitCode;
              if ( (int)ExitCode > 0 )
                v63 = (unsigned __int16)ExitCode | 0x80070000;
              v71 = v63;
            }
          }
          goto LABEL_110;
        }
        v60 = GetLastError();
        NextSessionIDToUse = v60;
        if ( v60 > 0 )
          NextSessionIDToUse = (unsigned __int16)v60 | 0x80070000;
      }
      else if ( (unsigned int)dword_140023000 > 5 )
      {
        LODWORD(v67) = NextSessionIDToUse;
        v86 = &v67;
        v87 = 4;
        tlgWriteTransfer_EventWriteTransfer(&dword_140023000, &word_14001E34E, 0, 0, 3, v85);
      }
      v58 = *(_DWORD *)Feature_ConfigRefresh__descriptor;
      if ( (*(_DWORD *)Feature_ConfigRefresh__descriptor & 4) == 0 )
      {
        v69 = *(HLOCAL *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigRefresh>::GetCachedFeatureEnabledState(
                           v57,
                           &v69);
        v58 = (unsigned int)v69;
      }
      LODWORD(v67) = 0;
      WORD2(v67) = 3;
      wil::details::ReportUsageToService(&qword_140024350, 43467477, (v58 >> 10) & 1, (v58 >> 11) & 1, &v67, 1);
      WaitForConfigRefreshSemaphore(v74);
    }
LABEL_110:
    v12 = v73;
LABEL_111:
    v13 = v72;
    goto LABEL_112;
  }
  NextSessionIDToUse = -2102657020;
LABEL_113:
  if ( ExitCode || NextSessionIDToUse < 0 )
  {
    if ( NextSessionIDToUse >= 0 )
    {
      if ( (int)ExitCode > 0 )
        NextSessionIDToUse = (unsigned __int16)ExitCode | 0x80070000;
      else
        NextSessionIDToUse = ExitCode;
    }
    if ( (unsigned int)dword_140023000 > 5 )
    {
      v69 = (HLOCAL)NextSessionIDToUse;
      v86 = &v69;
      v87 = 8;
      tlgWriteTransfer_EventWriteTransfer(&dword_140023000, byte_14001E319, 0, 0, 3, v85);
    }
    if ( NextSessionIDToUse < 0 )
    {
      if ( v10 )
      {
        NotifySessionResultRecovery(v10, NextSessionIDToUse);
        if ( v9 )
          NotifySessionResultRecovery(v9, NextSessionIDToUse);
      }
    }
  }
  if ( v13 )
    *v13 = v71;
  Logger = COmaDmPrcLogger::GetLogger();
  COmaDmPrcLogger::LogOmaDmPrcTriggerSessionResult(Logger, v12, v11, v10, v9, a8, a5, v77, v71, NextSessionIDToUse);
  wil::details::CloseProcessInformation((wil::details *)&v83, v65);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  if ( v16 )
    LocalFree(v16);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)NextSessionIDToUse;
}

```

## disassembly

```asm
0x1400128d4  push    rbp
0x1400128d6  push    rbx
0x1400128d7  push    rsi
0x1400128d8  push    rdi
0x1400128d9  push    r12
0x1400128db  push    r13
0x1400128dd  push    r14
0x1400128df  push    r15
0x1400128e1  lea     rbp, [rsp-28h]
0x1400128e6  sub     rsp, 128h
0x1400128ed  mov     rax, cs:__security_cookie
0x1400128f4  xor     rax, rsp
0x1400128f7  mov     [rbp+60h+var_48], rax
0x1400128fb  mov     rsi, r9
0x1400128fe  mov     [rsp+160h+var_108], r9
0x140012903  mov     r15, r8
0x140012906  mov     [rbp+60h+var_E0], r8
0x14001290a  mov     r12, rdx
0x14001290d  mov     [rbp+60h+var_B8], rdx
0x140012911  mov     r14, rcx
0x140012914  mov     [rsp+160h+var_E8], rcx
0x140012919  mov     r13, [rbp+60h+arg_40]
0x140012920  mov     [rsp+160h+var_F0], r13
0x140012925  xor     edi, edi
0x140012927  mov     dword ptr [rsp+160h+var_110], edi
0x14001292b  mov     [rsp+160h+ExitCode], edi
0x14001292f  mov     [rsp+160h+var_F4], edi
0x140012933  mov     [rbp+60h+var_C8], edi
0x140012936  mov     [rbp+60h+hKey], rdi
0x14001293a  call    cs:__imp_RtlIsStateSeparationEnabled
0x140012941  nop     dword ptr [rax+rax+00h]
0x140012946  lea     rcx, aSoftwareMicros_3; "Software\\Microsoft\\Provisioning\\OMAD"...
0x14001294d  lea     rdx, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Provisioni"...
0x140012954  test    al, al
0x140012956  cmovz   rdx, rcx
0x14001295a  mov     r9, r12
0x14001295d  lea     r8, asc_140019FC8; "\\"
0x140012964  lea     ecx, [rdi+3]
0x140012967  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x14001296e  nop     dword ptr [rax+rax+00h]
0x140012973  mov     rbx, rax
0x140012976  mov     [rbp+60h+var_98], rax
0x14001297a  mov     [rbp+60h+hObject], rdi
0x14001297e  xorps   xmm0, xmm0
0x140012981  xor     eax, eax
0x140012983  movups  [rbp+60h+var_90], xmm0
0x140012987  mov     [rbp+60h+var_80], rax
0x14001298b  mov     rcx, r12
0x14001298e  call    ?ShouldDisableOnRoaming@@YAHPEBGW4tagDMACCOUNTLOOKUPTYPE@@@Z; ShouldDisableOnRoaming(ushort const *,tagDMACCOUNTLOOKUPTYPE)
0x140012993  test    eax, eax
0x140012995  jz      short loc_1400129A1
0x140012997  mov     edi, 82AC0004h
0x14001299c  jmp     loc_1400131EE
0x1400129a1  mov     rcx, r12
0x1400129a4  call    ?ShouldDisableAsDeletePending@@YAHPEBGW4tagDMACCOUNTLOOKUPTYPE@@@Z; ShouldDisableAsDeletePending(ushort const *,tagDMACCOUNTLOOKUPTYPE)
0x1400129a9  test    eax, eax
0x1400129ab  jz      short loc_1400129B7
0x1400129ad  mov     edi, 82AC0006h
0x1400129b2  jmp     loc_1400131EE
0x1400129b7  test    rbx, rbx
0x1400129ba  jnz     short loc_1400129C6
0x1400129bc  mov     edi, 8007000Eh
0x1400129c1  jmp     loc_1400131EE
0x1400129c6  mov     rsi, [rbp+60h+hKey]
0x1400129ca  test    rsi, rsi
0x1400129cd  jz      short loc_1400129FC
0x1400129cf  call    cs:__imp_GetLastError
0x1400129d6  nop     dword ptr [rax+rax+00h]
0x1400129db  mov     edi, eax
0x1400129dd  mov     rcx, rsi; hKey
0x1400129e0  call    cs:__imp_RegCloseKey
0x1400129e7  nop     dword ptr [rax+rax+00h]
0x1400129ec  mov     ecx, edi; dwErrCode
0x1400129ee  call    cs:__imp_SetLastError
0x1400129f5  nop     dword ptr [rax+rax+00h]
0x1400129fa  xor     edi, edi
0x1400129fc  mov     [rbp+60h+hKey], rdi
0x140012a00  mov     [rsp+160h+lpdwDisposition], rdi; lpdwDisposition
0x140012a05  lea     rax, [rbp+60h+hKey]
0x140012a09  mov     [rsp+160h+phkResult], rax; phkResult
0x140012a0e  mov     [rsp+160h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x140012a13  mov     [rsp+160h+samDesired], 2001Fh; samDesired
0x140012a1b  mov     [rsp+160h+dwOptions], edi; dwOptions
0x140012a1f  xor     r9d, r9d; lpClass
0x140012a22  xor     r8d, r8d; Reserved
0x140012a25  mov     rdx, rbx; lpSubKey
0x140012a28  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140012a2f  call    cs:__imp_RegCreateKeyExW
0x140012a36  nop     dword ptr [rax+rax+00h]
0x140012a3b  mov     edi, eax
0x140012a3d  test    eax, eax
0x140012a3f  jz      short loc_140012A55
0x140012a41  jle     loc_1400131E9
0x140012a47  movzx   edi, ax
0x140012a4a  or      edi, 80070000h
0x140012a50  jmp     loc_1400131E9
0x140012a55  xor     edx, edx
0x140012a57  mov     rcx, [rbp+60h+hKey]
0x140012a5b  test    r15, r15
0x140012a5e  jnz     short loc_140012AD0
0x140012a60  mov     r9d, [rbp+60h+arg_20]
0x140012a67  lea     r8, aSessionid; "SessionId"
0x140012a6e  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x140012a75  nop     dword ptr [rax+rax+00h]
0x140012a7a  mov     edi, eax
0x140012a7c  test    eax, eax
0x140012a7e  js      loc_1400131E9
0x140012a84  mov     r9d, [rbp+60h+arg_28]
0x140012a8b  lea     r8, aUimode; "UIMode"
0x140012a92  xor     edx, edx
0x140012a94  mov     rcx, [rbp+60h+hKey]
0x140012a98  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x140012a9f  nop     dword ptr [rax+rax+00h]
0x140012aa4  mov     edi, eax
0x140012aa6  test    eax, eax
0x140012aa8  js      loc_1400131E9
0x140012aae  mov     r9d, [rbp+60h+arg_38]
0x140012ab5  lea     r8, aOrigin; "Origin"
0x140012abc  xor     edx, edx
0x140012abe  mov     rcx, [rbp+60h+hKey]
0x140012ac2  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x140012ac9  nop     dword ptr [rax+rax+00h]
0x140012ace  jmp     short loc_140012AE6
0x140012ad0  mov     r9, r15
0x140012ad3  lea     r8, aInitiationid_0; "InitiationId"
0x140012ada  call    cs:__imp_?OmaDmRegistrySetString@@YAJPEAUHKEY__@@PEBG11@Z; OmaDmRegistrySetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x140012ae1  nop     dword ptr [rax+rax+00h]
0x140012ae6  test    eax, eax
0x140012ae8  mov     edi, eax
0x140012aea  js      loc_1400131E9
0x140012af0  mov     rcx, r12
0x140012af3  call    cs:__imp_?IsWvdFeatureAllowed@@YAHPEBG@Z; IsWvdFeatureAllowed(ushort const *)
0x140012afa  nop     dword ptr [rax+rax+00h]
0x140012aff  xor     edi, edi
0x140012b01  test    eax, eax
0x140012b03  jz      loc_140012F0E
0x140012b09  cmp     cs:qword_140024308, rdi
0x140012b10  jz      loc_140012F0E
0x140012b16  cmp     [rbp+60h+arg_20], edi
0x140012b1c  jnz     short loc_140012B43
0x140012b1e  lea     r8, [rbp+60h+arg_20]
0x140012b25  lea     edx, [rdi+1]
0x140012b28  mov     rcx, r12
0x140012b2b  call    cs:__imp_?OmaDmGetNextSessionIDToUse@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@PEAK@Z; OmaDmGetNextSessionIDToUse(ushort const *,tagDMACCOUNTLOOKUPTYPE,ulong *)
0x140012b32  nop     dword ptr [rax+rax+00h]
0x140012b37  mov     edi, eax
0x140012b39  test    eax, eax
0x140012b3b  js      loc_1400131E9
0x140012b41  xor     edi, edi
0x140012b43  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140012b4a  mov     ecx, 30h ; '0'; unsigned __int64
0x140012b4f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140012b54  mov     rsi, rax
0x140012b57  test    rax, rax
0x140012b5a  jz      short loc_140012B75
0x140012b5c  mov     [rax+20h], rdi
0x140012b60  mov     [rax+28h], rdi
0x140012b64  mov     [rax], rdi
0x140012b67  mov     [rax+8], rdi
0x140012b6b  mov     [rax+10h], rdi
0x140012b6f  mov     [rax+18h], rdi
0x140012b73  jmp     short loc_140012B78
0x140012b75  mov     rsi, rdi
0x140012b78  test    r14, r14
0x140012b7b  jz      short loc_140012B99
0x140012b7d  mov     rdx, r14; unsigned __int16 *
0x140012b80  lea     rcx, [rsp+160h+var_110]; this
0x140012b85  call    ?make_hlocal_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_hlocal_string_nothrow(ushort const *,unsigned __int64)
0x140012b8a  mov     r14, rax
0x140012b8d  mov     r15d, 1
0x140012b93  mov     rcx, [rbp+60h+hMem]
0x140012b97  jmp     short loc_140012BAA
0x140012b99  mov     rcx, rdi
0x140012b9c  mov     [rbp+60h+hMem], rcx
0x140012ba0  lea     r14, [rbp+60h+hMem]
0x140012ba4  mov     r15d, 2
0x140012baa  cmp     rsi, r14
0x140012bad  jz      short loc_140012BF5
0x140012baf  mov     r13, [r14]
0x140012bb2  mov     r12, [rsi]
0x140012bb5  test    r12, r12
0x140012bb8  jz      short loc_140012BE7
0x140012bba  call    cs:__imp_GetLastError
0x140012bc1  nop     dword ptr [rax+rax+00h]
0x140012bc6  mov     edi, eax
0x140012bc8  mov     rcx, r12; hMem
0x140012bcb  call    cs:__imp_LocalFree
0x140012bd2  nop     dword ptr [rax+rax+00h]
0x140012bd7  mov     ecx, edi; dwErrCode
0x140012bd9  call    cs:__imp_SetLastError
0x140012be0  nop     dword ptr [rax+rax+00h]
0x140012be5  xor     edi, edi
0x140012be7  mov     [rsi], r13
0x140012bea  mov     [r14], rdi
0x140012bed  mov     rcx, [rbp+60h+hMem]; hMem
0x140012bf1  mov     r12, [rbp+60h+var_B8]
0x140012bf5  test    r15b, 2
0x140012bf9  jz      short loc_140012C10
0x140012bfb  and     r15d, 0FFFFFFFDh
0x140012bff  test    rcx, rcx
0x140012c02  jz      short loc_140012C10
0x140012c04  call    cs:__imp_LocalFree
0x140012c0b  nop     dword ptr [rax+rax+00h]
0x140012c10  test    r15b, 1
0x140012c14  jz      short loc_140012C30
0x140012c16  and     r15d, 0FFFFFFFEh
0x140012c1a  mov     rcx, [rsp+160h+var_110]; hMem
0x140012c1f  test    rcx, rcx
0x140012c22  jz      short loc_140012C30
0x140012c24  call    cs:__imp_LocalFree
0x140012c2b  nop     dword ptr [rax+rax+00h]
0x140012c30  mov     rdx, r12; unsigned __int16 *
0x140012c33  lea     rcx, [rbp+60h+var_C0]; this
0x140012c37  call    ?make_hlocal_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_hlocal_string_nothrow(ushort const *,unsigned __int64)
0x140012c3c  mov     r14, rax
0x140012c3f  lea     r12, [rsi+8]
0x140012c43  cmp     r12, rax
0x140012c46  jz      short loc_140012C92
0x140012c48  mov     rax, [rax]
0x140012c4b  mov     [rsp+160h+var_110], rax
0x140012c50  mov     r13, [r12]
0x140012c54  test    r13, r13
0x140012c57  jz      short loc_140012C8B
0x140012c59  call    cs:__imp_GetLastError
0x140012c60  nop     dword ptr [rax+rax+00h]
0x140012c65  mov     edi, eax
0x140012c67  mov     rcx, r13; hMem
0x140012c6a  call    cs:__imp_LocalFree
0x140012c71  nop     dword ptr [rax+rax+00h]
0x140012c76  mov     ecx, edi; dwErrCode
0x140012c78  call    cs:__imp_SetLastError
0x140012c7f  nop     dword ptr [rax+rax+00h]
0x140012c84  mov     rax, [rsp+160h+var_110]
0x140012c89  xor     edi, edi
0x140012c8b  mov     [r12], rax
0x140012c8f  mov     [r14], rdi
0x140012c92  mov     rcx, [rbp+60h+var_C0]; hMem
0x140012c96  test    rcx, rcx
0x140012c99  jz      short loc_140012CA7
0x140012c9b  call    cs:__imp_LocalFree
0x140012ca2  nop     dword ptr [rax+rax+00h]
0x140012ca7  mov     r13d, 4
0x140012cad  mov     rdx, [rbp+60h+var_E0]; unsigned __int16 *
0x140012cb1  test    rdx, rdx
0x140012cb4  jz      short loc_140012CCC
0x140012cb6  lea     rcx, [rsp+160h+var_100]; this
0x140012cbb  call    ?make_hlocal_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_hlocal_string_nothrow(ushort const *,unsigned __int64)
0x140012cc0  mov     r12, rax
0x140012cc3  mov     r14d, r13d
0x140012cc6  mov     rcx, [rbp+60h+var_A8]
0x140012cca  jmp     short loc_140012CDD
0x140012ccc  mov     rcx, rdi
0x140012ccf  mov     [rbp+60h+var_A8], rcx
0x140012cd3  lea     r12, [rbp+60h+var_A8]
0x140012cd7  mov     r14d, 8
0x140012cdd  or      r14d, r15d
0x140012ce0  lea     r15, [rsi+10h]
0x140012ce4  cmp     r15, r12
0x140012ce7  jz      short loc_140012D3C
0x140012ce9  mov     rax, [r12]
0x140012ced  mov     [rsp+160h+var_110], rax
0x140012cf2  mov     rax, [r15]
0x140012cf5  mov     [rbp+60h+var_C0], rax
0x140012cf9  test    rax, rax
0x140012cfc  jz      short loc_140012D2C
0x140012cfe  call    cs:__imp_GetLastError
0x140012d05  nop     dword ptr [rax+rax+00h]
0x140012d0a  mov     edi, eax
0x140012d0c  mov     rcx, [rbp+60h+var_C0]; hMem
0x140012d10  call    cs:__imp_LocalFree
0x140012d17  nop     dword ptr [rax+rax+00h]
0x140012d1c  mov     ecx, edi; dwErrCode
0x140012d1e  call    cs:__imp_SetLastError
0x140012d25  nop     dword ptr [rax+rax+00h]
0x140012d2a  xor     edi, edi
0x140012d2c  mov     rax, [rsp+160h+var_110]
0x140012d31  mov     [r15], rax
0x140012d34  mov     [r12], rdi
0x140012d38  mov     rcx, [rbp+60h+var_A8]; hMem
0x140012d3c  test    r14b, 8
0x140012d40  jz      short loc_140012D57
0x140012d42  and     r14d, 0FFFFFFF7h
0x140012d46  test    rcx, rcx
0x140012d49  jz      short loc_140012D57
0x140012d4b  call    cs:__imp_LocalFree
0x140012d52  nop     dword ptr [rax+rax+00h]
0x140012d57  test    r13b, r14b
0x140012d5a  jz      short loc_140012D76
0x140012d5c  and     r14d, 0FFFFFFFBh
0x140012d60  mov     rcx, [rsp+160h+var_100]; hMem
0x140012d65  test    rcx, rcx
0x140012d68  jz      short loc_140012D76
0x140012d6a  call    cs:__imp_LocalFree
0x140012d71  nop     dword ptr [rax+rax+00h]
0x140012d76  mov     rdx, [rsp+160h+var_108]; unsigned __int16 *
0x140012d7b  test    rdx, rdx
0x140012d7e  jz      short loc_140012D99
0x140012d80  lea     rcx, [rsp+160h+var_110]; this
0x140012d85  call    ?make_hlocal_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_hlocal_string_nothrow(ushort const *,unsigned __int64)
0x140012d8a  mov     r12, rax
  ... truncated ...
```

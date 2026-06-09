# ServiceStart(void)

- ea: `0x1400480f0`
- end: `0x140048e14`
- name: `?ServiceStart@@YAKXZ`
- size: `3364`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400236a0`

## callees

- `0x140002c43`
- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140025194`
- `0x1400257b0`
- `0x14002af68`
- `0x140047c20`
- `0x1400480f0`
- `0x14004fdac`
- `0x1400500dc`
- `0x1400569ec`
- `0x14005a080`
- `0x140065d14`
- `0x140065dbc`
- `0x140065df8`
- `0x140067168`
- `0x14006f634`
- `0x140070e74`
- `0x1400714b8`
- `0x1400716a8`
- `0x14007c07c`
- `0x14007ca0c`
- `0x14007cc68`
- `0x14007fe54`
- `0x14007ff0c`
- `0x140080044`
- `0x140080278`
- `0x14008050c`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!RegisterEventSourceW` at `0x14004847a`
- `ADVAPI32!RegisterEventSourceW` at `0x14004847a`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1400482e9`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1400482e9`
- `KERNEL32!GetLastError` at `0x1400484f8`
- `KERNEL32!GetLastError` at `0x1400485a6`
- `KERNEL32!GetLastError` at `0x140048604`
- `KERNEL32!GetLastError` at `0x14004865f`
- `KERNEL32!GetLastError` at `0x14004875c`
- `KERNEL32!GetLastError` at `0x1400487c7`
- `KERNEL32!GetLastError` at `0x140048820`
- `KERNEL32!GetLastError` at `0x1400488f7`
- `KERNEL32!GetLastError` at `0x14004897c`
- `KERNEL32!GetLastError` at `0x140048ba9`
- `KERNEL32!GetLastError` at `0x140048c4c`
- `KERNEL32!GetLastError` at `0x140048ca6`
- `KERNEL32!GetLastError` at `0x140048d84`
- `KERNEL32!GetLastError` at `0x1400484f8`
- `KERNEL32!GetLastError` at `0x1400485a6`
- `KERNEL32!GetLastError` at `0x140048604`
- `KERNEL32!GetLastError` at `0x14004865f`
- `KERNEL32!GetLastError` at `0x14004875c`
- `KERNEL32!GetLastError` at `0x1400487c7`
- `KERNEL32!GetLastError` at `0x140048820`
- `KERNEL32!GetLastError` at `0x1400488f7`
- `KERNEL32!GetLastError` at `0x14004897c`
- `KERNEL32!GetLastError` at `0x140048ba9`
- `KERNEL32!GetLastError` at `0x140048c4c`
- `KERNEL32!GetLastError` at `0x140048ca6`
- `KERNEL32!GetLastError` at `0x140048d84`
- `KERNEL32!CloseHandle` at `0x140048c72`
- `KERNEL32!CloseHandle` at `0x140048cb9`
- `KERNEL32!CloseHandle` at `0x140048c72`
- `KERNEL32!CloseHandle` at `0x140048cb9`
- `KERNEL32!EnterCriticalSection` at `0x14004839f`
- `KERNEL32!EnterCriticalSection` at `0x140048497`
- `KERNEL32!EnterCriticalSection` at `0x140048848`
- `KERNEL32!EnterCriticalSection` at `0x140048a4c`
- `KERNEL32!EnterCriticalSection` at `0x140048a59`
- `KERNEL32!EnterCriticalSection` at `0x14004839f`
- `KERNEL32!EnterCriticalSection` at `0x140048497`
- `KERNEL32!EnterCriticalSection` at `0x140048848`
- `KERNEL32!EnterCriticalSection` at `0x140048a4c`
- `KERNEL32!EnterCriticalSection` at `0x140048a59`
- `KERNEL32!LeaveCriticalSection` at `0x1400483eb`
- `KERNEL32!LeaveCriticalSection` at `0x14004846b`
- `KERNEL32!LeaveCriticalSection` at `0x1400484e3`
- `KERNEL32!LeaveCriticalSection` at `0x14004853a`
- `KERNEL32!LeaveCriticalSection` at `0x14004887a`
- `KERNEL32!LeaveCriticalSection` at `0x140048a6d`
- `KERNEL32!LeaveCriticalSection` at `0x140048a7a`
- `KERNEL32!LeaveCriticalSection` at `0x1400483eb`
- `KERNEL32!LeaveCriticalSection` at `0x14004846b`
- `KERNEL32!LeaveCriticalSection` at `0x1400484e3`
- `KERNEL32!LeaveCriticalSection` at `0x14004853a`
- `KERNEL32!LeaveCriticalSection` at `0x14004887a`
- `KERNEL32!LeaveCriticalSection` at `0x140048a6d`
- `KERNEL32!LeaveCriticalSection` at `0x140048a7a`
- `KERNEL32!WaitForSingleObject` at `0x140048be4`
- `KERNEL32!WaitForSingleObject` at `0x140048be4`
- `KERNEL32!CreateEventW` at `0x1400485f2`
- `KERNEL32!CreateEventW` at `0x1400485f2`
- `KERNEL32!GetExitCodeThread` at `0x140048c84`
- `KERNEL32!GetExitCodeThread` at `0x140048c84`
- `KERNEL32!CreateThread` at `0x140048b77`
- `KERNEL32!CreateThread` at `0x140048d56`
- `KERNEL32!CreateThread` at `0x140048b77`
- `KERNEL32!CreateThread` at `0x140048d56`

## pseudocode

```c
__int64 __fastcall ServiceStart(__int64 a1, unsigned int a2)
{
  unsigned int v2; // edx
  unsigned int v3; // eax
  unsigned int v4; // edx
  CMapDeviceId *v5; // rcx
  __int64 v6; // rdx
  unsigned int FaxRegistry; // eax
  unsigned int *v8; // rbx
  void *v9; // rax
  unsigned int v10; // esi
  __int64 v11; // rdi
  __int64 v12; // rax
  _DWORD *v13; // rdx
  unsigned int v14; // edx
  unsigned int i; // edi
  DWORD LastError; // eax
  DWORD v17; // ebx
  DWORD started; // eax
  CMapDeviceId *v20; // rcx
  __int64 v21; // rdx
  unsigned int v22; // edx
  unsigned int v23; // edx
  _OWORD *v24; // rax
  DWORD v25; // eax
  int FaxServiceInstance; // eax
  CMapDeviceId *v27; // rcx
  __int64 v28; // rdx
  unsigned int *v29; // rdx
  DWORD v30; // eax
  DWORD v31; // eax
  DWORD v32; // eax
  unsigned int v33; // edx
  DWORD Configuration; // eax
  unsigned int v35; // edx
  CMapDeviceId *v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // r9
  struct _REG_FAX_SERVICE *v39; // rcx
  unsigned int v40; // edx
  DWORD v41; // eax
  DWORD v42; // ebx
  int v43; // eax
  unsigned __int16 *v44; // rdx
  unsigned int v45; // eax
  unsigned int v46; // edx
  unsigned int v47; // ebx
  int v48; // eax
  unsigned __int16 *v49; // rdx
  unsigned int v50; // eax
  unsigned int v51; // edx
  __int64 v52; // r9
  CNotificationMap *v53; // rcx
  unsigned int v54; // edx
  unsigned int v55; // edx
  HANDLE v56; // rdi
  DWORD v57; // eax
  unsigned int v58; // edx
  DWORD v59; // eax
  __int64 v60; // rdx
  void *v61; // rdx
  unsigned __int16 *v62; // rcx
  DWORD dwCreationFlags[2]; // [rsp+20h] [rbp-79h]
  LPDWORD lpThreadId; // [rsp+28h] [rbp-71h]
  LPVOID lpParameter; // [rsp+30h] [rbp-69h] BYREF
  DWORD ExitCode; // [rsp+38h] [rbp-61h] BYREF
  DWORD ThreadId; // [rsp+3Ch] [rbp-5Dh] BYREF
  const wchar_t *v68; // [rsp+40h] [rbp-59h] BYREF
  int v69; // [rsp+48h] [rbp-51h]
  int v70; // [rsp+4Ch] [rbp-4Dh]
  const wchar_t *v71; // [rsp+50h] [rbp-49h]
  int v72; // [rsp+58h] [rbp-41h]
  int v73; // [rsp+5Ch] [rbp-3Dh]
  const wchar_t *v74; // [rsp+60h] [rbp-39h]
  int v75; // [rsp+68h] [rbp-31h]
  int v76; // [rsp+6Ch] [rbp-2Dh]
  const wchar_t *v77; // [rsp+70h] [rbp-29h]
  int v78; // [rsp+78h] [rbp-21h]
  int v79; // [rsp+7Ch] [rbp-1Dh]
  DWORD v80; // [rsp+80h] [rbp-19h]
  unsigned __int16 v81[14]; // [rsp+84h] [rbp-15h] BYREF

  ThreadId = 0;
  ExitCode = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids);
  }
  ReportServiceStatus(2u, a2, 0xEA60u);
  if ( !(unsigned int)IsFaxShared() )
  {
    LODWORD(lpParameter) = 0;
    v3 = IsLocalFaxPrinterShared(&lpParameter);
    if ( v3 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_26;
      }
      v6 = 22;
    }
    else
    {
      if ( !(_DWORD)lpParameter )
        goto LABEL_26;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids);
      }
      v3 = SetLocalFaxPrinterSharing();
      if ( !v3 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids);
        }
        goto LABEL_26;
      }
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_26:
        ReportServiceStatus(2u, v4, 0xEA60u);
        goto LABEL_27;
      }
      v6 = 21;
    }
    WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v3);
    goto LABEL_26;
  }
LABEL_27:
  ReportServiceStatus(2u, v2, 0xEA60u);
  v69 = 1;
  v68 = L"Initialization/Termination";
  v71 = L"Outbound";
  v74 = L"Inbound";
  v77 = L"Unknown";
  v70 = 2;
  v72 = 2;
  v73 = 2;
  v75 = 3;
  v76 = 2;
  v78 = 4;
  v79 = 2;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ac5a08ad8a3d3e294c0851b9f863ab66_Traceguids);
  }
  if ( InitializeCriticalSectionAndSpinCount(&stru_1400A1850, 0x80000000) )
    byte_1400A18A8 = 1;
  lpParameter = 0;
  FaxRegistry = GetFaxRegistry(&lpParameter);
  if ( FaxRegistry )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_ac5a08ad8a3d3e294c0851b9f863ab66_Traceguids, FaxRegistry);
    }
    goto LABEL_57;
  }
  v8 = (unsigned int *)lpParameter;
  if ( !(unsigned int)CreateFaxEventSource(lpParameter, &v68) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_ac5a08ad8a3d3e294c0851b9f863ab66_Traceguids);
    }
LABEL_56:
    FreeFaxRegistry(v8);
LABEL_57:
    LastError = GetLastError();
    v17 = LastError;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, LastError);
    }
    return v17;
  }
  EnterCriticalSection(&stru_1400A1850);
  v9 = (void *)pMemAlloc(16LL * v8[14]);
  gs_pFaxCategory = v9;
  if ( !v9 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_ac5a08ad8a3d3e294c0851b9f863ab66_Traceguids);
    }
    LeaveCriticalSection(&stru_1400A1850);
    goto LABEL_56;
  }
  memset_0(v9, 0, 16LL * v8[14]);
  v10 = 0;
  dword_1400A187C = v8[14];
  if ( dword_1400A187C )
  {
    while ( 1 )
    {
      v11 = 2LL * v10;
      v12 = StringDup(*(unsigned __int16 **)(*((_QWORD *)v8 + 6) + 16LL * v10));
      v13 = gs_pFaxCategory;
      *((_QWORD *)gs_pFaxCategory + 2 * v10) = v12;
      if ( !v12 )
        break;
      ++v10;
      v13[2 * v11 + 2] = *(_DWORD *)(*((_QWORD *)v8 + 6) + 8 * v11 + 8);
      v13[2 * v11 + 3] = *(_DWORD *)(*((_QWORD *)v8 + 6) + 8 * v11 + 12);
      if ( v10 >= v8[14] )
        goto LABEL_52;
    }
    LeaveCriticalSection(&stru_1400A1850);
    goto LABEL_53;
  }
LABEL_52:
  LeaveCriticalSection(&stru_1400A1850);
  hEventLog = RegisterEventSourceW(0, L"Microsoft Fax");
  if ( !hEventLog )
  {
LABEL_53:
    EnterCriticalSection(&stru_1400A1850);
    for ( i = 0; i < v8[14]; ++i )
      pMemFree(*((LPVOID *)gs_pFaxCategory + 2 * i));
    pMemFree(gs_pFaxCategory);
    gs_pFaxCategory = 0;
    dword_1400A187C = 0;
    LeaveCriticalSection(&stru_1400A1850);
    goto LABEL_56;
  }
  ReportServiceStatus(2u, v14, 0xEA60u);
  started = EnableProcessPrivilege();
  v17 = started;
  if ( started )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_187;
    }
    v21 = 24;
LABEL_186:
    WPP_SF_d(*((_QWORD *)v20 + 2), v21, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, started);
LABEL_187:
    v80 = v17;
    v81[0] = 0;
    StringCchPrintfW(v81, 0xCu, L"%ld", v17, *(_QWORD *)dwCreationFlags, lpThreadId);
    v52 = 3221257513LL;
LABEL_188:
    FaxLog(1, 1, 1, v52);
    return v17;
  }
  if ( !(unsigned int)InitializeStringTable() )
  {
    started = GetLastError();
    v17 = started;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_187;
    }
    v21 = 25;
    goto LABEL_186;
  }
  ReportServiceStatus(2u, v22, 0xEA60u);
  g_hThreadCountEvent = CreateEventW(0, 1, 1, 0);
  if ( !g_hThreadCountEvent )
  {
    started = GetLastError();
    v17 = started;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_187;
    }
    v21 = 26;
    goto LABEL_186;
  }
  ReportServiceStatus(2u, v23, 0xEA60u);
  v24 = (_OWORD *)pMemAlloc(0x3Cu);
  g_pFaxPerfCounters = v24;
  if ( !v24 )
  {
    v25 = GetLastError();
    v17 = v25;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v25);
    }
    goto LABEL_83;
  }
  *v24 = 0;
  v24[1] = 0;
  v24[2] = 0;
  *(_OWORD *)((char *)v24 + 44) = 0;
  FaxServiceInstance = PerfInitialize();
  if ( FaxServiceInstance < 0 )
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_83;
    }
    v28 = 28;
LABEL_89:
    WPP_SF_d(
      *((_QWORD *)v27 + 2),
      v28,
      WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids,
      (unsigned int)FaxServiceInstance);
LABEL_83:
    FaxLog(1, 1, 0, 3221257586LL);
    return v17;
  }
  FaxServiceInstance = PerfGetFaxServiceInstance();
  if ( FaxServiceInstance < 0 )
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_83;
    }
    v28 = 29;
    goto LABEL_89;
  }
  if ( PerfSetFaxInboundRefValue(
         (char *)g_pFaxPerfCounters + 16,
         v29,
         (unsigned int *)g_pFaxPerfCounters + 1,
         (unsigned int *)g_pFaxPerfCounters + 3,
         (unsigned int *)g_pFaxPerfCounters + 2)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v30 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v30);
  }
  if ( PerfSetFaxOutboundRefValue(
         (char *)g_pFaxPerfCounters + 36,
         (char *)g_pFaxPerfCounters + 40,
         (char *)g_pFaxPerfCounters + 20,
         (char *)g_pFaxPerfCounters + 24,
         (char *)g_pFaxPerfCounters + 32,
         (char *)g_pFaxPerfCounters + 28)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v31 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v31);
  }
  if ( PerfSetFaxServiceRefValue(
         (char *)g_pFaxPerfCounters + 44,
         (char *)g_pFaxPerfCounters + 48,
         (char *)g_pFaxPerfCounters + 56,
         (char *)g_pFaxPerfCounters + 52)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v32 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v32);
  }
  EnterCriticalSection(&g_CsPerfCounters);
  g_dwOutboundSeconds = 60 * *((_DWORD *)g_pFaxPerfCounters + 8);
  g_dwTotalSeconds = 60 * *((_DWORD *)g_pFaxPerfCounters + 14);
  g_dwInboundSeconds = 60 * *((_DWORD *)g_pFaxPerfCounters + 3);
  LeaveCriticalSection(&g_CsPerfCounters);
  ReportServiceStatus(2u, v33, 0xEA60u);
  Configuration = LoadConfiguration((struct _REG_FAX_SERVICE **)&lpParameter);
  v17 = Configuration;
  if ( Configuration )
  {
    v36 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v17;
    }
    v37 = 33;
    goto LABEL_115;
  }
  ReportServiceStatus(2u, v35, 0xEA60u);
  if ( !(unsigned int)InitializeFaxQueue(v39) )
  {
    v41 = GetLastError();
    v42 = v41;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v41);
    }
    v80 = v42;
    v81[0] = 0;
    v43 = StringCchPrintfW(v81, 0xCu, L"%ld", v42);
    v44 = v81;
    if ( v43 < 0 )
      v44 = 0;
    lpThreadId = (LPDWORD)v44;
    *(_QWORD *)dwCreationFlags = *((_QWORD *)g_pFaxConfig + 12);
    FaxLog(1, 1, 2, 3221257576LL);
    started = GetLastError();
    v17 = started;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_187;
    }
    v21 = 35;
    goto LABEL_186;
  }
  ReportServiceStatus(2u, v40, 0xEA60u);
  v45 = InitializeLogging();
  v47 = v45;
  if ( v45 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v45);
    }
    v80 = v47;
    v81[0] = 0;
    v48 = StringCchPrintfW(v81, 0xCu, L"%ld", v47);
    v49 = v81;
    if ( v48 < 0 )
      v49 = 0;
    lpThreadId = (LPDWORD)v49;
    *(_QWORD *)dwCreationFlags = *(_QWORD *)&fDesiredAccess;
    FaxLog(1, 1, 2, 3221257577LL);
    EnterCriticalSection(&g_CsInboundActivityLogging);
    EnterCriticalSection(&g_CsOutboundActivityLogging);
    *(_QWORD *)((char *)&g_ActivityLoggingConfig + 4) = 0;
    LeaveCriticalSection(&g_CsOutboundActivityLogging);
    LeaveCriticalSection(&g_CsInboundActivityLogging);
  }
  ReportServiceStatus(2u, v46, 0xEA60u);
  v50 = InitializeServerEvents();
  v17 = v50;
  if ( v50 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v50);
    }
    v80 = v17;
    v81[0] = 0;
    StringCchPrintfW(v81, 0xCu, L"%ld", v17, *(_QWORD *)dwCreationFlags, lpThreadId);
    v52 = 3221257516LL;
    goto LABEL_188;
  }
  ReportServiceStatus(2u, v51, 0xEA60u);
  started = CNotificationMap::Init(v53);
  v17 = started;
  if ( started )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_187;
    }
    v21 = 38;
    goto LABEL_186;
  }
  ReportServiceStatus(2u, v54, 0xEA60u);
  v56 = CreateThread(0, 0, FaxInitThread, lpParameter, 0, &ThreadId);
  if ( !v56 )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v17;
    }
    Configuration = GetLastError();
    v36 = WPP_GLOBAL_Control;
    v37 = 39;
    v17 = Configuration;
LABEL_115:
    v38 = Configuration;
LABEL_116:
    WPP_SF_d(*((_QWORD *)v36 + 2), v37, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v38);
    return v17;
  }
  ReportServiceStatus(2u, v55, 0x4E20u);
  while ( 1 )
  {
    v57 = WaitForSingleObject(v56, 0x2710u);
    v17 = v57;
    if ( !v57 )
      break;
    if ( v57 != 258 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v59 = GetLastError();
        v60 = 42;
        goto LABEL_164;
      }
      goto LABEL_165;
    }
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids);
    }
    ReportServiceStatus(2u, v58, 0x7530u);
  }
  if ( !GetExitCodeThread(v56, &ExitCode) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v59 = GetLastError();
      v60 = 40;
LABEL_164:
      v17 = v59;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v60, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v59);
    }
LABEL_165:
    CloseHandle(v56);
    return v17;
  }
  v17 = ExitCode;
  CloseHandle(v56);
  if ( v17 )
  {
    v36 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v17;
    }
    v37 = 43;
    v38 = v17;
    goto LABEL_116;
  }
  FaxLog(1, 3, 0, 1073773825);
  started = StartFaxRpcServer(v62, v61);
  v17 = started;
  if ( started )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_187;
    }
    v21 = 44;
    goto LABEL_186;
  }
  g_hRPCListeningThread = CreateThread(0, 0, FaxRPCListeningThread, 0, 0, &ThreadId);
  if ( !g_hRPCListeningThread )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_187;
    }
    started = GetLastError();
    v20 = WPP_GLOBAL_Control;
    v21 = 45;
    v17 = started;
    goto LABEL_186;
  }
  return 0;
}

```

## disassembly

```asm
0x1400480f0  push    rbp
0x1400480f2  push    rbx
0x1400480f3  push    rsi
0x1400480f4  push    rdi
0x1400480f5  push    r12
0x1400480f7  push    r13
0x1400480f9  push    r14
0x1400480fb  push    r15
0x1400480fd  lea     rbp, [rsp-1Fh]
0x140048102  sub     rsp, 0B8h
0x140048109  mov     rax, cs:__security_cookie
0x140048110  xor     rax, rsp
0x140048113  mov     [rbp+57h+var_50], rax
0x140048117  xor     r15d, r15d
0x14004811a  mov     [rbp+57h+ThreadId], r15d
0x14004811e  mov     [rbp+57h+ExitCode], r15d
0x140048122  mov     rcx, cs:WPP_GLOBAL_Control
0x140048129  lea     r12, WPP_GLOBAL_Control
0x140048130  lea     rdi, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x140048137  mov     sil, 5
0x14004813a  lea     r13d, [r15+4]
0x14004813e  cmp     rcx, r12
0x140048141  jz      short loc_14004815F
0x140048143  test    [rcx+1Ch], r13b
0x140048147  jz      short loc_14004815F
0x140048149  cmp     [rcx+19h], sil
0x14004814d  jb      short loc_14004815F
0x14004814f  mov     rcx, [rcx+10h]
0x140048153  lea     edx, [r15+11h]
0x140048157  mov     r8, rdi
0x14004815a  call    WPP_SF_
0x14004815f  mov     ebx, 0EA60h
0x140048164  mov     r14d, 2
0x14004816a  mov     r8d, ebx; unsigned int
0x14004816d  mov     ecx, r14d; unsigned int
0x140048170  call    ?ReportServiceStatus@@YAHKKK@Z; ReportServiceStatus(ulong,ulong,ulong)
0x140048175  call    IsFaxShared
0x14004817a  test    eax, eax
0x14004817c  jnz     loc_140048250
0x140048182  lea     rcx, [rbp+57h+lpParameter]
0x140048186  mov     dword ptr [rbp+57h+lpParameter], r15d
0x14004818a  call    IsLocalFaxPrinterShared
0x14004818f  test    eax, eax
0x140048191  jnz     loc_140048219
0x140048197  cmp     dword ptr [rbp+57h+lpParameter], r15d
0x14004819b  jz      loc_140048245
0x1400481a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400481a8  cmp     rcx, r12
0x1400481ab  jz      short loc_1400481C8
0x1400481ad  test    [rcx+1Ch], r13b
0x1400481b1  jz      short loc_1400481C8
0x1400481b3  cmp     [rcx+19h], sil
0x1400481b7  jb      short loc_1400481C8
0x1400481b9  mov     rcx, [rcx+10h]
0x1400481bd  lea     edx, [rax+13h]
0x1400481c0  mov     r8, rdi
0x1400481c3  call    WPP_SF_
0x1400481c8  call    SetLocalFaxPrinterSharing
0x1400481cd  test    eax, eax
0x1400481cf  jnz     short loc_1400481FA
0x1400481d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400481d8  cmp     rcx, r12
0x1400481db  jz      short loc_140048245
0x1400481dd  test    [rcx+1Ch], r13b
0x1400481e1  jz      short loc_140048245
0x1400481e3  cmp     [rcx+19h], sil
0x1400481e7  jb      short loc_140048245
0x1400481e9  mov     rcx, [rcx+10h]
0x1400481ed  lea     edx, [rax+14h]
0x1400481f0  mov     r8, rdi
0x1400481f3  call    WPP_SF_
0x1400481f8  jmp     short loc_140048245
0x1400481fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140048201  cmp     rcx, r12
0x140048204  jz      short loc_140048245
0x140048206  test    [rcx+1Ch], r13b
0x14004820a  jz      short loc_140048245
0x14004820c  cmp     [rcx+19h], r14b
0x140048210  jb      short loc_140048245
0x140048212  mov     edx, 15h
0x140048217  jmp     short loc_140048236
0x140048219  mov     rcx, cs:WPP_GLOBAL_Control
0x140048220  cmp     rcx, r12
0x140048223  jz      short loc_140048245
0x140048225  test    [rcx+1Ch], r13b
0x140048229  jz      short loc_140048245
0x14004822b  cmp     [rcx+19h], r14b
0x14004822f  jb      short loc_140048245
0x140048231  mov     edx, 16h
0x140048236  mov     rcx, [rcx+10h]
0x14004823a  mov     r9d, eax
0x14004823d  mov     r8, rdi
0x140048240  call    WPP_SF_d
0x140048245  mov     r8d, ebx; unsigned int
0x140048248  mov     ecx, r14d; unsigned int
0x14004824b  call    ?ReportServiceStatus@@YAHKKK@Z; ReportServiceStatus(ulong,ulong,ulong)
0x140048250  mov     r8d, ebx; unsigned int
0x140048253  mov     ecx, r14d; unsigned int
0x140048256  call    ?ReportServiceStatus@@YAHKKK@Z; ReportServiceStatus(ulong,ulong,ulong)
0x14004825b  lea     rax, aInitialization; "Initialization/Termination"
0x140048262  mov     [rbp+57h+var_A8], 1
0x140048269  mov     [rbp+57h+var_B0], rax
0x14004826d  lea     rax, aOutbound; "Outbound"
0x140048274  mov     [rbp+57h+var_A0], rax
0x140048278  lea     rax, aInbound; "Inbound"
0x14004827f  mov     [rbp+57h+var_90], rax
0x140048283  lea     rax, aUnknown_0; "Unknown"
0x14004828a  mov     [rbp+57h+var_80], rax
0x14004828e  mov     [rbp+57h+var_A4], r14d
0x140048292  mov     [rbp+57h+var_98], r14d
0x140048296  mov     [rbp+57h+var_94], r14d
0x14004829a  mov     [rbp+57h+var_88], 3
0x1400482a1  mov     [rbp+57h+var_84], r14d
0x1400482a5  mov     [rbp+57h+var_78], r13d
0x1400482a9  mov     [rbp+57h+var_74], r14d
0x1400482ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400482b4  cmp     rcx, r12
0x1400482b7  jz      short loc_1400482DA
0x1400482b9  test    [rcx+1Ch], r14b
0x1400482bd  jz      short loc_1400482DA
0x1400482bf  cmp     [rcx+19h], sil
0x1400482c3  jb      short loc_1400482DA
0x1400482c5  mov     rcx, [rcx+10h]
0x1400482c9  lea     r8, WPP_ac5a08ad8a3d3e294c0851b9f863ab66_Traceguids
0x1400482d0  mov     edx, 0Ch
0x1400482d5  call    WPP_SF_
0x1400482da  lea     rsi, stru_1400A1850
0x1400482e1  mov     edx, 80000000h; dwSpinCount
0x1400482e6  mov     rcx, rsi; lpCriticalSection
0x1400482e9  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1400482ef  test    eax, eax
0x1400482f1  jz      short loc_1400482FA
0x1400482f3  mov     cs:byte_1400A18A8, 1
0x1400482fa  lea     rcx, [rbp+57h+lpParameter]
0x1400482fe  mov     [rbp+57h+lpParameter], r15
0x140048302  call    GetFaxRegistry
0x140048307  test    eax, eax
0x140048309  jz      short loc_14004834C
0x14004830b  mov     rcx, cs:WPP_GLOBAL_Control
0x140048312  cmp     rcx, r12
0x140048315  jz      loc_1400484F8
0x14004831b  test    [rcx+1Ch], r14b
0x14004831f  jz      loc_1400484F8
0x140048325  cmp     [rcx+19h], r14b
0x140048329  jb      loc_1400484F8
0x14004832f  mov     rcx, [rcx+10h]
0x140048333  lea     r8, WPP_ac5a08ad8a3d3e294c0851b9f863ab66_Traceguids
0x14004833a  mov     edx, 0Eh
0x14004833f  mov     r9d, eax
0x140048342  call    WPP_SF_d
0x140048347  jmp     loc_1400484F8
0x14004834c  mov     rbx, [rbp+57h+lpParameter]
0x140048350  lea     rdx, [rbp+57h+var_B0]
0x140048354  mov     rcx, rbx
0x140048357  call    CreateFaxEventSource
0x14004835c  test    eax, eax
0x14004835e  jnz     short loc_14004839C
0x140048360  mov     rcx, cs:WPP_GLOBAL_Control
0x140048367  cmp     rcx, r12
0x14004836a  jz      loc_1400484F0
0x140048370  test    [rcx+1Ch], r14b
0x140048374  jz      loc_1400484F0
0x14004837a  cmp     [rcx+19h], r14b
0x14004837e  jb      loc_1400484F0
0x140048384  mov     rcx, [rcx+10h]
0x140048388  lea     edx, [rax+0Fh]
0x14004838b  lea     r8, WPP_ac5a08ad8a3d3e294c0851b9f863ab66_Traceguids
0x140048392  call    WPP_SF_
0x140048397  jmp     loc_1400484F0
0x14004839c  mov     rcx, rsi; lpCriticalSection
0x14004839f  call    cs:__imp_EnterCriticalSection
0x1400483a5  mov     ecx, [rbx+38h]
0x1400483a8  shl     rcx, 4; dwBytes
0x1400483ac  call    pMemAlloc
0x1400483b1  mov     cs:?gs_pFaxCategory@@3PEAU_FAX_LOG_CATEGORYW@@EA, rax; _FAX_LOG_CATEGORYW * gs_pFaxCategory
0x1400483b8  test    rax, rax
0x1400483bb  jnz     short loc_1400483F6
0x1400483bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400483c4  cmp     rcx, r12
0x1400483c7  jz      short loc_1400483E8
0x1400483c9  test    [rcx+1Ch], r14b
0x1400483cd  jz      short loc_1400483E8
0x1400483cf  cmp     [rcx+19h], r14b
0x1400483d3  jb      short loc_1400483E8
0x1400483d5  mov     rcx, [rcx+10h]
0x1400483d9  lea     edx, [rax+10h]
0x1400483dc  lea     r8, WPP_ac5a08ad8a3d3e294c0851b9f863ab66_Traceguids
0x1400483e3  call    WPP_SF_
0x1400483e8  mov     rcx, rsi; lpCriticalSection
0x1400483eb  call    cs:__imp_LeaveCriticalSection
0x1400483f1  jmp     loc_1400484F0
0x1400483f6  mov     r8d, [rbx+38h]
0x1400483fa  xor     edx, edx; Val
0x1400483fc  shl     r8, 4; Size
0x140048400  mov     rcx, rax; void *
0x140048403  call    memset_0
0x140048408  mov     eax, [rbx+38h]
0x14004840b  mov     esi, r15d
0x14004840e  mov     cs:dword_1400A187C, eax
0x140048414  test    eax, eax
0x140048416  jz      short loc_140048464
0x140048418  mov     rcx, [rbx+30h]
0x14004841c  mov     edi, esi
0x14004841e  add     rdi, rdi
0x140048421  mov     rcx, [rcx+rdi*8]; unsigned __int16 *
0x140048425  call    StringDup
0x14004842a  mov     rdx, cs:?gs_pFaxCategory@@3PEAU_FAX_LOG_CATEGORYW@@EA; _FAX_LOG_CATEGORYW * gs_pFaxCategory
0x140048431  mov     [rdx+rdi*8], rax
0x140048435  test    rax, rax
0x140048438  jz      loc_140048533
0x14004843e  mov     rax, [rbx+30h]
0x140048442  inc     esi
0x140048444  mov     ecx, [rax+rdi*8+8]
0x140048448  mov     [rdx+rdi*8+8], ecx
0x14004844c  mov     rax, [rbx+30h]
0x140048450  mov     ecx, [rax+rdi*8+0Ch]
0x140048454  mov     [rdx+rdi*8+0Ch], ecx
0x140048458  cmp     esi, [rbx+38h]
0x14004845b  jb      short loc_140048418
0x14004845d  lea     rdi, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x140048464  lea     rcx, stru_1400A1850; lpCriticalSection
0x14004846b  call    cs:__imp_LeaveCriticalSection
0x140048471  lea     rdx, SourceName; "Microsoft Fax"
0x140048478  xor     ecx, ecx; lpUNCServerName
0x14004847a  call    cs:__imp_RegisterEventSourceW
0x140048480  mov     cs:hEventLog, rax
0x140048487  test    rax, rax
0x14004848a  jnz     loc_140048545
0x140048490  lea     rcx, stru_1400A1850; lpCriticalSection
0x140048497  call    cs:__imp_EnterCriticalSection
0x14004849d  mov     edi, r15d
0x1400484a0  cmp     [rbx+38h], r15d
0x1400484a4  jbe     short loc_1400484C2
0x1400484a6  mov     rcx, cs:?gs_pFaxCategory@@3PEAU_FAX_LOG_CATEGORYW@@EA; _FAX_LOG_CATEGORYW * gs_pFaxCategory
0x1400484ad  mov     eax, edi
0x1400484af  add     rax, rax
0x1400484b2  mov     rcx, [rcx+rax*8]; lpMem
0x1400484b6  call    pMemFree
0x1400484bb  inc     edi
0x1400484bd  cmp     edi, [rbx+38h]
0x1400484c0  jb      short loc_1400484A6
0x1400484c2  mov     rcx, cs:?gs_pFaxCategory@@3PEAU_FAX_LOG_CATEGORYW@@EA; lpMem
0x1400484c9  call    pMemFree
0x1400484ce  lea     rcx, stru_1400A1850; lpCriticalSection
0x1400484d5  mov     cs:?gs_pFaxCategory@@3PEAU_FAX_LOG_CATEGORYW@@EA, r15; _FAX_LOG_CATEGORYW * gs_pFaxCategory
0x1400484dc  mov     cs:dword_1400A187C, r15d
0x1400484e3  call    cs:__imp_LeaveCriticalSection
0x1400484e9  lea     rdi, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x1400484f0  mov     rcx, rbx; lpMem
0x1400484f3  call    FreeFaxRegistry
0x1400484f8  call    cs:__imp_GetLastError
0x1400484fe  mov     ebx, eax
0x140048500  mov     rcx, cs:WPP_GLOBAL_Control
0x140048507  cmp     rcx, r12
0x14004850a  jz      short loc_14004852C
0x14004850c  test    [rcx+1Ch], r13b
0x140048510  jz      short loc_14004852C
0x140048512  cmp     [rcx+19h], r14b
0x140048516  jb      short loc_14004852C
0x140048518  mov     rcx, [rcx+10h]
0x14004851c  mov     edx, 17h
0x140048521  mov     r9d, eax
0x140048524  mov     r8, rdi
0x140048527  call    WPP_SF_d
0x14004852c  mov     eax, ebx
0x14004852e  jmp     loc_140048DF4
0x140048533  lea     rcx, stru_1400A1850; lpCriticalSection
0x14004853a  call    cs:__imp_LeaveCriticalSection
0x140048540  jmp     loc_140048490
0x140048545  mov     esi, 0EA60h
0x14004854a  mov     ecx, r14d; unsigned int
0x14004854d  mov     r8d, esi; unsigned int
0x140048550  call    ?ReportServiceStatus@@YAHKKK@Z; ReportServiceStatus(ulong,ulong,ulong)
0x140048555  call    EnableProcessPrivilege
0x14004855a  mov     ebx, eax
0x14004855c  test    eax, eax
0x14004855e  jz      short loc_14004859D
0x140048560  mov     rcx, cs:WPP_GLOBAL_Control
0x140048567  cmp     rcx, r12
0x14004856a  jz      loc_140048DA7
0x140048570  test    [rcx+1Ch], r13b
0x140048574  jz      loc_140048DA7
0x14004857a  cmp     [rcx+19h], r14b
0x14004857e  jb      loc_140048DA7
0x140048584  mov     edx, 18h
0x140048589  mov     rcx, [rcx+10h]
0x14004858d  mov     r9d, eax
0x140048590  mov     r8, rdi
0x140048593  call    WPP_SF_d
0x140048598  jmp     loc_140048DA7
0x14004859d  call    ?InitializeStringTable@@YAHXZ; InitializeStringTable(void)
0x1400485a2  test    eax, eax
0x1400485a4  jnz     short loc_1400485D9
0x1400485a6  call    cs:__imp_GetLastError
0x1400485ac  mov     ebx, eax
0x1400485ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400485b5  cmp     rcx, r12
0x1400485b8  jz      loc_140048DA7
0x1400485be  test    [rcx+1Ch], r13b
0x1400485c2  jz      loc_140048DA7
  ... truncated ...
```

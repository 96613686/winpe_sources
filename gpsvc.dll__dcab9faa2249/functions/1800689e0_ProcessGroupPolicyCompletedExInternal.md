# ProcessGroupPolicyCompletedExInternal

- ea: `0x1800689e0`
- end: `0x180069744`
- name: `ProcessGroupPolicyCompletedExInternal`
- size: `3428`
- prototype: `__int64 __fastcall(struct _GUID *, HLOCAL hMem)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18009c710`

## callees

- `0x180001830`
- `0x18002408c`
- `0x18002c690`
- `0x18002c70c`
- `0x18002e088`
- `0x180030bcc`
- `0x18003d8d0`
- `0x18003d96c`
- `0x18005541c`
- `0x1800585e8`
- `0x18005b2d0`
- `0x180063a04`
- `0x180063df0`
- `0x180067258`
- `0x180067d58`
- `0x1800689e0`
- `0x18006b2f8`
- `0x180073984`
- `0x1800739ec`
- `0x1800746f0`
- `0x180075ec0`
- `0x18007d320`
- `0x18007de08`
- `0x1800b98e0`
- `0x1800ba058`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068aad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068ae2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068c41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068c70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068aad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068ae2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068c41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068c70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800696a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800696a3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180069312`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180069312`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006932a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006932a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180069286`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180069286`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800692c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800692c1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180068d99`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800694fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800695c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180068d99`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800694fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800695c7`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFlags` at `0x180068a83`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFlags` at `0x180068c21`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFlags` at `0x180068a83`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFlags` at `0x180068c21`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18006934a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18006934a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800695b6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800695b6`

## string_xrefs

- `0x1800691cd`: `Software\Microsoft\Windows NT\CurrentVersion\Winlogon\GPExtensions`
- `0x180068ab6`: `ProcessGroupPolicyCompletedExInternal: pAsyncHandle memory is invalid, dwStatus = 0x%x`
- `0x180068aeb`: `ProcessGroupPolicyCompletedExInternal: pAsyncHandle memory is invalid, dwStatus = 0x%x`
- `0x180068b4d`: `ProcessGroupPolicyCompletedExInternal: Entering. Extension = %s, dwStatus = 0x%x`
- `0x180068b94`: `ProcessGroupPolicyCompletedExInternal: Entering. Extension = %s, dwStatus = 0x%x`
- `0x180068bc2`: `Extension %s asynchronous completion is stale`
- `0x180068bef`: `Extension %s asynchronous completion is stale`
- `0x180068c4a`: `ProcessGroupPolicyCompletedExInternal: pGPOInfo memory is invalid, dwStatus = 0x%x`
- `0x180068c79`: `ProcessGroupPolicyCompletedExInternal: pGPOInfo memory is invalid, dwStatus = 0x%x`
- `0x180068ccd`: `Extension %s asynchronous completion has invalid pGPHandle->pGPOInfo`
- `0x180068cf9`: `Extension %s asynchronous completion has invalid pGPHandle->pGPOInfo`
- `0x180068d4d`: `Extension %s asynchronous completion, aborting due to machine shutdown or logoff`
- `0x180068d7a`: `Extension %s asynchronous completion, aborting due to machine shutdown or logoff`
- `0x180068f2f`: `Extension %s asynchronous completion, failed to save GPOList`
- `0x180068f64`: `Extension %s asynchronous completion, failed to save GPOList`
- `0x180068f8c`: `Extension %s asynchronous completion, failed to read shadow GPOList`
- `0x180068faf`: `Extension %s asynchronous completion, failed to read shadow GPOList`
- `0x180069091`: `ProcessGroupPolicyCompletedExInternal: SetNextFgPolicyRefreshInfo failed, %d.`
- `0x1800690b4`: `ProcessGroupPolicyCompletedExInternal: SetNextFgPolicyRefreshInfo failed, %d.`
- `0x1800690e2`: `ProcessGroupPolicyCompletedExInternal: Extension %s requires a synchronous logon.`
- `0x18006910f`: `ProcessGroupPolicyCompletedExInternal: Extension %s requires a synchronous logon.`
- `0x1800693a8`: `ProcessGroupPolicyCompletedExInternal: Extension %s doesn't support rsop logging.`
- `0x1800693d3`: `ProcessGroupPolicyCompletedExInternal: Extension %s doesn't support rsop logging.`
- `0x18006942d`: `ProcessGroupPolicyCompletedExInternal: Extension %s was able to log data. Error = 0x%x, dwRet = %d. Clearing the dirty bit`
- `0x18006945f`: `ProcessGroupPolicyCompletedExInternal: Extension %s was able to log data. Error = 0x%x, dwRet = %d. Clearing the dirty bit`
- `0x1800694af`: `ProcessGroupPolicyCompletedExInternal: Extension %s was not able to log data. Error = 0x%x, dwRet = %d. leaving the log dirty`
- `0x1800694e1`: `ProcessGroupPolicyCompletedExInternal: Extension %s was not able to log data. Error = 0x%x, dwRet = %d. leaving the log dirty`
- `0x1800695ed`: `ProcessGroupPolicyCompletedExInternal: Finished processing extension <%ws> at %d ticks (ms)`
- `0x180069618`: `ProcessGroupPolicyCompletedExInternal: Finished processing extension <%ws> at %d ticks (ms)`
- `0x180069662`: `ProcessGroupPolicyCompletedExInternal: pGPHandle->dwExtnCount is %d for %s.`
- `0x180069691`: `ProcessGroupPolicyCompletedExInternal: pGPHandle->dwExtnCount is %d for %s.`
- `0x1800696da`: `ProcessGroupPolicyCompletedExInternal: Leaving. Extension = %s, Return status dwRet = 0x%x`
- `0x180069709`: `ProcessGroupPolicyCompletedExInternal: Leaving. Extension = %s, Return status dwRet = 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall ProcessGroupPolicyCompletedExInternal(struct _GUID *a1, HLOCAL *hMem, DWORD a3, int a4)
{
  int *v7; // rdi
  void (*v9)(unsigned int, const unsigned __int16 *, ...); // rbx
  __int64 LastError; // r8
  DWORD v11; // eax
  DWORD v12; // esi
  int v13; // ecx
  int v14; // ecx
  void (*v15)(unsigned int, const unsigned __int16 *, ...); // rax
  void (*v16)(unsigned int, const unsigned __int16 *, ...); // rbx
  __int64 v17; // r8
  DWORD v18; // eax
  HLOCAL v19; // r13
  unsigned __int16 *v20; // rsi
  int v21; // ebx
  DWORD v22; // edi
  int v23; // ebx
  unsigned int GPSourceFileId; // eax
  int *v25; // r8
  int v26; // ebx
  HKEY v27; // r8
  HKEY v28; // r8
  void (*v29)(unsigned int, const unsigned __int16 *, ...); // rax
  const unsigned __int16 *v30; // rdx
  unsigned __int16 *v31; // rbx
  unsigned int FgPolicyRefreshInfoImpl2; // eax
  unsigned int v33; // eax
  int v34; // ecx
  const unsigned __int16 *v35; // r8
  __int64 v36; // rax
  const WCHAR *v37; // r8
  __int64 v38; // rdx
  WCHAR *v39; // rcx
  WCHAR v40; // r9
  WCHAR *v41; // rax
  __int64 v42; // rax
  LSTATUS v43; // eax
  int v44; // ebx
  int v45; // r8d
  __int64 v46; // rsi
  int v47; // ebx
  DWORD v48; // edi
  CGPPolicyEventReporting **v49; // r13
  int v50; // ebx
  unsigned int v51; // eax
  __int64 v52; // rdx
  int *v53; // r8
  __int64 TickCount; // r9
  unsigned int *v55; // rbx
  unsigned int v56; // edi
  PHKEY phkResult; // [rsp+20h] [rbp-568h]
  PHKEY phkResulta; // [rsp+20h] [rbp-568h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-560h]
  struct _GPOINFO *v60; // [rsp+30h] [rbp-558h]
  unsigned int v61; // [rsp+50h] [rbp-538h]
  DWORD cbData; // [rsp+54h] [rbp-534h] BYREF
  int v63; // [rsp+58h] [rbp-530h]
  HKEY hKey; // [rsp+60h] [rbp-528h] BYREF
  DWORD Type; // [rsp+68h] [rbp-520h] BYREF
  struct IWbemServices *v66; // [rsp+70h] [rbp-518h] BYREF
  __int64 v67; // [rsp+78h] [rbp-510h] BYREF
  CGPPolicyEventReporting **v68; // [rsp+80h] [rbp-508h]
  struct _GROUP_POLICY_OBJECTW *v69; // [rsp+88h] [rbp-500h] BYREF
  HLOCAL hMema; // [rsp+90h] [rbp-4F8h]
  struct _GUID *v71; // [rsp+98h] [rbp-4F0h]
  HLOCAL *v72; // [rsp+A0h] [rbp-4E8h]
  _QWORD v73[10]; // [rsp+B0h] [rbp-4D8h] BYREF
  _QWORD v74[9]; // [rsp+100h] [rbp-488h] BYREF
  int v75; // [rsp+148h] [rbp-440h]
  _DWORD v76[5]; // [rsp+1B0h] [rbp-3D8h] BYREF
  __int64 v77; // [rsp+1C4h] [rbp-3C4h]
  unsigned __int16 v78[64]; // [rsp+1D0h] [rbp-3B8h] BYREF
  BYTE Data[2]; // [rsp+250h] [rbp-338h] BYREF
  WCHAR SubKey[264]; // [rsp+2C0h] [rbp-2C8h] BYREF
  BYTE v82[112]; // [rsp+4D0h] [rbp-B8h] BYREF

  v63 = a4;
  cbData = a3;
  hMema = hMem;
  hKey = (HKEY)a1;
  v71 = a1;
  v72 = hMem;
  Type = a3;
  LODWORD(v67) = a4;
  v61 = -2147467259;
  v69 = 0;
  v7 = 0;
  v68 = 0;
  LODWORD(v66) = GetCurTime();
  if ( !hMem )
    return 87;
  if ( !a1 )
    return 87;
  if ( LocalFlags(hMem) == 0x8000 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v9 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        LastError = GetLastError();
        v9(4u, L"ProcessGroupPolicyCompletedExInternal: pAsyncHandle memory is invalid, dwStatus = 0x%x", LastError);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v11 = GetLastError();
        RedirectDebugMsg(
          4u,
          L"ProcessGroupPolicyCompletedExInternal: pAsyncHandle memory is invalid, dwStatus = 0x%x",
          v11);
      }
    }
    v12 = cbData;
    v13 = -2147467259;
    goto LABEL_171;
  }
  GuidToString(a1, v78);
  v14 = *(_DWORD *)&g_dwDebugLevel;
  v15 = g_lpDebugMsg;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"ProcessGroupPolicyCompletedExInternal: Entering. Extension = %s, dwStatus = 0x%x", v78, a3);
LABEL_16:
      v14 = *(_DWORD *)&g_dwDebugLevel;
      v15 = g_lpDebugMsg;
      goto LABEL_20;
    }
    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"ProcessGroupPolicyCompletedExInternal: Entering. Extension = %s, dwStatus = 0x%x", v78, a3);
      goto LABEL_16;
    }
  }
LABEL_20:
  if ( !*((_DWORD *)hMem + 2) )
  {
    if ( v14 )
    {
      if ( v15 )
      {
        v15(2u, L"Extension %s asynchronous completion is stale", v78);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"Extension %s asynchronous completion is stale", v78);
      }
    }
    v12 = cbData;
    v13 = -2147467259;
    goto LABEL_171;
  }
  if ( *hMem )
  {
    if ( LocalFlags(*hMem) == 0x8000 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v16 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v17 = GetLastError();
          v16(4u, L"ProcessGroupPolicyCompletedExInternal: pGPOInfo memory is invalid, dwStatus = 0x%x", v17);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v18 = GetLastError();
          RedirectDebugMsg(
            4u,
            L"ProcessGroupPolicyCompletedExInternal: pGPOInfo memory is invalid, dwStatus = 0x%x",
            v18);
        }
      }
      v7 = 0;
      v68 = 0;
      v12 = cbData;
      v13 = -2147467259;
      goto LABEL_171;
    }
    v14 = *(_DWORD *)&g_dwDebugLevel;
    v15 = g_lpDebugMsg;
  }
  v19 = *hMem;
  if ( !*hMem )
  {
    if ( v14 )
    {
      if ( v15 )
      {
        v15(2u, L"Extension %s asynchronous completion has invalid pGPHandle->pGPOInfo", v78);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"Extension %s asynchronous completion has invalid pGPHandle->pGPOInfo", v78);
      }
    }
    v12 = cbData;
    v13 = -2147467259;
    goto LABEL_171;
  }
  v7 = (int *)*hMem;
  v68 = (CGPPolicyEventReporting **)*hMem;
  if ( !*((_DWORD *)v19 + 60) )
  {
    v12 = cbData;
    if ( cbData )
    {
      v13 = 0;
      v61 = 0;
      goto LABEL_171;
    }
    if ( (*(_BYTE *)v19 & 1) != 0 || (v26 = 1, !ExtensionHasPerUserLocalSetting(v78, HKEY_LOCAL_MACHINE)) )
      v26 = 0;
    if ( ReadGPOList(v78, *((HKEY *)v19 + 5), HKEY_LOCAL_MACHINE, *((const unsigned __int16 **)v19 + 9), 1, &v69, v60) )
    {
      if ( SaveGPOList(v78, (struct _GPOINFO *)v19, v27, 0, 0, v69, (int)v60)
        && (!v26
         || SaveGPOList(v78, (struct _GPOINFO *)v19, v28, *((const unsigned __int16 **)v19 + 9), 0, v69, (int)v60)) )
      {
        v13 = 0;
        v61 = 0;
        goto LABEL_171;
      }
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_77;
      v29 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"Extension %s asynchronous completion, failed to save GPOList", v78);
        goto LABEL_77;
      }
      v30 = L"Extension %s asynchronous completion, failed to save GPOList";
    }
    else
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_77;
      v29 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"Extension %s asynchronous completion, failed to read shadow GPOList", v78);
        goto LABEL_77;
      }
      v30 = L"Extension %s asynchronous completion, failed to read shadow GPOList";
    }
    v29(2u, v30, v78);
LABEL_77:
    v13 = -2147467259;
    goto LABEL_171;
  }
  if ( v14 )
  {
    if ( v15 )
    {
      v15(2u, L"Extension %s asynchronous completion, aborting due to machine shutdown or logoff", v78);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(2u, L"Extension %s asynchronous completion, aborting due to machine shutdown or logoff", v78);
    }
  }
  v20 = (unsigned __int16 *)*((_QWORD *)v19 + 33);
  v21 = *((_DWORD *)v19 + 64);
  v22 = GetTickCount() - v21;
  v23 = *((_DWORD *)v19 + 70);
  GPSourceFileId = GetGPSourceFileId(L"ds\\grouppolicy\\client\\gpsvc\\engine\\gpt.cpp");
  LODWORD(lpcbData) = v22;
  LODWORD(phkResult) = v23;
  CGPAdminEventInfo::CGPAdminEventInfo(
    (CGPAdminEventInfo *)v73,
    (__int64)gpEvent_GPO_PROC_STOPPED,
    GPSourceFileId,
    5820,
    (__int64)phkResult,
    (__int64)lpcbData,
    v20);
  CGPPolicyEventReporting::Report(*((CGPPolicyEventReporting **)v19 + 34), (struct CGPEventInfo *)v73, v25);
  v73[0] = &CGPAdminEvent::`vftable';
  CGPEventBase::~CGPEventBase((CGPEventBase *)v73);
  v7 = (int *)v68;
  v12 = cbData;
  v13 = -2147467259;
LABEL_171:
  try
  {
    if ( !v7 )
      goto LABEL_155;
    v31 = 0;
    if ( (*(_BYTE *)v7 & 1) == 0 )
      v31 = (unsigned __int16 *)*((_QWORD *)v7 + 9);
    if ( v12 == 1274 )
    {
      v67 = 0;
      gpGetFgPolicyRefreshInfo(v13, v31, (struct _tagFgPolicyRefreshInfo *)&v67);
      gpSetFgPolicyRefreshInfo(1, v31, v67);
      hKey = (HKEY)0x100000002LL;
      FgPolicyRefreshInfoImpl2 = SetNextFgPolicyRefreshInfoImpl2(v31);
      if ( FgPolicyRefreshInfoImpl2 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(
              4u,
              L"ProcessGroupPolicyCompletedExInternal: SetNextFgPolicyRefreshInfo failed, %d.",
              FgPolicyRefreshInfoImpl2);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(
              4u,
              L"ProcessGroupPolicyCompletedExInternal: SetNextFgPolicyRefreshInfo failed, %d.",
              FgPolicyRefreshInfoImpl2);
          }
        }
      }
      else if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"ProcessGroupPolicyCompletedExInternal: Extension %s requires a synchronous logon.", v78);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(
            2u,
            L"ProcessGroupPolicyCompletedExInternal: Extension %s requires a synchronous logon.",
            v78);
        }
      }
      v13 = v61;
    }
    if ( v13 )
      goto LABEL_155;
    v33 = *v7;
    if ( (*v7 & 1) != 0 || (v34 = 1, !*((_QWORD *)v7 + 9)) )
      v34 = 0;
    v76[3] = 0;
    v77 = 0;
    v76[0] = (v33 >> 18) & 1;
    v76[1] = v7[54];
    v76[2] = v12;
    v76[4] = (_DWORD)v66;
    if ( v34 )
      v35 = (const unsigned __int16 *)*((_QWORD *)v7 + 9);
    else
      v35 = 0;
    WriteStatus(v78, (struct _GPOINFO *)v7, v35, (const BYTE *)v76);
    memset_0(v74, 0, 0xB0u);
    hKey = 0;
    cbData = 0;
    Type = 0;
    v36 = 2147483646;
    v37 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\GPExtensions";
    v38 = 260;
    v39 = SubKey;
    do
    {
      if ( !v36 )
        break;
      v40 = *v37;
      if ( !*v37 )
        break;
      ++v37;
      *v39++ = v40;
      --v36;
      --v38;
    }
    while ( v38 );
    v41 = v39 - 1;
    if ( v38 )
      v41 = v39;
    *v41 = 0;
    v42 = -1;
    do
      ++v42;
    while ( SubKey[v42] );
    if ( SubKey[v42 - 1] != 92 )
      *(_DWORD *)&SubKey[v42] = 92;
    StringCchCatW(SubKey, 0x104u, v78);
    *(_WORD *)Data = 0;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
    {
      v44 = v75;
    }
    else
    {
      cbData = 100;
      if ( RegQueryValueExW(hKey, 0, 0, &Type, Data, &cbData) )
        StringCchCopyW((unsigned __int16 *)Data, 0x32u, v78);
      cbData = 100;
      v43 = RegQueryValueExA(hKey, "ProcessGroupPolicyEx", 0, &Type, v82, &cbData);
      v44 = v75;
      if ( !v43 )
        v44 = 1;
      RegCloseKey(hKey);
    }
    if ( !v7[54] || CoInitializeEx(0, 0) < 0 )
    {
LABEL_149:
      TickCount = GetTickCount();
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(
            4u,
            L"ProcessGroupPolicyCompletedExInternal: Finished processing extension <%ws> at %d ticks (ms)",
            Data,
            TickCount);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(
            4u,
            L"ProcessGroupPolicyCompletedExInternal: Finished processing extension <%ws> at %d ticks (ms)",
            Data,
            TickCount);
        }
      }
LABEL_155:
      v55 = (unsigned int *)hMema;
      if ( hMema && _InterlockedExchangeAdd((volatile signed __int32 *)hMema + 3, 0xFFFFFFFF) == 1 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(
              4u,
              L"ProcessGroupPolicyCompletedExInternal: pGPHandle->dwExtnCount is %d for %s.",
              v55[3],
              v78);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(
              4u,
              L"ProcessGroupPolicyCompletedExInternal: pGPHandle->dwExtnCount is %d for %s.",
              v55[3],
              v78);
          }
        }
        LocalFree(v55);
      }
      FreeGPOListImpl(v69);
      v56 = v61;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(
            4u,
            L"ProcessGroupPolicyCompletedExInternal: Leaving. Extension = %s, Return status dwRet = 0x%x",
            v78,
            v61);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(
            4u,
            L"ProcessGroupPolicyCompletedExInternal: Leaving. Extension = %s, Return status dwRet = 0x%x",
            v78,
            v61);
        }
      }
      return v56;
    }
    v66 = 0;
    GetWbemServices((struct _GPOINFO *)v7, L"\\\\.\\Root\\Rsop", 1, 0, &v66);
    if ( v66 )
    {
      if ( v44 )
      {
        if ( v63 < 0 || (*(_DWORD *)&CGPServiceEventReporting::s_dwTestFlags & 0x40000) != 0 )
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              LODWORD(phkResulta) = v12;
              g_lpDebugMsg(
                4u,
                L"ProcessGroupPolicyCompletedExInternal: Extension %s was not able to log data. Error = 0x%x, dwRet = %d. "
                 "leaving the log dirty",
                v78,
                (unsigned int)v63,
                phkResulta);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              LODWORD(phkResulta) = v12;
              RedirectDebugMsg(
                4u,
                L"ProcessGroupPolicyCompletedExInternal: Extension %s was not able to log data. Error = 0x%x, dwRet = %d. "
                 "leaving the log dirty",
                v78,
                (unsigned int)v63,
                phkResulta);
            }
          }
          v46 = *((_QWORD *)v7 + 33);
          v47 = v7[64];
          v48 = GetTickCount() - v47;
          v49 = v68;
          v50 = *((_DWORD *)v68 + 70);
          v51 = GetGPSourceFileId(L"ds\\grouppolicy\\client\\gpsvc\\engine\\gpt.cpp");
          LODWORD(v60) = (unsigned __int16)v63;
          LODWORD(lpcbData) = v48;
          LODWORD(phkResulta) = v50;
          CGPAdminEventCSEFailure::CGPAdminEventCSEFailure(
            (CGPAdminEventCSEFailure *)v74,
            v52,
            v51,
            6031,
            (__int64)phkResulta,
            (__int64)lpcbData,
            (__int64)v60,
            v46,
            (unsigned __int16 *)Data,
            v78);
          CGPPolicyEventReporting::Report(v49[34], (struct CGPEventInfo *)v74, v53);
          UpdateExtSessionStatus(v66, v78, 1, 0);
          v74[0] = &CGPAdminEventLdapFailure::`vftable';
          CGPAdminEventInitFailure::~CGPAdminEventInitFailure((CGPAdminEventInitFailure *)v74);
          goto LABEL_148;
        }
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            LODWORD(phkResulta) = v12;
            g_lpDebugMsg(
              4u,
              L"ProcessGroupPolicyCompletedExInternal: Extension %s was able to log data. Error = 0x%x, dwRet = %d. Cleari"
               "ng the dirty bit",
              v78,
              (unsigned int)v63,
              phkResulta);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            LODWORD(phkResulta) = v12;
            RedirectDebugMsg(
              4u,
              L"ProcessGroupPolicyCompletedExInternal: Extension %s was able to log data. Error = 0x%x, dwRet = %d. Cleari"
               "ng the dirty bit",
              v78,
              (unsigned int)v63,
              phkResulta);
          }
        }
        v45 = 0;
      }
      else
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"ProcessGroupPolicyCompletedExInternal: Extension %s doesn't support rsop logging.", v78);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(
              4u,
              L"ProcessGroupPolicyCompletedExInternal: Extension %s doesn't support rsop logging.",
              v78);
          }
        }
        v45 = 1;
      }
      UpdateExtSessionStatus(v66, v78, v45, 0);
    }
LABEL_148:
    CoUninitialize();
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v66);
    goto LABEL_149;
  }
  catch ( ... )
  {
    return 574;
  }
  return v56;
}

```

## disassembly

```asm
0x1800689e0  push    rbx
0x1800689e2  push    rsi
0x1800689e3  push    rdi
0x1800689e4  push    r12
0x1800689e6  push    r13
0x1800689e8  push    r14
0x1800689ea  push    r15
0x1800689ec  sub     rsp, 550h
0x1800689f3  mov     rax, cs:__security_cookie
0x1800689fa  xor     rax, rsp
0x1800689fd  mov     [rsp+588h+var_48], rax
0x180068a05  mov     [rsp+588h+var_530], r9d
0x180068a0a  mov     ebx, r8d
0x180068a0d  mov     [rsp+588h+cbData], ebx
0x180068a11  mov     rsi, rdx
0x180068a14  mov     [rsp+588h+hMem], rdx
0x180068a1c  mov     r13, rcx
0x180068a1f  mov     [rsp+588h+hKey], rcx
0x180068a24  mov     [rsp+588h+var_4F0], rcx
0x180068a2c  mov     [rsp+588h+var_4E8], rdx
0x180068a34  mov     [rsp+588h+Type], ebx
0x180068a38  mov     dword ptr [rsp+588h+var_510], r9d
0x180068a3d  mov     edi, 80004005h
0x180068a42  mov     [rsp+588h+var_538], edi
0x180068a46  xor     r14d, r14d
0x180068a49  mov     [rsp+588h+var_500], r14
0x180068a51  mov     edi, r14d
0x180068a54  mov     [rsp+588h+var_508], r14
0x180068a5c  call    ?GetCurTime@@YAKXZ; GetCurTime(void)
0x180068a61  mov     dword ptr [rsp+588h+var_518], eax
0x180068a65  test    rsi, rsi
0x180068a68  jnz     short loc_180068A72
0x180068a6a  lea     eax, [rsi+57h]
0x180068a6d  jmp     loc_180069720
0x180068a72  test    r13, r13
0x180068a75  jnz     short loc_180068A80
0x180068a77  lea     eax, [r13+57h]
0x180068a7b  jmp     loc_180069720
0x180068a80  mov     rcx, rsi; hMem
0x180068a83  call    cs:__imp_LocalFlags
0x180068a89  mov     r15d, 8000h
0x180068a8f  cmp     eax, r15d
0x180068a92  jnz     loc_180068B1C
0x180068a98  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x180068a9f  jz      short loc_180068B02
0x180068aa1  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180068aa8  test    rbx, rbx
0x180068aab  jz      short loc_180068AD0
0x180068aad  call    cs:__imp_GetLastError
0x180068ab3  mov     r8d, eax
0x180068ab6  lea     rdx, aProcessgrouppo_13; "ProcessGroupPolicyCompletedExInternal: "...
0x180068abd  mov     r12d, 4
0x180068ac3  mov     ecx, r12d
0x180068ac6  mov     rax, rbx
0x180068ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068ace  jmp     short loc_180068B08
0x180068ad0  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x180068ad7  jz      short loc_180068B02
0x180068ad9  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180068ae0  jz      short loc_180068B02
0x180068ae2  call    cs:__imp_GetLastError
0x180068ae8  mov     r8d, eax
0x180068aeb  lea     rdx, aProcessgrouppo_13; "ProcessGroupPolicyCompletedExInternal: "...
0x180068af2  mov     r12d, 4
0x180068af8  mov     ecx, r12d; unsigned int
0x180068afb  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180068b00  jmp     short loc_180068ACE
0x180068b02  mov     r12d, 4
0x180068b08  mov     r15d, 1
0x180068b0e  mov     esi, [rsp+588h+cbData]
0x180068b12  mov     ecx, 80004005h
0x180068b17  jmp     loc_18006900D
0x180068b1c  lea     rdx, [rsp+588h+var_3B8]; unsigned __int16 *
0x180068b24  mov     rcx, r13; struct _GUID *
0x180068b27  call    ?GuidToString@@YAXPEBU_GUID@@PEAG@Z; GuidToString(_GUID const *,ushort *)
0x180068b2c  mov     ecx, cs:?g_dwDebugLevel@@3KA; ulong g_dwDebugLevel
0x180068b32  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180068b39  test    ecx, ecx
0x180068b3b  jz      short loc_180068BA5
0x180068b3d  test    rax, rax
0x180068b40  jz      short loc_180068B71
0x180068b42  mov     r9d, ebx
0x180068b45  lea     r8, [rsp+588h+var_3B8]
0x180068b4d  lea     rdx, aProcessgrouppo_12; "ProcessGroupPolicyCompletedExInternal: "...
0x180068b54  mov     r12d, 4
0x180068b5a  mov     ecx, r12d
0x180068b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068b62  mov     ecx, cs:?g_dwDebugLevel@@3KA; ulong g_dwDebugLevel
0x180068b68  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180068b6f  jmp     short loc_180068BAB
0x180068b71  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x180068b78  jz      short loc_180068BA5
0x180068b7a  mov     r12d, 4
0x180068b80  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180068b87  jz      short loc_180068BAB
0x180068b89  mov     r9d, ebx
0x180068b8c  lea     r8, [rsp+588h+var_3B8]
0x180068b94  lea     rdx, aProcessgrouppo_12; "ProcessGroupPolicyCompletedExInternal: "...
0x180068b9b  mov     ecx, r12d; unsigned int
0x180068b9e  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180068ba3  jmp     short loc_180068B62
0x180068ba5  mov     r12d, 4
0x180068bab  cmp     [rsi+8], r14d
0x180068baf  jnz     short loc_180068C15
0x180068bb1  test    ecx, ecx
0x180068bb3  jz      short loc_180068C01
0x180068bb5  test    rax, rax
0x180068bb8  jz      short loc_180068BD5
0x180068bba  lea     r8, [rsp+588h+var_3B8]
0x180068bc2  lea     rdx, aExtensionSAsyn_3; "Extension %s asynchronous completion is"...
0x180068bc9  mov     ecx, 2
0x180068bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068bd3  jmp     short loc_180068C01
0x180068bd5  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x180068bdc  jz      short loc_180068C01
0x180068bde  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180068be5  jz      short loc_180068C01
0x180068be7  lea     r8, [rsp+588h+var_3B8]
0x180068bef  lea     rdx, aExtensionSAsyn_3; "Extension %s asynchronous completion is"...
0x180068bf6  mov     ecx, 2; unsigned int
0x180068bfb  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180068c00  nop
0x180068c01  mov     r15d, 1
0x180068c07  mov     esi, [rsp+588h+cbData]
0x180068c0b  mov     ecx, 80004005h
0x180068c10  jmp     loc_18006900D
0x180068c15  cmp     [rsi], r14
0x180068c18  jz      loc_180068CB4
0x180068c1e  mov     rcx, [rsi]; hMem
0x180068c21  call    cs:__imp_LocalFlags
0x180068c27  cmp     eax, r15d
0x180068c2a  jnz     short loc_180068CA7
0x180068c2c  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x180068c33  jz      short loc_180068C88
0x180068c35  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180068c3c  test    rbx, rbx
0x180068c3f  jz      short loc_180068C5E
0x180068c41  call    cs:__imp_GetLastError
0x180068c47  mov     r8d, eax
0x180068c4a  lea     rdx, aProcessgrouppo_8; "ProcessGroupPolicyCompletedExInternal: "...
0x180068c51  mov     ecx, r12d
0x180068c54  mov     rax, rbx
0x180068c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068c5c  jmp     short loc_180068C88
0x180068c5e  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x180068c65  jz      short loc_180068C88
0x180068c67  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180068c6e  jz      short loc_180068C88
0x180068c70  call    cs:__imp_GetLastError
0x180068c76  mov     r8d, eax
0x180068c79  lea     rdx, aProcessgrouppo_8; "ProcessGroupPolicyCompletedExInternal: "...
0x180068c80  mov     ecx, r12d; unsigned int
0x180068c83  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180068c88  mov     rdi, r14
0x180068c8b  mov     [rsp+588h+var_508], r14
0x180068c93  mov     r15d, 1
0x180068c99  mov     esi, [rsp+588h+cbData]
0x180068c9d  mov     ecx, 80004005h
0x180068ca2  jmp     loc_18006900D
0x180068ca7  mov     ecx, cs:?g_dwDebugLevel@@3KA; ulong g_dwDebugLevel
0x180068cad  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180068cb4  mov     r13, [rsi]
0x180068cb7  test    r13, r13
0x180068cba  jnz     short loc_180068D24
0x180068cbc  test    ecx, ecx
0x180068cbe  jz      short loc_180068D0B
0x180068cc0  test    rax, rax
0x180068cc3  jz      short loc_180068CDF
0x180068cc5  lea     r8, [rsp+588h+var_3B8]
0x180068ccd  lea     rdx, aExtensionSAsyn_1; "Extension %s asynchronous completion ha"...
0x180068cd4  lea     ecx, [r13+2]
0x180068cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068cdd  jmp     short loc_180068D0B
0x180068cdf  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x180068ce6  jz      short loc_180068D0B
0x180068ce8  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180068cef  jz      short loc_180068D0B
0x180068cf1  lea     r8, [rsp+588h+var_3B8]
0x180068cf9  lea     rdx, aExtensionSAsyn_1; "Extension %s asynchronous completion ha"...
0x180068d00  mov     ecx, 2; unsigned int
0x180068d05  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180068d0a  nop
0x180068d0b  mov     r15d, 1
0x180068d11  mov     r13, [rsp+588h+hKey]
0x180068d16  mov     esi, [rsp+588h+cbData]
0x180068d1a  mov     ecx, 80004005h
0x180068d1f  jmp     loc_18006900D
0x180068d24  mov     rdi, r13
0x180068d27  mov     [rsp+588h+var_508], r13
0x180068d2f  cmp     [r13+0F0h], r14d
0x180068d36  jz      loc_180068E34
0x180068d3c  test    ecx, ecx
0x180068d3e  jz      short loc_180068D8B
0x180068d40  test    rax, rax
0x180068d43  jz      short loc_180068D60
0x180068d45  lea     r8, [rsp+588h+var_3B8]
0x180068d4d  lea     rdx, aExtensionSAsyn_0; "Extension %s asynchronous completion, a"...
0x180068d54  mov     ecx, 2
0x180068d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068d5e  jmp     short loc_180068D8B
0x180068d60  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x180068d67  jz      short loc_180068D8B
0x180068d69  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180068d70  jz      short loc_180068D8B
0x180068d72  lea     r8, [rsp+588h+var_3B8]
0x180068d7a  lea     rdx, aExtensionSAsyn_0; "Extension %s asynchronous completion, a"...
0x180068d81  mov     ecx, 2; unsigned int
0x180068d86  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180068d8b  mov     rsi, [r13+108h]
0x180068d92  mov     ebx, [r13+100h]
0x180068d99  call    cs:__imp_GetTickCount
0x180068d9f  mov     edi, eax
0x180068da1  sub     edi, ebx
0x180068da3  mov     ebx, [r13+118h]
0x180068daa  lea     rcx, aDsGrouppolicyC_5; "ds\\grouppolicy\\client\\gpsvc\\engine"...
0x180068db1  call    ?GetGPSourceFileId@@YAKPEBG@Z; GetGPSourceFileId(ushort const *)
0x180068db6  mov     [rsp+588h+var_558], rsi
0x180068dbb  mov     dword ptr [rsp+588h+lpcbData], edi
0x180068dbf  mov     dword ptr [rsp+588h+phkResult], ebx
0x180068dc3  mov     r9d, 16BCh
0x180068dc9  mov     r8d, eax
0x180068dcc  lea     rdx, gpEvent_GPO_PROC_STOPPED
0x180068dd3  lea     rcx, [rsp+588h+var_4D8]
0x180068ddb  call    ??0CGPAdminEventInfo@@QEAA@PEBU_EVENT_DESCRIPTOR@@KKW4ProcessingModeEnum@@KPEBG@Z; CGPAdminEventInfo::CGPAdminEventInfo(_EVENT_DESCRIPTOR const *,ulong,ulong,ProcessingModeEnum,ulong,ushort const *)
0x180068de0  nop
0x180068de1  lea     rdx, [rsp+588h+var_4D8]; struct CGPEventInfo *
0x180068de9  mov     rcx, [r13+110h]; this
0x180068df0  call    ?Report@CGPPolicyEventReporting@@QEAAKPEAVCGPEventInfo@@PEAH@Z; CGPPolicyEventReporting::Report(CGPEventInfo *,int *)
0x180068df5  nop
0x180068df6  lea     rax, ??_7CGPAdminEvent@@6B@; const CGPAdminEvent::`vftable'
0x180068dfd  mov     [rsp+588h+var_4D8], rax
0x180068e05  lea     rcx, [rsp+588h+var_4D8]; this
0x180068e0d  call    ??1CGPEventBase@@UEAA@XZ; CGPEventBase::~CGPEventBase(void)
0x180068e12  nop
0x180068e13  mov     r15d, 1
0x180068e19  mov     rdi, [rsp+588h+var_508]
0x180068e21  mov     r13, [rsp+588h+hKey]
0x180068e26  mov     esi, [rsp+588h+cbData]
0x180068e2a  mov     ecx, 80004005h
0x180068e2f  jmp     loc_18006900D
0x180068e34  mov     esi, [rsp+588h+cbData]
0x180068e38  test    esi, esi
0x180068e3a  jz      short loc_180068E53
0x180068e3c  mov     ecx, r14d
0x180068e3f  mov     [rsp+588h+var_538], ecx
0x180068e43  mov     r15d, 1
0x180068e49  mov     r13, [rsp+588h+hKey]
0x180068e4e  jmp     loc_18006900D
0x180068e53  mov     r15d, 1
0x180068e59  test    [r13+0], r15b
0x180068e5d  jnz     short loc_180068E7A
0x180068e5f  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180068e66  lea     rcx, [rsp+588h+var_3B8]; unsigned __int16 *
0x180068e6e  call    ?ExtensionHasPerUserLocalSetting@@YAHPEBGPEAUHKEY__@@@Z; ExtensionHasPerUserLocalSetting(ushort const *,HKEY__ *)
0x180068e73  test    eax, eax
0x180068e75  mov     ebx, r15d
0x180068e78  jnz     short loc_180068E7D
0x180068e7a  mov     ebx, r14d
0x180068e7d  lea     rax, [rsp+588h+var_500]
0x180068e85  mov     [rsp+588h+lpcbData], rax; struct _GROUP_POLICY_OBJECTW **
0x180068e8a  mov     dword ptr [rsp+588h+phkResult], r15d; int
0x180068e8f  mov     r9, [r13+48h]; unsigned __int16 *
0x180068e93  mov     r8, 0FFFFFFFF80000002h; HKEY
0x180068e9a  mov     rdx, [r13+28h]; HKEY
0x180068e9e  lea     rcx, [rsp+588h+var_3B8]; unsigned __int16 *
0x180068ea6  call    ?ReadGPOList@@YAHPEBGPEAUHKEY__@@10HPEAPEAU_GROUP_POLICY_OBJECTW@@PEAU_GPOINFO@@@Z; ReadGPOList(ushort const *,HKEY__ *,HKEY__ *,ushort const *,int,_GROUP_POLICY_OBJECTW * *,_GPOINFO *)
0x180068eab  test    eax, eax
0x180068ead  jz      loc_180068F77
0x180068eb3  mov     rax, [rsp+588h+var_500]
0x180068ebb  mov     [rsp+588h+lpcbData], rax; struct _GROUP_POLICY_OBJECTW *
0x180068ec0  mov     dword ptr [rsp+588h+phkResult], r14d; int
0x180068ec5  xor     r9d, r9d; unsigned __int16 *
0x180068ec8  mov     rdx, r13; struct _GPOINFO *
0x180068ecb  lea     rcx, [rsp+588h+var_3B8]; unsigned __int16 *
0x180068ed3  call    ?SaveGPOList@@YAHPEBGPEAU_GPOINFO@@PEAUHKEY__@@0HPEAU_GROUP_POLICY_OBJECTW@@H@Z; SaveGPOList(ushort const *,_GPOINFO *,HKEY__ *,ushort const *,int,_GROUP_POLICY_OBJECTW *,int)
0x180068ed8  test    eax, eax
0x180068eda  jz      short loc_180068F16
0x180068edc  test    ebx, ebx
0x180068ede  jz      short loc_180068F0A
0x180068ee0  mov     rax, [rsp+588h+var_500]
0x180068ee8  mov     [rsp+588h+lpcbData], rax; struct _GROUP_POLICY_OBJECTW *
0x180068eed  mov     dword ptr [rsp+588h+phkResult], r14d; int
0x180068ef2  mov     r9, [r13+48h]; unsigned __int16 *
0x180068ef6  mov     rdx, r13; struct _GPOINFO *
0x180068ef9  lea     rcx, [rsp+588h+var_3B8]; unsigned __int16 *
0x180068f01  call    ?SaveGPOList@@YAHPEBGPEAU_GPOINFO@@PEAUHKEY__@@0HPEAU_GROUP_POLICY_OBJECTW@@H@Z; SaveGPOList(ushort const *,_GPOINFO *,HKEY__ *,ushort const *,int,_GROUP_POLICY_OBJECTW *,int)
0x180068f06  test    eax, eax
0x180068f08  jz      short loc_180068F16
0x180068f0a  mov     ecx, r14d
0x180068f0d  mov     [rsp+588h+var_538], ecx
0x180068f11  jmp     loc_180068FC5
0x180068f16  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x180068f1d  jz      loc_180068FC0
0x180068f23  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180068f2a  test    rax, rax
0x180068f2d  jz      short loc_180068F4A
0x180068f2f  lea     rdx, aExtensionSAsyn; "Extension %s asynchronous completion, f"...
0x180068f36  lea     r8, [rsp+588h+var_3B8]
0x180068f3e  mov     ecx, 2
0x180068f43  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```

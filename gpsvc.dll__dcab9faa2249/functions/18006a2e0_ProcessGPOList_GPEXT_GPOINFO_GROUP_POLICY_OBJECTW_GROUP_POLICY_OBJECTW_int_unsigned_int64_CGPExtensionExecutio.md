# ProcessGPOList(_GPEXT *,_GPOINFO *,_GROUP_POLICY_OBJECTW *,_GROUP_POLICY_OBJECTW *,int,unsigned __int64,CGPExtensionExecutionState *,long *)

- ea: `0x18006a2e0`
- end: `0x18006b194`
- name: `?ProcessGPOList@@YAKPEAU_GPEXT@@PEAU_GPOINFO@@PEAU_GROUP_POLICY_OBJECTW@@2H_KPEAVCGPExtensionExecutionState@@PEAJ@Z`
- size: `3764`
- prototype: `unsigned int __usercall@<eax>(struct _GPEXT *@<rcx>, struct _GPOINFO *@<rdx>, struct _GROUP_POLICY_OBJECTW *@<r8>, struct _GROUP_POLICY_OBJECTW *@<r9>, int, unsigned __int64, struct CGPExtensionExecutionState *, int *)`
- caller_count: `2`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180058f20`
- `0x18005ce5c`

## callees

- `0x180001f30`
- `0x180003770`
- `0x180005e10`
- `0x180030bcc`
- `0x18005541c`
- `0x180055e3c`
- `0x180057be4`
- `0x18005c80c`
- `0x180067d58`
- `0x18006a2e0`
- `0x180073984`
- `0x1800739ec`
- `0x1800746f0`
- `0x180075ec0`
- `0x18007d320`
- `0x1800849d4`
- `0x180084ab8`
- `0x18009a4b8`
- `0x1800a1e20`
- `0x1800a427c`
- `0x1800acbd8`
- `0x1800b9ec4`
- `0x1800b9fb4`
- `0x1800ba058`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18006a447`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18006a447`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006b169`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006b169`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a384`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a46a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a49b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006aa19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a384`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a46a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a49b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006aa19`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006ad8e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006afd6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006ad8e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006afd6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006acac`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006acac`
- `api-ms-win-core-sysinfo-l1-2-0!GetOsSafeBootMode` at `0x18006a56e`
- `api-ms-win-core-sysinfo-l1-2-0!GetOsSafeBootMode` at `0x18006a56e`

## string_xrefs

- `0x18006a3d9`: `ProcessGPOList:++ Entering for extension %s`
- `0x18006a403`: `ProcessGPOList:++ Entering for extension %s`
- `0x18006a5af`: `ProcessGPOList: Passing in the rsop transition flag to Extension %s`
- `0x18006a5d8`: `ProcessGPOList: Passing in the rsop transition flag to Extension %s`
- `0x18006a624`: `ProcessGPOList: Passing in the force refresh flag to Extension %s`
- `0x18006a64d`: `ProcessGPOList: Passing in the force refresh flag to Extension %s`
- `0x18006a6c9`: `ProcessGPOList: Couldn't get the wbemservices intf pointer`
- `0x18006a6ee`: `ProcessGPOList: Couldn't get the wbemservices intf pointer`
- `0x18006a74a`: `ProcessGPOList: No changes. CSE will not be passed in the IwbemServices intf ptr`
- `0x18006a770`: `ProcessGPOList: No changes. CSE will not be passed in the IwbemServices intf ptr`
- `0x18006a825`: `ProcessGPOList: ProcessGPORegistryPolicy failed.`
- `0x18006a84a`: `ProcessGPOList: ProcessGPORegistryPolicy failed.`
- `0x18006a8cc`: `ProcessGPOList: Skipping extension %s due to failed Registry extension.`
- `0x18006a8f2`: `ProcessGPOList: Skipping extension %s due to failed Registry extension.`
- `0x18006a9e0`: `ProcessGPOList: LoadGPExtension %s failed.`
- `0x18006aa08`: `ProcessGPOList: LoadGPExtension %s failed.`
- `0x18006acd1`: `ProcessGPOList: Extension %s returned 0x%x.`
- `0x18006ad3f`: `ProcessGPOList: Extension %s returned 0x%x.`
- `0x18006ae75`: `ProcessGPOList: Extension %s was able to log data. RsopStatus = 0x%x, dwRet = %d, Clearing the dirty bit`
- `0x18006aea9`: `ProcessGPOList: Extension %s was able to log data. RsopStatus = 0x%x, dwRet = %d, Clearing the dirty bit`
- `0x18006aee2`: `ProcessGPOList: Extension %s doesn't support rsop logging`
- `0x18006af0f`: `ProcessGPOList: Extension %s doesn't support rsop logging`
- `0x18006af67`: `ProcessGPOList: Extension %s was not able to log data. Error = 0x%x, dwRet = %d,leaving the log dirty`
- `0x18006af9b`: `ProcessGPOList: Extension %s was not able to log data. Error = 0x%x, dwRet = %d,leaving the log dirty`
- `0x18006b0ae`: `ProcessGPOList: Extension %s status was not updated because there was no changes and no transition or rsop wasn't enabled`
- `0x18006b0db`: `ProcessGPOList: Extension %s status was not updated because there was no changes and no transition or rsop wasn't enabled`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ProcessGPOList(
        struct _GPEXT *a1,
        struct _GPOINFO *a2,
        struct _GROUP_POLICY_OBJECTW *a3,
        struct _GROUP_POLICY_OBJECTW *a4,
        int a5,
        unsigned __int64 a6,
        struct CGPExtensionExecutionState *a7,
        int *a8)
{
  struct _GPOINFO *v8; // rsi
  struct _GPEXT *v9; // r15
  DWORD LastError; // ebx
  HINSTANCE HandleForCallingDll; // rax
  void (*v12)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v13; // eax
  DWORD v14; // eax
  int v15; // r8d
  int v16; // edx
  int v17; // ecx
  int v18; // edx
  int v19; // ecx
  int v20; // eax
  int v21; // edi
  struct IWbemServices **v22; // rdi
  struct IWbemServices *v23; // rax
  DWORD v24; // edi
  int v25; // r9d
  int v26; // eax
  int v27; // ecx
  unsigned int *v28; // r15
  int v29; // r9d
  int v30; // eax
  int v31; // ecx
  const unsigned __int16 **v32; // rax
  int v33; // ecx
  CGPNonSystemExtensionDetector *v34; // rcx
  const unsigned __int16 *v35; // rdi
  const unsigned __int16 *v36; // rsi
  unsigned int GPSourceFileId; // eax
  unsigned int v38; // r8d
  int *v39; // r8
  __int64 v40; // rax
  unsigned int v42; // eax
  struct IWbemServices *v43; // r10
  struct IWbemServices *v44; // r10
  const unsigned __int16 **v45; // r12
  const unsigned __int16 *v46; // r14
  const unsigned __int16 *v47; // r15
  __int64 v48; // r12
  int v49; // edi
  DWORD v50; // esi
  unsigned int v51; // edi
  unsigned int v52; // eax
  __int64 v53; // r8
  int *v54; // r8
  struct IWbemServices *v55; // r12
  struct _GPEXT *v56; // r14
  int v57; // r8d
  __int64 v58; // r9
  unsigned __int16 **v59; // r15
  __int64 v60; // r9
  unsigned __int16 *v61; // r14
  unsigned __int16 *v62; // r15
  __int64 v63; // r12
  int v64; // r13d
  int v65; // edi
  DWORD v66; // esi
  int v67; // edi
  unsigned int v68; // eax
  __int64 v69; // rdx
  int *v70; // r8
  int *v71; // rcx
  int v72; // eax
  struct IWbemServices **v74; // [rsp+20h] [rbp-388h]
  __int64 v75; // [rsp+28h] [rbp-380h]
  __int64 v76; // [rsp+30h] [rbp-378h]
  unsigned int v77; // [rsp+60h] [rbp-348h]
  int v78; // [rsp+64h] [rbp-344h]
  unsigned int v79; // [rsp+68h] [rbp-340h]
  int v80; // [rsp+6Ch] [rbp-33Ch] BYREF
  struct _GPEXT *v81; // [rsp+70h] [rbp-338h]
  DWORD v82; // [rsp+78h] [rbp-330h]
  int v83; // [rsp+7Ch] [rbp-32Ch]
  int v84; // [rsp+80h] [rbp-328h]
  struct _GPEXT *v85; // [rsp+88h] [rbp-320h]
  struct IWbemServices *v86; // [rsp+90h] [rbp-318h]
  int *v87; // [rsp+98h] [rbp-310h]
  int v88; // [rsp+A0h] [rbp-308h] BYREF
  struct _GPOINFO *v89; // [rsp+A8h] [rbp-300h]
  DWORD v90; // [rsp+B0h] [rbp-2F8h]
  struct _GROUP_POLICY_OBJECTW *v91; // [rsp+B8h] [rbp-2F0h]
  CGPExtensionExecutionState *v92; // [rsp+C0h] [rbp-2E8h]
  const unsigned __int16 **v93; // [rsp+C8h] [rbp-2E0h]
  struct _GROUP_POLICY_OBJECTW *v94; // [rsp+D0h] [rbp-2D8h]
  const unsigned __int16 **v95; // [rsp+D8h] [rbp-2D0h]
  struct _GPOINFO *v96; // [rsp+E0h] [rbp-2C8h]
  struct _GPEXT *v97; // [rsp+E8h] [rbp-2C0h]
  void **v98; // [rsp+F0h] [rbp-2B8h]
  __int64 v99; // [rsp+F8h] [rbp-2B0h]
  __int64 v100; // [rsp+100h] [rbp-2A8h]
  __int128 v101; // [rsp+108h] [rbp-2A0h]
  _QWORD v102[14]; // [rsp+120h] [rbp-288h] BYREF
  _QWORD v103[14]; // [rsp+190h] [rbp-218h] BYREF
  _OWORD v104[2]; // [rsp+200h] [rbp-1A8h] BYREF
  WCHAR Buffer[56]; // [rsp+220h] [rbp-188h] BYREF
  unsigned __int16 v106[104]; // [rsp+290h] [rbp-118h] BYREF

  v91 = a4;
  v94 = a3;
  v8 = a2;
  v89 = a2;
  v9 = a1;
  v81 = a1;
  v97 = a1;
  v85 = a1;
  v96 = a2;
  v92 = a7;
  v87 = a8;
  v84 = (*(_DWORD *)a2 >> 18) & 1;
  v78 = 0;
  v83 = 0;
  v88 = 0;
  LastError = GetLastError();
  v90 = LastError;
  *a8 = 0;
  v98 = &CGPNonSystemExtensionDetector::`vftable';
  v99 = 0;
  v100 = 0;
  v101 = 0;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"ProcessGPOList:++ Entering for extension %s", *(_QWORD *)v9);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"ProcessGPOList:++ Entering for extension %s", *(_QWORD *)v9);
    }
  }
  if ( *((_QWORD *)v8 + 18) )
  {
    HandleForCallingDll = GetHandleForCallingDll();
    if ( LoadStringW(HandleForCallingDll, 0x6Cu, Buffer, 50) )
    {
      v78 = StringCchPrintfW(v106, 0x64u, Buffer, *(_QWORD *)v9);
      v83 = v78;
      (*((void (__fastcall **)(__int64, unsigned __int16 *))v8 + 18))(1, v106);
    }
    else if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v12 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v13 = GetLastError();
        v12(2u, L"ProcessGPOList: LoadString failed with error %d.", v13);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v14 = GetLastError();
        RedirectDebugMsg(2u, L"ProcessGPOList: LoadString failed with error %d.", v14);
      }
    }
  }
  v15 = *(_DWORD *)v8;
  v16 = *(_DWORD *)v8 & 1 | 0x10;
  if ( (*(_DWORD *)v8 & 0x10000) == 0 )
    v16 = *(_DWORD *)v8 & 1;
  v17 = v16 | 0x1000;
  if ( (v15 & 8) == 0 )
    v17 = v16;
  v18 = v17 | 0x20;
  if ( (v15 & 0x40000) == 0 )
    v18 = v17;
  v19 = v18 | 0x100;
  if ( v84 == **((_DWORD **)v9 + 19) )
    v19 = v18;
  v20 = v19 | 0x40;
  if ( (v15 & 0x80000) == 0 )
    v20 = v19;
  v21 = v20 | 0x80;
  if ( !a5 )
    v21 = v20;
  v88 = 0;
  GetOsSafeBootMode(&v88);
  if ( v88 )
    v21 |= 0x800u;
  v79 = v21;
  if ( *((_DWORD *)v9 + 33) )
  {
    v21 |= 0x200u;
    v79 = v21;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"ProcessGPOList: Passing in the rsop transition flag to Extension %s", *(_QWORD *)v9);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"ProcessGPOList: Passing in the rsop transition flag to Extension %s", *(_QWORD *)v9);
      }
    }
  }
  if ( (*(_DWORD *)v8 & 0x100000) != 0 || (*(_DWORD *)v8 & 0x10000) == 0 && *(_DWORD *)(*((_QWORD *)v9 + 19) + 24LL) )
  {
    v21 |= 0x400u;
    v79 = v21;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"ProcessGPOList: Passing in the force refresh flag to Extension %s", *(_QWORD *)v9);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"ProcessGPOList: Passing in the force refresh flag to Extension %s", *(_QWORD *)v9);
      }
    }
  }
  if ( !*((_DWORD *)v8 + 54) || !*((_DWORD *)v9 + 33) && a5 && (v21 & 0x400) == 0 )
  {
    v23 = 0;
    v86 = 0;
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_67;
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"ProcessGPOList: No changes. CSE will not be passed in the IwbemServices intf ptr");
    }
    else
    {
      if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
        goto LABEL_67;
      RedirectDebugMsg(4u, L"ProcessGPOList: No changes. CSE will not be passed in the IwbemServices intf ptr");
    }
    v23 = 0;
    goto LABEL_67;
  }
  v22 = (struct IWbemServices **)((char *)v8 + 192);
  if ( !*((_QWORD *)v8 + 24)
    && !(unsigned int)GetWbemServices(v8, L"\\\\.\\Root\\Rsop", 0, 0, (struct IWbemServices **)v8 + 24) )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"ProcessGPOList: Couldn't get the wbemservices intf pointer");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"ProcessGPOList: Couldn't get the wbemservices intf pointer");
      }
    }
    *((_DWORD *)v8 + 54) = 0;
    *v87 = -2147467259;
    v78 = -2147467259;
    v83 = -2147467259;
  }
  v23 = *v22;
  v86 = *v22;
LABEL_67:
  v24 = 0;
  v77 = 0;
  v82 = 0;
  if ( *((_DWORD *)v9 + 29) )
  {
    if ( v23 )
    {
      if ( *((_DWORD *)v9 + 33) || (v79 & 0x400) != 0 || (v25 = 0, !a5) )
        v25 = 1;
      v26 = LogExtSessionStatus(v23, v9, 1, v25);
      *((_DWORD *)v8 + 54) = v26;
      v27 = v78;
      if ( !v26 )
        v27 = -2147467259;
      v78 = v27;
    }
    v28 = (unsigned int *)v87;
    if ( !(unsigned int)ProcessGPORegistryPolicy(v8, v91, (unsigned __int16 *)v87) )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"ProcessGPOList: ProcessGPORegistryPolicy failed.");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"ProcessGPOList: ProcessGPORegistryPolicy failed.");
        }
      }
      v24 = -2147467259;
      v77 = -2147467259;
    }
    goto LABEL_154;
  }
  if ( !*((_DWORD *)v9 + 25)
    || (memset(v104, 0, 28), ReadStatus(&c_szRegistryExtName, v8, 0, (struct _GPEXTSTATUS *)v104), DWORD1(v104[1]))
    && !DWORD2(v104[0]) )
  {
    if ( v86 )
    {
      if ( *((_DWORD *)v9 + 33) || (v79 & 0x400) != 0 || (v29 = 0, !a5) )
        v29 = 1;
      v30 = LogExtSessionStatus(v86, v9, *((_DWORD *)v9 + 18), v29);
      *((_DWORD *)v8 + 54) = v30;
      v31 = v78;
      if ( !v30 )
        v31 = -2147467259;
      v78 = v31;
      v83 = v31;
    }
    v80 = 0;
    v32 = (const unsigned __int16 **)((char *)v9 + 8);
    v93 = (const unsigned __int16 **)((char *)v9 + 8);
    if ( v92 )
    {
      CGPExtensionExecutionState::BeginExtensionExecution((HLOCAL *)v92, *v32, &v80);
      v32 = (const unsigned __int16 **)((char *)v9 + 8);
      v33 = v80;
    }
    else
    {
      v33 = 1;
    }
    v95 = v32;
    v84 = v33;
    if ( v33 )
    {
      if ( (unsigned int)LoadGPExtension(v9, 0) )
      {
        v80 = 1;
      }
      else
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"ProcessGPOList: LoadGPExtension %s failed.", *(_QWORD *)v9);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"ProcessGPOList: LoadGPExtension %s failed.", *(_QWORD *)v9);
          }
        }
        v24 = GetLastError();
        v77 = v24;
        v82 = v24;
        v80 = 0;
      }
    }
    else
    {
      v80 = 0;
      v35 = *(const unsigned __int16 **)v9;
      v36 = *v32;
      GPSourceFileId = GetGPSourceFileId(L"ds\\grouppolicy\\client\\gpsvc\\engine\\gpt.cpp");
      CCSEFailureRecoveryAdminEvent::CCSEFailureRecoveryAdminEvent(
        (CCSEFailureRecoveryAdminEvent *)v102,
        GPSourceFileId,
        v38,
        v36,
        v35);
      v8 = v89;
      CGPPolicyEventReporting::Report(*((CGPPolicyEventReporting **)v89 + 34), (struct CGPEventInfo *)v102, v39);
      v102[0] = &CGPAdminEvent::`vftable';
      CGPEventBase::~CGPEventBase((CGPEventBase *)v102);
      v24 = v92 != 0 ? 0xB : 0;
      v77 = v24;
      v82 = v24;
    }
    if ( !*((_DWORD *)v9 + 26)
      || CGPNonSystemExtensionDetector::IsNonReportingSystemExtension(v34, *((const unsigned __int16 **)v9 + 1)) )
    {
      a6 = 0;
    }
    else
    {
      v40 = *((_QWORD *)v8 + 29);
      if ( v40 )
      {
        _InterlockedIncrement((volatile signed __int32 *)(v40 + 12));
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(
              4u,
              L"ProcessGPOList: lpGPOInfo->lpGPInfoHandle->dwExtnCount is %d for %s.",
              *(unsigned int *)(*((_QWORD *)v8 + 29) + 12LL),
              *(_QWORD *)v9);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(
              4u,
              L"ProcessGPOList: lpGPOInfo->lpGPInfoHandle->dwExtnCount is %d for %s.",
              *(unsigned int *)(*((_QWORD *)v8 + 29) + 12LL),
              *(_QWORD *)v9);
          }
        }
      }
    }
    if ( v80 )
    {
      if ( *((_DWORD *)v9 + 18) )
        v42 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, struct _GROUP_POLICY_OBJECTW *, struct _GROUP_POLICY_OBJECTW *, unsigned __int64, __int64, _QWORD, struct IWbemServices *, int *))v9
               + 7))(
                v79,
                *((_QWORD *)v8 + 1),
                *((_QWORD *)v8 + 5),
                v94,
                v91,
                a6,
                (__int64)v8 + 240,
                *((_QWORD *)v8 + 18),
                v86,
                v87);
      else
        v42 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, struct _GROUP_POLICY_OBJECTW *, struct _GROUP_POLICY_OBJECTW *, unsigned __int64, __int64, _QWORD))v9
               + 6))(
                v79,
                *((_QWORD *)v8 + 1),
                *((_QWORD *)v8 + 5),
                v94,
                v91,
                a6,
                (__int64)v8 + 240,
                *((_QWORD *)v8 + 18));
      v82 = v42;
      v77 = v42;
      v24 = v42;
    }
    if ( v84 && v92 )
      CGPExtensionExecutionState::EndExtensionExecution(v92);
    if ( v86 )
    {
      try
      {
        if ( !(unsigned int)CompareGuid(&GUID_GP_SECURITY, (const struct _GUID *)((char *)v9 + 136)) )
          WriteTelemetryForGPSecuritySettings(*(_BYTE *)v8 & 1, v43);
        if ( !(unsigned int)CompareGuid(&GUID_GPP_REGISTRY, (const struct _GUID *)((char *)v9 + 136)) )
          WriteTelemetryForGPPRegistrySettings(*(_BYTE *)v8 & 1, v44);
      }
      catch ( ... )
      {
        v24 = v82;
        v77 = v82;
        v78 = v83;
        LastError = v90;
        v8 = v96;
        v89 = v96;
        v9 = v97;
        v81 = v97;
        v45 = v95;
        goto LABEL_141;
      }
    }
    v45 = v93;
LABEL_141:
    RevertToSelf();
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"ProcessGPOList: Extension %s returned 0x%x.", *(_QWORD *)v9, v24);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"ProcessGPOList: Extension %s returned 0x%x.", *(_QWORD *)v9, v24);
      }
    }
    if ( (v24 && v24 != 1252 && v24 != -2147483638 || (CGPServiceEventReporting::s_dwTestFlags & 0x80u) != 0) && v80 )
    {
      v46 = *v45;
      v47 = *(const unsigned __int16 **)v9;
      v48 = *((_QWORD *)v8 + 33);
      v49 = *((_DWORD *)v8 + 64);
      v50 = GetTickCount() - v49;
      v51 = *((_DWORD *)v89 + 70);
      v52 = GetGPSourceFileId(L"ds\\grouppolicy\\client\\gpsvc\\engine\\gpt.cpp");
      CGPAdminEventCSEFailure::CGPAdminEventCSEFailure(v102, v52, v53, v51, v50, v77, v48, v47, v46);
      v8 = v89;
      CGPPolicyEventReporting::Report(*((CGPPolicyEventReporting **)v89 + 34), (struct CGPEventInfo *)v102, v54);
      v102[0] = &CGPAdminEventLdapFailure::`vftable';
      CGPAdminEventInitFailure::~CGPAdminEventInitFailure((CGPAdminEventInitFailure *)v102);
      v24 = v77;
    }
    v28 = (unsigned int *)v87;
LABEL_154:
    v55 = v86;
    if ( !v86 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(
            4u,
            L"ProcessGPOList: Extension %s status was not updated because there was no changes and no transition or rsop wasn't enabled",
            *(_QWORD *)v81);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(
            4u,
            L"ProcessGPOList: Extension %s status was not updated because there was no changes and no transition or rsop wasn't enabled",
            *(_QWORD *)v81);
        }
      }
      v56 = v85;
      goto LABEL_190;
    }
    v56 = v85;
    if ( v24 != -2147483638 && (*v28 & 0x80000000) == 0 )
    {
      if ( *((_DWORD *)v85 + 18) )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            LODWORD(v74) = v24;
            g_lpDebugMsg(
              4u,
              L"ProcessGPOList: Extension %s was able to log data. RsopStatus = 0x%x, dwRet = %d, Clearing the dirty bit",
              *(_QWORD *)v81,
              *v28,
              v74);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            LODWORD(v74) = v24;
            RedirectDebugMsg(
              4u,
              L"ProcessGPOList: Extension %s was able to log data. RsopStatus = 0x%x, dwRet = %d, Clearing the dirty bit",
              *(_QWORD *)v81,
              *v28,
              v74);
          }
        }
        v57 = 0;
LABEL_173:
        UpdateExtSessionStatus(v55, *((const unsigned __int16 **)v56 + 1), v57, v24);
        goto LABEL_190;
      }
LABEL_166:
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"ProcessGPOList: Extension %s doesn't support rsop logging", *(_QWORD *)v81);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"ProcessGPOList: Extension %s doesn't support rsop logging", *(_QWORD *)v81);
        }
      }
      v57 = 1;
      goto LABEL_173;
    }
    if ( !*((_DWORD *)v85 + 18) )
      goto LABEL_166;
    if ( (*v28 & 0x80000000) == 0 )
    {
LABEL_190:
      v71 = v87;
      if ( *v87 < 0 || (v72 = v78, v78 >= 0) )
        v72 = *v87;
      *v87 = v72;
      if ( !*((_DWORD *)v56 + 18) )
        v72 = -2147024846;
      *v71 = v72;
      goto LABEL_196;
    }
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        LODWORD(v74) = v24;
        v58 = *v28;
        v59 = (unsigned __int16 **)v81;
        g_lpDebugMsg(
          4u,
          L"ProcessGPOList: Extension %s was not able to log data. Error = 0x%x, dwRet = %d,leaving the log dirty",
          *(_QWORD *)v81,
          v58,
          v74);
LABEL_182:
        v61 = (unsigned __int16 *)*((_QWORD *)v56 + 1);
        v62 = *v59;
        v63 = *((_QWORD *)v8 + 33);
        v64 = (unsigned __int16)*v87;
        v65 = *((_DWORD *)v8 + 64);
        v66 = GetTickCount() - v65;
        v67 = *((_DWORD *)v89 + 70);
        v68 = GetGPSourceFileId(L"ds\\grouppolicy\\client\\gpsvc\\engine\\gpt.cpp");
        LODWORD(v76) = v64;
        LODWORD(v75) = v66;
        LODWORD(v74) = v67;
        CGPAdminEventCSEFailure::CGPAdminEventCSEFailure(
          (CGPAdminEventCSEFailure *)v103,
          v69,
          v68,
          5453,
          (__int64)v74,
          v75,
          v76,
          v63,
          v62,
          v61);
        CGPPolicyEventReporting::Report(*((CGPPolicyEventReporting **)v89 + 34), (struct CGPEventInfo *)v103, v70);
        v24 = v77;
        v56 = v85;
        UpdateExtSessionStatus(v86, *((const unsigned __int16 **)v85 + 1), 1, v77);
        v103[0] = &CGPAdminEventLdapFailure::`vftable';
        CGPAdminEventInitFailure::~CGPAdminEventInitFailure((CGPAdminEventInitFailure *)v103);
        goto LABEL_190;
      }
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        LODWORD(v74) = v24;
        v60 = *v28;
        v59 = (unsigned __int16 **)v81;
        RedirectDebugMsg(
          4u,
          L"ProcessGPOList: Extension %s was not able to log data. Error = 0x%x, dwRet = %d,leaving the log dirty",
          *(_QWORD *)v81,
          v60,
          v74);
        goto LABEL_182;
      }
    }
    v59 = (unsigned __int16 **)v81;
    goto LABEL_182;
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"ProcessGPOList: Skipping extension %s due to failed Registry extension.", *(_QWORD *)v9);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"ProcessGPOList: Skipping extension %s due to failed Registry extension.", *(_QWORD *)v9);
    }
  }
  v24 = -2147467259;
LABEL_196:
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"ProcessGPOList:--");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"ProcessGPOList:--");
    }
  }
  SetLastError(LastError);
  return v24;
}

```

## disassembly

```asm
0x18006a2e0  push    rbx
0x18006a2e2  push    rsi
0x18006a2e3  push    rdi
0x18006a2e4  push    r12
0x18006a2e6  push    r13
0x18006a2e8  push    r14
0x18006a2ea  push    r15
0x18006a2ec  sub     rsp, 370h
0x18006a2f3  mov     rax, cs:__security_cookie
0x18006a2fa  xor     rax, rsp
0x18006a2fd  mov     [rsp+3A8h+var_48], rax
0x18006a305  mov     [rsp+3A8h+var_2F0], r9
0x18006a30d  mov     [rsp+3A8h+var_2D8], r8
0x18006a315  mov     rsi, rdx
0x18006a318  mov     [rsp+3A8h+var_300], rdx
0x18006a320  mov     r15, rcx
0x18006a323  mov     [rsp+3A8h+var_338], rcx
0x18006a328  mov     [rsp+3A8h+var_2C0], rcx
0x18006a330  mov     [rsp+3A8h+var_320], rcx
0x18006a338  mov     [rsp+3A8h+var_2C8], rdx
0x18006a340  mov     rax, [rsp+3A8h+arg_30]
0x18006a348  mov     [rsp+3A8h+var_2E8], rax
0x18006a350  mov     r14, [rsp+3A8h+arg_38]
0x18006a358  mov     [rsp+3A8h+var_310], r14
0x18006a360  mov     eax, [rdx]
0x18006a362  shr     eax, 12h
0x18006a365  and     eax, 1
0x18006a368  mov     [rsp+3A8h+var_328], eax
0x18006a36f  xor     r13d, r13d
0x18006a372  mov     [rsp+3A8h+var_344], r13d
0x18006a377  mov     [rsp+3A8h+var_32C], r13d
0x18006a37c  mov     [rsp+3A8h+var_308], r13d
0x18006a384  call    cs:__imp_GetLastError
0x18006a38a  mov     ebx, eax
0x18006a38c  mov     [rsp+3A8h+var_2F8], eax
0x18006a393  mov     [r14], r13d
0x18006a396  lea     rax, ??_7CGPNonSystemExtensionDetector@@6B@; const CGPNonSystemExtensionDetector::`vftable'
0x18006a39d  mov     [rsp+3A8h+var_2B8], rax
0x18006a3a5  mov     [rsp+3A8h+var_2B0], r13
0x18006a3ad  mov     [rsp+3A8h+var_2A8], r13
0x18006a3b5  xorps   xmm0, xmm0
0x18006a3b8  movdqu  [rsp+3A8h+var_2A0], xmm0
0x18006a3c1  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18006a3c8  jz      short loc_18006A41A
0x18006a3ca  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006a3d1  test    rax, rax
0x18006a3d4  jz      short loc_18006A3EE
0x18006a3d6  mov     r8, [r15]
0x18006a3d9  lea     rdx, aProcessgpolist_11; "ProcessGPOList:++ Entering for extensio"...
0x18006a3e0  lea     r14d, [r13+4]
0x18006a3e4  mov     ecx, r14d
0x18006a3e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a3ec  jmp     short loc_18006A420
0x18006a3ee  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18006a3f5  jz      short loc_18006A41A
0x18006a3f7  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006a3fe  jz      short loc_18006A41A
0x18006a400  mov     r8, [r15]
0x18006a403  lea     rdx, aProcessgpolist_11; "ProcessGPOList:++ Entering for extensio"...
0x18006a40a  mov     r14d, 4
0x18006a410  mov     ecx, r14d; unsigned int
0x18006a413  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006a418  jmp     short loc_18006A420
0x18006a41a  mov     r14d, 4
0x18006a420  cmp     [rsi+90h], r13
0x18006a427  jz      loc_18006A4F5
0x18006a42d  call    ?GetHandleForCallingDll@@YAPEAUHINSTANCE__@@XZ; GetHandleForCallingDll(void)
0x18006a432  mov     rcx, rax; hInstance
0x18006a435  mov     r9d, 32h ; '2'; cchBufferMax
0x18006a43b  lea     r8, [rsp+3A8h+Buffer]; lpBuffer
0x18006a443  lea     edx, [r9+3Ah]; uID
0x18006a447  call    cs:__imp_LoadStringW
0x18006a44d  test    eax, eax
0x18006a44f  jnz     short loc_18006A4B7
0x18006a451  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18006a458  jz      loc_18006A4F5
0x18006a45e  mov     rdi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006a465  test    rdi, rdi
0x18006a468  jz      short loc_18006A489
0x18006a46a  call    cs:__imp_GetLastError
0x18006a470  mov     r8d, eax
0x18006a473  lea     rdx, aProcessgpolist_14; "ProcessGPOList: LoadString failed with "...
0x18006a47a  mov     ecx, 2
0x18006a47f  mov     rax, rdi
0x18006a482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a487  jmp     short loc_18006A4F5
0x18006a489  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18006a490  jz      short loc_18006A4F5
0x18006a492  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006a499  jz      short loc_18006A4F5
0x18006a49b  call    cs:__imp_GetLastError
0x18006a4a1  mov     r8d, eax
0x18006a4a4  lea     rdx, aProcessgpolist_14; "ProcessGPOList: LoadString failed with "...
0x18006a4ab  mov     ecx, 2; unsigned int
0x18006a4b0  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006a4b5  jmp     short loc_18006A4F5
0x18006a4b7  mov     r9, [r15]
0x18006a4ba  lea     r8, [rsp+3A8h+Buffer]; unsigned __int16 *
0x18006a4c2  mov     edx, 64h ; 'd'; unsigned __int64
0x18006a4c7  lea     rcx, [rsp+3A8h+var_118]; unsigned __int16 *
0x18006a4cf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006a4d4  mov     [rsp+3A8h+var_344], eax
0x18006a4d8  mov     [rsp+3A8h+var_32C], eax
0x18006a4dc  lea     rdx, [rsp+3A8h+var_118]
0x18006a4e4  mov     ecx, 1
0x18006a4e9  mov     rax, [rsi+90h]
0x18006a4f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a4f5  mov     r8d, [rsi]
0x18006a4f8  mov     ecx, r8d
0x18006a4fb  and     ecx, 1
0x18006a4fe  mov     edx, ecx
0x18006a500  or      edx, 10h
0x18006a503  bt      r8d, 10h
0x18006a508  cmovnb  edx, ecx
0x18006a50b  mov     ecx, edx
0x18006a50d  bts     ecx, 0Ch
0x18006a511  test    r8b, 8
0x18006a515  cmovz   ecx, edx
0x18006a518  mov     edx, ecx
0x18006a51a  or      edx, 20h
0x18006a51d  bt      r8d, 12h
0x18006a522  cmovnb  edx, ecx
0x18006a525  mov     rax, [r15+98h]
0x18006a52c  mov     ecx, edx
0x18006a52e  bts     ecx, 8
0x18006a532  mov     r9d, [rsp+3A8h+var_328]
0x18006a53a  cmp     r9d, [rax]
0x18006a53d  cmovz   ecx, edx
0x18006a540  mov     eax, ecx
0x18006a542  or      eax, 40h
0x18006a545  bt      r8d, 13h
0x18006a54a  cmovnb  eax, ecx
0x18006a54d  mov     edi, eax
0x18006a54f  bts     edi, 7
0x18006a553  cmp     [rsp+3A8h+arg_20], r13d
0x18006a55b  cmovz   edi, eax
0x18006a55e  mov     [rsp+3A8h+var_308], r13d
0x18006a566  lea     rcx, [rsp+3A8h+var_308]
0x18006a56e  call    cs:__imp_GetOsSafeBootMode
0x18006a574  cmp     [rsp+3A8h+var_308], r13d
0x18006a57c  jz      short loc_18006A582
0x18006a57e  bts     edi, 0Bh
0x18006a582  mov     [rsp+3A8h+var_340], edi
0x18006a586  cmp     [r15+84h], r13d
0x18006a58d  jz      short loc_18006A5E7
0x18006a58f  bts     edi, 9
0x18006a593  mov     [rsp+3A8h+var_340], edi
0x18006a597  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18006a59e  jz      short loc_18006A5E7
0x18006a5a0  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006a5a7  test    r9, r9
0x18006a5aa  jz      short loc_18006A5C3
0x18006a5ac  mov     r8, [r15]
0x18006a5af  lea     rdx, aProcessgpolist_6; "ProcessGPOList: Passing in the rsop tra"...
0x18006a5b6  mov     ecx, r14d
0x18006a5b9  mov     rax, r9
0x18006a5bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a5c1  jmp     short loc_18006A5E7
0x18006a5c3  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18006a5ca  jz      short loc_18006A5E7
0x18006a5cc  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006a5d3  jz      short loc_18006A5E7
0x18006a5d5  mov     r8, [r15]
0x18006a5d8  lea     rdx, aProcessgpolist_6; "ProcessGPOList: Passing in the rsop tra"...
0x18006a5df  mov     ecx, r14d; unsigned int
0x18006a5e2  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006a5e7  test    dword ptr [rsi], 100000h
0x18006a5ed  jnz     short loc_18006A604
0x18006a5ef  test    dword ptr [rsi], 10000h
0x18006a5f5  jnz     short loc_18006A65C
0x18006a5f7  mov     rax, [r15+98h]
0x18006a5fe  cmp     [rax+18h], r13d
0x18006a602  jz      short loc_18006A65C
0x18006a604  bts     edi, 0Ah
0x18006a608  mov     [rsp+3A8h+var_340], edi
0x18006a60c  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18006a613  jz      short loc_18006A65C
0x18006a615  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006a61c  test    r9, r9
0x18006a61f  jz      short loc_18006A638
0x18006a621  mov     r8, [r15]
0x18006a624  lea     rdx, aProcessgpolist_13; "ProcessGPOList: Passing in the force re"...
0x18006a62b  mov     ecx, r14d
0x18006a62e  mov     rax, r9
0x18006a631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a636  jmp     short loc_18006A65C
0x18006a638  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18006a63f  jz      short loc_18006A65C
0x18006a641  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006a648  jz      short loc_18006A65C
0x18006a64a  mov     r8, [r15]
0x18006a64d  lea     rdx, aProcessgpolist_13; "ProcessGPOList: Passing in the force re"...
0x18006a654  mov     ecx, r14d; unsigned int
0x18006a657  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006a65c  cmp     [rsi+0D8h], r13d
0x18006a663  jz      loc_18006A72A
0x18006a669  cmp     [r15+84h], r13d
0x18006a670  jnz     short loc_18006A686
0x18006a672  cmp     [rsp+3A8h+arg_20], r13d
0x18006a67a  jz      short loc_18006A686
0x18006a67c  bt      edi, 0Ah
0x18006a680  jnb     loc_18006A72A
0x18006a686  lea     rdi, [rsi+0C0h]
0x18006a68d  cmp     [rdi], r13
0x18006a690  jnz     loc_18006A71D
0x18006a696  mov     [rsp+3A8h+var_388], rdi; struct IWbemServices **
0x18006a69b  xor     r9d, r9d; int *
0x18006a69e  xor     r8d, r8d; int
0x18006a6a1  lea     rdx, aRootRsop_1; "\\\\.\\Root\\Rsop"
0x18006a6a8  mov     rcx, rsi; struct _GPOINFO *
0x18006a6ab  call    ?GetWbemServices@@YAHPEAU_GPOINFO@@PEBGHPEAHPEAPEAUIWbemServices@@@Z; GetWbemServices(_GPOINFO *,ushort const *,int,int *,IWbemServices * *)
0x18006a6b0  test    eax, eax
0x18006a6b2  jnz     short loc_18006A71D
0x18006a6b4  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18006a6bb  jz      short loc_18006A6FF
0x18006a6bd  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006a6c4  test    rax, rax
0x18006a6c7  jz      short loc_18006A6DC
0x18006a6c9  lea     rdx, aProcessgpolist_0; "ProcessGPOList: Couldn't get the wbemse"...
0x18006a6d0  mov     ecx, 2
0x18006a6d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a6da  jmp     short loc_18006A6FF
0x18006a6dc  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18006a6e3  jz      short loc_18006A6FF
0x18006a6e5  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006a6ec  jz      short loc_18006A6FF
0x18006a6ee  lea     rdx, aProcessgpolist_0; "ProcessGPOList: Couldn't get the wbemse"...
0x18006a6f5  mov     ecx, 2; unsigned int
0x18006a6fa  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006a6ff  mov     [rsi+0D8h], r13d
0x18006a706  mov     ecx, 80004005h
0x18006a70b  mov     rax, [rsp+3A8h+var_310]
0x18006a713  mov     [rax], ecx
0x18006a715  mov     [rsp+3A8h+var_344], ecx
0x18006a719  mov     [rsp+3A8h+var_32C], ecx
0x18006a71d  mov     rax, [rdi]
0x18006a720  mov     [rsp+3A8h+var_318], rax
0x18006a728  jmp     short loc_18006A782
0x18006a72a  mov     rax, r13
0x18006a72d  mov     [rsp+3A8h+var_318], rax
0x18006a735  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18006a73c  jz      short loc_18006A782
0x18006a73e  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006a745  test    r9, r9
0x18006a748  jz      short loc_18006A75E
0x18006a74a  lea     rdx, aProcessgpolist_12; "ProcessGPOList: No changes. CSE will no"...
0x18006a751  mov     ecx, r14d
0x18006a754  mov     rax, r9
0x18006a757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a75c  jmp     short loc_18006A77F
0x18006a75e  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18006a765  jz      short loc_18006A782
0x18006a767  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006a76e  jz      short loc_18006A782
0x18006a770  lea     rdx, aProcessgpolist_12; "ProcessGPOList: No changes. CSE will no"...
0x18006a777  mov     ecx, r14d; unsigned int
0x18006a77a  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006a77f  mov     rax, r13
0x18006a782  mov     edi, r13d
0x18006a785  mov     [rsp+3A8h+var_348], r13d
0x18006a78a  mov     [rsp+3A8h+var_330], r13d
0x18006a78f  cmp     [r15+74h], r13d
0x18006a793  jz      loc_18006A869
0x18006a799  test    rax, rax
0x18006a79c  jz      short loc_18006A7ED
0x18006a79e  cmp     [r15+84h], r13d
0x18006a7a5  jnz     short loc_18006A7BE
0x18006a7a7  test    [rsp+3A8h+var_340], 400h
0x18006a7af  jnz     short loc_18006A7BE
0x18006a7b1  cmp     [rsp+3A8h+arg_20], r13d
0x18006a7b9  mov     r9d, r13d
0x18006a7bc  jnz     short loc_18006A7C4
0x18006a7be  mov     r9d, 1; int
0x18006a7c4  mov     r8d, 1; int
0x18006a7ca  mov     rdx, r15; struct _GPEXT *
0x18006a7cd  mov     rcx, rax; struct IWbemServices *
0x18006a7d0  call    ?LogExtSessionStatus@@YAHPEAUIWbemServices@@PEAU_GPEXT@@HH@Z; LogExtSessionStatus(IWbemServices *,_GPEXT *,int,int)
0x18006a7d5  mov     [rsi+0D8h], eax
0x18006a7db  mov     ecx, [rsp+3A8h+var_344]
0x18006a7df  test    eax, eax
0x18006a7e1  mov     eax, 80004005h
0x18006a7e6  cmovz   ecx, eax
0x18006a7e9  mov     [rsp+3A8h+var_344], ecx
0x18006a7ed  mov     r15, [rsp+3A8h+var_310]
0x18006a7f5  mov     r8, r15; int *
0x18006a7f8  mov     rdx, [rsp+3A8h+var_2F0]; struct _GROUP_POLICY_OBJECTW *
0x18006a800  mov     rcx, rsi; struct _GPOINFO *
0x18006a803  call    ?ProcessGPORegistryPolicy@@YAHPEAU_GPOINFO@@PEAU_GROUP_POLICY_OBJECTW@@PEAJ@Z; ProcessGPORegistryPolicy(_GPOINFO *,_GROUP_POLICY_OBJECTW *,long *)
0x18006a808  test    eax, eax
0x18006a80a  jnz     loc_18006AE25
0x18006a810  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18006a817  jz      short loc_18006A85B
0x18006a819  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006a820  test    rax, rax
0x18006a823  jz      short loc_18006A838
0x18006a825  lea     rdx, aProcessgpolist; "ProcessGPOList: ProcessGPORegistryPolic"...
0x18006a82c  mov     ecx, 2
0x18006a831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a836  jmp     short loc_18006A85B
0x18006a838  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
  ... truncated ...
```

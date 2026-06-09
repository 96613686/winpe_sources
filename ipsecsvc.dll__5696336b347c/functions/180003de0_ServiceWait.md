# ServiceWait

- ea: `0x180003de0`
- end: `0x180004768`
- name: `ServiceWait`
- size: `2440`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180001e20`

## callees

- `0x1800013d0`
- `0x180001590`
- `0x180001710`
- `0x180003de0`
- `0x180004770`
- `0x180004840`
- `0x180004910`
- `0x1800049e0`
- `0x180004a30`
- `0x180007160`
- `0x180008744`
- `0x18000acb4`
- `0x18000adac`
- `0x18000e1f8`
- `0x18000e510`
- `0x18000f638`
- `0x18000f660`
- `0x18000f6ac`
- `0x18002cf74`
- `0x18002d2ec`
- `0x18004d090`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004367`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004367`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180003f7b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800041b4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800041ea`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180004223`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180004249`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180004282`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800042c9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800042ef`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800043d9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180003f7b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800041b4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800041ea`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180004223`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180004249`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180004282`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800042c9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800042ef`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800043d9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003f6e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800041dd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000423c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800042e2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003f6e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800041dd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000423c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800042e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004431`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004431`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000407a`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000407a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000450e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000450e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003fe4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003ff3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003fe4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003ff3`
- `FwRemoteSvr!FwRpcAPIsInitialize` at `0x180004472`
- `FwRemoteSvr!FwRpcAPIsInitialize` at `0x180004472`
- `FwRemoteSvr!FwRpcAPIsShutdown` at `0x1800044d3`
- `FwRemoteSvr!FwRpcAPIsShutdown` at `0x1800044d3`

## pseudocode

```c
__int64 ServiceWait()
{
  unsigned int v0; // esi
  int v1; // ebp
  DWORD v2; // r14d
  unsigned int v3; // eax
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  int v6; // ecx
  int v7; // ecx
  DWORD v8; // edi
  DWORD TickCount; // eax
  __int64 CurrentSpdTime; // r15
  _QWORD *v11; // r10
  DWORD v12; // ebx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  DWORD LastError; // eax
  unsigned int v17; // eax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r8
  int v21; // r11d
  int v22; // ecx
  int v23; // eax
  __int64 v24; // rbx
  __int64 v25; // rax
  __int64 v26; // r9
  unsigned int v27; // eax
  unsigned int v28; // ebx
  _QWORD *v29; // rcx
  __int64 v30; // rdx
  __int64 *v31; // r8
  __int64 v32; // r9
  int v34; // [rsp+40h] [rbp-98h] BYREF
  HANDLE Handles[2]; // [rsp+48h] [rbp-90h] BYREF
  __int128 v36; // [rsp+58h] [rbp-80h]
  __int128 v37; // [rsp+68h] [rbp-70h]
  HANDLE v38; // [rsp+78h] [rbp-60h]

  v0 = 0;
  v38 = 0;
  v1 = 0;
  *(_OWORD *)Handles = 0;
  v2 = 6;
  v36 = 0;
  v37 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids,
      "LipsApiCrimsonAuditPolicyChanged");
  v3 = LipsAuditReportCrimsonSecurityEvent(1, 1269628939, 0, 0);
  v4 = v3;
  if ( v3 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids, v3);
        v5 = WPP_GLOBAL_Control;
      }
      if ( v5 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v5 + 28) & 0x10) != 0 )
        {
          WPP_SF_d(v5[2], 16, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids, v4);
          v5 = WPP_GLOBAL_Control;
        }
        if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x10) != 0 )
          WPP_SF_d(v5[2], 10, WPP_15df32206d723562be0133e7e3a0231c_Traceguids, v4);
      }
    }
  }
  Handles[0] = ghServiceStopEvent;
  Handles[1] = ghIfChangeEvent;
  *(_QWORD *)&v36 = ghNewLocalPolicyEvent;
  *((_QWORD *)&v36 + 1) = ghNewDSPolicyEvent;
  *(_QWORD *)&v37 = ghForcedPolicyReloadEvent;
  *((_QWORD *)&v37 + 1) = ghGpupdateRefreshEvent;
  if ( ghFWRmtMgmtEvent )
  {
    v38 = ghFWRmtMgmtEvent;
    v2 = 7;
  }
  StartStatePollingManager(gpIpsecPolicyState);
  SetEvent(ghPolicyChangeNotifyEvent);
  ResetEvent(ghPolicyChangeNotifyEvent);
  v6 = *(_DWORD *)gpIpsecPolicyState;
  if ( (!*(_DWORD *)gpIpsecPolicyState || v6 == 3 || v6 == 11) && gGetListsFromStackError != 1 )
  {
    v7 = gCurrentPollingInterval;
  }
  else
  {
    v7 = gDefaultPollingInterval;
    if ( 60 * (gdwRetryCount + 1) * (gdwRetryCount + 1) < (unsigned int)gDefaultPollingInterval )
      v7 = 60 * (gdwRetryCount + 1) * (gdwRetryCount + 1);
    gCurrentPollingInterval = v7;
  }
  v8 = 1000 * v7;
  if ( !(1000 * v7) )
    v8 = -1;
  if ( !gGlobalTimer )
    gGlobalTimer = GetTickCount();
  TickCount = GetTickCount();
  if ( TickCount < (unsigned int)gGlobalTimer )
    ++HIDWORD(gGlobalTimer);
  LODWORD(gGlobalTimer) = TickCount;
  CurrentSpdTime = gGlobalTimer;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_36;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_30b1e6bcc16c3b7539347dd95346bae4_Traceguids);
    v11 = WPP_GLOBAL_Control;
  }
  do
  {
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 )
      WPP_SF_d(v11[2], 11, WPP_30b1e6bcc16c3b7539347dd95346bae4_Traceguids, v8);
LABEL_36:
    v12 = WaitForMultipleObjectsEx(v2, Handles, 0, v8, 0);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_30b1e6bcc16c3b7539347dd95346bae4_Traceguids, v8);
        v13 = WPP_GLOBAL_Control;
      }
      if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 4) != 0 )
        WPP_SF_(v13[2], 25, WPP_30b1e6bcc16c3b7539347dd95346bae4_Traceguids);
    }
    PADeleteInUseMMPolicies();
    PADeleteInUseMMAuthMethods();
    PADeleteInUseQMPolicies();
    if ( v12 == 6 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_30b1e6bcc16c3b7539347dd95346bae4_Traceguids);
      ResetEvent(ghFWRmtMgmtEvent);
      v34 = 0;
      v17 = IsRemoteManagementEnabled(&v34);
      if ( v17 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_107;
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_196d68d6ad89386858c02b7e955f8655_Traceguids, v17);
        goto LABEL_106;
      }
      EnterCriticalSection(&gcSPDSection);
      if ( v34 )
      {
        if ( gbFWRemoteMgmtActive )
          goto LABEL_105;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_196d68d6ad89386858c02b7e955f8655_Traceguids);
        if ( (unsigned int)FwRpcAPIsInitialize() )
          goto LABEL_105;
        gbFWRemoteMgmtActive = 1;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_105;
        v19 = 20;
      }
      else
      {
        if ( !gbFWRemoteMgmtActive )
          goto LABEL_105;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_196d68d6ad89386858c02b7e955f8655_Traceguids);
        FwRpcAPIsShutdown();
        gbFWRemoteMgmtActive = 0;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_105;
        v19 = 22;
      }
      WPP_SF_(v18[2], v19, WPP_196d68d6ad89386858c02b7e955f8655_Traceguids);
LABEL_105:
      LeaveCriticalSection(&gcSPDSection);
      goto LABEL_106;
    }
    if ( v12 <= 0x102 )
    {
      if ( v12 != 258 )
      {
        switch ( v12 )
        {
          case 0u:
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_30b1e6bcc16c3b7539347dd95346bae4_Traceguids);
              v11 = WPP_GLOBAL_Control;
            }
            v0 = 0;
            v1 = 1;
            break;
          case 1u:
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_30b1e6bcc16c3b7539347dd95346bae4_Traceguids);
            OnInterfaceChangeEvent();
            goto LABEL_106;
          case 2u:
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_30b1e6bcc16c3b7539347dd95346bae4_Traceguids);
            ResetEvent(ghNewLocalPolicyEvent);
            if ( ((*(_DWORD *)gpIpsecPolicyState - 3) & 0xFFFFFFFB) != 0 )
            {
              ProcessLocalPolicyPollState();
              SetEvent(ghPolicyChangeNotifyEvent);
              ResetEvent(ghPolicyChangeNotifyEvent);
            }
            goto LABEL_106;
          case 3u:
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_30b1e6bcc16c3b7539347dd95346bae4_Traceguids);
            ResetEvent(ghNewDSPolicyEvent);
            OnPolicyChanged(gpIpsecPolicyState);
            SetEvent(ghPolicyChangeNotifyEvent);
            ResetEvent(ghPolicyChangeNotifyEvent);
            goto LABEL_106;
          case 4u:
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_30b1e6bcc16c3b7539347dd95346bae4_Traceguids);
            ResetEvent(ghForcedPolicyReloadEvent);
            OnPolicyChanged(gpIpsecPolicyState);
            SetEvent(ghPolicyChangeNotifyEvent);
            ResetEvent(ghPolicyChangeNotifyEvent);
            AuditEventOld(v15, v14, 0x4BAD000Au, 0, 0, 1u);
            goto LABEL_106;
          case 5u:
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_30b1e6bcc16c3b7539347dd95346bae4_Traceguids);
            ResetEvent(ghGpupdateRefreshEvent);
            v0 = ProcessDirectoryPolicyPollState(gpIpsecPolicyState);
            goto LABEL_106;
          default:
            goto LABEL_76;
        }
        goto LABEL_107;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_30b1e6bcc16c3b7539347dd95346bae4_Traceguids);
      CurrentSpdTime = GetCurrentSpdTime();
      OnPolicyPoll();
      OnSpecialAddrsChange();
LABEL_106:
      v11 = WPP_GLOBAL_Control;
      goto LABEL_107;
    }
    if ( v12 != -1 )
    {
LABEL_76:
      v0 = 151;
      v1 = 1;
      goto LABEL_106;
    }
    LastError = GetLastError();
    v0 = LastError;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_30b1e6bcc16c3b7539347dd95346bae4_Traceguids, LastError);
      v11 = WPP_GLOBAL_Control;
    }
    v1 = 1;
LABEL_107:
    v20 = (unsigned int)gdwRetryCount;
    v21 = gGetListsFromStackError;
    v22 = *(_DWORD *)gpIpsecPolicyState;
    if ( (!*(_DWORD *)gpIpsecPolicyState || v22 == 3 || v22 == 11) && gGetListsFromStackError != 1 )
    {
      v23 = gCurrentPollingInterval;
    }
    else
    {
      v23 = gDefaultPollingInterval;
      if ( 60 * (gdwRetryCount + 1) * (gdwRetryCount + 1) < (unsigned int)gDefaultPollingInterval )
        v23 = 60 * (gdwRetryCount + 1) * (gdwRetryCount + 1);
      gCurrentPollingInterval = v23;
    }
    if ( 1000 * v23 )
    {
      v24 = CurrentSpdTime + (unsigned int)(1000 * v23);
      v25 = GetCurrentSpdTime();
      v20 = (unsigned int)gdwRetryCount;
      v11 = WPP_GLOBAL_Control;
      v21 = gGetListsFromStackError;
      v8 = 0;
      if ( v24 > v25 )
        v8 = v24 - v25;
    }
    else
    {
      v8 = -1;
    }
    v26 = *(unsigned int *)gpIpsecPolicyState;
    if ( (_DWORD)v26 && (_DWORD)v26 != 3 && (_DWORD)v26 != 11 || v21 )
    {
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 )
      {
        WPP_SF_dd(v11[2], 23, WPP_30b1e6bcc16c3b7539347dd95346bae4_Traceguids);
        goto LABEL_129;
      }
    }
    else
    {
      gdwRetryCount = 0;
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 )
      {
        WPP_SF_d(v11[2], 22, WPP_30b1e6bcc16c3b7539347dd95346bae4_Traceguids, v26);
LABEL_129:
        v11 = WPP_GLOBAL_Control;
      }
    }
  }
  while ( !v1 );
  if ( v0 )
  {
    AuditOneArgErrorEvent(3417112680LL, v0, v20);
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v30 = 24;
      v31 = WPP_30b1e6bcc16c3b7539347dd95346bae4_Traceguids;
      v32 = v0;
LABEL_148:
      WPP_SF_d(v29[2], v30, v31, v32);
    }
  }
  else
  {
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 )
      WPP_SF_s(v11[2], 14, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids, "LipsApiCrimsonAuditPolicyChanged");
    v27 = LipsAuditReportCrimsonSecurityEvent(1, -1951596493, 0, 0);
    v28 = v27;
    if ( v27 )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids, v27);
          v29 = WPP_GLOBAL_Control;
        }
        if ( v29 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v29 + 28) & 0x10) != 0 )
          {
            WPP_SF_d(v29[2], 16, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids, v28);
            v29 = WPP_GLOBAL_Control;
          }
          if ( v29 != &WPP_GLOBAL_Control && (*((_BYTE *)v29 + 28) & 0x10) != 0 )
          {
            v30 = 10;
            v31 = WPP_15df32206d723562be0133e7e3a0231c_Traceguids;
            v32 = v28;
            goto LABEL_148;
          }
        }
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180003de0  push    rbx
0x180003de2  push    rbp
0x180003de3  push    rsi
0x180003de4  push    rdi
0x180003de5  push    r12
0x180003de7  push    r13
0x180003de9  push    r14
0x180003deb  push    r15
0x180003ded  sub     rsp, 98h
0x180003df4  mov     rax, cs:__security_cookie
0x180003dfb  xor     rax, rsp
0x180003dfe  mov     [rsp+0D8h+var_58], rax
0x180003e06  xor     r13d, r13d
0x180003e09  xorps   xmm0, xmm0
0x180003e0c  xor     eax, eax
0x180003e0e  mov     esi, r13d
0x180003e11  mov     [rsp+0D8h+var_60], rax
0x180003e16  mov     ebp, r13d
0x180003e19  movups  xmmword ptr [rsp+0D8h+Handles], xmm0
0x180003e1e  mov     r14d, 6
0x180003e24  movups  [rsp+0D8h+var_80], xmm0
0x180003e29  movups  [rsp+0D8h+var_70], xmm0
0x180003e2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e35  lea     r12, WPP_GLOBAL_Control
0x180003e3c  cmp     rcx, r12
0x180003e3f  jz      short loc_180003E63
0x180003e41  test    byte ptr [rcx+1Ch], 4
0x180003e45  jz      short loc_180003E63
0x180003e47  mov     rcx, [rcx+10h]
0x180003e4b  lea     r9, aLipsapicrimson; "LipsApiCrimsonAuditPolicyChanged"
0x180003e52  mov     edx, 0Eh
0x180003e57  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x180003e5e  call    WPP_SF_s
0x180003e63  xor     r9d, r9d
0x180003e66  xor     r8d, r8d
0x180003e69  mov     edx, 4BAD000Bh
0x180003e6e  mov     ecx, 1
0x180003e73  call    LipsAuditReportCrimsonSecurityEvent
0x180003e78  mov     ebx, eax
0x180003e7a  test    eax, eax
0x180003e7c  jz      short loc_180003EFC
0x180003e7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e85  cmp     rcx, r12
0x180003e88  jz      short loc_180003EFC
0x180003e8a  test    byte ptr [rcx+1Ch], 10h
0x180003e8e  jz      short loc_180003EAF
0x180003e90  mov     rcx, [rcx+10h]
0x180003e94  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x180003e9b  mov     edx, 0Fh
0x180003ea0  mov     r9d, eax
0x180003ea3  call    WPP_SF_d
0x180003ea8  mov     rcx, cs:WPP_GLOBAL_Control
0x180003eaf  cmp     rcx, r12
0x180003eb2  jz      short loc_180003EFC
0x180003eb4  test    byte ptr [rcx+1Ch], 10h
0x180003eb8  jz      short loc_180003ED9
0x180003eba  mov     rcx, [rcx+10h]
0x180003ebe  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x180003ec5  mov     edx, 10h
0x180003eca  mov     r9d, ebx
0x180003ecd  call    WPP_SF_d
0x180003ed2  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ed9  cmp     rcx, r12
0x180003edc  jz      short loc_180003EFC
0x180003ede  test    byte ptr [rcx+1Ch], 10h
0x180003ee2  jz      short loc_180003EFC
0x180003ee4  mov     rcx, [rcx+10h]
0x180003ee8  lea     r8, WPP_15df32206d723562be0133e7e3a0231c_Traceguids
0x180003eef  mov     edx, 0Ah
0x180003ef4  mov     r9d, ebx
0x180003ef7  call    WPP_SF_d
0x180003efc  mov     rax, cs:ghServiceStopEvent
0x180003f03  mov     [rsp+0D8h+Handles], rax
0x180003f08  mov     rax, cs:ghIfChangeEvent
0x180003f0f  mov     [rsp+0D8h+Handles+8], rax
0x180003f14  mov     rax, cs:ghNewLocalPolicyEvent
0x180003f1b  mov     qword ptr [rsp+0D8h+var_80], rax
0x180003f20  mov     rax, cs:ghNewDSPolicyEvent
0x180003f27  mov     qword ptr [rsp+0D8h+var_80+8], rax
0x180003f2c  mov     rax, cs:ghForcedPolicyReloadEvent
0x180003f33  mov     qword ptr [rsp+0D8h+var_70], rax
0x180003f38  mov     rax, cs:ghGpupdateRefreshEvent
0x180003f3f  mov     qword ptr [rsp+0D8h+var_70+8], rax
0x180003f44  mov     rax, cs:ghFWRmtMgmtEvent
0x180003f4b  test    rax, rax
0x180003f4e  jz      short loc_180003F5B
0x180003f50  mov     [rsp+0D8h+var_60], rax
0x180003f55  mov     r14d, 7
0x180003f5b  mov     rcx, cs:gpIpsecPolicyState
0x180003f62  call    StartStatePollingManager
0x180003f67  mov     rcx, cs:ghPolicyChangeNotifyEvent; hEvent
0x180003f6e  call    cs:__imp_SetEvent
0x180003f74  mov     rcx, cs:ghPolicyChangeNotifyEvent; hEvent
0x180003f7b  call    cs:__imp_ResetEvent
0x180003f81  mov     rax, cs:gpIpsecPolicyState
0x180003f88  mov     ecx, [rax]
0x180003f8a  test    ecx, ecx
0x180003f8c  jz      short loc_180003F98
0x180003f8e  cmp     ecx, 3
0x180003f91  jz      short loc_180003F98
0x180003f93  cmp     ecx, 0Bh
0x180003f96  jnz     short loc_180003FA1
0x180003f98  cmp     cs:gGetListsFromStackError, 1
0x180003f9f  jnz     short loc_180003FC5
0x180003fa1  mov     eax, cs:gdwRetryCount
0x180003fa7  lea     ecx, [rax+1]
0x180003faa  inc     eax
0x180003fac  imul    ecx, eax
0x180003faf  imul    eax, ecx, 3Ch ; '<'
0x180003fb2  mov     ecx, cs:gDefaultPollingInterval
0x180003fb8  cmp     eax, ecx
0x180003fba  cmovb   ecx, eax
0x180003fbd  mov     cs:gCurrentPollingInterval, ecx
0x180003fc3  jmp     short loc_180003FCB
0x180003fc5  mov     ecx, cs:gCurrentPollingInterval
0x180003fcb  imul    edi, ecx, 3E8h
0x180003fd1  mov     eax, 0FFFFFFFFh
0x180003fd6  test    edi, edi
0x180003fd8  cmovz   edi, eax
0x180003fdb  cmp     cs:gGlobalTimer, rsi
0x180003fe2  jnz     short loc_180003FF3
0x180003fe4  call    cs:__imp_GetTickCount
0x180003fea  mov     eax, eax
0x180003fec  mov     cs:gGlobalTimer, rax
0x180003ff3  call    cs:__imp_GetTickCount
0x180003ff9  cmp     eax, dword ptr cs:gGlobalTimer
0x180003fff  jnb     short loc_180004007
0x180004001  inc     dword ptr cs:gGlobalTimer+4
0x180004007  mov     dword ptr cs:gGlobalTimer, eax
0x18000400d  mov     r15, cs:gGlobalTimer
0x180004014  mov     r10, cs:WPP_GLOBAL_Control
0x18000401b  cmp     r10, r12
0x18000401e  jz      short loc_180004067
0x180004020  test    byte ptr [r10+1Ch], 4
0x180004025  jz      short loc_180004043
0x180004027  mov     rcx, [r10+10h]
0x18000402b  lea     r8, WPP_30b1e6bcc16c3b7539347dd95346bae4_Traceguids
0x180004032  mov     edx, 0Ah
0x180004037  call    WPP_SF_
0x18000403c  mov     r10, cs:WPP_GLOBAL_Control
0x180004043  cmp     r10, r12
0x180004046  jz      short loc_180004067
0x180004048  test    byte ptr [r10+1Ch], 4
0x18000404d  jz      short loc_180004067
0x18000404f  mov     rcx, [r10+10h]
0x180004053  lea     r8, WPP_30b1e6bcc16c3b7539347dd95346bae4_Traceguids
0x18000405a  mov     edx, 0Bh
0x18000405f  mov     r9d, edi
0x180004062  call    WPP_SF_d
0x180004067  mov     r9d, edi; dwMilliseconds
0x18000406a  mov     [rsp+0D8h+bAlertable], r13d; bAlertable
0x18000406f  xor     r8d, r8d; bWaitAll
0x180004072  lea     rdx, [rsp+0D8h+Handles]; lpHandles
0x180004077  mov     ecx, r14d; nCount
0x18000407a  call    cs:__imp_WaitForMultipleObjectsEx
0x180004080  mov     ebx, eax
0x180004082  mov     rcx, cs:WPP_GLOBAL_Control
0x180004089  cmp     rcx, r12
0x18000408c  jz      short loc_1800040D3
0x18000408e  test    byte ptr [rcx+1Ch], 4
0x180004092  jz      short loc_1800040B3
0x180004094  mov     rcx, [rcx+10h]
0x180004098  lea     r8, WPP_30b1e6bcc16c3b7539347dd95346bae4_Traceguids
0x18000409f  mov     edx, 0Ch
0x1800040a4  mov     r9d, edi
0x1800040a7  call    WPP_SF_d
0x1800040ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040b3  cmp     rcx, r12
0x1800040b6  jz      short loc_1800040D3
0x1800040b8  test    byte ptr [rcx+1Ch], 4
0x1800040bc  jz      short loc_1800040D3
0x1800040be  mov     rcx, [rcx+10h]
0x1800040c2  lea     r8, WPP_30b1e6bcc16c3b7539347dd95346bae4_Traceguids
0x1800040c9  mov     edx, 19h
0x1800040ce  call    WPP_SF_
0x1800040d3  call    PADeleteInUseMMPolicies
0x1800040d8  call    PADeleteInUseMMAuthMethods
0x1800040dd  call    PADeleteInUseQMPolicies
0x1800040e2  cmp     ebx, 6
0x1800040e5  jz      loc_1800043AB
0x1800040eb  cmp     ebx, 102h
0x1800040f1  ja      loc_180004353
0x1800040f7  jz      loc_180004315
0x1800040fd  cmp     ebx, 5; switch 6 cases
0x180004100  ja      def_180004117; jumptable 0000000180004117 default case
0x180004106  lea     rcx, __ImageBase
0x18000410d  mov     eax, ds:(jpt_180004117 - 180000000h)[rcx+rbx*4]
0x180004114  add     rax, rcx
0x180004117  jmp     rax; switch jump
0x180004119  mov     r10, cs:WPP_GLOBAL_Control; jumptable 0000000180004117 case 0
0x180004120  cmp     r10, r12
0x180004123  jz      short loc_180004148
0x180004125  test    byte ptr [r10+1Ch], 4
0x18000412a  jz      short loc_180004148
0x18000412c  mov     rcx, [r10+10h]
0x180004130  lea     r8, WPP_30b1e6bcc16c3b7539347dd95346bae4_Traceguids
0x180004137  mov     edx, 0Dh
0x18000413c  call    WPP_SF_
0x180004141  mov     r10, cs:WPP_GLOBAL_Control
0x180004148  mov     esi, r13d
0x18000414b  mov     ebp, 1
0x180004150  jmp     loc_18000451B
0x180004155  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000180004117 case 1
0x18000415c  cmp     rcx, r12
0x18000415f  jz      short loc_18000417C
0x180004161  test    byte ptr [rcx+1Ch], 4
0x180004165  jz      short loc_18000417C
0x180004167  mov     rcx, [rcx+10h]
0x18000416b  lea     r8, WPP_30b1e6bcc16c3b7539347dd95346bae4_Traceguids
0x180004172  mov     edx, 0Eh
0x180004177  call    WPP_SF_
0x18000417c  call    OnInterfaceChangeEvent
0x180004181  jmp     loc_180004514
0x180004186  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000180004117 case 2
0x18000418d  cmp     rcx, r12
0x180004190  jz      short loc_1800041AD
0x180004192  test    byte ptr [rcx+1Ch], 4
0x180004196  jz      short loc_1800041AD
0x180004198  mov     rcx, [rcx+10h]
0x18000419c  lea     r8, WPP_30b1e6bcc16c3b7539347dd95346bae4_Traceguids
0x1800041a3  mov     edx, 0Fh
0x1800041a8  call    WPP_SF_
0x1800041ad  mov     rcx, cs:ghNewLocalPolicyEvent; hEvent
0x1800041b4  call    cs:__imp_ResetEvent
0x1800041ba  mov     rcx, cs:gpIpsecPolicyState
0x1800041c1  mov     eax, [rcx]
0x1800041c3  sub     eax, 3
0x1800041c6  test    eax, 0FFFFFFFBh
0x1800041cb  jz      loc_180004514
0x1800041d1  call    ProcessLocalPolicyPollState
0x1800041d6  mov     rcx, cs:ghPolicyChangeNotifyEvent; hEvent
0x1800041dd  call    cs:__imp_SetEvent
0x1800041e3  mov     rcx, cs:ghPolicyChangeNotifyEvent; hEvent
0x1800041ea  call    cs:__imp_ResetEvent
0x1800041f0  jmp     loc_180004514
0x1800041f5  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000180004117 case 3
0x1800041fc  cmp     rcx, r12
0x1800041ff  jz      short loc_18000421C
0x180004201  test    byte ptr [rcx+1Ch], 4
0x180004205  jz      short loc_18000421C
0x180004207  mov     rcx, [rcx+10h]
0x18000420b  lea     r8, WPP_30b1e6bcc16c3b7539347dd95346bae4_Traceguids
0x180004212  mov     edx, 10h
0x180004217  call    WPP_SF_
0x18000421c  mov     rcx, cs:ghNewDSPolicyEvent; hEvent
0x180004223  call    cs:__imp_ResetEvent
0x180004229  mov     rcx, cs:gpIpsecPolicyState
0x180004230  call    OnPolicyChanged
0x180004235  mov     rcx, cs:ghPolicyChangeNotifyEvent; hEvent
0x18000423c  call    cs:__imp_SetEvent
0x180004242  mov     rcx, cs:ghPolicyChangeNotifyEvent; hEvent
0x180004249  call    cs:__imp_ResetEvent
0x18000424f  jmp     loc_180004514
0x180004254  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000180004117 case 5
0x18000425b  cmp     rcx, r12
0x18000425e  jz      short loc_18000427B
0x180004260  test    byte ptr [rcx+1Ch], 4
0x180004264  jz      short loc_18000427B
0x180004266  mov     rcx, [rcx+10h]
0x18000426a  lea     r8, WPP_30b1e6bcc16c3b7539347dd95346bae4_Traceguids
0x180004271  mov     edx, 11h
0x180004276  call    WPP_SF_
0x18000427b  mov     rcx, cs:ghGpupdateRefreshEvent; hEvent
0x180004282  call    cs:__imp_ResetEvent
0x180004288  mov     rcx, cs:gpIpsecPolicyState
0x18000428f  call    ProcessDirectoryPolicyPollState
0x180004294  mov     esi, eax
0x180004296  jmp     loc_180004514
0x18000429b  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000180004117 case 4
0x1800042a2  cmp     rcx, r12
0x1800042a5  jz      short loc_1800042C2
0x1800042a7  test    byte ptr [rcx+1Ch], 4
0x1800042ab  jz      short loc_1800042C2
0x1800042ad  mov     rcx, [rcx+10h]
0x1800042b1  lea     r8, WPP_30b1e6bcc16c3b7539347dd95346bae4_Traceguids
0x1800042b8  mov     edx, 12h
0x1800042bd  call    WPP_SF_
0x1800042c2  mov     rcx, cs:ghForcedPolicyReloadEvent; hEvent
0x1800042c9  call    cs:__imp_ResetEvent
0x1800042cf  mov     rcx, cs:gpIpsecPolicyState
0x1800042d6  call    OnPolicyChanged
0x1800042db  mov     rcx, cs:ghPolicyChangeNotifyEvent; hEvent
0x1800042e2  call    cs:__imp_SetEvent
0x1800042e8  mov     rcx, cs:ghPolicyChangeNotifyEvent; hEvent
0x1800042ef  call    cs:__imp_ResetEvent
0x1800042f5  xor     r9d, r9d
0x1800042f8  mov     [rsp+0D8h+var_B0], 1
0x180004300  mov     r8d, 4BAD000Ah
0x180004306  mov     [rsp+0D8h+bAlertable], r13d
0x18000430b  call    AuditEventOld
0x180004310  jmp     loc_180004514
0x180004315  mov     rcx, cs:WPP_GLOBAL_Control
0x18000431c  cmp     rcx, r12
0x18000431f  jz      short loc_18000433C
0x180004321  test    byte ptr [rcx+1Ch], 4
0x180004325  jz      short loc_18000433C
0x180004327  mov     rcx, [rcx+10h]
0x18000432b  lea     r8, WPP_30b1e6bcc16c3b7539347dd95346bae4_Traceguids
0x180004332  mov     edx, 14h
0x180004337  call    WPP_SF_
  ... truncated ...
```

# Scavenger

- ea: `0x180051cfc`
- end: `0x1800524cc`
- name: `Scavenger`
- size: `2000`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027ce0`

## callees

- `0x180002854`
- `0x180002898`
- `0x180003548`
- `0x180003864`
- `0x180004ce4`
- `0x1800057f4`
- `0x18000d0c8`
- `0x18001d098`
- `0x18001e828`
- `0x180020964`
- `0x180025264`
- `0x180025424`
- `0x180029ab8`
- `0x180033948`
- `0x180036420`
- `0x180050260`
- `0x1800519fc`
- `0x180051a60`
- `0x180051cfc`
- `0x180062964`
- `0x1800672f0`
- `0x18006760c`
- `0x18007811c`
- `0x18007abcc`
- `0x18008ef3c`
- `0x1800b5590`
- `0x1800cc9e0`

## import_xrefs

- `msvcrt!time` at `0x180051df5`
- `msvcrt!time` at `0x180051f69`
- `msvcrt!time` at `0x180051f8c`
- `msvcrt!time` at `0x180052096`
- `msvcrt!time` at `0x180052474`
- `msvcrt!time` at `0x180051df5`
- `msvcrt!time` at `0x180051f69`
- `msvcrt!time` at `0x180051f8c`
- `msvcrt!time` at `0x180052096`
- `msvcrt!time` at `0x180052474`
- `KERNEL32!ResetEvent` at `0x180052486`
- `KERNEL32!ResetEvent` at `0x180052486`
- `KERNEL32!GetLocalTime` at `0x1800522bc`
- `KERNEL32!GetLocalTime` at `0x1800522bc`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180052023`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180052023`
- `KERNEL32!CompareFileTime` at `0x180051f03`
- `KERNEL32!CompareFileTime` at `0x180051f03`
- `KERNEL32!EnterCriticalSection` at `0x180051e11`
- `KERNEL32!EnterCriticalSection` at `0x180051e24`
- `KERNEL32!EnterCriticalSection` at `0x180052251`
- `KERNEL32!EnterCriticalSection` at `0x1800522db`
- `KERNEL32!EnterCriticalSection` at `0x18005233e`
- `KERNEL32!EnterCriticalSection` at `0x180051e11`
- `KERNEL32!EnterCriticalSection` at `0x180051e24`
- `KERNEL32!EnterCriticalSection` at `0x180052251`
- `KERNEL32!EnterCriticalSection` at `0x1800522db`
- `KERNEL32!EnterCriticalSection` at `0x18005233e`
- `KERNEL32!LeaveCriticalSection` at `0x180051e42`
- `KERNEL32!LeaveCriticalSection` at `0x180051e55`
- `KERNEL32!LeaveCriticalSection` at `0x180052270`
- `KERNEL32!LeaveCriticalSection` at `0x18005232b`
- `KERNEL32!LeaveCriticalSection` at `0x180052392`
- `KERNEL32!LeaveCriticalSection` at `0x180051e42`
- `KERNEL32!LeaveCriticalSection` at `0x180051e55`
- `KERNEL32!LeaveCriticalSection` at `0x180052270`
- `KERNEL32!LeaveCriticalSection` at `0x18005232b`
- `KERNEL32!LeaveCriticalSection` at `0x180052392`

## pseudocode

```c
__int64 __fastcall Scavenger(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v4; // r12d
  int v5; // r13d
  unsigned int v6; // edi
  char *v7; // rbx
  __int64 v8; // rcx
  unsigned int v9; // ebx
  unsigned __int64 v11; // rbx
  FILETIME v12; // r8
  _QWORD *v13; // r9
  unsigned int v14; // r15d
  __int64 v15; // rdx
  __int64 v16; // rcx
  char *v17; // rcx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  HANDLE v20; // rax
  DWORD v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rcx
  __int64 v26; // rdx
  void *v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // ebx
  unsigned int v34; // eax
  unsigned int v35; // ebx
  unsigned int v36; // ebx
  int v37; // ebx
  __int64 v38; // rdx
  __int64 v39; // rcx
  int v40; // ebx
  __int64 v41; // rdx
  __int64 v42; // rcx
  unsigned int v43; // eax
  __int64 v44; // rcx
  unsigned int v45; // eax
  FILETIME DateTime; // [rsp+40h] [rbp-91h] BYREF
  FILETIME FileTime1; // [rsp+48h] [rbp-89h] BYREF
  FILETIME FileTime2; // [rsp+50h] [rbp-81h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+58h] [rbp-79h] BYREF
  HANDLE Handles; // [rsp+68h] [rbp-69h] BYREF
  HANDLE hEvent; // [rsp+70h] [rbp-61h]
  HANDLE v52; // [rsp+78h] [rbp-59h]
  int *v53; // [rsp+88h] [rbp-49h]
  _QWORD v54[9]; // [rsp+90h] [rbp-41h] BYREF
  char v55[16]; // [rsp+D8h] [rbp+7h] BYREF
  char v56[16]; // [rsp+E8h] [rbp+17h] BYREF

  v4 = 1;
  v5 = 0;
  SystemTime = 0;
  DateTime = (FILETIME)DhcpGetDateTime(a1, a2, a3, a4);
  v53 = &DhcpGlobalScavengerTimeout;
  v54[0] = DateTime;
  v54[1] = &DhcpGlobalBackupInterval;
  v54[2] = DateTime;
  v54[4] = DateTime;
  v54[6] = DateTime;
  v54[8] = DateTime;
  v54[3] = &DhcpGlobalCleanupInterval;
  v52 = DhcpGlobalRecomputeTimerEvent;
  v54[5] = &DhcpGlobalScavengeIpAddressInterval;
  Handles = DhcpGlobalProcessTerminationEvent;
  v54[7] = &DhcpGlobalScavengeStatelessInterval;
  hEvent = DhcpGlobalRogueWaitEvent;
  DhcpRegGetValue(DhcpGlobalRegParam, L"DisableRogueDetection");
  v6 = RogueDetectStateMachine(0);
  if ( v6 != -1 )
    v6 += time(0);
  v7 = (char *)DhcpGlobalThisServerV6;
  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  EnterCriticalSection(&DhcpGlobalStatelessCritSect);
  v9 = DhcpCountStatelessRecordsPerSubnet(v8, v7 + 112);
  LeaveCriticalSection(&DhcpGlobalStatelessCritSect);
  LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  if ( !v9 )
  {
    LODWORD(v11) = 0;
    while ( 1 )
    {
      v12 = (FILETIME)-1LL;
      FileTime2 = 0;
      FileTime1 = (FILETIME)-1LL;
      v13 = v54;
      v14 = 0;
      LODWORD(v15) = 0;
      do
      {
        v16 = *(unsigned int *)*(v13 - 1);
        if ( *v13 + 10000 * v16 < *(unsigned __int64 *)&v12 )
        {
          v12 = (FILETIME)(*v13 + 10000 * v16);
          FileTime1 = v12;
          v14 = v15;
        }
        v15 = (unsigned int)(v15 + 1);
        v13 += 2;
      }
      while ( (unsigned int)v15 < 5 );
      FileTime2 = (FILETIME)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))DhcpGetDateTime)(
                              v16,
                              v15,
                              v12,
                              v13);
      if ( CompareFileTime(&FileTime1, &FileTime2) > 0 )
        v11 = (*(_QWORD *)&FileTime1 - *(_QWORD *)&FileTime2) / 0x2710uLL;
      v17 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids, v14, v11);
        v17 = (char *)WPP_GLOBAL_Control;
      }
      if ( v6 == -1 )
        goto LABEL_26;
      v18 = time(0);
      if ( v18 < v6 )
        goto LABEL_22;
      v6 = RogueDetectStateMachine(0);
      if ( v6 != -1 )
        break;
LABEL_25:
      v17 = (char *)WPP_GLOBAL_Control;
LABEL_26:
      if ( v17 != (char *)&WPP_GLOBAL_Control && v17[28] < 0 )
        WPP_SF_D(*((_QWORD *)v17 + 2), 32, &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids, (unsigned int)v11 / 0x3E8);
      v20 = DhcpGlobalRogueWaitEvent;
      if ( v6 == -1 )
        v20 = DhcpGlobalGenericEndpointReadyEvent;
      hEvent = v20;
      DhcpDnsHandleCallbacks();
      Dhcpv6DnsHandleCallbacks();
      v21 = WaitForMultipleObjectsEx(3u, &Handles, 0, v11, 1);
      LODWORD(v11) = 0;
      if ( !v21 )
      {
        DhcpTelemetryReportInfo(0);
        return 0;
      }
      if ( v21 == 1 )
      {
        v6 = RogueDetectStateMachine(0);
        if ( v6 != -1 )
          v6 += time(0);
        ResetEvent(hEvent);
      }
      else if ( v21 != 2 )
      {
        v25 = v21 - 192;
        if ( v21 != 192 )
        {
          if ( v21 == 258 )
          {
            if ( v6 == -1 || (unsigned int)time(0) < v6 )
            {
              DateTime = (FILETIME)DhcpGetDateTime(v25, v22, v23, v24);
              if ( v14 )
              {
                switch ( v14 )
                {
                  case 1u:
                    v32 = DhcpBackupConfiguration(DhcpGlobalBackupConfigFileName);
                    v33 = v32;
                    if ( v32 )
                    {
                      DhcpServerEventLog(1017, 1, v32);
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                      {
                        WPP_SF_D(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          37,
                          &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids,
                          v33);
                      }
                    }
                    v34 = DhcpBackupDatabase(DhcpGlobalOemJetBackupPath);
                    v35 = v34;
                    if ( v34 )
                    {
                      DhcpServerEventLog(1016, 1, v34);
                      v27 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                      {
                        WPP_SF_D(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          38,
                          &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids,
                          v35);
                      }
                    }
                    LODWORD(v11) = 0;
                    break;
                  case 2u:
                    v31 = CleanupDatabase(&DateTime, 0);
                    v27 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                    {
                      WPP_SF_D(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        36,
                        &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids,
                        v31);
                    }
                    break;
                  case 3u:
                    v30 = DhcpGlobalScavengeIpAddress;
                    goto LABEL_87;
                  default:
                    if ( DhcpGlobalIsStatelessTestEnv && (Microsoft_Windows_DHCP_ServerEnableBits & 1) != 0 )
                      McGenEventWrite_EventWriteTransfer(
                        (__int64)v27,
                        &ScavengerStatelessStart,
                        v28,
                        1u,
                        (PEVENT_DATA_DESCRIPTOR)v55);
                    ScavengeStatelessEntries();
                    if ( DhcpGlobalIsStatelessTestEnv && (Microsoft_Windows_DHCP_ServerEnableBits & 1) != 0 )
                      McGenEventWrite_EventWriteTransfer(
                        (__int64)v27,
                        &ScavengerStatelessEnd,
                        v28,
                        1u,
                        (PEVENT_DATA_DESCRIPTOR)v56);
                    break;
                }
              }
              else
              {
                RwLockAcquireForWrite(&DhcpGlobalReadWriteLock);
                EnterCriticalSection(&DhcpGlobalInProgressCritSect);
                v36 = ((__int64 (__fastcall *)(_QWORD))DhcpDeleteExpiredCtxt)(DateTime);
                LeaveCriticalSection(&DhcpGlobalInProgressCritSect);
                RwLockRelease(&DhcpGlobalReadWriteLock);
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                {
                  WPP_SF_D(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    33,
                    &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids,
                    v36);
                }
                DeleteExpiredMcastScopes(&DateTime);
                GetLocalTime(&SystemTime);
                LODWORD(v11) = 0;
                if ( SystemTime.wHour )
                {
                  v4 = 1;
                }
                else
                {
                  EnterCriticalSection(&AuditLogCritSect);
                  v37 = CurrentDay;
                  if ( (unsigned int)HasDayChanged(&CurrentDay) )
                  {
                    AuditLogStop();
                    if ( (unsigned int)AuditLogStart(v39, v38) )
                    {
                      CurrentDay = v37;
                      AuditLogStop();
                    }
                    AuditLogErrorLogged = 0;
                    DiskSpaceLow = 0;
                  }
                  LeaveCriticalSection(&AuditLogCritSect);
                  EnterCriticalSection(&DhcpV6AuditLogCritSect);
                  v40 = DhcpV6CurrentDay;
                  if ( (unsigned int)HasDayChanged(&DhcpV6CurrentDay) )
                  {
                    DhcpV6AuditLogStop();
                    if ( (unsigned int)DhcpV6AuditLogStart(v42, v41) )
                    {
                      DhcpV6CurrentDay = v40;
                      DhcpV6AuditLogStop();
                    }
                    LODWORD(v11) = 0;
                    DhcpV6AuditLogErrorLogged = 0;
                    DhcpV6DiskSpaceLow = 0;
                  }
                  else
                  {
                    LODWORD(v11) = 0;
                  }
                  LeaveCriticalSection(&DhcpV6AuditLogCritSect);
                  if ( v4 == 1 )
                  {
                    v43 = CleanupDatabase(&DateTime, 0);
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                    {
                      WPP_SF_D(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        34,
                        &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids,
                        v43);
                    }
                    AddressCacherIPv6Scavenger();
                    DhcpTelemetryReportInfo(v44);
                    v4 = 0;
                  }
                }
                v30 = DhcpGlobalScavengeIpAddress;
                if ( DhcpGlobalScavengeIpAddress && !v5 )
                {
                  v5 = 1;
LABEL_87:
                  if ( v30 )
                  {
                    v45 = CleanupDatabase(&DateTime, 1);
                    v27 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                    {
                      WPP_SF_D(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        35,
                        &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids,
                        v45);
                    }
                    DhcpGlobalScavengeIpAddress = 0;
                  }
                  if ( v14 == 3 )
                    v5 = 0;
                }
              }
              v54[2 * v14] = DhcpGetDateTime(v27, v26, v28, v29);
            }
          }
          else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids, v21);
          }
        }
      }
    }
    v18 = time(0);
    v6 += v18;
LABEL_22:
    v19 = 1000 * (v6 - v18);
    if ( v19 >= (unsigned int)v11 )
      v19 = v11;
    LODWORD(v11) = v19;
    goto LABEL_25;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180051cfc  mov     rax, rsp
0x180051cff  mov     [rax+8], rbx
0x180051d03  mov     [rax+10h], rsi
0x180051d07  mov     [rax+18h], rdi
0x180051d0b  push    rbp
0x180051d0c  push    r12
0x180051d0e  push    r13
0x180051d10  push    r14
0x180051d12  push    r15
0x180051d14  lea     rbp, [rax-5Fh]
0x180051d18  sub     rsp, 100h
0x180051d1f  mov     rax, cs:__security_cookie
0x180051d26  xor     rax, rsp
0x180051d29  mov     [rbp+57h+var_30], rax
0x180051d2d  xor     esi, esi
0x180051d2f  xorps   xmm0, xmm0
0x180051d32  mov     ebx, 1
0x180051d37  mov     dword ptr [rsp+120h+var_F0], esi
0x180051d3b  mov     r12d, ebx
0x180051d3e  mov     r13d, esi
0x180051d41  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180051d45  call    DhcpGetDateTime
0x180051d4a  mov     qword ptr [rsp+120h+var_E8.dwLowDateTime], rax
0x180051d4f  lea     rcx, DhcpGlobalScavengerTimeout
0x180051d56  mov     [rbp+57h+var_A0], rcx
0x180051d5a  lea     r9, [rsp+120h+var_F0]
0x180051d5f  mov     [rbp+57h+var_98], rax
0x180051d63  lea     rcx, DhcpGlobalBackupInterval
0x180051d6a  mov     [rbp+57h+var_90], rcx
0x180051d6e  lea     r8d, [rbx+3]
0x180051d72  mov     [rbp+57h+var_88], rax
0x180051d76  lea     rcx, DhcpGlobalCleanupInterval
0x180051d7d  mov     [rbp+57h+var_78], rax
0x180051d81  lea     rdx, aDisableroguede; "DisableRogueDetection"
0x180051d88  mov     [rbp+57h+var_68], rax
0x180051d8c  mov     [rbp+57h+var_58], rax
0x180051d90  mov     rax, cs:DhcpGlobalRecomputeTimerEvent
0x180051d97  mov     [rbp+57h+var_80], rcx
0x180051d9b  lea     rcx, DhcpGlobalScavengeIpAddressInterval
0x180051da2  mov     [rbp+57h+var_B0], rax
0x180051da6  mov     rax, cs:DhcpGlobalProcessTerminationEvent
0x180051dad  mov     [rbp+57h+var_70], rcx
0x180051db1  lea     rcx, DhcpGlobalScavengeStatelessInterval
0x180051db8  mov     [rbp+57h+Handles], rax
0x180051dbc  mov     rax, cs:DhcpGlobalRogueWaitEvent
0x180051dc3  mov     [rbp+57h+var_60], rcx
0x180051dc7  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x180051dce  mov     [rbp+57h+hEvent], rax
0x180051dd2  call    DhcpRegGetValue
0x180051dd7  test    eax, eax
0x180051dd9  jnz     short loc_180051DE5
0x180051ddb  cmp     dword ptr [rsp+120h+var_F0], esi
0x180051ddf  jz      short loc_180051DE5
0x180051de1  mov     dword ptr [rsp+120h+var_F0], ebx
0x180051de5  xor     ecx, ecx
0x180051de7  call    RogueDetectStateMachine
0x180051dec  mov     edi, eax
0x180051dee  cmp     eax, 0FFFFFFFFh
0x180051df1  jz      short loc_180051E03
0x180051df3  xor     ecx, ecx; Time
0x180051df5  call    cs:__imp_time
0x180051dfc  nop     dword ptr [rax+rax+00h]
0x180051e01  add     edi, eax
0x180051e03  mov     rbx, cs:DhcpGlobalThisServerV6
0x180051e0a  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180051e11  call    cs:__imp_EnterCriticalSection
0x180051e18  nop     dword ptr [rax+rax+00h]
0x180051e1d  lea     rcx, DhcpGlobalStatelessCritSect; lpCriticalSection
0x180051e24  call    cs:__imp_EnterCriticalSection
0x180051e2b  nop     dword ptr [rax+rax+00h]
0x180051e30  lea     rdx, [rbx+70h]
0x180051e34  call    DhcpCountStatelessRecordsPerSubnet
0x180051e39  lea     rcx, DhcpGlobalStatelessCritSect; lpCriticalSection
0x180051e40  mov     ebx, eax
0x180051e42  call    cs:__imp_LeaveCriticalSection
0x180051e49  nop     dword ptr [rax+rax+00h]
0x180051e4e  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180051e55  call    cs:__imp_LeaveCriticalSection
0x180051e5c  nop     dword ptr [rax+rax+00h]
0x180051e61  test    ebx, ebx
0x180051e63  jz      short loc_180051E9D
0x180051e65  mov     rcx, cs:WPP_GLOBAL_Control
0x180051e6c  lea     rsi, WPP_GLOBAL_Control
0x180051e73  cmp     rcx, rsi
0x180051e76  jz      short loc_180051E96
0x180051e78  test    byte ptr [rcx+1Ch], 10h
0x180051e7c  jz      short loc_180051E96
0x180051e7e  mov     rcx, [rcx+10h]
0x180051e82  lea     r8, WPP_f0e25f423f3133668f92132b43c41a83_Traceguids
0x180051e89  mov     edx, 1Fh
0x180051e8e  mov     r9d, ebx
0x180051e91  call    WPP_SF_D
0x180051e96  mov     eax, ebx
0x180051e98  jmp     loc_18005249E
0x180051e9d  lea     rsi, WPP_GLOBAL_Control
0x180051ea4  xor     ebx, ebx
0x180051ea6  lea     r14, WPP_f0e25f423f3133668f92132b43c41a83_Traceguids
0x180051ead  or      r8, 0FFFFFFFFFFFFFFFFh
0x180051eb1  mov     qword ptr [rsp+120h+FileTime2.dwLowDateTime], rbx
0x180051eb6  mov     qword ptr [rsp+120h+FileTime1.dwLowDateTime], r8
0x180051ebb  lea     r9, [rbp+57h+var_98]
0x180051ebf  mov     r15d, ebx
0x180051ec2  mov     edx, ebx
0x180051ec4  mov     rax, [r9-8]
0x180051ec8  mov     ecx, [rax]
0x180051eca  imul    rax, rcx, 2710h
0x180051ed1  add     rax, [r9]
0x180051ed4  cmp     rax, r8
0x180051ed7  jnb     short loc_180051EE4
0x180051ed9  mov     r8, rax
0x180051edc  mov     qword ptr [rsp+120h+FileTime1.dwLowDateTime], rax
0x180051ee1  mov     r15d, edx
0x180051ee4  inc     edx
0x180051ee6  add     r9, 10h
0x180051eea  cmp     edx, 5
0x180051eed  jb      short loc_180051EC4
0x180051eef  call    DhcpGetDateTime
0x180051ef4  lea     rdx, [rsp+120h+FileTime2]; lpFileTime2
0x180051ef9  mov     qword ptr [rsp+120h+FileTime2.dwLowDateTime], rax
0x180051efe  lea     rcx, [rsp+120h+FileTime1]; lpFileTime1
0x180051f03  call    cs:__imp_CompareFileTime
0x180051f0a  nop     dword ptr [rax+rax+00h]
0x180051f0f  test    eax, eax
0x180051f11  jle     short loc_180051F31
0x180051f13  mov     rcx, qword ptr [rsp+120h+FileTime1.dwLowDateTime]
0x180051f18  mov     rax, 346DC5D63886594Bh
0x180051f22  sub     rcx, qword ptr [rsp+120h+FileTime2.dwLowDateTime]
0x180051f27  mul     rcx
0x180051f2a  mov     rbx, rdx
0x180051f2d  shr     rbx, 0Bh
0x180051f31  mov     rcx, cs:WPP_GLOBAL_Control
0x180051f38  cmp     rcx, rsi
0x180051f3b  jz      short loc_180051F62
0x180051f3d  test    byte ptr [rcx+1Ch], 80h
0x180051f41  jz      short loc_180051F62
0x180051f43  mov     rcx, [rcx+10h]
0x180051f47  mov     edx, 0Ah
0x180051f4c  mov     r9d, r15d
0x180051f4f  mov     [rsp+120h+bAlertable], ebx
0x180051f53  mov     r8, r14
0x180051f56  call    WPP_SF_dD
0x180051f5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180051f62  cmp     edi, 0FFFFFFFFh
0x180051f65  jz      short loc_180051FB4
0x180051f67  xor     ecx, ecx; Time
0x180051f69  call    cs:__imp_time
0x180051f70  nop     dword ptr [rax+rax+00h]
0x180051f75  mov     rcx, rax
0x180051f78  cmp     eax, edi
0x180051f7a  jb      short loc_180051F9C
0x180051f7c  xor     ecx, ecx
0x180051f7e  call    RogueDetectStateMachine
0x180051f83  mov     edi, eax
0x180051f85  cmp     eax, 0FFFFFFFFh
0x180051f88  jz      short loc_180051FAD
0x180051f8a  xor     ecx, ecx; Time
0x180051f8c  call    cs:__imp_time
0x180051f93  nop     dword ptr [rax+rax+00h]
0x180051f98  mov     ecx, eax
0x180051f9a  add     edi, eax
0x180051f9c  mov     eax, edi
0x180051f9e  sub     eax, ecx
0x180051fa0  imul    ecx, eax, 3E8h
0x180051fa6  cmp     ecx, ebx
0x180051fa8  cmovnb  ecx, ebx
0x180051fab  mov     ebx, ecx
0x180051fad  mov     rcx, cs:WPP_GLOBAL_Control
0x180051fb4  cmp     rcx, rsi
0x180051fb7  jz      short loc_180051FDE
0x180051fb9  test    byte ptr [rcx+1Ch], 80h
0x180051fbd  jz      short loc_180051FDE
0x180051fbf  mov     rcx, [rcx+10h]
0x180051fc3  mov     eax, 10624DD3h
0x180051fc8  mul     ebx
0x180051fca  mov     r8, r14
0x180051fcd  mov     r9d, edx
0x180051fd0  mov     edx, 20h ; ' '
0x180051fd5  shr     r9d, 6
0x180051fd9  call    WPP_SF_D
0x180051fde  mov     rcx, cs:DhcpGlobalRogueWaitEvent
0x180051fe5  cmp     edi, 0FFFFFFFFh
0x180051fe8  mov     rax, rcx
0x180051feb  cmovz   rax, cs:DhcpGlobalGenericEndpointReadyEvent
0x180051ff3  mov     [rbp+57h+hEvent], rax
0x180051ff7  xor     eax, eax
0x180051ff9  cmp     dword ptr [rsp+120h+var_F0], eax
0x180051ffd  jz      short loc_180052003
0x180051fff  mov     [rbp+57h+hEvent], rcx
0x180052003  call    DhcpDnsHandleCallbacks
0x180052008  call    Dhcpv6DnsHandleCallbacks
0x18005200d  xor     r8d, r8d; bWaitAll
0x180052010  mov     [rsp+120h+bAlertable], 1; bAlertable
0x180052018  mov     r9d, ebx; dwMilliseconds
0x18005201b  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18005201f  lea     ecx, [r8+3]; nCount
0x180052023  call    cs:__imp_WaitForMultipleObjectsEx
0x18005202a  nop     dword ptr [rax+rax+00h]
0x18005202f  xor     ebx, ebx
0x180052031  mov     ecx, eax
0x180052033  test    eax, eax
0x180052035  jz      loc_180052497
0x18005203b  sub     ecx, 1
0x18005203e  jz      loc_180052464
0x180052044  sub     ecx, 1
0x180052047  jz      loc_180051EAD
0x18005204d  sub     ecx, 0BEh
0x180052053  jz      loc_180051EAD
0x180052059  cmp     ecx, 42h ; 'B'
0x18005205c  jz      short loc_18005208F
0x18005205e  mov     rcx, cs:WPP_GLOBAL_Control
0x180052065  cmp     rcx, rsi
0x180052068  jz      loc_180051EAD
0x18005206e  test    byte ptr [rcx+1Ch], 10h
0x180052072  jz      loc_180051EAD
0x180052078  mov     rcx, [rcx+10h]
0x18005207c  lea     edx, [rbx+27h]
0x18005207f  mov     r9d, eax
0x180052082  mov     r8, r14
0x180052085  call    WPP_SF_D
0x18005208a  jmp     loc_180051EAD
0x18005208f  cmp     edi, 0FFFFFFFFh
0x180052092  jz      short loc_1800520AA
0x180052094  xor     ecx, ecx; Time
0x180052096  call    cs:__imp_time
0x18005209d  nop     dword ptr [rax+rax+00h]
0x1800520a2  cmp     eax, edi
0x1800520a4  jnb     loc_180051EAD
0x1800520aa  call    DhcpGetDateTime
0x1800520af  mov     qword ptr [rsp+120h+var_E8.dwLowDateTime], rax
0x1800520b4  mov     eax, r15d
0x1800520b7  test    r15d, r15d
0x1800520ba  jz      loc_18005223E
0x1800520c0  sub     eax, 1
0x1800520c3  jz      loc_180052193
0x1800520c9  sub     eax, 1
0x1800520cc  jz      loc_180052154
0x1800520d2  sub     eax, 1
0x1800520d5  jz      short loc_180052149
0x1800520d7  cmp     eax, 1
0x1800520da  jnz     loc_180052455
0x1800520e0  cmp     cs:DhcpGlobalIsStatelessTestEnv, ebx
0x1800520e6  jz      short loc_18005210B
0x1800520e8  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, al
0x1800520ee  jz      short loc_18005210B
0x1800520f0  lea     rax, [rbp+57h+var_50]
0x1800520f4  mov     r9d, 1
0x1800520fa  lea     rdx, ScavengerStatelessStart
0x180052101  mov     qword ptr [rsp+120h+bAlertable], rax
0x180052106  call    McGenEventWrite_EventWriteTransfer
0x18005210b  call    ScavengeStatelessEntries
0x180052110  cmp     cs:DhcpGlobalIsStatelessTestEnv, ebx
0x180052116  jz      loc_180052229
0x18005211c  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 1
0x180052123  jz      loc_180052229
0x180052129  lea     rax, [rbp+57h+var_40]
0x18005212d  mov     r9d, 1
0x180052133  lea     rdx, ScavengerStatelessEnd
0x18005213a  mov     qword ptr [rsp+120h+bAlertable], rax
0x18005213f  call    McGenEventWrite_EventWriteTransfer
0x180052144  jmp     loc_180052229
0x180052149  mov     eax, cs:DhcpGlobalScavengeIpAddress
0x18005214f  jmp     loc_180052408
0x180052154  xor     edx, edx
0x180052156  lea     rcx, [rsp+120h+var_E8]
0x18005215b  call    CleanupDatabase
0x180052160  mov     rcx, cs:WPP_GLOBAL_Control
0x180052167  cmp     rcx, rsi
0x18005216a  jz      loc_180052229
0x180052170  test    byte ptr [rcx+1Ch], 10h
0x180052174  jz      loc_180052229
0x18005217a  mov     rcx, [rcx+10h]
0x18005217e  mov     edx, 24h ; '$'
0x180052183  mov     r9d, eax
0x180052186  mov     r8, r14
0x180052189  call    WPP_SF_D
0x18005218e  jmp     loc_180052229
0x180052193  mov     rcx, cs:DhcpGlobalBackupConfigFileName; lpFileName
0x18005219a  call    DhcpBackupConfiguration
0x18005219f  mov     ebx, eax
0x1800521a1  test    eax, eax
0x1800521a3  jz      short loc_1800521DD
0x1800521a5  mov     r8d, eax
0x1800521a8  mov     edx, 1
0x1800521ad  mov     ecx, 3F9h
0x1800521b2  call    DhcpServerEventLog
0x1800521b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800521be  cmp     rcx, rsi
0x1800521c1  jz      short loc_1800521DD
0x1800521c3  test    byte ptr [rcx+1Ch], 10h
0x1800521c7  jz      short loc_1800521DD
0x1800521c9  mov     rcx, [rcx+10h]
0x1800521cd  mov     edx, 25h ; '%'
0x1800521d2  mov     r9d, ebx
0x1800521d5  mov     r8, r14
0x1800521d8  call    WPP_SF_D
0x1800521dd  mov     rcx, cs:DhcpGlobalOemJetBackupPath
0x1800521e4  call    DhcpBackupDatabase
0x1800521e9  mov     ebx, eax
0x1800521eb  test    eax, eax
0x1800521ed  jz      short loc_180052227
  ... truncated ...
```

# Scavenger

- ea: `0x180051a00`
- end: `0x1800521d3`
- name: `Scavenger`
- size: `2003`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027260`

## callees

- `0x18000282c`
- `0x180002870`
- `0x18000353c`
- `0x180003858`
- `0x180004ce4`
- `0x1800057e0`
- `0x18000c770`
- `0x18001c63c`
- `0x18001dde0`
- `0x18001fe44`
- `0x1800247a0`
- `0x180024960`
- `0x180029064`
- `0x180032f78`
- `0x180035ab0`
- `0x18004ff20`
- `0x1800516fc`
- `0x180051760`
- `0x180051a00`
- `0x1800626dc`
- `0x180067094`
- `0x1800673b0`
- `0x18007800c`
- `0x18007a9e8`
- `0x18008f0b4`
- `0x1800b6430`
- `0x1800cdac0`

## import_xrefs

- `msvcrt!time` at `0x180051af9`
- `msvcrt!time` at `0x180051c70`
- `msvcrt!time` at `0x180051c93`
- `msvcrt!time` at `0x180051d9d`
- `msvcrt!time` at `0x18005217b`
- `msvcrt!time` at `0x180051af9`
- `msvcrt!time` at `0x180051c70`
- `msvcrt!time` at `0x180051c93`
- `msvcrt!time` at `0x180051d9d`
- `msvcrt!time` at `0x18005217b`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180051d2a`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180051d2a`
- `KERNEL32!ResetEvent` at `0x18005218d`
- `KERNEL32!ResetEvent` at `0x18005218d`
- `KERNEL32!GetLocalTime` at `0x180051fc3`
- `KERNEL32!GetLocalTime` at `0x180051fc3`
- `KERNEL32!CompareFileTime` at `0x180051c0a`
- `KERNEL32!CompareFileTime` at `0x180051c0a`
- `KERNEL32!EnterCriticalSection` at `0x180051b15`
- `KERNEL32!EnterCriticalSection` at `0x180051b28`
- `KERNEL32!EnterCriticalSection` at `0x180051f58`
- `KERNEL32!EnterCriticalSection` at `0x180051fe2`
- `KERNEL32!EnterCriticalSection` at `0x180052045`
- `KERNEL32!EnterCriticalSection` at `0x180051b15`
- `KERNEL32!EnterCriticalSection` at `0x180051b28`
- `KERNEL32!EnterCriticalSection` at `0x180051f58`
- `KERNEL32!EnterCriticalSection` at `0x180051fe2`
- `KERNEL32!EnterCriticalSection` at `0x180052045`
- `KERNEL32!LeaveCriticalSection` at `0x180051b46`
- `KERNEL32!LeaveCriticalSection` at `0x180051b59`
- `KERNEL32!LeaveCriticalSection` at `0x180051f77`
- `KERNEL32!LeaveCriticalSection` at `0x180052032`
- `KERNEL32!LeaveCriticalSection` at `0x180052099`
- `KERNEL32!LeaveCriticalSection` at `0x180051b46`
- `KERNEL32!LeaveCriticalSection` at `0x180051b59`
- `KERNEL32!LeaveCriticalSection` at `0x180051f77`
- `KERNEL32!LeaveCriticalSection` at `0x180052032`
- `KERNEL32!LeaveCriticalSection` at `0x180052099`

## pseudocode

```c
__int64 Scavenger()
{
  int v0; // r12d
  int v1; // r13d
  unsigned int v2; // edi
  char *v3; // rbx
  __int64 v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  unsigned __int64 v8; // rbx
  FILETIME v9; // r9
  _QWORD *v10; // r10
  unsigned int v11; // r15d
  __int64 v12; // r8
  unsigned int *v13; // rax
  unsigned __int64 v14; // rcx
  char *v15; // rcx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  HANDLE v18; // rax
  DWORD v19; // eax
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rcx
  __int64 v23; // rdx
  void *v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // ebx
  unsigned int v31; // eax
  unsigned int v32; // ebx
  unsigned int v33; // ebx
  int v34; // ebx
  int v35; // ebx
  unsigned int v36; // eax
  __int64 v37; // rcx
  unsigned int v38; // eax
  FILETIME DateTime; // [rsp+40h] [rbp-91h] BYREF
  FILETIME FileTime1; // [rsp+48h] [rbp-89h] BYREF
  FILETIME FileTime2; // [rsp+50h] [rbp-81h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+58h] [rbp-79h] BYREF
  HANDLE Handles; // [rsp+68h] [rbp-69h] BYREF
  HANDLE hEvent; // [rsp+70h] [rbp-61h]
  HANDLE v45; // [rsp+78h] [rbp-59h]
  int *v46; // [rsp+88h] [rbp-49h]
  _QWORD v47[9]; // [rsp+90h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v48; // [rsp+D8h] [rbp+7h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v49; // [rsp+E8h] [rbp+17h] BYREF

  v0 = 1;
  v1 = 0;
  SystemTime = 0;
  DateTime = (FILETIME)((__int64 (*)(void))DhcpGetDateTime)();
  v46 = &DhcpGlobalScavengerTimeout;
  v47[0] = DateTime;
  v47[1] = &DhcpGlobalBackupInterval;
  v47[2] = DateTime;
  v47[4] = DateTime;
  v47[6] = DateTime;
  v47[8] = DateTime;
  v47[3] = &DhcpGlobalCleanupInterval;
  v45 = DhcpGlobalRecomputeTimerEvent;
  v47[5] = &DhcpGlobalScavengeIpAddressInterval;
  Handles = DhcpGlobalProcessTerminationEvent;
  v47[7] = &DhcpGlobalScavengeStatelessInterval;
  hEvent = DhcpGlobalRogueWaitEvent;
  DhcpRegGetValue(DhcpGlobalRegParam, L"DisableRogueDetection");
  v2 = RogueDetectStateMachine(0);
  if ( v2 != -1 )
    v2 += time(0);
  v3 = (char *)DhcpGlobalThisServerV6;
  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  EnterCriticalSection(&DhcpGlobalStatelessCritSect);
  v5 = DhcpCountStatelessRecordsPerSubnet(v4, v3 + 112);
  LeaveCriticalSection(&DhcpGlobalStatelessCritSect);
  LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  if ( !v5 )
  {
    LODWORD(v8) = 0;
    while ( 1 )
    {
      v9 = (FILETIME)-1LL;
      FileTime2 = 0;
      FileTime1 = (FILETIME)-1LL;
      v10 = v47;
      v11 = 0;
      LODWORD(v12) = 0;
      do
      {
        v13 = (unsigned int *)*(v10 - 1);
        v14 = *v10 + 10000LL * *v13;
        if ( v14 < *(_QWORD *)&v9 )
        {
          v9 = (FILETIME)(*v10 + 10000LL * *v13);
          FileTime1 = v9;
          v11 = v12;
        }
        v12 = (unsigned int)(v12 + 1);
        v10 += 2;
      }
      while ( (unsigned int)v12 < 5 );
      FileTime2 = (FILETIME)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))DhcpGetDateTime)(v14, v6, v12, v9);
      if ( CompareFileTime(&FileTime1, &FileTime2) > 0 )
        v8 = (*(_QWORD *)&FileTime1 - *(_QWORD *)&FileTime2) / 0x2710uLL;
      v15 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids, v11, v8);
        v15 = (char *)WPP_GLOBAL_Control;
      }
      if ( v2 == -1 )
        goto LABEL_26;
      v16 = time(0);
      if ( v16 < v2 )
        goto LABEL_22;
      v2 = RogueDetectStateMachine(0);
      if ( v2 != -1 )
        break;
LABEL_25:
      v15 = (char *)WPP_GLOBAL_Control;
LABEL_26:
      if ( v15 != (char *)&WPP_GLOBAL_Control && v15[28] < 0 )
        WPP_SF_D(*((_QWORD *)v15 + 2), 32, &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids, (unsigned int)v8 / 0x3E8);
      v18 = DhcpGlobalRogueWaitEvent;
      if ( v2 == -1 )
        v18 = DhcpGlobalGenericEndpointReadyEvent;
      hEvent = v18;
      DhcpDnsHandleCallbacks();
      Dhcpv6DnsHandleCallbacks();
      v19 = WaitForMultipleObjectsEx(3u, &Handles, 0, v8, 1);
      LODWORD(v8) = 0;
      if ( !v19 )
      {
        DhcpTelemetryReportInfo(0);
        return 0;
      }
      if ( v19 == 1 )
      {
        v2 = RogueDetectStateMachine(0);
        if ( v2 != -1 )
          v2 += time(0);
        ResetEvent(hEvent);
      }
      else if ( v19 != 2 )
      {
        v22 = v19 - 192;
        if ( v19 != 192 )
        {
          if ( v19 == 258 )
          {
            if ( v2 == -1 || (unsigned int)time(0) < v2 )
            {
              DateTime = (FILETIME)DhcpGetDateTime(v22, v6, v20, v21);
              if ( v11 )
              {
                switch ( v11 )
                {
                  case 1u:
                    v29 = DhcpBackupConfiguration(DhcpGlobalBackupConfigFileName);
                    v30 = v29;
                    if ( v29 )
                    {
                      DhcpServerEventLog(1017, 1, v29);
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                      {
                        WPP_SF_D(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          37,
                          &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids,
                          v30);
                      }
                    }
                    v31 = DhcpBackupDatabase(DhcpGlobalOemJetBackupPath);
                    v32 = v31;
                    if ( v31 )
                    {
                      DhcpServerEventLog(1016, 1, v31);
                      v24 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                      {
                        WPP_SF_D(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          38,
                          &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids,
                          v32);
                      }
                    }
                    LODWORD(v8) = 0;
                    break;
                  case 2u:
                    v28 = CleanupDatabase(&DateTime, 0);
                    v24 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                    {
                      WPP_SF_D(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        36,
                        &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids,
                        v28);
                    }
                    break;
                  case 3u:
                    v27 = DhcpGlobalScavengeIpAddress;
                    goto LABEL_87;
                  default:
                    if ( DhcpGlobalIsStatelessTestEnv && (Microsoft_Windows_DHCP_ServerEnableBits & 1) != 0 )
                      McGenEventWrite_EventWriteTransfer((__int64)v24, &ScavengerStatelessStart, v25, 1u, &v48);
                    ScavengeStatelessEntries();
                    if ( DhcpGlobalIsStatelessTestEnv && (Microsoft_Windows_DHCP_ServerEnableBits & 1) != 0 )
                      McGenEventWrite_EventWriteTransfer((__int64)v24, &ScavengerStatelessEnd, v25, 1u, &v49);
                    break;
                }
              }
              else
              {
                RwLockAcquireForWrite(&DhcpGlobalReadWriteLock);
                EnterCriticalSection(&DhcpGlobalInProgressCritSect);
                v33 = ((__int64 (__fastcall *)(_QWORD))DhcpDeleteExpiredCtxt)(DateTime);
                LeaveCriticalSection(&DhcpGlobalInProgressCritSect);
                RwLockRelease(&DhcpGlobalReadWriteLock);
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                {
                  WPP_SF_D(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    33,
                    &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids,
                    v33);
                }
                DeleteExpiredMcastScopes(&DateTime);
                GetLocalTime(&SystemTime);
                LODWORD(v8) = 0;
                if ( SystemTime.wHour )
                {
                  v0 = 1;
                }
                else
                {
                  EnterCriticalSection(&AuditLogCritSect);
                  v34 = CurrentDay;
                  if ( (unsigned int)HasDayChanged(&CurrentDay) )
                  {
                    AuditLogStop();
                    if ( (unsigned int)AuditLogStart() )
                    {
                      CurrentDay = v34;
                      AuditLogStop();
                    }
                    AuditLogErrorLogged = 0;
                    DiskSpaceLow = 0;
                  }
                  LeaveCriticalSection(&AuditLogCritSect);
                  EnterCriticalSection(&DhcpV6AuditLogCritSect);
                  v35 = DhcpV6CurrentDay;
                  if ( (unsigned int)HasDayChanged(&DhcpV6CurrentDay) )
                  {
                    DhcpV6AuditLogStop();
                    if ( (unsigned int)DhcpV6AuditLogStart() )
                    {
                      DhcpV6CurrentDay = v35;
                      DhcpV6AuditLogStop();
                    }
                    LODWORD(v8) = 0;
                    DhcpV6AuditLogErrorLogged = 0;
                    DhcpV6DiskSpaceLow = 0;
                  }
                  else
                  {
                    LODWORD(v8) = 0;
                  }
                  LeaveCriticalSection(&DhcpV6AuditLogCritSect);
                  if ( v0 == 1 )
                  {
                    v36 = CleanupDatabase(&DateTime, 0);
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                    {
                      WPP_SF_D(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        34,
                        &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids,
                        v36);
                    }
                    AddressCacherIPv6Scavenger();
                    DhcpTelemetryReportInfo(v37);
                    v0 = 0;
                  }
                }
                v27 = DhcpGlobalScavengeIpAddress;
                if ( DhcpGlobalScavengeIpAddress && !v1 )
                {
                  v1 = 1;
LABEL_87:
                  if ( v27 )
                  {
                    v38 = CleanupDatabase(&DateTime, 1);
                    v24 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                    {
                      WPP_SF_D(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        35,
                        &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids,
                        v38);
                    }
                    DhcpGlobalScavengeIpAddress = 0;
                  }
                  if ( v11 == 3 )
                    v1 = 0;
                }
              }
              v47[2 * v11] = DhcpGetDateTime(v24, v23, v25, v26);
            }
          }
          else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids, v19);
          }
        }
      }
    }
    v16 = time(0);
    v2 += v16;
LABEL_22:
    v17 = 1000 * (v2 - v16);
    if ( v17 >= (unsigned int)v8 )
      v17 = v8;
    LODWORD(v8) = v17;
    goto LABEL_25;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180051a00  mov     rax, rsp
0x180051a03  mov     [rax+8], rbx
0x180051a07  mov     [rax+10h], rsi
0x180051a0b  mov     [rax+18h], rdi
0x180051a0f  push    rbp
0x180051a10  push    r12
0x180051a12  push    r13
0x180051a14  push    r14
0x180051a16  push    r15
0x180051a18  lea     rbp, [rax-5Fh]
0x180051a1c  sub     rsp, 100h
0x180051a23  mov     rax, cs:__security_cookie
0x180051a2a  xor     rax, rsp
0x180051a2d  mov     [rbp+57h+var_30], rax
0x180051a31  xor     esi, esi
0x180051a33  xorps   xmm0, xmm0
0x180051a36  mov     ebx, 1
0x180051a3b  mov     dword ptr [rsp+120h+var_F0], esi
0x180051a3f  mov     r12d, ebx
0x180051a42  mov     r13d, esi
0x180051a45  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180051a49  call    DhcpGetDateTime
0x180051a4e  mov     qword ptr [rsp+120h+var_E8.dwLowDateTime], rax
0x180051a53  lea     rcx, DhcpGlobalScavengerTimeout
0x180051a5a  mov     [rbp+57h+var_A0], rcx
0x180051a5e  lea     r9, [rsp+120h+var_F0]
0x180051a63  mov     [rbp+57h+var_98], rax
0x180051a67  lea     rcx, DhcpGlobalBackupInterval
0x180051a6e  mov     [rbp+57h+var_90], rcx
0x180051a72  lea     r8d, [rbx+3]
0x180051a76  mov     [rbp+57h+var_88], rax
0x180051a7a  lea     rcx, DhcpGlobalCleanupInterval
0x180051a81  mov     [rbp+57h+var_78], rax
0x180051a85  lea     rdx, aDisableroguede; "DisableRogueDetection"
0x180051a8c  mov     [rbp+57h+var_68], rax
0x180051a90  mov     [rbp+57h+var_58], rax
0x180051a94  mov     rax, cs:DhcpGlobalRecomputeTimerEvent
0x180051a9b  mov     [rbp+57h+var_80], rcx
0x180051a9f  lea     rcx, DhcpGlobalScavengeIpAddressInterval
0x180051aa6  mov     [rbp+57h+var_B0], rax
0x180051aaa  mov     rax, cs:DhcpGlobalProcessTerminationEvent
0x180051ab1  mov     [rbp+57h+var_70], rcx
0x180051ab5  lea     rcx, DhcpGlobalScavengeStatelessInterval
0x180051abc  mov     [rbp+57h+Handles], rax
0x180051ac0  mov     rax, cs:DhcpGlobalRogueWaitEvent
0x180051ac7  mov     [rbp+57h+var_60], rcx
0x180051acb  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x180051ad2  mov     [rbp+57h+hEvent], rax
0x180051ad6  call    DhcpRegGetValue
0x180051adb  test    eax, eax
0x180051add  jnz     short loc_180051AE9
0x180051adf  cmp     dword ptr [rsp+120h+var_F0], esi
0x180051ae3  jz      short loc_180051AE9
0x180051ae5  mov     dword ptr [rsp+120h+var_F0], ebx
0x180051ae9  xor     ecx, ecx
0x180051aeb  call    RogueDetectStateMachine
0x180051af0  mov     edi, eax
0x180051af2  cmp     eax, 0FFFFFFFFh
0x180051af5  jz      short loc_180051B07
0x180051af7  xor     ecx, ecx; Time
0x180051af9  call    cs:__imp_time
0x180051b00  nop     dword ptr [rax+rax+00h]
0x180051b05  add     edi, eax
0x180051b07  mov     rbx, cs:DhcpGlobalThisServerV6
0x180051b0e  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180051b15  call    cs:__imp_EnterCriticalSection
0x180051b1c  nop     dword ptr [rax+rax+00h]
0x180051b21  lea     rcx, DhcpGlobalStatelessCritSect; lpCriticalSection
0x180051b28  call    cs:__imp_EnterCriticalSection
0x180051b2f  nop     dword ptr [rax+rax+00h]
0x180051b34  lea     rdx, [rbx+70h]
0x180051b38  call    DhcpCountStatelessRecordsPerSubnet
0x180051b3d  lea     rcx, DhcpGlobalStatelessCritSect; lpCriticalSection
0x180051b44  mov     ebx, eax
0x180051b46  call    cs:__imp_LeaveCriticalSection
0x180051b4d  nop     dword ptr [rax+rax+00h]
0x180051b52  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180051b59  call    cs:__imp_LeaveCriticalSection
0x180051b60  nop     dword ptr [rax+rax+00h]
0x180051b65  test    ebx, ebx
0x180051b67  jz      short loc_180051BA1
0x180051b69  mov     rcx, cs:WPP_GLOBAL_Control
0x180051b70  lea     rsi, WPP_GLOBAL_Control
0x180051b77  cmp     rcx, rsi
0x180051b7a  jz      short loc_180051B9A
0x180051b7c  test    byte ptr [rcx+1Ch], 10h
0x180051b80  jz      short loc_180051B9A
0x180051b82  mov     rcx, [rcx+10h]
0x180051b86  lea     r8, WPP_f0e25f423f3133668f92132b43c41a83_Traceguids
0x180051b8d  mov     edx, 1Fh
0x180051b92  mov     r9d, ebx
0x180051b95  call    WPP_SF_D
0x180051b9a  mov     eax, ebx
0x180051b9c  jmp     loc_1800521A5
0x180051ba1  lea     rsi, WPP_GLOBAL_Control
0x180051ba8  xor     ebx, ebx
0x180051baa  lea     r14, WPP_f0e25f423f3133668f92132b43c41a83_Traceguids
0x180051bb1  or      r9, 0FFFFFFFFFFFFFFFFh
0x180051bb5  mov     qword ptr [rsp+120h+FileTime2.dwLowDateTime], rbx
0x180051bba  mov     qword ptr [rsp+120h+FileTime1.dwLowDateTime], r9
0x180051bbf  lea     r10, [rbp+57h+var_98]
0x180051bc3  mov     r15d, ebx
0x180051bc6  mov     r8d, ebx
0x180051bc9  mov     rax, [r10-8]
0x180051bcd  mov     ecx, [rax]
0x180051bcf  imul    rcx, 2710h
0x180051bd6  add     rcx, [r10]
0x180051bd9  cmp     rcx, r9
0x180051bdc  jnb     short loc_180051BE9
0x180051bde  mov     r9, rcx
0x180051be1  mov     qword ptr [rsp+120h+FileTime1.dwLowDateTime], rcx
0x180051be6  mov     r15d, r8d
0x180051be9  inc     r8d
0x180051bec  add     r10, 10h
0x180051bf0  cmp     r8d, 5
0x180051bf4  jb      short loc_180051BC9
0x180051bf6  call    DhcpGetDateTime
0x180051bfb  lea     rdx, [rsp+120h+FileTime2]; lpFileTime2
0x180051c00  mov     qword ptr [rsp+120h+FileTime2.dwLowDateTime], rax
0x180051c05  lea     rcx, [rsp+120h+FileTime1]; lpFileTime1
0x180051c0a  call    cs:__imp_CompareFileTime
0x180051c11  nop     dword ptr [rax+rax+00h]
0x180051c16  test    eax, eax
0x180051c18  jle     short loc_180051C38
0x180051c1a  mov     rcx, qword ptr [rsp+120h+FileTime1.dwLowDateTime]
0x180051c1f  mov     rax, 346DC5D63886594Bh
0x180051c29  sub     rcx, qword ptr [rsp+120h+FileTime2.dwLowDateTime]
0x180051c2e  mul     rcx
0x180051c31  mov     rbx, rdx
0x180051c34  shr     rbx, 0Bh
0x180051c38  mov     rcx, cs:WPP_GLOBAL_Control
0x180051c3f  cmp     rcx, rsi
0x180051c42  jz      short loc_180051C69
0x180051c44  test    byte ptr [rcx+1Ch], 80h
0x180051c48  jz      short loc_180051C69
0x180051c4a  mov     rcx, [rcx+10h]
0x180051c4e  mov     edx, 0Ah
0x180051c53  mov     r9d, r15d
0x180051c56  mov     [rsp+120h+bAlertable], ebx
0x180051c5a  mov     r8, r14
0x180051c5d  call    WPP_SF_dD
0x180051c62  mov     rcx, cs:WPP_GLOBAL_Control
0x180051c69  cmp     edi, 0FFFFFFFFh
0x180051c6c  jz      short loc_180051CBB
0x180051c6e  xor     ecx, ecx; Time
0x180051c70  call    cs:__imp_time
0x180051c77  nop     dword ptr [rax+rax+00h]
0x180051c7c  mov     rcx, rax
0x180051c7f  cmp     eax, edi
0x180051c81  jb      short loc_180051CA3
0x180051c83  xor     ecx, ecx
0x180051c85  call    RogueDetectStateMachine
0x180051c8a  mov     edi, eax
0x180051c8c  cmp     eax, 0FFFFFFFFh
0x180051c8f  jz      short loc_180051CB4
0x180051c91  xor     ecx, ecx; Time
0x180051c93  call    cs:__imp_time
0x180051c9a  nop     dword ptr [rax+rax+00h]
0x180051c9f  mov     ecx, eax
0x180051ca1  add     edi, eax
0x180051ca3  mov     eax, edi
0x180051ca5  sub     eax, ecx
0x180051ca7  imul    ecx, eax, 3E8h
0x180051cad  cmp     ecx, ebx
0x180051caf  cmovnb  ecx, ebx
0x180051cb2  mov     ebx, ecx
0x180051cb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180051cbb  cmp     rcx, rsi
0x180051cbe  jz      short loc_180051CE5
0x180051cc0  test    byte ptr [rcx+1Ch], 80h
0x180051cc4  jz      short loc_180051CE5
0x180051cc6  mov     rcx, [rcx+10h]
0x180051cca  mov     eax, 10624DD3h
0x180051ccf  mul     ebx
0x180051cd1  mov     r8, r14
0x180051cd4  mov     r9d, edx
0x180051cd7  mov     edx, 20h ; ' '
0x180051cdc  shr     r9d, 6
0x180051ce0  call    WPP_SF_D
0x180051ce5  mov     rcx, cs:DhcpGlobalRogueWaitEvent
0x180051cec  cmp     edi, 0FFFFFFFFh
0x180051cef  mov     rax, rcx
0x180051cf2  cmovz   rax, cs:DhcpGlobalGenericEndpointReadyEvent
0x180051cfa  mov     [rbp+57h+hEvent], rax
0x180051cfe  xor     eax, eax
0x180051d00  cmp     dword ptr [rsp+120h+var_F0], eax
0x180051d04  jz      short loc_180051D0A
0x180051d06  mov     [rbp+57h+hEvent], rcx
0x180051d0a  call    DhcpDnsHandleCallbacks
0x180051d0f  call    Dhcpv6DnsHandleCallbacks
0x180051d14  xor     r8d, r8d; bWaitAll
0x180051d17  mov     [rsp+120h+bAlertable], 1; bAlertable
0x180051d1f  mov     r9d, ebx; dwMilliseconds
0x180051d22  lea     rdx, [rbp+57h+Handles]; lpHandles
0x180051d26  lea     ecx, [r8+3]; nCount
0x180051d2a  call    cs:__imp_WaitForMultipleObjectsEx
0x180051d31  nop     dword ptr [rax+rax+00h]
0x180051d36  xor     ebx, ebx
0x180051d38  mov     ecx, eax
0x180051d3a  test    eax, eax
0x180051d3c  jz      loc_18005219E
0x180051d42  sub     ecx, 1
0x180051d45  jz      loc_18005216B
0x180051d4b  sub     ecx, 1
0x180051d4e  jz      loc_180051BB1
0x180051d54  sub     ecx, 0BEh
0x180051d5a  jz      loc_180051BB1
0x180051d60  cmp     ecx, 42h ; 'B'
0x180051d63  jz      short loc_180051D96
0x180051d65  mov     rcx, cs:WPP_GLOBAL_Control
0x180051d6c  cmp     rcx, rsi
0x180051d6f  jz      loc_180051BB1
0x180051d75  test    byte ptr [rcx+1Ch], 10h
0x180051d79  jz      loc_180051BB1
0x180051d7f  mov     rcx, [rcx+10h]
0x180051d83  lea     edx, [rbx+27h]
0x180051d86  mov     r9d, eax
0x180051d89  mov     r8, r14
0x180051d8c  call    WPP_SF_D
0x180051d91  jmp     loc_180051BB1
0x180051d96  cmp     edi, 0FFFFFFFFh
0x180051d99  jz      short loc_180051DB1
0x180051d9b  xor     ecx, ecx; Time
0x180051d9d  call    cs:__imp_time
0x180051da4  nop     dword ptr [rax+rax+00h]
0x180051da9  cmp     eax, edi
0x180051dab  jnb     loc_180051BB1
0x180051db1  call    DhcpGetDateTime
0x180051db6  mov     qword ptr [rsp+120h+var_E8.dwLowDateTime], rax
0x180051dbb  mov     eax, r15d
0x180051dbe  test    r15d, r15d
0x180051dc1  jz      loc_180051F45
0x180051dc7  sub     eax, 1
0x180051dca  jz      loc_180051E9A
0x180051dd0  sub     eax, 1
0x180051dd3  jz      loc_180051E5B
0x180051dd9  sub     eax, 1
0x180051ddc  jz      short loc_180051E50
0x180051dde  cmp     eax, 1
0x180051de1  jnz     loc_18005215C
0x180051de7  cmp     cs:DhcpGlobalIsStatelessTestEnv, ebx
0x180051ded  jz      short loc_180051E12
0x180051def  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, al
0x180051df5  jz      short loc_180051E12
0x180051df7  lea     rax, [rbp+57h+var_50]
0x180051dfb  mov     r9d, 1
0x180051e01  lea     rdx, ScavengerStatelessStart
0x180051e08  mov     qword ptr [rsp+120h+bAlertable], rax
0x180051e0d  call    McGenEventWrite_EventWriteTransfer
0x180051e12  call    ScavengeStatelessEntries
0x180051e17  cmp     cs:DhcpGlobalIsStatelessTestEnv, ebx
0x180051e1d  jz      loc_180051F30
0x180051e23  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 1
0x180051e2a  jz      loc_180051F30
0x180051e30  lea     rax, [rbp+57h+var_40]
0x180051e34  mov     r9d, 1
0x180051e3a  lea     rdx, ScavengerStatelessEnd
0x180051e41  mov     qword ptr [rsp+120h+bAlertable], rax
0x180051e46  call    McGenEventWrite_EventWriteTransfer
0x180051e4b  jmp     loc_180051F30
0x180051e50  mov     eax, cs:DhcpGlobalScavengeIpAddress
0x180051e56  jmp     loc_18005210F
0x180051e5b  xor     edx, edx
0x180051e5d  lea     rcx, [rsp+120h+var_E8]
0x180051e62  call    CleanupDatabase
0x180051e67  mov     rcx, cs:WPP_GLOBAL_Control
0x180051e6e  cmp     rcx, rsi
0x180051e71  jz      loc_180051F30
0x180051e77  test    byte ptr [rcx+1Ch], 10h
0x180051e7b  jz      loc_180051F30
0x180051e81  mov     rcx, [rcx+10h]
0x180051e85  mov     edx, 24h ; '$'
0x180051e8a  mov     r9d, eax
0x180051e8d  mov     r8, r14
0x180051e90  call    WPP_SF_D
0x180051e95  jmp     loc_180051F30
0x180051e9a  mov     rcx, cs:DhcpGlobalBackupConfigFileName; lpFileName
0x180051ea1  call    DhcpBackupConfiguration
0x180051ea6  mov     ebx, eax
0x180051ea8  test    eax, eax
0x180051eaa  jz      short loc_180051EE4
0x180051eac  mov     r8d, eax
0x180051eaf  mov     edx, 1
0x180051eb4  mov     ecx, 3F9h
0x180051eb9  call    DhcpServerEventLog
0x180051ebe  mov     rcx, cs:WPP_GLOBAL_Control
0x180051ec5  cmp     rcx, rsi
0x180051ec8  jz      short loc_180051EE4
0x180051eca  test    byte ptr [rcx+1Ch], 10h
0x180051ece  jz      short loc_180051EE4
0x180051ed0  mov     rcx, [rcx+10h]
0x180051ed4  mov     edx, 25h ; '%'
0x180051ed9  mov     r9d, ebx
0x180051edc  mov     r8, r14
0x180051edf  call    WPP_SF_D
0x180051ee4  mov     rcx, cs:DhcpGlobalOemJetBackupPath
0x180051eeb  call    DhcpBackupDatabase
0x180051ef0  mov     ebx, eax
0x180051ef2  test    eax, eax
0x180051ef4  jz      short loc_180051F2E
  ... truncated ...
```

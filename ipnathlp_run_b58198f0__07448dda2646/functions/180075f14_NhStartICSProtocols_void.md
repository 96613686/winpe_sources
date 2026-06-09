# NhStartICSProtocols(void)

- ea: `0x180075f14`
- end: `0x1800765cd`
- name: `?NhStartICSProtocols@@YAKXZ`
- size: `1721`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004be98`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x180014b7c`
- `0x1800202e0`
- `0x18002259c`
- `0x1800231d0`
- `0x1800271d0`
- `0x1800437a0`
- `0x18004561c`
- `0x18004f0a0`
- `0x180051f30`
- `0x180059a04`
- `0x18006f210`
- `0x180072ffc`
- `0x18007368c`
- `0x180075f14`
- `0x180076724`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076111`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076111`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076148`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076148`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180076096`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180076221`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180076313`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180076096`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180076221`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180076313`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076011`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800760d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007625d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007634f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076011`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800760d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007625d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007634f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007618b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800762ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800763b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007618b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800762ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800763b3`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180075fcb`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180075fcb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800763d7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800763d7`

## pseudocode

```c
__int64 NhStartICSProtocols(void)
{
  unsigned int started; // edi
  SC_HANDLE v1; // rax
  __int64 v2; // r9
  SC_HANDLE v3; // rbx
  PVOID *v4; // rcx
  signed int LastError; // eax
  PVOID *v6; // rcx
  signed int v7; // eax
  __int64 v8; // rdx
  int IsServiceRunningOrGoingToRun; // eax
  unsigned __int8 v10; // al
  unsigned int v11; // eax
  struct _SUPPORT_FUNCTIONS_50 *v12; // rdx
  void *v13; // rcx
  unsigned int v14; // r9d
  unsigned int v15; // eax
  unsigned int v16; // eax
  int v17; // eax
  int v18; // ebx
  _QWORD *v19; // rdi
  int v20; // eax
  unsigned __int8 *v22; // rcx
  unsigned __int8 IPv4FragGrouping; // al
  unsigned int v24; // [rsp+20h] [rbp-49h]
  unsigned int v25; // [rsp+20h] [rbp-49h]
  unsigned int v26; // [rsp+28h] [rbp-41h]
  __int64 v27; // [rsp+30h] [rbp-39h] BYREF
  int v28; // [rsp+38h] [rbp-31h]
  unsigned int v29; // [rsp+3Ch] [rbp-2Dh] BYREF
  unsigned int v30[2]; // [rsp+40h] [rbp-29h] BYREF
  _QWORD *v31; // [rsp+48h] [rbp-21h] BYREF
  _QWORD v32[3]; // [rsp+50h] [rbp-19h] BYREF
  _DWORD v33[4]; // [rsp+68h] [rbp-1h] BYREF
  __int64 v34; // [rsp+78h] [rbp+Fh]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
  }
  v28 = 10080;
  v27 = 1;
  v33[0] = 1;
  v33[1] = 1;
  v33[3] = 1;
  v34 = 0;
  started = 1003;
  v32[0] = 1;
  v32[1] = 0;
  v32[2] = 0;
  v29 = 16820416;
  *(_QWORD *)v30 = 0xFFFFFF;
  v33[2] = 3;
  v1 = OpenSCManagerW(0, 0, 0x80000000);
  v3 = v1;
  if ( v1 )
  {
    NoLocalDns = (unsigned int)NhpIsServiceRunningOrGoingToRun(v1, L"DNS") == 0;
LABEL_13:
    v4 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_14;
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_18;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      67,
      &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
      (unsigned int)LastError);
    goto LABEL_13;
  }
LABEL_14:
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x200) != 0 && *((_BYTE *)v4 + 25) >= 5u )
  {
    LOBYTE(v2) = NoLocalDns != 0;
    WPP_SF_c(v4[2], 68, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v2);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_18:
  if ( NoLocalDns )
  {
    NhpStopDnsEvent = CreateEventW(0, 0, 0, 0);
    if ( !NhpStopDnsEvent )
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v7 = GetLastError();
          if ( v7 > 0 )
            v7 = (unsigned __int16)v7 | 0x80070000;
          v8 = 69;
LABEL_26:
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v8,
            &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
            (unsigned int)v7);
LABEL_92:
          v6 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_93;
        }
        goto LABEL_93;
      }
      return started;
    }
    EnterCriticalSection(&g_csDnsLock);
    started = DnsRmStartProtocol(NhpStopDnsEvent, 0, v33, 1u, 0x18u, 1u);
    LeaveCriticalSection(&g_csDnsLock);
    if ( started )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, started);
      }
      CloseHandle(NhpStopDnsEvent);
      NhpStopDnsEvent = 0;
      goto LABEL_92;
    }
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v3 )
  {
    IsServiceRunningOrGoingToRun = NhpIsServiceRunningOrGoingToRun(v3, L"DHCPServer");
    v4 = (PVOID *)WPP_GLOBAL_Control;
    v10 = IsServiceRunningOrGoingToRun == 0;
    NhpNoLocalDhcp = v10;
  }
  else
  {
    v10 = NhpNoLocalDhcp;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x200) != 0 && *((_BYTE *)v4 + 25) >= 5u )
  {
    LOBYTE(v2) = v10 != 0;
    WPP_SF_c(v4[2], 71, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v2);
    v10 = NhpNoLocalDhcp;
  }
  if ( v10 )
  {
    ClearPersistentDhcpExceptions();
    NhpStopDhcpEvent = CreateEventW(0, 0, 0, 0);
    if ( !NhpStopDhcpEvent )
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          v7 = GetLastError();
          if ( v7 > 0 )
            v7 = (unsigned __int16)v7 | 0x80070000;
          v8 = 72;
          goto LABEL_26;
        }
LABEL_93:
        if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x200) != 0 && *((_BYTE *)v6 + 25) >= 6u )
          WPP_SF_d(v6[2], 82, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, started);
      }
      return started;
    }
    NhQueryScopeInformation(&v29, v30);
    v29 &= v30[0];
    v11 = DhcpRmStartProtocol(NhpStopDhcpEvent, 0, &v27, 1u, 0x18u, 1u);
    started = v11;
    if ( v11 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v11);
      }
      CloseHandle(NhpStopDhcpEvent);
      NhpStopDhcpEvent = 0;
      goto LABEL_92;
    }
  }
  NhpStopDhcpV6InformEvent = CreateEventW(0, 0, 0, 0);
  if ( !NhpStopDhcpV6InformEvent )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v7 = GetLastError();
        if ( v7 > 0 )
          v7 = (unsigned __int16)v7 | 0x80070000;
        v8 = 74;
        goto LABEL_26;
      }
      goto LABEL_93;
    }
    return started;
  }
  v15 = DhcpV6InformRmStartProtocol(v13, v12, v32, v14, v24, v26);
  started = v15;
  if ( v15 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v15);
    }
    CloseHandle(NhpStopDhcpV6InformEvent);
    NhpStopDhcpV6InformEvent = 0;
    goto LABEL_92;
  }
  if ( v3 )
    CloseServiceHandle(v3);
  v16 = NhpEnableQoSWindowSizeAdjustment(1u);
  if ( v16 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v16);
    }
  }
  else
  {
    NhpQoSEnabled = 1;
  }
  v31 = 0;
  v17 = ATL::CComObject<CUdpBroadcastMapper>::CreateInstance(&v31);
  v18 = v17;
  if ( v17 < 0 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_88:
      started = 1003;
      if ( v6 != &WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)v6 + 7) & 0x200) != 0 && *((_BYTE *)v6 + 25) >= 2u )
        {
          WPP_SF_Dd(v6[2], 80, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, (unsigned int)v18, 1003);
          goto LABEL_92;
        }
        goto LABEL_93;
      }
      return started;
    }
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      77,
      &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
      (unsigned int)v17);
LABEL_87:
    v6 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_88;
  }
  v19 = v31;
  (*(void (__fastcall **)(_QWORD *))(*v31 + 8LL))(v31);
  v19[18] = &NatComponentReference;
  v20 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, struct IUdpBroadcastMapper **))*v19)(
          v19,
          &GUID_e501032a_64d3_492f_980e_a04d0fac3d7d,
          &NhpUdpBroadcastMapper);
  v18 = v20;
  if ( v20 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      79,
      &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
      (unsigned int)v20);
  }
  (*(void (__fastcall **)(_QWORD *))(*v19 + 16LL))(v19);
  if ( v18 < 0 )
    goto LABEL_87;
  StartBeaconSvr();
  IPv4FragGrouping = GroupForwardedFragmentsEnabled;
  if ( !GroupForwardedFragmentsEnabled )
  {
    IPv4FragGrouping = NatGetIPv4FragGrouping(v22);
    GroupForwardedFragmentsEnabled = IPv4FragGrouping;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(v25) = IPv4FragGrouping;
    WPP_SF_Dc(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, 0, v25);
  }
  return 0;
}

```

## disassembly

```asm
0x180075f14  push    rbp
0x180075f16  push    rbx
0x180075f17  push    rdi
0x180075f18  push    r12
0x180075f1a  push    r13
0x180075f1c  push    r14
0x180075f1e  push    r15
0x180075f20  lea     rbp, [rsp-27h]
0x180075f25  sub     rsp, 90h
0x180075f2c  mov     rax, cs:__security_cookie
0x180075f33  xor     rax, rsp
0x180075f36  mov     [rbp+57h+var_40], rax
0x180075f3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180075f41  lea     r15, WPP_GLOBAL_Control
0x180075f48  lea     r12, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180075f4f  mov     r14d, 200h
0x180075f55  cmp     rcx, r15
0x180075f58  jz      short loc_180075F77
0x180075f5a  test    [rcx+1Ch], r14d
0x180075f5e  jz      short loc_180075F77
0x180075f60  cmp     byte ptr [rcx+19h], 6
0x180075f64  jb      short loc_180075F77
0x180075f66  mov     rcx, [rcx+10h]
0x180075f6a  mov     edx, 42h ; 'B'
0x180075f6f  mov     r8, r12
0x180075f72  call    WPP_SF_
0x180075f77  mov     r13d, 1
0x180075f7d  mov     [rbp+57h+var_88], 2760h
0x180075f84  xor     eax, eax
0x180075f86  mov     [rbp+57h+var_90], r13
0x180075f8a  xor     edx, edx; lpDatabaseName
0x180075f8c  mov     [rbp+57h+var_58], r13d
0x180075f90  xor     ecx, ecx; lpMachineName
0x180075f92  mov     [rbp+57h+var_54], r13d
0x180075f96  mov     r8d, 80000000h; dwDesiredAccess
0x180075f9c  mov     [rbp+57h+var_4C], r13d
0x180075fa0  mov     [rbp+57h+var_48], rax
0x180075fa4  mov     edi, 3EBh
0x180075fa9  mov     [rbp+57h+var_70], r13
0x180075fad  mov     [rbp+57h+var_68], rax
0x180075fb1  mov     [rbp+57h+var_60], rax
0x180075fb5  mov     [rbp+57h+var_84], 100A8C0h
0x180075fbc  mov     qword ptr [rbp+57h+var_80], 0FFFFFFh
0x180075fc4  mov     [rbp+57h+var_50], 3
0x180075fcb  call    cs:__imp_OpenSCManagerW
0x180075fd2  nop     dword ptr [rax+rax+00h]
0x180075fd7  mov     rbx, rax
0x180075fda  test    rax, rax
0x180075fdd  jz      short loc_180075FF9
0x180075fdf  lea     rdx, aDns_2; "DNS"
0x180075fe6  mov     rcx, rax; hSCManager
0x180075fe9  call    ?NhpIsServiceRunningOrGoingToRun@@YAHPEAUSC_HANDLE__@@PEBG@Z; NhpIsServiceRunningOrGoingToRun(SC_HANDLE__ *,ushort const *)
0x180075fee  test    eax, eax
0x180075ff0  setz    cs:?NoLocalDns@@3EA; uchar NoLocalDns
0x180075ff7  jmp     short loc_180076044
0x180075ff9  mov     rcx, cs:WPP_GLOBAL_Control
0x180076000  cmp     rcx, r15
0x180076003  jz      short loc_18007607F
0x180076005  test    [rcx+1Ch], r14d
0x180076009  jz      short loc_18007604B
0x18007600b  cmp     byte ptr [rcx+19h], 3
0x18007600f  jb      short loc_18007604B
0x180076011  call    cs:__imp_GetLastError
0x180076018  nop     dword ptr [rax+rax+00h]
0x18007601d  test    eax, eax
0x18007601f  jle     short loc_180076029
0x180076021  movzx   eax, ax
0x180076024  or      eax, 80070000h
0x180076029  mov     rcx, cs:WPP_GLOBAL_Control
0x180076030  mov     edx, 43h ; 'C'
0x180076035  mov     r9d, eax
0x180076038  mov     r8, r12
0x18007603b  mov     rcx, [rcx+10h]
0x18007603f  call    WPP_SF_d
0x180076044  mov     rcx, cs:WPP_GLOBAL_Control
0x18007604b  cmp     rcx, r15
0x18007604e  jz      short loc_18007607F
0x180076050  test    [rcx+1Ch], r14d
0x180076054  jz      short loc_18007607F
0x180076056  cmp     byte ptr [rcx+19h], 5
0x18007605a  jb      short loc_18007607F
0x18007605c  cmp     cs:?NoLocalDns@@3EA, 0; uchar NoLocalDns
0x180076063  mov     edx, 44h ; 'D'
0x180076068  mov     rcx, [rcx+10h]
0x18007606c  mov     r8, r12
0x18007606f  setnz   r9b
0x180076073  call    WPP_SF_c
0x180076078  mov     rcx, cs:WPP_GLOBAL_Control
0x18007607f  cmp     cs:?NoLocalDns@@3EA, 0; uchar NoLocalDns
0x180076086  jz      loc_1800761AE
0x18007608c  xor     r9d, r9d; lpName
0x18007608f  xor     r8d, r8d; bInitialState
0x180076092  xor     edx, edx; bManualReset
0x180076094  xor     ecx, ecx; lpEventAttributes
0x180076096  call    cs:__imp_CreateEventW
0x18007609d  nop     dword ptr [rax+rax+00h]
0x1800760a2  mov     cs:?NhpStopDnsEvent@@3PEAXEA, rax; void * NhpStopDnsEvent
0x1800760a9  test    rax, rax
0x1800760ac  jnz     short loc_18007610A
0x1800760ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800760b5  cmp     rcx, r15
0x1800760b8  jz      loc_18007655D
0x1800760be  test    [rcx+1Ch], r14d
0x1800760c2  jz      loc_180076538
0x1800760c8  cmp     byte ptr [rcx+19h], 2
0x1800760cc  jb      loc_180076538
0x1800760d2  call    cs:__imp_GetLastError
0x1800760d9  nop     dword ptr [rax+rax+00h]
0x1800760de  test    eax, eax
0x1800760e0  jle     short loc_1800760EA
0x1800760e2  movzx   eax, ax
0x1800760e5  or      eax, 80070000h
0x1800760ea  mov     edx, 45h ; 'E'
0x1800760ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800760f6  mov     r9d, eax
0x1800760f9  mov     r8, r12
0x1800760fc  mov     rcx, [rcx+10h]
0x180076100  call    WPP_SF_d
0x180076105  jmp     loc_180076531
0x18007610a  lea     rcx, ?g_csDnsLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180076111  call    cs:__imp_EnterCriticalSection
0x180076118  nop     dword ptr [rax+rax+00h]
0x18007611d  mov     rcx, cs:?NhpStopDnsEvent@@3PEAXEA; void *
0x180076124  lea     r8, [rbp+57h+var_58]; void *
0x180076128  mov     r9d, r13d; unsigned int
0x18007612b  mov     [rsp+0C0h+var_98], r13d; unsigned int
0x180076130  xor     edx, edx; struct _SUPPORT_FUNCTIONS_50 *
0x180076132  mov     [rsp+0C0h+var_A0], 18h; unsigned int
0x18007613a  call    ?DnsRmStartProtocol@@YAKPEAXPEAU_SUPPORT_FUNCTIONS_50@@0KKK@Z; DnsRmStartProtocol(void *,_SUPPORT_FUNCTIONS_50 *,void *,ulong,ulong,ulong)
0x18007613f  lea     rcx, ?g_csDnsLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180076146  mov     edi, eax
0x180076148  call    cs:__imp_LeaveCriticalSection
0x18007614f  nop     dword ptr [rax+rax+00h]
0x180076154  test    edi, edi
0x180076156  jz      short loc_1800761A7
0x180076158  mov     rcx, cs:WPP_GLOBAL_Control
0x18007615f  cmp     rcx, r15
0x180076162  jz      short loc_180076184
0x180076164  test    [rcx+1Ch], r14d
0x180076168  jz      short loc_180076184
0x18007616a  cmp     byte ptr [rcx+19h], 2
0x18007616e  jb      short loc_180076184
0x180076170  mov     rcx, [rcx+10h]
0x180076174  mov     edx, 46h ; 'F'
0x180076179  mov     r9d, edi
0x18007617c  mov     r8, r12
0x18007617f  call    WPP_SF_d
0x180076184  mov     rcx, cs:?NhpStopDnsEvent@@3PEAXEA; hObject
0x18007618b  call    cs:__imp_CloseHandle
0x180076192  nop     dword ptr [rax+rax+00h]
0x180076197  mov     cs:?NhpStopDnsEvent@@3PEAXEA, 0; void * NhpStopDnsEvent
0x1800761a2  jmp     loc_180076531
0x1800761a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800761ae  test    rbx, rbx
0x1800761b1  jz      short loc_1800761D6
0x1800761b3  lea     rdx, aDhcpserver_1; "DHCPServer"
0x1800761ba  mov     rcx, rbx; hSCManager
0x1800761bd  call    ?NhpIsServiceRunningOrGoingToRun@@YAHPEAUSC_HANDLE__@@PEBG@Z; NhpIsServiceRunningOrGoingToRun(SC_HANDLE__ *,ushort const *)
0x1800761c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800761c9  test    eax, eax
0x1800761cb  setz    al
0x1800761ce  mov     cs:?NhpNoLocalDhcp@@3EA, al; uchar NhpNoLocalDhcp
0x1800761d4  jmp     short loc_1800761DC
0x1800761d6  mov     al, cs:?NhpNoLocalDhcp@@3EA; uchar NhpNoLocalDhcp
0x1800761dc  cmp     rcx, r15
0x1800761df  jz      short loc_18007620A
0x1800761e1  test    [rcx+1Ch], r14d
0x1800761e5  jz      short loc_18007620A
0x1800761e7  cmp     byte ptr [rcx+19h], 5
0x1800761eb  jb      short loc_18007620A
0x1800761ed  mov     rcx, [rcx+10h]
0x1800761f1  test    al, al
0x1800761f3  mov     edx, 47h ; 'G'
0x1800761f8  mov     r8, r12
0x1800761fb  setnz   r9b
0x1800761ff  call    WPP_SF_c
0x180076204  mov     al, cs:?NhpNoLocalDhcp@@3EA; uchar NhpNoLocalDhcp
0x18007620a  test    al, al
0x18007620c  jz      loc_180076309
0x180076212  call    ?ClearPersistentDhcpExceptions@@YAXXZ; ClearPersistentDhcpExceptions(void)
0x180076217  xor     r9d, r9d; lpName
0x18007621a  xor     r8d, r8d; bInitialState
0x18007621d  xor     edx, edx; bManualReset
0x18007621f  xor     ecx, ecx; lpEventAttributes
0x180076221  call    cs:__imp_CreateEventW
0x180076228  nop     dword ptr [rax+rax+00h]
0x18007622d  mov     cs:?NhpStopDhcpEvent@@3PEAXEA, rax; void * NhpStopDhcpEvent
0x180076234  test    rax, rax
0x180076237  jnz     short loc_18007627F
0x180076239  mov     rcx, cs:WPP_GLOBAL_Control
0x180076240  cmp     rcx, r15
0x180076243  jz      loc_18007655D
0x180076249  test    [rcx+1Ch], r14d
0x18007624d  jz      loc_180076538
0x180076253  cmp     byte ptr [rcx+19h], 3
0x180076257  jb      loc_180076538
0x18007625d  call    cs:__imp_GetLastError
0x180076264  nop     dword ptr [rax+rax+00h]
0x180076269  test    eax, eax
0x18007626b  jle     short loc_180076275
0x18007626d  movzx   eax, ax
0x180076270  or      eax, 80070000h
0x180076275  mov     edx, 48h ; 'H'
0x18007627a  jmp     loc_1800760EF
0x18007627f  lea     rdx, [rbp+57h+var_80]; unsigned int *
0x180076283  lea     rcx, [rbp+57h+var_84]; unsigned int *
0x180076287  call    ?NhQueryScopeInformation@@YAEPEAK0@Z; NhQueryScopeInformation(ulong *,ulong *)
0x18007628c  mov     eax, [rbp+57h+var_80]
0x18007628f  lea     r8, [rbp+57h+var_90]; void *
0x180076293  mov     rcx, cs:?NhpStopDhcpEvent@@3PEAXEA; void *
0x18007629a  mov     r9d, r13d; unsigned int
0x18007629d  and     [rbp+57h+var_84], eax
0x1800762a0  xor     edx, edx; struct _SUPPORT_FUNCTIONS_50 *
0x1800762a2  mov     [rsp+0C0h+var_98], r13d; unsigned int
0x1800762a7  mov     [rsp+0C0h+var_A0], 18h; unsigned int
0x1800762af  call    ?DhcpRmStartProtocol@@YAKPEAXPEAU_SUPPORT_FUNCTIONS_50@@0KKK@Z; DhcpRmStartProtocol(void *,_SUPPORT_FUNCTIONS_50 *,void *,ulong,ulong,ulong)
0x1800762b4  mov     edi, eax
0x1800762b6  test    eax, eax
0x1800762b8  jz      short loc_180076309
0x1800762ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800762c1  cmp     rcx, r15
0x1800762c4  jz      short loc_1800762E6
0x1800762c6  test    [rcx+1Ch], r14d
0x1800762ca  jz      short loc_1800762E6
0x1800762cc  cmp     byte ptr [rcx+19h], 2
0x1800762d0  jb      short loc_1800762E6
0x1800762d2  mov     rcx, [rcx+10h]
0x1800762d6  mov     edx, 49h ; 'I'
0x1800762db  mov     r9d, eax
0x1800762de  mov     r8, r12
0x1800762e1  call    WPP_SF_d
0x1800762e6  mov     rcx, cs:?NhpStopDhcpEvent@@3PEAXEA; hObject
0x1800762ed  call    cs:__imp_CloseHandle
0x1800762f4  nop     dword ptr [rax+rax+00h]
0x1800762f9  mov     cs:?NhpStopDhcpEvent@@3PEAXEA, 0; void * NhpStopDhcpEvent
0x180076304  jmp     loc_180076531
0x180076309  xor     r9d, r9d; lpName
0x18007630c  xor     r8d, r8d; bInitialState
0x18007630f  xor     edx, edx; bManualReset
0x180076311  xor     ecx, ecx; lpEventAttributes
0x180076313  call    cs:__imp_CreateEventW
0x18007631a  nop     dword ptr [rax+rax+00h]
0x18007631f  mov     cs:?NhpStopDhcpV6InformEvent@@3PEAXEA, rax; void * NhpStopDhcpV6InformEvent
0x180076326  test    rax, rax
0x180076329  jnz     short loc_180076371
0x18007632b  mov     rcx, cs:WPP_GLOBAL_Control
0x180076332  cmp     rcx, r15
0x180076335  jz      loc_18007655D
0x18007633b  test    [rcx+1Ch], r14d
0x18007633f  jz      loc_180076538
0x180076345  cmp     byte ptr [rcx+19h], 3
0x180076349  jb      loc_180076538
0x18007634f  call    cs:__imp_GetLastError
0x180076356  nop     dword ptr [rax+rax+00h]
0x18007635b  test    eax, eax
0x18007635d  jle     short loc_180076367
0x18007635f  movzx   eax, ax
0x180076362  or      eax, 80070000h
0x180076367  mov     edx, 4Ah ; 'J'
0x18007636c  jmp     loc_1800760EF
0x180076371  lea     r8, [rbp+57h+var_70]; void *
0x180076375  call    ?DhcpV6InformRmStartProtocol@@YAKPEAXPEAU_SUPPORT_FUNCTIONS_50@@0KKK@Z; DhcpV6InformRmStartProtocol(void *,_SUPPORT_FUNCTIONS_50 *,void *,ulong,ulong,ulong)
0x18007637a  mov     edi, eax
0x18007637c  test    eax, eax
0x18007637e  jz      short loc_1800763CF
0x180076380  mov     rcx, cs:WPP_GLOBAL_Control
0x180076387  cmp     rcx, r15
0x18007638a  jz      short loc_1800763AC
0x18007638c  test    [rcx+1Ch], r14d
0x180076390  jz      short loc_1800763AC
0x180076392  cmp     byte ptr [rcx+19h], 2
0x180076396  jb      short loc_1800763AC
0x180076398  mov     rcx, [rcx+10h]
0x18007639c  mov     edx, 4Bh ; 'K'
0x1800763a1  mov     r9d, eax
0x1800763a4  mov     r8, r12
0x1800763a7  call    WPP_SF_d
0x1800763ac  mov     rcx, cs:?NhpStopDhcpV6InformEvent@@3PEAXEA; hObject
0x1800763b3  call    cs:__imp_CloseHandle
0x1800763ba  nop     dword ptr [rax+rax+00h]
0x1800763bf  mov     cs:?NhpStopDhcpV6InformEvent@@3PEAXEA, 0; void * NhpStopDhcpV6InformEvent
0x1800763ca  jmp     loc_180076531
0x1800763cf  test    rbx, rbx
0x1800763d2  jz      short loc_1800763E3
0x1800763d4  mov     rcx, rbx; hSCObject
0x1800763d7  call    cs:__imp_CloseServiceHandle
0x1800763de  nop     dword ptr [rax+rax+00h]
0x1800763e3  mov     cl, r13b; unsigned __int8
0x1800763e6  call    ?NhpEnableQoSWindowSizeAdjustment@@YAKE@Z; NhpEnableQoSWindowSizeAdjustment(uchar)
0x1800763eb  test    eax, eax
0x1800763ed  jnz     short loc_1800763F8
0x1800763ef  mov     cs:?NhpQoSEnabled@@3EA, r13b; uchar NhpQoSEnabled
0x1800763f6  jmp     short loc_180076424
0x1800763f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800763ff  cmp     rcx, r15
0x180076402  jz      short loc_180076424
0x180076404  test    [rcx+1Ch], r14d
0x180076408  jz      short loc_180076424
0x18007640a  cmp     byte ptr [rcx+19h], 3
0x18007640e  jb      short loc_180076424
  ... truncated ...
```

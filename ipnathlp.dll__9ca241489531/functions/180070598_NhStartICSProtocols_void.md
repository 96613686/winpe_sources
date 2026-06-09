# NhStartICSProtocols(void)

- ea: `0x180070598`
- end: `0x180070bfc`
- name: `?NhStartICSProtocols@@YAKXZ`
- size: `1636`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800482c0`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x180013b78`
- `0x18001ec08`
- `0x180024c90`
- `0x18002f690`
- `0x1800301f0`
- `0x180040198`
- `0x18004215c`
- `0x18004b358`
- `0x18004e0c0`
- `0x180055728`
- `0x180069eac`
- `0x18006d87c`
- `0x18006dec8`
- `0x180070598`
- `0x180070d4c`
- `0x180090010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007077d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007077d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800707ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800707ae`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007070e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007087b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007095b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007070e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007087b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007095b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007068f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070744`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800708b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007068f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070744`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800708b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070991`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800707eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007093b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800709ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800707eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007093b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800709ef`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18007064f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18007064f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180070a0d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180070a0d`

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
  unsigned int v14; // eax
  unsigned int v15; // eax
  int v16; // eax
  int v17; // ebx
  volatile int *v18; // rdi
  int v19; // eax
  unsigned __int8 *v21; // rcx
  unsigned __int8 IPv4FragGrouping; // al
  unsigned int v23; // [rsp+20h] [rbp-49h]
  __int64 v24; // [rsp+30h] [rbp-39h] BYREF
  int v25; // [rsp+38h] [rbp-31h]
  unsigned int v26; // [rsp+3Ch] [rbp-2Dh] BYREF
  unsigned int v27[2]; // [rsp+40h] [rbp-29h] BYREF
  volatile int *v28; // [rsp+48h] [rbp-21h] BYREF
  _QWORD v29[3]; // [rsp+50h] [rbp-19h] BYREF
  _DWORD v30[4]; // [rsp+68h] [rbp-1h] BYREF
  __int64 v31; // [rsp+78h] [rbp+Fh]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
  }
  v25 = 10080;
  v24 = 1;
  v30[0] = 1;
  v30[1] = 1;
  v30[3] = 1;
  v31 = 0;
  started = 1003;
  v29[0] = 1;
  v29[1] = 0;
  v29[2] = 0;
  v26 = 16820416;
  *(_QWORD *)v27 = 0xFFFFFF;
  v30[2] = 3;
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
    started = DnsRmStartProtocol(NhpStopDnsEvent, 0, v30, 1u, 0x18u, 1u);
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
    NhQueryScopeInformation(&v26, v27);
    v26 &= v27[0];
    v23 = 24;
    v11 = DhcpRmStartProtocol(NhpStopDhcpEvent, 0, (struct _IP_AUTO_DHCP_GLOBAL_INFO *)&v24);
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
  v14 = DhcpV6InformRmStartProtocol(v13, v12, v29);
  started = v14;
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v14);
    }
    CloseHandle(NhpStopDhcpV6InformEvent);
    NhpStopDhcpV6InformEvent = 0;
    goto LABEL_92;
  }
  if ( v3 )
    CloseServiceHandle(v3);
  v15 = NhpEnableQoSWindowSizeAdjustment(1u);
  if ( v15 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v15);
    }
  }
  else
  {
    NhpQoSEnabled = 1;
  }
  v28 = 0;
  v16 = ATL::CComObject<CUdpBroadcastMapper>::CreateInstance(&v28);
  v17 = v16;
  if ( v16 < 0 )
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
          WPP_SF_Dd(v6[2], 80, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, (unsigned int)v17, 1003);
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
      (unsigned int)v16);
LABEL_87:
    v6 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_88;
  }
  v18 = v28;
  (*(void (__fastcall **)(volatile int *))(*(_QWORD *)v28 + 8LL))(v28);
  *((_QWORD *)v18 + 18) = &NatComponentReference;
  v19 = (**(__int64 (__fastcall ***)(volatile int *, GUID *, struct IUdpBroadcastMapper **))v18)(
          v18,
          &GUID_e501032a_64d3_492f_980e_a04d0fac3d7d,
          &NhpUdpBroadcastMapper);
  v17 = v19;
  if ( v19 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      79,
      &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
      (unsigned int)v19);
  }
  (*(void (__fastcall **)(volatile int *))(*(_QWORD *)v18 + 16LL))(v18);
  if ( v17 < 0 )
    goto LABEL_87;
  StartBeaconSvr();
  IPv4FragGrouping = GroupForwardedFragmentsEnabled;
  if ( !GroupForwardedFragmentsEnabled )
  {
    IPv4FragGrouping = NatGetIPv4FragGrouping(v21);
    GroupForwardedFragmentsEnabled = IPv4FragGrouping;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(v23) = IPv4FragGrouping;
    WPP_SF_Dc(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, 0, v23);
  }
  return 0;
}

```

## disassembly

```asm
0x180070598  push    rbp
0x18007059a  push    rbx
0x18007059b  push    rdi
0x18007059c  push    r12
0x18007059e  push    r13
0x1800705a0  push    r14
0x1800705a2  push    r15
0x1800705a4  lea     rbp, [rsp-27h]
0x1800705a9  sub     rsp, 90h
0x1800705b0  mov     rax, cs:__security_cookie
0x1800705b7  xor     rax, rsp
0x1800705ba  mov     [rbp+57h+var_40], rax
0x1800705be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800705c5  lea     r15, WPP_GLOBAL_Control
0x1800705cc  lea     r12, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x1800705d3  mov     r14d, 200h
0x1800705d9  cmp     rcx, r15
0x1800705dc  jz      short loc_1800705FB
0x1800705de  test    [rcx+1Ch], r14d
0x1800705e2  jz      short loc_1800705FB
0x1800705e4  cmp     byte ptr [rcx+19h], 6
0x1800705e8  jb      short loc_1800705FB
0x1800705ea  mov     rcx, [rcx+10h]
0x1800705ee  mov     edx, 42h ; 'B'
0x1800705f3  mov     r8, r12
0x1800705f6  call    WPP_SF_
0x1800705fb  mov     r13d, 1
0x180070601  mov     [rbp+57h+var_88], 2760h
0x180070608  xor     eax, eax
0x18007060a  mov     [rbp+57h+var_90], r13
0x18007060e  xor     edx, edx; lpDatabaseName
0x180070610  mov     [rbp+57h+var_58], r13d
0x180070614  xor     ecx, ecx; lpMachineName
0x180070616  mov     [rbp+57h+var_54], r13d
0x18007061a  mov     r8d, 80000000h; dwDesiredAccess
0x180070620  mov     [rbp+57h+var_4C], r13d
0x180070624  mov     [rbp+57h+var_48], rax
0x180070628  mov     edi, 3EBh
0x18007062d  mov     [rbp+57h+var_70], r13
0x180070631  mov     [rbp+57h+var_68], rax
0x180070635  mov     [rbp+57h+var_60], rax
0x180070639  mov     [rbp+57h+var_84], 100A8C0h
0x180070640  mov     qword ptr [rbp+57h+var_80], 0FFFFFFh
0x180070648  mov     [rbp+57h+var_50], 3
0x18007064f  call    cs:__imp_OpenSCManagerW
0x180070655  mov     rbx, rax
0x180070658  test    rax, rax
0x18007065b  jz      short loc_180070677
0x18007065d  lea     rdx, aDns_2; "DNS"
0x180070664  mov     rcx, rax; hSCManager
0x180070667  call    ?NhpIsServiceRunningOrGoingToRun@@YAHPEAUSC_HANDLE__@@PEBG@Z; NhpIsServiceRunningOrGoingToRun(SC_HANDLE__ *,ushort const *)
0x18007066c  test    eax, eax
0x18007066e  setz    cs:?NoLocalDns@@3EA; uchar NoLocalDns
0x180070675  jmp     short loc_1800706BC
0x180070677  mov     rcx, cs:WPP_GLOBAL_Control
0x18007067e  cmp     rcx, r15
0x180070681  jz      short loc_1800706F7
0x180070683  test    [rcx+1Ch], r14d
0x180070687  jz      short loc_1800706C3
0x180070689  cmp     byte ptr [rcx+19h], 3
0x18007068d  jb      short loc_1800706C3
0x18007068f  call    cs:__imp_GetLastError
0x180070695  test    eax, eax
0x180070697  jle     short loc_1800706A1
0x180070699  movzx   eax, ax
0x18007069c  or      eax, 80070000h
0x1800706a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800706a8  mov     edx, 43h ; 'C'
0x1800706ad  mov     r9d, eax
0x1800706b0  mov     r8, r12
0x1800706b3  mov     rcx, [rcx+10h]
0x1800706b7  call    WPP_SF_d
0x1800706bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800706c3  cmp     rcx, r15
0x1800706c6  jz      short loc_1800706F7
0x1800706c8  test    [rcx+1Ch], r14d
0x1800706cc  jz      short loc_1800706F7
0x1800706ce  cmp     byte ptr [rcx+19h], 5
0x1800706d2  jb      short loc_1800706F7
0x1800706d4  cmp     cs:?NoLocalDns@@3EA, 0; uchar NoLocalDns
0x1800706db  mov     edx, 44h ; 'D'
0x1800706e0  mov     rcx, [rcx+10h]
0x1800706e4  mov     r8, r12
0x1800706e7  setnz   r9b
0x1800706eb  call    WPP_SF_c
0x1800706f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800706f7  cmp     cs:?NoLocalDns@@3EA, 0; uchar NoLocalDns
0x1800706fe  jz      loc_180070808
0x180070704  xor     r9d, r9d; lpName
0x180070707  xor     r8d, r8d; bInitialState
0x18007070a  xor     edx, edx; bManualReset
0x18007070c  xor     ecx, ecx; lpEventAttributes
0x18007070e  call    cs:__imp_CreateEventW
0x180070714  mov     cs:?NhpStopDnsEvent@@3PEAXEA, rax; void * NhpStopDnsEvent
0x18007071b  test    rax, rax
0x18007071e  jnz     short loc_180070776
0x180070720  mov     rcx, cs:WPP_GLOBAL_Control
0x180070727  cmp     rcx, r15
0x18007072a  jz      loc_180070B8D
0x180070730  test    [rcx+1Ch], r14d
0x180070734  jz      loc_180070B68
0x18007073a  cmp     byte ptr [rcx+19h], 2
0x18007073e  jb      loc_180070B68
0x180070744  call    cs:__imp_GetLastError
0x18007074a  test    eax, eax
0x18007074c  jle     short loc_180070756
0x18007074e  movzx   eax, ax
0x180070751  or      eax, 80070000h
0x180070756  mov     edx, 45h ; 'E'
0x18007075b  mov     rcx, cs:WPP_GLOBAL_Control
0x180070762  mov     r9d, eax
0x180070765  mov     r8, r12
0x180070768  mov     rcx, [rcx+10h]
0x18007076c  call    WPP_SF_d
0x180070771  jmp     loc_180070B61
0x180070776  lea     rcx, ?g_csDnsLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18007077d  call    cs:__imp_EnterCriticalSection
0x180070783  mov     rcx, cs:?NhpStopDnsEvent@@3PEAXEA; void *
0x18007078a  lea     r8, [rbp+57h+var_58]; void *
0x18007078e  mov     r9d, r13d; unsigned int
0x180070791  mov     [rsp+0C0h+var_98], r13d; unsigned int
0x180070796  xor     edx, edx; struct _SUPPORT_FUNCTIONS_50 *
0x180070798  mov     [rsp+0C0h+var_A0], 18h; unsigned int
0x1800707a0  call    ?DnsRmStartProtocol@@YAKPEAXPEAU_SUPPORT_FUNCTIONS_50@@0KKK@Z; DnsRmStartProtocol(void *,_SUPPORT_FUNCTIONS_50 *,void *,ulong,ulong,ulong)
0x1800707a5  lea     rcx, ?g_csDnsLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800707ac  mov     edi, eax
0x1800707ae  call    cs:__imp_LeaveCriticalSection
0x1800707b4  test    edi, edi
0x1800707b6  jz      short loc_180070801
0x1800707b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800707bf  cmp     rcx, r15
0x1800707c2  jz      short loc_1800707E4
0x1800707c4  test    [rcx+1Ch], r14d
0x1800707c8  jz      short loc_1800707E4
0x1800707ca  cmp     byte ptr [rcx+19h], 2
0x1800707ce  jb      short loc_1800707E4
0x1800707d0  mov     rcx, [rcx+10h]
0x1800707d4  mov     edx, 46h ; 'F'
0x1800707d9  mov     r9d, edi
0x1800707dc  mov     r8, r12
0x1800707df  call    WPP_SF_d
0x1800707e4  mov     rcx, cs:?NhpStopDnsEvent@@3PEAXEA; hObject
0x1800707eb  call    cs:__imp_CloseHandle
0x1800707f1  mov     cs:?NhpStopDnsEvent@@3PEAXEA, 0; void * NhpStopDnsEvent
0x1800707fc  jmp     loc_180070B61
0x180070801  mov     rcx, cs:WPP_GLOBAL_Control
0x180070808  test    rbx, rbx
0x18007080b  jz      short loc_180070830
0x18007080d  lea     rdx, aDhcpserver_1; "DHCPServer"
0x180070814  mov     rcx, rbx; hSCManager
0x180070817  call    ?NhpIsServiceRunningOrGoingToRun@@YAHPEAUSC_HANDLE__@@PEBG@Z; NhpIsServiceRunningOrGoingToRun(SC_HANDLE__ *,ushort const *)
0x18007081c  mov     rcx, cs:WPP_GLOBAL_Control
0x180070823  test    eax, eax
0x180070825  setz    al
0x180070828  mov     cs:?NhpNoLocalDhcp@@3EA, al; uchar NhpNoLocalDhcp
0x18007082e  jmp     short loc_180070836
0x180070830  mov     al, cs:?NhpNoLocalDhcp@@3EA; uchar NhpNoLocalDhcp
0x180070836  cmp     rcx, r15
0x180070839  jz      short loc_180070864
0x18007083b  test    [rcx+1Ch], r14d
0x18007083f  jz      short loc_180070864
0x180070841  cmp     byte ptr [rcx+19h], 5
0x180070845  jb      short loc_180070864
0x180070847  mov     rcx, [rcx+10h]
0x18007084b  test    al, al
0x18007084d  mov     edx, 47h ; 'G'
0x180070852  mov     r8, r12
0x180070855  setnz   r9b
0x180070859  call    WPP_SF_c
0x18007085e  mov     al, cs:?NhpNoLocalDhcp@@3EA; uchar NhpNoLocalDhcp
0x180070864  test    al, al
0x180070866  jz      loc_180070951
0x18007086c  call    ?ClearPersistentDhcpExceptions@@YAXXZ; ClearPersistentDhcpExceptions(void)
0x180070871  xor     r9d, r9d; lpName
0x180070874  xor     r8d, r8d; bInitialState
0x180070877  xor     edx, edx; bManualReset
0x180070879  xor     ecx, ecx; lpEventAttributes
0x18007087b  call    cs:__imp_CreateEventW
0x180070881  mov     cs:?NhpStopDhcpEvent@@3PEAXEA, rax; void * NhpStopDhcpEvent
0x180070888  test    rax, rax
0x18007088b  jnz     short loc_1800708CD
0x18007088d  mov     rcx, cs:WPP_GLOBAL_Control
0x180070894  cmp     rcx, r15
0x180070897  jz      loc_180070B8D
0x18007089d  test    [rcx+1Ch], r14d
0x1800708a1  jz      loc_180070B68
0x1800708a7  cmp     byte ptr [rcx+19h], 3
0x1800708ab  jb      loc_180070B68
0x1800708b1  call    cs:__imp_GetLastError
0x1800708b7  test    eax, eax
0x1800708b9  jle     short loc_1800708C3
0x1800708bb  movzx   eax, ax
0x1800708be  or      eax, 80070000h
0x1800708c3  mov     edx, 48h ; 'H'
0x1800708c8  jmp     loc_18007075B
0x1800708cd  lea     rdx, [rbp+57h+var_80]; unsigned int *
0x1800708d1  lea     rcx, [rbp+57h+var_84]; unsigned int *
0x1800708d5  call    ?NhQueryScopeInformation@@YAEPEAK0@Z; NhQueryScopeInformation(ulong *,ulong *)
0x1800708da  mov     eax, [rbp+57h+var_80]
0x1800708dd  lea     r8, [rbp+57h+var_90]; void *
0x1800708e1  mov     rcx, cs:?NhpStopDhcpEvent@@3PEAXEA; void *
0x1800708e8  mov     r9d, r13d; unsigned int
0x1800708eb  and     [rbp+57h+var_84], eax
0x1800708ee  xor     edx, edx; struct _SUPPORT_FUNCTIONS_50 *
0x1800708f0  mov     [rsp+0C0h+var_98], r13d; unsigned int
0x1800708f5  mov     [rsp+0C0h+var_A0], 18h; unsigned int
0x1800708fd  call    ?DhcpRmStartProtocol@@YAKPEAXPEAU_SUPPORT_FUNCTIONS_50@@0KKK@Z; DhcpRmStartProtocol(void *,_SUPPORT_FUNCTIONS_50 *,void *,ulong,ulong,ulong)
0x180070902  mov     edi, eax
0x180070904  test    eax, eax
0x180070906  jz      short loc_180070951
0x180070908  mov     rcx, cs:WPP_GLOBAL_Control
0x18007090f  cmp     rcx, r15
0x180070912  jz      short loc_180070934
0x180070914  test    [rcx+1Ch], r14d
0x180070918  jz      short loc_180070934
0x18007091a  cmp     byte ptr [rcx+19h], 2
0x18007091e  jb      short loc_180070934
0x180070920  mov     rcx, [rcx+10h]
0x180070924  mov     edx, 49h ; 'I'
0x180070929  mov     r9d, eax
0x18007092c  mov     r8, r12
0x18007092f  call    WPP_SF_d
0x180070934  mov     rcx, cs:?NhpStopDhcpEvent@@3PEAXEA; hObject
0x18007093b  call    cs:__imp_CloseHandle
0x180070941  mov     cs:?NhpStopDhcpEvent@@3PEAXEA, 0; void * NhpStopDhcpEvent
0x18007094c  jmp     loc_180070B61
0x180070951  xor     r9d, r9d; lpName
0x180070954  xor     r8d, r8d; bInitialState
0x180070957  xor     edx, edx; bManualReset
0x180070959  xor     ecx, ecx; lpEventAttributes
0x18007095b  call    cs:__imp_CreateEventW
0x180070961  mov     cs:?NhpStopDhcpV6InformEvent@@3PEAXEA, rax; void * NhpStopDhcpV6InformEvent
0x180070968  test    rax, rax
0x18007096b  jnz     short loc_1800709AD
0x18007096d  mov     rcx, cs:WPP_GLOBAL_Control
0x180070974  cmp     rcx, r15
0x180070977  jz      loc_180070B8D
0x18007097d  test    [rcx+1Ch], r14d
0x180070981  jz      loc_180070B68
0x180070987  cmp     byte ptr [rcx+19h], 3
0x18007098b  jb      loc_180070B68
0x180070991  call    cs:__imp_GetLastError
0x180070997  test    eax, eax
0x180070999  jle     short loc_1800709A3
0x18007099b  movzx   eax, ax
0x18007099e  or      eax, 80070000h
0x1800709a3  mov     edx, 4Ah ; 'J'
0x1800709a8  jmp     loc_18007075B
0x1800709ad  lea     r8, [rbp+57h+var_70]; void *
0x1800709b1  call    ?DhcpV6InformRmStartProtocol@@YAKPEAXPEAU_SUPPORT_FUNCTIONS_50@@0KKK@Z; DhcpV6InformRmStartProtocol(void *,_SUPPORT_FUNCTIONS_50 *,void *,ulong,ulong,ulong)
0x1800709b6  mov     edi, eax
0x1800709b8  test    eax, eax
0x1800709ba  jz      short loc_180070A05
0x1800709bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800709c3  cmp     rcx, r15
0x1800709c6  jz      short loc_1800709E8
0x1800709c8  test    [rcx+1Ch], r14d
0x1800709cc  jz      short loc_1800709E8
0x1800709ce  cmp     byte ptr [rcx+19h], 2
0x1800709d2  jb      short loc_1800709E8
0x1800709d4  mov     rcx, [rcx+10h]
0x1800709d8  mov     edx, 4Bh ; 'K'
0x1800709dd  mov     r9d, eax
0x1800709e0  mov     r8, r12
0x1800709e3  call    WPP_SF_d
0x1800709e8  mov     rcx, cs:?NhpStopDhcpV6InformEvent@@3PEAXEA; hObject
0x1800709ef  call    cs:__imp_CloseHandle
0x1800709f5  mov     cs:?NhpStopDhcpV6InformEvent@@3PEAXEA, 0; void * NhpStopDhcpV6InformEvent
0x180070a00  jmp     loc_180070B61
0x180070a05  test    rbx, rbx
0x180070a08  jz      short loc_180070A13
0x180070a0a  mov     rcx, rbx; hSCObject
0x180070a0d  call    cs:__imp_CloseServiceHandle
0x180070a13  mov     cl, r13b; unsigned __int8
0x180070a16  call    ?NhpEnableQoSWindowSizeAdjustment@@YAKE@Z; NhpEnableQoSWindowSizeAdjustment(uchar)
0x180070a1b  test    eax, eax
0x180070a1d  jnz     short loc_180070A28
0x180070a1f  mov     cs:?NhpQoSEnabled@@3EA, r13b; uchar NhpQoSEnabled
0x180070a26  jmp     short loc_180070A54
0x180070a28  mov     rcx, cs:WPP_GLOBAL_Control
0x180070a2f  cmp     rcx, r15
0x180070a32  jz      short loc_180070A54
0x180070a34  test    [rcx+1Ch], r14d
0x180070a38  jz      short loc_180070A54
0x180070a3a  cmp     byte ptr [rcx+19h], 3
0x180070a3e  jb      short loc_180070A54
0x180070a40  mov     rcx, [rcx+10h]
0x180070a44  mov     edx, 4Ch ; 'L'
0x180070a49  mov     r9d, eax
0x180070a4c  mov     r8, r12
0x180070a4f  call    WPP_SF_d
0x180070a54  lea     rcx, [rbp+57h+var_78]
0x180070a58  mov     [rbp+57h+var_78], 0
0x180070a60  call    ?CreateInstance@?$CComObject@VCUdpBroadcastMapper@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CUdpBroadcastMapper>::CreateInstance(ATL::CComObject<CUdpBroadcastMapper> * *)
0x180070a65  mov     ebx, eax
0x180070a67  test    eax, eax
0x180070a69  jns     short loc_180070AA8
0x180070a6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180070a72  cmp     rcx, r15
0x180070a75  jz      loc_180070B31
  ... truncated ...
```

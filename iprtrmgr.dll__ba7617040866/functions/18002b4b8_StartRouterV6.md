# StartRouterV6

- ea: `0x18002b4b8`
- end: `0x18002b9f6`
- name: `StartRouterV6`
- size: `1342`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002a4f0`

## callees

- `0x18000ac60`
- `0x18000c054`
- `0x18001f378`
- `0x1800208c4`
- `0x18002b4b8`
- `0x180057a64`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18002b72e`
- `KERNEL32!LeaveCriticalSection` at `0x18002b72e`
- `KERNEL32!EnterCriticalSection` at `0x18002b584`
- `KERNEL32!EnterCriticalSection` at `0x18002b584`
- `ADVAPI32!RegCloseKey` at `0x18002b721`
- `ADVAPI32!RegCloseKey` at `0x18002b721`
- `ADVAPI32!RegOpenKeyExW` at `0x18002b5bd`
- `ADVAPI32!RegOpenKeyExW` at `0x18002b5bd`
- `ADVAPI32!RegQueryValueExW` at `0x18002b5fd`
- `ADVAPI32!RegQueryValueExW` at `0x18002b63f`
- `ADVAPI32!RegQueryValueExW` at `0x18002b5fd`
- `ADVAPI32!RegQueryValueExW` at `0x18002b63f`
- `ADVAPI32!RegSetValueExW` at `0x18002b671`
- `ADVAPI32!RegSetValueExW` at `0x18002b671`

## string_xrefs

- `0x18002b5e2`: `AllowNetworkAccess`
- `0x18002b5af`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ipv6`

## pseudocode

```c
__int64 __fastcall StartRouterV6(__int64 a1, __int64 a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  __int64 result; // rax
  unsigned int v7; // eax
  unsigned int inited; // eax
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  struct _GUID v12; // [rsp+40h] [rbp-C0h] BYREF
  int v13; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v14[2044]; // [rsp+54h] [rbp-ACh] BYREF

  v13 = 0;
  v12 = GUID_NULL;
  memset_0(v14, 0, sizeof(v14));
  v4 = AddRoutingDomainToStore(&v12, (unsigned __int16 *)&qword_1800717C0, 1u, 0x57u);
  v5 = v4;
  if ( v4 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v13) = 0;
      FormatRRASErrorString(&v13, L"StartRouterV6: AddRoutingDomainToStore failed with error %d ", v4);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v13);
    }
    return v5;
  }
  EnterCriticalSection(&g_csFwdState);
  if ( !RouterRoleLanOnly )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ipv6",
            0,
            0x2001Fu,
            &hKey) )
    {
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"AllowNetworkAccess", 0, 0, Data, &cbData) && !*(_DWORD *)Data )
        g_bEnableFwdRequestV6 = 0;
      cbData = 4;
      if ( RegQueryValueExW(hKey, L"EnableNetbtBcastFwd", 0, 0, Data, &cbData) )
      {
        *(_DWORD *)Data = 1;
        v7 = RegSetValueExW(hKey, L"EnableNetbtBcastFwd", 0, 4u, Data, 4u);
        if ( v7 )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            LOWORD(v13) = 0;
            FormatRRASErrorString(&v13, L"error %d setting EnableNetbtBcastFwd value", v7);
            if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v13);
          }
        }
      }
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v13) = 0;
        FormatRRASErrorString(&v13, L"Netbt Enable mode is %d", *(unsigned int *)Data);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v13);
      }
      if ( *(_DWORD *)Data )
        g_bEnableNetbtBcastFrowarding = 1;
      EnableNetbtBcastForwarding(*(int *)Data);
      RegCloseKey(hKey);
    }
  }
  LeaveCriticalSection(&g_csFwdState);
  qword_18008CB28 = 0;
  qword_18008CB30 = (__int64)SetRouteInfo;
  qword_18008CB38 = 0;
  g_rgicInfoCbv6 = (__int64)"Route";
  qword_18008CB58 = (__int64)SetFilterInterfaceInfo;
  qword_18008CB60 = (__int64)BindFilterInterface;
  qword_18008CB48 = (__int64)"Filter";
  qword_18008CB80 = (__int64)SetDemandDialFilters;
  qword_18008CB70 = (__int64)"DemandFilter";
  qword_18008CB40 = 0;
  qword_18008CB50 = 0;
  qword_18008CB68 = 0;
  qword_18008CB78 = 0;
  qword_18008CB88 = 0;
  qword_18008CB90 = 0;
  inited = InitRouterV6(a2);
  v5 = inited;
  if ( inited )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v13) = 0;
      FormatRRASErrorString(&v13, L"StartRouter: InitRouterv6 failed %d", inited);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v13);
    }
    RouterManagerCleanup(87);
    LODWORD(RouterState) = 2;
    return v5;
  }
  g_bUninitServerv6 = 1;
  *(_QWORD *)(a1 + 8) = StopRouterV6;
  *(_DWORD *)a1 = 87;
  *(_QWORD *)(a1 + 32) = AddInterfaceV6;
  *(_QWORD *)(a1 + 128) = RtrMgrMIBEntryCreateV6;
  *(_QWORD *)(a1 + 40) = DeleteInterfaceV6;
  *(_QWORD *)(a1 + 136) = RtrMgrMIBEntryDeleteV6;
  *(_QWORD *)(a1 + 48) = RtrMgrGetInterfaceInfoV6;
  *(_QWORD *)(a1 + 152) = &RtrMgrMIBEntryGetV6;
  *(_QWORD *)(a1 + 56) = RtrMgrSetInterfaceInfoV6;
  *(_QWORD *)(a1 + 160) = &RtrMgrMIBEntryGetFirstV6;
  *(_QWORD *)(a1 + 80) = InterfaceNotReachableV6;
  *(_QWORD *)(a1 + 168) = &RtrMgrMIBEntryGetNextV6;
  *(_QWORD *)(a1 + 88) = InterfaceReachableV4;
  *(_QWORD *)(a1 + 24) = InterfaceConnectedV6;
  *(_QWORD *)(a1 + 96) = UpdateRoutesV6;
  *(_QWORD *)(a1 + 104) = GetUpdateRoutesResultV6;
  *(_QWORD *)(a1 + 112) = SetGlobalInfoV6;
  *(_QWORD *)(a1 + 120) = GetGlobalInfoV6;
  *(_QWORD *)(a1 + 192) = SetRasAdvEnableV6;
  *(_QWORD *)(a1 + 16) = RouterBootCompleteV6;
  *(_QWORD *)(a1 + 280) = ProtocolActionV6;
  *(_QWORD *)(a1 + 288) = GetProtocolStatisticsV6;
  *(_QWORD *)(a1 + 296) = RouterBufferFree;
  *(_QWORD *)(a1 + 320) = AddRoutingDomainV6;
  *(_QWORD *)(a1 + 328) = RemoveRoutingDomainV6;
  *(_QWORD *)(a1 + 304) = SetRoutingDomainGlobalInfoV6;
  *(_QWORD *)(a1 + 312) = GetRoutingDomainGlobalInfoV6;
  result = 0;
  *(_QWORD *)(a1 + 144) = RtrMgrMIBEntrySetV6;
  qword_18008C118 = (__int64)&RtrMgrMIBEntryGetV6;
  qword_18008C128 = (__int64)&RtrMgrMIBEntryGetNextV6;
  qword_18008C120 = (__int64)&RtrMgrMIBEntryGetFirstV6;
  qword_18008C110 = (__int64)RtrMgrMIBEntrySetV6;
  qword_18008C100 = (__int64)RtrMgrMIBEntryCreateV6;
  qword_18008C108 = (__int64)RtrMgrMIBEntryDeleteV6;
  g_bRouterBootCompleteV6 = 0;
  return result;
}

```

## disassembly

```asm
0x18002b4b8  mov     [rsp-8+arg_10], rbx
0x18002b4bd  mov     [rsp-8+arg_18], rsi
0x18002b4c2  push    rbp
0x18002b4c3  push    rdi
0x18002b4c4  push    r14
0x18002b4c6  lea     rbp, [rsp-760h]
0x18002b4ce  sub     rsp, 860h
0x18002b4d5  mov     rax, cs:__security_cookie
0x18002b4dc  xor     rax, rsp
0x18002b4df  mov     [rbp+770h+var_20], rax
0x18002b4e6  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002b4ed  mov     rsi, rdx
0x18002b4f0  mov     rdi, rcx
0x18002b4f3  xor     r14d, r14d
0x18002b4f6  lea     rcx, [rsp+870h+var_81C]; void *
0x18002b4fb  xor     edx, edx; Val
0x18002b4fd  mov     [rsp+870h+var_820], r14d
0x18002b502  mov     r8d, 7FCh; Size
0x18002b508  movdqu  xmmword ptr [rsp+870h+var_830.Data1], xmm0
0x18002b50e  call    memset_0
0x18002b513  lea     r9d, [r14+57h]; unsigned int
0x18002b517  lea     r8d, [r14+1]; unsigned int
0x18002b51b  lea     rdx, qword_1800717C0; unsigned __int16 *
0x18002b522  lea     rcx, [rsp+870h+var_830]; struct _GUID *
0x18002b527  call    AddRoutingDomainToStore
0x18002b52c  mov     ebx, eax
0x18002b52e  test    eax, eax
0x18002b530  jz      short loc_18002B57D
0x18002b532  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002b539  jz      short loc_18002B576
0x18002b53b  mov     r8d, eax
0x18002b53e  mov     word ptr [rsp+870h+var_820], r14w
0x18002b544  lea     rdx, aStartrouterv6A; "StartRouterV6: AddRoutingDomainToStore "...
0x18002b54b  lea     rcx, [rsp+870h+var_820]
0x18002b550  call    FormatRRASErrorString
0x18002b555  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002b55c  jz      short loc_18002B576
0x18002b55e  lea     r8, [rsp+870h+var_820]
0x18002b563  lea     rdx, RasRtrMgrTraceError
0x18002b56a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002b571  call    McTemplateU0z_EventWriteTransfer
0x18002b576  mov     eax, ebx
0x18002b578  jmp     loc_18002B9CF
0x18002b57d  lea     rcx, g_csFwdState; lpCriticalSection
0x18002b584  call    cs:__imp_EnterCriticalSection
0x18002b58a  cmp     cs:RouterRoleLanOnly, r14d
0x18002b591  jnz     loc_18002B727
0x18002b597  lea     rax, [rsp+870h+hKey]
0x18002b59c  mov     [rsp+870h+hKey], r14
0x18002b5a1  mov     r9d, 2001Fh; samDesired
0x18002b5a7  mov     [rsp+870h+phkResult], rax; phkResult
0x18002b5ac  xor     r8d, r8d; ulOptions
0x18002b5af  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Re"...
0x18002b5b6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b5bd  call    cs:__imp_RegOpenKeyExW
0x18002b5c3  test    eax, eax
0x18002b5c5  jnz     loc_18002B727
0x18002b5cb  mov     rcx, [rsp+870h+hKey]; hKey
0x18002b5d0  lea     ebx, [rax+4]
0x18002b5d3  lea     rax, [rsp+870h+cbData]
0x18002b5d8  mov     dword ptr [rsp+870h+Data], r14d
0x18002b5dd  mov     [rsp+870h+lpcbData], rax; lpcbData
0x18002b5e2  lea     rdx, aAllownetworkac; "AllowNetworkAccess"
0x18002b5e9  lea     rax, [rsp+870h+Data]
0x18002b5ee  mov     [rsp+870h+cbData], ebx
0x18002b5f2  xor     r9d, r9d; lpType
0x18002b5f5  mov     [rsp+870h+phkResult], rax; lpData
0x18002b5fa  xor     r8d, r8d; lpReserved
0x18002b5fd  call    cs:__imp_RegQueryValueExW
0x18002b603  test    eax, eax
0x18002b605  jnz     short loc_18002B615
0x18002b607  cmp     dword ptr [rsp+870h+Data], r14d
0x18002b60c  jnz     short loc_18002B615
0x18002b60e  mov     cs:g_bEnableFwdRequestV6, r14d
0x18002b615  mov     rcx, [rsp+870h+hKey]; hKey
0x18002b61a  lea     rax, [rsp+870h+cbData]
0x18002b61f  mov     [rsp+870h+lpcbData], rax; lpcbData
0x18002b624  lea     rdx, aEnablenetbtbca_2; "EnableNetbtBcastFwd"
0x18002b62b  lea     rax, [rsp+870h+Data]
0x18002b630  mov     [rsp+870h+cbData], ebx
0x18002b634  xor     r9d, r9d; lpType
0x18002b637  mov     [rsp+870h+phkResult], rax; lpData
0x18002b63c  xor     r8d, r8d; lpReserved
0x18002b63f  call    cs:__imp_RegQueryValueExW
0x18002b645  test    eax, eax
0x18002b647  jz      short loc_18002B6BF
0x18002b649  mov     rcx, [rsp+870h+hKey]; hKey
0x18002b64e  lea     rax, [rsp+870h+Data]
0x18002b653  mov     dword ptr [rsp+870h+lpcbData], ebx; cbData
0x18002b657  lea     rdx, aEnablenetbtbca_2; "EnableNetbtBcastFwd"
0x18002b65e  mov     r9d, ebx; dwType
0x18002b661  mov     [rsp+870h+phkResult], rax; lpData
0x18002b666  xor     r8d, r8d; Reserved
0x18002b669  mov     dword ptr [rsp+870h+Data], 1
0x18002b671  call    cs:__imp_RegSetValueExW
0x18002b677  test    eax, eax
0x18002b679  jz      short loc_18002B6BF
0x18002b67b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002b682  jz      short loc_18002B6BF
0x18002b684  mov     r8d, eax
0x18002b687  mov     word ptr [rsp+870h+var_820], r14w
0x18002b68d  lea     rdx, aErrorDSettingE; "error %d setting EnableNetbtBcastFwd va"...
0x18002b694  lea     rcx, [rsp+870h+var_820]
0x18002b699  call    FormatRRASErrorString
0x18002b69e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002b6a5  jz      short loc_18002B6BF
0x18002b6a7  lea     r8, [rsp+870h+var_820]
0x18002b6ac  lea     rdx, RasRtrMgrTraceError
0x18002b6b3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002b6ba  call    McTemplateU0z_EventWriteTransfer
0x18002b6bf  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18002b6c6  jge     short loc_18002B705
0x18002b6c8  mov     r8d, dword ptr [rsp+870h+Data]
0x18002b6cd  lea     rdx, aNetbtEnableMod; "Netbt Enable mode is %d"
0x18002b6d4  lea     rcx, [rsp+870h+var_820]
0x18002b6d9  mov     word ptr [rsp+870h+var_820], r14w
0x18002b6df  call    FormatRRASErrorString
0x18002b6e4  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18002b6eb  jge     short loc_18002B705
0x18002b6ed  lea     r8, [rsp+870h+var_820]
0x18002b6f2  lea     rdx, RasRtrmgrTraceInfo
0x18002b6f9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002b700  call    McTemplateU0z_EventWriteTransfer
0x18002b705  mov     ecx, dword ptr [rsp+870h+Data]
0x18002b709  test    ecx, ecx
0x18002b70b  jz      short loc_18002B717
0x18002b70d  mov     cs:g_bEnableNetbtBcastFrowarding, 1
0x18002b717  call    EnableNetbtBcastForwarding
0x18002b71c  mov     rcx, [rsp+870h+hKey]; hKey
0x18002b721  call    cs:__imp_RegCloseKey
0x18002b727  lea     rcx, g_csFwdState; lpCriticalSection
0x18002b72e  call    cs:__imp_LeaveCriticalSection
0x18002b734  lea     rax, SetRouteInfo
0x18002b73b  mov     cs:qword_18008CB28, r14
0x18002b742  mov     cs:qword_18008CB30, rax
0x18002b749  mov     rcx, rsi
0x18002b74c  lea     rax, aRoute; "Route"
0x18002b753  mov     cs:qword_18008CB38, r14
0x18002b75a  mov     cs:g_rgicInfoCbv6, rax
0x18002b761  lea     rax, SetFilterInterfaceInfo
0x18002b768  mov     cs:qword_18008CB58, rax
0x18002b76f  lea     rax, BindFilterInterface
0x18002b776  mov     cs:qword_18008CB60, rax
0x18002b77d  lea     rax, aFilter; "Filter"
0x18002b784  mov     cs:qword_18008CB48, rax
0x18002b78b  lea     rax, SetDemandDialFilters
0x18002b792  mov     cs:qword_18008CB80, rax
0x18002b799  lea     rax, aDemandfilter; "DemandFilter"
0x18002b7a0  mov     cs:qword_18008CB70, rax
0x18002b7a7  mov     cs:qword_18008CB40, r14
0x18002b7ae  mov     cs:qword_18008CB50, r14
0x18002b7b5  mov     cs:qword_18008CB68, r14
0x18002b7bc  mov     cs:qword_18008CB78, r14
0x18002b7c3  mov     cs:qword_18008CB88, r14
0x18002b7ca  mov     cs:qword_18008CB90, r14
0x18002b7d1  call    InitRouterV6
0x18002b7d6  mov     ebx, eax
0x18002b7d8  test    eax, eax
0x18002b7da  jz      short loc_18002B839
0x18002b7dc  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18002b7e3  jge     short loc_18002B820
0x18002b7e5  mov     r8d, eax
0x18002b7e8  mov     word ptr [rsp+870h+var_820], r14w
0x18002b7ee  lea     rdx, aStartrouterIni; "StartRouter: InitRouterv6 failed %d"
0x18002b7f5  lea     rcx, [rsp+870h+var_820]
0x18002b7fa  call    FormatRRASErrorString
0x18002b7ff  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18002b806  jge     short loc_18002B820
0x18002b808  lea     r8, [rsp+870h+var_820]
0x18002b80d  lea     rdx, RasRtrmgrTraceInfo
0x18002b814  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002b81b  call    McTemplateU0z_EventWriteTransfer
0x18002b820  mov     ecx, 57h ; 'W'
0x18002b825  call    RouterManagerCleanup
0x18002b82a  mov     dword ptr cs:RouterState, 2
0x18002b834  jmp     loc_18002B576
0x18002b839  mov     cs:g_bUninitServerv6, 1
0x18002b843  lea     rax, StopRouterV6
0x18002b84a  mov     [rdi+8], rax
0x18002b84e  lea     r11, RtrMgrMIBEntryCreateV6
0x18002b855  mov     dword ptr [rdi], 57h ; 'W'
0x18002b85b  lea     rax, AddInterfaceV6
0x18002b862  mov     [rdi+20h], rax
0x18002b866  lea     r10, RtrMgrMIBEntryDeleteV6
0x18002b86d  mov     [rdi+80h], r11
0x18002b874  lea     rax, DeleteInterfaceV6
0x18002b87b  mov     [rdi+28h], rax
0x18002b87f  lea     r9, RtrMgrMIBEntryGetV6
0x18002b886  mov     [rdi+88h], r10
0x18002b88d  lea     rax, RtrMgrGetInterfaceInfoV6
0x18002b894  mov     [rdi+30h], rax
0x18002b898  lea     r8, RtrMgrMIBEntryGetFirstV6
0x18002b89f  mov     [rdi+98h], r9
0x18002b8a6  lea     rax, RtrMgrSetInterfaceInfoV6
0x18002b8ad  mov     [rdi+38h], rax
0x18002b8b1  lea     rdx, RtrMgrMIBEntryGetNextV6
0x18002b8b8  mov     [rdi+0A0h], r8
0x18002b8bf  lea     rax, InterfaceNotReachableV6
0x18002b8c6  mov     [rdi+50h], rax
0x18002b8ca  lea     rcx, RtrMgrMIBEntrySetV6
0x18002b8d1  mov     [rdi+0A8h], rdx
0x18002b8d8  lea     rax, InterfaceReachableV4
0x18002b8df  mov     [rdi+58h], rax
0x18002b8e3  lea     rax, InterfaceConnectedV6
0x18002b8ea  mov     [rdi+18h], rax
0x18002b8ee  lea     rax, UpdateRoutesV6
0x18002b8f5  mov     [rdi+60h], rax
0x18002b8f9  lea     rax, GetUpdateRoutesResultV6
0x18002b900  mov     [rdi+68h], rax
0x18002b904  lea     rax, SetGlobalInfoV6
0x18002b90b  mov     [rdi+70h], rax
0x18002b90f  lea     rax, GetGlobalInfoV6
0x18002b916  mov     [rdi+78h], rax
0x18002b91a  lea     rax, SetRasAdvEnableV6
0x18002b921  mov     [rdi+0C0h], rax
0x18002b928  lea     rax, RouterBootCompleteV6
0x18002b92f  mov     [rdi+10h], rax
0x18002b933  lea     rax, ProtocolActionV6
0x18002b93a  mov     [rdi+118h], rax
0x18002b941  lea     rax, GetProtocolStatisticsV6
0x18002b948  mov     [rdi+120h], rax
0x18002b94f  lea     rax, RouterBufferFree
0x18002b956  mov     [rdi+128h], rax
0x18002b95d  lea     rax, AddRoutingDomainV6
0x18002b964  mov     [rdi+140h], rax
0x18002b96b  lea     rax, RemoveRoutingDomainV6
0x18002b972  mov     [rdi+148h], rax
0x18002b979  lea     rax, SetRoutingDomainGlobalInfoV6
0x18002b980  mov     [rdi+130h], rax
0x18002b987  lea     rax, GetRoutingDomainGlobalInfoV6
0x18002b98e  mov     [rdi+138h], rax
0x18002b995  xor     eax, eax
0x18002b997  mov     [rdi+90h], rcx
0x18002b99e  mov     cs:qword_18008C118, r9
0x18002b9a5  mov     cs:qword_18008C128, rdx
0x18002b9ac  mov     cs:qword_18008C120, r8
0x18002b9b3  mov     cs:qword_18008C110, rcx
0x18002b9ba  mov     cs:qword_18008C100, r11
0x18002b9c1  mov     cs:qword_18008C108, r10
0x18002b9c8  mov     cs:g_bRouterBootCompleteV6, r14d
0x18002b9cf  mov     rcx, [rbp+770h+var_20]
0x18002b9d6  xor     rcx, rsp; StackCookie
0x18002b9d9  call    __security_check_cookie
0x18002b9de  lea     r11, [rsp+870h+var_10]
0x18002b9e6  mov     rbx, [r11+30h]
0x18002b9ea  mov     rsi, [r11+38h]
0x18002b9ee  mov     rsp, r11
0x18002b9f1  pop     r14
0x18002b9f3  pop     rdi
0x18002b9f4  pop     rbp
0x18002b9f5  retn
```

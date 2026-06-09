# StartRouterV4

- ea: `0x18002aef4`
- end: `0x18002b4b0`
- name: `StartRouterV4`
- size: `1468`
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
- `0x180020238`
- `0x18002aef4`
- `0x180057a64`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18002b16a`
- `KERNEL32!LeaveCriticalSection` at `0x18002b16a`
- `KERNEL32!EnterCriticalSection` at `0x18002afc0`
- `KERNEL32!EnterCriticalSection` at `0x18002afc0`
- `ADVAPI32!RegCloseKey` at `0x18002b15d`
- `ADVAPI32!RegCloseKey` at `0x18002b15d`
- `ADVAPI32!RegOpenKeyExW` at `0x18002aff9`
- `ADVAPI32!RegOpenKeyExW` at `0x18002aff9`
- `ADVAPI32!RegQueryValueExW` at `0x18002b039`
- `ADVAPI32!RegQueryValueExW` at `0x18002b07b`
- `ADVAPI32!RegQueryValueExW` at `0x18002b039`
- `ADVAPI32!RegQueryValueExW` at `0x18002b07b`
- `ADVAPI32!RegSetValueExW` at `0x18002b0ad`
- `ADVAPI32!RegSetValueExW` at `0x18002b0ad`

## string_xrefs

- `0x18002afeb`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ip`
- `0x18002b01e`: `AllowNetworkAccess`

## pseudocode

```c
__int64 __fastcall StartRouterV4(__int64 a1, __int64 a2)
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
  v4 = AddRoutingDomainToStore(&v12, (unsigned __int16 *)&qword_1800717C0, 1u, 0x21u);
  v5 = v4;
  if ( v4 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v13) = 0;
      FormatRRASErrorString(&v13, L"StartRouterV4: AddRoutingDomainToStore failed with error %d ", v4);
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
            L"System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ip",
            0,
            0x2001Fu,
            &hKey) )
    {
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"AllowNetworkAccess", 0, 0, Data, &cbData) && !*(_DWORD *)Data )
        g_bEnableFwdRequestV4 = 0;
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
  qword_18008C9C8 = 0;
  qword_18008C9D0 = (__int64)SetRouteInfo;
  qword_18008C9D8 = 0;
  g_rgicInfoCbv4 = (__int64)"Route";
  qword_18008C9F8 = (__int64)SetFilterInterfaceInfo;
  qword_18008CA00 = (__int64)BindFilterInterface;
  qword_18008C9E8 = (__int64)"Filter";
  qword_18008CA20 = (__int64)SetDemandDialFilters;
  qword_18008CA10 = (__int64)"DemandFilter";
  qword_18008CA40 = (__int64)GetBoundaryInfo;
  qword_18008CA48 = (__int64)SetBoundaryInfo;
  qword_18008CA50 = (__int64)BindBoundaryInterface;
  qword_18008CA58 = (__int64)GetScopeInfo;
  qword_18008CA38 = (__int64)"MulticastBoundary";
  qword_18008CA68 = (__int64)GetMcastLimitInfo;
  qword_18008CA70 = (__int64)SetMcastLimitInfo;
  qword_18008CA60 = (__int64)"MulticastLimit";
  qword_18008C9E0 = 0;
  qword_18008C9F0 = 0;
  qword_18008CA08 = 0;
  qword_18008CA18 = 0;
  qword_18008CA28 = 0;
  qword_18008CA30 = 0;
  qword_18008CA78 = 0;
  qword_18008CA80 = 0;
  inited = InitRouterV4(a2);
  v5 = inited;
  if ( inited )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v13) = 0;
      FormatRRASErrorString(&v13, L"StartRouter: InitRouterv4 failed %d", inited);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v13);
    }
    RouterManagerCleanup(33);
    LODWORD(RouterState) = 2;
    return v5;
  }
  g_bUninitServerv4 = 1;
  *(_QWORD *)(a1 + 8) = StopRouterV4;
  *(_DWORD *)a1 = 33;
  *(_QWORD *)(a1 + 32) = AddInterfaceV4;
  *(_QWORD *)(a1 + 128) = RtrMgrMIBEntryCreateV4;
  *(_QWORD *)(a1 + 40) = DeleteInterfaceV4;
  *(_QWORD *)(a1 + 136) = RtrMgrMIBEntryDeleteV4;
  *(_QWORD *)(a1 + 48) = RtrMgrGetInterfaceInfoV6;
  *(_QWORD *)(a1 + 152) = &RtrMgrMIBEntryGetV4;
  *(_QWORD *)(a1 + 56) = RtrMgrSetInterfaceInfoV4;
  *(_QWORD *)(a1 + 160) = &RtrMgrMIBEntryGetFirstV4;
  *(_QWORD *)(a1 + 80) = InterfaceNotReachableV6;
  *(_QWORD *)(a1 + 168) = &RtrMgrMIBEntryGetNextV4;
  *(_QWORD *)(a1 + 88) = InterfaceReachableV4;
  *(_QWORD *)(a1 + 24) = InterfaceConnectedV4;
  *(_QWORD *)(a1 + 96) = UpdateRoutesV4;
  *(_QWORD *)(a1 + 104) = GetUpdateRoutesResultV6;
  *(_QWORD *)(a1 + 112) = SetGlobalInfoV4;
  *(_QWORD *)(a1 + 120) = GetGlobalInfoV4;
  *(_QWORD *)(a1 + 192) = SetRasAdvEnableV4;
  *(_QWORD *)(a1 + 16) = RouterBootCompleteV4;
  *(_QWORD *)(a1 + 280) = ProtocolActionV4;
  *(_QWORD *)(a1 + 288) = GetProtocolStatisticsV4;
  *(_QWORD *)(a1 + 296) = RouterBufferFree;
  *(_QWORD *)(a1 + 320) = AddRoutingDomainV4;
  *(_QWORD *)(a1 + 328) = RemoveRoutingDomainV4;
  *(_QWORD *)(a1 + 304) = SetRoutingDomainGlobalInfoV4;
  *(_QWORD *)(a1 + 312) = GetRoutingDomainGlobalInfoV4;
  result = 0;
  *(_QWORD *)(a1 + 144) = RtrMgrMIBEntrySetV4;
  qword_18008C118 = (__int64)&RtrMgrMIBEntryGetV4;
  qword_18008C128 = (__int64)&RtrMgrMIBEntryGetNextV4;
  qword_18008C120 = (__int64)&RtrMgrMIBEntryGetFirstV4;
  qword_18008C110 = (__int64)RtrMgrMIBEntrySetV4;
  qword_18008C100 = (__int64)RtrMgrMIBEntryCreateV4;
  qword_18008C108 = (__int64)RtrMgrMIBEntryDeleteV4;
  g_bRouterBootCompleteV4 = 0;
  return result;
}

```

## disassembly

```asm
0x18002aef4  mov     [rsp-8+arg_10], rbx
0x18002aef9  mov     [rsp-8+arg_18], rsi
0x18002aefe  push    rbp
0x18002aeff  push    rdi
0x18002af00  push    r14
0x18002af02  lea     rbp, [rsp-760h]
0x18002af0a  sub     rsp, 860h
0x18002af11  mov     rax, cs:__security_cookie
0x18002af18  xor     rax, rsp
0x18002af1b  mov     [rbp+770h+var_20], rax
0x18002af22  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002af29  mov     rsi, rdx
0x18002af2c  mov     rdi, rcx
0x18002af2f  xor     r14d, r14d
0x18002af32  lea     rcx, [rsp+870h+var_81C]; void *
0x18002af37  xor     edx, edx; Val
0x18002af39  mov     [rsp+870h+var_820], r14d
0x18002af3e  mov     r8d, 7FCh; Size
0x18002af44  movdqu  xmmword ptr [rsp+870h+var_830.Data1], xmm0
0x18002af4a  call    memset_0
0x18002af4f  lea     r9d, [r14+21h]; unsigned int
0x18002af53  lea     r8d, [r14+1]; unsigned int
0x18002af57  lea     rdx, qword_1800717C0; unsigned __int16 *
0x18002af5e  lea     rcx, [rsp+870h+var_830]; struct _GUID *
0x18002af63  call    AddRoutingDomainToStore
0x18002af68  mov     ebx, eax
0x18002af6a  test    eax, eax
0x18002af6c  jz      short loc_18002AFB9
0x18002af6e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002af75  jz      short loc_18002AFB2
0x18002af77  mov     r8d, eax
0x18002af7a  mov     word ptr [rsp+870h+var_820], r14w
0x18002af80  lea     rdx, aStartrouterv4A; "StartRouterV4: AddRoutingDomainToStore "...
0x18002af87  lea     rcx, [rsp+870h+var_820]
0x18002af8c  call    FormatRRASErrorString
0x18002af91  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002af98  jz      short loc_18002AFB2
0x18002af9a  lea     r8, [rsp+870h+var_820]
0x18002af9f  lea     rdx, RasRtrMgrTraceError
0x18002afa6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002afad  call    McTemplateU0z_EventWriteTransfer
0x18002afb2  mov     eax, ebx
0x18002afb4  jmp     loc_18002B489
0x18002afb9  lea     rcx, g_csFwdState; lpCriticalSection
0x18002afc0  call    cs:__imp_EnterCriticalSection
0x18002afc6  cmp     cs:RouterRoleLanOnly, r14d
0x18002afcd  jnz     loc_18002B163
0x18002afd3  lea     rax, [rsp+870h+hKey]
0x18002afd8  mov     [rsp+870h+hKey], r14
0x18002afdd  mov     r9d, 2001Fh; samDesired
0x18002afe3  mov     [rsp+870h+phkResult], rax; phkResult
0x18002afe8  xor     r8d, r8d; ulOptions
0x18002afeb  lea     rdx, aSystemCurrentc_7; "System\\CurrentControlSet\\Services\\Re"...
0x18002aff2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002aff9  call    cs:__imp_RegOpenKeyExW
0x18002afff  test    eax, eax
0x18002b001  jnz     loc_18002B163
0x18002b007  mov     rcx, [rsp+870h+hKey]; hKey
0x18002b00c  lea     ebx, [rax+4]
0x18002b00f  lea     rax, [rsp+870h+cbData]
0x18002b014  mov     dword ptr [rsp+870h+Data], r14d
0x18002b019  mov     [rsp+870h+lpcbData], rax; lpcbData
0x18002b01e  lea     rdx, aAllownetworkac; "AllowNetworkAccess"
0x18002b025  lea     rax, [rsp+870h+Data]
0x18002b02a  mov     [rsp+870h+cbData], ebx
0x18002b02e  xor     r9d, r9d; lpType
0x18002b031  mov     [rsp+870h+phkResult], rax; lpData
0x18002b036  xor     r8d, r8d; lpReserved
0x18002b039  call    cs:__imp_RegQueryValueExW
0x18002b03f  test    eax, eax
0x18002b041  jnz     short loc_18002B051
0x18002b043  cmp     dword ptr [rsp+870h+Data], r14d
0x18002b048  jnz     short loc_18002B051
0x18002b04a  mov     cs:g_bEnableFwdRequestV4, r14d
0x18002b051  mov     rcx, [rsp+870h+hKey]; hKey
0x18002b056  lea     rax, [rsp+870h+cbData]
0x18002b05b  mov     [rsp+870h+lpcbData], rax; lpcbData
0x18002b060  lea     rdx, aEnablenetbtbca_2; "EnableNetbtBcastFwd"
0x18002b067  lea     rax, [rsp+870h+Data]
0x18002b06c  mov     [rsp+870h+cbData], ebx
0x18002b070  xor     r9d, r9d; lpType
0x18002b073  mov     [rsp+870h+phkResult], rax; lpData
0x18002b078  xor     r8d, r8d; lpReserved
0x18002b07b  call    cs:__imp_RegQueryValueExW
0x18002b081  test    eax, eax
0x18002b083  jz      short loc_18002B0FB
0x18002b085  mov     rcx, [rsp+870h+hKey]; hKey
0x18002b08a  lea     rax, [rsp+870h+Data]
0x18002b08f  mov     dword ptr [rsp+870h+lpcbData], ebx; cbData
0x18002b093  lea     rdx, aEnablenetbtbca_2; "EnableNetbtBcastFwd"
0x18002b09a  mov     r9d, ebx; dwType
0x18002b09d  mov     [rsp+870h+phkResult], rax; lpData
0x18002b0a2  xor     r8d, r8d; Reserved
0x18002b0a5  mov     dword ptr [rsp+870h+Data], 1
0x18002b0ad  call    cs:__imp_RegSetValueExW
0x18002b0b3  test    eax, eax
0x18002b0b5  jz      short loc_18002B0FB
0x18002b0b7  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002b0be  jz      short loc_18002B0FB
0x18002b0c0  mov     r8d, eax
0x18002b0c3  mov     word ptr [rsp+870h+var_820], r14w
0x18002b0c9  lea     rdx, aErrorDSettingE; "error %d setting EnableNetbtBcastFwd va"...
0x18002b0d0  lea     rcx, [rsp+870h+var_820]
0x18002b0d5  call    FormatRRASErrorString
0x18002b0da  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002b0e1  jz      short loc_18002B0FB
0x18002b0e3  lea     r8, [rsp+870h+var_820]
0x18002b0e8  lea     rdx, RasRtrMgrTraceError
0x18002b0ef  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002b0f6  call    McTemplateU0z_EventWriteTransfer
0x18002b0fb  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18002b102  jge     short loc_18002B141
0x18002b104  mov     r8d, dword ptr [rsp+870h+Data]
0x18002b109  lea     rdx, aNetbtEnableMod; "Netbt Enable mode is %d"
0x18002b110  lea     rcx, [rsp+870h+var_820]
0x18002b115  mov     word ptr [rsp+870h+var_820], r14w
0x18002b11b  call    FormatRRASErrorString
0x18002b120  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18002b127  jge     short loc_18002B141
0x18002b129  lea     r8, [rsp+870h+var_820]
0x18002b12e  lea     rdx, RasRtrmgrTraceInfo
0x18002b135  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002b13c  call    McTemplateU0z_EventWriteTransfer
0x18002b141  mov     ecx, dword ptr [rsp+870h+Data]
0x18002b145  test    ecx, ecx
0x18002b147  jz      short loc_18002B153
0x18002b149  mov     cs:g_bEnableNetbtBcastFrowarding, 1
0x18002b153  call    EnableNetbtBcastForwarding
0x18002b158  mov     rcx, [rsp+870h+hKey]; hKey
0x18002b15d  call    cs:__imp_RegCloseKey
0x18002b163  lea     rcx, g_csFwdState; lpCriticalSection
0x18002b16a  call    cs:__imp_LeaveCriticalSection
0x18002b170  lea     rax, SetRouteInfo
0x18002b177  mov     cs:qword_18008C9C8, r14
0x18002b17e  mov     cs:qword_18008C9D0, rax
0x18002b185  mov     rcx, rsi
0x18002b188  lea     rax, aRoute; "Route"
0x18002b18f  mov     cs:qword_18008C9D8, r14
0x18002b196  mov     cs:g_rgicInfoCbv4, rax
0x18002b19d  lea     rax, SetFilterInterfaceInfo
0x18002b1a4  mov     cs:qword_18008C9F8, rax
0x18002b1ab  lea     rax, BindFilterInterface
0x18002b1b2  mov     cs:qword_18008CA00, rax
0x18002b1b9  lea     rax, aFilter; "Filter"
0x18002b1c0  mov     cs:qword_18008C9E8, rax
0x18002b1c7  lea     rax, SetDemandDialFilters
0x18002b1ce  mov     cs:qword_18008CA20, rax
0x18002b1d5  lea     rax, aDemandfilter; "DemandFilter"
0x18002b1dc  mov     cs:qword_18008CA10, rax
0x18002b1e3  lea     rax, GetBoundaryInfo
0x18002b1ea  mov     cs:qword_18008CA40, rax
0x18002b1f1  lea     rax, SetBoundaryInfo
0x18002b1f8  mov     cs:qword_18008CA48, rax
0x18002b1ff  lea     rax, BindBoundaryInterface
0x18002b206  mov     cs:qword_18008CA50, rax
0x18002b20d  lea     rax, GetScopeInfo
0x18002b214  mov     cs:qword_18008CA58, rax
0x18002b21b  lea     rax, aMulticastbound; "MulticastBoundary"
0x18002b222  mov     cs:qword_18008CA38, rax
0x18002b229  lea     rax, GetMcastLimitInfo
0x18002b230  mov     cs:qword_18008CA68, rax
0x18002b237  lea     rax, SetMcastLimitInfo
0x18002b23e  mov     cs:qword_18008CA70, rax
0x18002b245  lea     rax, aMulticastlimit; "MulticastLimit"
0x18002b24c  mov     cs:qword_18008CA60, rax
0x18002b253  mov     cs:qword_18008C9E0, r14
0x18002b25a  mov     cs:qword_18008C9F0, r14
0x18002b261  mov     cs:qword_18008CA08, r14
0x18002b268  mov     cs:qword_18008CA18, r14
0x18002b26f  mov     cs:qword_18008CA28, r14
0x18002b276  mov     cs:qword_18008CA30, r14
0x18002b27d  mov     cs:qword_18008CA78, r14
0x18002b284  mov     cs:qword_18008CA80, r14
0x18002b28b  call    InitRouterV4
0x18002b290  mov     ebx, eax
0x18002b292  test    eax, eax
0x18002b294  jz      short loc_18002B2F3
0x18002b296  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18002b29d  jge     short loc_18002B2DA
0x18002b29f  mov     r8d, eax
0x18002b2a2  mov     word ptr [rsp+870h+var_820], r14w
0x18002b2a8  lea     rdx, aStartrouterIni_0; "StartRouter: InitRouterv4 failed %d"
0x18002b2af  lea     rcx, [rsp+870h+var_820]
0x18002b2b4  call    FormatRRASErrorString
0x18002b2b9  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18002b2c0  jge     short loc_18002B2DA
0x18002b2c2  lea     r8, [rsp+870h+var_820]
0x18002b2c7  lea     rdx, RasRtrmgrTraceInfo
0x18002b2ce  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002b2d5  call    McTemplateU0z_EventWriteTransfer
0x18002b2da  mov     ecx, 21h ; '!'
0x18002b2df  call    RouterManagerCleanup
0x18002b2e4  mov     dword ptr cs:RouterState, 2
0x18002b2ee  jmp     loc_18002AFB2
0x18002b2f3  mov     cs:g_bUninitServerv4, 1
0x18002b2fd  lea     rax, StopRouterV4
0x18002b304  mov     [rdi+8], rax
0x18002b308  lea     r11, RtrMgrMIBEntryCreateV4
0x18002b30f  mov     dword ptr [rdi], 21h ; '!'
0x18002b315  lea     rax, AddInterfaceV4
0x18002b31c  mov     [rdi+20h], rax
0x18002b320  lea     r10, RtrMgrMIBEntryDeleteV4
0x18002b327  mov     [rdi+80h], r11
0x18002b32e  lea     rax, DeleteInterfaceV4
0x18002b335  mov     [rdi+28h], rax
0x18002b339  lea     r9, RtrMgrMIBEntryGetV4
0x18002b340  mov     [rdi+88h], r10
0x18002b347  lea     rax, RtrMgrGetInterfaceInfoV6
0x18002b34e  mov     [rdi+30h], rax
0x18002b352  lea     r8, RtrMgrMIBEntryGetFirstV4
0x18002b359  mov     [rdi+98h], r9
0x18002b360  lea     rax, RtrMgrSetInterfaceInfoV4
0x18002b367  mov     [rdi+38h], rax
0x18002b36b  lea     rdx, RtrMgrMIBEntryGetNextV4
0x18002b372  mov     [rdi+0A0h], r8
0x18002b379  lea     rax, InterfaceNotReachableV6
0x18002b380  mov     [rdi+50h], rax
0x18002b384  lea     rcx, RtrMgrMIBEntrySetV4
0x18002b38b  mov     [rdi+0A8h], rdx
0x18002b392  lea     rax, InterfaceReachableV4
0x18002b399  mov     [rdi+58h], rax
0x18002b39d  lea     rax, InterfaceConnectedV4
0x18002b3a4  mov     [rdi+18h], rax
0x18002b3a8  lea     rax, UpdateRoutesV4
0x18002b3af  mov     [rdi+60h], rax
0x18002b3b3  lea     rax, GetUpdateRoutesResultV6
0x18002b3ba  mov     [rdi+68h], rax
0x18002b3be  lea     rax, SetGlobalInfoV4
0x18002b3c5  mov     [rdi+70h], rax
0x18002b3c9  lea     rax, GetGlobalInfoV4
0x18002b3d0  mov     [rdi+78h], rax
0x18002b3d4  lea     rax, SetRasAdvEnableV4
0x18002b3db  mov     [rdi+0C0h], rax
0x18002b3e2  lea     rax, RouterBootCompleteV4
0x18002b3e9  mov     [rdi+10h], rax
0x18002b3ed  lea     rax, ProtocolActionV4
0x18002b3f4  mov     [rdi+118h], rax
0x18002b3fb  lea     rax, GetProtocolStatisticsV4
0x18002b402  mov     [rdi+120h], rax
0x18002b409  lea     rax, RouterBufferFree
0x18002b410  mov     [rdi+128h], rax
0x18002b417  lea     rax, AddRoutingDomainV4
0x18002b41e  mov     [rdi+140h], rax
0x18002b425  lea     rax, RemoveRoutingDomainV4
0x18002b42c  mov     [rdi+148h], rax
0x18002b433  lea     rax, SetRoutingDomainGlobalInfoV4
0x18002b43a  mov     [rdi+130h], rax
0x18002b441  lea     rax, GetRoutingDomainGlobalInfoV4
0x18002b448  mov     [rdi+138h], rax
0x18002b44f  xor     eax, eax
0x18002b451  mov     [rdi+90h], rcx
0x18002b458  mov     cs:qword_18008C118, r9
0x18002b45f  mov     cs:qword_18008C128, rdx
0x18002b466  mov     cs:qword_18008C120, r8
0x18002b46d  mov     cs:qword_18008C110, rcx
0x18002b474  mov     cs:qword_18008C100, r11
0x18002b47b  mov     cs:qword_18008C108, r10
0x18002b482  mov     cs:g_bRouterBootCompleteV4, r14d
0x18002b489  mov     rcx, [rbp+770h+var_20]
0x18002b490  xor     rcx, rsp; StackCookie
0x18002b493  call    __security_check_cookie
0x18002b498  lea     r11, [rsp+870h+var_10]
0x18002b4a0  mov     rbx, [r11+30h]
0x18002b4a4  mov     rsi, [r11+38h]
0x18002b4a8  mov     rsp, r11
0x18002b4ab  pop     r14
0x18002b4ad  pop     rdi
0x18002b4ae  pop     rbp
0x18002b4af  retn
```

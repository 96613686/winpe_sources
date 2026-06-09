# HandleDhcpContextConnected

- ea: `0x1800227ac`
- end: `0x180022faa`
- name: `HandleDhcpContextConnected`
- size: `2046`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `41`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800159d0`

## callees

- `0x1800026fc`
- `0x1800032b8`
- `0x180003544`
- `0x180003910`
- `0x180003b10`
- `0x180004a30`
- `0x180004ae0`
- `0x180004ce8`
- `0x1800057f0`
- `0x1800079e4`
- `0x180008e6c`
- `0x1800094f0`
- `0x18000a100`
- `0x18000b650`
- `0x18000f98c`
- `0x180010a40`
- `0x1800127fc`
- `0x180014bd8`
- `0x18001500c`
- `0x180015604`
- `0x180015668`
- `0x18001a2e4`
- `0x18001bc5c`
- `0x18001bf5c`
- `0x18001cef0`
- `0x18001ebd4`
- `0x180020404`
- `0x180020c4c`
- `0x180021128`
- `0x1800227ac`
- `0x180035ef4`
- `0x180036b1c`
- `0x18003f140`
- `0x180043e68`
- `0x180044d00`
- `0x18004d1a0`
- `0x18004d1e0`
- `0x18004d4c0`
- `0x18004d958`
- `0x18004e118`
- `0x18004e288`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022924`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022924`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180022df0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180022df0`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180022b48`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180022e48`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180022e5a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180022b48`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180022e48`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180022e5a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180022a84`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180022b05`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180022a84`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180022b05`
- `IPHLPAPI!GetDnsSettings` at `0x180022854`
- `IPHLPAPI!GetDnsSettings` at `0x180022854`
- `IPHLPAPI!FreeDnsSettings` at `0x180022878`
- `IPHLPAPI!FreeDnsSettings` at `0x180022878`

## pseudocode

```c
__int64 __fastcall HandleDhcpContextConnected(__int64 a1, __int64 a2)
{
  unsigned int AdapterKey; // esi
  int v5; // ebx
  void *v6; // rbx
  HKEY *v7; // rbx
  const WCHAR *v8; // rcx
  unsigned int v9; // eax
  ULONGLONG *v10; // rbx
  bool v11; // zf
  __int64 v12; // rcx
  char IsInitState; // al
  int v14; // edx
  char v15; // r9
  int v16; // r10d
  int v17; // eax
  __int64 v18; // r8
  __int64 v19; // r9
  int *v20; // rcx
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  int v28; // [rsp+50h] [rbp-B0h] BYREF
  int v29; // [rsp+54h] [rbp-ACh] BYREF
  DWORD v30; // [rsp+58h] [rbp-A8h] BYREF
  int v31; // [rsp+5Ch] [rbp-A4h] BYREF
  int v32; // [rsp+60h] [rbp-A0h] BYREF
  int v33; // [rsp+64h] [rbp-9Ch] BYREF
  int v34; // [rsp+68h] [rbp-98h] BYREF
  int v35; // [rsp+6Ch] [rbp-94h] BYREF
  int v36; // [rsp+70h] [rbp-90h] BYREF
  int *v37; // [rsp+78h] [rbp-88h] BYREF
  LARGE_INTEGER v38; // [rsp+80h] [rbp-80h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+88h] [rbp-78h] BYREF
  __int64 v40; // [rsp+90h] [rbp-70h] BYREF
  __int64 v41; // [rsp+98h] [rbp-68h] BYREF
  __int64 v42; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE Settings[48]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v44[32]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v45; // [rsp+100h] [rbp+0h]
  __int64 v46; // [rsp+108h] [rbp+8h]
  int *v47; // [rsp+110h] [rbp+10h]
  __int64 v48; // [rsp+118h] [rbp+18h]
  int *v49; // [rsp+120h] [rbp+20h]
  __int64 v50; // [rsp+128h] [rbp+28h]
  int *v51; // [rsp+130h] [rbp+30h]
  __int64 v52; // [rsp+138h] [rbp+38h]
  __int64 v53; // [rsp+140h] [rbp+40h]
  __int64 v54; // [rsp+148h] [rbp+48h]
  UUID *v55; // [rsp+150h] [rbp+50h]
  __int64 v56; // [rsp+158h] [rbp+58h]
  int *v57; // [rsp+160h] [rbp+60h]
  __int64 v58; // [rsp+168h] [rbp+68h]
  int *v59; // [rsp+170h] [rbp+70h]
  __int64 v60; // [rsp+178h] [rbp+78h]
  int *v61; // [rsp+180h] [rbp+80h]
  __int64 v62; // [rsp+188h] [rbp+88h]
  int *v63; // [rsp+190h] [rbp+90h]
  __int64 v64; // [rsp+198h] [rbp+98h]
  __int64 *v65; // [rsp+1A0h] [rbp+A0h]
  __int64 v66; // [rsp+1A8h] [rbp+A8h]
  int *v67; // [rsp+1B0h] [rbp+B0h]
  int v68; // [rsp+1B8h] [rbp+B8h]
  int v69; // [rsp+1BCh] [rbp+BCh]
  __int64 *v70; // [rsp+1C0h] [rbp+C0h]
  __int64 v71; // [rsp+1C8h] [rbp+C8h]

  AdapterKey = 0;
  PerformanceCount.QuadPart = 0;
  v38.QuadPart = 0;
  v42 = 0;
  v30 = 0;
  v28 = 0;
  v37 = 0;
  v29 = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_q(1028, 193, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, *(_QWORD *)(a1 + 24));
  if ( g_fUseIpv6OnlyPreferred )
    DhcpRefreshGlobalIpv6OnlyPreferredEnabled();
  memset(Settings, 0, sizeof(Settings));
  *(_DWORD *)Settings = 2;
  if ( GetDnsSettings((DNS_SETTINGS *)Settings) || (v5 = 1, (*(_WORD *)&Settings[40] & 0x400) == 0) )
    v5 = 0;
  FreeDnsSettings((DNS_SETTINGS *)Settings);
  dword_180061888 = v5;
  if ( g_fVelocityDhcpCaptivePortalSupport )
    *(_DWORD *)(a1 + 2172) = DhcpRefreshCaptivePortalEnabled();
  v6 = *(void **)(a1 + 56);
  DhcpDeleteRegistryOption(v6, 44, 0);
  DhcpDeleteRegistryOption(v6, 45, 0);
  DhcpDeleteRegistryOption(v6, 1, 1);
  DhcpDeleteRegistryOption(v6, 6, 0);
  ClearOptionsAndClasses(a1);
  DhcpStandbyResetStatus(a1 + 2016);
  v7 = (HKEY *)(a1 + 728);
  if ( (unsigned int)IsRegKeyValid(*(_QWORD *)(a1 + 728)) )
    goto LABEL_14;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_q(1028, 194, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, *(_QWORD *)(a1 + 24));
  RegCloseKey(*v7);
  v8 = *(const WCHAR **)(a1 + 56);
  *v7 = 0;
  AdapterKey = DhcpCreateAdapterKey(v8, (HKEY *)(a1 + 728));
  if ( !AdapterKey )
  {
LABEL_14:
    v9 = DhcpSetContextForcedBroadcastFlag(a1);
    if ( v9 && (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_D(1025, 195, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v9);
    *(_QWORD *)(a1 + 552) = 0;
    *(_QWORD *)(a1 + 1968) = 0;
    *(_QWORD *)(a1 + 584) = 0;
    *(_QWORD *)(a1 + 652) = 0;
    *(_DWORD *)(a1 + 648) = 0;
    *(_DWORD *)(a1 + 660) = 0;
    *(_DWORD *)(a1 + 1980) = 0;
    *(_DWORD *)(a1 + 560) = 0;
    *(_DWORD *)(a1 + 1992) = 0;
    if ( (unsigned int)DhcpIsFSEGuestSystem() )
    {
      if ( (xmmword_1800616A0 & 0x10) != 0 )
        WPP_SF_(1028, 196, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids);
      RefillDhcpContext(a1);
    }
    else
    {
      DhcpRegFillParams(a1, 1, &v28);
      DhcpRegFillFallbackConfig(a1);
      DhcpRegReadClassId(a1);
      DhcpRegFillSendOptions(a1 + 680, *(_QWORD *)(a1 + 56), *(_QWORD *)(a1 + 736), *(unsigned int *)(a1 + 744));
      if ( *(_DWORD *)(a1 + 792) )
      {
        DhcpRegReadOptionCache(a1 + 696, *v7, L"DhcpInterfaceOptions");
      }
      else if ( *(_BYTE *)(a1 + 84) != 8 )
      {
        DhcpRegSaveOptions(
          (_QWORD *)(a1 + 696),
          *(void **)(a1 + 56),
          *v7,
          *(_QWORD *)(a1 + 736),
          *(_DWORD *)(a1 + 744),
          0);
      }
    }
    v10 = (ULONGLONG *)(a1 + 1960);
    if ( g_fVelocityDhcpInitRebootRegressionFix )
      *v10 = GetTickCount64() / 0x3E8;
    if ( (unsigned int)IsAddressPlumbedOnInterface(*(unsigned int *)(a1 + 120), a2) )
    {
      *(_DWORD *)(a1 + 776) = 1;
    }
    else
    {
      v11 = g_fVelocityDhcpInitRebootRegressionFix == 0;
      *(_DWORD *)(a1 + 776) = 0;
      if ( v11
        || (v10 = (ULONGLONG *)(a1 + 1960), *(_QWORD *)(a1 + 1960) >= *(_QWORD *)(a1 + 472))
        || !(unsigned int)DhcpIsInitRebootState(a1) )
      {
        *(_DWORD *)(a1 + 132) = 0;
        *(_DWORD *)(a1 + 120) = 0;
      }
    }
    if ( !g_fVelocityDhcpInitRebootRegressionFix )
      *v10 = GetTickCount64() / 0x3E8;
    GetNetworkHint(*(_QWORD *)(a1 + 24), &v37, &v29, 0);
    QueryPerformanceCounter((LARGE_INTEGER *)(a1 + 1936));
    if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
      McTemplateU0z_EtwEventWriteTransfer(v12, StackMediaConnect, *(_QWORD *)(a1 + 56));
    TraceLogErrorv4(a1, 0, 74);
    if ( (xmmword_1800616A0 & 0x10) != 0 )
    {
      IsInitState = DhcpIsInitState((_DWORD *)a1);
      WPP_SF_S_guid_Llll(a1 + 32, v14, v14 == 0, v16, a1 + 32, v15, v14 == 0, v28, IsInitState);
    }
    if ( (unsigned int)dword_1800610D8 > 5 && tlgKeywordOn((__int64)&dword_1800610D8, 0x400000000000LL) )
    {
      v46 = 16;
      v45 = a1 + 32;
      v29 = *(_DWORD *)(a1 + 48);
      v47 = &v29;
      v31 = *(_DWORD *)(a1 + 112);
      v49 = &v31;
      v32 = *(_DWORD *)(a1 + 116);
      v51 = &v32;
      v53 = a1 + 2112;
      v55 = &DhcpGlobalBootGuid;
      v33 = *(_DWORD *)(a1 + 792);
      v57 = &v33;
      v34 = v28;
      v59 = &v34;
      v48 = 4;
      v50 = 4;
      v52 = 4;
      v54 = 16;
      v56 = 16;
      v58 = 4;
      v60 = 4;
      v17 = DhcpIsInitState((_DWORD *)a1);
      v20 = v37;
      v35 = v17;
      v61 = &v35;
      v36 = *(_DWORD *)&DhcpGlobalUseNetworkHint;
      v63 = &v36;
      v40 = *(_QWORD *)(a1 + 104);
      v65 = &v40;
      v62 = 4;
      v64 = 4;
      v66 = 8;
      if ( v37 )
      {
        v21 = -1;
        do
          ++v21;
        while ( *((_WORD *)v37 + v21) );
        v22 = 2 * v21 + 2;
      }
      else
      {
        v20 = &dword_180053FEC;
        v22 = 2;
      }
      v68 = v22;
      v67 = v20;
      v70 = &v41;
      v69 = 0;
      v41 = 0x1000000;
      v71 = 8;
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)v20,
        (unsigned __int8 *)byte_180059445,
        v18,
        v19,
        15,
        (__int64)v44);
    }
    SetEventNotification(1, *(_QWORD *)(a1 + 56));
    if ( (byte_1800619C9 & 1) != 0 )
    {
      McTemplateU0jq_EtwEventWriteTransfer(v23, PerftrackDHCPMediaConnectEnd, a1 + 32, *(unsigned int *)(a1 + 48));
      if ( (byte_1800619C9 & 1) != 0 )
        McTemplateU0jq_EtwEventWriteTransfer(v24, PerftrackDHCPMediaConnect, a1 + 32, *(unsigned int *)(a1 + 48));
    }
    if ( v28 && *(_DWORD *)(a1 + 792) )
    {
      AdapterKey = DisableDhcp(a1);
      if ( AdapterKey )
        goto LABEL_68;
      AdapterKey = RegDeleteValueW(*(HKEY *)(a1 + 728), L"DisableDhcpOnConnect");
      if ( AdapterKey )
        goto LABEL_68;
      *(_DWORD *)(a1 + 856) = 2;
    }
    else if ( *(_DWORD *)(a1 + 792) )
    {
      if ( *(_DWORD *)&DhcpGlobalUseNetworkHint )
      {
        if ( *(_DWORD *)(a1 + 792) )
        {
          QueryPerformanceCounter(&PerformanceCount);
          DhcpGetCachedNetwork(a1);
          QueryPerformanceCounter(&v38);
          if ( (xmmword_1800616A0 & 0x10) != 0 )
            WPP_SF_II(
              (unsigned __int64)(1000000000 * (v38.QuadPart - PerformanceCount.QuadPart))
            / DhcpGlobalPerformanceFrequency.QuadPart,
              198,
              WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids,
              (unsigned __int64)(1000000000 * (v38.QuadPart - PerformanceCount.QuadPart))
            / DhcpGlobalPerformanceFrequency.QuadPart
            / 0xF4240,
              (unsigned __int64)(1000000000 * (v38.QuadPart - PerformanceCount.QuadPart))
            / DhcpGlobalPerformanceFrequency.QuadPart);
        }
      }
      if ( (unsigned int)DhcpIsInitState((_DWORD *)a1) )
      {
        DhcpCleanupStack(a1);
        TrySetRenewalFunction(a1, ReObtainInitialParameters, 0);
        ResetCSStateVarsInContext(a1);
      }
      else
      {
        TrySetRenewalFunction(a1, ReRenewParameters, 0);
      }
    }
    else
    {
      *(_DWORD *)(a1 + 856) = (*(_BYTE *)(a1 + 84) != 8) + 1;
    }
    DhcpReadSavedConfigurations(*(HKEY *)(a1 + 728), &v42, &v30);
    *(_DWORD *)(a1 + 1932) = v30;
    if ( !*(_DWORD *)(a1 + 792) && (byte_1800619C9 & 1) != 0 )
    {
      McTemplateU0jq_EtwEventWriteTransfer(v25, SelfPerftrackDHCPStatic, a1 + 32, *(unsigned int *)(a1 + 48));
      if ( (byte_1800619C9 & 1) != 0 )
        McTemplateU0jq_EtwEventWriteTransfer(v26, PerftrackWlanDHCPStatic, a1 + 32, *(unsigned int *)(a1 + 48));
    }
  }
LABEL_68:
  DhcpPunycodeFree((LPVOID *)&v37);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_qD(1028, 199, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, *(_QWORD *)(a1 + 24), AdapterKey);
  return AdapterKey;
}

```

## disassembly

```asm
0x1800227ac  push    rbp
0x1800227ae  push    rbx
0x1800227af  push    rsi
0x1800227b0  push    rdi
0x1800227b1  push    r12
0x1800227b3  push    r13
0x1800227b5  push    r14
0x1800227b7  push    r15
0x1800227b9  lea     rbp, [rsp-0E8h]
0x1800227c1  sub     rsp, 1E8h
0x1800227c8  mov     rax, cs:__security_cookie
0x1800227cf  xor     rax, rsp
0x1800227d2  mov     [rbp+120h+var_50], rax
0x1800227d9  xor     r15d, r15d
0x1800227dc  mov     r14, rdx
0x1800227df  mov     esi, r15d
0x1800227e2  mov     qword ptr [rbp+120h+PerformanceCount], r15
0x1800227e6  mov     qword ptr [rbp+120h+var_1A0], r15
0x1800227ea  mov     rdi, rcx
0x1800227ed  mov     [rbp+120h+var_180], r15
0x1800227f1  mov     [rsp+220h+var_1C8], r15d
0x1800227f6  mov     [rsp+220h+var_1D0], r15d
0x1800227fb  mov     [rsp+220h+var_1A8], r15
0x180022800  mov     [rsp+220h+var_1CC], r15d
0x180022805  lea     r13d, [r15+10h]
0x180022809  test    byte ptr cs:xmmword_1800616A0, r13b
0x180022810  jz      short loc_18002282C
0x180022812  mov     r9, [rdi+18h]
0x180022816  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x18002281d  mov     edx, 0C1h
0x180022822  mov     ecx, 404h
0x180022827  call    WPP_SF_q
0x18002282c  cmp     cs:g_fUseIpv6OnlyPreferred, r15d
0x180022833  jz      short loc_18002283A
0x180022835  call    DhcpRefreshGlobalIpv6OnlyPreferredEnabled
0x18002283a  xorps   xmm0, xmm0
0x18002283d  lea     rcx, [rbp+120h+Settings]; Settings
0x180022841  movups  xmmword ptr [rbp+120h+Settings], xmm0
0x180022845  mov     dword ptr [rbp+120h+Settings], 2
0x18002284c  movups  xmmword ptr [rbp+120h+Settings+10h], xmm0
0x180022850  movups  xmmword ptr [rbp+120h+Settings+20h], xmm0
0x180022854  call    cs:__imp_GetDnsSettings
0x18002285a  mov     r12d, 1
0x180022860  test    eax, eax
0x180022862  jnz     short loc_180022871
0x180022864  test    qword ptr [rbp+120h+Settings+28h], 400h
0x18002286c  mov     ebx, r12d
0x18002286f  jnz     short loc_180022874
0x180022871  mov     ebx, r15d
0x180022874  lea     rcx, [rbp+120h+Settings]; Settings
0x180022878  call    cs:__imp_FreeDnsSettings
0x18002287e  cmp     cs:g_fVelocityDhcpCaptivePortalSupport, r15d
0x180022885  mov     cs:dword_180061888, ebx
0x18002288b  jz      short loc_180022898
0x18002288d  call    DhcpRefreshCaptivePortalEnabled
0x180022892  mov     [rdi+87Ch], eax
0x180022898  mov     rbx, [rdi+38h]
0x18002289c  xor     r8d, r8d
0x18002289f  mov     rcx, rbx; void *
0x1800228a2  lea     edx, [r8+2Ch]
0x1800228a6  call    DhcpDeleteRegistryOption
0x1800228ab  xor     r8d, r8d
0x1800228ae  mov     rcx, rbx; void *
0x1800228b1  lea     edx, [r8+2Dh]
0x1800228b5  call    DhcpDeleteRegistryOption
0x1800228ba  mov     r8d, r12d
0x1800228bd  mov     edx, r12d
0x1800228c0  mov     rcx, rbx; void *
0x1800228c3  call    DhcpDeleteRegistryOption
0x1800228c8  xor     r8d, r8d
0x1800228cb  mov     rcx, rbx; void *
0x1800228ce  lea     edx, [r8+6]
0x1800228d2  call    DhcpDeleteRegistryOption
0x1800228d7  mov     rcx, rdi
0x1800228da  call    ClearOptionsAndClasses
0x1800228df  lea     rcx, [rdi+7E0h]
0x1800228e6  call    DhcpStandbyResetStatus
0x1800228eb  lea     rbx, [rdi+2D8h]
0x1800228f2  mov     rcx, [rbx]
0x1800228f5  call    IsRegKeyValid
0x1800228fa  test    eax, eax
0x1800228fc  jnz     short loc_180022943
0x1800228fe  test    byte ptr cs:xmmword_1800616A0, r13b
0x180022905  jz      short loc_180022921
0x180022907  mov     r9, [rdi+18h]
0x18002290b  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x180022912  mov     edx, 0C2h
0x180022917  mov     ecx, 404h
0x18002291c  call    WPP_SF_q
0x180022921  mov     rcx, [rbx]; hKey
0x180022924  call    cs:__imp_RegCloseKey
0x18002292a  mov     rcx, [rdi+38h]; lpSubKey
0x18002292e  mov     rdx, rbx
0x180022931  mov     [rbx], r15
0x180022934  call    DhcpCreateAdapterKey
0x180022939  mov     esi, eax
0x18002293b  test    eax, eax
0x18002293d  jnz     loc_180022F54
0x180022943  mov     rcx, rdi
0x180022946  call    DhcpSetContextForcedBroadcastFlag
0x18002294b  test    eax, eax
0x18002294d  jz      short loc_180022971
0x18002294f  test    byte ptr cs:xmmword_1800616A0, 2
0x180022956  jz      short loc_180022971
0x180022958  mov     edx, 0C3h
0x18002295d  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x180022964  mov     ecx, 401h
0x180022969  mov     r9d, eax
0x18002296c  call    WPP_SF_D
0x180022971  mov     [rdi+228h], r15
0x180022978  mov     [rdi+7B0h], r15
0x18002297f  mov     [rdi+248h], r15
0x180022986  mov     [rdi+28Ch], r15
0x18002298d  mov     [rdi+288h], r15d
0x180022994  mov     [rdi+294h], r15d
0x18002299b  mov     [rdi+7BCh], r15d
0x1800229a2  mov     [rdi+230h], r15d
0x1800229a9  mov     [rdi+7C8h], r15d
0x1800229b0  call    DhcpIsFSEGuestSystem
0x1800229b5  test    eax, eax
0x1800229b7  jz      short loc_1800229E5
0x1800229b9  test    byte ptr cs:xmmword_1800616A0, r13b
0x1800229c0  jz      short loc_1800229D8
0x1800229c2  mov     edx, 0C4h
0x1800229c7  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x1800229ce  mov     ecx, 404h
0x1800229d3  call    WPP_SF_
0x1800229d8  mov     rcx, rdi
0x1800229db  call    RefillDhcpContext
0x1800229e0  jmp     loc_180022A74
0x1800229e5  lea     r8, [rsp+220h+var_1D0]
0x1800229ea  mov     edx, r12d
0x1800229ed  mov     rcx, rdi
0x1800229f0  call    DhcpRegFillParams
0x1800229f5  mov     rcx, rdi
0x1800229f8  call    DhcpRegFillFallbackConfig
0x1800229fd  mov     rcx, rdi
0x180022a00  call    DhcpRegReadClassId
0x180022a05  mov     r9d, [rdi+2E8h]
0x180022a0c  lea     rcx, [rdi+2A8h]
0x180022a13  mov     r8, [rdi+2E0h]
0x180022a1a  mov     rdx, [rdi+38h]
0x180022a1e  call    DhcpRegFillSendOptions
0x180022a23  mov     eax, [rdi+318h]
0x180022a29  test    eax, eax
0x180022a2b  jz      short loc_180022A45
0x180022a2d  mov     rdx, [rbx]
0x180022a30  lea     rcx, [rdi+2B8h]
0x180022a37  lea     r8, aDhcpinterfaceo; "DhcpInterfaceOptions"
0x180022a3e  call    DhcpRegReadOptionCache
0x180022a43  jmp     short loc_180022A74
0x180022a45  cmp     byte ptr [rdi+54h], 8
0x180022a49  jz      short loc_180022A74
0x180022a4b  mov     eax, [rdi+2E8h]
0x180022a51  lea     rcx, [rdi+2B8h]
0x180022a58  mov     r9, [rdi+2E0h]
0x180022a5f  mov     r8, [rbx]
0x180022a62  mov     rdx, [rdi+38h]
0x180022a66  mov     dword ptr [rsp+220h+var_1F8], r15d
0x180022a6b  mov     dword ptr [rsp+220h+var_200], eax
0x180022a6f  call    DhcpRegSaveOptions
0x180022a74  cmp     cs:g_fVelocityDhcpInitRebootRegressionFix, r15d
0x180022a7b  lea     rbx, [rdi+7A8h]
0x180022a82  jz      short loc_180022AAA
0x180022a84  call    cs:__imp_GetTickCount64
0x180022a8a  mov     rcx, rax
0x180022a8d  mov     rax, 624DD2F1A9FBE77h
0x180022a97  mul     rcx
0x180022a9a  sub     rcx, rdx
0x180022a9d  shr     rcx, 1
0x180022aa0  add     rcx, rdx
0x180022aa3  shr     rcx, 9
0x180022aa7  mov     [rbx], rcx
0x180022aaa  mov     ecx, [rdi+78h]
0x180022aad  mov     rdx, r14
0x180022ab0  call    IsAddressPlumbedOnInterface
0x180022ab5  test    eax, eax
0x180022ab7  jz      short loc_180022AC2
0x180022ab9  mov     [rdi+308h], r12d
0x180022ac0  jmp     short loc_180022AFC
0x180022ac2  cmp     cs:g_fVelocityDhcpInitRebootRegressionFix, r15d
0x180022ac9  mov     [rdi+308h], r15d
0x180022ad0  jz      short loc_180022AF1
0x180022ad2  mov     rax, [rdi+1D8h]
0x180022ad9  lea     rbx, [rdi+7A8h]
0x180022ae0  cmp     [rbx], rax
0x180022ae3  jnb     short loc_180022AF1
0x180022ae5  mov     rcx, rdi
0x180022ae8  call    DhcpIsInitRebootState
0x180022aed  test    eax, eax
0x180022aef  jnz     short loc_180022AFC
0x180022af1  mov     [rdi+84h], r15d
0x180022af8  mov     [rdi+78h], r15d
0x180022afc  cmp     cs:g_fVelocityDhcpInitRebootRegressionFix, r15d
0x180022b03  jnz     short loc_180022B2B
0x180022b05  call    cs:__imp_GetTickCount64
0x180022b0b  mov     rcx, rax
0x180022b0e  mov     rax, 624DD2F1A9FBE77h
0x180022b18  mul     rcx
0x180022b1b  sub     rcx, rdx
0x180022b1e  shr     rcx, 1
0x180022b21  add     rcx, rdx
0x180022b24  shr     rcx, 9
0x180022b28  mov     [rbx], rcx
0x180022b2b  mov     rcx, [rdi+18h]
0x180022b2f  lea     r8, [rsp+220h+var_1CC]
0x180022b34  xor     r9d, r9d
0x180022b37  lea     rdx, [rsp+220h+var_1A8]
0x180022b3c  call    GetNetworkHint
0x180022b41  lea     rcx, [rdi+790h]; lpPerformanceCount
0x180022b48  call    cs:__imp_QueryPerformanceCounter
0x180022b4e  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, r12b
0x180022b55  jz      short loc_180022B67
0x180022b57  mov     r8, [rdi+38h]
0x180022b5b  lea     rdx, StackMediaConnect
0x180022b62  call    McTemplateU0z_EtwEventWriteTransfer
0x180022b67  xor     edx, edx
0x180022b69  mov     rcx, rdi
0x180022b6c  lea     r8d, [rdx+4Ah]
0x180022b70  call    TraceLogErrorv4
0x180022b75  test    byte ptr cs:xmmword_1800616A0, r13b
0x180022b7c  jz      short loc_180022BC4
0x180022b7e  mov     edx, [rdi+318h]
0x180022b84  mov     rcx, rdi
0x180022b87  mov     r9d, [rdi+30h]
0x180022b8b  mov     r10, [rdi+38h]
0x180022b8f  call    DhcpIsInitState
0x180022b94  mov     [rsp+220h+var_1E0], eax
0x180022b98  lea     rcx, [rdi+20h]
0x180022b9c  mov     eax, [rsp+220h+var_1D0]
0x180022ba0  mov     r8d, r15d
0x180022ba3  mov     [rsp+220h+var_1E8], eax
0x180022ba7  test    edx, edx
0x180022ba9  setz    r8b
0x180022bad  mov     [rsp+220h+var_1F0], r8d
0x180022bb2  mov     dword ptr [rsp+220h+var_1F8], r9d
0x180022bb7  mov     r9, r10
0x180022bba  mov     [rsp+220h+var_200], rcx
0x180022bbf  call    WPP_SF_S_guid_Llll
0x180022bc4  mov     eax, cs:dword_1800610D8
0x180022bca  cmp     eax, 5
0x180022bcd  jbe     loc_180022D75
0x180022bd3  mov     rdx, 400000000000h
0x180022bdd  lea     rcx, dword_1800610D8
0x180022be4  call    _tlgKeywordOn
0x180022be9  test    al, al
0x180022beb  jz      loc_180022D75
0x180022bf1  lea     rax, [rdi+20h]
0x180022bf5  mov     [rbp+120h+var_118], r13
0x180022bf9  mov     [rbp+120h+var_120], rax
0x180022bfd  mov     rcx, rdi
0x180022c00  mov     eax, [rdi+30h]
0x180022c03  mov     [rsp+220h+var_1CC], eax
0x180022c07  lea     rax, [rsp+220h+var_1CC]
0x180022c0c  mov     [rbp+120h+var_110], rax
0x180022c10  mov     eax, [rdi+70h]
0x180022c13  mov     [rsp+220h+var_1C4], eax
0x180022c17  lea     rax, [rsp+220h+var_1C4]
0x180022c1c  mov     [rbp+120h+var_100], rax
0x180022c20  mov     eax, [rdi+74h]
0x180022c23  mov     [rsp+220h+var_1C0], eax
0x180022c27  lea     rax, [rsp+220h+var_1C0]
0x180022c2c  mov     [rbp+120h+var_F0], rax
0x180022c30  lea     rax, [rdi+840h]
0x180022c37  mov     [rbp+120h+var_E0], rax
0x180022c3b  lea     rax, DhcpGlobalBootGuid
0x180022c42  mov     [rbp+120h+var_D0], rax
0x180022c46  mov     eax, [rdi+318h]
0x180022c4c  mov     [rsp+220h+var_1BC], eax
0x180022c50  lea     rax, [rsp+220h+var_1BC]
0x180022c55  mov     [rbp+120h+var_C0], rax
0x180022c59  mov     eax, [rsp+220h+var_1D0]
0x180022c5d  mov     [rsp+220h+var_1B8], eax
0x180022c61  lea     rax, [rsp+220h+var_1B8]
0x180022c66  mov     [rbp+120h+var_B0], rax
0x180022c6a  mov     [rbp+120h+var_108], 4
0x180022c72  mov     [rbp+120h+var_F8], 4
0x180022c7a  mov     [rbp+120h+var_E8], 4
0x180022c82  mov     [rbp+120h+var_D8], r13
0x180022c86  mov     [rbp+120h+var_C8], r13
0x180022c8a  mov     [rbp+120h+var_B8], 4
0x180022c92  mov     [rbp+120h+var_A8], 4
0x180022c9a  call    DhcpIsInitState
0x180022c9f  mov     rcx, [rsp+220h+var_1A8]
0x180022ca4  mov     [rsp+220h+var_1B4], eax
0x180022ca8  lea     rax, [rsp+220h+var_1B4]
0x180022cad  mov     [rbp+120h+var_A0], rax
0x180022cb4  mov     eax, cs:DhcpGlobalUseNetworkHint
0x180022cba  mov     [rsp+220h+var_1B0], eax
0x180022cbe  lea     rax, [rsp+220h+var_1B0]
0x180022cc3  mov     [rbp+120h+var_90], rax
0x180022cca  mov     rax, [rdi+68h]
0x180022cce  mov     [rbp+120h+var_190], rax
0x180022cd2  lea     rax, [rbp+120h+var_190]
0x180022cd6  mov     [rbp+120h+var_80], rax
0x180022cdd  mov     [rbp+120h+var_98], 4
0x180022ce8  mov     [rbp+120h+var_88], 4
0x180022cf3  mov     [rbp+120h+var_78], 8
0x180022cfe  test    rcx, rcx
0x180022d01  jz      short loc_180022D1A
  ... truncated ...
```

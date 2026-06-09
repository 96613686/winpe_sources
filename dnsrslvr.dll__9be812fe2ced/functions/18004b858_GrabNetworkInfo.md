# GrabNetworkInfo

- ea: `0x18004b858`
- end: `0x18004bf4c`
- name: `GrabNetworkInfo`
- size: `1780`
- prototype: ``
- caller_count: `15`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180001880`
- `0x180001df0`
- `0x180005740`
- `0x18000ddc0`
- `0x180016778`
- `0x18001bf58`
- `0x180027c04`
- `0x18003508c`
- `0x18003dfd0`
- `0x18003e9b0`
- `0x18004c164`
- `0x18004c350`
- `0x18004c4ac`
- `0x18004cfa0`
- `0x18004e9b0`

## callees

- `0x180003c60`
- `0x180005bd0`
- `0x180005d50`
- `0x180025958`
- `0x18002b6d0`
- `0x18002b778`
- `0x18003508c`
- `0x180040cd4`
- `0x180045ac0`
- `0x180046ec0`
- `0x18004b808`
- `0x18004b858`
- `0x18004c2d4`
- `0x18007b150`
- `0x18007c8bc`
- `0x180086b1c`
- `0x180086b70`
- `0x180086f24`
- `0x180088578`

## import_xrefs

- `DNSAPI!NetInfo_CreatePerNetworkNetinfo` at `0x18004b9b8`
- `DNSAPI!NetInfo_CreatePerNetworkNetinfo` at `0x18004bb4f`
- `DNSAPI!NetInfo_CreatePerNetworkNetinfo` at `0x18004b9b8`
- `DNSAPI!NetInfo_CreatePerNetworkNetinfo` at `0x18004bb4f`
- `DNSAPI!DnsGlobals` at `0x18004bcd4`
- `DNSAPI!DnsTraceServerConfig` at `0x18004bc1d`
- `DNSAPI!DnsTraceServerConfig` at `0x18004bc1d`
- `DNSAPI!NetInfo_Free` at `0x18004be38`
- `DNSAPI!NetInfo_Free` at `0x18004be42`
- `DNSAPI!NetInfo_Free` at `0x18004be4c`
- `DNSAPI!NetInfo_Free` at `0x18004be38`
- `DNSAPI!NetInfo_Free` at `0x18004be42`
- `DNSAPI!NetInfo_Free` at `0x18004be4c`
- `DNSAPI!NetInfo_Copy` at `0x18004ba33`
- `DNSAPI!NetInfo_Copy` at `0x18004ba33`
- `DNSAPI!NetInfo_BuildEx` at `0x18004bad8`
- `DNSAPI!NetInfo_BuildEx` at `0x18004bad8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004bbb0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004bbb0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004bbc3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004bbc3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b951`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ba80`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004be1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004be2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b951`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ba80`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004be1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004be2e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b936`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b95e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b96e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004bc2a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b936`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b95e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b96e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004bc2a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004b8ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004b8ad`

## pseudocode

```c
__int64 __fastcall GrabNetworkInfo(int a1, __int64 *a2, __int64 *a3)
{
  unsigned int v3; // r12d
  unsigned int ConfigPrivate; // edi
  ULONGLONG TickCount64; // rax
  int v9; // r8d
  BOOL v10; // esi
  unsigned __int64 v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  unsigned int v15; // r15d
  unsigned int v16; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rdx
  unsigned int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r12
  __int64 i; // rbx
  int v25; // ebx
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  void *v30; // rax
  int v31; // r8d
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  _BOOL8 v35; // rcx
  __int64 v36; // r9
  __int64 v37; // r8
  int v39; // [rsp+30h] [rbp-69h]
  __int64 v40; // [rsp+38h] [rbp-61h]
  char v41; // [rsp+40h] [rbp-59h]
  unsigned int v42; // [rsp+44h] [rbp-55h]
  __int64 v43; // [rsp+48h] [rbp-51h]
  void *v44; // [rsp+50h] [rbp-49h]
  unsigned __int64 v45; // [rsp+58h] [rbp-41h]
  __int64 v46; // [rsp+60h] [rbp-39h] BYREF
  __int64 v47; // [rsp+68h] [rbp-31h] BYREF
  void *v48; // [rsp+70h] [rbp-29h] BYREF
  int v49; // [rsp+78h] [rbp-21h] BYREF
  int v50; // [rsp+7Ch] [rbp-1Dh] BYREF
  _OWORD v51[3]; // [rsp+80h] [rbp-19h] BYREF
  __int64 v52; // [rsp+B0h] [rbp+17h]

  v41 = a1;
  v40 = 0;
  v3 = a1 & 1;
  v46 = 0;
  v42 = v3;
  v43 = 0;
  v47 = 0;
  ConfigPrivate = 0;
  TickCount64 = GetTickCount64();
  v39 = 0;
  v49 = 0;
  memset(v51, 0, sizeof(v51));
  v10 = 0;
  v44 = 0;
  v48 = 0;
  v50 = 0;
  v11 = TickCount64 / 0x3E8;
  v45 = TickCount64 / 0x3E8;
  v52 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_Dqq(0, (TickCount64 * (unsigned __int128)0x624DD2F1A9FBE77uLL) >> 64, v9, a1, (__int64)a2, (__int64)a3);
  if ( a3 )
    *a3 = 0;
  if ( a2 )
    *a2 = 0;
  EnterCriticalSection(&g_csNetinfo);
  if ( (unsigned int)NetInfo_CheckCacheValidity(v3, (unsigned int)v11)
    || (LeaveCriticalSection(&g_csNetinfo),
        EnterCriticalSection(&g_csResolverNetInfo),
        v39 = 1,
        EnterCriticalSection(&g_csNetinfo),
        (unsigned int)NetInfo_CheckCacheValidity(v3, (unsigned int)v11)) )
  {
LABEL_13:
    v17 = g_pServerMapView;
    goto LABEL_14;
  }
  v15 = ++g_NetInfoTag;
  if ( v3 && (unsigned int)NetInfo_CheckCacheValidity(0, (unsigned int)v11) )
  {
    v16 = NetInfo_CreatePerNetworkNetinfo(g_NetworkInfo, &v46);
    ConfigPrivate = v16;
    if ( v16 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
        goto LABEL_80;
      WPP_SF_d(1035, 42, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, v16);
LABEL_75:
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      {
        if ( g_NetworkInfo )
          v31 = *(_DWORD *)(g_NetworkInfo + 56);
        else
          v31 = 0;
        WPP_SF_qD(1035, 50, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, g_NetworkInfo, v31);
      }
LABEL_80:
      LeaveCriticalSection(&g_csNetinfo);
      if ( !v39 )
        goto LABEL_82;
      goto LABEL_81;
    }
    *(_DWORD *)(v46 + 48) = v15;
    v12 = g_PerNetworkNetInfo;
    v43 = g_PerNetworkNetInfo;
    g_PerNetworkNetInfo = v46;
    v46 = 0;
    goto LABEL_13;
  }
  LeaveCriticalSection(&g_csNetinfo);
  if ( !g_fVelocityZtdnsProbing )
  {
    v21 = NetInfo_BuildEx(0, &v49, &v46);
    ConfigPrivate = v21;
    if ( v21 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
        goto LABEL_81;
      v22 = 44;
      goto LABEL_30;
    }
LABEL_32:
    v23 = 0;
    *(_DWORD *)(v46 + 48) = v15;
    v10 = (v41 & 2) == 0;
    for ( i = v46; (unsigned int)v23 < *(_DWORD *)(v46 + 68); v23 = (unsigned int)(v23 + 1) )
    {
      if ( (unsigned int)Hijack_IsHijack(*(unsigned int *)(160 * v23 + i + 152), 160 * v23 + i + 204) )
        *(_DWORD *)(160 * v23 + i + 172) |= 0x40000000u;
      i = v46;
    }
    v3 = v42;
    if ( v42 )
    {
      v21 = NetInfo_CreatePerNetworkNetinfo(i, &v47);
      ConfigPrivate = v21;
      if ( v21 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
          goto LABEL_81;
        v22 = 45;
        goto LABEL_30;
      }
      *(_DWORD *)(v47 + 48) = v15;
      i = v46;
    }
    v21 = CreateServerMapView(i, &v48);
    ConfigPrivate = v21;
    if ( v21 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
        goto LABEL_81;
      v22 = 46;
    }
    else
    {
      if ( !g_fZtdnsSelfhostBranch )
        goto LABEL_49;
      ConfigPrivate = ZtGetConfigPrivate(0, v51, &v50, 0);
      if ( ConfigPrivate )
        goto LABEL_81;
      AcquireSRWLockShared(&g_rwZtSettingsLock);
      v25 = g_fZtDriverRunning;
      ReleaseSRWLockShared(&g_rwZtSettingsLock);
      if ( !v25 || v50 == ConfigPrivate || (v21 = DnsZtAddNetinfoServers(v46), (ConfigPrivate = v21) == 0) )
      {
LABEL_49:
        DnsTraceServerConfig(v46, 1, 1);
        EnterCriticalSection(&g_csNetinfo);
        if ( v15 != g_NetInfoTag )
        {
          if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
            WPP_SF_dd(1035, 48, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, v15, g_NetInfoTag);
          if ( a3 )
          {
            v30 = v48;
            if ( !v48 )
            {
              MicrosoftTelemetryAssertTriggeredNoArgs(v27, v26, v28, v29);
              v30 = v48;
            }
            *a3 = (__int64)v30;
            v48 = 0;
          }
          if ( !a2 )
          {
            v40 = v46;
            v46 = 0;
            goto LABEL_75;
          }
          if ( v42 )
          {
            v40 = v46;
            v19 = v47;
            v47 = 0;
          }
          else
          {
            if ( v47 )
              MicrosoftTelemetryAssertTriggeredNoArgs(v27, v26, v28, v29);
            v19 = v46;
          }
          v46 = 0;
          goto LABEL_74;
        }
        g_ResetServerPriorityTime = DnsGlobals[88] + v45;
        g_EnableNdisIfNetInfoProcessing = v49 & 1;
        DnsPrint_NetworkInfo("Updating g_NetworkInfo: ", v46);
        DnsPrint_NetworkInfo("Updating g_PerNetworkInfo: ", v47);
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_q(1035, 49, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, v48);
        v17 = v48;
        v44 = g_pServerMapView;
        v40 = g_NetworkInfo;
        g_NetworkInfo = v46;
        g_pServerMapView = v48;
        v48 = 0;
        v46 = 0;
        if ( v42 )
        {
          v43 = g_PerNetworkNetInfo;
          g_PerNetworkNetInfo = v47;
          v47 = 0;
        }
        g_IsReachableServerUpdateRequired = 1;
LABEL_14:
        if ( a3 )
        {
          if ( !v17 || !v17[2] )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs(v17, v12, v13, v14);
            v17 = g_pServerMapView;
          }
          *a3 = (__int64)v17;
          AddRefServerMapView(v17, v12, v13, v14);
        }
        if ( !a2 )
          goto LABEL_75;
        v18 = g_PerNetworkNetInfo;
        if ( !v3 )
          v18 = g_NetworkInfo;
        v19 = NetInfo_Copy(v18);
        v46 = v19;
        if ( !v19 )
        {
          ConfigPrivate = 14;
          goto LABEL_75;
        }
        ConfigPrivate = 0;
        v46 = 0;
LABEL_74:
        *a2 = v19;
        goto LABEL_75;
      }
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
        goto LABEL_81;
      v22 = 47;
    }
    goto LABEL_30;
  }
  v21 = DnsApi_NetInfo_BuildEx2(0, v20, &v49, &v46);
  ConfigPrivate = v21;
  if ( !v21 )
    goto LABEL_32;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    v22 = 43;
LABEL_30:
    WPP_SF_d(1035, v22, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, v21);
  }
LABEL_81:
  LeaveCriticalSection(&g_csResolverNetInfo);
LABEL_82:
  NetInfo_Free(v40);
  NetInfo_Free(v43);
  NetInfo_Free(v47);
  DeRefServerMapView(v44);
  DeRefServerMapView(v48);
  if ( v10 )
    NS_Process();
  if ( a2 )
  {
    v35 = *a2 != 0;
    if ( (ConfigPrivate == 0) != v35 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v35, v32, v33, v34);
  }
  if ( a3 )
  {
    v36 = *a3;
    if ( *a3 )
    {
      v37 = *(_QWORD *)(v36 + 16);
      if ( v37 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_qqd(1035, 51, (unsigned int)WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, v36, v37);
      }
    }
  }
  if ( a2 && *a2 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      return ConfigPrivate;
    WPP_SF_qD(1035, 52, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, *a2, *(_DWORD *)(*a2 + 56));
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 53, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, ConfigPrivate);
  return ConfigPrivate;
}

```

## disassembly

```asm
0x18004b858  mov     [rsp-8+arg_18], rbx
0x18004b85d  push    rbp
0x18004b85e  push    rsi
0x18004b85f  push    rdi
0x18004b860  push    r12
0x18004b862  push    r13
0x18004b864  push    r14
0x18004b866  push    r15
0x18004b868  lea     rbp, [rsp-27h]
0x18004b86d  sub     rsp, 0C0h
0x18004b874  mov     rax, cs:__security_cookie
0x18004b87b  xor     rax, rsp
0x18004b87e  mov     [rbp+57h+var_38], rax
0x18004b882  xor     eax, eax
0x18004b884  mov     [rbp+57h+var_B0], ecx
0x18004b887  mov     r12d, ecx
0x18004b88a  mov     [rbp+57h+var_B8], rax
0x18004b88e  and     r12d, 1
0x18004b892  mov     [rbp+57h+var_90], rax
0x18004b896  mov     [rbp+57h+var_AC], r12d
0x18004b89a  mov     r13, r8
0x18004b89d  mov     r14, rdx
0x18004b8a0  mov     [rbp+57h+var_A8], rax
0x18004b8a4  mov     r15d, ecx
0x18004b8a7  mov     [rbp+57h+var_88], rax
0x18004b8ab  mov     edi, eax
0x18004b8ad  call    cs:__imp_GetTickCount64
0x18004b8b3  xor     ecx, ecx
0x18004b8b5  xorps   xmm0, xmm0
0x18004b8b8  mov     rbx, rax
0x18004b8bb  mov     [rbp+57h+var_C0], ecx
0x18004b8be  mov     rax, 624DD2F1A9FBE77h
0x18004b8c8  mov     [rbp+57h+var_78], ecx
0x18004b8cb  mul     rbx
0x18004b8ce  movups  [rbp+57h+var_70], xmm0
0x18004b8d2  movups  [rbp+57h+var_60], xmm0
0x18004b8d6  mov     esi, ecx
0x18004b8d8  mov     [rbp+57h+var_A0], rcx
0x18004b8dc  sub     rbx, rdx
0x18004b8df  mov     [rbp+57h+var_80], rcx
0x18004b8e3  shr     rbx, 1
0x18004b8e6  add     rbx, rdx
0x18004b8e9  mov     [rbp+57h+var_74], ecx
0x18004b8ec  shr     rbx, 9
0x18004b8f0  xor     eax, eax
0x18004b8f2  mov     [rbp+57h+var_98], rbx
0x18004b8f6  mov     [rbp+57h+var_40], rax
0x18004b8fa  movups  [rbp+57h+var_50], xmm0
0x18004b8fe  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004b905  jz      short loc_18004B91B
0x18004b907  mov     [rsp+0F0h+var_C8], r13
0x18004b90c  mov     r9d, r15d
0x18004b90f  mov     [rsp+0F0h+var_D0], r14
0x18004b914  call    WPP_SF_Dqq
0x18004b919  xor     ecx, ecx
0x18004b91b  test    r13, r13
0x18004b91e  jz      short loc_18004B924
0x18004b920  mov     [r13+0], rcx
0x18004b924  test    r14, r14
0x18004b927  jz      short loc_18004B92C
0x18004b929  mov     [r14], rcx
0x18004b92c  lea     r15, g_csNetinfo
0x18004b933  mov     rcx, r15; lpCriticalSection
0x18004b936  call    cs:__imp_EnterCriticalSection
0x18004b93c  mov     edx, ebx
0x18004b93e  mov     ecx, r12d
0x18004b941  call    NetInfo_CheckCacheValidity
0x18004b946  test    eax, eax
0x18004b948  jnz     loc_18004B9EA
0x18004b94e  mov     rcx, r15; lpCriticalSection
0x18004b951  call    cs:__imp_LeaveCriticalSection
0x18004b957  lea     rcx, g_csResolverNetInfo; lpCriticalSection
0x18004b95e  call    cs:__imp_EnterCriticalSection
0x18004b964  mov     rcx, r15; lpCriticalSection
0x18004b967  mov     [rbp+57h+var_C0], 1
0x18004b96e  call    cs:__imp_EnterCriticalSection
0x18004b974  mov     edx, ebx
0x18004b976  mov     ecx, r12d
0x18004b979  call    NetInfo_CheckCacheValidity
0x18004b97e  test    eax, eax
0x18004b980  jnz     short loc_18004B9EA
0x18004b982  mov     r15d, cs:g_NetInfoTag
0x18004b989  inc     r15d
0x18004b98c  mov     cs:g_NetInfoTag, r15d
0x18004b993  test    r12d, r12d
0x18004b996  jz      loc_18004BA79
0x18004b99c  mov     edx, ebx
0x18004b99e  xor     ecx, ecx
0x18004b9a0  call    NetInfo_CheckCacheValidity
0x18004b9a5  test    eax, eax
0x18004b9a7  jz      loc_18004BA79
0x18004b9ad  mov     rcx, cs:g_NetworkInfo
0x18004b9b4  lea     rdx, [rbp+57h+var_90]
0x18004b9b8  call    cs:__imp_NetInfo_CreatePerNetworkNetinfo
0x18004b9be  mov     edi, eax
0x18004b9c0  test    eax, eax
0x18004b9c2  jnz     loc_18004BA4E
0x18004b9c8  mov     rcx, [rbp+57h+var_90]
0x18004b9cc  mov     [rcx+30h], r15d
0x18004b9d0  mov     rdx, cs:g_PerNetworkNetInfo
0x18004b9d7  mov     rcx, [rbp+57h+var_90]
0x18004b9db  mov     [rbp+57h+var_A8], rdx
0x18004b9df  mov     cs:g_PerNetworkNetInfo, rcx
0x18004b9e6  mov     [rbp+57h+var_90], rsi
0x18004b9ea  mov     rcx, cs:g_pServerMapView
0x18004b9f1  test    r13, r13
0x18004b9f4  jz      short loc_18004BA17
0x18004b9f6  test    rcx, rcx
0x18004b9f9  jz      short loc_18004BA02
0x18004b9fb  cmp     qword ptr [rcx+10h], 0
0x18004ba00  jnz     short loc_18004BA0E
0x18004ba02  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004ba07  mov     rcx, cs:g_pServerMapView
0x18004ba0e  mov     [r13+0], rcx
0x18004ba12  call    AddRefServerMapView
0x18004ba17  test    r14, r14
0x18004ba1a  jz      loc_18004BDD4
0x18004ba20  mov     rcx, cs:g_PerNetworkNetInfo
0x18004ba27  test    r12d, r12d
0x18004ba2a  jnz     short loc_18004BA33
0x18004ba2c  mov     rcx, cs:g_NetworkInfo
0x18004ba33  call    cs:__imp_NetInfo_Copy
0x18004ba39  mov     [rbp+57h+var_90], rax
0x18004ba3d  test    rax, rax
0x18004ba40  jnz     loc_18004BDCB
0x18004ba46  lea     edi, [rax+0Eh]
0x18004ba49  jmp     loc_18004BDD4
0x18004ba4e  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004ba55  jz      loc_18004BE14
0x18004ba5b  mov     edx, 2Ah ; '*'
0x18004ba60  lea     r8, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids
0x18004ba67  mov     ecx, 40Bh
0x18004ba6c  mov     r9d, eax
0x18004ba6f  call    WPP_SF_d
0x18004ba74  jmp     loc_18004BDD4
0x18004ba79  lea     rcx, g_csNetinfo; lpCriticalSection
0x18004ba80  call    cs:__imp_LeaveCriticalSection
0x18004ba86  cmp     cs:g_fVelocityZtdnsProbing, esi
0x18004ba8c  jz      short loc_18004BACE
0x18004ba8e  lea     r9, [rbp+57h+var_90]
0x18004ba92  xor     ecx, ecx
0x18004ba94  lea     r8, [rbp+57h+var_78]
0x18004ba98  call    DnsApi_NetInfo_BuildEx2
0x18004ba9d  mov     edi, eax
0x18004ba9f  test    eax, eax
0x18004baa1  jz      short loc_18004BAE8
0x18004baa3  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004baaa  jz      loc_18004BE27
0x18004bab0  mov     edx, 2Bh ; '+'
0x18004bab5  mov     ecx, 40Bh
0x18004baba  lea     r8, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids
0x18004bac1  mov     r9d, eax
0x18004bac4  call    WPP_SF_d
0x18004bac9  jmp     loc_18004BE27
0x18004bace  lea     r8, [rbp+57h+var_90]
0x18004bad2  xor     ecx, ecx
0x18004bad4  lea     rdx, [rbp+57h+var_78]
0x18004bad8  call    cs:__imp_NetInfo_BuildEx
0x18004bade  mov     edi, eax
0x18004bae0  test    eax, eax
0x18004bae2  jnz     loc_18004BDB8
0x18004bae8  mov     rax, [rbp+57h+var_90]
0x18004baec  xor     r12d, r12d
0x18004baef  mov     esi, [rbp+57h+var_B0]
0x18004baf2  shr     esi, 1
0x18004baf4  not     esi
0x18004baf6  mov     [rax+30h], r15d
0x18004bafa  and     esi, 1
0x18004bafd  mov     rbx, [rbp+57h+var_90]
0x18004bb01  cmp     [rbx+44h], r12d
0x18004bb05  jbe     short loc_18004BB3F
0x18004bb07  lea     rdi, [r12+r12*4]
0x18004bb0b  shl     rdi, 5
0x18004bb0f  lea     rdx, [rbx+0CCh]
0x18004bb16  add     rdx, rdi
0x18004bb19  mov     ecx, [rdi+rbx+98h]
0x18004bb20  call    Hijack_IsHijack
0x18004bb25  test    eax, eax
0x18004bb27  jz      short loc_18004BB32
0x18004bb29  bts     dword ptr [rdi+rbx+0ACh], 1Eh
0x18004bb32  mov     rbx, [rbp+57h+var_90]
0x18004bb36  inc     r12d
0x18004bb39  cmp     r12d, [rbx+44h]
0x18004bb3d  jb      short loc_18004BB07
0x18004bb3f  mov     r12d, [rbp+57h+var_AC]
0x18004bb43  test    r12d, r12d
0x18004bb46  jz      short loc_18004BB6B
0x18004bb48  lea     rdx, [rbp+57h+var_88]
0x18004bb4c  mov     rcx, rbx
0x18004bb4f  call    cs:__imp_NetInfo_CreatePerNetworkNetinfo
0x18004bb55  mov     edi, eax
0x18004bb57  test    eax, eax
0x18004bb59  jnz     loc_18004BBF8
0x18004bb5f  mov     rax, [rbp+57h+var_88]
0x18004bb63  mov     [rax+30h], r15d
0x18004bb67  mov     rbx, [rbp+57h+var_90]
0x18004bb6b  lea     rdx, [rbp+57h+var_80]
0x18004bb6f  mov     rcx, rbx
0x18004bb72  call    CreateServerMapView
0x18004bb77  mov     edi, eax
0x18004bb79  test    eax, eax
0x18004bb7b  jnz     loc_18004BDA5
0x18004bb81  cmp     cs:g_fZtdnsSelfhostBranch, eax
0x18004bb87  jz      loc_18004BC0F
0x18004bb8d  xor     r9d, r9d
0x18004bb90  lea     r8, [rbp+57h+var_74]
0x18004bb94  lea     rdx, [rbp+57h+var_70]
0x18004bb98  xor     ecx, ecx
0x18004bb9a  call    ZtGetConfigPrivate
0x18004bb9f  mov     edi, eax
0x18004bba1  test    eax, eax
0x18004bba3  jnz     loc_18004BE27
0x18004bba9  lea     rcx, g_rwZtSettingsLock; SRWLock
0x18004bbb0  call    cs:__imp_AcquireSRWLockShared
0x18004bbb6  mov     ebx, cs:g_fZtDriverRunning
0x18004bbbc  lea     rcx, g_rwZtSettingsLock; SRWLock
0x18004bbc3  call    cs:__imp_ReleaseSRWLockShared
0x18004bbc9  test    ebx, ebx
0x18004bbcb  jz      short loc_18004BC0F
0x18004bbcd  cmp     [rbp+57h+var_74], edi
0x18004bbd0  jz      short loc_18004BC0F
0x18004bbd2  mov     rcx, [rbp+57h+var_90]
0x18004bbd6  call    DnsZtAddNetinfoServers
0x18004bbdb  mov     edi, eax
0x18004bbdd  test    eax, eax
0x18004bbdf  jz      short loc_18004BC0F
0x18004bbe1  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004bbe8  jz      loc_18004BE27
0x18004bbee  mov     edx, 2Fh ; '/'
0x18004bbf3  jmp     loc_18004BAB5
0x18004bbf8  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004bbff  jz      loc_18004BE27
0x18004bc05  mov     edx, 2Dh ; '-'
0x18004bc0a  jmp     loc_18004BAB5
0x18004bc0f  mov     rcx, [rbp+57h+var_90]
0x18004bc13  mov     ebx, 1
0x18004bc18  mov     r8d, ebx
0x18004bc1b  mov     edx, ebx
0x18004bc1d  call    cs:__imp_DnsTraceServerConfig
0x18004bc23  lea     rcx, g_csNetinfo; lpCriticalSection
0x18004bc2a  call    cs:__imp_EnterCriticalSection
0x18004bc30  mov     eax, cs:g_NetInfoTag
0x18004bc36  cmp     r15d, eax
0x18004bc39  jz      loc_18004BCD4
0x18004bc3f  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004bc46  jz      short loc_18004BC63
0x18004bc48  lea     edx, [rbx+2Fh]
0x18004bc4b  mov     dword ptr [rsp+0F0h+var_D0], eax
0x18004bc4f  mov     ecx, 40Bh
0x18004bc54  lea     r8, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids
0x18004bc5b  mov     r9d, r15d
0x18004bc5e  call    WPP_SF_dd
0x18004bc63  test    r13, r13
0x18004bc66  jz      short loc_18004BC86
0x18004bc68  mov     rax, [rbp+57h+var_80]
0x18004bc6c  test    rax, rax
0x18004bc6f  jnz     short loc_18004BC7A
0x18004bc71  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004bc76  mov     rax, [rbp+57h+var_80]
0x18004bc7a  mov     [r13+0], rax
0x18004bc7e  mov     [rbp+57h+var_80], 0
0x18004bc86  test    r14, r14
0x18004bc89  jnz     short loc_18004BC9C
0x18004bc8b  mov     rbx, [rbp+57h+var_90]
0x18004bc8f  mov     [rbp+57h+var_B8], rbx
0x18004bc93  mov     [rbp+57h+var_90], r14
0x18004bc97  jmp     loc_18004BDD4
0x18004bc9c  test    r12d, r12d
0x18004bc9f  jz      short loc_18004BCB7
0x18004bca1  mov     rax, [rbp+57h+var_90]
0x18004bca5  mov     [rbp+57h+var_B8], rax
0x18004bca9  mov     rax, [rbp+57h+var_88]
0x18004bcad  mov     [rbp+57h+var_88], 0
0x18004bcb5  jmp     short loc_18004BCC7
0x18004bcb7  cmp     [rbp+57h+var_88], 0
0x18004bcbc  jz      short loc_18004BCC3
0x18004bcbe  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004bcc3  mov     rax, [rbp+57h+var_90]
0x18004bcc7  mov     [rbp+57h+var_90], 0
0x18004bccf  jmp     loc_18004BDD1
0x18004bcd4  mov     rax, cs:__imp_DnsGlobals
0x18004bcdb  mov     rdx, [rbp+57h+var_90]
0x18004bcdf  mov     ecx, [rax+160h]
0x18004bce5  mov     rax, [rbp+57h+var_98]
0x18004bce9  add     eax, ecx
0x18004bceb  lea     rcx, aUpdatingGNetwo; "Updating g_NetworkInfo: "
0x18004bcf2  mov     cs:g_ResetServerPriorityTime, eax
0x18004bcf8  mov     eax, [rbp+57h+var_78]
0x18004bcfb  and     eax, ebx
0x18004bcfd  mov     cs:g_EnableNdisIfNetInfoProcessing, eax
0x18004bd03  call    DnsPrint_NetworkInfo
0x18004bd08  mov     rdx, [rbp+57h+var_88]
0x18004bd0c  lea     rcx, aUpdatingGPerne; "Updating g_PerNetworkInfo: "
0x18004bd13  call    DnsPrint_NetworkInfo
0x18004bd18  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004bd1f  jz      short loc_18004BD3B
0x18004bd21  mov     r9, [rbp+57h+var_80]
0x18004bd25  lea     r8, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids
0x18004bd2c  mov     edx, 31h ; '1'
0x18004bd31  mov     ecx, 40Bh
  ... truncated ...
```

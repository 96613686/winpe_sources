# GrabNetworkInfoOld

- ea: `0x18003e1d4`
- end: `0x18003e99e`
- name: `GrabNetworkInfoOld`
- size: `1994`
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
- `0x18002a690`
- `0x18002b6d0`
- `0x18002b778`
- `0x18003508c`
- `0x18003e1d4`
- `0x180040cd4`
- `0x180045ac0`
- `0x180046ec0`
- `0x18004b808`
- `0x18007b150`
- `0x180086b1c`
- `0x180086b70`
- `0x180086f24`
- `0x180087138`
- `0x180088578`

## import_xrefs

- `DNSAPI!NetInfo_CreatePerNetworkNetinfo` at `0x18003e3d2`
- `DNSAPI!NetInfo_CreatePerNetworkNetinfo` at `0x18003e4ff`
- `DNSAPI!NetInfo_CreatePerNetworkNetinfo` at `0x18003e3d2`
- `DNSAPI!NetInfo_CreatePerNetworkNetinfo` at `0x18003e4ff`
- `DNSAPI!DnsGlobals` at `0x18003e333`
- `DNSAPI!DnsGlobals` at `0x18003e3ae`
- `DNSAPI!DnsGlobals` at `0x18003e6c0`
- `DNSAPI!DnsTraceServerConfig` at `0x18003e5d6`
- `DNSAPI!DnsTraceServerConfig` at `0x18003e5d6`
- `DNSAPI!NetInfo_Free` at `0x18003e889`
- `DNSAPI!NetInfo_Free` at `0x18003e892`
- `DNSAPI!NetInfo_Free` at `0x18003e89c`
- `DNSAPI!NetInfo_Free` at `0x18003e889`
- `DNSAPI!NetInfo_Free` at `0x18003e892`
- `DNSAPI!NetInfo_Free` at `0x18003e89c`
- `DNSAPI!NetInfo_Copy` at `0x18003e7d6`
- `DNSAPI!NetInfo_Copy` at `0x18003e7d6`
- `DNSAPI!NetInfo_ResetServerPriorities` at `0x18003e32d`
- `DNSAPI!NetInfo_ResetServerPriorities` at `0x18003e3a8`
- `DNSAPI!NetInfo_ResetServerPriorities` at `0x18003e32d`
- `DNSAPI!NetInfo_ResetServerPriorities` at `0x18003e3a8`
- `DNSAPI!NetInfo_BuildEx` at `0x18003e48b`
- `DNSAPI!NetInfo_BuildEx` at `0x18003e48b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003e55c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003e55c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003e56f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003e56f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e2ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e447`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e829`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e880`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e2ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e447`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e829`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e880`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e2ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e30c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e5e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e2ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e30c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e5e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003e222`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003e222`

## pseudocode

```c
__int64 __fastcall GrabNetworkInfoOld(int a1, int a2, __int64 *a3, _QWORD *a4)
{
  _QWORD *v5; // r15
  ULONGLONG TickCount64; // rax
  int v9; // r8d
  int v10; // edi
  int v11; // esi
  unsigned __int64 v12; // r13
  __int64 v13; // r9
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // rdx
  int RereadTimeFromNetInfo; // eax
  __int64 v18; // r8
  unsigned int ConfigPrivate; // edi
  _QWORD *v20; // rcx
  unsigned int v21; // r15d
  int v22; // eax
  __int64 v23; // r8
  __int64 v24; // r9
  unsigned int v25; // eax
  __int64 v26; // rbx
  __int64 v27; // rdx
  unsigned int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // r12
  __int64 i; // rbx
  unsigned int v32; // eax
  int v33; // ebx
  __int64 v34; // rdx
  void *v35; // rax
  __int64 v36; // rax
  void *v37; // r12
  __int64 v38; // r15
  int v39; // eax
  __int64 v40; // rax
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  _BOOL8 v44; // rcx
  __int64 v45; // r9
  __int64 v46; // r8
  __int64 v48; // [rsp+40h] [rbp-79h]
  __int64 v49; // [rsp+48h] [rbp-71h]
  void *v50; // [rsp+50h] [rbp-69h]
  int v51; // [rsp+58h] [rbp-61h]
  __int64 v54; // [rsp+70h] [rbp-49h] BYREF
  __int64 v55; // [rsp+78h] [rbp-41h] BYREF
  __int64 v56; // [rsp+80h] [rbp-39h] BYREF
  void *v57; // [rsp+88h] [rbp-31h] BYREF
  int v58; // [rsp+90h] [rbp-29h] BYREF
  int v59; // [rsp+94h] [rbp-25h] BYREF
  _OWORD v60[3]; // [rsp+98h] [rbp-21h] BYREF
  __int64 v61; // [rsp+C8h] [rbp+Fh]

  v48 = 0;
  v5 = a4;
  v54 = 0;
  v49 = 0;
  v56 = 0;
  TickCount64 = GetTickCount64();
  v51 = 0;
  v55 = 0;
  memset(v60, 0, sizeof(v60));
  v10 = 0;
  v58 = 0;
  v50 = 0;
  v11 = 0;
  v57 = 0;
  v12 = TickCount64 / 0x3E8;
  v59 = 0;
  v61 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_llqq(0, (TickCount64 * (unsigned __int128)0x624DD2F1A9FBE77uLL) >> 64, v9, a1, a2, (__int64)a3, (__int64)v5);
  if ( v5 )
    *v5 = 0;
  if ( a3 )
    *a3 = 0;
  while ( 1 )
  {
    EnterCriticalSection(&g_csNetinfo);
    v13 = g_NetworkInfo;
    if ( a1 )
    {
      v14 = g_PerNetworkNetInfo;
      v55 = g_PerNetworkNetInfo;
      v15 = g_PerNetworkNetInfo;
      v16 = g_PerNetworkNetInfo;
    }
    else
    {
      v14 = g_NetworkInfo;
      v55 = g_NetworkInfo;
      v15 = g_NetworkInfo;
      v16 = g_NetworkInfo;
    }
    if ( v15 )
    {
      RereadTimeFromNetInfo = GetRereadTimeFromNetInfo(v14, v16);
      if ( *(_DWORD *)(v16 + 44) + RereadTimeFromNetInfo > (unsigned int)v12 )
      {
        ConfigPrivate = 0;
        if ( g_ResetServerPriorityTime < (unsigned int)v12 )
        {
          NetInfo_ResetServerPriorities(v18, 1);
          v18 = v55;
          v13 = g_NetworkInfo;
          g_ResetServerPriorityTime = v12 + DnsGlobals[88];
        }
        v20 = g_pServerMapView;
        goto LABEL_77;
      }
    }
    if ( v10 )
      break;
    LeaveCriticalSection(&g_csNetinfo);
    EnterCriticalSection(&g_csResolverNetInfo);
    v10 = 1;
    v51 = 1;
  }
  v21 = ++g_NetInfoTag;
  if ( !a1 || !v13 || (v22 = GetRereadTimeFromNetInfo(v13, v16), *(_DWORD *)(v24 + 44) + v22 <= (unsigned int)v12) )
  {
    LeaveCriticalSection(&g_csNetinfo);
    if ( g_fVelocityZtdnsProbing )
    {
      v28 = DnsApi_NetInfo_BuildEx2(0, v27, &v58, &v54);
      ConfigPrivate = v28;
      if ( v28 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        {
          v29 = 23;
LABEL_94:
          WPP_SF_d(1035, v29, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, v28);
          goto LABEL_95;
        }
        goto LABEL_95;
      }
    }
    else
    {
      v28 = NetInfo_BuildEx(0, &v58, &v54);
      ConfigPrivate = v28;
      if ( v28 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        {
          v29 = 24;
          goto LABEL_94;
        }
LABEL_95:
        v26 = 0;
        goto LABEL_96;
      }
    }
    LOBYTE(v11) = a2 != 0;
    v30 = 0;
    *(_DWORD *)(v54 + 48) = v21;
    for ( i = v54; (unsigned int)v30 < *(_DWORD *)(v54 + 68); v30 = (unsigned int)(v30 + 1) )
    {
      if ( (unsigned int)Hijack_IsHijack(*(unsigned int *)(160 * v30 + i + 152), 160 * v30 + i + 204) )
        *(_DWORD *)(160 * v30 + i + 172) |= 0x40000000u;
      i = v54;
    }
    if ( a1 )
    {
      v32 = NetInfo_CreatePerNetworkNetinfo(i, &v56);
      ConfigPrivate = v32;
      if ( v32 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        {
          v34 = 25;
          goto LABEL_49;
        }
LABEL_50:
        v26 = 0;
LABEL_96:
        v37 = 0;
        v38 = 0;
        goto LABEL_97;
      }
      *(_DWORD *)(v56 + 48) = v21;
      i = v54;
    }
    v32 = CreateServerMapView(i, &v57);
    ConfigPrivate = v32;
    if ( v32 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
        goto LABEL_50;
      v34 = 26;
      goto LABEL_49;
    }
    if ( g_fZtdnsSelfhostBranch )
    {
      ConfigPrivate = ZtGetConfigPrivate(0, v60, &v59, 0);
      if ( ConfigPrivate )
        goto LABEL_50;
      AcquireSRWLockShared(&g_rwZtSettingsLock);
      v33 = g_fZtDriverRunning;
      ReleaseSRWLockShared(&g_rwZtSettingsLock);
      if ( v33 )
      {
        if ( v59 != ConfigPrivate )
        {
          v32 = DnsZtAddNetinfoServers(v54);
          ConfigPrivate = v32;
          if ( v32 )
          {
            if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
            {
              v34 = 27;
LABEL_49:
              WPP_SF_d(1035, v34, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, v32);
              goto LABEL_50;
            }
            goto LABEL_50;
          }
        }
      }
    }
    DnsTraceServerConfig(v54, 1, 1);
    EnterCriticalSection(&g_csNetinfo);
    if ( v21 != g_NetInfoTag )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_dd(1035, 28, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, v21, g_NetInfoTag);
      if ( a4 )
      {
        v35 = v57;
        if ( !v57 )
        {
          ((void (*)(void))MicrosoftTelemetryAssertTriggeredNoArgs)();
          v35 = v57;
        }
        *a4 = v35;
        v57 = 0;
      }
      if ( !a3 )
      {
        v26 = v54;
        v13 = g_NetworkInfo;
        v54 = 0;
        goto LABEL_67;
      }
      if ( a1 )
      {
        v48 = v54;
        v36 = v56;
        v56 = 0;
      }
      else
      {
        if ( v56 )
          ((void (*)(void))MicrosoftTelemetryAssertTriggeredNoArgs)();
        v36 = v54;
      }
      v13 = g_NetworkInfo;
      *a3 = v36;
      v54 = 0;
      goto LABEL_66;
    }
    g_ResetServerPriorityTime = v12 + DnsGlobals[88];
    g_EnableNdisIfNetInfoProcessing = v58 & 1;
    DnsPrint_NetworkInfo("Updating g_NetworkInfo: ", v54);
    DnsPrint_NetworkInfo("Updating g_PerNetworkInfo: ", v56);
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_q(1035, 29, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, v57);
    v20 = v57;
    v13 = v54;
    v50 = g_pServerMapView;
    v48 = g_NetworkInfo;
    g_pServerMapView = v57;
    v57 = 0;
    g_NetworkInfo = v54;
    v54 = 0;
    if ( a1 )
    {
      v18 = v56;
      v49 = g_PerNetworkNetInfo;
      g_PerNetworkNetInfo = v56;
      v55 = v56;
      v56 = 0;
    }
    else
    {
      v18 = v13;
      v55 = v13;
    }
    g_IsReachableServerUpdateRequired = 1;
LABEL_76:
    v5 = a4;
LABEL_77:
    if ( v5 )
    {
      if ( !v20 || !v20[2] )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v20, v16, v18, v13);
        v20 = g_pServerMapView;
      }
      *v5 = v20;
      AddRefServerMapView(v20, v16, v18, v13);
      v18 = v55;
      v13 = g_NetworkInfo;
    }
    if ( a3 )
    {
      v40 = NetInfo_Copy(v18);
      v13 = g_NetworkInfo;
      v26 = v48;
      v54 = v40;
      if ( v40 )
      {
        ConfigPrivate = 0;
        *a3 = v40;
        v54 = 0;
      }
      else
      {
        ConfigPrivate = 14;
      }
      goto LABEL_67;
    }
LABEL_66:
    v26 = v48;
    goto LABEL_67;
  }
  if ( g_ResetServerPriorityTime < (unsigned int)v12 )
  {
    NetInfo_ResetServerPriorities(v23, 1);
    v24 = g_NetworkInfo;
    g_ResetServerPriorityTime = v12 + DnsGlobals[88];
  }
  v25 = NetInfo_CreatePerNetworkNetinfo(v24, &v55);
  ConfigPrivate = v25;
  if ( !v25 )
  {
    v13 = g_NetworkInfo;
    *(_DWORD *)(v55 + 48) = v21;
    v18 = v55;
    v20 = g_pServerMapView;
    v49 = g_PerNetworkNetInfo;
    g_PerNetworkNetInfo = v55;
    goto LABEL_76;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 22, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, v25);
  v13 = g_NetworkInfo;
  v26 = 0;
LABEL_67:
  v37 = v50;
  v38 = v49;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    if ( v13 )
      v39 = *(_DWORD *)(v13 + 56);
    else
      v39 = 0;
    WPP_SF_qD(1035, 30, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, v13, v39);
  }
  LeaveCriticalSection(&g_csNetinfo);
  if ( v51 )
LABEL_97:
    LeaveCriticalSection(&g_csResolverNetInfo);
  NetInfo_Free(v26);
  NetInfo_Free(v38);
  NetInfo_Free(v56);
  DeRefServerMapView(v37);
  DeRefServerMapView(v57);
  if ( v11 )
    NS_Process();
  if ( a3 )
  {
    v44 = *a3 != 0;
    if ( (ConfigPrivate == 0) != v44 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v44, v41, v42, v43);
  }
  if ( a4 )
  {
    v45 = *a4;
    if ( *a4 )
    {
      v46 = *(_QWORD *)(v45 + 16);
      if ( v46 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_qqd(1035, 31, (unsigned int)WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, v45, v46);
      }
    }
  }
  if ( a3 && *a3 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      WPP_SF_qD(1035, 32, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, *a3, *(_DWORD *)(*a3 + 56));
      goto LABEL_112;
    }
  }
  else
  {
LABEL_112:
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 33, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, ConfigPrivate);
  }
  return ConfigPrivate;
}

```

## disassembly

```asm
0x18003e1d4  mov     [rsp-8+arg_8], rbx
0x18003e1d9  push    rbp
0x18003e1da  push    rsi
0x18003e1db  push    rdi
0x18003e1dc  push    r12
0x18003e1de  push    r13
0x18003e1e0  push    r14
0x18003e1e2  push    r15
0x18003e1e4  lea     rbp, [rsp-27h]
0x18003e1e9  sub     rsp, 0E0h
0x18003e1f0  mov     rax, cs:__security_cookie
0x18003e1f7  xor     rax, rsp
0x18003e1fa  mov     [rbp+57h+var_40], rax
0x18003e1fe  mov     ebx, ecx
0x18003e200  mov     [rbp+57h+var_A8], ecx
0x18003e203  xor     ecx, ecx
0x18003e205  mov     [rbp+57h+var_B0], r9
0x18003e209  mov     [rbp+57h+var_D0], rcx
0x18003e20d  mov     r15, r9
0x18003e210  mov     [rbp+57h+var_A0], rcx
0x18003e214  mov     r14, r8
0x18003e217  mov     [rbp+57h+var_C8], rcx
0x18003e21b  mov     r12d, edx
0x18003e21e  mov     [rbp+57h+var_90], rcx
0x18003e222  call    cs:__imp_GetTickCount64
0x18003e228  xor     ecx, ecx
0x18003e22a  xorps   xmm0, xmm0
0x18003e22d  mov     r13, rax
0x18003e230  mov     [rbp+57h+var_B8], ecx
0x18003e233  mov     rax, 624DD2F1A9FBE77h
0x18003e23d  mov     [rbp+57h+var_98], rcx
0x18003e241  mul     r13
0x18003e244  movups  [rbp+57h+var_78], xmm0
0x18003e248  movups  [rbp+57h+var_68], xmm0
0x18003e24c  mov     edi, ecx
0x18003e24e  mov     [rbp+57h+var_80], ecx
0x18003e251  sub     r13, rdx
0x18003e254  mov     [rbp+57h+var_C0], rcx
0x18003e258  shr     r13, 1
0x18003e25b  mov     esi, ecx
0x18003e25d  add     r13, rdx
0x18003e260  mov     [rbp+57h+var_88], rcx
0x18003e264  shr     r13, 9
0x18003e268  xor     eax, eax
0x18003e26a  mov     [rbp+57h+var_7C], ecx
0x18003e26d  mov     [rbp+57h+var_48], rax
0x18003e271  movups  [rbp+57h+var_58], xmm0
0x18003e275  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003e27c  jz      short loc_18003E297
0x18003e27e  mov     [rsp+110h+var_E0], r15
0x18003e283  mov     r9d, ebx
0x18003e286  mov     [rsp+110h+var_E8], r14
0x18003e28b  mov     dword ptr [rsp+110h+var_F0], r12d
0x18003e290  call    WPP_SF_llqq
0x18003e295  xor     ecx, ecx
0x18003e297  test    r15, r15
0x18003e29a  jz      short loc_18003E29F
0x18003e29c  mov     [r15], rcx
0x18003e29f  test    r14, r14
0x18003e2a2  jz      short loc_18003E2A7
0x18003e2a4  mov     [r14], rcx
0x18003e2a7  lea     rcx, g_csNetinfo; lpCriticalSection
0x18003e2ae  call    cs:__imp_EnterCriticalSection
0x18003e2b4  mov     r9, cs:g_NetworkInfo
0x18003e2bb  test    ebx, ebx
0x18003e2bd  jz      short loc_18003E2D2
0x18003e2bf  mov     r8, cs:g_PerNetworkNetInfo
0x18003e2c6  mov     [rbp+57h+var_98], r8
0x18003e2ca  mov     rax, r8
0x18003e2cd  mov     rdx, r8
0x18003e2d0  jmp     short loc_18003E2DF
0x18003e2d2  mov     r8, r9
0x18003e2d5  mov     [rbp+57h+var_98], r9
0x18003e2d9  mov     rax, r9
0x18003e2dc  mov     rdx, r9
0x18003e2df  test    rax, rax
0x18003e2e2  jz      short loc_18003E2F4
0x18003e2e4  mov     rcx, r8
0x18003e2e7  call    GetRereadTimeFromNetInfo
0x18003e2ec  add     eax, [rdx+2Ch]
0x18003e2ef  cmp     eax, r13d
0x18003e2f2  ja      short loc_18003E31C
0x18003e2f4  test    edi, edi
0x18003e2f6  jnz     short loc_18003E360
0x18003e2f8  lea     rcx, g_csNetinfo; lpCriticalSection
0x18003e2ff  call    cs:__imp_LeaveCriticalSection
0x18003e305  lea     rcx, g_csResolverNetInfo; lpCriticalSection
0x18003e30c  call    cs:__imp_EnterCriticalSection
0x18003e312  mov     edi, 1
0x18003e317  mov     [rbp+57h+var_B8], edi
0x18003e31a  jmp     short loc_18003E2A7
0x18003e31c  xor     edi, edi
0x18003e31e  cmp     cs:g_ResetServerPriorityTime, r13d
0x18003e325  jnb     short loc_18003E354
0x18003e327  lea     edx, [rdi+1]
0x18003e32a  mov     rcx, r8
0x18003e32d  call    cs:__imp_NetInfo_ResetServerPriorities
0x18003e333  mov     rax, cs:__imp_DnsGlobals
0x18003e33a  mov     r8, [rbp+57h+var_98]
0x18003e33e  mov     r9, cs:g_NetworkInfo
0x18003e345  mov     eax, [rax+160h]
0x18003e34b  add     eax, r13d
0x18003e34e  mov     cs:g_ResetServerPriorityTime, eax
0x18003e354  mov     rcx, cs:g_pServerMapView
0x18003e35b  jmp     loc_18003E79A
0x18003e360  mov     r15d, cs:g_NetInfoTag
0x18003e367  inc     r15d
0x18003e36a  mov     cs:g_NetInfoTag, r15d
0x18003e371  test    ebx, ebx
0x18003e373  jz      loc_18003E440
0x18003e379  test    r9, r9
0x18003e37c  jz      loc_18003E440
0x18003e382  mov     rcx, r9
0x18003e385  call    GetRereadTimeFromNetInfo
0x18003e38a  add     eax, [r9+2Ch]
0x18003e38e  cmp     eax, r13d
0x18003e391  jbe     loc_18003E440
0x18003e397  cmp     cs:g_ResetServerPriorityTime, r13d
0x18003e39e  jnb     short loc_18003E3CB
0x18003e3a0  mov     edx, 1
0x18003e3a5  mov     rcx, r8
0x18003e3a8  call    cs:__imp_NetInfo_ResetServerPriorities
0x18003e3ae  mov     rax, cs:__imp_DnsGlobals
0x18003e3b5  mov     r9, cs:g_NetworkInfo
0x18003e3bc  mov     eax, [rax+160h]
0x18003e3c2  add     eax, r13d
0x18003e3c5  mov     cs:g_ResetServerPriorityTime, eax
0x18003e3cb  lea     rdx, [rbp+57h+var_98]
0x18003e3cf  mov     rcx, r9
0x18003e3d2  call    cs:__imp_NetInfo_CreatePerNetworkNetinfo
0x18003e3d8  mov     edi, eax
0x18003e3da  test    eax, eax
0x18003e3dc  jnz     short loc_18003E40F
0x18003e3de  mov     rcx, [rbp+57h+var_98]
0x18003e3e2  mov     r9, cs:g_NetworkInfo
0x18003e3e9  mov     [rcx+30h], r15d
0x18003e3ed  mov     rax, cs:g_PerNetworkNetInfo
0x18003e3f4  mov     r8, [rbp+57h+var_98]
0x18003e3f8  mov     rcx, cs:g_pServerMapView
0x18003e3ff  mov     [rbp+57h+var_C8], rax
0x18003e403  mov     cs:g_PerNetworkNetInfo, r8
0x18003e40a  jmp     loc_18003E796
0x18003e40f  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003e416  jz      short loc_18003E431
0x18003e418  mov     edx, 16h
0x18003e41d  lea     r8, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids
0x18003e424  mov     ecx, 40Bh
0x18003e429  mov     r9d, eax
0x18003e42c  call    WPP_SF_d
0x18003e431  mov     r9, cs:g_NetworkInfo
0x18003e438  mov     rbx, rsi
0x18003e43b  jmp     loc_18003E699
0x18003e440  lea     rcx, g_csNetinfo; lpCriticalSection
0x18003e447  call    cs:__imp_LeaveCriticalSection
0x18003e44d  cmp     cs:g_fVelocityZtdnsProbing, esi
0x18003e453  jz      short loc_18003E481
0x18003e455  lea     r9, [rbp+57h+var_A0]
0x18003e459  xor     ecx, ecx
0x18003e45b  lea     r8, [rbp+57h+var_80]
0x18003e45f  call    DnsApi_NetInfo_BuildEx2
0x18003e464  mov     edi, eax
0x18003e466  test    eax, eax
0x18003e468  jz      short loc_18003E49B
0x18003e46a  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003e471  jz      loc_18003E870
0x18003e477  mov     edx, 17h
0x18003e47c  jmp     loc_18003E85C
0x18003e481  lea     r8, [rbp+57h+var_A0]
0x18003e485  xor     ecx, ecx
0x18003e487  lea     rdx, [rbp+57h+var_80]
0x18003e48b  call    cs:__imp_NetInfo_BuildEx
0x18003e491  mov     edi, eax
0x18003e493  test    eax, eax
0x18003e495  jnz     loc_18003E84E
0x18003e49b  mov     rax, [rbp+57h+var_A0]
0x18003e49f  test    r12d, r12d
0x18003e4a2  setnz   sil
0x18003e4a6  xor     r12d, r12d
0x18003e4a9  mov     [rax+30h], r15d
0x18003e4ad  mov     rbx, [rbp+57h+var_A0]
0x18003e4b1  cmp     [rbx+44h], r12d
0x18003e4b5  jbe     short loc_18003E4EF
0x18003e4b7  lea     rdi, [r12+r12*4]
0x18003e4bb  shl     rdi, 5
0x18003e4bf  lea     rdx, [rbx+0CCh]
0x18003e4c6  add     rdx, rdi
0x18003e4c9  mov     ecx, [rdi+rbx+98h]
0x18003e4d0  call    Hijack_IsHijack
0x18003e4d5  test    eax, eax
0x18003e4d7  jz      short loc_18003E4E2
0x18003e4d9  bts     dword ptr [rdi+rbx+0ACh], 1Eh
0x18003e4e2  mov     rbx, [rbp+57h+var_A0]
0x18003e4e6  inc     r12d
0x18003e4e9  cmp     r12d, [rbx+44h]
0x18003e4ed  jb      short loc_18003E4B7
0x18003e4ef  mov     r12d, [rbp+57h+var_A8]
0x18003e4f3  test    r12d, r12d
0x18003e4f6  jz      short loc_18003E51B
0x18003e4f8  lea     rdx, [rbp+57h+var_90]
0x18003e4fc  mov     rcx, rbx
0x18003e4ff  call    cs:__imp_NetInfo_CreatePerNetworkNetinfo
0x18003e505  mov     edi, eax
0x18003e507  test    eax, eax
0x18003e509  jnz     loc_18003E59D
0x18003e50f  mov     rax, [rbp+57h+var_90]
0x18003e513  mov     [rax+30h], r15d
0x18003e517  mov     rbx, [rbp+57h+var_A0]
0x18003e51b  lea     rdx, [rbp+57h+var_88]
0x18003e51f  mov     rcx, rbx
0x18003e522  call    CreateServerMapView
0x18003e527  mov     edi, eax
0x18003e529  test    eax, eax
0x18003e52b  jnz     loc_18003E837
0x18003e531  cmp     cs:g_fZtdnsSelfhostBranch, eax
0x18003e537  jz      loc_18003E5C8
0x18003e53d  xor     r9d, r9d
0x18003e540  lea     r8, [rbp+57h+var_7C]
0x18003e544  lea     rdx, [rbp+57h+var_78]
0x18003e548  xor     ecx, ecx
0x18003e54a  call    ZtGetConfigPrivate
0x18003e54f  mov     edi, eax
0x18003e551  test    eax, eax
0x18003e553  jnz     short loc_18003E5BF
0x18003e555  lea     rcx, g_rwZtSettingsLock; SRWLock
0x18003e55c  call    cs:__imp_AcquireSRWLockShared
0x18003e562  mov     ebx, cs:g_fZtDriverRunning
0x18003e568  lea     rcx, g_rwZtSettingsLock; SRWLock
0x18003e56f  call    cs:__imp_ReleaseSRWLockShared
0x18003e575  test    ebx, ebx
0x18003e577  jz      short loc_18003E5C8
0x18003e579  cmp     [rbp+57h+var_7C], edi
0x18003e57c  jz      short loc_18003E5C8
0x18003e57e  mov     rcx, [rbp+57h+var_A0]
0x18003e582  call    DnsZtAddNetinfoServers
0x18003e587  mov     edi, eax
0x18003e589  test    eax, eax
0x18003e58b  jz      short loc_18003E5C8
0x18003e58d  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003e594  jz      short loc_18003E5BF
0x18003e596  mov     edx, 1Bh
0x18003e59b  jmp     short loc_18003E5AB
0x18003e59d  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003e5a4  jz      short loc_18003E5BF
0x18003e5a6  mov     edx, 19h
0x18003e5ab  mov     ecx, 40Bh
0x18003e5b0  lea     r8, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids
0x18003e5b7  mov     r9d, eax
0x18003e5ba  call    WPP_SF_d
0x18003e5bf  mov     rbx, [rbp+57h+var_D0]
0x18003e5c3  jmp     loc_18003E873
0x18003e5c8  mov     rcx, [rbp+57h+var_A0]
0x18003e5cc  mov     ebx, 1
0x18003e5d1  mov     r8d, ebx
0x18003e5d4  mov     edx, ebx
0x18003e5d6  call    cs:__imp_DnsTraceServerConfig
0x18003e5dc  lea     rcx, g_csNetinfo; lpCriticalSection
0x18003e5e3  call    cs:__imp_EnterCriticalSection
0x18003e5e9  mov     eax, cs:g_NetInfoTag
0x18003e5ef  cmp     r15d, eax
0x18003e5f2  jz      loc_18003E6C0
0x18003e5f8  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003e5ff  jz      short loc_18003E61C
0x18003e601  lea     edx, [rbx+1Bh]
0x18003e604  mov     dword ptr [rsp+110h+var_F0], eax
0x18003e608  mov     ecx, 40Bh
0x18003e60d  lea     r8, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids
0x18003e614  mov     r9d, r15d
0x18003e617  call    WPP_SF_dd
0x18003e61c  mov     r15, [rbp+57h+var_B0]
0x18003e620  test    r15, r15
0x18003e623  jz      short loc_18003E642
0x18003e625  mov     rax, [rbp+57h+var_88]
0x18003e629  test    rax, rax
0x18003e62c  jnz     short loc_18003E637
0x18003e62e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003e633  mov     rax, [rbp+57h+var_88]
0x18003e637  mov     [r15], rax
0x18003e63a  mov     [rbp+57h+var_88], 0
0x18003e642  test    r14, r14
0x18003e645  jnz     short loc_18003E658
0x18003e647  mov     rbx, [rbp+57h+var_A0]
0x18003e64b  mov     r9, cs:g_NetworkInfo
0x18003e652  mov     [rbp+57h+var_A0], r14
0x18003e656  jmp     short loc_18003E699
0x18003e658  test    r12d, r12d
0x18003e65b  jz      short loc_18003E673
0x18003e65d  mov     rax, [rbp+57h+var_A0]
0x18003e661  mov     [rbp+57h+var_D0], rax
0x18003e665  mov     rax, [rbp+57h+var_90]
0x18003e669  mov     [rbp+57h+var_90], 0
0x18003e671  jmp     short loc_18003E683
0x18003e673  cmp     [rbp+57h+var_90], 0
0x18003e678  jz      short loc_18003E67F
0x18003e67a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003e67f  mov     rax, [rbp+57h+var_A0]
0x18003e683  mov     r9, cs:g_NetworkInfo
0x18003e68a  mov     [r14], rax
0x18003e68d  mov     [rbp+57h+var_A0], 0
0x18003e695  mov     rbx, [rbp+57h+var_D0]
0x18003e699  mov     r12, [rbp+57h+var_C0]
  ... truncated ...
```

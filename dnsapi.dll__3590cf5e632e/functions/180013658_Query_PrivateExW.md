# Query_PrivateExW

- ea: `0x180013658`
- end: `0x1800143ff`
- name: `Query_PrivateExW`
- size: `3495`
- prototype: `__int64 __usercall@<rax>(PCNZWCH lpString1@<rcx>, int, int, __int64, __int64, __int64, int, __int64, __int16, __int64, __int64)`
- caller_count: `5`
- callee_count: `33`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012510`
- `0x180012e70`
- `0x1800131f0`
- `0x18006d640`
- `0x180093bc0`

## callees

- `0x180005c1c`
- `0x180008830`
- `0x18000dfb8`
- `0x1800112d0`
- `0x180011700`
- `0x180013658`
- `0x180015150`
- `0x180015474`
- `0x180015590`
- `0x180015610`
- `0x18002733c`
- `0x180029d80`
- `0x18002a4e0`
- `0x18002b050`
- `0x18002c020`
- `0x18004ef1c`
- `0x18006cf08`
- `0x18006fd34`
- `0x1800749b4`
- `0x180083954`
- `0x18008b5f0`
- `0x180092310`
- `0x180092d54`
- `0x180092f48`
- `0x18009358c`
- `0x1800bbc80`
- `0x1800bbd2c`
- `0x1800dbadc`
- `0x1800dbfe0`
- `0x1800dc9e0`
- `0x1800dd050`
- `0x1800de650`
- `0x1800dfcac`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013835`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013835`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x180013962`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x180013962`

## pseudocode

```c
__int64 __fastcall Query_PrivateExW(
        PCNZWCH lpString1,
        unsigned __int16 a2,
        __int64 *a3,
        __int64 a4,
        int a5,
        int a6,
        __int128 *a7,
        __int64 a8,
        _DWORD *a9,
        unsigned int a10,
        void *a11,
        __int16 a12,
        __int64 a13,
        __int64 a14)
{
  const WCHAR *v15; // r13
  int v16; // esi
  __int64 v17; // rax
  unsigned int v18; // eax
  __int64 v19; // rcx
  unsigned int DnsServerRRSet; // edi
  int v21; // r9d
  unsigned int v22; // r14d
  int v23; // ebx
  __int64 RecordForIpString_W; // rax
  __int64 *v25; // r15
  unsigned int v26; // eax
  __int64 v27; // r8
  unsigned __int16 v28; // bx
  DNS_STATUS v29; // eax
  unsigned int v30; // edi
  LPVOID v31; // rbx
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // eax
  int v33; // ecx
  NET_IF_COMPARTMENT_ID v34; // r15d
  unsigned int v35; // eax
  void *v36; // rbx
  unsigned int v38; // eax
  __int64 v39; // rax
  __int64 v40; // rdx
  unsigned int v41; // r10d
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // rax
  char v45; // al
  void *HostName; // rax
  bool v47; // zf
  unsigned int v48; // eax
  void *v49; // rax
  char v50; // r9
  unsigned int v51; // r14d
  unsigned int v52; // eax
  char v53; // r9
  __int64 v54; // [rsp+38h] [rbp-C8h]
  _DWORD v56[3]; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v57; // [rsp+90h] [rbp-70h]
  LPVOID v58; // [rsp+98h] [rbp-68h]
  int v59; // [rsp+A0h] [rbp-60h]
  __int128 *v60; // [rsp+A8h] [rbp-58h]
  __int64 v61; // [rsp+B0h] [rbp-50h]
  __int64 v62; // [rsp+B8h] [rbp-48h]
  __int64 v63; // [rsp+C0h] [rbp-40h]
  int v64; // [rsp+C8h] [rbp-38h]
  __int64 v65; // [rsp+D0h] [rbp-30h]
  LPVOID v66; // [rsp+D8h] [rbp-28h]
  __int64 v67; // [rsp+E0h] [rbp-20h]
  LPVOID lpMem; // [rsp+E8h] [rbp-18h]
  LPVOID v69[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v70; // [rsp+100h] [rbp+0h] BYREF
  _DWORD v71[2]; // [rsp+110h] [rbp+10h] BYREF

  v15 = lpString1;
  v62 = a8;
  v63 = a14;
  v16 = a2;
  lpMem = 0;
  v56[0] = 0;
  v66 = 0;
  v71[0] = 0;
  v69[0] = 0;
  v67 = a4;
  v60 = a7;
  v58 = a11;
  v61 = a13;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_Sdiqql((_DWORD)lpString1, *a3, (_DWORD)a3, (_DWORD)lpString1, a2, *a3, a4, (__int64)a9, (*a3 & 0x200) != 0);
  TraceCustomServers(a10, a11);
  *(_QWORD *)&v56[1] = a13 + 16;
  *(_QWORD *)(a13 + 16) = 0;
  v17 = *a3;
  if ( (*a3 & 0x200) != 0 )
  {
    *(_QWORD *)(a13 + 24) = 0;
    *a3 |= 8uLL;
    v17 = *a3;
  }
  if ( (v17 & 0x100) != 0 )
  {
    v17 |= 0x68uLL;
    *a3 = v17;
  }
  if ( (v17 & 0x4000000) != 0 )
  {
    v17 |= 0x1000000uLL;
    *a3 = v17;
  }
  if ( (v17 & 0x2000000) != 0 )
  {
    v17 |= 8uLL;
    *a3 = v17;
  }
  if ( (v17 & 0x400) != 0 )
  {
    v17 |= 0x68uLL;
    *a3 = v17;
  }
  if ( (v17 & 0x40000) != 0 )
  {
    v17 |= 0x100000000000uLL;
    *a3 = v17;
  }
  v65 = a13 + 8;
  *(_QWORD *)(a13 + 8) = v17;
  v18 = DnsPinModule();
  DnsServerRRSet = v18;
  if ( v18 )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_d(1035, 73, WPP_df5265f5adb03ed46da236b8e39fbd95_Traceguids, v18);
    v28 = v16;
    goto LABEL_50;
  }
  v64 = *(_DWORD *)a7;
  if ( v64 || *((_QWORD *)a7 + 1) )
  {
    v70 = *a7;
    v59 = 0;
    if ( !(unsigned int)Rpc_ValidateCallbackInfo(&v70) )
    {
      DnsServerRRSet = 87;
      if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
      {
LABEL_69:
        v28 = a2;
LABEL_61:
        v25 = *(__int64 **)&v56[1];
        goto LABEL_62;
      }
      v42 = 74;
      v43 = v41;
LABEL_77:
      WPP_SF_d(v43, v42, WPP_df5265f5adb03ed46da236b8e39fbd95_Traceguids, 87);
      goto LABEL_69;
    }
  }
  else
  {
    v21 = 1;
    v59 = 1;
  }
  v22 = 0;
  v57 = 0;
  if ( a9 )
  {
    if ( *a9 == -2147483647 )
    {
      v44 = ExtraInfo_FindInList(a9, 12);
      if ( v44 )
      {
        v22 = *(_DWORD *)(v44 + 24);
        v57 = v22;
      }
    }
  }
  DnsEtwTraceQueryExStart((_DWORD)v15, (unsigned __int16)v16, *a3, v67, a5, a6, v22, v21 ^ 1);
  if ( !v22 )
    goto LABEL_21;
  v45 = BYTE1(xmmword_1801119E0);
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
  {
    WPP_SF_d(1035, 75, WPP_df5265f5adb03ed46da236b8e39fbd95_Traceguids, v22);
    v45 = BYTE1(xmmword_1801119E0);
  }
  if ( !v67 )
  {
LABEL_21:
    if ( !g_fVelocityDisableInternalExports )
      Reg_Init();
    if ( !v15 )
      goto LABEL_97;
    v23 = *v15;
    if ( (*(_DWORD *)a3 & 0x40000000) == 0
      && CompareStringW(0x409u, 1u, v15, -1, L"..DnsServers", -1) == 2
      && ((_WORD)v16 == 1 || v16 == 28)
      && (*(_DWORD *)a3 & 0x200LL) == 0 )
    {
      v25 = *(__int64 **)&v56[1];
      DnsServerRRSet = GetDnsServerRRSet(*(_QWORD *)&v56[1], (unsigned __int16)v16);
LABEL_91:
      v28 = v16;
LABEL_51:
      if ( DnsServerRRSet == 9506 )
      {
        if ( (Microsoft_Windows_DNS_ClientEnableBits & 4) != 0 )
        {
          v36 = v66;
          McTemplateU0z_EtwEventWriteTransfer(v19, DNS_QUERYEX_PENDING_EVENT, v66);
          goto LABEL_54;
        }
LABEL_53:
        v36 = v66;
LABEL_54:
        DnsApiFree(lpMem);
        DnsApiFree(v69[0]);
        v69[0] = 0;
        DnsApiFree(v36);
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          WPP_SF_d(1035, 96, WPP_df5265f5adb03ed46da236b8e39fbd95_Traceguids, DnsServerRRSet);
        return DnsServerRRSet;
      }
LABEL_62:
      v39 = v61;
      if ( v61 )
      {
        *(_DWORD *)(v61 + 4) = DnsServerRRSet;
        v39 = *v25;
      }
      DnsEtwTraceQueryExComplete((_DWORD)v15, v28, *a3, DnsServerRRSet, v39);
      goto LABEL_53;
    }
    if ( v23 )
    {
      RecordForIpString_W = Dns_CreateRecordForIpString_W(v15);
      v25 = *(__int64 **)&v56[1];
      if ( RecordForIpString_W )
      {
        **(_QWORD **)&v56[1] = RecordForIpString_W;
        DnsServerRRSet = 0;
        goto LABEL_94;
      }
      v26 = Query_CheckIp6Literal(v15, (unsigned __int16)v16, *(_QWORD *)&v56[1]);
      DnsServerRRSet = v26;
      if ( v26 )
      {
        if ( v26 == 9561 )
          DnsServerRRSet = 0;
        goto LABEL_91;
      }
    }
    else
    {
LABEL_97:
      HostName = (void *)Reg_GetHostName(1);
      v25 = *(__int64 **)&v56[1];
      lpMem = HostName;
      if ( !HostName )
      {
        DnsServerRRSet = 9701;
        goto LABEL_94;
      }
      v15 = (const WCHAR *)HostName;
    }
    if ( (*a3 & 0x4000) != 0 && v16 != 28 )
    {
      DnsServerRRSet = 87;
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      {
        v40 = 77;
LABEL_100:
        WPP_SF_d(1035, v40, WPP_df5265f5adb03ed46da236b8e39fbd95_Traceguids, 87);
        goto LABEL_34;
      }
      goto LABEL_34;
    }
    if ( g_fVelocityDisableInternalExports )
    {
      if ( !(unsigned int)Dns_IsServer() )
        goto LABEL_32;
      v47 = (*(_DWORD *)a3 & 0x10000000) == 0;
    }
    else
    {
      if ( !dword_1801116D4 )
      {
LABEL_32:
        v27 = *a3;
        if ( (*a3 & 0xC0000000000000LL) == 0xC0000000000000LL )
        {
          DnsServerRRSet = 87;
          if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          {
            v40 = 78;
            goto LABEL_100;
          }
LABEL_34:
          v28 = a2;
          goto LABEL_62;
        }
        if ( (v27 & 0x18) == 0x18 )
        {
          DnsServerRRSet = 87;
          if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
            goto LABEL_34;
          v40 = 79;
          goto LABEL_100;
        }
        if ( (v27 & 0x20) == 0 )
        {
          v38 = Query_CheckLocalQuery(v15, (__int64)v56, (__int64)v25);
          DnsServerRRSet = v38;
          if ( v56[0] )
          {
            if ( !v38 )
            {
              if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
                WPP_SF_(1035, 80, WPP_df5265f5adb03ed46da236b8e39fbd95_Traceguids);
              goto LABEL_91;
            }
          }
        }
        v29 = DnsValidateName_W(v15, DnsNameDomain);
        DnsServerRRSet = v29;
        if ( v29 && v29 != 9556 )
        {
          if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
            WPP_SF_S(1035, 81, WPP_df5265f5adb03ed46da236b8e39fbd95_Traceguids, v15);
          goto LABEL_91;
        }
        if ( !v67 )
        {
          v30 = a10;
          v31 = v58;
          goto LABEL_40;
        }
        if ( *(_DWORD *)(v67 + 4) && !v58 && !a10 )
        {
          v48 = ConvertAddrArrayToCustomServers(v67, 0, 0, (unsigned int)v71, (__int64)v69);
          DnsServerRRSet = v48;
          if ( v48 )
          {
            if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
              WPP_SF_d(1035, 82, WPP_df5265f5adb03ed46da236b8e39fbd95_Traceguids, v48);
            goto LABEL_91;
          }
          v31 = v69[0];
          v30 = v71[0];
          v58 = v69[0];
          a10 = v71[0];
LABEL_40:
          if ( (*(_BYTE *)a3 & 0x18) == 0x18 )
          {
            DnsServerRRSet = 87;
            if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
              goto LABEL_34;
            v40 = 83;
            goto LABEL_100;
          }
          if ( (*a3 & 0x10000000000000LL) != 0 )
          {
            DnsServerRRSet = 87;
            if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
              goto LABEL_34;
            v40 = 84;
            goto LABEL_100;
          }
          v56[0] = 0;
          if ( !v59 && (Microsoft_Windows_DNS_ClientEnableBits & 4) != 0 )
          {
            v49 = (void *)Dns_Allocate(512);
            v66 = v49;
            if ( !v49 )
            {
              DnsServerRRSet = 14;
              goto LABEL_34;
            }
            v71[1] = 512;
            if ( !(unsigned int)Dns_StringCopy(v49, 1, 1) )
            {
              DnsServerRRSet = 87;
              if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
                goto LABEL_34;
              v40 = 85;
              goto LABEL_100;
            }
          }
          CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
          v33 = g_fVelocityInprocDnsCleanup;
          v34 = CurrentThreadCompartmentId;
          if ( g_fVelocityInprocDnsCleanup )
          {
            if ( CurrentThreadCompartmentId != g_DefaultCompartmentId )
            {
              MicrosoftTelemetryAssertTriggeredNoArgs();
              v33 = g_fVelocityInprocDnsCleanup;
              if ( v34 != g_DefaultCompartmentId )
              {
                DnsServerRRSet = 87;
                if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
                  WPP_SF_Dd(1035, 86, WPP_df5265f5adb03ed46da236b8e39fbd95_Traceguids, 87, v34);
                goto LABEL_69;
              }
            }
          }
          else if ( CurrentThreadCompartmentId != g_DefaultCompartmentId )
          {
            v50 = BYTE1(xmmword_1801119E0);
            if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
            {
              WPP_SF_d(1035, 87, WPP_df5265f5adb03ed46da236b8e39fbd95_Traceguids, CurrentThreadCompartmentId);
              v50 = BYTE1(xmmword_1801119E0);
            }
            v28 = a2;
            goto LABEL_132;
          }
          v70 = *v60;
          if ( g_DnsIsCache )
          {
            v54 = (__int64)v31;
            v28 = a2;
            DnsServerRRSet = ResolverQueryInProc((_DWORD)v15, a2, v22, a5, a6, v34, v30, v54, a12);
            v51 = 0;
          }
          else
          {
            if ( v33 )
            {
              v35 = Rpc_ResolverQuery(v63, v15, a2, v65, v22, a5, a6, v34, &v70, 0, v30, v58, a12, v62, v61, v56);
              if ( !v35 )
              {
                DnsServerRRSet = v56[0];
LABEL_49:
                v28 = a2;
LABEL_50:
                v25 = *(__int64 **)&v56[1];
                goto LABEL_51;
              }
              if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
                WPP_SF_d(1035, 88, WPP_df5265f5adb03ed46da236b8e39fbd95_Traceguids, v35);
              v56[0] = StartDnsServiceOnDemand();
              DnsServerRRSet = v56[0];
              if ( v56[0] )
                goto LABEL_49;
              v70 = *v60;
              v52 = Rpc_ResolverQuery(v63, v15, a2, v65, v22, a5, a6, v34, &v70, 1, a10, v58, a12, v62, v61, v56);
              v51 = v52;
              if ( v52 )
              {
                if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
                  WPP_SF_d(1035, 89, WPP_df5265f5adb03ed46da236b8e39fbd95_Traceguids, v52);
                DnsServerRRSet = v51;
                goto LABEL_49;
              }
            }
            else
            {
              v51 = Rpc_ResolverQuery(v63, v15, a2, v65, v22, a5, a6, v34, &v70, 0, v30, v58, a12, v62, v61, v56);
              if ( v51 && !(unsigned int)StartDnsServiceOnDemand() )
              {
                v70 = *v60;
                v51 = Rpc_ResolverQuery(v63, v15, a2, v65, v57, a5, a6, v34, &v70, 1, a10, v58, a12, v62, v61, v56);
              }
            }
            v28 = a2;
            DnsServerRRSet = v56[0];
          }
          if ( g_fVelocityInprocDnsCleanup )
            goto LABEL_50;
          if ( v51 )
          {
            v50 = BYTE1(xmmword_1801119E0);
            if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
            {
LABEL_152:
              v22 = v57;
LABEL_132:
              if ( !dword_18011179C )
              {
                DnsServerRRSet = 87;
                if ( (v50 & 8) != 0 )
                  WPP_SF_d(1035, 92, WPP_df5265f5adb03ed46da236b8e39fbd95_Traceguids, 87);
                goto LABEL_61;
              }
              if ( (v50 & 8) != 0 )
              {
                WPP_SF_Sd(1035, 93, (unsigned int)WPP_df5265f5adb03ed46da236b8e39fbd95_Traceguids, (_DWORD)v15, a2);
                v50 = BYTE1(xmmword_1801119E0);
              }
              if ( !v69[0] && (a10 || v58) )
              {
                DnsServerRRSet = 87;
                if ( (v50 & 8) == 0 )
                  goto LABEL_69;
                v42 = 94;
              }
              else
              {
                if ( v59 || (v70 = *v60, (unsigned int)Rpc_ValidateCallbackInfo(&v70)) && v64 == 1 )
                {
                  v70 = *v60;
                  DnsServerRRSet = InProc_InitiateQuery(v63, v15, a2, v65, v67, v22, a5, a6, v34, &v70, v62, v61);
                  goto LABEL_49;
                }
                DnsServerRRSet = 87;
                if ( (v53 & 8) == 0 )
                  goto LABEL_69;
                v42 = 95;
              }
              v43 = 1035;
              goto LABEL_77;
            }
            WPP_SF_d(1035, 90, WPP_df5265f5adb03ed46da236b8e39fbd95_Traceguids, v51);
          }
          else
          {
            if ( DnsServerRRSet != 9851 )
              goto LABEL_50;
            v50 = BYTE1(xmmword_1801119E0);
            if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
              goto LABEL_152;
            WPP_SF_(1035, 91, WPP_df5265f5adb03ed46da236b8e39fbd95_Traceguids);
          }
          v50 = BYTE1(xmmword_1801119E0);
          goto LABEL_152;
        }
        DnsServerRRSet = 87;
LABEL_94:
        v28 = v16;
        goto LABEL_62;
      }
      v47 = (*a3 & 0x10000000) == 0;
    }
    if ( !v47 )
    {
      *(_QWORD *)&v70 = 0;
      DWORD2(v70) = 0;
      Dns_ReadDwordEnvar(v19, &v70);
      if ( DWORD2(v70) )
      {
        if ( DWORD1(v70) )
          *a3 &= ~0x10000000uLL;
      }
    }
    goto LABEL_32;
  }
  if ( (v45 & 8) != 0 )
    WPP_SF_(1035, 76, WPP_df5265f5adb03ed46da236b8e39fbd95_Traceguids);
  *(_DWORD *)(a13 + 4) = 0;
  return 87;
}

```

## disassembly

```asm
0x180013658  push    rbp
0x18001365a  push    rbx
0x18001365b  push    rsi
0x18001365c  push    rdi
0x18001365d  push    r12
0x18001365f  push    r13
0x180013661  push    r14
0x180013663  push    r15
0x180013665  lea     rbp, [rsp-28h]
0x18001366a  sub     rsp, 128h
0x180013671  mov     rax, cs:__security_cookie
0x180013678  xor     rax, rsp
0x18001367b  mov     [rbp+60h+var_48], rax
0x18001367f  mov     rax, [rbp+60h+arg_38]
0x180013686  mov     r12, r8
0x180013689  mov     r14, [rbp+60h+arg_30]
0x180013690  mov     r13, rcx
0x180013693  mov     rdi, [rbp+60h+arg_50]
0x18001369a  mov     r15, [rbp+60h+arg_60]
0x1800136a1  mov     rbx, [rbp+60h+arg_40]
0x1800136a8  mov     [rbp+60h+var_A8], rax
0x1800136ac  mov     rax, [rbp+60h+arg_68]
0x1800136b3  mov     [rbp+60h+var_A0], rax
0x1800136b7  xor     eax, eax
0x1800136b9  movzx   esi, dx
0x1800136bc  mov     [rbp+60h+lpMem], rax
0x1800136c0  mov     dword ptr [rbp+60h+var_DC], eax
0x1800136c3  mov     [rbp+60h+var_88], rax
0x1800136c7  mov     [rbp+60h+var_50], eax
0x1800136ca  mov     [rbp+60h+var_70], rax
0x1800136ce  mov     [rbp+60h+var_80], r9
0x1800136d2  mov     [rbp+60h+var_E0], si
0x1800136d6  mov     [rbp+60h+var_B8], r14
0x1800136da  mov     [rbp+60h+var_C8], rdi
0x1800136de  mov     [rbp+60h+var_B0], r15
0x1800136e2  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800136e9  jnz     loc_180013BBE
0x1800136ef  mov     ecx, [rbp+60h+arg_48]
0x1800136f5  mov     rdx, rdi
0x1800136f8  call    TraceCustomServers
0x1800136fd  lea     rax, [r15+10h]
0x180013701  mov     qword ptr [rbp+60h+var_DC+4], rax
0x180013705  mov     qword ptr [rax], 0
0x18001370c  mov     rax, [r12]
0x180013710  bt      rax, 9
0x180013715  jb      loc_180013BEF
0x18001371b  bt      rax, 8
0x180013720  jb      loc_180013C05
0x180013726  bt      rax, 1Ah
0x18001372b  jb      loc_180013C12
0x180013731  bt      rax, 19h
0x180013736  jb      loc_180013C20
0x18001373c  bt      rax, 0Ah
0x180013741  jb      loc_180013C2D
0x180013747  bt      rax, 12h
0x18001374c  jb      loc_180013C3A
0x180013752  lea     rcx, [r15+8]
0x180013756  mov     [rbp+60h+var_90], rcx
0x18001375a  mov     [rcx], rax
0x18001375d  call    DnsPinModule
0x180013762  mov     edi, eax
0x180013764  mov     r10d, 40Bh
0x18001376a  test    eax, eax
0x18001376c  jnz     loc_180014396
0x180013772  mov     eax, [r14]
0x180013775  mov     [rbp+60h+var_98], eax
0x180013778  test    eax, eax
0x18001377a  jnz     loc_180013C50
0x180013780  cmp     qword ptr [r14+8], 0
0x180013785  jnz     loc_180013C50
0x18001378b  lea     r9d, [rdi+1]
0x18001378f  mov     [rbp+60h+var_C0], r9d
0x180013793  xor     r14d, r14d
0x180013796  mov     [rbp+60h+var_D0], r14d
0x18001379a  test    rbx, rbx
0x18001379d  jnz     loc_180013CA9
0x1800137a3  xor     ebx, ebx
0x1800137a5  mov     eax, [rbp+60h+arg_28]
0x1800137ab  xor     r9d, 1
0x1800137af  mov     rdi, [rbp+60h+var_80]
0x1800137b3  movzx   edx, si
0x1800137b6  mov     r8, [r12]
0x1800137ba  mov     rcx, r13
0x1800137bd  mov     dword ptr [rsp+160h+var_128], r9d
0x1800137c2  mov     r9, rdi
0x1800137c5  mov     dword ptr [rsp+160h+var_130], r14d
0x1800137ca  mov     [rsp+160h+cchCount2], eax
0x1800137ce  mov     eax, [rbp+60h+arg_20]
0x1800137d4  mov     dword ptr [rsp+160h+lpString2], eax
0x1800137d8  call    DnsEtwTraceQueryExStart
0x1800137dd  test    r14d, r14d
0x1800137e0  jnz     loc_180013CDA
0x1800137e6  cmp     cs:g_fVelocityDisableInternalExports, ebx
0x1800137ec  jz      loc_1800138E3
0x1800137f2  test    r13, r13
0x1800137f5  jz      loc_180013DA6
0x1800137fb  movzx   ebx, word ptr [r13+0]
0x180013800  xor     eax, eax
0x180013802  movzx   ecx, ax
0x180013805  mov     eax, [r12]
0x180013809  sub     ebx, ecx
0x18001380b  bt      rax, 1Eh
0x180013810  jb      short loc_18001384A
0x180013812  or      r9d, 0FFFFFFFFh; cchCount1
0x180013816  lea     rax, aDnsservers_0; "..DnsServers"
0x18001381d  mov     [rsp+160h+cchCount2], r9d; cchCount2
0x180013822  mov     r8, r13; lpString1
0x180013825  mov     ecx, 409h; Locale
0x18001382a  mov     [rsp+160h+lpString2], rax; lpString2
0x18001382f  lea     edi, [r9+2]
0x180013833  mov     edx, edi; dwCmpFlags
0x180013835  call    cs:__imp_CompareStringW
0x18001383c  nop     dword ptr [rax+rax+00h]
0x180013841  cmp     eax, 2
0x180013844  jz      loc_180013D34
0x18001384a  test    ebx, ebx
0x18001384c  jz      loc_180013DA4
0x180013852  movzx   edx, si
0x180013855  mov     rcx, r13; AddressString
0x180013858  call    Dns_CreateRecordForIpString_W
0x18001385d  mov     r15, qword ptr [rbp+60h+var_DC+4]
0x180013861  xor     ebx, ebx
0x180013863  test    rax, rax
0x180013866  jnz     loc_180013D85
0x18001386c  mov     r8, r15
0x18001386f  movzx   edx, si
0x180013872  mov     rcx, r13
0x180013875  call    Query_CheckIp6Literal
0x18001387a  mov     edi, eax
0x18001387c  test    eax, eax
0x18001387e  jnz     loc_180013D99
0x180013884  lea     edi, [rbx+1]
0x180013887  test    qword ptr [r12], 4000h
0x18001388f  jnz     loc_180013B99
0x180013895  cmp     cs:g_fVelocityDisableInternalExports, ebx
0x18001389b  jnz     loc_180013DEC
0x1800138a1  cmp     cs:dword_1801116D4, ebx
0x1800138a7  jnz     loc_180013E05
0x1800138ad  mov     r8, [r12]
0x1800138b1  mov     rcx, 0C0000000000000h
0x1800138bb  mov     rax, r8
0x1800138be  and     rax, rcx
0x1800138c1  cmp     rax, rcx
0x1800138c4  jnz     short loc_1800138ED
0x1800138c6  mov     esi, 57h ; 'W'
0x1800138cb  mov     edi, esi
0x1800138cd  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800138d4  jnz     loc_180013E42
0x1800138da  movzx   ebx, [rbp+60h+var_E0]
0x1800138de  jmp     loc_180013B15
0x1800138e3  call    Reg_Init
0x1800138e8  jmp     loc_1800137F2
0x1800138ed  mov     al, r8b
0x1800138f0  and     al, 18h
0x1800138f2  cmp     al, 18h
0x1800138f4  jz      loc_180013E49
0x1800138fa  test    r8b, 20h
0x1800138fe  jz      loc_180013AAB
0x180013904  xor     edx, edx; Format
0x180013906  mov     rcx, r13; pszName
0x180013909  call    DnsValidateName_W
0x18001390e  mov     edi, eax
0x180013910  test    eax, eax
0x180013912  jnz     loc_180013E65
0x180013918  mov     rcx, [rbp+60h+var_80]
0x18001391c  test    rcx, rcx
0x18001391f  jnz     loc_180013E9B
0x180013925  mov     edi, [rbp+60h+arg_48]
0x18001392b  mov     rbx, [rbp+60h+var_C8]
0x18001392f  mov     al, [r12]
0x180013933  and     al, 18h
0x180013935  cmp     al, 18h
0x180013937  jz      loc_180013F00
0x18001393d  mov     rax, 10000000000000h
0x180013947  test    [r12], rax
0x18001394b  jnz     loc_18001437D
0x180013951  cmp     [rbp+60h+var_C0], 0
0x180013955  mov     dword ptr [rbp+60h+var_DC], 0
0x18001395c  jz      loc_180013F1C
0x180013962  call    cs:__imp_GetCurrentThreadCompartmentId
0x180013969  nop     dword ptr [rax+rax+00h]
0x18001396e  mov     ecx, cs:g_fVelocityInprocDnsCleanup
0x180013974  mov     esi, 57h ; 'W'
0x180013979  mov     r15d, eax
0x18001397c  test    ecx, ecx
0x18001397e  jnz     loc_180013B3E
0x180013984  cmp     eax, cs:g_DefaultCompartmentId
0x18001398a  jnz     loc_180013F93
0x180013990  cmp     cs:g_DnsIsCache, 0
0x180013997  mov     rax, [rbp+60h+var_B8]
0x18001399b  movaps  xmm0, xmmword ptr [rax]
0x18001399e  movdqa  [rbp+60h+var_60], xmm0
0x1800139a3  jnz     loc_180014004
0x1800139a9  movzx   ebx, [rbp+60h+arg_58]
0x1800139b0  lea     rax, [rbp+60h+var_DC]
0x1800139b4  mov     r9, [rbp+60h+var_90]
0x1800139b8  test    ecx, ecx
0x1800139ba  mov     rcx, [rbp+60h+var_A0]
0x1800139be  mov     rdx, r13
0x1800139c1  mov     [rsp+160h+var_E8], rax
0x1800139c6  mov     rax, [rbp+60h+var_B0]
0x1800139ca  mov     [rsp+160h+var_F0], rax
0x1800139cf  mov     rax, [rbp+60h+var_A8]
0x1800139d3  mov     [rsp+160h+var_F8], rax
0x1800139d8  mov     rax, [rbp+60h+var_C8]
0x1800139dc  mov     word ptr [rsp+160h+var_100], bx
0x1800139e1  mov     [rsp+160h+var_108], rax
0x1800139e6  lea     rax, [rbp+60h+var_60]
0x1800139ea  mov     dword ptr [rsp+160h+var_110], edi
0x1800139ee  mov     dword ptr [rsp+160h+var_118], 0
0x1800139f6  mov     [rsp+160h+var_120], rax
0x1800139fb  mov     eax, [rbp+60h+arg_28]
0x180013a01  mov     dword ptr [rsp+160h+var_128], r15d
0x180013a06  mov     dword ptr [rsp+160h+var_130], eax
0x180013a0a  mov     eax, [rbp+60h+arg_20]
0x180013a10  mov     [rsp+160h+cchCount2], eax
0x180013a14  mov     dword ptr [rsp+160h+lpString2], r14d
0x180013a19  jz      loc_180014159
0x180013a1f  movzx   r8d, [rbp+60h+var_E0]
0x180013a24  call    Rpc_ResolverQuery
0x180013a29  test    eax, eax
0x180013a2b  jnz     loc_18001406F
0x180013a31  mov     edi, dword ptr [rbp+60h+var_DC]
0x180013a34  movzx   ebx, [rbp+60h+var_E0]
0x180013a38  mov     r15, qword ptr [rbp+60h+var_DC+4]
0x180013a3c  cmp     edi, 2522h
0x180013a42  jnz     loc_180013B15
0x180013a48  test    byte ptr cs:Microsoft_Windows_DNS_ClientEnableBits, 4
0x180013a4f  jnz     loc_1800143C9
0x180013a55  mov     rbx, [rbp+60h+var_88]
0x180013a59  mov     rcx, [rbp+60h+lpMem]; lpMem
0x180013a5d  call    DnsApiFree
0x180013a62  mov     rcx, [rbp+60h+var_70]; lpMem
0x180013a66  call    DnsApiFree
0x180013a6b  mov     rcx, rbx; lpMem
0x180013a6e  mov     [rbp+60h+var_70], 0
0x180013a76  call    DnsApiFree
0x180013a7b  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180013a82  jnz     loc_1800143E1
0x180013a88  mov     eax, edi
0x180013a8a  mov     rcx, [rbp+60h+var_48]
0x180013a8e  xor     rcx, rsp; StackCookie
0x180013a91  call    __security_check_cookie
0x180013a96  add     rsp, 128h
0x180013a9d  pop     r15
0x180013a9f  pop     r14
0x180013aa1  pop     r13
0x180013aa3  pop     r12
0x180013aa5  pop     rdi
0x180013aa6  pop     rsi
0x180013aa7  pop     rbx
0x180013aa8  pop     rbp
0x180013aa9  retn
0x180013aab  mov     r9, r8
0x180013aae  mov     qword ptr [rsp+160h+cchCount2], r15; __int64
0x180013ab3  shr     r9, 1Ch
0x180013ab7  lea     rax, [rbp+60h+var_DC]
0x180013abb  not     r9d
0x180013abe  shr     r8, 0Eh
0x180013ac2  and     r9d, edi
0x180013ac5  mov     [rsp+160h+lpString2], rax; __int64
0x180013aca  and     r8d, edi
0x180013acd  movzx   edx, si
0x180013ad0  mov     rcx, r13; lpString1
0x180013ad3  call    Query_CheckLocalQuery
0x180013ad8  mov     edi, eax
0x180013ada  cmp     dword ptr [rbp+60h+var_DC], ebx
0x180013add  jz      loc_180013904
0x180013ae3  test    eax, eax
0x180013ae5  jnz     loc_180013904
0x180013aeb  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180013af2  jz      loc_180013D7D
0x180013af8  lea     edx, [rax+50h]
0x180013afb  mov     ecx, 40Bh
0x180013b00  lea     r8, WPP_df5265f5adb03ed46da236b8e39fbd95_Traceguids
0x180013b07  call    WPP_SF_
0x180013b0c  jmp     loc_180013D7D
0x180013b11  mov     r15, qword ptr [rbp+60h+var_DC+4]
0x180013b15  mov     rax, [rbp+60h+var_B0]
0x180013b19  test    rax, rax
0x180013b1c  jnz     loc_1800143BE
0x180013b22  mov     r8, [r12]
0x180013b26  mov     r9d, edi
0x180013b29  movzx   edx, bx
0x180013b2c  mov     rcx, r13
0x180013b2f  mov     [rsp+160h+lpString2], rax
0x180013b34  call    DnsEtwTraceQueryExComplete
0x180013b39  jmp     loc_180013A55
0x180013b3e  mov     eax, cs:g_DefaultCompartmentId
0x180013b44  cmp     r15d, eax
0x180013b47  jz      loc_180013990
0x180013b4d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180013b52  mov     eax, cs:g_DefaultCompartmentId
0x180013b58  mov     ecx, cs:g_fVelocityInprocDnsCleanup
0x180013b5e  cmp     r15d, eax
0x180013b61  jz      loc_180013990
0x180013b67  mov     edi, esi
0x180013b69  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180013b70  jz      short loc_180013B90
0x180013b72  mov     edx, 56h ; 'V'
  ... truncated ...
```

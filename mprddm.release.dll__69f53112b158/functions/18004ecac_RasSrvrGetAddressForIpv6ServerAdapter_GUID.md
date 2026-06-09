# RasSrvrGetAddressForIpv6ServerAdapter(_GUID)

- ea: `0x18004ecac`
- end: `0x18004f4c5`
- name: `?RasSrvrGetAddressForIpv6ServerAdapter@@YAKU_GUID@@@Z`
- size: `2073`
- prototype: `unsigned int __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800540f0`

## callees

- `0x180027ec0`
- `0x18004ecac`
- `0x18004f8c4`
- `0x180054544`
- `0x180057520`
- `0x18005a844`
- `0x18005aa44`
- `0x18005aa98`
- `0x18005aaf8`
- `0x18005ab2c`
- `0x18005ad18`
- `0x18005adcc`
- `0x18005af78`
- `0x18005c360`
- `0x18005d770`
- `0x1800755b8`
- `0x1800785b8`
- `0x1800796f8`
- `0x18007eff4`
- `0x18007f074`
- `0x18007f1c8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18004ee6a`
- `msvcrt!memcpy_s` at `0x18004ee6a`
- `KERNEL32!DeviceIoControl` at `0x18004eede`
- `KERNEL32!DeviceIoControl` at `0x18004eede`
- `KERNEL32!GetLastError` at `0x18004eeee`
- `KERNEL32!GetLastError` at `0x18004eeee`
- `KERNEL32!LeaveCriticalSection` at `0x18004f486`
- `KERNEL32!LeaveCriticalSection` at `0x18004f486`
- `KERNEL32!EnterCriticalSection` at `0x18004edbb`
- `KERNEL32!EnterCriticalSection` at `0x18004edbb`
- `ntdll!RtlIpv6AddressToStringA` at `0x18004f0df`
- `ntdll!RtlIpv6AddressToStringA` at `0x18004f0df`

## string_xrefs

- `0x18004f27f`: `AddOrRemoveIpv6Prefix completes with 0x%x`
- `0x18004f226`: `SetIpv6InterfaceProperties completes with 0x%x`
- `0x18004ee13`: `Error %d in finding compartment for routing domain`
- `0x18004ef0e`: `Error %d mapping IPv6 server adapter for compartment %d`
- `0x18004ef39`: `RasSrvrIpv6AdapterMapped: Interface Index: %d  compartment: %d`

## pseudocode

```c
__int64 __fastcall RasSrvrGetAddressForIpv6ServerAdapter(struct _GUID *a1)
{
  __int64 v1; // r15
  unsigned int v3; // ebx
  int v4; // r13d
  __int64 NboServerIpv6Address; // rax
  unsigned int v6; // r12d
  unsigned __int64 v7; // r14
  unsigned int RoutingDomainConfigData; // eax
  DWORD LastError; // eax
  unsigned int RoutingDomainAddressPool; // ebx
  BOOL v11; // esi
  int v12; // ecx
  int v13; // edx
  int v14; // r8d
  int v15; // r9d
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  int lpOutBuffer; // [rsp+28h] [rbp-E0h]
  int v22; // [rsp+48h] [rbp-C0h] BYREF
  unsigned int v23; // [rsp+50h] [rbp-B8h] BYREF
  unsigned int v24; // [rsp+54h] [rbp-B4h] BYREF
  DWORD OutBuffer; // [rsp+58h] [rbp-B0h] BYREF
  __int128 OutBuffer_8; // [rsp+60h] [rbp-A8h] BYREF
  int v27; // [rsp+70h] [rbp-98h]
  _BYTE v28[24]; // [rsp+78h] [rbp-90h] BYREF
  struct _GUID v29; // [rsp+98h] [rbp-70h]
  __int128 v30; // [rsp+A8h] [rbp-60h]
  struct in6_addr v31; // [rsp+B8h] [rbp-50h] BYREF
  int v32; // [rsp+C8h] [rbp-40h]
  struct _GUID v33; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v34; // [rsp+E8h] [rbp-20h]
  struct in6_addr v35; // [rsp+F8h] [rbp-10h]
  int v36; // [rsp+108h] [rbp+0h]
  __int64 Source; // [rsp+118h] [rbp+10h] BYREF
  struct in6_addr Addr; // [rsp+120h] [rbp+18h] BYREF
  int v39; // [rsp+138h] [rbp+30h] BYREF
  _BYTE v40[2044]; // [rsp+13Ch] [rbp+34h] BYREF
  CHAR S[128]; // [rsp+938h] [rbp+830h] BYREF

  v1 = 0;
  v27 = 0;
  OutBuffer = 0;
  *(_QWORD *)v28 = 0;
  v3 = 0;
  v24 = 1;
  OutBuffer_8 = 0;
  v4 = 0;
  Addr = 0;
  NboServerIpv6Address = RasRdGetNboServerIpv6Address(&v33, a1);
  v23 = 0;
  v22 = 4;
  v29 = *(struct _GUID *)NboServerIpv6Address;
  v30 = *(_OWORD *)(NboServerIpv6Address + 16);
  v31 = *(struct in6_addr *)(NboServerIpv6Address + 32);
  v32 = *(_DWORD *)(NboServerIpv6Address + 48);
  RasRoutingDomainGetConfigParam(a1, 8, &v22, &v23);
  v6 = v23;
  LODWORD(v7) = RasRdGetServerAdapterLuidIndex(a1);
  Source = RasRdGetServerAdapterIPv6IfId(a1);
  v39 = 0;
  memset_0(v40, 0, sizeof(v40));
  if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800D0740 + 1),
      L"Entering RasSrvrGetAddressForIpv6ServerAdapter");
  EnterCriticalSection(&RasSrvrCriticalSection);
  if ( *(_QWORD *)&a1->Data1 != *(_QWORD *)&GUID_NULL.Data1 || *(_QWORD *)a1->Data4 != *(_QWORD *)GUID_NULL.Data4 )
  {
    RoutingDomainConfigData = GetRoutingDomainConfigData(a1, 256, 4, &v24);
    v3 = RoutingDomainConfigData;
    if ( RoutingDomainConfigData )
    {
      if ( (_QWORD)xmmword_1800D0740 )
      {
        LOWORD(v39) = 0;
        FormatRRASErrorString(&v39, L"Error %d in finding compartment for routing domain", RoutingDomainConfigData);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v39);
      }
      goto LABEL_51;
    }
  }
  DWORD2(OutBuffer_8) = v24;
  *(_QWORD *)&OutBuffer_8 = 0xFFFFFFFF00000001uLL;
  memcpy_s((char *)&OutBuffer_8 + 12, 8u, &Source, 8u);
  v23 = 0;
  v22 = 4;
  RasRoutingDomainGetConfigParam(a1, 5, &v22, &v23);
  if ( v23 )
    goto LABEL_15;
  *(_QWORD *)&v33.Data1 = 0;
  if ( DeviceIoControl(HelperWanArpv6Handle, 0x90018014, &OutBuffer_8, 0x14u, &OutBuffer_8, 0x14u, &OutBuffer, 0) )
  {
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v39) = 0;
      FormatRRASErrorString(
        &v39,
        L"RasSrvrIpv6AdapterMapped: Interface Index: %d  compartment: %d",
        DWORD1(OutBuffer_8),
        DWORD2(OutBuffer_8));
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v39);
    }
    NsiConvertInterfaceIndexToLuid((char *)&OutBuffer_8 + 4, &v33);
    v7 = (*(_QWORD *)&v33.Data1 >> 24) & 0xFFFFFFLL;
    v22 = (*(_QWORD *)&v33.Data1 >> 24) & 0xFFFFFF;
    RasRoutingDomainSetConfigParam(a1, 7, 4, &v22);
    v6 = DWORD1(OutBuffer_8);
    v22 = DWORD1(OutBuffer_8);
    RasRoutingDomainSetConfigParam(a1, 8, 4, &v22);
    v22 = 1;
    RasRoutingDomainSetConfigParam(a1, 5, 4, &v22);
LABEL_15:
    if ( v31.u.Word[0] )
      goto LABEL_45;
    if ( __PAIR32__(v31.u.Word[1], 0) != v31.u.Word[2] )
      goto LABEL_45;
    if ( __PAIR32__(v31.u.Word[3], 0) != v31.u.Word[4] )
      goto LABEL_45;
    if ( __PAIR32__(v31.u.Word[5], 0) != v31.u.Word[6] )
      goto LABEL_45;
    if ( v31.u.Word[7] )
      goto LABEL_45;
    v33 = *a1;
    v3 = RasSrvrAcquireIpv6AddressForServer((void *)0xEE170466LL);
    if ( v3 )
      goto LABEL_45;
    v33 = *a1;
    RoutingDomainAddressPool = RasGetRoutingDomainAddressPool(&v33, 2, v28);
    v33 = v29;
    v11 = RoutingDomainAddressPool == 0;
    v31 = Addr;
    v4 = 1;
    v36 = v32;
    v34 = v30;
    v35 = Addr;
    RasRdSetNboServerIpv6Address(a1, &v33);
    if ( RoutingDomainAddressPool || (v1 = *(_QWORD *)v28) == 0 )
    {
      if ( (_QWORD)xmmword_1800D0740 != v1 )
      {
        LOWORD(v39) = v1;
        FormatRRASErrorString(&v39, L"Failed to get the pool for inserting VPN address %d", RoutingDomainAddressPool);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v39);
      }
      v3 = 717;
    }
    else
    {
      **(_QWORD **)v28 = *(_QWORD *)v31.u.Byte;
      RtlIpv6AddressToStringA(&Addr, S);
      if ( (_QWORD)xmmword_1800D0740 )
      {
        LOWORD(v39) = 0;
        FormatRRASErrorString(&v39, L"Acquired IPv6 address %hs for Server", S);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v39);
      }
      *(_QWORD *)&v34 = 128;
      DWORD2(v34) = 0;
      *(_QWORD *)v28 = (v7 & 0xFFFFFF | 0x17000000) << 24;
      v33 = (struct _GUID)0xFFFFFFFFFFFFFFFFuLL;
      *(struct in6_addr *)&v28[8] = v31;
      v3 = SetAllParameters(v12, (unsigned int)&NPI_MS_IPV6_MODULEID, 10, (unsigned int)v28, 24, (__int64)&v33, 28, 2);
      if ( v3 )
      {
        v1 = 0;
        if ( (_QWORD)xmmword_1800D0740 )
        {
          LOWORD(v39) = 0;
          FormatRRASErrorString(&v39, L"SetIPv6AddressOnInterface failed and returned %d", v3);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800D0740,
            &v39);
        }
      }
      else
      {
        LOBYTE(v14) = 1;
        LOBYTE(v13) = 1;
        LOBYTE(v15) = dword_1800D0938 != 0;
        v3 = 0;
        v16 = SetIpv6InterfaceProperties(v6, v13, v14, v15, lpOutBuffer, 1);
        if ( (_QWORD)xmmword_1800D0740 )
        {
          LOWORD(v39) = 0;
          FormatRRASErrorString(&v39, L"SetIpv6InterfaceProperties completes with 0x%x", v16);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800D0740,
            &v39);
        }
        v17 = AddOrRemoveIpv6PrefixForAdvertisement(v1, v6, 0, 256);
        v1 = 0;
        if ( (_QWORD)xmmword_1800D0740 )
        {
          LOWORD(v39) = 0;
          FormatRRASErrorString(&v39, L"AddOrRemoveIpv6Prefix completes with 0x%x", v17);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800D0740,
            &v39);
        }
        *(struct _GUID *)v28 = *a1;
        v18 = RasReleaseRoutingDomainAddressPool(v28);
        if ( v18 )
        {
          if ( (_QWORD)xmmword_1800D0740 )
          {
            LOWORD(v39) = 0;
            FormatRRASErrorString(
              &v39,
              L"RasReleaseRoutingDomainAddressPool failed to release lock and returned %d",
              v18);
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
              gRasIpAddrMgmtEtwContext,
              xmmword_1800D0740,
              &v39);
          }
        }
        else
        {
          v11 = 0;
        }
        *(struct _GUID *)v28 = *a1;
        RasSrvrInterfaceIdInsert(v28, &Source);
        RasSrvrSetProxyArpV6(&v31, 1, &v31, v24, a1);
      }
    }
    if ( !v11 )
      goto LABEL_45;
    *(struct _GUID *)v28 = *a1;
    v19 = RasReleaseRoutingDomainAddressPool(v28);
    if ( !v19 || (_QWORD)xmmword_1800D0740 == v1 )
      goto LABEL_45;
    LOWORD(v39) = v1;
    FormatRRASErrorString(&v39, L"RasReleaseRoutingDomainAddressPool failed to release lock and returned %d", v19);
    goto LABEL_44;
  }
  LastError = GetLastError();
  v3 = LastError;
  if ( (_QWORD)xmmword_1800D0740 )
  {
    LOWORD(v39) = 0;
    FormatRRASErrorString(
      &v39,
      L"Error %d mapping IPv6 server adapter for compartment %d",
      LastError,
      DWORD2(OutBuffer_8));
LABEL_44:
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800D0740,
      &v39);
  }
LABEL_45:
  if ( !v3 )
    goto LABEL_52;
  if ( v4 )
  {
    if ( dword_1800D08DC )
    {
      RasDhcpReleaseIpv6Prefix(&Addr);
    }
    else
    {
      *(struct _GUID *)v28 = *a1;
      RasStatReleaseIpv6Prefix(v28, &Addr);
    }
    RasSrvrSetProxyArpV6(&v31, 0, &v31, v24, a1);
  }
LABEL_51:
  ResetIpv6AddressOnInterface((unsigned int)v7, &v31);
  v31.u.Byte[0] = 0;
LABEL_52:
  if ( (_QWORD)xmmword_1800D0740 )
  {
    LOWORD(v39) = 0;
    FormatRRASErrorString(&v39, L"RasSrvrGetAddressForIpv6ServerAdapter: done %d", v3);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800D0740,
      &v39);
  }
  LeaveCriticalSection(&RasSrvrCriticalSection);
  return v3;
}

```

## disassembly

```asm
0x18004ecac  mov     rax, rsp
0x18004ecaf  mov     [rax+10h], rbx
0x18004ecb3  mov     [rax+18h], rsi
0x18004ecb7  mov     [rax+20h], rdi
0x18004ecbb  push    rbp
0x18004ecbc  push    r12
0x18004ecbe  push    r13
0x18004ecc0  push    r14
0x18004ecc2  push    r15
0x18004ecc4  lea     rbp, [rax-8E8h]
0x18004eccb  sub     rsp, 9C0h
0x18004ecd2  mov     rax, cs:__security_cookie
0x18004ecd9  xor     rax, rsp
0x18004ecdc  mov     [rbp+8E0h+var_30], rax
0x18004ece3  xor     r15d, r15d
0x18004ece6  xor     eax, eax
0x18004ece8  xorps   xmm0, xmm0
0x18004eceb  mov     dword ptr [rsp+9E0h+var_978], eax
0x18004ecef  mov     rdi, rcx
0x18004ecf2  mov     dword ptr [rsp+9E0h+OutBuffer], r15d
0x18004ecf7  mov     rdx, rcx
0x18004ecfa  mov     qword ptr [rsp+9E0h+var_978+8], r15
0x18004ecff  lea     esi, [rax+1]
0x18004ed02  mov     ebx, r15d
0x18004ed05  lea     rcx, [rbp+8E0h+var_910]
0x18004ed09  mov     [rsp+9E0h+var_994], esi
0x18004ed0d  movups  [rsp+9E0h+OutBuffer+8], xmm0
0x18004ed12  mov     r13d, r15d
0x18004ed15  movups  xmmword ptr [rbp+8E0h+Addr.u], xmm0
0x18004ed19  call    RasRdGetNboServerIpv6Address
0x18004ed1e  lea     r9, [rsp+9E0h+var_998]
0x18004ed23  mov     [rsp+9E0h+var_998], r15d
0x18004ed28  lea     r8, [rsp+9E0h+var_9A0]
0x18004ed2d  mov     [rsp+9E0h+var_9A0], 4
0x18004ed35  lea     edx, [rsi+7]
0x18004ed38  mov     rcx, rdi
0x18004ed3b  movups  xmm0, xmmword ptr [rax]
0x18004ed3e  movups  [rbp+8E0h+var_950], xmm0
0x18004ed42  movups  xmm1, xmmword ptr [rax+10h]
0x18004ed46  movups  [rbp+8E0h+var_940], xmm1
0x18004ed4a  movups  xmm0, xmmword ptr [rax+20h]
0x18004ed4e  movups  xmmword ptr [rbp+8E0h+var_930.u], xmm0
0x18004ed52  mov     eax, [rax+30h]
0x18004ed55  mov     [rbp+8E0h+var_920], eax
0x18004ed58  call    RasRoutingDomainGetConfigParam
0x18004ed5d  mov     r12d, [rsp+9E0h+var_998]
0x18004ed62  mov     rcx, rdi
0x18004ed65  call    RasRdGetServerAdapterLuidIndex
0x18004ed6a  mov     rcx, rdi
0x18004ed6d  mov     r14d, eax
0x18004ed70  call    RasRdGetServerAdapterIPv6IfId
0x18004ed75  xor     edx, edx; Val
0x18004ed77  mov     [rbp+8E0h+Source], rax
0x18004ed7b  mov     r8d, 7FCh; Size
0x18004ed81  mov     [rbp+8E0h+var_8B0], r15d
0x18004ed85  lea     rcx, [rbp+8E0h+var_8AC]; void *
0x18004ed89  call    memset_0
0x18004ed8e  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x18004ed95  test    rdx, rdx
0x18004ed98  jz      short loc_18004EDB4
0x18004ed9a  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004eda1  lea     r8, aEnteringRassrv; "Entering RasSrvrGetAddressForIpv6Server"...
0x18004eda8  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004edaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004edb4  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004edbb  call    cs:__imp_EnterCriticalSection
0x18004edc2  nop     dword ptr [rax+rax+00h]
0x18004edc7  mov     rax, [rdi]
0x18004edca  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18004edd1  jnz     short loc_18004EDE0
0x18004edd3  mov     rax, [rdi+8]
0x18004edd7  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18004edde  jz      short loc_18004EE46
0x18004ede0  lea     r9, [rsp+9E0h+var_994]
0x18004ede5  mov     edx, 100h
0x18004edea  mov     r8d, 4
0x18004edf0  mov     rcx, rdi
0x18004edf3  call    GetRoutingDomainConfigData
0x18004edf8  mov     ebx, eax
0x18004edfa  test    eax, eax
0x18004edfc  jz      short loc_18004EE46
0x18004edfe  cmp     qword ptr cs:xmmword_1800D0740, r15
0x18004ee05  jz      loc_18004F42B
0x18004ee0b  mov     r8d, eax
0x18004ee0e  mov     word ptr [rbp+8E0h+var_8B0], r15w
0x18004ee13  lea     rdx, aErrorDInFindin; "Error %d in finding compartment for rou"...
0x18004ee1a  lea     rcx, [rbp+8E0h+var_8B0]
0x18004ee1e  call    FormatRRASErrorString
0x18004ee23  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18004ee2a  lea     r8, [rbp+8E0h+var_8B0]
0x18004ee2e  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004ee35  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004ee3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee41  jmp     loc_18004F42B
0x18004ee46  mov     eax, [rsp+9E0h+var_994]
0x18004ee4a  lea     r8, [rbp+8E0h+Source]; Source
0x18004ee4e  or      dword ptr [rsp+9E0h+OutBuffer+0Ch], 0FFFFFFFFh
0x18004ee53  lea     rcx, [rsp+9E0h+Destination]; Destination
0x18004ee58  mov     [rsp+9E0h+var_980], eax
0x18004ee5c  mov     eax, 8
0x18004ee61  mov     r9d, eax; SourceSize
0x18004ee64  mov     dword ptr [rsp+9E0h+OutBuffer+8], esi
0x18004ee68  mov     edx, eax; DestinationSize
0x18004ee6a  call    cs:__imp_memcpy_s
0x18004ee71  nop     dword ptr [rax+rax+00h]
0x18004ee76  lea     r9, [rsp+9E0h+var_998]
0x18004ee7b  mov     [rsp+9E0h+var_998], r15d
0x18004ee80  lea     r8, [rsp+9E0h+var_9A0]
0x18004ee85  mov     [rsp+9E0h+var_9A0], 4
0x18004ee8d  mov     edx, 5
0x18004ee92  mov     rcx, rdi
0x18004ee95  call    RasRoutingDomainGetConfigParam
0x18004ee9a  cmp     [rsp+9E0h+var_998], r15d
0x18004ee9f  jnz     loc_18004EFE3
0x18004eea5  mov     rcx, cs:?HelperWanArpv6Handle@@3PEAXEA; hDevice
0x18004eeac  lea     rax, [rsp+9E0h+OutBuffer]
0x18004eeb1  mov     [rsp+9E0h+lpOverlapped], r15; lpOverlapped
0x18004eeb6  lea     r8, [rsp+9E0h+OutBuffer+8]; lpInBuffer
0x18004eebb  mov     [rsp+9E0h+lpBytesReturned], rax; lpBytesReturned
0x18004eec0  mov     r9d, 14h; nInBufferSize
0x18004eec6  lea     rax, [rsp+9E0h+OutBuffer+8]
0x18004eecb  mov     [rsp+9E0h+nOutBufferSize], r9d; nOutBufferSize
0x18004eed0  mov     edx, 90018014h; dwIoControlCode
0x18004eed5  mov     [rsp+9E0h+lpOutBuffer], rax; lpOutBuffer
0x18004eeda  mov     qword ptr [rbp+8E0h+var_910], r15
0x18004eede  call    cs:__imp_DeviceIoControl
0x18004eee5  nop     dword ptr [rax+rax+00h]
0x18004eeea  test    eax, eax
0x18004eeec  jnz     short loc_18004EF2B
0x18004eeee  call    cs:__imp_GetLastError
0x18004eef5  nop     dword ptr [rax+rax+00h]
0x18004eefa  cmp     qword ptr cs:xmmword_1800D0740, r15
0x18004ef01  mov     ebx, eax
0x18004ef03  jz      loc_18004F3DA
0x18004ef09  mov     r9d, [rsp+9E0h+var_980]
0x18004ef0e  lea     rdx, aErrorDMappingI; "Error %d mapping IPv6 server adapter fo"...
0x18004ef15  mov     r8d, eax
0x18004ef18  mov     word ptr [rbp+8E0h+var_8B0], r15w
0x18004ef1d  lea     rcx, [rbp+8E0h+var_8B0]
0x18004ef21  call    FormatRRASErrorString
0x18004ef26  jmp     loc_18004F3BC
0x18004ef2b  cmp     qword ptr cs:xmmword_1800D0740, r15
0x18004ef32  jz      short loc_18004EF71
0x18004ef34  mov     r9d, [rsp+9E0h+var_980]
0x18004ef39  lea     rdx, aRassrvripv6ada; "RasSrvrIpv6AdapterMapped: Interface Ind"...
0x18004ef40  mov     r8d, dword ptr [rsp+9E0h+OutBuffer+0Ch]
0x18004ef45  lea     rcx, [rbp+8E0h+var_8B0]
0x18004ef49  mov     word ptr [rbp+8E0h+var_8B0], r15w
0x18004ef4e  call    FormatRRASErrorString
0x18004ef53  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18004ef5a  lea     r8, [rbp+8E0h+var_8B0]
0x18004ef5e  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004ef65  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004ef6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ef71  lea     rdx, [rbp+8E0h+var_910]
0x18004ef75  lea     rcx, [rsp+9E0h+OutBuffer+0Ch]
0x18004ef7a  call    NsiConvertInterfaceIndexToLuid
0x18004ef7f  mov     r14, qword ptr [rbp+8E0h+var_910]
0x18004ef83  lea     r9, [rsp+9E0h+var_9A0]
0x18004ef88  mov     edx, 7
0x18004ef8d  shr     r14, 18h
0x18004ef91  and     r14d, 0FFFFFFh
0x18004ef98  mov     rcx, rdi
0x18004ef9b  mov     [rsp+9E0h+var_9A0], r14d
0x18004efa0  lea     r8d, [rdx-3]
0x18004efa4  call    RasRoutingDomainSetConfigParam
0x18004efa9  mov     r12d, dword ptr [rsp+9E0h+OutBuffer+0Ch]
0x18004efae  lea     r9, [rsp+9E0h+var_9A0]
0x18004efb3  mov     edx, 8
0x18004efb8  mov     [rsp+9E0h+var_9A0], r12d
0x18004efbd  mov     rcx, rdi
0x18004efc0  lea     r8d, [rdx-4]
0x18004efc4  call    RasRoutingDomainSetConfigParam
0x18004efc9  mov     edx, 5
0x18004efce  mov     [rsp+9E0h+var_9A0], esi
0x18004efd2  lea     r9, [rsp+9E0h+var_9A0]
0x18004efd7  mov     rcx, rdi
0x18004efda  lea     r8d, [rdx-1]
0x18004efde  call    RasRoutingDomainSetConfigParam
0x18004efe3  cmp     word ptr [rbp+8E0h+var_930.u], r15w
0x18004efe8  jnz     loc_18004F3DA
0x18004efee  cmp     word ptr [rbp+8E0h+var_930.u+2], r15w
0x18004eff3  jnz     loc_18004F3DA
0x18004eff9  cmp     word ptr [rbp+8E0h+var_930.u+4], r15w
0x18004effe  jnz     loc_18004F3DA
0x18004f004  cmp     word ptr [rbp+8E0h+var_930.u+6], r15w
0x18004f009  jnz     loc_18004F3DA
0x18004f00f  cmp     word ptr [rbp+8E0h+var_930.u+8], r15w
0x18004f014  jnz     loc_18004F3DA
0x18004f01a  cmp     word ptr [rbp+8E0h+var_930.u+0Ah], r15w
0x18004f01f  jnz     loc_18004F3DA
0x18004f025  cmp     word ptr [rbp+8E0h+var_930.u+0Ch], r15w
0x18004f02a  jnz     loc_18004F3DA
0x18004f030  cmp     word ptr [rbp+8E0h+var_930.u+0Eh], r15w
0x18004f035  jnz     loc_18004F3DA
0x18004f03b  movaps  xmm0, xmmword ptr [rdi]
0x18004f03e  lea     r8, [rbp+8E0h+Addr]
0x18004f042  lea     rdx, [rbp+8E0h+var_910]
0x18004f046  movdqa  [rbp+8E0h+var_910], xmm0
0x18004f04b  mov     ecx, 0EE170466h; void *
0x18004f050  call    RasSrvrAcquireIpv6AddressForServer
0x18004f055  mov     ebx, eax
0x18004f057  test    eax, eax
0x18004f059  jnz     loc_18004F3DA
0x18004f05f  movaps  xmm0, xmmword ptr [rdi]
0x18004f062  lea     r8, [rsp+9E0h+var_978+8]
0x18004f067  lea     edx, [rax+2]
0x18004f06a  movdqa  [rbp+8E0h+var_910], xmm0
0x18004f06f  lea     rcx, [rbp+8E0h+var_910]
0x18004f073  call    RasGetRoutingDomainAddressPool
0x18004f078  movups  xmm2, xmmword ptr [rbp+8E0h+Addr.u]
0x18004f07c  test    eax, eax
0x18004f07e  mov     ebx, eax
0x18004f080  movups  xmm0, [rbp+8E0h+var_950]
0x18004f084  mov     eax, [rbp+8E0h+var_920]
0x18004f087  mov     esi, r15d
0x18004f08a  movups  xmm1, [rbp+8E0h+var_940]
0x18004f08e  lea     rdx, [rbp+8E0h+var_910]
0x18004f092  mov     rcx, rdi
0x18004f095  movaps  [rbp+8E0h+var_910], xmm0
0x18004f099  setz    sil
0x18004f09d  movups  xmmword ptr [rbp+8E0h+var_930.u], xmm2
0x18004f0a1  mov     r13d, 1
0x18004f0a7  mov     [rbp+8E0h+var_8E0], eax
0x18004f0aa  movaps  [rbp+8E0h+var_900], xmm1
0x18004f0ae  movaps  [rbp+8E0h+var_8F0], xmm2
0x18004f0b2  call    RasRdSetNboServerIpv6Address
0x18004f0b7  test    ebx, ebx
0x18004f0b9  jnz     loc_18004F33B
0x18004f0bf  mov     r15, qword ptr [rsp+9E0h+var_978+8]
0x18004f0c4  test    r15, r15
0x18004f0c7  jz      loc_18004F33B
0x18004f0cd  mov     rax, qword ptr [rbp+8E0h+var_930.u]
0x18004f0d1  lea     rdx, [rbp+8E0h+S]; S
0x18004f0d8  lea     rcx, [rbp+8E0h+Addr]; Addr
0x18004f0dc  mov     [r15], rax
0x18004f0df  call    cs:__imp_RtlIpv6AddressToStringA
0x18004f0e6  nop     dword ptr [rax+rax+00h]
0x18004f0eb  xor     eax, eax
0x18004f0ed  cmp     qword ptr cs:xmmword_1800D0740, rax
0x18004f0f4  jz      short loc_18004F12F
0x18004f0f6  lea     r8, [rbp+8E0h+S]
0x18004f0fd  mov     word ptr [rbp+8E0h+var_8B0], ax
0x18004f101  lea     rdx, aAcquiredIpv6Ad; "Acquired IPv6 address %hs for Server"
0x18004f108  lea     rcx, [rbp+8E0h+var_8B0]
0x18004f10c  call    FormatRRASErrorString
0x18004f111  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18004f118  lea     r8, [rbp+8E0h+var_8B0]
0x18004f11c  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004f123  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004f12a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f12f  xor     eax, eax
0x18004f131  mov     dword ptr [rsp+9E0h+lpOverlapped], 2
0x18004f139  mov     qword ptr [rbp+8E0h+var_900], rax
0x18004f13d  lea     r9, [rsp+9E0h+var_978+8]
0x18004f142  mov     dword ptr [rbp+8E0h+var_900+8], eax
0x18004f145  lea     rdx, NPI_MS_IPV6_MODULEID
0x18004f14c  xorps   xmm0, xmm0
0x18004f14f  mov     dword ptr [rsp+9E0h+lpBytesReturned], 1Ch
0x18004f157  movups  [rbp+8E0h+var_910], xmm0
0x18004f15b  mov     eax, r14d
0x18004f15e  mov     r8d, 0Ah
0x18004f164  movups  xmm0, xmmword ptr [rbp+8E0h+var_930.u]
0x18004f168  and     eax, 0FFFFFFh
0x18004f16d  mov     byte ptr [rbp+8E0h+var_900], 80h
0x18004f171  or      rax, 17000000h
0x18004f177  shl     rax, 18h
0x18004f17b  mov     qword ptr [rsp+9E0h+var_978+8], rax
0x18004f180  or      eax, 0FFFFFFFFh
0x18004f183  mov     dword ptr [rbp+8E0h+var_910], eax
0x18004f186  mov     dword ptr [rbp+8E0h+var_910+4], eax
0x18004f189  lea     rax, [rbp+8E0h+var_910]
0x18004f18d  mov     qword ptr [rsp+9E0h+nOutBufferSize], rax
0x18004f192  mov     dword ptr [rsp+9E0h+lpOutBuffer], 18h
0x18004f19a  movdqu  [rsp+9E0h+var_968], xmm0
0x18004f1a0  call    SetAllParameters
0x18004f1a5  mov     ebx, eax
0x18004f1a7  xor     eax, eax
0x18004f1a9  test    ebx, ebx
0x18004f1ab  jz      short loc_18004F1F8
0x18004f1ad  xor     r15d, r15d
0x18004f1b0  cmp     qword ptr cs:xmmword_1800D0740, r15
0x18004f1b7  jz      loc_18004F37F
0x18004f1bd  mov     r8d, ebx
0x18004f1c0  mov     word ptr [rbp+8E0h+var_8B0], r15w
0x18004f1c5  lea     rdx, aSetipv6address; "SetIPv6AddressOnInterface failed and re"...
0x18004f1cc  lea     rcx, [rbp+8E0h+var_8B0]
0x18004f1d0  call    FormatRRASErrorString
0x18004f1d5  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18004f1dc  lea     r8, [rbp+8E0h+var_8B0]
0x18004f1e0  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004f1e7  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004f1ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f1f3  jmp     loc_18004F37F
0x18004f1f8  cmp     cs:dword_1800D0938, eax
0x18004f1fe  mov     r8b, r13b
0x18004f201  mov     dl, r13b
0x18004f204  mov     byte ptr [rsp+9E0h+nOutBufferSize], r13b
0x18004f209  setnz   r9b
0x18004f20d  mov     ecx, r12d
  ... truncated ...
```

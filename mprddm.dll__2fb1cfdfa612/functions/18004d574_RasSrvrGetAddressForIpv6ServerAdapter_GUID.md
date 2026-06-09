# RasSrvrGetAddressForIpv6ServerAdapter(_GUID)

- ea: `0x18004d574`
- end: `0x18004ddc8`
- name: `?RasSrvrGetAddressForIpv6ServerAdapter@@YAKU_GUID@@@Z`
- size: `2132`
- prototype: `unsigned int __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180052670`

## callees

- `0x180002bbe`
- `0x180025c98`
- `0x18004d574`
- `0x18004e19c`
- `0x180052a44`
- `0x180055750`
- `0x1800588f4`
- `0x180058ae4`
- `0x180058b34`
- `0x180058b94`
- `0x180058bcc`
- `0x180058dc4`
- `0x180058e78`
- `0x180059030`
- `0x18005a3f4`
- `0x18005b5d8`
- `0x180071cec`
- `0x1800748c8`
- `0x18007593c`
- `0x18007a180`
- `0x18007a204`
- `0x18007a34c`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18004d716`
- `msvcrt!memcpy_s` at `0x18004d716`
- `KERNEL32!DeviceIoControl` at `0x18004d77f`
- `KERNEL32!DeviceIoControl` at `0x18004d77f`
- `KERNEL32!GetLastError` at `0x18004d789`
- `KERNEL32!GetLastError` at `0x18004d789`
- `KERNEL32!LeaveCriticalSection` at `0x18004dd9d`
- `KERNEL32!LeaveCriticalSection` at `0x18004dd9d`
- `KERNEL32!EnterCriticalSection` at `0x18004d66e`
- `KERNEL32!EnterCriticalSection` at `0x18004d66e`
- `ntdll!RtlIpv6AddressToStringA` at `0x18004d9ca`
- `ntdll!RtlIpv6AddressToStringA` at `0x18004d9ca`

## string_xrefs

- `0x18004db9c`: `AddOrRemoveIpv6Prefix completes with 0x%x`
- `0x18004db3f`: `SetIpv6InterfaceProperties completes with 0x%x`
- `0x18004d6bd`: `Error %d in finding compartment for routing domain`
- `0x18004d7a2`: `Error %d mapping IPv6 server adapter for compartment %d`
- `0x18004d7cc`: `RasSrvrIpv6AdapterMapped: Interface Index: %d  compartment: %d`

## pseudocode

```c
__int64 __fastcall RasSrvrGetAddressForIpv6ServerAdapter(struct _GUID *a1)
{
  __int64 v1; // r15
  unsigned int v3; // ebx
  __int64 NboServerIpv6Address; // rax
  unsigned __int64 v5; // r14
  unsigned int RoutingDomainConfigData; // eax
  int v7; // r13d
  DWORD LastError; // eax
  NET_IFINDEX v9; // r12d
  unsigned int RoutingDomainAddressPool; // ebx
  BOOL v11; // esi
  int v12; // ecx
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  int lpOutBuffer; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v21; // [rsp+48h] [rbp-B8h] BYREF
  int v22; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD BytesReturned[4]; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD Buf1[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 Destination; // [rsp+80h] [rbp-80h] BYREF
  int v26; // [rsp+90h] [rbp-70h]
  __m256i v27; // [rsp+98h] [rbp-68h]
  struct in6_addr v28; // [rsp+B8h] [rbp-48h] BYREF
  int v29; // [rsp+C8h] [rbp-38h]
  __m256i v30; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v31; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v32; // [rsp+F8h] [rbp-8h]
  int v33; // [rsp+100h] [rbp+0h]
  struct in6_addr Addr; // [rsp+110h] [rbp+10h] BYREF
  __int64 Source; // [rsp+120h] [rbp+20h] BYREF
  int v36; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v37[2044]; // [rsp+134h] [rbp+34h] BYREF
  CHAR S[128]; // [rsp+930h] [rbp+830h] BYREF

  v1 = 0;
  v26 = 0;
  BytesReturned[0] = 0;
  *(_QWORD *)&Buf1[0] = 0;
  v3 = 0;
  v21 = 1;
  Destination = 0;
  Addr = 0;
  NboServerIpv6Address = RasRdGetNboServerIpv6Address(&v30, a1);
  v22 = 4;
  v27 = *(__m256i *)NboServerIpv6Address;
  v28 = *(struct in6_addr *)(NboServerIpv6Address + 32);
  v29 = *(_DWORD *)(NboServerIpv6Address + 48);
  v30.m256i_i32[0] = 0;
  RasRoutingDomainGetConfigParam(a1, 8, &v22, &v30);
  LODWORD(v5) = RasRdGetServerAdapterLuidIndex(a1);
  Source = RasRdGetServerAdapterIPv6IfId(a1);
  v36 = 0;
  memset_0(v37, 0, sizeof(v37));
  if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800C9740 + 1),
      L"Entering RasSrvrGetAddressForIpv6ServerAdapter");
  EnterCriticalSection(&RasSrvrCriticalSection);
  if ( memcmp_0(a1, &GUID_NULL, 0x10u) )
  {
    RoutingDomainConfigData = GetRoutingDomainConfigData(a1, 256, 4, &v21);
    v3 = RoutingDomainConfigData;
    if ( RoutingDomainConfigData )
    {
      if ( (_QWORD)xmmword_1800C9740 )
      {
        LOWORD(v36) = 0;
        FormatRRASErrorString(&v36, L"Error %d in finding compartment for routing domain", RoutingDomainConfigData);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800C9740,
          &v36);
      }
      goto LABEL_51;
    }
  }
  DWORD2(Destination) = v21;
  *(_QWORD *)&Destination = 0xFFFFFFFF00000001uLL;
  v7 = 0;
  memcpy_s((char *)&Destination + 12, 8u, &Source, 8u);
  v22 = 0;
  v20 = 4;
  RasRoutingDomainGetConfigParam(a1, 5, &v20, &v22);
  if ( v22 )
  {
    v9 = v30.m256i_i32[0];
  }
  else
  {
    v30.m256i_i64[0] = 0;
    if ( !DeviceIoControl(HelperWanArpv6Handle, 0x90018014, &Destination, 0x14u, &Destination, 0x14u, BytesReturned, 0) )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( (_QWORD)xmmword_1800C9740 )
      {
        LOWORD(v36) = 0;
        FormatRRASErrorString(
          &v36,
          L"Error %d mapping IPv6 server adapter for compartment %d",
          LastError,
          DWORD2(Destination));
LABEL_44:
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800C9740,
          &v36);
        goto LABEL_45;
      }
      goto LABEL_45;
    }
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v36) = 0;
      FormatRRASErrorString(
        &v36,
        L"RasSrvrIpv6AdapterMapped: Interface Index: %d  compartment: %d",
        DWORD1(Destination),
        DWORD2(Destination));
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v36);
    }
    NsiConvertInterfaceIndexToLuid((char *)&Destination + 4, &v30);
    v5 = ((unsigned __int64)v30.m256i_i64[0] >> 24) & 0xFFFFFF;
    v20 = ((unsigned __int64)v30.m256i_i64[0] >> 24) & 0xFFFFFF;
    RasRoutingDomainSetConfigParam(a1, 7, 4, &v20);
    v9 = DWORD1(Destination);
    v20 = DWORD1(Destination);
    RasRoutingDomainSetConfigParam(a1, 8, 4, &v20);
    v20 = 1;
    RasRoutingDomainSetConfigParam(a1, 5, 4, &v20);
  }
  if ( !v28.u.Word[0]
    && __PAIR32__(v28.u.Word[1], 0) == v28.u.Word[2]
    && __PAIR32__(v28.u.Word[3], 0) == v28.u.Word[4]
    && __PAIR32__(v28.u.Word[5], 0) == v28.u.Word[6]
    && !v28.u.Word[7] )
  {
    *(struct _GUID *)v30.m256i_i8 = *a1;
    Addr = 0;
    v3 = RasSrvrAcquireIpv6AddressForServer((void *)0xEE170466LL);
    if ( v3 )
      goto LABEL_51;
    *(struct _GUID *)v30.m256i_i8 = *a1;
    RoutingDomainAddressPool = RasGetRoutingDomainAddressPool(&v30, 2, Buf1);
    v31 = *(_QWORD *)Addr.u.Byte;
    v7 = 1;
    v11 = RoutingDomainAddressPool == 0;
    v30 = v27;
    v28 = Addr;
    v32 = _mm_srli_si128((__m128i)Addr, 8).m128i_u64[0];
    v33 = v29;
    RasRdSetNboServerIpv6Address(a1, &v30);
    if ( RoutingDomainAddressPool || (v1 = *(_QWORD *)&Buf1[0]) == 0 )
    {
      if ( (_QWORD)xmmword_1800C9740 != v1 )
      {
        LOWORD(v36) = v1;
        FormatRRASErrorString(&v36, L"Failed to get the pool for inserting VPN address %d", RoutingDomainAddressPool);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800C9740,
          &v36);
      }
      v3 = 717;
    }
    else
    {
      **(_QWORD **)&Buf1[0] = *(_QWORD *)v28.u.Byte;
      RtlIpv6AddressToStringA(&Addr, S);
      if ( (_QWORD)xmmword_1800C9740 )
      {
        LOWORD(v36) = 0;
        FormatRRASErrorString(&v36, L"Acquired IPv6 address %hs for Server", S);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800C9740,
          &v36);
      }
      *(_QWORD *)&Buf1[0] = (v5 & 0xFFFFFF | 0x17000000) << 24;
      *(struct in6_addr *)((char *)Buf1 + 8) = v28;
      v30.m256i_i32[0] = -1;
      *(__int64 *)((char *)v30.m256i_i64 + 4) = 0xFFFFFFFFLL;
      *(_OWORD *)((char *)&v30.m256i_u64[1] + 4) = 0;
      v30.m256i_i8[16] = 0x80;
      v13 = SetAllParameters(v12, (unsigned int)&NPI_MS_IPV6_MODULEID, 10, (unsigned int)Buf1, 24, (__int64)&v30, 28, 2);
      v3 = v13;
      if ( v13 )
      {
        v1 = 0;
        if ( (_QWORD)xmmword_1800C9740 )
        {
          LOWORD(v36) = 0;
          FormatRRASErrorString(&v36, L"SetIPv6AddressOnInterface failed and returned %d", v13);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800C9740,
            &v36);
        }
      }
      else
      {
        v14 = SetIpv6InterfaceProperties(v9, lpOutBuffer, 1);
        if ( (_QWORD)xmmword_1800C9740 )
        {
          LOWORD(v36) = 0;
          FormatRRASErrorString(&v36, L"SetIpv6InterfaceProperties completes with 0x%x", v14);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800C9740,
            &v36);
        }
        v15 = AddOrRemoveIpv6PrefixForAdvertisement(v1, v9, 0, 256);
        v1 = 0;
        if ( (_QWORD)xmmword_1800C9740 )
        {
          LOWORD(v36) = 0;
          FormatRRASErrorString(&v36, L"AddOrRemoveIpv6Prefix completes with 0x%x", v15);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800C9740,
            &v36);
        }
        Buf1[0] = *a1;
        v16 = RasReleaseRoutingDomainAddressPool(Buf1);
        if ( v16 )
        {
          if ( (_QWORD)xmmword_1800C9740 )
          {
            LOWORD(v36) = 0;
            FormatRRASErrorString(
              &v36,
              L"RasReleaseRoutingDomainAddressPool failed to release lock and returned %d",
              v16);
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
              gRasIpAddrMgmtEtwContext,
              xmmword_1800C9740,
              &v36);
          }
        }
        else
        {
          v11 = 0;
        }
        Buf1[0] = *a1;
        RasSrvrInterfaceIdInsert(Buf1);
        RasSrvrSetProxyArpV6(&v28, 1, &v28, v21, a1);
        v3 = 0;
      }
    }
    if ( v11 )
    {
      Buf1[0] = *a1;
      v17 = RasReleaseRoutingDomainAddressPool(Buf1);
      if ( v17 )
      {
        if ( (_QWORD)xmmword_1800C9740 != v1 )
        {
          LOWORD(v36) = v1;
          FormatRRASErrorString(&v36, L"RasReleaseRoutingDomainAddressPool failed to release lock and returned %d", v17);
          goto LABEL_44;
        }
      }
    }
  }
LABEL_45:
  if ( !v3 )
    goto LABEL_52;
  if ( v7 )
  {
    if ( dword_1800C98DC == (_DWORD)v1 )
    {
      Buf1[0] = *a1;
      RasStatReleaseIpv6Prefix(Buf1, &Addr);
    }
    else
    {
      RasDhcpReleaseIpv6Prefix(&Addr);
    }
    RasSrvrSetProxyArpV6(&v28, 0, &v28, v21, a1);
  }
LABEL_51:
  ResetIpv6AddressOnInterface((unsigned int)v5, &v28);
  v28.u.Byte[0] = v1;
LABEL_52:
  if ( (_QWORD)xmmword_1800C9740 != v1 )
  {
    LOWORD(v36) = v1;
    FormatRRASErrorString(&v36, L"RasSrvrGetAddressForIpv6ServerAdapter: done %d", v3);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800C9740,
      &v36);
  }
  LeaveCriticalSection(&RasSrvrCriticalSection);
  return v3;
}

```

## disassembly

```asm
0x18004d574  push    rbp
0x18004d576  push    rbx
0x18004d577  push    rsi
0x18004d578  push    rdi
0x18004d579  push    r12
0x18004d57b  push    r13
0x18004d57d  push    r14
0x18004d57f  push    r15
0x18004d581  lea     rbp, [rsp-8C8h]
0x18004d589  sub     rsp, 9C8h
0x18004d590  mov     rax, cs:__security_cookie
0x18004d597  xor     rax, rsp
0x18004d59a  mov     [rbp+900h+var_50], rax
0x18004d5a1  xor     eax, eax
0x18004d5a3  xorps   xmm0, xmm0
0x18004d5a6  xor     r15d, r15d
0x18004d5a9  mov     [rbp+900h+var_970], eax
0x18004d5ac  mov     rdi, rcx
0x18004d5af  mov     [rsp+0A00h+BytesReturned], r15d
0x18004d5b4  mov     rdx, rcx
0x18004d5b7  mov     qword ptr [rsp+0A00h+Buf1], r15
0x18004d5bc  lea     esi, [rax+1]
0x18004d5bf  mov     ebx, r15d
0x18004d5c2  lea     rcx, [rbp+900h+var_930]
0x18004d5c6  mov     [rsp+0A00h+var_9B8], esi
0x18004d5ca  movups  [rbp+900h+Destination], xmm0
0x18004d5ce  movups  xmmword ptr [rbp+900h+Addr.u], xmm0
0x18004d5d2  call    RasRdGetNboServerIpv6Address
0x18004d5d7  lea     r12d, [r15+4]
0x18004d5db  mov     rcx, rdi
0x18004d5de  lea     r9, [rbp+900h+var_930]
0x18004d5e2  mov     [rsp+0A00h+var_9B4], r12d
0x18004d5e7  lea     r8, [rsp+0A00h+var_9B4]
0x18004d5ec  movups  xmm0, xmmword ptr [rax]
0x18004d5ef  lea     edx, [rsi+7]
0x18004d5f2  movups  [rbp+900h+var_968], xmm0
0x18004d5f6  movups  xmm1, xmmword ptr [rax+10h]
0x18004d5fa  movups  [rbp+900h+var_958], xmm1
0x18004d5fe  movups  xmm0, xmmword ptr [rax+20h]
0x18004d602  movups  xmmword ptr [rbp+900h+var_948.u], xmm0
0x18004d606  mov     eax, [rax+30h]
0x18004d609  mov     [rbp+900h+var_938], eax
0x18004d60c  mov     dword ptr [rbp+900h+var_930], r15d
0x18004d610  call    RasRoutingDomainGetConfigParam
0x18004d615  mov     rcx, rdi
0x18004d618  call    RasRdGetServerAdapterLuidIndex
0x18004d61d  mov     rcx, rdi
0x18004d620  mov     r14d, eax
0x18004d623  call    RasRdGetServerAdapterIPv6IfId
0x18004d628  xor     edx, edx; Val
0x18004d62a  mov     [rbp+900h+Source], rax
0x18004d62e  mov     r8d, 7FCh; Size
0x18004d634  mov     [rbp+900h+var_8D0], r15d
0x18004d638  lea     rcx, [rbp+900h+var_8CC]; void *
0x18004d63c  call    memset_0
0x18004d641  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x18004d648  test    rdx, rdx
0x18004d64b  jz      short loc_18004D667
0x18004d64d  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004d654  lea     r8, aEnteringRassrv; "Entering RasSrvrGetAddressForIpv6Server"...
0x18004d65b  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004d662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d667  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004d66e  call    cs:__imp_EnterCriticalSection
0x18004d674  mov     r8d, 10h; Size
0x18004d67a  lea     rdx, GUID_NULL; Buf2
0x18004d681  mov     rcx, rdi; Buf1
0x18004d684  call    memcmp_0
0x18004d689  test    eax, eax
0x18004d68b  jz      short loc_18004D6F0
0x18004d68d  lea     r9, [rsp+0A00h+var_9B8]
0x18004d692  mov     r8d, r12d
0x18004d695  mov     edx, 100h
0x18004d69a  mov     rcx, rdi
0x18004d69d  call    GetRoutingDomainConfigData
0x18004d6a2  mov     ebx, eax
0x18004d6a4  test    eax, eax
0x18004d6a6  jz      short loc_18004D6F0
0x18004d6a8  cmp     qword ptr cs:xmmword_1800C9740, r15
0x18004d6af  jz      loc_18004DD47
0x18004d6b5  mov     r8d, eax
0x18004d6b8  mov     word ptr [rbp+900h+var_8D0], r15w
0x18004d6bd  lea     rdx, aErrorDInFindin; "Error %d in finding compartment for rou"...
0x18004d6c4  lea     rcx, [rbp+900h+var_8D0]
0x18004d6c8  call    FormatRRASErrorString
0x18004d6cd  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18004d6d4  lea     r8, [rbp+900h+var_8D0]
0x18004d6d8  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004d6df  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004d6e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d6eb  jmp     loc_18004DD47
0x18004d6f0  mov     eax, [rsp+0A00h+var_9B8]
0x18004d6f4  lea     r8, [rbp+900h+Source]; Source
0x18004d6f8  mov     dword ptr [rbp+900h+Destination+8], eax
0x18004d6fb  lea     rcx, [rbp+900h+Destination+0Ch]; Destination
0x18004d6ff  mov     eax, 8
0x18004d704  mov     dword ptr [rbp+900h+Destination], esi
0x18004d707  mov     r9d, eax; SourceSize
0x18004d70a  mov     dword ptr [rbp+900h+Destination+4], 0FFFFFFFFh
0x18004d711  mov     edx, eax; DestinationSize
0x18004d713  mov     r13d, r15d
0x18004d716  call    cs:__imp_memcpy_s
0x18004d71c  lea     r9, [rsp+0A00h+var_9B4]
0x18004d721  mov     [rsp+0A00h+var_9B4], r15d
0x18004d726  lea     r8, [rsp+0A00h+var_9C0]
0x18004d72b  mov     [rsp+0A00h+var_9C0], r12d
0x18004d730  mov     edx, 5
0x18004d735  mov     rcx, rdi
0x18004d738  call    RasRoutingDomainGetConfigParam
0x18004d73d  cmp     [rsp+0A00h+var_9B4], r15d
0x18004d742  jnz     loc_18004D874
0x18004d748  mov     rcx, cs:?HelperWanArpv6Handle@@3PEAXEA; hDevice
0x18004d74f  lea     rax, [rsp+0A00h+BytesReturned]
0x18004d754  mov     [rsp+0A00h+lpOverlapped], r15; lpOverlapped
0x18004d759  lea     r8, [rbp+900h+Destination]; lpInBuffer
0x18004d75d  mov     [rsp+0A00h+lpBytesReturned], rax; lpBytesReturned
0x18004d762  mov     r9d, 14h; nInBufferSize
0x18004d768  lea     rax, [rbp+900h+Destination]
0x18004d76c  mov     [rsp+0A00h+nOutBufferSize], r9d; nOutBufferSize
0x18004d771  mov     edx, 90018014h; dwIoControlCode
0x18004d776  mov     [rsp+0A00h+lpOutBuffer], rax; lpOutBuffer
0x18004d77b  mov     qword ptr [rbp+900h+var_930], r15
0x18004d77f  call    cs:__imp_DeviceIoControl
0x18004d785  test    eax, eax
0x18004d787  jnz     short loc_18004D7BF
0x18004d789  call    cs:__imp_GetLastError
0x18004d78f  cmp     qword ptr cs:xmmword_1800C9740, r15
0x18004d796  mov     ebx, eax
0x18004d798  jz      loc_18004DCFA
0x18004d79e  mov     r9d, dword ptr [rbp+900h+Destination+8]
0x18004d7a2  lea     rdx, aErrorDMappingI; "Error %d mapping IPv6 server adapter fo"...
0x18004d7a9  mov     r8d, eax
0x18004d7ac  mov     word ptr [rbp+900h+var_8D0], r15w
0x18004d7b1  lea     rcx, [rbp+900h+var_8D0]
0x18004d7b5  call    FormatRRASErrorString
0x18004d7ba  jmp     loc_18004DCDC
0x18004d7bf  cmp     qword ptr cs:xmmword_1800C9740, r15
0x18004d7c6  jz      short loc_18004D803
0x18004d7c8  mov     r9d, dword ptr [rbp+900h+Destination+8]
0x18004d7cc  lea     rdx, aRassrvripv6ada; "RasSrvrIpv6AdapterMapped: Interface Ind"...
0x18004d7d3  mov     r8d, dword ptr [rbp+900h+Destination+4]
0x18004d7d7  lea     rcx, [rbp+900h+var_8D0]
0x18004d7db  mov     word ptr [rbp+900h+var_8D0], r15w
0x18004d7e0  call    FormatRRASErrorString
0x18004d7e5  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18004d7ec  lea     r8, [rbp+900h+var_8D0]
0x18004d7f0  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004d7f7  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004d7fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d803  lea     rdx, [rbp+900h+var_930]
0x18004d807  lea     rcx, [rbp+900h+Destination+4]
0x18004d80b  call    NsiConvertInterfaceIndexToLuid
0x18004d810  mov     r14, qword ptr [rbp+900h+var_930]
0x18004d814  lea     r9, [rsp+0A00h+var_9C0]
0x18004d819  shr     r14, 18h
0x18004d81d  mov     r8d, r12d
0x18004d820  and     r14d, 0FFFFFFh
0x18004d827  mov     edx, 7
0x18004d82c  mov     rcx, rdi
0x18004d82f  mov     [rsp+0A00h+var_9C0], r14d
0x18004d834  call    RasRoutingDomainSetConfigParam
0x18004d839  mov     r12d, dword ptr [rbp+900h+Destination+4]
0x18004d83d  lea     r9, [rsp+0A00h+var_9C0]
0x18004d842  mov     edx, 8
0x18004d847  mov     [rsp+0A00h+var_9C0], r12d
0x18004d84c  mov     rcx, rdi
0x18004d84f  lea     r8d, [rdx-4]
0x18004d853  call    RasRoutingDomainSetConfigParam
0x18004d858  mov     edx, 5
0x18004d85d  mov     [rsp+0A00h+var_9C0], esi
0x18004d861  lea     r9, [rsp+0A00h+var_9C0]
0x18004d866  mov     rcx, rdi
0x18004d869  lea     r8d, [rdx-1]
0x18004d86d  call    RasRoutingDomainSetConfigParam
0x18004d872  jmp     short loc_18004D878
0x18004d874  mov     r12d, dword ptr [rbp+900h+var_930]
0x18004d878  cmp     word ptr [rbp+900h+var_948.u], r15w
0x18004d87d  jnz     loc_18004DCFA
0x18004d883  cmp     word ptr [rbp+900h+var_948.u+2], r15w
0x18004d888  jnz     loc_18004DCFA
0x18004d88e  cmp     word ptr [rbp+900h+var_948.u+4], r15w
0x18004d893  jnz     loc_18004DCFA
0x18004d899  cmp     word ptr [rbp+900h+var_948.u+6], r15w
0x18004d89e  jnz     loc_18004DCFA
0x18004d8a4  cmp     word ptr [rbp+900h+var_948.u+8], r15w
0x18004d8a9  jnz     loc_18004DCFA
0x18004d8af  cmp     word ptr [rbp+900h+var_948.u+0Ah], r15w
0x18004d8b4  jnz     loc_18004DCFA
0x18004d8ba  cmp     word ptr [rbp+900h+var_948.u+0Ch], r15w
0x18004d8bf  jnz     loc_18004DCFA
0x18004d8c5  cmp     word ptr [rbp+900h+var_948.u+0Eh], r15w
0x18004d8ca  jnz     loc_18004DCFA
0x18004d8d0  movaps  xmm1, xmmword ptr [rdi]
0x18004d8d3  lea     r8, [rbp+900h+Addr]
0x18004d8d7  xorps   xmm0, xmm0
0x18004d8da  movdqa  [rbp+900h+var_930], xmm1
0x18004d8df  lea     rdx, [rbp+900h+var_930]
0x18004d8e3  mov     ecx, 0EE170466h; void *
0x18004d8e8  movups  xmmword ptr [rbp+900h+Addr.u], xmm0
0x18004d8ec  call    RasSrvrAcquireIpv6AddressForServer
0x18004d8f1  mov     ebx, eax
0x18004d8f3  test    eax, eax
0x18004d8f5  jnz     loc_18004DD47
0x18004d8fb  movaps  xmm0, xmmword ptr [rdi]
0x18004d8fe  lea     r8, [rsp+0A00h+Buf1]
0x18004d903  lea     edx, [rax+2]
0x18004d906  movdqa  [rbp+900h+var_930], xmm0
0x18004d90b  lea     rcx, [rbp+900h+var_930]
0x18004d90f  call    RasGetRoutingDomainAddressPool
0x18004d914  mov     rcx, qword ptr [rbp+900h+Addr.u]
0x18004d918  lea     rdx, [rbp+900h+var_930]
0x18004d91c  movups  xmm2, xmmword ptr [rbp+900h+Addr.u]
0x18004d920  test    eax, eax
0x18004d922  mov     ebx, eax
0x18004d924  movups  xmm0, [rbp+900h+var_968]
0x18004d928  mov     rax, rcx
0x18004d92b  mov     word ptr [rbp+900h+var_910], cx
0x18004d92f  movups  xmm1, [rbp+900h+var_958]
0x18004d933  mov     esi, r15d
0x18004d936  mov     r13d, 1
0x18004d93c  setz    sil
0x18004d940  movaps  [rbp+900h+var_930], xmm0
0x18004d944  shr     rax, 10h
0x18004d948  mov     word ptr [rbp+900h+var_910+2], ax
0x18004d94c  mov     rax, rcx
0x18004d94f  shr     rax, 20h
0x18004d953  mov     word ptr [rbp+900h+var_910+4], ax
0x18004d957  shr     rcx, 30h
0x18004d95b  mov     word ptr [rbp+900h+var_910+6], cx
0x18004d95f  movdqu  xmmword ptr [rbp+900h+var_948.u], xmm2
0x18004d964  psrldq  xmm2, 8
0x18004d969  movq    rcx, xmm2
0x18004d96e  movaps  [rbp+900h+var_920], xmm1
0x18004d972  mov     rax, rcx
0x18004d975  mov     [rbp+900h+var_908], cx
0x18004d979  shr     rax, 10h
0x18004d97d  mov     [rbp+900h+var_906], ax
0x18004d981  mov     rax, rcx
0x18004d984  shr     rax, 20h
0x18004d988  shr     rcx, 30h
0x18004d98c  mov     [rbp+900h+var_904], ax
0x18004d990  mov     eax, [rbp+900h+var_938]
0x18004d993  mov     [rbp+900h+var_902], cx
0x18004d997  mov     rcx, rdi
0x18004d99a  mov     [rbp+900h+var_900], eax
0x18004d99d  call    RasRdSetNboServerIpv6Address
0x18004d9a2  test    ebx, ebx
0x18004d9a4  jnz     loc_18004DC5B
0x18004d9aa  mov     r15, qword ptr [rsp+0A00h+Buf1]
0x18004d9af  test    r15, r15
0x18004d9b2  jz      loc_18004DC5B
0x18004d9b8  mov     rax, qword ptr [rbp+900h+var_948.u]
0x18004d9bc  lea     rdx, [rbp+900h+S]; S
0x18004d9c3  lea     rcx, [rbp+900h+Addr]; Addr
0x18004d9c7  mov     [r15], rax
0x18004d9ca  call    cs:__imp_RtlIpv6AddressToStringA
0x18004d9d0  cmp     qword ptr cs:xmmword_1800C9740, 0
0x18004d9d8  jz      short loc_18004DA15
0x18004d9da  xor     eax, eax
0x18004d9dc  lea     r8, [rbp+900h+S]
0x18004d9e3  lea     rdx, aAcquiredIpv6Ad; "Acquired IPv6 address %hs for Server"
0x18004d9ea  mov     word ptr [rbp+900h+var_8D0], ax
0x18004d9ee  lea     rcx, [rbp+900h+var_8D0]
0x18004d9f2  call    FormatRRASErrorString
0x18004d9f7  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18004d9fe  lea     r8, [rbp+900h+var_8D0]
0x18004da02  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004da09  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004da10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004da15  mov     eax, r14d
0x18004da18  mov     dword ptr [rsp+0A00h+lpOverlapped], 2
0x18004da20  and     eax, 0FFFFFFh
0x18004da25  mov     dword ptr [rsp+0A00h+lpBytesReturned], 1Ch
0x18004da2d  or      rax, 17000000h
0x18004da33  lea     r9, [rsp+0A00h+Buf1]
0x18004da38  shl     rax, 18h
0x18004da3c  lea     rdx, NPI_MS_IPV6_MODULEID
0x18004da43  mov     qword ptr [rsp+0A00h+Buf1], rax
0x18004da48  xorps   xmm0, xmm0
0x18004da4b  movzx   eax, word ptr [rbp+900h+var_948.u]
0x18004da4f  mov     r8d, 0Ah
0x18004da55  mov     word ptr [rsp+0A00h+Buf1+8], ax
0x18004da5a  movzx   eax, word ptr [rbp+900h+var_948.u+2]
0x18004da5e  mov     word ptr [rsp+0A00h+Buf1+0Ah], ax
0x18004da63  movzx   eax, word ptr [rbp+900h+var_948.u+4]
0x18004da67  mov     word ptr [rsp+0A00h+Buf1+0Ch], ax
0x18004da6c  movzx   eax, word ptr [rbp+900h+var_948.u+6]
0x18004da70  mov     word ptr [rsp+0A00h+Buf1+0Eh], ax
0x18004da75  movzx   eax, word ptr [rbp+900h+var_948.u+8]
0x18004da79  mov     word ptr [rsp+0A00h+Buf1+10h], ax
0x18004da7e  movzx   eax, word ptr [rbp+900h+var_948.u+0Ah]
0x18004da82  mov     word ptr [rsp+0A00h+Buf1+12h], ax
0x18004da87  movzx   eax, word ptr [rbp+900h+var_948.u+0Ch]
0x18004da8b  mov     word ptr [rsp+0A00h+Buf1+14h], ax
0x18004da90  movzx   eax, word ptr [rbp+900h+var_948.u+0Eh]
0x18004da94  movups  [rbp+900h+var_930], xmm0
0x18004da98  mov     word ptr [rsp+0A00h+Buf1+16h], ax
0x18004da9d  or      eax, 0FFFFFFFFh
0x18004daa0  mov     dword ptr [rbp+900h+var_930], eax
0x18004daa3  mov     dword ptr [rbp+900h+var_930+4], eax
  ... truncated ...
```

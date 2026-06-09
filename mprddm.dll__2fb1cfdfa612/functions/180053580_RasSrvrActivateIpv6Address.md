# RasSrvrActivateIpv6Address

- ea: `0x180053580`
- end: `0x180053b5e`
- name: `RasSrvrActivateIpv6Address`
- size: `1502`
- prototype: `__int64 __usercall@<rax>(struct _GUID *@<rcx>, struct in6_addr *Addr@<rdx>, char)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002bbe`
- `0x180025c98`
- `0x180028e50`
- `0x18004d430`
- `0x18004e19c`
- `0x18004e920`
- `0x180053580`
- `0x1800588f4`
- `0x180058ae4`
- `0x180058b94`
- `0x180058dc4`
- `0x180071cec`
- `0x180073664`
- `0x1800748c8`
- `0x180075668`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180053b2b`
- `KERNEL32!LeaveCriticalSection` at `0x180053b2b`
- `KERNEL32!EnterCriticalSection` at `0x18005383a`
- `KERNEL32!EnterCriticalSection` at `0x18005383a`
- `ntdll!RtlIpv6AddressToStringA` at `0x180053871`
- `ntdll!RtlIpv6AddressToStringA` at `0x180053871`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180053a54`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180053a54`

## string_xrefs

- `0x1800536aa`: `RasSrvrStop: GetRoutingDomainConfigData (compartmentId) failed and returned %d`
- `0x1800538f6`: `Create Ipv6 Neighbor for Global addr: 0x%x`
- `0x180053979`: `Create Ipv6 Neighbor for link-local addr: 0x%x`
- `0x180053af0`: `AddOrRemoveIpv6Prefix returned 0x%x`

## pseudocode

```c
__int64 __fastcall RasSrvrActivateIpv6Address(struct _GUID *a1, struct in6_addr *Addr, int a3, NET_LUID *a4, char a5)
{
  __int64 NboServerIpv6Address; // rax
  __int128 v10; // xmm1
  struct in6_addr v11; // xmm0
  unsigned int v12; // r15d
  unsigned int RoutingDomainConfigData; // eax
  __int64 v14; // rdx
  unsigned __int64 Value; // r8
  NET_LUID *v16; // rbx
  __int64 v17; // r9
  struct _GUID v18; // xmm1
  struct _ACQUIRED_IPv6ADDR *Aipv6Node; // rax
  unsigned int v20; // eax
  unsigned int v21; // esi
  unsigned int v22; // eax
  unsigned int v23; // esi
  __int64 v24; // r12
  unsigned int v25; // eax
  unsigned __int64 v27; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v28; // [rsp+38h] [rbp-C8h] BYREF
  ULONG InterfaceIndex[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v30[3]; // [rsp+48h] [rbp-B8h] BYREF
  struct _GUID v31; // [rsp+60h] [rbp-A0h] BYREF
  struct in6_addr v32; // [rsp+70h] [rbp-90h] BYREF
  __int128 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+90h] [rbp-70h]
  struct in6_addr v35; // [rsp+A0h] [rbp-60h] BYREF
  int v36; // [rsp+B0h] [rbp-50h]
  _BYTE v37[56]; // [rsp+B8h] [rbp-48h] BYREF
  _OWORD v38[3]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v39[30]; // [rsp+120h] [rbp+20h]
  __int16 v40; // [rsp+13Eh] [rbp+3Eh]
  CHAR S[128]; // [rsp+140h] [rbp+40h] BYREF
  int v42; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v43[2044]; // [rsp+1C4h] [rbp+C4h] BYREF

  v30[0] = 33022;
  v28 = 1;
  v27 = 0;
  NboServerIpv6Address = RasRdGetNboServerIpv6Address(v37, a1);
  *(_QWORD *)InterfaceIndex = 0;
  v10 = *(_OWORD *)(NboServerIpv6Address + 16);
  v33 = *(_OWORD *)NboServerIpv6Address;
  v11 = *(struct in6_addr *)(NboServerIpv6Address + 32);
  LODWORD(NboServerIpv6Address) = *(_DWORD *)(NboServerIpv6Address + 48);
  v34 = v10;
  v36 = NboServerIpv6Address;
  v35 = v11;
  v40 = 0;
  v38[0] = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  v38[2] = *(_OWORD *)L"000-0000-000000000000}";
  v42 = 0;
  v38[1] = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  *(_OWORD *)v39 = *(_OWORD *)L"-000000000000}";
  *(_OWORD *)&v39[14] = *(_OWORD *)L"000000}";
  memset_0(v43, 0, sizeof(v43));
  if ( !memcmp_0(a1, &GUID_NULL, 0x10u) )
  {
    v12 = 0;
  }
  else
  {
    RoutingDomainConfigData = GetRoutingDomainConfigData(a1, 256, 4, &v28);
    v12 = RoutingDomainConfigData;
    if ( RoutingDomainConfigData && (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v42) = 0;
      FormatRRASErrorString(
        &v42,
        L"RasSrvrStop: GetRoutingDomainConfigData (compartmentId) failed and returned %d",
        RoutingDomainConfigData);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v42);
    }
    MprConvertGuidToString(a1, v14, v38);
  }
  if ( a3 )
  {
    Value = a4->Value;
    v16 = (NET_LUID *)&v27;
  }
  else
  {
    Value = ((RasRdGetServerAdapterLuidIndex(a1) & 0xFFFFFF) << 24) | 0x17000000000000LL;
    v16 = a4;
  }
  v27 = Value;
  if ( (_QWORD)xmmword_1800C9740 )
  {
    LOWORD(v42) = 0;
    v17 = v16 ? (v16->Value >> 24) & 0xFFFFFF : 0LL;
    FormatRRASErrorString(
      &v42,
      L"RasSrvrActivateIpv6Address: InterfaceLuid %d Subinterface Luid %d",
      (Value >> 24) & 0xFFFFFF,
      v17);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800C9740,
      &v42);
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v42) = 0;
      FormatRRASErrorString(&v42, L"RasSrvrActivateIpv6Address: RDID- %ws Address = ", v38);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v42);
    }
  }
  if ( (byte_1800C8404 & 0x10) != 0 )
    McTemplateU0zqbr1_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasDdmTraceByteBuffer,
      (unsigned int)L"RasDDM Packet buffer",
      16,
      (__int64)Addr);
  EnterCriticalSection(&RasSrvrCriticalSection);
  v18 = *a1;
  v32 = *Addr;
  v31 = v18;
  Aipv6Node = RasSrvrFindAipv6Node(&v31, &v32, 0);
  if ( Aipv6Node )
  {
    *((_DWORD *)Aipv6Node + 14) |= 2u;
    v20 = CreateOrSetOrDeleteIpv6NeighborEntry(&v27, v16, 0, Addr);
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v42) = 0;
      FormatRRASErrorString(&v42, L"Create Ipv6 Neighbor for Global addr: 0x%x", v20);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v42);
    }
    v30[1] = *(_QWORD *)&Addr->u.Word[4];
    v21 = CreateOrSetOrDeleteIpv6NeighborEntry(&v27, v16, 0, v30);
    RasSrvrSetProxyArpV6(Addr, 1, &v35, v28, a1);
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v42) = 0;
      FormatRRASErrorString(&v42, L"Create Ipv6 Neighbor for link-local addr: 0x%x", v21);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v42);
    }
    if ( a3 == 2 )
    {
      v22 = SetIpv6InterfacePropertiesUsingLuidForDD(v16);
      v23 = v22;
      if ( (_QWORD)xmmword_1800C9740 )
      {
        LOWORD(v42) = 0;
        FormatRRASErrorString(&v42, L"SetIpv6InterfacePropertiesUsingLuidForDD returned 0x%x", v22);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800C9740,
          &v42);
      }
      v31 = *a1;
      if ( !(unsigned int)RasGetRoutingDomainAddressPool(&v31, 2, InterfaceIndex) )
      {
        v24 = *(_QWORD *)InterfaceIndex;
        if ( *(_QWORD *)InterfaceIndex )
        {
          InterfaceIndex[0] = 0;
          v23 = ConvertInterfaceLuidToIndex(v16, InterfaceIndex);
          if ( !v23 )
            v23 = AddOrRemoveIpv6PrefixForAdvertisement(v24, InterfaceIndex[0], 0, a5 != 0 ? 4096 : 256);
        }
        v31 = *a1;
        v25 = RasReleaseRoutingDomainAddressPool(&v31);
        if ( v25 )
        {
          if ( !(_QWORD)xmmword_1800C9740 )
            goto LABEL_38;
          LOWORD(v42) = 0;
          FormatRRASErrorString(&v42, L"RasReleaseRoutingDomainAddressPool failed to release lock and returned %d", v25);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800C9740,
            &v42);
        }
      }
      if ( (_QWORD)xmmword_1800C9740 )
      {
        LOWORD(v42) = 0;
        FormatRRASErrorString(&v42, L"AddOrRemoveIpv6Prefix returned 0x%x", v23);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800C9740,
          &v42);
      }
    }
  }
  else
  {
    RtlIpv6AddressToStringA(Addr, S);
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v42) = 0;
      FormatRRASErrorString(&v42, L"Couldn't find address %hs in Acquired Ip Addresses list", S);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v42);
    }
    v12 = 716;
  }
LABEL_38:
  LeaveCriticalSection(&RasSrvrCriticalSection);
  return v12;
}

```

## disassembly

```asm
0x180053580  mov     [rsp-8+arg_10], rbx
0x180053585  push    rbp
0x180053586  push    rsi
0x180053587  push    rdi
0x180053588  push    r12
0x18005358a  push    r13
0x18005358c  push    r14
0x18005358e  push    r15
0x180053590  lea     rbp, [rsp-8D0h]
0x180053598  sub     rsp, 9D0h
0x18005359f  mov     rax, cs:__security_cookie
0x1800535a6  xor     rax, rsp
0x1800535a9  mov     [rbp+900h+var_40], rax
0x1800535b0  mov     rdi, rdx
0x1800535b3  mov     [rsp+0A00h+var_9B8], 80FEh
0x1800535bc  mov     rdx, rcx
0x1800535bf  mov     [rsp+0A00h+var_9C8], 1
0x1800535c7  mov     r14, rcx
0x1800535ca  xor     r13d, r13d
0x1800535cd  lea     rcx, [rbp+900h+var_948]
0x1800535d1  mov     [rsp+0A00h+var_9D0], r13
0x1800535d6  mov     rsi, r9
0x1800535d9  mov     r12d, r8d
0x1800535dc  call    RasRdGetNboServerIpv6Address
0x1800535e1  xor     edx, edx; Val
0x1800535e3  mov     qword ptr [rsp+0A00h+InterfaceIndex], r13
0x1800535e8  mov     r8d, 7FCh; Size
0x1800535ee  lea     rcx, [rbp+900h+var_83C]; void *
0x1800535f5  movups  xmm0, xmmword ptr [rax]
0x1800535f8  movups  xmm1, xmmword ptr [rax+10h]
0x1800535fc  movups  [rbp+900h+var_980], xmm0
0x180053600  movups  xmm0, xmmword ptr [rax+20h]
0x180053604  mov     eax, [rax+30h]
0x180053607  movups  [rbp+900h+var_970], xmm1
0x18005360b  mov     [rbp+900h+var_950], eax
0x18005360e  xor     eax, eax
0x180053610  movaps  xmm1, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x180053617  movups  xmmword ptr [rbp+900h+var_960.u], xmm0
0x18005361b  mov     [rbp+900h+var_8C2], ax
0x18005361f  movaps  xmm0, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x180053626  movaps  [rbp+900h+var_910], xmm0
0x18005362a  movaps  xmm0, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x180053631  movaps  [rbp+900h+var_8F0], xmm0
0x180053635  movups  xmm0, xmmword ptr cs:a00000000000000+3Eh; "000000}"
0x18005363c  mov     [rbp+900h+var_840], r13d
0x180053643  movaps  [rbp+900h+var_900], xmm1
0x180053647  movaps  xmm1, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x18005364e  movaps  xmmword ptr [rbp+900h+var_8E0], xmm1
0x180053652  movups  xmmword ptr [rbp+900h+var_8E0+0Eh], xmm0
0x180053656  call    memset_0
0x18005365b  lea     r8d, [r13+10h]; Size
0x18005365f  mov     rcx, r14; Buf1
0x180053662  lea     rdx, GUID_NULL; Buf2
0x180053669  call    memcmp_0
0x18005366e  test    eax, eax
0x180053670  jnz     short loc_180053677
0x180053672  mov     r15d, r13d
0x180053675  jmp     short loc_1800536EA
0x180053677  lea     r9, [rsp+0A00h+var_9C8]
0x18005367c  mov     edx, 100h
0x180053681  mov     r8d, 4
0x180053687  mov     rcx, r14
0x18005368a  call    GetRoutingDomainConfigData
0x18005368f  mov     r15d, eax
0x180053692  test    eax, eax
0x180053694  jz      short loc_1800536DE
0x180053696  cmp     qword ptr cs:xmmword_1800C9740, r13
0x18005369d  jz      short loc_1800536DE
0x18005369f  mov     r8d, eax
0x1800536a2  mov     word ptr [rbp+900h+var_840], r13w
0x1800536aa  lea     rdx, aRassrvrstopGet; "RasSrvrStop: GetRoutingDomainConfigData"...
0x1800536b1  lea     rcx, [rbp+900h+var_840]
0x1800536b8  call    FormatRRASErrorString
0x1800536bd  mov     rdx, qword ptr cs:xmmword_1800C9740
0x1800536c4  lea     r8, [rbp+900h+var_840]
0x1800536cb  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800536d2  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800536d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800536de  lea     r8, [rbp+900h+var_910]
0x1800536e2  mov     rcx, r14
0x1800536e5  call    MprConvertGuidToString
0x1800536ea  test    r12d, r12d
0x1800536ed  jnz     short loc_180053743
0x1800536ef  mov     rax, [rsp+0A00h+var_9D0]
0x1800536f4  mov     rcx, 0FFFFFFFFFFFFh
0x1800536fe  and     rax, rcx
0x180053701  mov     rcx, 17000000000000h
0x18005370b  or      rax, rcx
0x18005370e  mov     rcx, r14
0x180053711  mov     [rsp+0A00h+var_9D0], rax
0x180053716  call    RasRdGetServerAdapterLuidIndex
0x18005371b  mov     rcx, [rsp+0A00h+var_9D0]
0x180053720  mov     r8d, eax
0x180053723  and     r8d, 0FFFFFFh
0x18005372a  mov     rax, 0FFFF000000000000h
0x180053734  shl     r8, 18h
0x180053738  and     rcx, rax
0x18005373b  or      r8, rcx
0x18005373e  mov     rbx, rsi
0x180053741  jmp     short loc_18005374B
0x180053743  mov     r8, [rsi]
0x180053746  lea     rbx, [rsp+0A00h+var_9D0]
0x18005374b  cmp     qword ptr cs:xmmword_1800C9740, r13
0x180053752  mov     [rsp+0A00h+var_9D0], r8
0x180053757  jz      loc_180053805
0x18005375d  mov     word ptr [rbp+900h+var_840], r13w
0x180053765  test    rbx, rbx
0x180053768  jz      short loc_18005377A
0x18005376a  mov     r9, [rbx]
0x18005376d  shr     r9, 18h
0x180053771  and     r9d, 0FFFFFFh
0x180053778  jmp     short loc_18005377D
0x18005377a  mov     r9, r13
0x18005377d  shr     r8, 18h
0x180053781  lea     rdx, aRassrvractivat_1; "RasSrvrActivateIpv6Address: InterfaceLu"...
0x180053788  and     r8d, 0FFFFFFh
0x18005378f  lea     rcx, [rbp+900h+var_840]
0x180053796  call    FormatRRASErrorString
0x18005379b  mov     rdx, qword ptr cs:xmmword_1800C9740
0x1800537a2  lea     r8, [rbp+900h+var_840]
0x1800537a9  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800537b0  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800537b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800537bc  cmp     qword ptr cs:xmmword_1800C9740, r13
0x1800537c3  jz      short loc_180053805
0x1800537c5  lea     r8, [rbp+900h+var_910]
0x1800537c9  mov     word ptr [rbp+900h+var_840], r13w
0x1800537d1  lea     rdx, aRassrvractivat_0; "RasSrvrActivateIpv6Address: RDID- %ws A"...
0x1800537d8  lea     rcx, [rbp+900h+var_840]
0x1800537df  call    FormatRRASErrorString
0x1800537e4  mov     rdx, qword ptr cs:xmmword_1800C9740
0x1800537eb  lea     r8, [rbp+900h+var_840]
0x1800537f2  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800537f9  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180053800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053805  test    cs:byte_1800C8404, 10h
0x18005380c  jz      short loc_180053833
0x18005380e  mov     r9d, 10h
0x180053814  mov     [rsp+0A00h+var_9E0], rdi
0x180053819  lea     r8, aRasddmPacketBu; "RasDDM Packet buffer"
0x180053820  lea     rdx, RasDdmTraceByteBuffer
0x180053827  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18005382e  call    McTemplateU0zqbr1_EventWriteTransfer
0x180053833  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005383a  call    cs:__imp_EnterCriticalSection
0x180053840  movups  xmm0, xmmword ptr [rdi]
0x180053843  xor     r8d, r8d; int
0x180053846  lea     rdx, [rsp+0A00h+var_990]; struct in6_addr
0x18005384b  movups  xmm1, xmmword ptr [r14]
0x18005384f  lea     rcx, [rsp+0A00h+var_9A0]; struct _GUID
0x180053854  movdqu  xmmword ptr [rsp+0A00h+var_990.u], xmm0
0x18005385a  movdqu  xmmword ptr [rsp+0A00h+var_9A0.Data1], xmm1
0x180053860  call    ?RasSrvrFindAipv6Node@@YAPEAU_ACQUIRED_IPv6ADDR@@U_GUID@@Uin6_addr@@H@Z; RasSrvrFindAipv6Node(_GUID,in6_addr,int)
0x180053865  test    rax, rax
0x180053868  jnz     short loc_1800538CB
0x18005386a  lea     rdx, [rbp+900h+S]; S
0x18005386e  mov     rcx, rdi; Addr
0x180053871  call    cs:__imp_RtlIpv6AddressToStringA
0x180053877  cmp     qword ptr cs:xmmword_1800C9740, r13
0x18005387e  jz      short loc_1800538C0
0x180053880  lea     r8, [rbp+900h+S]
0x180053884  mov     word ptr [rbp+900h+var_840], r13w
0x18005388c  lea     rdx, aCouldnTFindAdd; "Couldn't find address %hs in Acquired I"...
0x180053893  lea     rcx, [rbp+900h+var_840]
0x18005389a  call    FormatRRASErrorString
0x18005389f  mov     rdx, qword ptr cs:xmmword_1800C9740
0x1800538a6  lea     r8, [rbp+900h+var_840]
0x1800538ad  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800538b4  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800538bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800538c0  mov     r15d, 2CCh
0x1800538c6  jmp     loc_180053B24
0x1800538cb  or      dword ptr [rax+38h], 2
0x1800538cf  lea     rcx, [rsp+0A00h+var_9D0]
0x1800538d4  mov     r9, rdi
0x1800538d7  xor     r8d, r8d
0x1800538da  mov     rdx, rbx
0x1800538dd  call    CreateOrSetOrDeleteIpv6NeighborEntry
0x1800538e2  cmp     qword ptr cs:xmmword_1800C9740, r13
0x1800538e9  jz      short loc_18005392A
0x1800538eb  mov     r8d, eax
0x1800538ee  mov     word ptr [rbp+900h+var_840], r13w
0x1800538f6  lea     rdx, aCreateIpv6Neig_0; "Create Ipv6 Neighbor for Global addr: 0"...
0x1800538fd  lea     rcx, [rbp+900h+var_840]
0x180053904  call    FormatRRASErrorString
0x180053909  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180053910  lea     r8, [rbp+900h+var_840]
0x180053917  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005391e  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180053925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005392a  mov     rax, [rdi+8]
0x18005392e  lea     r9, [rsp+0A00h+var_9B8]
0x180053933  xor     r8d, r8d
0x180053936  mov     [rsp+0A00h+var_9B0], rax
0x18005393b  mov     rdx, rbx
0x18005393e  lea     rcx, [rsp+0A00h+var_9D0]
0x180053943  call    CreateOrSetOrDeleteIpv6NeighborEntry
0x180053948  mov     r9d, [rsp+0A00h+var_9C8]; unsigned int
0x18005394d  lea     r8, [rbp+900h+var_960]; struct in6_addr *
0x180053951  mov     edx, 1; int
0x180053956  mov     [rsp+0A00h+var_9E0], r14; struct _GUID *
0x18005395b  mov     rcx, rdi; Addr
0x18005395e  mov     esi, eax
0x180053960  call    ?RasSrvrSetProxyArpV6@@YAXPEBUin6_addr@@H0IPEBU_GUID@@@Z; RasSrvrSetProxyArpV6(in6_addr const *,int,in6_addr const *,uint,_GUID const *)
0x180053965  cmp     qword ptr cs:xmmword_1800C9740, r13
0x18005396c  jz      short loc_1800539AD
0x18005396e  mov     r8d, esi
0x180053971  mov     word ptr [rbp+900h+var_840], r13w
0x180053979  lea     rdx, aCreateIpv6Neig; "Create Ipv6 Neighbor for link-local add"...
0x180053980  lea     rcx, [rbp+900h+var_840]
0x180053987  call    FormatRRASErrorString
0x18005398c  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180053993  lea     r8, [rbp+900h+var_840]
0x18005399a  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800539a1  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800539a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800539ad  cmp     r12d, 2
0x1800539b1  jnz     loc_180053B24
0x1800539b7  mov     rcx, rbx; union _NET_LUID_LH *
0x1800539ba  call    ?SetIpv6InterfacePropertiesUsingLuidForDD@@YAKPEAT_NET_LUID_LH@@@Z; SetIpv6InterfacePropertiesUsingLuidForDD(_NET_LUID_LH *)
0x1800539bf  cmp     qword ptr cs:xmmword_1800C9740, r13
0x1800539c6  mov     esi, eax
0x1800539c8  jz      short loc_180053A09
0x1800539ca  mov     r8d, eax
0x1800539cd  mov     word ptr [rbp+900h+var_840], r13w
0x1800539d5  lea     rdx, aSetipv6interfa_0; "SetIpv6InterfacePropertiesUsingLuidForD"...
0x1800539dc  lea     rcx, [rbp+900h+var_840]
0x1800539e3  call    FormatRRASErrorString
0x1800539e8  mov     rdx, qword ptr cs:xmmword_1800C9740
0x1800539ef  lea     r8, [rbp+900h+var_840]
0x1800539f6  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800539fd  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180053a04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053a09  movups  xmm0, xmmword ptr [r14]
0x180053a0d  lea     r8, [rsp+0A00h+InterfaceIndex]
0x180053a12  mov     edx, 2
0x180053a17  lea     rcx, [rsp+0A00h+var_9A0]
0x180053a1c  movdqu  xmmword ptr [rsp+0A00h+var_9A0.Data1], xmm0
0x180053a22  call    RasGetRoutingDomainAddressPool
0x180053a27  test    eax, eax
0x180053a29  jnz     loc_180053ADC
0x180053a2f  mov     r12, qword ptr [rsp+0A00h+InterfaceIndex]
0x180053a34  test    r12, r12
0x180053a37  jz      short loc_180053A78
0x180053a39  neg     [rbp+900h+arg_20]
0x180053a3f  lea     rdx, [rsp+0A00h+InterfaceIndex]; InterfaceIndex
0x180053a44  mov     rcx, rbx; InterfaceLuid
0x180053a47  mov     [rsp+0A00h+InterfaceIndex], r13d
0x180053a4c  sbb     edi, edi
0x180053a4e  and     edi, 0F00h
0x180053a54  call    cs:__imp_ConvertInterfaceLuidToIndex
0x180053a5a  mov     esi, eax
0x180053a5c  test    eax, eax
0x180053a5e  jnz     short loc_180053A78
0x180053a60  mov     edx, [rsp+0A00h+InterfaceIndex]
0x180053a64  lea     r9d, [rdi+100h]
0x180053a6b  xor     r8d, r8d
0x180053a6e  mov     rcx, r12
0x180053a71  call    AddOrRemoveIpv6PrefixForAdvertisement
0x180053a76  mov     esi, eax
0x180053a78  movups  xmm0, xmmword ptr [r14]
0x180053a7c  lea     rcx, [rsp+0A00h+var_9A0]
0x180053a81  movdqu  xmmword ptr [rsp+0A00h+var_9A0.Data1], xmm0
0x180053a87  call    RasReleaseRoutingDomainAddressPool
0x180053a8c  test    eax, eax
0x180053a8e  jz      short loc_180053ADC
0x180053a90  cmp     qword ptr cs:xmmword_1800C9740, r13
0x180053a97  jz      loc_180053B24
0x180053a9d  mov     r8d, eax
0x180053aa0  mov     word ptr [rbp+900h+var_840], r13w
0x180053aa8  lea     rdx, aRasreleaserout; "RasReleaseRoutingDomainAddressPool fail"...
0x180053aaf  lea     rcx, [rbp+900h+var_840]
0x180053ab6  call    FormatRRASErrorString
0x180053abb  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180053ac2  lea     r8, [rbp+900h+var_840]
0x180053ac9  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180053ad0  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180053ad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053adc  cmp     qword ptr cs:xmmword_1800C9740, r13
0x180053ae3  jz      short loc_180053B24
0x180053ae5  mov     r8d, esi
0x180053ae8  mov     word ptr [rbp+900h+var_840], r13w
0x180053af0  lea     rdx, aAddorremoveipv; "AddOrRemoveIpv6Prefix returned 0x%x"
0x180053af7  lea     rcx, [rbp+900h+var_840]
0x180053afe  call    FormatRRASErrorString
0x180053b03  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180053b0a  lea     r8, [rbp+900h+var_840]
0x180053b11  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180053b18  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180053b1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b24  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180053b2b  call    cs:__imp_LeaveCriticalSection
0x180053b31  mov     eax, r15d
0x180053b34  mov     rcx, [rbp+900h+var_40]
0x180053b3b  xor     rcx, rsp; StackCookie
0x180053b3e  call    __security_check_cookie
0x180053b43  mov     rbx, [rsp+0A00h+arg_10]
0x180053b4b  add     rsp, 9D0h
0x180053b52  pop     r15
0x180053b54  pop     r14
  ... truncated ...
```

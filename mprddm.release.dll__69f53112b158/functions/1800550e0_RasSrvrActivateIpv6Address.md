# RasSrvrActivateIpv6Address

- ea: `0x1800550e0`
- end: `0x1800556e9`
- name: `RasSrvrActivateIpv6Address`
- size: `1545`
- prototype: `__int64 __usercall@<rax>(struct _GUID *@<rcx>, struct in6_addr *Addr@<rdx>, char)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180027ec0`
- `0x18002b140`
- `0x18004eb54`
- `0x18004f8c4`
- `0x1800500c0`
- `0x1800550e0`
- `0x18005a844`
- `0x18005aa44`
- `0x18005aaf8`
- `0x18005ad18`
- `0x1800755b8`
- `0x1800771b8`
- `0x1800785b8`
- `0x180079428`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800556af`
- `KERNEL32!LeaveCriticalSection` at `0x1800556af`
- `KERNEL32!EnterCriticalSection` at `0x1800553ac`
- `KERNEL32!EnterCriticalSection` at `0x1800553ac`
- `ntdll!RtlIpv6AddressToStringA` at `0x1800553e8`
- `ntdll!RtlIpv6AddressToStringA` at `0x1800553e8`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x1800555c3`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x1800555c3`

## string_xrefs

- `0x180055220`: `RasSrvrStop: GetRoutingDomainConfigData (compartmentId) failed and returned %d`
- `0x180055473`: `Create Ipv6 Neighbor for Global addr: 0x%x`
- `0x1800554f7`: `Create Ipv6 Neighbor for link-local addr: 0x%x`
- `0x180055674`: `AddOrRemoveIpv6Prefix returned 0x%x`

## pseudocode

```c
__int64 __fastcall RasSrvrActivateIpv6Address(struct _GUID *a1, struct in6_addr *Addr, int a3, NET_LUID *a4, char a5)
{
  unsigned int v9; // r14d
  __int64 NboServerIpv6Address; // rax
  __int128 v11; // xmm1
  struct in6_addr v12; // xmm0
  unsigned int RoutingDomainConfigData; // eax
  __int64 v14; // rdx
  NET_LUID *v15; // rbx
  unsigned __int64 Value; // rax
  __int64 v17; // r9
  struct _GUID v18; // xmm1
  struct _ACQUIRED_IPv6ADDR *Aipv6Node; // rax
  unsigned int v20; // eax
  unsigned int v21; // r15d
  unsigned int v22; // eax
  unsigned int v23; // esi
  __int64 v24; // r15
  unsigned int v25; // eax
  unsigned __int64 v27; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v28; // [rsp+38h] [rbp-C8h] BYREF
  ULONG InterfaceIndex[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v30[3]; // [rsp+48h] [rbp-B8h] BYREF
  struct _GUID v31; // [rsp+60h] [rbp-A0h] BYREF
  struct in6_addr v32; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v33[56]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v34; // [rsp+B8h] [rbp-48h]
  __int128 v35; // [rsp+C8h] [rbp-38h]
  struct in6_addr v36; // [rsp+D8h] [rbp-28h] BYREF
  int v37; // [rsp+E8h] [rbp-18h]
  _OWORD v38[4]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v39; // [rsp+130h] [rbp+30h]
  int v40; // [rsp+138h] [rbp+38h]
  wchar_t v41; // [rsp+13Ch] [rbp+3Ch]
  __int16 v42; // [rsp+13Eh] [rbp+3Eh]
  CHAR S[128]; // [rsp+140h] [rbp+40h] BYREF
  int v44; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v45[2044]; // [rsp+1C4h] [rbp+C4h] BYREF

  v30[0] = 33022;
  v28 = 1;
  v27 = 0;
  v9 = 0;
  NboServerIpv6Address = RasRdGetNboServerIpv6Address(v33, a1);
  *(_QWORD *)InterfaceIndex = 0;
  v11 = *(_OWORD *)(NboServerIpv6Address + 16);
  v34 = *(_OWORD *)NboServerIpv6Address;
  v12 = *(struct in6_addr *)(NboServerIpv6Address + 32);
  v37 = *(_DWORD *)(NboServerIpv6Address + 48);
  v36 = v12;
  v40 = *(_DWORD *)L"0}";
  v38[0] = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  v35 = v11;
  v41 = a00000000000000[38];
  v38[2] = *(_OWORD *)L"000-0000-000000000000}";
  v38[1] = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  v39 = *(_QWORD *)L"00000}";
  v38[3] = *(_OWORD *)L"-000000000000}";
  v42 = 0;
  v44 = 0;
  memset_0(v45, 0, sizeof(v45));
  if ( *(_OWORD *)a1 != *(_OWORD *)&GUID_NULL )
  {
    RoutingDomainConfigData = GetRoutingDomainConfigData(a1, 256, 4, &v28);
    v9 = RoutingDomainConfigData;
    if ( RoutingDomainConfigData && (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v44) = 0;
      FormatRRASErrorString(
        &v44,
        L"RasSrvrStop: GetRoutingDomainConfigData (compartmentId) failed and returned %d",
        RoutingDomainConfigData);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v44);
    }
    MprConvertGuidToString(a1, v14, v38);
  }
  if ( a3 )
  {
    Value = a4->Value;
    v15 = (NET_LUID *)&v27;
  }
  else
  {
    v15 = a4;
    Value = ((RasRdGetServerAdapterLuidIndex(a1) & 0xFFFFFF) << 24) | 0x17000000000000LL;
  }
  v27 = Value;
  if ( (_QWORD)xmmword_1800D0740 )
  {
    LOWORD(v44) = 0;
    v17 = v15 ? (v15->Value >> 24) & 0xFFFFFF : 0LL;
    FormatRRASErrorString(
      &v44,
      L"RasSrvrActivateIpv6Address: InterfaceLuid %d Subinterface Luid %d",
      (Value >> 24) & 0xFFFFFF,
      v17);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800D0740,
      &v44);
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v44) = 0;
      FormatRRASErrorString(&v44, L"RasSrvrActivateIpv6Address: RDID- %ws Address = ", v38);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v44);
    }
  }
  if ( (byte_1800CF404 & 0x10) != 0 )
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
    v20 = CreateOrSetOrDeleteIpv6NeighborEntry(&v27, v15, 0, Addr);
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v44) = 0;
      FormatRRASErrorString(&v44, L"Create Ipv6 Neighbor for Global addr: 0x%x", v20);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v44);
    }
    v30[1] = *(_QWORD *)&Addr->u.Word[4];
    v21 = CreateOrSetOrDeleteIpv6NeighborEntry(&v27, v15, 0, v30);
    RasSrvrSetProxyArpV6(Addr, 1, &v36, v28, a1);
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v44) = 0;
      FormatRRASErrorString(&v44, L"Create Ipv6 Neighbor for link-local addr: 0x%x", v21);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v44);
    }
    if ( a3 == 2 )
    {
      v22 = SetIpv6InterfacePropertiesUsingLuidForDD(v15);
      v23 = v22;
      if ( (_QWORD)xmmword_1800D0740 )
      {
        LOWORD(v44) = 0;
        FormatRRASErrorString(&v44, L"SetIpv6InterfacePropertiesUsingLuidForDD returned 0x%x", v22);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v44);
      }
      v31 = *a1;
      if ( !(unsigned int)RasGetRoutingDomainAddressPool(&v31, 2, InterfaceIndex) )
      {
        v24 = *(_QWORD *)InterfaceIndex;
        if ( *(_QWORD *)InterfaceIndex )
        {
          InterfaceIndex[0] = 0;
          v23 = ConvertInterfaceLuidToIndex(v15, InterfaceIndex);
          if ( !v23 )
            v23 = AddOrRemoveIpv6PrefixForAdvertisement(v24, InterfaceIndex[0], 0, a5 != 0 ? 4096 : 256);
        }
        v31 = *a1;
        v25 = RasReleaseRoutingDomainAddressPool(&v31);
        if ( v25 )
        {
          if ( !(_QWORD)xmmword_1800D0740 )
            goto LABEL_37;
          LOWORD(v44) = 0;
          FormatRRASErrorString(&v44, L"RasReleaseRoutingDomainAddressPool failed to release lock and returned %d", v25);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800D0740,
            &v44);
        }
      }
      if ( (_QWORD)xmmword_1800D0740 )
      {
        LOWORD(v44) = 0;
        FormatRRASErrorString(&v44, L"AddOrRemoveIpv6Prefix returned 0x%x", v23);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v44);
      }
    }
  }
  else
  {
    RtlIpv6AddressToStringA(Addr, S);
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v44) = 0;
      FormatRRASErrorString(&v44, L"Couldn't find address %hs in Acquired Ip Addresses list", S);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v44);
    }
    v9 = 716;
  }
LABEL_37:
  LeaveCriticalSection(&RasSrvrCriticalSection);
  return v9;
}

```

## disassembly

```asm
0x1800550e0  mov     [rsp-8+arg_10], rbx
0x1800550e5  push    rbp
0x1800550e6  push    rsi
0x1800550e7  push    rdi
0x1800550e8  push    r12
0x1800550ea  push    r13
0x1800550ec  push    r14
0x1800550ee  push    r15
0x1800550f0  lea     rbp, [rsp-8D0h]
0x1800550f8  sub     rsp, 9D0h
0x1800550ff  mov     rax, cs:__security_cookie
0x180055106  xor     rax, rsp
0x180055109  mov     [rbp+900h+var_40], rax
0x180055110  mov     rsi, rdx
0x180055113  mov     [rsp+0A00h+var_9B8], 80FEh
0x18005511c  mov     rdx, rcx
0x18005511f  mov     [rsp+0A00h+var_9C8], 1
0x180055127  mov     rdi, rcx
0x18005512a  xor     r13d, r13d
0x18005512d  lea     rcx, [rbp+900h+var_980]
0x180055131  mov     [rsp+0A00h+var_9D0], r13
0x180055136  mov     r15, r9
0x180055139  mov     r12d, r8d
0x18005513c  mov     r14d, r13d
0x18005513f  call    RasRdGetNboServerIpv6Address
0x180055144  xor     edx, edx; Val
0x180055146  mov     qword ptr [rsp+0A00h+InterfaceIndex], r13
0x18005514b  mov     r8d, 7FCh; Size
0x180055151  lea     rcx, [rbp+900h+var_83C]; void *
0x180055158  movups  xmm0, xmmword ptr [rax]
0x18005515b  movups  xmm1, xmmword ptr [rax+10h]
0x18005515f  movups  [rbp+900h+var_948], xmm0
0x180055163  movups  xmm0, xmmword ptr [rax+20h]
0x180055167  mov     eax, [rax+30h]
0x18005516a  mov     [rbp+900h+var_918], eax
0x18005516d  mov     eax, dword ptr cs:a00000000000000+48h; "0}"
0x180055173  movups  xmmword ptr [rbp+900h+var_928.u], xmm0
0x180055177  mov     [rbp+900h+var_8C8], eax
0x18005517a  movaps  xmm0, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x180055181  movzx   eax, word ptr cs:a00000000000000+4Ch; ""
0x180055188  movaps  [rbp+900h+var_910], xmm0
0x18005518c  movaps  xmm0, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x180055193  movups  [rbp+900h+var_938], xmm1
0x180055197  mov     [rbp+900h+var_8C4], ax
0x18005519b  xor     eax, eax
0x18005519d  movaps  xmm1, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x1800551a4  movaps  [rbp+900h+var_8F0], xmm0
0x1800551a8  movsd   xmm0, qword ptr cs:a00000000000000+40h; "00000}"
0x1800551b0  movaps  [rbp+900h+var_900], xmm1
0x1800551b4  movaps  xmm1, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x1800551bb  movsd   [rbp+900h+var_8D0], xmm0
0x1800551c0  movaps  [rbp+900h+var_8E0], xmm1
0x1800551c4  mov     [rbp+900h+var_8C2], ax
0x1800551c8  mov     [rbp+900h+var_840], r13d
0x1800551cf  call    memset_0
0x1800551d4  mov     rax, [rdi]
0x1800551d7  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800551de  jnz     short loc_1800551ED
0x1800551e0  mov     rax, [rdi+8]
0x1800551e4  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800551eb  jz      short loc_180055260
0x1800551ed  lea     r9, [rsp+0A00h+var_9C8]
0x1800551f2  mov     edx, 100h
0x1800551f7  mov     r8d, 4
0x1800551fd  mov     rcx, rdi
0x180055200  call    GetRoutingDomainConfigData
0x180055205  mov     r14d, eax
0x180055208  test    eax, eax
0x18005520a  jz      short loc_180055254
0x18005520c  cmp     qword ptr cs:xmmword_1800D0740, r13
0x180055213  jz      short loc_180055254
0x180055215  mov     r8d, eax
0x180055218  mov     word ptr [rbp+900h+var_840], r13w
0x180055220  lea     rdx, aRassrvrstopGet; "RasSrvrStop: GetRoutingDomainConfigData"...
0x180055227  lea     rcx, [rbp+900h+var_840]
0x18005522e  call    FormatRRASErrorString
0x180055233  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18005523a  lea     r8, [rbp+900h+var_840]
0x180055241  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180055248  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005524f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055254  lea     r8, [rbp+900h+var_910]
0x180055258  mov     rcx, rdi
0x18005525b  call    MprConvertGuidToString
0x180055260  test    r12d, r12d
0x180055263  jnz     short loc_1800552B4
0x180055265  mov     rax, [rsp+0A00h+var_9D0]
0x18005526a  mov     rcx, 0FFFFFFFFFFFFh
0x180055274  and     rax, rcx
0x180055277  mov     rcx, 17000000000000h
0x180055281  or      rax, rcx
0x180055284  mov     rcx, rdi
0x180055287  mov     [rsp+0A00h+var_9D0], rax
0x18005528c  call    RasRdGetServerAdapterLuidIndex
0x180055291  mov     rcx, [rsp+0A00h+var_9D0]
0x180055296  and     eax, 0FFFFFFh
0x18005529b  mov     rdx, 0FFFF000000000000h
0x1800552a5  shl     rax, 18h
0x1800552a9  and     rcx, rdx
0x1800552ac  mov     rbx, r15
0x1800552af  or      rax, rcx
0x1800552b2  jmp     short loc_1800552BC
0x1800552b4  mov     rax, [r15]
0x1800552b7  lea     rbx, [rsp+0A00h+var_9D0]
0x1800552bc  cmp     qword ptr cs:xmmword_1800D0740, r13
0x1800552c3  mov     [rsp+0A00h+var_9D0], rax
0x1800552c8  jz      loc_180055377
0x1800552ce  mov     word ptr [rbp+900h+var_840], r13w
0x1800552d6  test    rbx, rbx
0x1800552d9  jz      short loc_1800552EB
0x1800552db  mov     r9, [rbx]
0x1800552de  shr     r9, 18h
0x1800552e2  and     r9d, 0FFFFFFh
0x1800552e9  jmp     short loc_1800552EE
0x1800552eb  mov     r9, r13
0x1800552ee  shr     rax, 18h
0x1800552f2  lea     rdx, aRassrvractivat_1; "RasSrvrActivateIpv6Address: InterfaceLu"...
0x1800552f9  and     eax, 0FFFFFFh
0x1800552fe  lea     rcx, [rbp+900h+var_840]
0x180055305  mov     r8d, eax
0x180055308  call    FormatRRASErrorString
0x18005530d  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180055314  lea     r8, [rbp+900h+var_840]
0x18005531b  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180055322  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180055329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005532e  cmp     qword ptr cs:xmmword_1800D0740, r13
0x180055335  jz      short loc_180055377
0x180055337  lea     r8, [rbp+900h+var_910]
0x18005533b  mov     word ptr [rbp+900h+var_840], r13w
0x180055343  lea     rdx, aRassrvractivat_0; "RasSrvrActivateIpv6Address: RDID- %ws A"...
0x18005534a  lea     rcx, [rbp+900h+var_840]
0x180055351  call    FormatRRASErrorString
0x180055356  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18005535d  lea     r8, [rbp+900h+var_840]
0x180055364  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005536b  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180055372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055377  mov     r9d, 10h
0x18005537d  test    cs:byte_1800CF404, r9b
0x180055384  jz      short loc_1800553A5
0x180055386  lea     r8, aRasddmPacketBu; "RasDDM Packet buffer"
0x18005538d  mov     [rsp+0A00h+var_9E0], rsi
0x180055392  lea     rdx, RasDdmTraceByteBuffer
0x180055399  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800553a0  call    McTemplateU0zqbr1_EventWriteTransfer
0x1800553a5  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800553ac  call    cs:__imp_EnterCriticalSection
0x1800553b3  nop     dword ptr [rax+rax+00h]
0x1800553b8  movups  xmm0, xmmword ptr [rsi]
0x1800553bb  xor     r8d, r8d; int
0x1800553be  lea     rdx, [rsp+0A00h+var_990]; struct in6_addr
0x1800553c3  movups  xmm1, xmmword ptr [rdi]
0x1800553c6  lea     rcx, [rsp+0A00h+var_9A0]; struct _GUID
0x1800553cb  movdqu  xmmword ptr [rsp+0A00h+var_990.u], xmm0
0x1800553d1  movdqu  xmmword ptr [rsp+0A00h+var_9A0.Data1], xmm1
0x1800553d7  call    ?RasSrvrFindAipv6Node@@YAPEAU_ACQUIRED_IPv6ADDR@@U_GUID@@Uin6_addr@@H@Z; RasSrvrFindAipv6Node(_GUID,in6_addr,int)
0x1800553dc  test    rax, rax
0x1800553df  jnz     short loc_180055448
0x1800553e1  lea     rdx, [rbp+900h+S]; S
0x1800553e5  mov     rcx, rsi; Addr
0x1800553e8  call    cs:__imp_RtlIpv6AddressToStringA
0x1800553ef  nop     dword ptr [rax+rax+00h]
0x1800553f4  cmp     qword ptr cs:xmmword_1800D0740, r13
0x1800553fb  jz      short loc_18005543D
0x1800553fd  lea     r8, [rbp+900h+S]
0x180055401  mov     word ptr [rbp+900h+var_840], r13w
0x180055409  lea     rdx, aCouldnTFindAdd; "Couldn't find address %hs in Acquired I"...
0x180055410  lea     rcx, [rbp+900h+var_840]
0x180055417  call    FormatRRASErrorString
0x18005541c  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180055423  lea     r8, [rbp+900h+var_840]
0x18005542a  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180055431  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180055438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005543d  mov     r14d, 2CCh
0x180055443  jmp     loc_1800556A8
0x180055448  or      dword ptr [rax+38h], 2
0x18005544c  lea     rcx, [rsp+0A00h+var_9D0]
0x180055451  mov     r9, rsi
0x180055454  xor     r8d, r8d
0x180055457  mov     rdx, rbx
0x18005545a  call    CreateOrSetOrDeleteIpv6NeighborEntry
0x18005545f  cmp     qword ptr cs:xmmword_1800D0740, r13
0x180055466  jz      short loc_1800554A7
0x180055468  mov     r8d, eax
0x18005546b  mov     word ptr [rbp+900h+var_840], r13w
0x180055473  lea     rdx, aCreateIpv6Neig_0; "Create Ipv6 Neighbor for Global addr: 0"...
0x18005547a  lea     rcx, [rbp+900h+var_840]
0x180055481  call    FormatRRASErrorString
0x180055486  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18005548d  lea     r8, [rbp+900h+var_840]
0x180055494  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005549b  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800554a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800554a7  mov     rax, [rsi+8]
0x1800554ab  lea     r9, [rsp+0A00h+var_9B8]
0x1800554b0  xor     r8d, r8d
0x1800554b3  mov     [rsp+0A00h+var_9B0], rax
0x1800554b8  mov     rdx, rbx
0x1800554bb  lea     rcx, [rsp+0A00h+var_9D0]
0x1800554c0  call    CreateOrSetOrDeleteIpv6NeighborEntry
0x1800554c5  mov     r9d, [rsp+0A00h+var_9C8]; unsigned int
0x1800554ca  lea     r8, [rbp+900h+var_928]; struct in6_addr *
0x1800554ce  mov     edx, 1; int
0x1800554d3  mov     [rsp+0A00h+var_9E0], rdi; struct _GUID *
0x1800554d8  mov     rcx, rsi; Addr
0x1800554db  mov     r15d, eax
0x1800554de  call    ?RasSrvrSetProxyArpV6@@YAXPEBUin6_addr@@H0IPEBU_GUID@@@Z; RasSrvrSetProxyArpV6(in6_addr const *,int,in6_addr const *,uint,_GUID const *)
0x1800554e3  cmp     qword ptr cs:xmmword_1800D0740, r13
0x1800554ea  jz      short loc_18005552B
0x1800554ec  mov     r8d, r15d
0x1800554ef  mov     word ptr [rbp+900h+var_840], r13w
0x1800554f7  lea     rdx, aCreateIpv6Neig; "Create Ipv6 Neighbor for link-local add"...
0x1800554fe  lea     rcx, [rbp+900h+var_840]
0x180055505  call    FormatRRASErrorString
0x18005550a  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180055511  lea     r8, [rbp+900h+var_840]
0x180055518  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005551f  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180055526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005552b  cmp     r12d, 2
0x18005552f  jnz     loc_1800556A8
0x180055535  mov     rcx, rbx; union _NET_LUID_LH *
0x180055538  call    ?SetIpv6InterfacePropertiesUsingLuidForDD@@YAKPEAT_NET_LUID_LH@@@Z; SetIpv6InterfacePropertiesUsingLuidForDD(_NET_LUID_LH *)
0x18005553d  cmp     qword ptr cs:xmmword_1800D0740, r13
0x180055544  mov     esi, eax
0x180055546  jz      short loc_180055587
0x180055548  mov     r8d, eax
0x18005554b  mov     word ptr [rbp+900h+var_840], r13w
0x180055553  lea     rdx, aSetipv6interfa_0; "SetIpv6InterfacePropertiesUsingLuidForD"...
0x18005555a  lea     rcx, [rbp+900h+var_840]
0x180055561  call    FormatRRASErrorString
0x180055566  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18005556d  lea     r8, [rbp+900h+var_840]
0x180055574  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005557b  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180055582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055587  movups  xmm0, xmmword ptr [rdi]
0x18005558a  lea     r8, [rsp+0A00h+InterfaceIndex]
0x18005558f  mov     edx, 2
0x180055594  lea     rcx, [rsp+0A00h+var_9A0]
0x180055599  movdqu  xmmword ptr [rsp+0A00h+var_9A0.Data1], xmm0
0x18005559f  call    RasGetRoutingDomainAddressPool
0x1800555a4  test    eax, eax
0x1800555a6  jnz     loc_180055660
0x1800555ac  mov     r15, qword ptr [rsp+0A00h+InterfaceIndex]
0x1800555b1  test    r15, r15
0x1800555b4  jz      short loc_1800555FD
0x1800555b6  lea     rdx, [rsp+0A00h+InterfaceIndex]; InterfaceIndex
0x1800555bb  mov     [rsp+0A00h+InterfaceIndex], r13d
0x1800555c0  mov     rcx, rbx; InterfaceLuid
0x1800555c3  call    cs:__imp_ConvertInterfaceLuidToIndex
0x1800555ca  nop     dword ptr [rax+rax+00h]
0x1800555cf  mov     esi, eax
0x1800555d1  test    eax, eax
0x1800555d3  jnz     short loc_1800555FD
0x1800555d5  neg     [rbp+900h+arg_20]
0x1800555db  mov     rcx, r15
0x1800555de  mov     edx, [rsp+0A00h+InterfaceIndex]
0x1800555e2  sbb     r9d, r9d
0x1800555e5  xor     r8d, r8d
0x1800555e8  and     r9d, 0F00h
0x1800555ef  add     r9d, 100h
0x1800555f6  call    AddOrRemoveIpv6PrefixForAdvertisement
0x1800555fb  mov     esi, eax
0x1800555fd  movups  xmm0, xmmword ptr [rdi]
0x180055600  lea     rcx, [rsp+0A00h+var_9A0]
0x180055605  movdqu  xmmword ptr [rsp+0A00h+var_9A0.Data1], xmm0
0x18005560b  call    RasReleaseRoutingDomainAddressPool
0x180055610  test    eax, eax
0x180055612  jz      short loc_180055660
0x180055614  cmp     qword ptr cs:xmmword_1800D0740, r13
0x18005561b  jz      loc_1800556A8
0x180055621  mov     r8d, eax
0x180055624  mov     word ptr [rbp+900h+var_840], r13w
0x18005562c  lea     rdx, aRasreleaserout; "RasReleaseRoutingDomainAddressPool fail"...
0x180055633  lea     rcx, [rbp+900h+var_840]
0x18005563a  call    FormatRRASErrorString
0x18005563f  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180055646  lea     r8, [rbp+900h+var_840]
0x18005564d  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180055654  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005565b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055660  cmp     qword ptr cs:xmmword_1800D0740, r13
0x180055667  jz      short loc_1800556A8
0x180055669  mov     r8d, esi
0x18005566c  mov     word ptr [rbp+900h+var_840], r13w
0x180055674  lea     rdx, aAddorremoveipv; "AddOrRemoveIpv6Prefix returned 0x%x"
0x18005567b  lea     rcx, [rbp+900h+var_840]
0x180055682  call    FormatRRASErrorString
0x180055687  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18005568e  lea     r8, [rbp+900h+var_840]
0x180055695  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005569c  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800556a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800556a8  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800556af  call    cs:__imp_LeaveCriticalSection
0x1800556b6  nop     dword ptr [rax+rax+00h]
0x1800556bb  mov     eax, r14d
  ... truncated ...
```

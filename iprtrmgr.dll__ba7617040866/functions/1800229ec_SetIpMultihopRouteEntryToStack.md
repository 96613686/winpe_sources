# SetIpMultihopRouteEntryToStack

- ea: `0x1800229ec`
- end: `0x180022f1c`
- name: `SetIpMultihopRouteEntryToStack`
- size: `1328`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180046848`

## callees

- `0x1800010a0`
- `0x180001f90`
- `0x18000ac60`
- `0x180011790`
- `0x1800224b0`
- `0x180022894`
- `0x1800229ec`
- `0x180052c3c`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180022c80`
- `ntdll!RtlNtStatusToDosError` at `0x180022c80`
- `IPHLPAPI!DeleteIpForwardEntry` at `0x180022db9`
- `IPHLPAPI!DeleteIpForwardEntry` at `0x180022db9`
- `WS2_32!__imp_ntohl` at `0x180022bde`
- `WS2_32!__imp_ntohl` at `0x180022bde`

## string_xrefs

- `0x180022ae3`: `SetIpMultihopRouteEntryToStack: NsiGetRoutingDomainIdForCompartment failed with error %d.`
- `0x180022d54`: `Route is owned by the stack, the router manager should not delete the route from the stack. The route type is %d`
- `0x180022dd4`: `DeleteIpForwardEntry returns with 0x%x; Index = %d; Dest = 0x%x; nexthop = 0x%x`

## pseudocode

```c
__int64 __fastcall SetIpMultihopRouteEntryToStack(_DWORD *a1, NET_IF_COMPARTMENT_ID a2, int a3)
{
  ULONG v6; // edi
  ULONG RoutingDomainIdForCompartment; // eax
  DWORD v8; // edx
  DWORD v9; // r8d
  DWORD v10; // ecx
  u_long v11; // eax
  u_long v12; // edx
  int v13; // r9d
  char v14; // cl
  int v15; // r8d
  int v16; // eax
  DWORD dwForwardNextHop; // edx
  NTSTATUS v18; // eax
  ULONG FirstRouteInfoForDestination; // eax
  int v20; // eax
  DWORD v21; // edx
  char v23; // al
  __int64 v24; // [rsp+20h] [rbp-908h]
  __int64 v25; // [rsp+28h] [rbp-900h]
  struct _MIB_IPFORWARDROW pRoute; // [rsp+38h] [rbp-8F0h] BYREF
  __int128 v27; // [rsp+70h] [rbp-8B8h] BYREF
  _OWORD v28[4]; // [rsp+80h] [rbp-8A8h] BYREF
  int v29; // [rsp+C0h] [rbp-868h] BYREF
  __int128 v30; // [rsp+C4h] [rbp-864h]
  __int128 v31; // [rsp+D4h] [rbp-854h]
  int v32; // [rsp+E4h] [rbp-844h]
  int v33; // [rsp+F0h] [rbp-838h] BYREF
  int v34; // [rsp+F4h] [rbp-834h] BYREF

  v33 = 0;
  v6 = 0;
  memset(v28, 0, sizeof(v28));
  v27 = 0;
  memset(&pRoute, 0, sizeof(pRoute));
  memset_0(&v34, 0, 0x7FCu);
  v29 = 0;
  v32 = 0;
  v30 = 0;
  v31 = 0;
  if ( a2 != 1 )
  {
    if ( gIsRtrMgrEtwEnabled )
    {
      RoutingDomainIdForCompartment = NsiGetRoutingDomainIdForCompartment(a2, &v27);
      v6 = RoutingDomainIdForCompartment;
      if ( RoutingDomainIdForCompartment )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          LOWORD(v33) = 0;
          FormatRRASErrorString(
            &v33,
            L"SetIpMultihopRouteEntryToStack: NsiGetRoutingDomainIdForCompartment failed with error %d.",
            RoutingDomainIdForCompartment);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v33);
        }
        return v6;
      }
    }
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v29) = 0;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Entered: SetIpMultihopRouteEntryToStack",
      (unsigned int)&v27,
      0,
      (__int64)&v29);
  }
  v8 = a1[9];
  v9 = a1[2];
  v10 = a1[12];
  pRoute.dwForwardNextHop = a1[8];
  pRoute.dwForwardIfIndex = a1[3];
  pRoute.dwForwardProto = a1[10];
  pRoute.dwForwardAge = a1[11];
  pRoute.dwForwardMetric1 = a1[4];
  pRoute.dwForwardMetric2 = a1[5];
  pRoute.dwForwardMetric3 = a1[6];
  pRoute.dwForwardMetric4 = a1[7];
  pRoute.dwForwardMetric5 = a1[13];
  pRoute.dwForwardDest = v9;
  pRoute.dwForwardMask = v10;
  pRoute.dwForwardPolicy = 0;
  pRoute.dwForwardType = v8;
  pRoute.dwForwardNextHopAS = 0;
  if ( v8 != 2 )
  {
    DWORD1(v28[0]) = v9;
    v11 = ntohl(v10);
    v12 = v11 << 16;
    if ( (v11 & 0x10000) == 0 )
      v12 = v11;
    v13 = (v11 & 0x10000) != 0 ? 0x10 : 0;
    if ( (v12 & 0x100) != 0 )
    {
      LOBYTE(v13) = v13 + 8;
      v12 <<= 8;
    }
    v14 = v13 + 4;
    v15 = 16 * v12;
    if ( (v12 & 0x10) == 0 )
    {
      v15 = v12;
      v14 = v13;
    }
    for ( ; v15; v15 *= 2 )
      ++v14;
    BYTE8(v28[0]) = v14;
    if ( a3 )
      DeleteRTRMgrOwnedRoutesToDestFromStack(v28, 1, a2);
    if ( pRoute.dwForwardProto <= 4 )
      return v6;
    v16 = IsOnLinkRoute(&pRoute, a2);
    dwForwardNextHop = pRoute.dwForwardNextHop;
    if ( v16 )
      dwForwardNextHop = 0;
    pRoute.dwForwardNextHop = dwForwardNextHop;
    v18 = CreateOrSetIpForwardEntry(&pRoute);
    v6 = RtlNtStatusToDosError(v18);
    goto LABEL_38;
  }
  FirstRouteInfoForDestination = GetFirstRouteInfoForDestination(&pRoute, a2);
  v6 = FirstRouteInfoForDestination;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LODWORD(v25) = pRoute.dwForwardNextHop;
    LODWORD(v24) = pRoute.dwForwardDest;
    LOWORD(v33) = 0;
    LOWORD(v29) = 0;
    FormatRRASErrorString(
      &v33,
      L"GetFirstRouteInfoForDestination returns with 0x%x; Index = %d; Dest = 0x%x; nexthop = 0x%x",
      FirstRouteInfoForDestination,
      pRoute.dwForwardIfIndex,
      v24,
      v25);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v33,
        (unsigned int)&v27,
        0,
        (__int64)&v29);
  }
  v20 = IsOnLinkRoute(&pRoute, a2);
  v21 = pRoute.dwForwardNextHop;
  if ( v20 )
    v21 = 0;
  pRoute.dwForwardNextHop = v21;
  if ( v6 )
  {
LABEL_38:
    v23 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v33) = 0;
      LOWORD(v29) = 0;
      FormatRRASErrorString(&v33, L"SetIpForwardEntry returns with 0x%X\n", v6);
      v23 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v33,
          (unsigned int)&v27,
          0,
          (__int64)&v29);
        v23 = Microsoft_Windows_RRASEnableBits;
      }
    }
    goto LABEL_41;
  }
  pRoute.dwForwardType = a1[9];
  if ( pRoute.dwForwardProto > 4 )
  {
    v6 = DeleteIpForwardEntry(&pRoute);
    v23 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL
      || (LODWORD(v25) = pRoute.dwForwardNextHop,
          LODWORD(v24) = pRoute.dwForwardDest,
          LOWORD(v33) = 0,
          LOWORD(v29) = 0,
          FormatRRASErrorString(
            &v33,
            L"DeleteIpForwardEntry returns with 0x%x; Index = %d; Dest = 0x%x; nexthop = 0x%x",
            v6,
            pRoute.dwForwardIfIndex,
            v24,
            v25),
          v23 = Microsoft_Windows_RRASEnableBits,
          (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL) )
    {
LABEL_41:
      if ( v23 < 0 )
      {
        LOWORD(v29) = 0;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)L"Leaving: SetIpMultihopRouteEntryToStack",
          (unsigned int)&v27,
          0,
          (__int64)&v29);
      }
      return v6;
    }
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)&v33,
      (unsigned int)&v27,
      0,
      (__int64)&v29);
    goto LABEL_38;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v33) = 0;
    LOWORD(v29) = 0;
    FormatRRASErrorString(
      &v33,
      L"Route is owned by the stack, the router manager should not delete the route from the stack. The route type is %d");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v33,
        (unsigned int)&v27,
        0,
        (__int64)&v29);
  }
  return 0;
}

```

## disassembly

```asm
0x1800229ec  mov     r11, rsp
0x1800229ef  mov     [r11+18h], rbx
0x1800229f3  mov     [r11+20h], rsi
0x1800229f7  push    rdi
0x1800229f8  push    r12
0x1800229fa  push    r13
0x1800229fc  push    r14
0x1800229fe  push    r15
0x180022a00  sub     rsp, 900h
0x180022a07  mov     rax, cs:__security_cookie
0x180022a0e  xor     rax, rsp
0x180022a11  mov     [rsp+928h+var_38], rax
0x180022a19  xorps   xmm0, xmm0
0x180022a1c  xorps   xmm1, xmm1
0x180022a1f  mov     r15d, r8d
0x180022a22  mov     r14d, edx
0x180022a25  mov     rsi, rcx
0x180022a28  xor     r12d, r12d
0x180022a2b  xor     eax, eax
0x180022a2d  mov     [r11-838h], r12d
0x180022a34  xor     edx, edx; Val
0x180022a36  mov     qword ptr [rsp+928h+pRoute.dwForwardMetric4], rax
0x180022a3b  mov     r8d, 7FCh; Size
0x180022a41  lea     rcx, [r11-834h]; void *
0x180022a48  mov     edi, r12d
0x180022a4b  movups  [rsp+928h+var_8A8], xmm0
0x180022a53  movups  [rsp+928h+var_898], xmm0
0x180022a5b  movups  [rsp+928h+var_888], xmm0
0x180022a63  movups  [rsp+928h+var_8B8], xmm0
0x180022a68  movups  xmmword ptr [rsp+928h+pRoute.dwForwardDest], xmm1
0x180022a6d  movups  xmmword ptr [rsp+928h+pRoute.dwForwardIfIndex], xmm1
0x180022a72  movups  xmmword ptr [rsp+928h+pRoute.dwForwardNextHopAS], xmm1
0x180022a77  call    memset_0
0x180022a7c  xorps   xmm0, xmm0
0x180022a7f  mov     [rsp+928h+var_868], r12d
0x180022a87  xor     eax, eax
0x180022a89  mov     [rsp+928h+var_844], eax
0x180022a90  movups  [rsp+928h+var_864], xmm0
0x180022a98  movups  [rsp+928h+var_854], xmm0
0x180022aa0  movups  [rsp+928h+var_878], xmm0
0x180022aa8  cmp     r14d, 1
0x180022aac  jz      short loc_180022B24
0x180022aae  cmp     cs:gIsRtrMgrEtwEnabled, r12d
0x180022ab5  jz      short loc_180022B24
0x180022ab7  lea     rdx, [rsp+928h+var_8B8]
0x180022abc  mov     ecx, r14d
0x180022abf  call    NsiGetRoutingDomainIdForCompartment
0x180022ac4  mov     edi, eax
0x180022ac6  test    eax, eax
0x180022ac8  jz      short loc_180022B24
0x180022aca  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180022ad1  jz      loc_180022EED
0x180022ad7  mov     r8d, eax
0x180022ada  mov     word ptr [rsp+928h+var_838], r12w
0x180022ae3  lea     rdx, aSetipmultihopr; "SetIpMultihopRouteEntryToStack: NsiGetR"...
0x180022aea  lea     rcx, [rsp+928h+var_838]
0x180022af2  call    FormatRRASErrorString
0x180022af7  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180022afe  jz      loc_180022EED
0x180022b04  lea     r8, [rsp+928h+var_838]
0x180022b0c  lea     rdx, RasRtrMgrTraceError
0x180022b13  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180022b1a  call    McTemplateU0z_EventWriteTransfer
0x180022b1f  jmp     loc_180022EED
0x180022b24  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180022b2b  lea     rbx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180022b32  lea     r13, RasRtrmgrParamTraceInfo
0x180022b39  jz      short loc_180022B6D
0x180022b3b  lea     rax, [rsp+928h+var_868]
0x180022b43  mov     word ptr [rsp+928h+var_868], r12w
0x180022b4c  mov     [rsp+928h+var_900], rax
0x180022b51  lea     r9, [rsp+928h+var_8B8]
0x180022b56  lea     r8, aEnteredSetipmu; "Entered: SetIpMultihopRouteEntryToStack"
0x180022b5d  mov     [rsp+928h+var_908], r12
0x180022b62  mov     rdx, r13
0x180022b65  mov     rcx, rbx
0x180022b68  call    McTemplateU0zjzz_EventWriteTransfer
0x180022b6d  mov     eax, [rsi+20h]
0x180022b70  mov     edx, [rsi+24h]
0x180022b73  mov     r8d, [rsi+8]
0x180022b77  mov     ecx, [rsi+30h]; netlong
0x180022b7a  mov     [rsp+928h+pRoute.dwForwardNextHop], eax
0x180022b7e  mov     eax, [rsi+0Ch]
0x180022b81  mov     [rsp+928h+pRoute.dwForwardIfIndex], eax
0x180022b85  mov     eax, [rsi+28h]
0x180022b88  mov     dword ptr [rsp+928h+pRoute.18h], eax
0x180022b8c  mov     eax, [rsi+2Ch]
0x180022b8f  mov     [rsp+928h+pRoute.dwForwardAge], eax
0x180022b93  mov     eax, [rsi+10h]
0x180022b96  mov     [rsp+928h+pRoute.dwForwardMetric1], eax
0x180022b9a  mov     eax, [rsi+14h]
0x180022b9d  mov     [rsp+928h+pRoute.dwForwardMetric2], eax
0x180022ba1  mov     eax, [rsi+18h]
0x180022ba4  mov     [rsp+928h+pRoute.dwForwardMetric3], eax
0x180022ba8  mov     eax, [rsi+1Ch]
0x180022bab  mov     [rsp+928h+pRoute.dwForwardMetric4], eax
0x180022baf  mov     eax, [rsi+34h]
0x180022bb2  mov     [rsp+928h+pRoute.dwForwardMetric5], eax
0x180022bb6  mov     [rsp+928h+pRoute.dwForwardDest], r8d
0x180022bbb  mov     [rsp+928h+pRoute.dwForwardMask], ecx
0x180022bbf  mov     [rsp+928h+pRoute.dwForwardPolicy], r12d
0x180022bc4  mov     dword ptr [rsp+928h+pRoute.14h], edx
0x180022bc8  mov     [rsp+928h+pRoute.dwForwardNextHopAS], r12d
0x180022bcd  cmp     edx, 2
0x180022bd0  jz      loc_180022C8D
0x180022bd6  mov     dword ptr [rsp+928h+var_8A8+4], r8d
0x180022bde  call    cs:__imp_ntohl
0x180022be4  mov     edx, eax
0x180022be6  mov     ecx, eax
0x180022be8  shl     edx, 10h
0x180022beb  and     ecx, 10000h
0x180022bf1  cmovz   edx, eax
0x180022bf4  neg     ecx
0x180022bf6  sbb     r9d, r9d
0x180022bf9  and     r9d, 10h
0x180022bfd  bt      edx, 8
0x180022c01  jnb     short loc_180022C0A
0x180022c03  add     r9d, 8
0x180022c07  shl     edx, 8
0x180022c0a  mov     r8d, edx
0x180022c0d  lea     ecx, [r9+4]
0x180022c11  shl     r8d, 4
0x180022c15  bt      edx, 4
0x180022c19  cmovnb  r8d, edx
0x180022c1d  cmovnb  ecx, r9d
0x180022c21  test    r8d, r8d
0x180022c24  jz      short loc_180022C2D
0x180022c26  inc     ecx
0x180022c28  add     r8d, r8d
0x180022c2b  jnz     short loc_180022C26
0x180022c2d  mov     byte ptr [rsp+928h+var_8A8+8], cl
0x180022c34  test    r15d, r15d
0x180022c37  jz      short loc_180022C4E
0x180022c39  mov     r8d, r14d
0x180022c3c  lea     rcx, [rsp+928h+var_8A8]
0x180022c44  mov     edx, 1
0x180022c49  call    DeleteRTRMgrOwnedRoutesToDestFromStack
0x180022c4e  cmp     dword ptr [rsp+928h+pRoute.18h], 4
0x180022c53  jbe     loc_180022EED
0x180022c59  mov     edx, r14d
0x180022c5c  lea     rcx, [rsp+928h+pRoute]
0x180022c61  call    IsOnLinkRoute
0x180022c66  mov     edx, [rsp+928h+pRoute.dwForwardNextHop]
0x180022c6a  lea     rcx, [rsp+928h+pRoute]
0x180022c6f  test    eax, eax
0x180022c71  cmovnz  edx, r12d
0x180022c75  mov     [rsp+928h+pRoute.dwForwardNextHop], edx
0x180022c79  call    CreateOrSetIpForwardEntry
0x180022c7e  mov     ecx, eax; Status
0x180022c80  call    cs:__imp_RtlNtStatusToDosError
0x180022c86  mov     edi, eax
0x180022c88  jmp     loc_180022E47
0x180022c8d  mov     edx, r14d
0x180022c90  lea     rcx, [rsp+928h+pRoute]
0x180022c95  call    GetFirstRouteInfoForDestination
0x180022c9a  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x180022ca1  mov     edi, eax
0x180022ca3  jge     short loc_180022D16
0x180022ca5  mov     eax, [rsp+928h+pRoute.dwForwardNextHop]
0x180022ca9  lea     rdx, aGetfirstroutei; "GetFirstRouteInfoForDestination returns"...
0x180022cb0  mov     r9d, [rsp+928h+pRoute.dwForwardIfIndex]
0x180022cb5  lea     rcx, [rsp+928h+var_838]
0x180022cbd  mov     dword ptr [rsp+928h+var_900], eax
0x180022cc1  mov     r8d, edi
0x180022cc4  mov     eax, [rsp+928h+pRoute.dwForwardDest]
0x180022cc8  mov     dword ptr [rsp+928h+var_908], eax
0x180022ccc  mov     word ptr [rsp+928h+var_838], r12w
0x180022cd5  mov     word ptr [rsp+928h+var_868], r12w
0x180022cde  call    FormatRRASErrorString
0x180022ce3  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x180022cea  jge     short loc_180022D16
0x180022cec  lea     rax, [rsp+928h+var_868]
0x180022cf4  mov     rdx, r13
0x180022cf7  mov     [rsp+928h+var_900], rax
0x180022cfc  lea     r9, [rsp+928h+var_8B8]
0x180022d01  lea     r8, [rsp+928h+var_838]
0x180022d09  mov     [rsp+928h+var_908], r12
0x180022d0e  mov     rcx, rbx
0x180022d11  call    McTemplateU0zjzz_EventWriteTransfer
0x180022d16  mov     edx, r14d
0x180022d19  lea     rcx, [rsp+928h+pRoute]
0x180022d1e  call    IsOnLinkRoute
0x180022d23  mov     edx, [rsp+928h+pRoute.dwForwardNextHop]
0x180022d27  test    eax, eax
0x180022d29  cmovnz  edx, r12d
0x180022d2d  mov     [rsp+928h+pRoute.dwForwardNextHop], edx
0x180022d31  test    edi, edi
0x180022d33  jnz     loc_180022E47
0x180022d39  mov     r8d, dword ptr [rsp+928h+pRoute.18h]
0x180022d3e  mov     eax, [rsi+24h]
0x180022d41  mov     dword ptr [rsp+928h+pRoute.14h], eax
0x180022d45  cmp     r8d, 4
0x180022d49  ja      short loc_180022DB4
0x180022d4b  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x180022d52  jge     short loc_180022DAD
0x180022d54  lea     rdx, aRouteIsOwnedBy; "Route is owned by the stack, the router"...
0x180022d5b  mov     word ptr [rsp+928h+var_838], r12w
0x180022d64  lea     rcx, [rsp+928h+var_838]
0x180022d6c  mov     word ptr [rsp+928h+var_868], r12w
0x180022d75  call    FormatRRASErrorString
0x180022d7a  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x180022d81  jge     short loc_180022DAD
0x180022d83  lea     rax, [rsp+928h+var_868]
0x180022d8b  mov     rdx, r13
0x180022d8e  mov     [rsp+928h+var_900], rax
0x180022d93  lea     r9, [rsp+928h+var_8B8]
0x180022d98  lea     r8, [rsp+928h+var_838]
0x180022da0  mov     [rsp+928h+var_908], r12
0x180022da5  mov     rcx, rbx
0x180022da8  call    McTemplateU0zjzz_EventWriteTransfer
0x180022dad  xor     eax, eax
0x180022daf  jmp     loc_180022EEF
0x180022db4  lea     rcx, [rsp+928h+pRoute]; pRoute
0x180022db9  call    cs:__imp_DeleteIpForwardEntry
0x180022dbf  mov     edi, eax
0x180022dc1  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180022dc8  test    al, al
0x180022dca  jns     loc_180022EB7
0x180022dd0  mov     eax, [rsp+928h+pRoute.dwForwardNextHop]
0x180022dd4  lea     rdx, aDeleteipforwar_1; "DeleteIpForwardEntry returns with 0x%x;"...
0x180022ddb  mov     r9d, [rsp+928h+pRoute.dwForwardIfIndex]
0x180022de0  lea     rcx, [rsp+928h+var_838]
0x180022de8  mov     dword ptr [rsp+928h+var_900], eax
0x180022dec  mov     r8d, edi
0x180022def  mov     eax, [rsp+928h+pRoute.dwForwardDest]
0x180022df3  mov     dword ptr [rsp+928h+var_908], eax
0x180022df7  mov     word ptr [rsp+928h+var_838], r12w
0x180022e00  mov     word ptr [rsp+928h+var_868], r12w
0x180022e09  call    FormatRRASErrorString
0x180022e0e  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180022e15  test    al, al
0x180022e17  jns     loc_180022EB7
0x180022e1d  lea     rax, [rsp+928h+var_868]
0x180022e25  mov     rdx, r13
0x180022e28  mov     [rsp+928h+var_900], rax
0x180022e2d  lea     r9, [rsp+928h+var_8B8]
0x180022e32  lea     r8, [rsp+928h+var_838]
0x180022e3a  mov     [rsp+928h+var_908], r12
0x180022e3f  mov     rcx, rbx
0x180022e42  call    McTemplateU0zjzz_EventWriteTransfer
0x180022e47  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180022e4e  test    al, al
0x180022e50  jns     short loc_180022EB7
0x180022e52  mov     r8d, edi
0x180022e55  mov     word ptr [rsp+928h+var_838], r12w
0x180022e5e  lea     rdx, aSetipforwarden; "SetIpForwardEntry returns with 0x%X\n"
0x180022e65  mov     word ptr [rsp+928h+var_868], r12w
0x180022e6e  lea     rcx, [rsp+928h+var_838]
0x180022e76  call    FormatRRASErrorString
0x180022e7b  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180022e82  test    al, al
0x180022e84  jns     short loc_180022EB7
0x180022e86  lea     rax, [rsp+928h+var_868]
0x180022e8e  mov     rdx, r13
0x180022e91  mov     [rsp+928h+var_900], rax
0x180022e96  lea     r9, [rsp+928h+var_8B8]
0x180022e9b  lea     r8, [rsp+928h+var_838]
0x180022ea3  mov     [rsp+928h+var_908], r12
0x180022ea8  mov     rcx, rbx
0x180022eab  call    McTemplateU0zjzz_EventWriteTransfer
0x180022eb0  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180022eb7  test    al, 80h
0x180022eb9  jz      short loc_180022EED
0x180022ebb  lea     rax, [rsp+928h+var_868]
0x180022ec3  mov     word ptr [rsp+928h+var_868], r12w
0x180022ecc  mov     [rsp+928h+var_900], rax
0x180022ed1  lea     r9, [rsp+928h+var_8B8]
0x180022ed6  lea     r8, aLeavingSetipmu; "Leaving: SetIpMultihopRouteEntryToStack"
0x180022edd  mov     [rsp+928h+var_908], r12
0x180022ee2  mov     rdx, r13
0x180022ee5  mov     rcx, rbx
0x180022ee8  call    McTemplateU0zjzz_EventWriteTransfer
0x180022eed  mov     eax, edi
0x180022eef  mov     rcx, [rsp+928h+var_38]
0x180022ef7  xor     rcx, rsp; StackCookie
0x180022efa  call    __security_check_cookie
0x180022eff  lea     r11, [rsp+928h+var_28]
0x180022f07  mov     rbx, [r11+40h]
0x180022f0b  mov     rsi, [r11+48h]
0x180022f0f  mov     rsp, r11
0x180022f12  pop     r15
0x180022f14  pop     r14
0x180022f16  pop     r13
0x180022f18  pop     r12
0x180022f1a  pop     rdi
0x180022f1b  retn
```

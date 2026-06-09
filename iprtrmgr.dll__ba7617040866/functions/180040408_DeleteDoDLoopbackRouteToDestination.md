# DeleteDoDLoopbackRouteToDestination

- ea: `0x180040408`
- end: `0x180040bdc`
- name: `DeleteDoDLoopbackRouteToDestination`
- size: `2004`
- prototype: `__int64 __fastcall(PRTM_NET_ADDRESS pNetAddress)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180043c50`
- `0x180044d2c`

## callees

- `0x18000ac60`
- `0x18000f80c`
- `0x180011790`
- `0x18002ee20`
- `0x180040408`
- `0x180040be4`
- `0x18004aa08`
- `0x180051be4`
- `0x180057c48`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18004073d`
- `ntdll!RtlReleaseResource` at `0x180040844`
- `ntdll!RtlReleaseResource` at `0x180040912`
- `ntdll!RtlReleaseResource` at `0x18004073d`
- `ntdll!RtlReleaseResource` at `0x180040844`
- `ntdll!RtlReleaseResource` at `0x180040912`
- `ntdll!RtlAcquireResourceShared` at `0x180040716`
- `ntdll!RtlAcquireResourceShared` at `0x180040716`
- `WS2_32!__imp_htonl` at `0x1800406d4`
- `WS2_32!__imp_htonl` at `0x1800406d4`
- `rtm!RtmReleaseNextHopInfo` at `0x1800407c8`
- `rtm!RtmReleaseNextHopInfo` at `0x1800408d0`
- `rtm!RtmReleaseNextHopInfo` at `0x180040aca`
- `rtm!RtmReleaseNextHopInfo` at `0x1800407c8`
- `rtm!RtmReleaseNextHopInfo` at `0x1800408d0`
- `rtm!RtmReleaseNextHopInfo` at `0x180040aca`
- `rtm!RtmGetNextHopInfo` at `0x18004068b`
- `rtm!RtmGetNextHopInfo` at `0x18004068b`
- `rtm!RtmGetEntityInfo` at `0x180040596`
- `rtm!RtmGetEntityInfo` at `0x180040596`
- `rtm!RtmConvertNetAddressToIpv6AddressAndLength` at `0x180040705`
- `rtm!RtmConvertNetAddressToIpv6AddressAndLength` at `0x180040705`

## string_xrefs

- `0x1800404ee`: `DeleteDoDLoopbackRouteToDestination`
- `0x18004062e`: `DeleteDoDLoopbackRouteToDestination`
- `0x1800407d6`: `DeleteDoDLoopbackRouteToDestination`
- `0x1800408e3`: `DeleteDoDLoopbackRouteToDestination`
- `0x180040ad9`: `DeleteDoDLoopbackRouteToDestination`
- `0x1800405b4`: `DeleteDoDLoopbackRouteToDestination: Error %d retrieving entity info from RTM`
- `0x1800406a5`: `DeleteDoDLoopbackRouteToDestination: Error %d retrieving next hop info from RTM`
- `0x180040754`: `DeleteDoDLoopbackRouteToDestination: **Error** NULL pBinding, tried to delete route from %d as DOD\n`
- `0x18004085d`: `DeleteDoDLoopbackRouteToDestination: Error %d retrieving loopback index for compartment %d\n `
- `0x180040a6e`: `DeleteDoDLoopbackRouteToDestination: Deleting loopback route over  %hs %d.%d.%d.%d/%d.%d.%d.%d with %d`
- `0x180040bb8`: `DeleteDoDLoopbackRouteToDestination: Deleting loopback route over  %hs %hs/%d with %d`

## pseudocode

```c
__int64 __fastcall DeleteDoDLoopbackRouteToDestination(
        PRTM_NET_ADDRESS pNetAddress,
        __int64 a2,
        __int64 a3,
        struct _GUID *a4)
{
  __int128 *v7; // r9
  USHORT AddressFamily; // si
  BOOL v9; // edi
  unsigned int v10; // edx
  void *RtmRegistrationHandle; // r15
  DWORD LoopbackIdentifiersFromCompartmentId; // ebx
  char v13; // cl
  const wchar_t *v14; // rdx
  __int128 *v15; // r9
  bool v16; // sf
  USHORT NumBits; // ax
  u_long v19; // eax
  __int64 InterfaceBinding; // rax
  __int64 v21; // rdi
  __int128 *v22; // r9
  __int128 *v23; // r9
  int v24; // ebx
  unsigned int v25; // r12d
  const char *v26; // rcx
  __int128 *v27; // r9
  __int64 Ipv6StringFromAddress; // r9
  const char *v29; // r8
  __int64 v30; // [rsp+20h] [rbp-A38h]
  __int64 v31; // [rsp+28h] [rbp-A30h]
  DWORD pLength[4]; // [rsp+60h] [rbp-9F8h] BYREF
  __int128 v33; // [rsp+70h] [rbp-9E8h] BYREF
  __int128 v34; // [rsp+80h] [rbp-9D8h] BYREF
  __int128 v35; // [rsp+90h] [rbp-9C8h]
  __int128 v36; // [rsp+A0h] [rbp-9B8h]
  __int128 v37; // [rsp+B0h] [rbp-9A8h]
  __int64 v38; // [rsp+C0h] [rbp-998h]
  int v39[4]; // [rsp+D0h] [rbp-988h] BYREF
  __int128 v40; // [rsp+E0h] [rbp-978h]
  __int128 v41; // [rsp+F0h] [rbp-968h]
  __int128 v42; // [rsp+100h] [rbp-958h]
  __int64 v43; // [rsp+110h] [rbp-948h]
  struct _RTM_NEXTHOP_INFO NextHopInfo; // [rsp+120h] [rbp-938h] BYREF
  __int128 v45; // [rsp+158h] [rbp-900h] BYREF
  __int128 v46; // [rsp+168h] [rbp-8F0h] BYREF
  struct _RTM_ENTITY_INFO EntityInfo; // [rsp+178h] [rbp-8E0h] BYREF
  struct in6_addr pAddress; // [rsp+188h] [rbp-8D0h] BYREF
  int v49; // [rsp+198h] [rbp-8C0h] BYREF
  __int128 v50; // [rsp+19Ch] [rbp-8BCh]
  __int128 v51; // [rsp+1ACh] [rbp-8ACh]
  int v52; // [rsp+1BCh] [rbp-89Ch]
  _BYTE v53[80]; // [rsp+1C0h] [rbp-898h] BYREF
  int v54; // [rsp+210h] [rbp-848h] BYREF
  _BYTE v55[2044]; // [rsp+214h] [rbp-844h] BYREF

  *(_QWORD *)&v33 = a2;
  memset_0(&v34, 0, 0x48u);
  memset_0(v53, 0, 0x41u);
  pLength[0] = 0;
  v54 = 0;
  EntityInfo = 0;
  memset(&NextHopInfo, 0, sizeof(NextHopInfo));
  v46 = 0;
  memset_0(v55, 0, sizeof(v55));
  v49 = 0;
  v50 = 0;
  v52 = 0;
  v51 = 0;
  v45 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v54) = 0;
    LOWORD(v49) = 0;
    FormatRRASErrorString(&v54, L"Entered: %ws", L"DeleteDoDLoopbackRouteToDestination");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v7 = &v45;
      if ( a4 )
        LODWORD(v7) = (_DWORD)a4;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v54,
        (_DWORD)v7,
        0,
        (__int64)&v49);
    }
  }
  AddressFamily = pNetAddress->AddressFamily;
  v9 = pNetAddress->AddressFamily == 2;
  v10 = 33;
  if ( pNetAddress->AddressFamily != 2 )
    v10 = 87;
  RtmRegistrationHandle = (void *)GetRtmRegistrationHandle(a4, v10, 2u);
  LoopbackIdentifiersFromCompartmentId = RtmGetEntityInfo(
                                           RtmRegistrationHandle,
                                           *(RTM_ENTITY_HANDLE *)(a3 + 8),
                                           &EntityInfo);
  if ( LoopbackIdentifiersFromCompartmentId )
  {
    v13 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v14 = L"DeleteDoDLoopbackRouteToDestination: Error %d retrieving entity info from RTM";
      goto LABEL_11;
    }
    goto LABEL_15;
  }
  LoopbackIdentifiersFromCompartmentId = RtmGetNextHopInfo(
                                           RtmRegistrationHandle,
                                           *(RTM_NEXTHOP_HANDLE *)(a3 + 56),
                                           &NextHopInfo);
  if ( LoopbackIdentifiersFromCompartmentId )
  {
    v13 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v14 = L"DeleteDoDLoopbackRouteToDestination: Error %d retrieving next hop info from RTM";
LABEL_11:
      LOWORD(v54) = 0;
      LOWORD(v49) = 0;
      FormatRRASErrorString(&v54, v14, LoopbackIdentifiersFromCompartmentId);
      v13 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v15 = &v45;
        if ( a4 )
          LODWORD(v15) = (_DWORD)a4;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v54,
          (_DWORD)v15,
          0,
          (__int64)&v49);
        v13 = Microsoft_Windows_RRASEnableBits;
      }
    }
LABEL_15:
    if ( v13 >= 0 )
      return LoopbackIdentifiersFromCompartmentId;
    LOWORD(v54) = 0;
    FormatRRASErrorString(&v54, L"Leaving: %ws", L"DeleteDoDLoopbackRouteToDestination");
    v16 = (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL;
LABEL_17:
    if ( v16 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v54);
    return LoopbackIdentifiersFromCompartmentId;
  }
  if ( AddressFamily == 2 )
  {
    NumBits = pNetAddress->NumBits;
    if ( NumBits )
      v19 = htonl(-1 << (32 - NumBits));
    else
      v19 = 0;
    pLength[0] = v19;
  }
  else
  {
    pAddress = 0;
    RtmConvertNetAddressToIpv6AddressAndLength(pNetAddress, &pAddress, pLength, 0x10u);
  }
  RtlAcquireResourceShared(&stru_18008C500, 1u);
  InterfaceBinding = GetInterfaceBinding(NextHopInfo.InterfaceIndex, v9);
  v21 = InterfaceBinding;
  if ( !InterfaceBinding )
  {
    RtlReleaseResource(&stru_18008C500);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v54) = 0;
      LOWORD(v49) = 0;
      FormatRRASErrorString(
        &v54,
        L"DeleteDoDLoopbackRouteToDestination: **Error** NULL pBinding, tried to delete route from %d as DOD\n",
        NextHopInfo.InterfaceIndex);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v22 = &v45;
        if ( a4 )
          LODWORD(v22) = (_DWORD)a4;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v54,
          (_DWORD)v22,
          0,
          (__int64)&v49);
      }
    }
    RtmReleaseNextHopInfo(RtmRegistrationHandle, &NextHopInfo);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v54) = 0;
      FormatRRASErrorString(&v54, L"Leaving: %ws", L"DeleteDoDLoopbackRouteToDestination");
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v54);
    }
    return 0;
  }
  LoopbackIdentifiersFromCompartmentId = GetLoopbackIdentifiersFromCompartmentId(
                                           *(unsigned int *)(InterfaceBinding + 56),
                                           &v46);
  if ( LoopbackIdentifiersFromCompartmentId )
  {
    RtlReleaseResource(&stru_18008C500);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v54) = 0;
      LOWORD(v49) = 0;
      FormatRRASErrorString(
        &v54,
        L"DeleteDoDLoopbackRouteToDestination: Error %d retrieving loopback index for compartment %d\n ",
        LoopbackIdentifiersFromCompartmentId,
        *(unsigned int *)(v21 + 56));
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v23 = &v45;
        if ( a4 )
          LODWORD(v23) = (_DWORD)a4;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v54,
          (_DWORD)v23,
          0,
          (__int64)&v49);
      }
    }
    RtmReleaseNextHopInfo(RtmRegistrationHandle, &NextHopInfo);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return LoopbackIdentifiersFromCompartmentId;
    LOWORD(v54) = 0;
    FormatRRASErrorString(&v54, L"Leaving: %ws", L"DeleteDoDLoopbackRouteToDestination");
    v16 = (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL;
    goto LABEL_17;
  }
  RtlReleaseResource(&stru_18008C500);
  v24 = DWORD2(v46);
  ConvertRtmToRouteInfo(EntityInfo.EntityId.EntityProtocolId, pNetAddress, a3, &NextHopInfo, &v34);
  *(_OWORD *)v39 = v34;
  v41 = v36;
  LODWORD(v37) = v24;
  v40 = v35;
  v43 = v38;
  v42 = v37;
  v25 = DeleteSingleRoute((int)v39, v33);
  if ( AddressFamily == 2 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v26 = " succeeded";
      LODWORD(v31) = BYTE2(v34);
      if ( v25 )
        v26 = "failed";
      LODWORD(v30) = BYTE1(v34);
      LOWORD(v54) = 0;
      LOWORD(v49) = 0;
      FormatRRASErrorString(
        &v54,
        L"DeleteDoDLoopbackRouteToDestination: Deleting loopback route over  %hs %d.%d.%d.%d/%d.%d.%d.%d with %d",
        v26,
        (unsigned __int8)v34,
        v30,
        v31,
        BYTE3(v34),
        BYTE4(v34),
        BYTE5(v34),
        BYTE6(v34),
        HIBYTE(DWORD1(v34)),
        v25,
        *(_QWORD *)pLength);
LABEL_52:
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v27 = &v45;
        if ( a4 )
          LODWORD(v27) = (_DWORD)a4;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v54,
          (_DWORD)v27,
          0,
          (__int64)&v49);
      }
    }
  }
  else if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v33 = v34;
    LOWORD(v54) = 0;
    LOWORD(v49) = 0;
    Ipv6StringFromAddress = GetIpv6StringFromAddress(&v33, v53);
    LODWORD(v31) = v25;
    v29 = " succeeded";
    if ( v25 )
      v29 = "failed";
    LODWORD(v30) = v35;
    FormatRRASErrorString(
      &v54,
      L"DeleteDoDLoopbackRouteToDestination: Deleting loopback route over  %hs %hs/%d with %d",
      v29,
      Ipv6StringFromAddress,
      v30,
      v31);
    goto LABEL_52;
  }
  RtmReleaseNextHopInfo(RtmRegistrationHandle, &NextHopInfo);
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v54) = 0;
    FormatRRASErrorString(&v54, L"Leaving: %ws", L"DeleteDoDLoopbackRouteToDestination");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v54);
  }
  return v25;
}

```

## disassembly

```asm
0x180040408  push    rbx
0x18004040a  push    rsi
0x18004040b  push    rdi
0x18004040c  push    r12
0x18004040e  push    r13
0x180040410  push    r14
0x180040412  push    r15
0x180040414  sub     rsp, 0A20h
0x18004041b  mov     rax, cs:__security_cookie
0x180040422  xor     rax, rsp
0x180040425  mov     [rsp+0A58h+var_48], rax
0x18004042d  mov     qword ptr [rsp+0A58h+var_9E8], rdx
0x180040432  mov     r13, r8
0x180040435  xor     edx, edx; Val
0x180040437  mov     r12, rcx
0x18004043a  lea     rcx, [rsp+0A58h+var_9D8]; void *
0x180040442  mov     r14, r9
0x180040445  lea     r8d, [rdx+48h]; Size
0x180040449  call    memset_0
0x18004044e  xor     edx, edx; Val
0x180040450  lea     rcx, [rsp+0A58h+var_898]; void *
0x180040458  lea     r8d, [rdx+41h]; Size
0x18004045c  call    memset_0
0x180040461  xorps   xmm1, xmm1
0x180040464  lea     rcx, [rsp+0A58h+var_844]; void *
0x18004046c  xorps   xmm0, xmm0
0x18004046f  xor     eax, eax
0x180040471  xor     ebx, ebx
0x180040473  mov     [rsp+0A58h+NextHopInfo.RemoteNextHop], rax
0x18004047b  xor     edx, edx; Val
0x18004047d  mov     [rsp+0A58h+pLength], ebx
0x180040481  mov     r8d, 7FCh; Size
0x180040487  mov     [rsp+0A58h+var_848], ebx
0x18004048e  movups  xmmword ptr [rsp+0A58h+EntityInfo.RtmInstanceId], xmm0
0x180040496  movups  xmmword ptr [rsp+0A58h+NextHopInfo.NextHopAddress.AddressFamily], xmm1
0x18004049e  movups  xmmword ptr [rsp+0A58h+NextHopInfo.NextHopAddress.AddrBits+0Ch], xmm1
0x1800404a6  movups  xmmword ptr [rsp+0A58h+NextHopInfo.InterfaceIndex], xmm1
0x1800404ae  movups  [rsp+0A58h+var_8F0], xmm0
0x1800404b6  call    memset_0
0x1800404bb  xorps   xmm0, xmm0
0x1800404be  mov     [rsp+0A58h+var_8C0], ebx
0x1800404c5  xor     eax, eax
0x1800404c7  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x1800404cd  movups  [rsp+0A58h+var_8BC], xmm0
0x1800404d5  mov     [rsp+0A58h+var_89C], eax
0x1800404dc  movups  [rsp+0A58h+var_8AC], xmm0
0x1800404e4  movups  [rsp+0A58h+var_900], xmm0
0x1800404ec  jge     short loc_18004055D
0x1800404ee  lea     r8, aDeletedodloopb_0; "DeleteDoDLoopbackRouteToDestination"
0x1800404f5  mov     word ptr [rsp+0A58h+var_848], bx
0x1800404fd  lea     rdx, aEnteredWs; "Entered: %ws"
0x180040504  mov     word ptr [rsp+0A58h+var_8C0], bx
0x18004050c  lea     rcx, [rsp+0A58h+var_848]
0x180040514  call    FormatRRASErrorString
0x180040519  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18004051f  jge     short loc_18004055D
0x180040521  test    r14, r14
0x180040524  lea     rax, [rsp+0A58h+var_8C0]
0x18004052c  mov     [rsp+0A58h+var_A30], rax
0x180040531  lea     r9, [rsp+0A58h+var_900]
0x180040539  cmovnz  r9, r14
0x18004053d  mov     [rsp+0A58h+var_A38], rbx
0x180040542  lea     r8, [rsp+0A58h+var_848]
0x18004054a  lea     rdx, RasRtrmgrParamTraceInfo
0x180040551  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180040558  call    McTemplateU0zjzz_EventWriteTransfer
0x18004055d  movzx   esi, word ptr [r12]
0x180040562  mov     ecx, 2
0x180040567  cmp     si, cx
0x18004056a  mov     r8d, ecx; unsigned int
0x18004056d  mov     edi, ebx
0x18004056f  setz    dil
0x180040573  lea     edx, [rcx+1Fh]
0x180040576  lea     eax, [rcx+55h]
0x180040579  mov     rcx, r14; struct _GUID *
0x18004057c  cmovnz  edx, eax; unsigned int
0x18004057f  call    GetRtmRegistrationHandle
0x180040584  mov     rdx, [r13+8]; EntityHandle
0x180040588  lea     r8, [rsp+0A58h+EntityInfo]; EntityInfo
0x180040590  mov     rcx, rax; RtmRegHandle
0x180040593  mov     r15, rax
0x180040596  call    cs:__imp_RtmGetEntityInfo
0x18004059c  mov     ebx, eax
0x18004059e  test    eax, eax
0x1800405a0  jz      loc_18004067C
0x1800405a6  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x1800405ad  xor     edi, edi
0x1800405af  test    cl, 40h
0x1800405b2  jz      short loc_18004062A
0x1800405b4  lea     rdx, aDeletedodloopb_3; "DeleteDoDLoopbackRouteToDestination: Er"...
0x1800405bb  mov     r8d, ebx
0x1800405be  mov     word ptr [rsp+0A58h+var_848], di
0x1800405c6  lea     rcx, [rsp+0A58h+var_848]
0x1800405ce  mov     word ptr [rsp+0A58h+var_8C0], di
0x1800405d6  call    FormatRRASErrorString
0x1800405db  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x1800405e2  test    cl, 40h
0x1800405e5  jz      short loc_18004062A
0x1800405e7  test    r14, r14
0x1800405ea  lea     rax, [rsp+0A58h+var_8C0]
0x1800405f2  mov     [rsp+0A58h+var_A30], rax
0x1800405f7  lea     r9, [rsp+0A58h+var_900]
0x1800405ff  cmovnz  r9, r14
0x180040603  mov     [rsp+0A58h+var_A38], rdi
0x180040608  lea     r8, [rsp+0A58h+var_848]
0x180040610  lea     rdx, RasRtrMgrParamTraceError
0x180040617  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004061e  call    McTemplateU0zjzz_EventWriteTransfer
0x180040623  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18004062a  test    cl, cl
0x18004062c  jns     short loc_180040675
0x18004062e  lea     r8, aDeletedodloopb_0; "DeleteDoDLoopbackRouteToDestination"
0x180040635  mov     word ptr [rsp+0A58h+var_848], di
0x18004063d  lea     rdx, aLeavingWs; "Leaving: %ws"
0x180040644  lea     rcx, [rsp+0A58h+var_848]
0x18004064c  call    FormatRRASErrorString
0x180040651  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180040658  jge     short loc_180040675
0x18004065a  lea     r8, [rsp+0A58h+var_848]
0x180040662  lea     rdx, RasRtrmgrTraceInfo
0x180040669  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180040670  call    McTemplateU0z_EventWriteTransfer
0x180040675  mov     eax, ebx
0x180040677  jmp     loc_180040B24
0x18004067c  mov     rdx, [r13+38h]; NextHopHandle
0x180040680  lea     r8, [rsp+0A58h+NextHopInfo]; NextHopInfo
0x180040688  mov     rcx, r15; RtmRegHandle
0x18004068b  call    cs:__imp_RtmGetNextHopInfo
0x180040691  mov     ebx, eax
0x180040693  test    eax, eax
0x180040695  jz      short loc_1800406B1
0x180040697  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18004069e  xor     edi, edi
0x1800406a0  test    cl, 40h
0x1800406a3  jz      short loc_18004062A
0x1800406a5  lea     rdx, aDeletedodloopb_6; "DeleteDoDLoopbackRouteToDestination: Er"...
0x1800406ac  jmp     loc_1800405BB
0x1800406b1  mov     eax, 2
0x1800406b6  cmp     si, ax
0x1800406b9  jnz     short loc_1800406E4
0x1800406bb  movzx   eax, word ptr [r12+2]
0x1800406c1  xor     ebx, ebx
0x1800406c3  test    ax, ax
0x1800406c6  jz      short loc_1800406DC
0x1800406c8  lea     ecx, [rbx+20h]
0x1800406cb  sub     ecx, eax
0x1800406cd  or      eax, 0FFFFFFFFh
0x1800406d0  shl     eax, cl
0x1800406d2  mov     ecx, eax; hostlong
0x1800406d4  call    cs:__imp_htonl
0x1800406da  jmp     short loc_1800406DE
0x1800406dc  mov     eax, ebx
0x1800406de  mov     [rsp+0A58h+pLength], eax
0x1800406e2  jmp     short loc_18004070D
0x1800406e4  xorps   xmm0, xmm0
0x1800406e7  lea     r8, [rsp+0A58h+pLength]; pLength
0x1800406ec  mov     r9d, 10h; dwAddressSize
0x1800406f2  lea     rdx, [rsp+0A58h+pAddress]; pAddress
0x1800406fa  mov     rcx, r12; pNetAddress
0x1800406fd  movups  xmmword ptr [rsp+0A58h+pAddress.u], xmm0
0x180040705  call    cs:__imp_RtmConvertNetAddressToIpv6AddressAndLength
0x18004070b  xor     ebx, ebx
0x18004070d  mov     dl, 1; Wait
0x18004070f  lea     rcx, stru_18008C500; Resource
0x180040716  call    cs:__imp_RtlAcquireResourceShared
0x18004071c  mov     ecx, [rsp+0A58h+NextHopInfo.InterfaceIndex]
0x180040723  mov     edx, edi
0x180040725  call    GetInterfaceBinding
0x18004072a  mov     rdi, rax
0x18004072d  test    rax, rax
0x180040730  jnz     loc_180040823
0x180040736  lea     rcx, stru_18008C500; Resource
0x18004073d  call    cs:__imp_RtlReleaseResource
0x180040743  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004074a  jz      short loc_1800407BD
0x18004074c  mov     r8d, [rsp+0A58h+NextHopInfo.InterfaceIndex]
0x180040754  lea     rdx, aDeletedodloopb_7; "DeleteDoDLoopbackRouteToDestination: **"...
0x18004075b  lea     rcx, [rsp+0A58h+var_848]
0x180040763  mov     word ptr [rsp+0A58h+var_848], bx
0x18004076b  mov     word ptr [rsp+0A58h+var_8C0], bx
0x180040773  call    FormatRRASErrorString
0x180040778  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004077f  jz      short loc_1800407BD
0x180040781  test    r14, r14
0x180040784  lea     rax, [rsp+0A58h+var_8C0]
0x18004078c  mov     [rsp+0A58h+var_A30], rax
0x180040791  lea     r9, [rsp+0A58h+var_900]
0x180040799  cmovnz  r9, r14
0x18004079d  mov     [rsp+0A58h+var_A38], rbx
0x1800407a2  lea     r8, [rsp+0A58h+var_848]
0x1800407aa  lea     rdx, RasRtrMgrParamTraceError
0x1800407b1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800407b8  call    McTemplateU0zjzz_EventWriteTransfer
0x1800407bd  lea     rdx, [rsp+0A58h+NextHopInfo]; NextHopInfo
0x1800407c5  mov     rcx, r15; RtmRegHandle
0x1800407c8  call    cs:__imp_RtmReleaseNextHopInfo
0x1800407ce  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x1800407d4  jge     short loc_18004081C
0x1800407d6  lea     r8, aDeletedodloopb_0; "DeleteDoDLoopbackRouteToDestination"
0x1800407dd  mov     word ptr [rsp+0A58h+var_848], bx
0x1800407e5  lea     rdx, aLeavingWs; "Leaving: %ws"
0x1800407ec  lea     rcx, [rsp+0A58h+var_848]
0x1800407f4  call    FormatRRASErrorString
0x1800407f9  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x1800407ff  jge     short loc_18004081C
0x180040801  lea     r8, [rsp+0A58h+var_848]
0x180040809  lea     rdx, RasRtrmgrTraceInfo
0x180040810  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180040817  call    McTemplateU0z_EventWriteTransfer
0x18004081c  xor     eax, eax
0x18004081e  jmp     loc_180040B24
0x180040823  mov     ecx, [rax+38h]
0x180040826  lea     rdx, [rsp+0A58h+var_8F0]
0x18004082e  call    GetLoopbackIdentifiersFromCompartmentId
0x180040833  lea     rcx, stru_18008C500; Resource
0x18004083a  mov     ebx, eax
0x18004083c  test    eax, eax
0x18004083e  jz      loc_180040912
0x180040844  call    cs:__imp_RtlReleaseResource
0x18004084a  xor     esi, esi
0x18004084c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180040853  jz      short loc_1800408C5
0x180040855  mov     word ptr [rsp+0A58h+var_848], si
0x18004085d  lea     rdx, aDeletedodloopb_1; "DeleteDoDLoopbackRouteToDestination: Er"...
0x180040864  mov     word ptr [rsp+0A58h+var_8C0], si
0x18004086c  lea     rcx, [rsp+0A58h+var_848]
0x180040874  mov     r9d, [rdi+38h]
0x180040878  mov     r8d, ebx
0x18004087b  call    FormatRRASErrorString
0x180040880  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180040887  jz      short loc_1800408C5
0x180040889  test    r14, r14
0x18004088c  lea     rax, [rsp+0A58h+var_8C0]
0x180040894  mov     [rsp+0A58h+var_A30], rax
0x180040899  lea     r9, [rsp+0A58h+var_900]
0x1800408a1  cmovnz  r9, r14
0x1800408a5  mov     [rsp+0A58h+var_A38], rsi
0x1800408aa  lea     r8, [rsp+0A58h+var_848]
0x1800408b2  lea     rdx, RasRtrMgrParamTraceError
0x1800408b9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800408c0  call    McTemplateU0zjzz_EventWriteTransfer
0x1800408c5  lea     rdx, [rsp+0A58h+NextHopInfo]; NextHopInfo
0x1800408cd  mov     rcx, r15; RtmRegHandle
0x1800408d0  call    cs:__imp_RtmReleaseNextHopInfo
0x1800408d6  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x1800408dd  jge     loc_180040675
0x1800408e3  lea     r8, aDeletedodloopb_0; "DeleteDoDLoopbackRouteToDestination"
0x1800408ea  mov     word ptr [rsp+0A58h+var_848], si
0x1800408f2  lea     rdx, aLeavingWs; "Leaving: %ws"
0x1800408f9  lea     rcx, [rsp+0A58h+var_848]
0x180040901  call    FormatRRASErrorString
0x180040906  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x18004090d  jmp     loc_180040658
0x180040912  call    cs:__imp_RtlReleaseResource
0x180040918  mov     ecx, dword ptr [rsp+0A58h+EntityInfo.EntityId]
0x18004091f  lea     rax, [rsp+0A58h+var_9D8]
0x180040927  mov     ebx, dword ptr [rsp+0A58h+var_8F0+8]
0x18004092e  lea     r9, [rsp+0A58h+NextHopInfo]
0x180040936  mov     r8, r13
0x180040939  mov     [rsp+0A58h+var_A38], rax
0x18004093e  mov     rdx, r12
0x180040941  call    ConvertRtmToRouteInfo
0x180040946  movaps  xmm0, [rsp+0A58h+var_9D8]
0x18004094e  lea     rcx, [rsp+0A58h+var_988]; int
0x180040956  movaps  xmm1, [rsp+0A58h+var_9C8]
0x18004095e  mov     r9, r14
0x180040961  mov     rdx, qword ptr [rsp+0A58h+var_9E8]; int
0x180040966  movaps  xmmword ptr [rsp+0A58h+var_988], xmm0
0x18004096e  movaps  xmm0, [rsp+0A58h+var_9B8]
0x180040976  movaps  [rsp+0A58h+var_968], xmm0
0x18004097e  movsd   xmm0, [rsp+0A58h+var_998]
0x180040987  mov     dword ptr [rsp+0A58h+var_9A8], ebx
0x18004098e  movaps  [rsp+0A58h+var_978], xmm1
0x180040996  movaps  xmm1, [rsp+0A58h+var_9A8]
0x18004099e  movsd   [rsp+0A58h+var_948], xmm0
0x1800409a7  movaps  [rsp+0A58h+var_958], xmm1
0x1800409af  call    DeleteSingleRoute
0x1800409b4  mov     r12d, eax
0x1800409b7  xor     r13d, r13d
0x1800409ba  mov     eax, 2
0x1800409bf  cmp     si, ax
0x1800409c2  jnz     loc_180040B47
0x1800409c8  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x1800409cf  jge     loc_180040ABF
0x1800409d5  mov     edx, dword ptr [rsp+0A58h+var_9D8+4]
0x1800409dc  mov     esi, edx
0x1800409de  mov     [rsp+0A58h+var_A00], r12d
0x1800409e3  mov     ecx, edx
0x1800409e5  shr     ecx, 10h
0x1800409e8  mov     eax, edx
0x1800409ea  shr     eax, 8
0x1800409ed  movzx   ebx, al
0x1800409f0  movzx   edi, cl
0x1800409f3  mov     ecx, dword ptr [rsp+0A58h+var_9D8]
0x1800409fa  mov     r10d, ecx
0x1800409fd  mov     eax, ecx
0x1800409ff  movzx   r11d, dl
0x180040a03  shr     eax, 10h
0x180040a06  movzx   r8d, al
0x180040a0a  mov     eax, ecx
  ... truncated ...
```

# AddDoDRoute

- ea: `0x18003e45c`
- end: `0x18003ec2c`
- name: `AddDoDRoute`
- size: `2000`
- prototype: `__int64 __fastcall(PRTM_NET_ADDRESS pNetAddress)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180044d2c`
- `0x18004b844`

## callees

- `0x18000ac60`
- `0x18000f80c`
- `0x180011790`
- `0x18002ee20`
- `0x18003e45c`
- `0x18003f1a4`
- `0x18004aa08`
- `0x180051be4`
- `0x180057c48`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18003e789`
- `ntdll!RtlReleaseResource` at `0x18003e890`
- `ntdll!RtlReleaseResource` at `0x18003e995`
- `ntdll!RtlReleaseResource` at `0x18003e789`
- `ntdll!RtlReleaseResource` at `0x18003e890`
- `ntdll!RtlReleaseResource` at `0x18003e995`
- `ntdll!RtlAcquireResourceShared` at `0x18003e762`
- `ntdll!RtlAcquireResourceShared` at `0x18003e762`
- `WS2_32!__imp_htonl` at `0x18003e721`
- `WS2_32!__imp_htonl` at `0x18003e721`
- `rtm!RtmReleaseNextHopInfo` at `0x18003e811`
- `rtm!RtmReleaseNextHopInfo` at `0x18003e91c`
- `rtm!RtmReleaseNextHopInfo` at `0x18003eb0f`
- `rtm!RtmReleaseNextHopInfo` at `0x18003e811`
- `rtm!RtmReleaseNextHopInfo` at `0x18003e91c`
- `rtm!RtmReleaseNextHopInfo` at `0x18003eb0f`
- `rtm!RtmGetNextHopInfo` at `0x18003e6e1`
- `rtm!RtmGetNextHopInfo` at `0x18003e6e1`
- `rtm!RtmGetEntityInfo` at `0x18003e5eb`
- `rtm!RtmGetEntityInfo` at `0x18003e5eb`
- `rtm!RtmConvertNetAddressToIpv6AddressAndLength` at `0x18003e753`
- `rtm!RtmConvertNetAddressToIpv6AddressAndLength` at `0x18003e753`

## string_xrefs

- `0x18003e8a8`: `AddDoDRoute: Error %d retrieving loopback index for compartment %d\n `

## pseudocode

```c
__int64 __fastcall AddDoDRoute(PRTM_NET_ADDRESS pNetAddress, __int64 a2, unsigned int a3, struct _GUID *a4)
{
  __int128 *v8; // r9
  void *RtmRegistrationHandle; // r15
  DWORD v10; // ebx
  char v11; // cl
  const wchar_t *v12; // rdx
  __int128 *v13; // r9
  USHORT NumBits; // ax
  u_long v16; // eax
  __int64 InterfaceBinding; // rax
  _DWORD *v18; // rbx
  __int128 *v19; // r9
  unsigned int LoopbackIdentifiersFromCompartmentId; // edi
  __int128 *v21; // r9
  unsigned int v22; // r12d
  unsigned int v23; // r13d
  const char *v24; // r8
  __int128 *v25; // r9
  __int64 Ipv6StringFromAddress; // rax
  const char *v27; // r9
  int v28[2]; // [rsp+20h] [rbp-9F8h]
  int v29[2]; // [rsp+28h] [rbp-9F0h]
  __int64 v30; // [rsp+30h] [rbp-9E8h]
  __int64 v31; // [rsp+38h] [rbp-9E0h]
  struct _GUID *v32; // [rsp+40h] [rbp-9D8h]
  __int64 v33; // [rsp+48h] [rbp-9D0h]
  DWORD pLength[4]; // [rsp+70h] [rbp-9A8h] BYREF
  _QWORD v35[2]; // [rsp+80h] [rbp-998h] BYREF
  _QWORD v36[2]; // [rsp+90h] [rbp-988h] BYREF
  int v37; // [rsp+A0h] [rbp-978h]
  struct _RTM_NEXTHOP_INFO NextHopInfo; // [rsp+E0h] [rbp-938h] BYREF
  __int128 v39; // [rsp+118h] [rbp-900h] BYREF
  __int128 v40; // [rsp+128h] [rbp-8F0h] BYREF
  struct _RTM_ENTITY_INFO EntityInfo; // [rsp+138h] [rbp-8E0h] BYREF
  struct in6_addr pAddress; // [rsp+148h] [rbp-8D0h] BYREF
  int v43; // [rsp+158h] [rbp-8C0h] BYREF
  __int128 v44; // [rsp+15Ch] [rbp-8BCh]
  __int128 v45; // [rsp+16Ch] [rbp-8ACh]
  int v46; // [rsp+17Ch] [rbp-89Ch]
  _BYTE v47[80]; // [rsp+180h] [rbp-898h] BYREF
  int v48; // [rsp+1D0h] [rbp-848h] BYREF
  _BYTE v49[2044]; // [rsp+1D4h] [rbp-844h] BYREF

  v35[0] = a2;
  memset_0(v36, 0, 0x48u);
  memset(&NextHopInfo, 0, sizeof(NextHopInfo));
  pLength[0] = 0;
  EntityInfo = 0;
  memset_0(v47, 0, 0x41u);
  v48 = 0;
  v40 = 0;
  memset_0(v49, 0, sizeof(v49));
  v43 = 0;
  v44 = 0;
  v46 = 0;
  v45 = 0;
  v39 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v48) = 0;
    LOWORD(v43) = 0;
    FormatRRASErrorString(&v48, L"Entered: %ws", L"AddDoDRoute");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v8 = &v39;
      if ( a4 )
        LODWORD(v8) = (_DWORD)a4;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v48,
        (_DWORD)v8,
        0,
        (__int64)&v43);
    }
  }
  RtmRegistrationHandle = (void *)GetRtmRegistrationHandle(a4, a3 != 0 ? 33 : 87, 2u);
  v10 = RtmGetEntityInfo(RtmRegistrationHandle, *(RTM_ENTITY_HANDLE *)(a2 + 8), &EntityInfo);
  if ( v10 )
  {
    v11 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v12 = L"AddDoDRoute: Error %d retrieving entity info from RTM";
      goto LABEL_9;
    }
    goto LABEL_13;
  }
  v10 = RtmGetNextHopInfo(RtmRegistrationHandle, *(RTM_NEXTHOP_HANDLE *)(a2 + 56), &NextHopInfo);
  if ( v10 )
  {
    v11 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v12 = L"AddDoDRoute: Error %d retrieving next hop info from RTM";
LABEL_9:
      LOWORD(v48) = 0;
      LOWORD(v43) = 0;
      FormatRRASErrorString(&v48, v12, v10);
      v11 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v13 = &v39;
        if ( a4 )
          LODWORD(v13) = (_DWORD)a4;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v48,
          (_DWORD)v13,
          0,
          (__int64)&v43);
        v11 = Microsoft_Windows_RRASEnableBits;
      }
    }
LABEL_13:
    if ( v11 < 0 )
    {
      LOWORD(v48) = 0;
      FormatRRASErrorString(&v48, L"Leaving: %ws", L"AddDoDRoute");
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v48);
    }
    return v10;
  }
  if ( a3 )
  {
    NumBits = pNetAddress->NumBits;
    if ( NumBits )
      v16 = htonl(-1 << (32 - NumBits));
    else
      v16 = 0;
    pLength[0] = v16;
  }
  else
  {
    pAddress = 0;
    RtmConvertNetAddressToIpv6AddressAndLength(pNetAddress, &pAddress, pLength, 0x10u);
  }
  RtlAcquireResourceShared(&stru_18008C500, 1u);
  InterfaceBinding = GetInterfaceBinding(NextHopInfo.InterfaceIndex, a3);
  v18 = (_DWORD *)InterfaceBinding;
  if ( !InterfaceBinding )
  {
    RtlReleaseResource(&stru_18008C500);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v48) = 0;
      LOWORD(v43) = 0;
      FormatRRASErrorString(&v48, L"AddDoDRoute: **Error** NULL pBinding, tried to add route to over %d as DOD\n", 0);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v19 = &v39;
        if ( a4 )
          LODWORD(v19) = (_DWORD)a4;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v48,
          (_DWORD)v19,
          0,
          (__int64)&v43);
      }
    }
    RtmReleaseNextHopInfo(RtmRegistrationHandle, &NextHopInfo);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v48) = 0;
      FormatRRASErrorString(&v48, L"Leaving: %ws", L"AddDoDRoute");
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v48);
    }
    return 0;
  }
  LoopbackIdentifiersFromCompartmentId = GetLoopbackIdentifiersFromCompartmentId(
                                           *(unsigned int *)(InterfaceBinding + 56),
                                           &v40);
  if ( LoopbackIdentifiersFromCompartmentId )
  {
    RtlReleaseResource(&stru_18008C500);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v48) = 0;
      LOWORD(v43) = 0;
      FormatRRASErrorString(
        &v48,
        L"AddDoDRoute: Error %d retrieving loopback index for compartment %d\n ",
        LoopbackIdentifiersFromCompartmentId,
        (unsigned int)v18[14]);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v21 = &v39;
        if ( a4 )
          LODWORD(v21) = (_DWORD)a4;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v48,
          (_DWORD)v21,
          0,
          (__int64)&v43);
      }
    }
    RtmReleaseNextHopInfo(RtmRegistrationHandle, &NextHopInfo);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v48) = 0;
      FormatRRASErrorString(&v48, L"Leaving: %ws", L"AddDoDRoute");
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v48);
    }
    return LoopbackIdentifiersFromCompartmentId;
  }
  if ( v18[4] )
    v22 = v18[6];
  else
    v22 = DWORD2(v40);
  RtlReleaseResource(&stru_18008C500);
  ConvertRtmToRouteInfo(EntityInfo.EntityId.EntityProtocolId, pNetAddress, v35[0], &NextHopInfo, v36);
  v23 = AddSingleRoute(v22, (unsigned __int8 *)v36, pLength[0], 0, 1u, 1, 1, a3, a4, 0);
  if ( a3 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v24 = " succeeded";
      LOWORD(v48) = 0;
      LOWORD(v43) = 0;
      LODWORD(v33) = BYTE5(v36[0]);
      if ( v23 )
        v24 = "failed";
      LODWORD(v32) = BYTE4(v36[0]);
      LODWORD(v31) = HIBYTE(LODWORD(v36[0]));
      LODWORD(v30) = BYTE2(v36[0]);
      v29[0] = BYTE1(v36[0]);
      v28[0] = LOBYTE(v36[0]);
      FormatRRASErrorString(
        &v48,
        L"AddDoDRoute: Adding route over  interface %d %hs %d.%d.%d.%d/%d.%d.%d.%d with %d",
        v22,
        v24,
        *(_QWORD *)v28,
        *(_QWORD *)v29,
        v30,
        v31,
        v32,
        v33,
        BYTE6(v36[0]),
        HIBYTE(HIDWORD(v36[0])),
        v23);
LABEL_54:
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v25 = &v39;
        if ( a4 )
          LODWORD(v25) = (_DWORD)a4;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v48,
          (_DWORD)v25,
          0,
          (__int64)&v43);
      }
    }
  }
  else if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v35[0] = v36[0];
    v35[1] = v36[1];
    LOWORD(v48) = 0;
    LOWORD(v43) = 0;
    Ipv6StringFromAddress = GetIpv6StringFromAddress(v35, v47);
    LODWORD(v30) = v23;
    v27 = " succeeded";
    if ( v23 )
      v27 = "failed";
    v29[0] = v37;
    FormatRRASErrorString(
      &v48,
      L"AddDoDRoute: Adding route over interface %d  %hs %hs/%d with %d",
      v22,
      v27,
      Ipv6StringFromAddress,
      *(_QWORD *)v29,
      v30);
    goto LABEL_54;
  }
  RtmReleaseNextHopInfo(RtmRegistrationHandle, &NextHopInfo);
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v48) = 0;
    FormatRRASErrorString(&v48, L"Leaving: %ws", L"AddDoDRoute");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v48);
  }
  return v23;
}

```

## disassembly

```asm
0x18003e45c  push    rbx
0x18003e45e  push    rsi
0x18003e45f  push    rdi
0x18003e460  push    r12
0x18003e462  push    r13
0x18003e464  push    r14
0x18003e466  push    r15
0x18003e468  sub     rsp, 9E0h
0x18003e46f  mov     rax, cs:__security_cookie
0x18003e476  xor     rax, rsp
0x18003e479  mov     [rsp+0A18h+var_48], rax
0x18003e481  mov     rdi, rdx
0x18003e484  mov     [rsp+0A18h+var_998], rdx
0x18003e48c  xor     edx, edx; Val
0x18003e48e  mov     esi, r8d
0x18003e491  mov     r13, rcx
0x18003e494  mov     r14, r9
0x18003e497  lea     rcx, [rsp+0A18h+var_988]; void *
0x18003e49f  lea     r8d, [rdx+48h]; Size
0x18003e4a3  call    memset_0
0x18003e4a8  xorps   xmm0, xmm0
0x18003e4ab  lea     rcx, [rsp+0A18h+var_898]; void *
0x18003e4b3  xor     eax, eax
0x18003e4b5  xor     r12d, r12d
0x18003e4b8  xor     edx, edx; Val
0x18003e4ba  mov     [rsp+0A18h+NextHopInfo.RemoteNextHop], rax
0x18003e4c2  movups  xmmword ptr [rsp+0A18h+NextHopInfo.NextHopAddress.AddressFamily], xmm0
0x18003e4ca  mov     [rsp+0A18h+pLength], r12d
0x18003e4cf  lea     r8d, [rax+41h]; Size
0x18003e4d3  movups  xmmword ptr [rsp+0A18h+NextHopInfo.NextHopAddress.AddrBits+0Ch], xmm0
0x18003e4db  movups  xmmword ptr [rsp+0A18h+NextHopInfo.InterfaceIndex], xmm0
0x18003e4e3  movups  xmmword ptr [rsp+0A18h+EntityInfo.RtmInstanceId], xmm0
0x18003e4eb  call    memset_0
0x18003e4f0  xorps   xmm0, xmm0
0x18003e4f3  mov     [rsp+0A18h+var_848], r12d
0x18003e4fb  xor     edx, edx; Val
0x18003e4fd  lea     rcx, [rsp+0A18h+var_844]; void *
0x18003e505  mov     r8d, 7FCh; Size
0x18003e50b  movups  [rsp+0A18h+var_8F0], xmm0
0x18003e513  call    memset_0
0x18003e518  xorps   xmm0, xmm0
0x18003e51b  mov     [rsp+0A18h+var_8C0], r12d
0x18003e523  xor     eax, eax
0x18003e525  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18003e52c  movups  [rsp+0A18h+var_8BC], xmm0
0x18003e534  mov     [rsp+0A18h+var_89C], eax
0x18003e53b  movups  [rsp+0A18h+var_8AC], xmm0
0x18003e543  movups  [rsp+0A18h+var_900], xmm0
0x18003e54b  jge     short loc_18003E5BF
0x18003e54d  lea     r8, aAdddodroute; "AddDoDRoute"
0x18003e554  mov     word ptr [rsp+0A18h+var_848], r12w
0x18003e55d  lea     rdx, aEnteredWs; "Entered: %ws"
0x18003e564  mov     word ptr [rsp+0A18h+var_8C0], r12w
0x18003e56d  lea     rcx, [rsp+0A18h+var_848]
0x18003e575  call    FormatRRASErrorString
0x18003e57a  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18003e581  jge     short loc_18003E5BF
0x18003e583  test    r14, r14
0x18003e586  lea     rax, [rsp+0A18h+var_8C0]
0x18003e58e  mov     qword ptr [rsp+0A18h+var_9F0], rax
0x18003e593  lea     r9, [rsp+0A18h+var_900]
0x18003e59b  cmovnz  r9, r14
0x18003e59f  mov     qword ptr [rsp+0A18h+var_9F8], r12
0x18003e5a4  lea     r8, [rsp+0A18h+var_848]
0x18003e5ac  lea     rdx, RasRtrmgrParamTraceInfo
0x18003e5b3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003e5ba  call    McTemplateU0zjzz_EventWriteTransfer
0x18003e5bf  mov     eax, esi
0x18003e5c1  mov     r8d, 2; unsigned int
0x18003e5c7  neg     eax
0x18003e5c9  mov     rcx, r14; struct _GUID *
0x18003e5cc  sbb     edx, edx
0x18003e5ce  and     edx, 0FFFFFFCAh
0x18003e5d1  add     edx, 57h ; 'W'; unsigned int
0x18003e5d4  call    GetRtmRegistrationHandle
0x18003e5d9  mov     rdx, [rdi+8]; EntityHandle
0x18003e5dd  lea     r8, [rsp+0A18h+EntityInfo]; EntityInfo
0x18003e5e5  mov     rcx, rax; RtmRegHandle
0x18003e5e8  mov     r15, rax
0x18003e5eb  call    cs:__imp_RtmGetEntityInfo
0x18003e5f1  mov     ebx, eax
0x18003e5f3  test    eax, eax
0x18003e5f5  jz      loc_18003E6D2
0x18003e5fb  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18003e602  test    cl, 40h
0x18003e605  jz      short loc_18003E67F
0x18003e607  lea     rdx, aAdddodrouteErr; "AddDoDRoute: Error %d retrieving entity"...
0x18003e60e  mov     r8d, ebx
0x18003e611  mov     word ptr [rsp+0A18h+var_848], r12w
0x18003e61a  lea     rcx, [rsp+0A18h+var_848]
0x18003e622  mov     word ptr [rsp+0A18h+var_8C0], r12w
0x18003e62b  call    FormatRRASErrorString
0x18003e630  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18003e637  test    cl, 40h
0x18003e63a  jz      short loc_18003E67F
0x18003e63c  test    r14, r14
0x18003e63f  lea     rax, [rsp+0A18h+var_8C0]
0x18003e647  mov     qword ptr [rsp+0A18h+var_9F0], rax
0x18003e64c  lea     r9, [rsp+0A18h+var_900]
0x18003e654  cmovnz  r9, r14
0x18003e658  mov     qword ptr [rsp+0A18h+var_9F8], r12
0x18003e65d  lea     r8, [rsp+0A18h+var_848]
0x18003e665  lea     rdx, RasRtrMgrParamTraceError
0x18003e66c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003e673  call    McTemplateU0zjzz_EventWriteTransfer
0x18003e678  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18003e67f  test    cl, cl
0x18003e681  jns     short loc_18003E6CB
0x18003e683  lea     r8, aAdddodroute; "AddDoDRoute"
0x18003e68a  mov     word ptr [rsp+0A18h+var_848], r12w
0x18003e693  lea     rdx, aLeavingWs; "Leaving: %ws"
0x18003e69a  lea     rcx, [rsp+0A18h+var_848]
0x18003e6a2  call    FormatRRASErrorString
0x18003e6a7  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18003e6ae  jge     short loc_18003E6CB
0x18003e6b0  lea     r8, [rsp+0A18h+var_848]
0x18003e6b8  lea     rdx, RasRtrmgrTraceInfo
0x18003e6bf  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003e6c6  call    McTemplateU0z_EventWriteTransfer
0x18003e6cb  mov     eax, ebx
0x18003e6cd  jmp     loc_18003EB66
0x18003e6d2  mov     rdx, [rdi+38h]; NextHopHandle
0x18003e6d6  lea     r8, [rsp+0A18h+NextHopInfo]; NextHopInfo
0x18003e6de  mov     rcx, r15; RtmRegHandle
0x18003e6e1  call    cs:__imp_RtmGetNextHopInfo
0x18003e6e7  mov     ebx, eax
0x18003e6e9  test    eax, eax
0x18003e6eb  jz      short loc_18003E705
0x18003e6ed  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18003e6f4  test    cl, 40h
0x18003e6f7  jz      short loc_18003E67F
0x18003e6f9  lea     rdx, aAdddodrouteErr_1; "AddDoDRoute: Error %d retrieving next h"...
0x18003e700  jmp     loc_18003E60E
0x18003e705  test    esi, esi
0x18003e707  jz      short loc_18003E732
0x18003e709  movzx   eax, word ptr [r13+2]
0x18003e70e  test    ax, ax
0x18003e711  jz      short loc_18003E729
0x18003e713  mov     ecx, 20h ; ' '
0x18003e718  sub     ecx, eax
0x18003e71a  or      eax, 0FFFFFFFFh
0x18003e71d  shl     eax, cl
0x18003e71f  mov     ecx, eax; hostlong
0x18003e721  call    cs:__imp_htonl
0x18003e727  jmp     short loc_18003E72C
0x18003e729  mov     eax, r12d
0x18003e72c  mov     [rsp+0A18h+pLength], eax
0x18003e730  jmp     short loc_18003E759
0x18003e732  xorps   xmm0, xmm0
0x18003e735  lea     r8, [rsp+0A18h+pLength]; pLength
0x18003e73a  mov     r9d, 10h; dwAddressSize
0x18003e740  lea     rdx, [rsp+0A18h+pAddress]; pAddress
0x18003e748  mov     rcx, r13; pNetAddress
0x18003e74b  movups  xmmword ptr [rsp+0A18h+pAddress.u], xmm0
0x18003e753  call    cs:__imp_RtmConvertNetAddressToIpv6AddressAndLength
0x18003e759  mov     dl, 1; Wait
0x18003e75b  lea     rcx, stru_18008C500; Resource
0x18003e762  call    cs:__imp_RtlAcquireResourceShared
0x18003e768  mov     ecx, [rsp+0A18h+NextHopInfo.InterfaceIndex]
0x18003e76f  mov     edx, esi
0x18003e771  call    GetInterfaceBinding
0x18003e776  mov     rbx, rax
0x18003e779  test    rax, rax
0x18003e77c  jnz     loc_18003E86F
0x18003e782  lea     rcx, stru_18008C500; Resource
0x18003e789  call    cs:__imp_RtlReleaseResource
0x18003e78f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18003e796  jz      short loc_18003E806
0x18003e798  xor     r8d, r8d
0x18003e79b  mov     word ptr [rsp+0A18h+var_848], r12w
0x18003e7a4  lea     rdx, aAdddodrouteErr_0; "AddDoDRoute: **Error** NULL pBinding, t"...
0x18003e7ab  mov     word ptr [rsp+0A18h+var_8C0], r12w
0x18003e7b4  lea     rcx, [rsp+0A18h+var_848]
0x18003e7bc  call    FormatRRASErrorString
0x18003e7c1  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18003e7c8  jz      short loc_18003E806
0x18003e7ca  test    r14, r14
0x18003e7cd  lea     rax, [rsp+0A18h+var_8C0]
0x18003e7d5  mov     qword ptr [rsp+0A18h+var_9F0], rax
0x18003e7da  lea     r9, [rsp+0A18h+var_900]
0x18003e7e2  cmovnz  r9, r14
0x18003e7e6  mov     qword ptr [rsp+0A18h+var_9F8], r12
0x18003e7eb  lea     r8, [rsp+0A18h+var_848]
0x18003e7f3  lea     rdx, RasRtrMgrParamTraceError
0x18003e7fa  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003e801  call    McTemplateU0zjzz_EventWriteTransfer
0x18003e806  lea     rdx, [rsp+0A18h+NextHopInfo]; NextHopInfo
0x18003e80e  mov     rcx, r15; RtmRegHandle
0x18003e811  call    cs:__imp_RtmReleaseNextHopInfo
0x18003e817  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18003e81e  jge     short loc_18003E868
0x18003e820  lea     r8, aAdddodroute; "AddDoDRoute"
0x18003e827  mov     word ptr [rsp+0A18h+var_848], r12w
0x18003e830  lea     rdx, aLeavingWs; "Leaving: %ws"
0x18003e837  lea     rcx, [rsp+0A18h+var_848]
0x18003e83f  call    FormatRRASErrorString
0x18003e844  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18003e84b  jge     short loc_18003E868
0x18003e84d  lea     r8, [rsp+0A18h+var_848]
0x18003e855  lea     rdx, RasRtrmgrTraceInfo
0x18003e85c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003e863  call    McTemplateU0z_EventWriteTransfer
0x18003e868  xor     eax, eax
0x18003e86a  jmp     loc_18003EB66
0x18003e86f  mov     ecx, [rax+38h]
0x18003e872  lea     rdx, [rsp+0A18h+var_8F0]
0x18003e87a  call    GetLoopbackIdentifiersFromCompartmentId
0x18003e87f  mov     edi, eax
0x18003e881  test    eax, eax
0x18003e883  jz      loc_18003E97A
0x18003e889  lea     rcx, stru_18008C500; Resource
0x18003e890  call    cs:__imp_RtlReleaseResource
0x18003e896  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18003e89d  jz      short loc_18003E911
0x18003e89f  mov     word ptr [rsp+0A18h+var_848], r12w
0x18003e8a8  lea     rdx, aAdddodrouteErr_2; "AddDoDRoute: Error %d retrieving loopba"...
0x18003e8af  mov     word ptr [rsp+0A18h+var_8C0], r12w
0x18003e8b8  lea     rcx, [rsp+0A18h+var_848]
0x18003e8c0  mov     r9d, [rbx+38h]
0x18003e8c4  mov     r8d, edi
0x18003e8c7  call    FormatRRASErrorString
0x18003e8cc  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18003e8d3  jz      short loc_18003E911
0x18003e8d5  test    r14, r14
0x18003e8d8  lea     rax, [rsp+0A18h+var_8C0]
0x18003e8e0  mov     qword ptr [rsp+0A18h+var_9F0], rax
0x18003e8e5  lea     r9, [rsp+0A18h+var_900]
0x18003e8ed  cmovnz  r9, r14
0x18003e8f1  mov     qword ptr [rsp+0A18h+var_9F8], r12
0x18003e8f6  lea     r8, [rsp+0A18h+var_848]
0x18003e8fe  lea     rdx, RasRtrMgrParamTraceError
0x18003e905  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003e90c  call    McTemplateU0zjzz_EventWriteTransfer
0x18003e911  lea     rdx, [rsp+0A18h+NextHopInfo]; NextHopInfo
0x18003e919  mov     rcx, r15; RtmRegHandle
0x18003e91c  call    cs:__imp_RtmReleaseNextHopInfo
0x18003e922  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18003e929  jge     short loc_18003E973
0x18003e92b  lea     r8, aAdddodroute; "AddDoDRoute"
0x18003e932  mov     word ptr [rsp+0A18h+var_848], r12w
0x18003e93b  lea     rdx, aLeavingWs; "Leaving: %ws"
0x18003e942  lea     rcx, [rsp+0A18h+var_848]
0x18003e94a  call    FormatRRASErrorString
0x18003e94f  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18003e956  jge     short loc_18003E973
0x18003e958  lea     r8, [rsp+0A18h+var_848]
0x18003e960  lea     rdx, RasRtrmgrTraceInfo
0x18003e967  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003e96e  call    McTemplateU0z_EventWriteTransfer
0x18003e973  mov     eax, edi
0x18003e975  jmp     loc_18003EB66
0x18003e97a  cmp     [rbx+10h], r12d
0x18003e97e  jz      short loc_18003E986
0x18003e980  mov     r12d, [rbx+18h]
0x18003e984  jmp     short loc_18003E98E
0x18003e986  mov     r12d, dword ptr [rsp+0A18h+var_8F0+8]
0x18003e98e  lea     rcx, stru_18008C500; Resource
0x18003e995  call    cs:__imp_RtlReleaseResource
0x18003e99b  mov     r8, [rsp+0A18h+var_998]
0x18003e9a3  lea     rax, [rsp+0A18h+var_988]
0x18003e9ab  mov     ecx, dword ptr [rsp+0A18h+EntityInfo.EntityId]
0x18003e9b2  lea     r9, [rsp+0A18h+NextHopInfo]
0x18003e9ba  mov     rdx, r13
0x18003e9bd  mov     qword ptr [rsp+0A18h+var_9F8], rax
0x18003e9c2  call    ConvertRtmToRouteInfo
0x18003e9c7  mov     r8d, [rsp+0A18h+pLength]; int
0x18003e9cc  lea     rdx, [rsp+0A18h+var_988]; int
0x18003e9d4  xor     ebx, ebx
0x18003e9d6  xor     r9d, r9d; int
0x18003e9d9  mov     [rsp+0A18h+var_9D0], rbx; __int64
0x18003e9de  mov     ecx, r12d; int
0x18003e9e1  mov     [rsp+0A18h+var_9D8], r14; struct _GUID *
0x18003e9e6  mov     dword ptr [rsp+0A18h+var_9E0], esi; int
0x18003e9ea  lea     eax, [rbx+1]
0x18003e9ed  mov     dword ptr [rsp+0A18h+var_9E8], eax; int
0x18003e9f1  mov     [rsp+0A18h+var_9F0], eax; int
0x18003e9f5  mov     [rsp+0A18h+var_9F8], eax; int
0x18003e9f9  call    AddSingleRoute
0x18003e9fe  mov     r13d, eax
0x18003ea01  test    esi, esi
0x18003ea03  jz      loc_18003EB89
0x18003ea09  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18003ea0f  jge     loc_18003EB04
0x18003ea15  mov     edx, dword ptr [rsp+0A18h+var_988+4]
0x18003ea1c  lea     r8, aSucceeded; " succeeded"
0x18003ea23  mov     [rsp+0A18h+var_9B8], r13d
0x18003ea28  mov     ecx, edx
0x18003ea2a  shr     ecx, 10h
0x18003ea2d  mov     eax, edx
0x18003ea2f  shr     eax, 8
0x18003ea32  mov     esi, edx
0x18003ea34  movzx   edi, cl
0x18003ea37  mov     ecx, dword ptr [rsp+0A18h+var_988]
0x18003ea3e  mov     r10d, ecx
0x18003ea41  movzx   r11d, dl
0x18003ea45  shr     r10d, 18h
0x18003ea49  mov     word ptr [rsp+0A18h+var_848], bx
0x18003ea51  mov     word ptr [rsp+0A18h+var_8C0], bx
0x18003ea59  movzx   ebx, al
0x18003ea5c  mov     eax, ecx
  ... truncated ...
```

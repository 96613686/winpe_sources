# ChangeRouteWithForwarder

- ea: `0x180046848`
- end: `0x180047dbb`
- name: `ChangeRouteWithForwarder`
- size: `5491`
- prototype: `__int64 __usercall@<rax>(PRTM_NET_ADDRESS pNetAddress@<rcx>, int, struct _GUID *, int)`
- caller_count: `4`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800435e0`
- `0x1800482a4`
- `0x18004b844`
- `0x18004c950`

## callees

- `0x18000ac60`
- `0x180011790`
- `0x1800229ec`
- `0x18002ee20`
- `0x180045708`
- `0x180046848`
- `0x180051be4`
- `0x180057b34`
- `0x180057c48`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180058600`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x180047d8f`
- `msvcrt!_resetstkoflw` at `0x180047d8f`
- `ntdll!RtlReleaseResource` at `0x1800470f8`
- `ntdll!RtlReleaseResource` at `0x18004719c`
- `ntdll!RtlReleaseResource` at `0x18004753f`
- `ntdll!RtlReleaseResource` at `0x1800475d8`
- `ntdll!RtlReleaseResource` at `0x1800470f8`
- `ntdll!RtlReleaseResource` at `0x18004719c`
- `ntdll!RtlReleaseResource` at `0x18004753f`
- `ntdll!RtlReleaseResource` at `0x1800475d8`
- `ntdll!RtlAcquireResourceShared` at `0x1800470d0`
- `ntdll!RtlAcquireResourceShared` at `0x1800470d0`
- `WS2_32!__imp_htonl` at `0x180046b4b`
- `WS2_32!__imp_htonl` at `0x180046cb5`
- `WS2_32!__imp_htonl` at `0x180046b4b`
- `WS2_32!__imp_htonl` at `0x180046cb5`
- `rtm!RtmReleaseNextHopInfo` at `0x180047018`
- `rtm!RtmReleaseNextHopInfo` at `0x180047018`
- `rtm!RtmGetNextHopInfo` at `0x180046f8f`
- `rtm!RtmGetNextHopInfo` at `0x180046f8f`
- `rtm!RtmGetEntityInfo` at `0x180046eb5`
- `rtm!RtmGetEntityInfo` at `0x180046eb5`

## string_xrefs

- `0x1800471c5`: `Error %d retrieving loopback index for compartment %d\n `

## pseudocode

```c
__int64 __fastcall ChangeRouteWithForwarder(
        PRTM_NET_ADDRESS pNetAddress,
        __int64 a2,
        int a3,
        BOOL a4,
        unsigned int a5,
        struct _GUID *a6,
        int a7)
{
  char v10; // al
  __int128 *v11; // r9
  __int128 *v13; // r9
  const wchar_t *v14; // r8
  __int64 *v15; // rdx
  unsigned int v16; // ecx
  __int128 *v17; // r9
  unsigned int v18; // esi
  USHORT NumBits; // cx
  u_long v20; // ecx
  __int128 *v21; // r9
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // rcx
  unsigned __int64 v24; // rcx
  void *v25; // rsp
  void *v26; // rsp
  int v27; // ecx
  u_long v28; // eax
  __int128 *v29; // r9
  __int128 *v30; // r9
  NET_IF_COMPARTMENT_ID CompartmentIdForRoutingDomain; // eax
  unsigned int v32; // ebx
  __int64 v33; // rdi
  DWORD v34; // eax
  unsigned int v35; // ecx
  char v36; // cl
  __int128 *v37; // r9
  unsigned int v38; // edx
  __int64 v39; // rbx
  DWORD v40; // eax
  __int128 *v41; // r9
  __int128 *v42; // r9
  __int64 InterfaceBinding; // rax
  unsigned __int64 v44; // rdi
  __int128 *v45; // r9
  unsigned int LoopbackIdentifiersFromCompartmentId; // ebx
  unsigned int v47; // r10d
  char v48; // cl
  __int128 *v49; // r9
  int v50; // ebx
  char v51; // al
  __int128 *v52; // r9
  __int128 *v53; // r9
  int v54; // edx
  __int128 *v55; // r9
  unsigned int v56; // r8d
  __int128 *v57; // r9
  int v58; // ebx
  int v59; // eax
  __int64 v60; // rcx
  int v61; // r9d
  unsigned int v62; // edx
  int v63; // eax
  unsigned int v64; // r8d
  __int64 v65; // rcx
  __int128 *v66; // r9
  NET_IF_COMPARTMENT_ID v67; // eax
  unsigned int v68; // eax
  __int128 *v69; // r9
  __int128 *v70; // r9
  __int128 *v71; // r9
  __int128 *v72; // r9
  __int128 *v73; // r9
  __int128 *v74; // r9
  __int128 *v75; // r9
  __int128 *v76; // r9
  __int128 *v77; // r9
  __int128 *v78; // r9
  struct _GUID *v79; // [rsp+20h] [rbp-40h]
  int v80[2]; // [rsp+28h] [rbp-38h]
  __int64 v81; // [rsp+30h] [rbp-30h]
  __int64 v82; // [rsp+38h] [rbp-28h]
  __int64 v83; // [rsp+40h] [rbp-20h]
  __int64 v84; // [rsp+48h] [rbp-18h]
  unsigned int v85; // [rsp+60h] [rbp+0h] BYREF
  BOOL v86; // [rsp+64h] [rbp+4h]
  unsigned int v87; // [rsp+68h] [rbp+8h]
  int v88; // [rsp+6Ch] [rbp+Ch]
  unsigned int v89; // [rsp+70h] [rbp+10h]
  int v90; // [rsp+74h] [rbp+14h]
  __int64 v91; // [rsp+78h] [rbp+18h]
  int v92; // [rsp+80h] [rbp+20h]
  unsigned int v93; // [rsp+84h] [rbp+24h]
  unsigned __int64 v94; // [rsp+88h] [rbp+28h]
  RTM_ENTITY_HANDLE RtmRegHandle; // [rsp+90h] [rbp+30h]
  unsigned int *v96; // [rsp+98h] [rbp+38h]
  struct _RTM_NEXTHOP_INFO NextHopInfo; // [rsp+A0h] [rbp+40h] BYREF
  __int128 v98; // [rsp+D8h] [rbp+78h] BYREF
  struct _RTM_ENTITY_INFO EntityInfo; // [rsp+E8h] [rbp+88h] BYREF
  __int128 v100; // [rsp+F8h] [rbp+98h] BYREF
  int v101; // [rsp+108h] [rbp+A8h] BYREF
  __int128 v102; // [rsp+10Ch] [rbp+ACh]
  __int128 v103; // [rsp+11Ch] [rbp+BCh]
  int v104; // [rsp+12Ch] [rbp+CCh]
  int v105; // [rsp+130h] [rbp+D0h] BYREF
  char v106[2044]; // [rsp+134h] [rbp+D4h] BYREF

  v86 = a4;
  v88 = a3;
  v91 = a2;
  v93 = a5;
  EntityInfo = 0;
  memset(&NextHopInfo, 0, 52);
  v100 = 0;
  v105 = 0;
  memset_0(v106, 0, sizeof(v106));
  v101 = 0;
  v102 = 0;
  v103 = 0;
  v104 = 0;
  v98 = 0;
  v10 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v105) = 0;
    LOWORD(v101) = 0;
    FormatRRASErrorString(&v105, L"Entered: %ws", L"ChangeRouteWithForwarder");
    v10 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v11 = &v98;
      if ( a6 )
        LODWORD(v11) = (_DWORD)a6;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v105,
        (_DWORD)v11,
        0,
        (__int64)&v101);
      v10 = Microsoft_Windows_RRASEnableBits;
    }
  }
  if ( !v93 )
    return AddOrRemoteIPv6RouteToStack(pNetAddress, a2, a3, v86, a6, a7);
  if ( !g_bSetRoutesToStack )
  {
    if ( v10 < 0 )
    {
      LOWORD(v101) = 0;
      v13 = &v98;
      if ( a6 )
        LODWORD(v13) = (_DWORD)a6;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)L"ChangeRouteWithForwarder: SetRoutesToStack is FALSE",
        (_DWORD)v13,
        0,
        (__int64)&v101);
      v10 = Microsoft_Windows_RRASEnableBits;
    }
    if ( v10 >= 0 )
      return 0;
    goto LABEL_14;
  }
  if ( a3 )
  {
    if ( !a2 )
    {
      if ( (v10 & 0x40) != 0 )
      {
        v14 = L"Error adding route, route == NULL";
        goto LABEL_23;
      }
LABEL_42:
      if ( v10 < 0 )
      {
        LOWORD(v105) = 0;
        FormatRRASErrorString(&v105, L"Leaving: %ws", L"ChangeRouteWithForwarder");
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v105);
      }
      return 87;
    }
    if ( (*(_BYTE *)(a2 + 25) & 0x20) == 0 )
    {
      if ( v10 < 0 )
      {
        LOWORD(v105) = 0;
        LOWORD(v101) = 0;
        FormatRRASErrorString(
          &v105,
          L"INFO: Stack bit(%d) is clear. Route not added to stack",
          *(_BYTE *)(a2 + 25) & 0x20);
        v10 = Microsoft_Windows_RRASEnableBits;
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v17 = &v98;
          if ( a6 )
            LODWORD(v17) = (_DWORD)a6;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v105,
            (_DWORD)v17,
            0,
            (__int64)&v101);
          v10 = Microsoft_Windows_RRASEnableBits;
        }
      }
      v18 = *(_DWORD *)pNetAddress->AddrBits;
      NumBits = pNetAddress->NumBits;
      if ( NumBits )
      {
        v20 = htonl(-1 << (32 - NumBits));
        v10 = Microsoft_Windows_RRASEnableBits;
      }
      else
      {
        v20 = 0;
      }
      if ( v10 >= 0 )
        return 87;
      LOWORD(v105) = 0;
      LOWORD(v101) = 0;
      v80[0] = HIBYTE(v18);
      LODWORD(v79) = BYTE2(v18);
      FormatRRASErrorString(
        &v105,
        L"Not adding route with address: %d.%d.%d.%d/%d.%d.%d.%d",
        (unsigned __int8)v18,
        BYTE1(v18),
        v79,
        *(_QWORD *)v80,
        (unsigned __int8)v20,
        BYTE1(v20),
        BYTE2(v20),
        HIBYTE(v20));
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        return 87;
      v14 = (const wchar_t *)&v105;
      v15 = RasRtrmgrParamTraceInfo;
      goto LABEL_39;
    }
    if ( !*(_WORD *)(a2 + 48) )
    {
      if ( (v10 & 0x40) != 0 )
      {
        v14 = L"Error adding route, no nexthops";
LABEL_23:
        LOWORD(v101) = 0;
        v15 = RasRtrMgrParamTraceError;
LABEL_39:
        v21 = &v98;
        if ( a6 )
          LODWORD(v21) = (_DWORD)a6;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (_DWORD)v15,
          (_DWORD)v14,
          (_DWORD)v21,
          0,
          (__int64)&v101);
        v10 = Microsoft_Windows_RRASEnableBits;
        goto LABEL_42;
      }
      goto LABEL_42;
    }
    v16 = 16 * *(unsigned __int16 *)(a2 + 48) + 60;
  }
  else
  {
    v16 = 76;
  }
  v22 = v16;
  v23 = v16 + 15LL;
  if ( v23 <= v22 )
    v23 = 0xFFFFFFFFFFFFFF0LL;
  v24 = v23 & 0xFFFFFFFFFFFFFFF0uLL;
  v25 = alloca(v24);
  v26 = alloca(v24);
  v96 = &v85;
  v27 = pNetAddress->NumBits;
  v87 = *(_DWORD *)pNetAddress->AddrBits;
  if ( v27 )
    v28 = htonl(-1 << (32 - v27));
  else
    v28 = 0;
  LODWORD(RtmRegHandle) = v28;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v105) = 0;
    LOWORD(v101) = 0;
    v80[0] = HIBYTE(v87);
    LODWORD(v79) = BYTE2(v87);
    FormatRRASErrorString(
      &v105,
      L"route to %d.%d.%d.%d/%d.%d.%d.%d",
      (unsigned __int8)v87,
      BYTE1(v87),
      v79,
      *(_QWORD *)v80,
      (unsigned __int8)RtmRegHandle,
      BYTE1(RtmRegHandle),
      BYTE2(RtmRegHandle),
      BYTE3(RtmRegHandle));
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v29 = &v98;
      if ( a6 )
        LODWORD(v29) = (_DWORD)a6;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v105,
        (_DWORD)v29,
        0,
        (__int64)&v101);
    }
  }
  if ( !v88 )
  {
    v93 = 2;
    v85 = 0;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v105) = 0;
      LOWORD(v101) = 0;
      LODWORD(v84) = BYTE3(RtmRegHandle);
      LODWORD(v83) = BYTE2(RtmRegHandle);
      LODWORD(v82) = BYTE1(RtmRegHandle);
      LODWORD(v81) = (unsigned __int8)RtmRegHandle;
      v80[0] = HIBYTE(v87);
      LODWORD(v79) = BYTE2(v87);
      FormatRRASErrorString(
        &v105,
        L"ChangeRouteWithForwarder: Deleting all routes to %d.%d.%d.%d/%d.%d.%d.%d",
        (unsigned __int8)v87,
        BYTE1(v87),
        v79,
        *(_QWORD *)v80,
        v81,
        v82,
        v83,
        v84);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v30 = &v98;
        if ( a6 )
          LODWORD(v30) = (_DWORD)a6;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v105,
          (_DWORD)v30,
          0,
          (__int64)&v101);
      }
    }
    CompartmentIdForRoutingDomain = GetCompartmentIdForRoutingDomain(a6);
    v32 = SetIpMultihopRouteEntryToStack(&v85, CompartmentIdForRoutingDomain, a7);
    goto LABEL_64;
  }
  RtmRegHandle = (RTM_ENTITY_HANDLE)GetRtmRegistrationHandle(a6, 0x21u, 2u);
  v33 = v91;
  v34 = RtmGetEntityInfo(RtmRegHandle, *(RTM_ENTITY_HANDLE *)(v91 + 8), &EntityInfo);
  v32 = v34;
  v35 = 0;
  if ( v34 )
  {
    v36 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v105) = 0;
      LOWORD(v101) = 0;
      FormatRRASErrorString(&v105, L"Error %d retrieving entity info from RTM", v34);
      v36 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v37 = &v98;
        if ( a6 )
          LODWORD(v37) = (_DWORD)a6;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v105,
          (_DWORD)v37,
          0,
          (__int64)&v101);
        v36 = Microsoft_Windows_RRASEnableBits;
      }
    }
    if ( v36 < 0 )
      goto LABEL_65;
    return v32;
  }
  v94 = EntityInfo.EntityId.EntityProtocolId | 0xFFFFFFFF00000000uLL;
  v89 = *(_DWORD *)(v33 + 28);
  v90 = -1;
  v91 = -1;
  HIDWORD(RtmRegHandle) = -1;
  v38 = 0;
  v85 = 0;
  while ( 1 )
  {
    v89 = v35;
    if ( v35 >= *(unsigned __int16 *)(v33 + 48) )
      break;
    v39 = v35;
    v40 = RtmGetNextHopInfo(RtmRegHandle, *(RTM_NEXTHOP_HANDLE *)(v33 + 8LL * v35 + 56), &NextHopInfo);
    if ( v40 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v105) = 0;
        LOWORD(v101) = 0;
        FormatRRASErrorString(&v105, L"Error %d retrieving next hop info from RTM", v40);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v41 = &v98;
          if ( a6 )
            LODWORD(v41) = (_DWORD)a6;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v105,
            (_DWORD)v41,
            0,
            (__int64)&v101);
        }
      }
      goto LABEL_96;
    }
    RtmReleaseNextHopInfo(RtmRegHandle, &NextHopInfo);
    v87 = *(_DWORD *)NextHopInfo.NextHopAddress.AddrBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v105) = 0;
      LOWORD(v101) = 0;
      LODWORD(v81) = NextHopInfo.InterfaceIndex;
      v80[0] = NextHopInfo.NextHopAddress.AddrBits[3];
      LODWORD(v79) = NextHopInfo.NextHopAddress.AddrBits[2];
      FormatRRASErrorString(
        &v105,
        L"Next Hop %d.%d.%d.%d, If 0x%x, handle is 0x%x",
        NextHopInfo.NextHopAddress.AddrBits[0],
        NextHopInfo.NextHopAddress.AddrBits[1],
        v79,
        *(_QWORD *)v80,
        v81,
        *(_QWORD *)(v33 + 8 * v39 + 56));
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v42 = &v98;
        if ( a6 )
          LODWORD(v42) = (_DWORD)a6;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v105,
          (_DWORD)v42,
          0,
          (__int64)&v101);
      }
    }
    RtlAcquireResourceShared(&stru_18008C500, 1u);
    InterfaceBinding = GetInterfaceBinding(NextHopInfo.InterfaceIndex, v93);
    v44 = InterfaceBinding;
    v94 = InterfaceBinding;
    if ( !InterfaceBinding )
    {
      RtlReleaseResource(&stru_18008C500);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v105) = 0;
        LOWORD(v101) = 0;
        FormatRRASErrorString(
          &v105,
          L"**Warning** tried to %hs route with interface %d which is no longer present",
          "add",
          NextHopInfo.InterfaceIndex);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v45 = &v98;
          if ( a6 )
            LODWORD(v45) = (_DWORD)a6;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v105,
            (_DWORD)v45,
            0,
            (__int64)&v101);
        }
      }
      goto LABEL_95;
    }
    LoopbackIdentifiersFromCompartmentId = GetLoopbackIdentifiersFromCompartmentId(
                                             *(unsigned int *)(InterfaceBinding + 56),
                                             &v100);
    v47 = 0;
    if ( LoopbackIdentifiersFromCompartmentId )
    {
      RtlReleaseResource(&stru_18008C500);
      v48 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v105) = 0;
        LOWORD(v101) = 0;
        FormatRRASErrorString(
          &v105,
          L"Error %d retrieving loopback index for compartment %d\n ",
          LoopbackIdentifiersFromCompartmentId,
          *(unsigned int *)(v44 + 56));
        v48 = Microsoft_Windows_RRASEnableBits;
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v49 = &v98;
          if ( a6 )
            LODWORD(v49) = (_DWORD)a6;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v105,
            (_DWORD)v49,
            0,
            (__int64)&v101);
          v48 = Microsoft_Windows_RRASEnableBits;
        }
      }
      if ( v48 < 0 )
      {
        LOWORD(v105) = 0;
        FormatRRASErrorString(&v105, L"Leaving: %ws", L"AddDoDRoute");
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v105);
      }
      goto LABEL_95;
    }
    if ( *(_DWORD *)(v44 + 16) )
      v50 = *(_DWORD *)(v44 + 24);
    else
      v50 = DWORD2(v100);
    v92 = v50;
    v51 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v105) = 0;
      LOWORD(v101) = 0;
      FormatRRASErrorString(&v105, L"Using %d as the interface index for the route", *(unsigned int *)(v44 + 24));
      v51 = Microsoft_Windows_RRASEnableBits;
      v47 = 0;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v52 = &v98;
        if ( a6 )
          LODWORD(v52) = (_DWORD)a6;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v105,
          (_DWORD)v52,
          0,
          (__int64)&v101);
        v51 = Microsoft_Windows_RRASEnableBits;
        v47 = 0;
      }
    }
    if ( (((_DWORD)v94 - 10002) & 0xFFFFFFFB) != 0 || *(_DWORD *)(v44 + 48) != 2 )
    {
      v88 = 0;
      if ( v50 == -1 )
      {
        if ( (v51 & 0x40) != 0 )
        {
          LOWORD(v105) = 0;
          LOWORD(v101) = 0;
          LODWORD(v82) = *(_DWORD *)(v44 + 24);
          LODWORD(v81) = HIBYTE(v87);
          v80[0] = BYTE2(v87);
          LODWORD(v79) = BYTE1(v87);
          FormatRRASErrorString(
            &v105,
            L"**Error** Tried to %hs route to %d.%d.%d.%d over %d as DOD\n",
            "add",
            (unsigned __int8)v87,
            v79,
            *(_QWORD *)v80,
            v81,
            v82);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            v57 = &v98;
            if ( a6 )
              LODWORD(v57) = (_DWORD)a6;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrMgrParamTraceError,
              (unsigned int)&v105,
              (_DWORD)v57,
              0,
              (__int64)&v101);
          }
        }
        RtlReleaseResource(&stru_18008C500);
LABEL_95:
        v33 = v91;
LABEL_96:
        v38 = v85;
        goto LABEL_97;
      }
    }
    else
    {
      v88 = *(_DWORD *)(v44 + 100);
      if ( v51 < 0 )
      {
        LOWORD(v105) = 0;
        LOWORD(v101) = 0;
        FormatRRASErrorString(&v105, L"route context : ICB == %d\n\n", *(unsigned int *)(v44 + 100));
        v51 = Microsoft_Windows_RRASEnableBits;
        v47 = 0;
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v53 = &v98;
          if ( a6 )
            LODWORD(v53) = (_DWORD)a6;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v105,
            (_DWORD)v53,
            0,
            (__int64)&v101);
          v51 = Microsoft_Windows_RRASEnableBits;
          v47 = 0;
        }
      }
    }
    v54 = *(_DWORD *)(v44 + 48);
    if ( (unsigned int)(v54 - 1) <= 1 || v54 == 7 )
    {
      if ( *(_DWORD *)(v44 + 16) )
      {
        if ( v51 < 0 )
        {
          LOWORD(v105) = 0;
          LOWORD(v101) = 0;
          LODWORD(v84) = *(unsigned __int8 *)(v44 + 79);
          LODWORD(v83) = *(unsigned __int8 *)(v44 + 78);
          LODWORD(v82) = *(unsigned __int8 *)(v44 + 77);
          LODWORD(v81) = *(unsigned __int8 *)(v94 + 76);
          v80[0] = HIBYTE(v87);
          LODWORD(v79) = BYTE2(v87);
          FormatRRASErrorString(
            &v105,
            L"Next Hop %d.%d.%d.%d, remote address %d.%d.%d.%d, bound p2p",
            (unsigned __int8)v87,
            BYTE1(v87),
            v79,
            *(_QWORD *)v80,
            v81,
            v82,
            v83,
            v84);
          v47 = 0;
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            v55 = &v98;
            if ( a6 )
              LODWORD(v55) = (_DWORD)a6;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrmgrParamTraceInfo,
              (unsigned int)&v105,
              (_DWORD)v55,
              0,
              (__int64)&v101);
            v47 = 0;
          }
          v44 = v94;
        }
        v56 = v87;
        if ( !v87 && *(_DWORD *)(v44 + 48) != 2 )
        {
          v56 = *(_DWORD *)(v44 + 76);
          v87 = v56;
        }
      }
      else
      {
        v56 = 0;
        v87 = 0;
      }
    }
    else
    {
      v56 = v87;
    }
    v58 = 1;
    if ( *(_DWORD *)(v44 + 16) )
    {
      if ( *(_DWORD *)(v44 + 52) == 1 && *(_DWORD *)(v44 + 108) == -1 )
      {
        v59 = *(_DWORD *)(v44 + 76);
        if ( v59 && v87 == v59 || v87 == v56 || *(_DWORD *)(v44 + 104) == v56 )
LABEL_157:
          v58 = 3;
        else
          v58 = 4;
      }
      else
      {
        v58 = 4;
        while ( 1 )
        {
          v89 = v47;
          if ( v47 >= *(_DWORD *)(v44 + 52) )
            break;
          v60 = 28LL * v47;
          v61 = *(_DWORD *)(v60 + v44 + 104);
          if ( (*(_DWORD *)(v60 + v44 + 108) & v61) == (*(_DWORD *)(v60 + v44 + 108) & v87)
            || v56 == 16777343
            || v56 == v61 )
          {
            goto LABEL_157;
          }
          ++v47;
        }
      }
    }
    RtlReleaseResource(&stru_18008C500);
    v62 = v85;
    v63 = v92;
    v64 = v87;
    if ( v85 )
    {
      v65 = 2LL * (v85 - 1);
      *((_DWORD *)&v96 + 2 * v65 + 1) = v58;
      *(_DWORD *)&NextHopInfo.NextHopAddress.AddrBits[8 * v65] = v63;
      *((_DWORD *)&NextHopInfo.NextHopAddress.AddressFamily + 2 * v65) = v64;
      *(_DWORD *)&NextHopInfo.NextHopAddress.AddrBits[8 * v65 + 4] = v88;
    }
    else
    {
      v93 = v58;
      v88 = v92;
      v92 = v87;
      LODWORD(v96) = v63;
    }
    v38 = v62 + 1;
    v85 = v38;
    v33 = v91;
LABEL_97:
    v35 = v89 + 1;
  }
  v85 = v38;
  v86 = v86;
  if ( !v38 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v101) = 0;
      v76 = &v98;
      if ( a6 )
        LODWORD(v76) = (_DWORD)a6;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)L"Route not added since there are no next hops",
        (_DWORD)v76,
        0,
        (__int64)&v101);
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v105) = 0;
      LOWORD(v101) = 0;
      LODWORD(v84) = BYTE3(RtmRegHandle);
      LODWORD(v83) = BYTE2(RtmRegHandle);
      LODWORD(v82) = BYTE1(RtmRegHandle);
      LODWORD(v81) = (unsigned __int8)RtmRegHandle;
      v80[0] = HIBYTE(v87);
      LODWORD(v79) = BYTE2(v87);
      FormatRRASErrorString(
        &v105,
        L"%d.%d.%d.%d/%d.%d.%d.%d Proto: %d Metric %d",
        (unsigned __int8)v87,
        BYTE1(v87),
        v79,
        *(_QWORD *)v80,
        v81,
        v82,
        v83,
        v84,
        v94,
        v89);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v77 = &v98;
        if ( a6 )
          LODWORD(v77) = (_DWORD)a6;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v105,
          (_DWORD)v77,
          0,
          (__int64)&v101);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          LOWORD(v105) = 0;
          LOWORD(v101) = 0;
          LODWORD(v83) = (_DWORD)v96;
          LODWORD(v82) = v93;
          LODWORD(v81) = v88;
          v80[0] = HIBYTE(v92);
          LODWORD(v79) = BYTE2(v92);
          FormatRRASErrorString(
            &v105,
            L"Via %d.%d.%d.%d/0x%x Type %d Context 0x%x",
            (unsigned __int8)v92,
            BYTE1(v92),
            v79,
            *(_QWORD *)v80,
            v81,
            v82,
            v83);
          goto LABEL_220;
        }
      }
    }
    while ( v85 > 1 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v105) = 0;
        LOWORD(v101) = 0;
        LODWORD(v83) = NextHopInfo.NextHopOwner;
        LODWORD(v82) = *(_DWORD *)&NextHopInfo.NextHopAddress.AddrBits[8];
        LODWORD(v81) = *((_DWORD *)&NextHopInfo.NextHopAddress + 5);
        v80[0] = NextHopInfo.NextHopAddress.AddrBits[15];
        LODWORD(v79) = NextHopInfo.NextHopAddress.AddrBits[14];
        FormatRRASErrorString(
          &v105,
          L"Via %d.%d.%d.%d/0x%x Type %d Context 0x%x\n",
          NextHopInfo.NextHopAddress.AddrBits[12],
          NextHopInfo.NextHopAddress.AddrBits[13],
          v79,
          *(_QWORD *)v80,
          v81,
          v82,
          v83);
LABEL_220:
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v78 = &v98;
          if ( a6 )
            LODWORD(v78) = (_DWORD)a6;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v105,
            (_DWORD)v78,
            0,
            (__int64)&v101);
        }
        continue;
      }
    }
LABEL_227:
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return 0;
LABEL_14:
    LOWORD(v105) = 0;
    FormatRRASErrorString(&v105, L"Leaving: %ws", L"ChangeRouteWithForwarder");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v105);
    return 0;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v105) = 0;
    LOWORD(v101) = 0;
    LODWORD(v84) = BYTE3(RtmRegHandle);
    LODWORD(v83) = BYTE2(RtmRegHandle);
    LODWORD(v82) = BYTE1(RtmRegHandle);
    LODWORD(v81) = (unsigned __int8)RtmRegHandle;
    v80[0] = HIBYTE(v87);
    LODWORD(v79) = BYTE2(v87);
    FormatRRASErrorString(
      &v105,
      L"ChangeRouteWithForwarder: Adding routes to %d.%d.%d.%d/%d.%d.%d.%d",
      (unsigned __int8)v87,
      BYTE1(v87),
      v79,
      *(_QWORD *)v80,
      v81,
      v82,
      v83,
      v84);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v66 = &v98;
      if ( a6 )
        LODWORD(v66) = (_DWORD)a6;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v105,
        (_DWORD)v66,
        0,
        (__int64)&v101);
    }
  }
  v67 = GetCompartmentIdForRoutingDomain(a6);
  v68 = SetIpMultihopRouteEntryToStack(&v85, v67, a7);
  v32 = v68;
  v86 = v68;
  if ( !v68 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v101) = 0;
      v73 = &v98;
      if ( a6 )
        LODWORD(v73) = (_DWORD)a6;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)L"Route addition succeeded for",
        (_DWORD)v73,
        0,
        (__int64)&v101);
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_208;
    LOWORD(v105) = 0;
    LOWORD(v101) = 0;
    LODWORD(v84) = BYTE3(RtmRegHandle);
    LODWORD(v83) = BYTE2(RtmRegHandle);
    LODWORD(v82) = BYTE1(RtmRegHandle);
    LODWORD(v81) = (unsigned __int8)RtmRegHandle;
    v80[0] = HIBYTE(v87);
    LODWORD(v79) = BYTE2(v87);
    FormatRRASErrorString(
      &v105,
      L"%d.%d.%d.%d/%d.%d.%d.%d Proto: %d Metric %d",
      (unsigned __int8)v87,
      BYTE1(v87),
      v79,
      *(_QWORD *)v80,
      v81,
      v82,
      v83,
      v84,
      v94,
      v89);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_208;
    v74 = &v98;
    if ( a6 )
      LODWORD(v74) = (_DWORD)a6;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)&v105,
      (_DWORD)v74,
      0,
      (__int64)&v101);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
    {
LABEL_208:
      do
      {
LABEL_207:
        if ( v85 <= 1 )
          goto LABEL_227;
      }
      while ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL );
      LOWORD(v105) = 0;
      LOWORD(v101) = 0;
      LODWORD(v83) = NextHopInfo.NextHopOwner;
      LODWORD(v82) = *(_DWORD *)&NextHopInfo.NextHopAddress.AddrBits[8];
      LODWORD(v81) = *((_DWORD *)&NextHopInfo.NextHopAddress + 5);
      v80[0] = NextHopInfo.NextHopAddress.AddrBits[15];
      LODWORD(v79) = NextHopInfo.NextHopAddress.AddrBits[14];
      FormatRRASErrorString(
        &v105,
        L"Via %d.%d.%d.%d/0x%x Type %d Context 0x%x\n",
        NextHopInfo.NextHopAddress.AddrBits[12],
        NextHopInfo.NextHopAddress.AddrBits[13],
        v79,
        *(_QWORD *)v80,
        v81,
        v82,
        v83);
    }
    else
    {
      LOWORD(v105) = 0;
      LOWORD(v101) = 0;
      LODWORD(v83) = (_DWORD)v96;
      LODWORD(v82) = v93;
      LODWORD(v81) = v88;
      v80[0] = HIBYTE(v92);
      LODWORD(v79) = BYTE2(v92);
      FormatRRASErrorString(
        &v105,
        L"Via %d.%d.%d.%d/0x%x Type %d Context 0x%x",
        (unsigned __int8)v92,
        BYTE1(v92),
        v79,
        *(_QWORD *)v80,
        v81,
        v82,
        v83);
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v75 = &v98;
      if ( a6 )
        LODWORD(v75) = (_DWORD)a6;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v105,
        (_DWORD)v75,
        0,
        (__int64)&v101);
    }
    goto LABEL_207;
  }
  if ( v92 != 16777343 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_186;
    LOWORD(v105) = 0;
    LOWORD(v101) = 0;
    FormatRRASErrorString(&v105, L"Route addition failed with %x for", v68);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_186;
    v69 = &v98;
    if ( a6 )
      LODWORD(v69) = (_DWORD)a6;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)&v105,
      (_DWORD)v69,
      0,
      (__int64)&v101);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_186;
    LOWORD(v105) = 0;
    LOWORD(v101) = 0;
    LODWORD(v84) = BYTE3(RtmRegHandle);
    LODWORD(v83) = BYTE2(RtmRegHandle);
    LODWORD(v82) = BYTE1(RtmRegHandle);
    LODWORD(v81) = (unsigned __int8)RtmRegHandle;
    v80[0] = HIBYTE(v87);
    LODWORD(v79) = BYTE2(v87);
    FormatRRASErrorString(
      &v105,
      L"%d.%d.%d.%d/%d.%d.%d.%d Proto: %d Metric %d",
      (unsigned __int8)v87,
      BYTE1(v87),
      v79,
      *(_QWORD *)v80,
      v81,
      v82,
      v83,
      v84,
      v94,
      v89);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v70 = &v98;
      if ( a6 )
        LODWORD(v70) = (_DWORD)a6;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v105,
        (_DWORD)v70,
        0,
        (__int64)&v101);
    }
    v32 = v86;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
    {
LABEL_186:
      do
      {
LABEL_185:
        if ( v85 <= 1 )
          goto LABEL_188;
      }
      while ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL );
      LOWORD(v105) = 0;
      LOWORD(v101) = 0;
      LODWORD(v83) = NextHopInfo.NextHopOwner;
      LODWORD(v82) = *(_DWORD *)&NextHopInfo.NextHopAddress.AddrBits[8];
      LODWORD(v81) = *((_DWORD *)&NextHopInfo.NextHopAddress + 5);
      v80[0] = NextHopInfo.NextHopAddress.AddrBits[15];
      LODWORD(v79) = NextHopInfo.NextHopAddress.AddrBits[14];
      FormatRRASErrorString(
        &v105,
        L"Via %d.%d.%d.%d/0x%x Type %d Context 0x%x\n",
        NextHopInfo.NextHopAddress.AddrBits[12],
        NextHopInfo.NextHopAddress.AddrBits[13],
        v79,
        *(_QWORD *)v80,
        v81,
        v82,
        v83);
    }
    else
    {
      LOWORD(v105) = 0;
      LOWORD(v101) = 0;
      LODWORD(v83) = (_DWORD)v96;
      LODWORD(v82) = v93;
      LODWORD(v81) = v88;
      v80[0] = HIBYTE(v92);
      LODWORD(v79) = BYTE2(v92);
      FormatRRASErrorString(
        &v105,
        L"Via %d.%d.%d.%d/0x%x Type %d Context 0x%x",
        (unsigned __int8)v92,
        BYTE1(v92),
        v79,
        *(_QWORD *)v80,
        v81,
        v82,
        v83);
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v71 = &v98;
      if ( a6 )
        LODWORD(v71) = (_DWORD)a6;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v105,
        (_DWORD)v71,
        0,
        (__int64)&v101);
    }
    goto LABEL_185;
  }
LABEL_188:
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v105) = 0;
    LOWORD(v101) = 0;
    FormatRRASErrorString(&v105, L"Route addition failed with %x for local route", v32);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v72 = &v98;
      if ( a6 )
        LODWORD(v72) = (_DWORD)a6;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v105,
        (_DWORD)v72,
        0,
        (__int64)&v101);
LABEL_64:
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
LABEL_65:
        LOWORD(v105) = 0;
        FormatRRASErrorString(&v105, L"Leaving: %ws", L"ChangeRouteWithForwarder");
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v105);
      }
    }
  }
  return v32;
}

```

## disassembly

```asm
0x180046848  push    rbp
0x18004684a  push    rbx
0x18004684b  push    rsi
0x18004684c  push    rdi
0x18004684d  push    r12
0x18004684f  push    r14
0x180046851  push    r15
0x180046853  sub     rsp, 940h
0x18004685a  lea     rbp, [rsp+60h]
0x18004685f  mov     rax, cs:__security_cookie
0x180046866  xor     rax, rbp
0x180046869  mov     [rbp+910h+var_40], rax
0x180046870  mov     [rbp+910h+var_90C], r9d
0x180046874  mov     ebx, r8d
0x180046877  mov     [rbp+910h+var_904], ebx
0x18004687a  mov     rsi, rdx
0x18004687d  mov     [rbp+910h+var_8F8], rdx
0x180046881  mov     rdi, rcx
0x180046884  mov     r14, [rbp+910h+arg_28]
0x18004688b  mov     eax, [rbp+910h+arg_20]
0x180046891  mov     [rbp+910h+var_8EC], eax
0x180046894  xorps   xmm0, xmm0
0x180046897  movups  xmmword ptr [rbp+910h+EntityInfo.RtmInstanceId], xmm0
0x18004689e  xor     eax, eax
0x1800468a0  movups  xmmword ptr [rbp+910h+NextHopInfo.NextHopAddress.AddressFamily], xmm0
0x1800468a4  movups  xmmword ptr [rbp+910h+NextHopInfo.NextHopAddress.AddrBits+0Ch], xmm0
0x1800468a8  movups  xmmword ptr [rbp+910h+NextHopInfo.InterfaceIndex], xmm0
0x1800468ac  mov     dword ptr [rbp+910h+NextHopInfo.RemoteNextHop], eax
0x1800468af  movups  [rbp+910h+var_878], xmm0
0x1800468b6  xor     ecx, ecx
0x1800468b8  mov     [rbp+910h+var_840], ecx
0x1800468be  xor     edx, edx; Val
0x1800468c0  mov     r8d, 7FCh; Size
0x1800468c6  lea     rcx, [rbp+910h+var_83C]; void *
0x1800468cd  call    memset_0
0x1800468d2  xor     edx, edx
0x1800468d4  mov     [rbp+910h+var_868], edx
0x1800468da  xorps   xmm0, xmm0
0x1800468dd  xor     eax, eax
0x1800468df  movups  [rbp+910h+var_864], xmm0
0x1800468e6  movups  [rbp+910h+var_854], xmm0
0x1800468ed  mov     [rbp+910h+var_844], eax
0x1800468f3  movups  [rbp+910h+var_898], xmm0
0x1800468f7  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x1800468fe  test    al, al
0x180046900  jns     short loc_18004697E
0x180046902  mov     word ptr [rbp+910h+var_840], dx
0x180046909  mov     word ptr [rbp+910h+var_868], dx
0x180046910  lea     r8, aChangeroutewit; "ChangeRouteWithForwarder"
0x180046917  lea     rdx, aEnteredWs; "Entered: %ws"
0x18004691e  lea     rcx, [rbp+910h+var_840]
0x180046925  call    FormatRRASErrorString
0x18004692a  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180046931  xor     edx, edx
0x180046933  lea     r12, RasRtrmgrParamTraceInfo
0x18004693a  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180046941  test    al, al
0x180046943  jns     short loc_18004698C
0x180046945  lea     r9, [rbp+910h+var_898]
0x180046949  test    r14, r14
0x18004694c  cmovnz  r9, r14
0x180046950  lea     rax, [rbp+910h+var_868]
0x180046957  mov     qword ptr [rsp+970h+var_948], rax
0x18004695c  mov     [rsp+970h+var_950], rdx
0x180046961  lea     r8, [rbp+910h+var_840]
0x180046968  mov     rdx, r12
0x18004696b  mov     rcx, r15
0x18004696e  call    McTemplateU0zjzz_EventWriteTransfer
0x180046973  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18004697a  xor     edx, edx
0x18004697c  jmp     short loc_18004698C
0x18004697e  lea     r12, RasRtrmgrParamTraceInfo
0x180046985  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004698c  cmp     [rbp+910h+var_8EC], edx
0x18004698f  jnz     short loc_1800469B7
0x180046991  mov     eax, [rbp+910h+arg_30]
0x180046997  mov     [rsp+970h+var_948], eax; int
0x18004699b  mov     [rsp+970h+var_950], r14; struct _GUID *
0x1800469a0  mov     r9d, [rbp+910h+var_90C]
0x1800469a4  mov     r8d, ebx
0x1800469a7  mov     rdx, rsi
0x1800469aa  mov     rcx, rdi; pNetAddress
0x1800469ad  call    AddOrRemoteIPv6RouteToStack
0x1800469b2  jmp     loc_180047D9A
0x1800469b7  cmp     cs:g_bSetRoutesToStack, edx
0x1800469bd  jnz     loc_180046A50
0x1800469c3  test    al, 80h
0x1800469c5  jz      short loc_180046A05
0x1800469c7  mov     word ptr [rbp+910h+var_868], dx
0x1800469ce  lea     r9, [rbp+910h+var_898]
0x1800469d2  test    r14, r14
0x1800469d5  cmovnz  r9, r14
0x1800469d9  lea     rax, [rbp+910h+var_868]
0x1800469e0  mov     qword ptr [rsp+970h+var_948], rax
0x1800469e5  mov     [rsp+970h+var_950], rdx
0x1800469ea  lea     r8, aChangeroutewit_2; "ChangeRouteWithForwarder: SetRoutesToSt"...
0x1800469f1  mov     rdx, r12
0x1800469f4  mov     rcx, r15
0x1800469f7  call    McTemplateU0zjzz_EventWriteTransfer
0x1800469fc  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180046a03  xor     edx, edx
0x180046a05  test    al, al
0x180046a07  jns     short loc_180046A49
0x180046a09  mov     word ptr [rbp+910h+var_840], dx
0x180046a10  lea     r8, aChangeroutewit; "ChangeRouteWithForwarder"
0x180046a17  lea     rdx, aLeavingWs; "Leaving: %ws"
0x180046a1e  lea     rcx, [rbp+910h+var_840]
0x180046a25  call    FormatRRASErrorString
0x180046a2a  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180046a31  jge     short loc_180046A49
0x180046a33  lea     r8, [rbp+910h+var_840]
0x180046a3a  lea     rdx, RasRtrmgrTraceInfo
0x180046a41  mov     rcx, r15
0x180046a44  call    McTemplateU0z_EventWriteTransfer
0x180046a49  xor     eax, eax
0x180046a4b  jmp     loc_180047D9A
0x180046a50  test    ebx, ebx
0x180046a52  mov     ebx, 20h ; ' '
0x180046a57  jz      loc_180046C6A
0x180046a5d  test    rsi, rsi
0x180046a60  jz      short loc_180046AB2
0x180046a62  test    [rsi+19h], bl
0x180046a65  jz      short loc_180046AAD
0x180046a67  movzx   ecx, word ptr [rsi+30h]
0x180046a6b  test    ecx, ecx
0x180046a6d  jnz     short loc_180046AA2
0x180046a6f  test    al, 40h
0x180046a71  jz      loc_180046C1C
0x180046a77  lea     r8, aErrorAddingRou; "Error adding route, no nexthops"
0x180046a7e  lea     rax, [rbp+910h+var_868]
0x180046a85  mov     qword ptr [rsp+970h+var_948], rax
0x180046a8a  mov     [rsp+970h+var_950], rdx
0x180046a8f  mov     word ptr [rbp+910h+var_868], dx
0x180046a96  lea     rdx, RasRtrMgrParamTraceError
0x180046a9d  jmp     loc_180046C00
0x180046aa2  shl     ecx, 4
0x180046aa5  add     ecx, 3Ch ; '<'
0x180046aa8  jmp     loc_180046C6F
0x180046aad  test    rsi, rsi
0x180046ab0  jnz     short loc_180046AC3
0x180046ab2  test    al, 40h
0x180046ab4  jz      loc_180046C1C
0x180046aba  lea     r8, aErrorAddingRou_0; "Error adding route, route == NULL"
0x180046ac1  jmp     short loc_180046A7E
0x180046ac3  test    al, al
0x180046ac5  jns     short loc_180046B34
0x180046ac7  mov     word ptr [rbp+910h+var_840], dx
0x180046ace  mov     word ptr [rbp+910h+var_868], dx
0x180046ad5  movzx   r8d, byte ptr [rsi+19h]
0x180046ada  and     r8d, ebx
0x180046add  lea     rdx, aInfoStackBitDI; "INFO: Stack bit(%d) is clear. Route not"...
0x180046ae4  lea     rcx, [rbp+910h+var_840]
0x180046aeb  call    FormatRRASErrorString
0x180046af0  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180046af7  xor     edx, edx
0x180046af9  test    al, al
0x180046afb  jns     short loc_180046B34
0x180046afd  lea     r9, [rbp+910h+var_898]
0x180046b01  test    r14, r14
0x180046b04  cmovnz  r9, r14
0x180046b08  lea     rax, [rbp+910h+var_868]
0x180046b0f  mov     qword ptr [rsp+970h+var_948], rax
0x180046b14  mov     [rsp+970h+var_950], rdx
0x180046b19  lea     r8, [rbp+910h+var_840]
0x180046b20  mov     rdx, r12
0x180046b23  mov     rcx, r15
0x180046b26  call    McTemplateU0zjzz_EventWriteTransfer
0x180046b2b  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180046b32  xor     edx, edx
0x180046b34  mov     esi, [rdi+4]
0x180046b37  movzx   ecx, word ptr [rdi+2]
0x180046b3b  test    cx, cx
0x180046b3e  jz      short loc_180046B5E
0x180046b40  sub     ebx, ecx
0x180046b42  or      eax, 0FFFFFFFFh
0x180046b45  mov     cl, bl
0x180046b47  shl     eax, cl
0x180046b49  mov     ecx, eax; hostlong
0x180046b4b  call    cs:__imp_htonl
0x180046b51  mov     ecx, eax
0x180046b53  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180046b5a  xor     edx, edx
0x180046b5c  jmp     short loc_180046B60
0x180046b5e  mov     ecx, edx
0x180046b60  test    al, al
0x180046b62  jns     loc_180046C60
0x180046b68  mov     word ptr [rbp+910h+var_840], dx
0x180046b6f  mov     word ptr [rbp+910h+var_868], dx
0x180046b76  mov     edi, ecx
0x180046b78  shr     edi, 18h
0x180046b7b  mov     eax, ecx
0x180046b7d  shr     eax, 10h
0x180046b80  movzx   ebx, al
0x180046b83  mov     eax, ecx
0x180046b85  shr     eax, 8
0x180046b88  movzx   r11d, al
0x180046b8c  movzx   edx, cl
0x180046b8f  mov     r10d, esi
0x180046b92  shr     r10d, 18h
0x180046b96  mov     eax, esi
0x180046b98  shr     eax, 10h
0x180046b9b  movzx   ecx, al
0x180046b9e  mov     eax, esi
0x180046ba0  shr     eax, 8
0x180046ba3  movzx   r9d, al
0x180046ba7  movzx   r8d, sil
0x180046bab  mov     dword ptr [rsp+970h+var_928], edi
0x180046baf  mov     dword ptr [rsp+970h+var_930], ebx
0x180046bb3  mov     dword ptr [rsp+970h+var_938], r11d
0x180046bb8  mov     dword ptr [rsp+970h+var_940], edx
0x180046bbc  mov     [rsp+970h+var_948], r10d
0x180046bc1  mov     dword ptr [rsp+970h+var_950], ecx
0x180046bc5  lea     rdx, aNotAddingRoute_0; "Not adding route with address: %d.%d.%d"...
0x180046bcc  lea     rcx, [rbp+910h+var_840]
0x180046bd3  call    FormatRRASErrorString
0x180046bd8  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180046bdf  xor     edx, edx
0x180046be1  test    al, al
0x180046be3  jns     short loc_180046C60
0x180046be5  lea     rax, [rbp+910h+var_868]
0x180046bec  mov     qword ptr [rsp+970h+var_948], rax
0x180046bf1  mov     [rsp+970h+var_950], rdx
0x180046bf6  lea     r8, [rbp+910h+var_840]
0x180046bfd  mov     rdx, r12
0x180046c00  lea     r9, [rbp+910h+var_898]
0x180046c04  test    r14, r14
0x180046c07  cmovnz  r9, r14
0x180046c0b  mov     rcx, r15
0x180046c0e  call    McTemplateU0zjzz_EventWriteTransfer
0x180046c13  xor     edx, edx
0x180046c15  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180046c1c  test    al, al
0x180046c1e  jns     short loc_180046C60
0x180046c20  mov     word ptr [rbp+910h+var_840], dx
0x180046c27  lea     r8, aChangeroutewit; "ChangeRouteWithForwarder"
0x180046c2e  lea     rdx, aLeavingWs; "Leaving: %ws"
0x180046c35  lea     rcx, [rbp+910h+var_840]
0x180046c3c  call    FormatRRASErrorString
0x180046c41  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180046c48  jge     short loc_180046C60
0x180046c4a  lea     r8, [rbp+910h+var_840]
0x180046c51  lea     rdx, RasRtrmgrTraceInfo
0x180046c58  mov     rcx, r15
0x180046c5b  call    McTemplateU0z_EventWriteTransfer
0x180046c60  mov     eax, 57h ; 'W'
0x180046c65  jmp     loc_180047D9A
0x180046c6a  mov     ecx, 4Ch ; 'L'
0x180046c6f  mov     eax, ecx
0x180046c71  lea     rcx, [rax+0Fh]
0x180046c75  cmp     rcx, rax
0x180046c78  ja      short loc_180046C84
0x180046c7a  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180046c84  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180046c88  mov     rax, rcx
0x180046c8b  call    _alloca_probe
0x180046c90  sub     rsp, rcx
0x180046c93  lea     rsi, [rsp+970h+var_910]
0x180046c98  mov     [rbp+910h+var_8D8], rsi
0x180046c9c  movzx   ecx, word ptr [rdi+2]
0x180046ca0  mov     eax, [rdi+4]
0x180046ca3  mov     [rsi+8], eax
0x180046ca6  test    ecx, ecx
0x180046ca8  jz      short loc_180046CBF
0x180046caa  sub     ebx, ecx
0x180046cac  or      eax, 0FFFFFFFFh
0x180046caf  mov     cl, bl
0x180046cb1  shl     eax, cl
0x180046cb3  mov     ecx, eax; hostlong
0x180046cb5  call    cs:__imp_htonl
0x180046cbb  xor     edx, edx
0x180046cbd  jmp     short loc_180046CC1
0x180046cbf  mov     eax, edx
0x180046cc1  mov     [rsi+30h], eax
0x180046cc4  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dl
0x180046cca  jge     loc_180046D69
0x180046cd0  mov     word ptr [rbp+910h+var_840], dx
0x180046cd7  mov     word ptr [rbp+910h+var_868], dx
0x180046cde  movzx   r10d, byte ptr [rsi+33h]
0x180046ce3  movzx   r11d, byte ptr [rsi+32h]
0x180046ce8  movzx   ebx, byte ptr [rsi+31h]
0x180046cec  movzx   eax, byte ptr [rsi+30h]
0x180046cf0  movzx   ecx, byte ptr [rsi+0Bh]
0x180046cf4  movzx   edx, byte ptr [rsi+0Ah]
0x180046cf8  movzx   r9d, byte ptr [rsi+9]
0x180046cfd  movzx   r8d, byte ptr [rsi+8]
0x180046d02  mov     dword ptr [rsp+970h+var_928], r10d
0x180046d07  mov     dword ptr [rsp+970h+var_930], r11d
0x180046d0c  mov     dword ptr [rsp+970h+var_938], ebx
0x180046d10  mov     dword ptr [rsp+970h+var_940], eax
0x180046d14  mov     [rsp+970h+var_948], ecx
0x180046d18  mov     dword ptr [rsp+970h+var_950], edx
0x180046d1c  lea     rdx, aRouteToDDDDDDD; "route to %d.%d.%d.%d/%d.%d.%d.%d"
0x180046d23  lea     rcx, [rbp+910h+var_840]
0x180046d2a  call    FormatRRASErrorString
0x180046d2f  xor     edx, edx
0x180046d31  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dl
0x180046d37  jge     short loc_180046D69
0x180046d39  lea     r9, [rbp+910h+var_898]
0x180046d3d  test    r14, r14
0x180046d40  cmovnz  r9, r14
  ... truncated ...
```

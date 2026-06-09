# AddOrRemoteIPv6RouteToStack

- ea: `0x180045708`
- end: `0x18004683f`
- name: `AddOrRemoteIPv6RouteToStack`
- size: `4407`
- prototype: `__int64 __usercall@<rax>(PRTM_NET_ADDRESS pNetAddress@<rcx>, struct _GUID *, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180046848`

## callees

- `0x1800010a0`
- `0x18000ac60`
- `0x18000f80c`
- `0x180011790`
- `0x180022560`
- `0x18002ee20`
- `0x180045708`
- `0x180051be4`
- `0x180052dc4`
- `0x180057b34`
- `0x180057c48`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180046186`
- `ntdll!RtlReleaseResource` at `0x180046205`
- `ntdll!RtlReleaseResource` at `0x1800464a5`
- `ntdll!RtlReleaseResource` at `0x180046602`
- `ntdll!RtlReleaseResource` at `0x180046186`
- `ntdll!RtlReleaseResource` at `0x180046205`
- `ntdll!RtlReleaseResource` at `0x1800464a5`
- `ntdll!RtlReleaseResource` at `0x180046602`
- `ntdll!RtlAcquireResourceShared` at `0x180046163`
- `ntdll!RtlAcquireResourceShared` at `0x180046163`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x1800464b6`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x1800464b6`
- `rtm!RtmReleaseNextHopInfo` at `0x180046089`
- `rtm!RtmReleaseNextHopInfo` at `0x180046089`
- `rtm!RtmGetNextHopInfo` at `0x18004603c`
- `rtm!RtmGetNextHopInfo` at `0x18004603c`
- `rtm!RtmGetEntityInfo` at `0x180045ee3`
- `rtm!RtmGetEntityInfo` at `0x180045ee3`
- `rtm!RtmConvertNetAddressToIpv6AddressAndLength` at `0x180045a1c`
- `rtm!RtmConvertNetAddressToIpv6AddressAndLength` at `0x180045b4a`
- `rtm!RtmConvertNetAddressToIpv6AddressAndLength` at `0x1800460a7`
- `rtm!RtmConvertNetAddressToIpv6AddressAndLength` at `0x180045a1c`
- `rtm!RtmConvertNetAddressToIpv6AddressAndLength` at `0x180045b4a`
- `rtm!RtmConvertNetAddressToIpv6AddressAndLength` at `0x1800460a7`

## string_xrefs

- `0x18004621d`: `Error %d retrieving loopback index for compartment %d\n `
- `0x180045c55`: `Deleted`
- `0x180045d50`: `AddOrRemoveIpv6Route: Failed to get first route to dest %hs with error %d`
- `0x180045dc9`: `AddOrRemoveIPv6RouteToStack: The route owned by the stack is not deleted from the stack. Route Type is %d`
- `0x180045e92`: `SetAllParameters:NsiSetDelete returns with 0x%hs dwResult %d`

## pseudocode

```c
__int64 __fastcall AddOrRemoteIPv6RouteToStack(
        PRTM_NET_ADDRESS pNetAddress,
        __int64 a2,
        int a3,
        __int64 a4,
        struct _GUID *a5,
        int a6)
{
  char v9; // al
  __int128 *v10; // r9
  __int128 *v11; // r9
  const wchar_t *v12; // r8
  __int64 v13; // r8
  __int128 *v14; // r9
  __int64 Ipv6StringFromAddress; // rax
  __int64 *v16; // rdx
  __int128 *v17; // r9
  DWORD v19; // ebx
  char v20; // cl
  const wchar_t *v21; // rdx
  __int128 *v22; // r9
  const wchar_t *v23; // rbx
  __int64 v24; // rax
  __int128 *v25; // r9
  NET_IF_COMPARTMENT_ID CompartmentIdForRoutingDomain; // eax
  __int64 v27; // r8
  DWORD FirstRouteKeyForDestination; // eax
  int v29; // ecx
  __int64 *v30; // rdx
  __int128 *v31; // r9
  __int128 *v32; // r9
  DWORD v33; // eax
  void *RtmRegistrationHandle; // rax
  void *v35; // rdx
  void *v36; // r14
  __int64 v37; // r8
  __int128 *v38; // r9
  char v39; // cl
  unsigned int v40; // r13d
  DWORD v41; // eax
  __int64 v42; // rbx
  __int64 v43; // rax
  __int128 *v44; // r9
  __int64 InterfaceBinding; // rax
  __int64 v46; // r14
  __int64 *v47; // rdx
  unsigned int LoopbackIdentifiersFromCompartmentId; // ebx
  __int128 *v49; // r9
  NET_IFINDEX v50; // r12d
  char v51; // al
  __int128 *v52; // r9
  __int128 *v53; // r9
  int v54; // edx
  struct in6_addr v55; // xmm0
  __int64 v56; // rbx
  __int64 v57; // rax
  __int128 *v58; // r9
  int v59; // ecx
  int v60; // r8d
  __int128 *v61; // r9
  int v62; // ebx
  __int64 v63; // rax
  __int128 *v64; // r9
  NET_IF_COMPARTMENT_ID v65; // eax
  const wchar_t *v66; // rdx
  __int128 *v67; // r9
  unsigned int v68; // ebx
  __int64 v69; // rax
  __int64 v70; // [rsp+20h] [rbp-A68h]
  DWORD pLength; // [rsp+40h] [rbp-A48h] BYREF
  DWORD v72[3]; // [rsp+44h] [rbp-A44h] BYREF
  struct in6_addr v73; // [rsp+50h] [rbp-A38h] BYREF
  struct in6_addr v74; // [rsp+60h] [rbp-A28h] BYREF
  struct _RTM_NEXTHOP_INFO NextHopInfo; // [rsp+70h] [rbp-A18h] BYREF
  __int128 v76; // [rsp+A8h] [rbp-9E0h] BYREF
  __m256i v77; // [rsp+B8h] [rbp-9D0h] BYREF
  struct in6_addr v78; // [rsp+E0h] [rbp-9A8h] BYREF
  struct in6_addr pAddress; // [rsp+F0h] [rbp-998h] BYREF
  struct _RTM_ENTITY_INFO EntityInfo; // [rsp+100h] [rbp-988h] BYREF
  struct in6_addr v81; // [rsp+110h] [rbp-978h] BYREF
  __int128 v82; // [rsp+120h] [rbp-968h] BYREF
  int v83; // [rsp+130h] [rbp-958h] BYREF
  struct in6_addr v84; // [rsp+134h] [rbp-954h]
  char v85; // [rsp+144h] [rbp-944h]
  NET_LUID InterfaceLuid; // [rsp+158h] [rbp-930h] BYREF
  NET_LUID v87; // [rsp+160h] [rbp-928h]
  struct in6_addr v88; // [rsp+168h] [rbp-920h]
  _BYTE v89[4]; // [rsp+180h] [rbp-908h] BYREF
  struct in6_addr v90; // [rsp+184h] [rbp-904h]
  char v91; // [rsp+194h] [rbp-8F4h]
  int v92; // [rsp+1D0h] [rbp-8B8h] BYREF
  __int128 v93; // [rsp+1D4h] [rbp-8B4h]
  __int128 v94; // [rsp+1E4h] [rbp-8A4h]
  int v95; // [rsp+1F4h] [rbp-894h]
  _BYTE v96[80]; // [rsp+200h] [rbp-888h] BYREF
  int v97; // [rsp+250h] [rbp-838h] BYREF
  _BYTE v98[2044]; // [rsp+254h] [rbp-834h] BYREF

  v72[0] = 0;
  EntityInfo = 0;
  memset(&NextHopInfo, 0, 52);
  memset_0(&v83, 0, 0x48u);
  memset(&v77, 0, 29);
  v78 = 0;
  v81 = 0;
  memset_0(v96, 0, 0x41u);
  memset_0(v89, 0, 0x48u);
  v97 = 0;
  v82 = 0;
  memset_0(v98, 0, sizeof(v98));
  v92 = 0;
  v95 = 0;
  v9 = Microsoft_Windows_RRASEnableBits;
  v93 = 0;
  v94 = 0;
  v76 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v97) = 0;
    LOWORD(v92) = 0;
    FormatRRASErrorString(&v97, L"Entered: %ws", L"AddOrRemoteIPv6Route");
    v9 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v10 = &v76;
      if ( a5 )
        LODWORD(v10) = (_DWORD)a5;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v97,
        (_DWORD)v10,
        0,
        (__int64)&v92);
      v9 = Microsoft_Windows_RRASEnableBits;
    }
  }
  if ( g_bSetRoutesToStack )
  {
    if ( a3 )
    {
      if ( !a2 )
      {
        if ( (v9 & 0x40) != 0 )
        {
          v12 = L"Error adding route, route == NULL";
          goto LABEL_30;
        }
LABEL_34:
        if ( v9 < 0 )
        {
          LOWORD(v97) = 0;
          FormatRRASErrorString(&v97, L"Leaving: %ws", L"AddOrRemoteIPv6Route");
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v97);
        }
        return 87;
      }
      if ( (*(_BYTE *)(a2 + 25) & 0x20) == 0 )
      {
        pLength = 0;
        pAddress = 0;
        if ( v9 < 0 )
        {
          v13 = *(_BYTE *)(a2 + 25) & 0x20;
          LOWORD(v97) = 0;
          LOWORD(v92) = 0;
          FormatRRASErrorString(&v97, L"INFO: Stack bit(%d) is clear. Route not added to stack", v13);
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            v14 = &v76;
            if ( a5 )
              LODWORD(v14) = (_DWORD)a5;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrmgrParamTraceInfo,
              (unsigned int)&v97,
              (_DWORD)v14,
              0,
              (__int64)&v92);
          }
        }
        RtmConvertNetAddressToIpv6AddressAndLength(pNetAddress, &pAddress, &pLength, 0x10u);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
          return 87;
        v73 = pAddress;
        LOWORD(v97) = 0;
        LOWORD(v92) = 0;
        Ipv6StringFromAddress = GetIpv6StringFromAddress(&v73, v96);
        FormatRRASErrorString(&v97, L"Not adding route with address: %hs/%d", Ipv6StringFromAddress, pLength);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
          return 87;
        v12 = (const wchar_t *)&v97;
        v16 = RasRtrmgrParamTraceInfo;
        goto LABEL_31;
      }
      if ( !*(_WORD *)(a2 + 48) )
      {
        if ( (v9 & 0x40) != 0 )
        {
          v12 = L"Error adding route, no nexthops";
LABEL_30:
          LOWORD(v92) = 0;
          v16 = RasRtrMgrParamTraceError;
LABEL_31:
          v17 = &v76;
          if ( a5 )
            LODWORD(v17) = (_DWORD)a5;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (_DWORD)v16,
            (_DWORD)v12,
            (_DWORD)v17,
            0,
            (__int64)&v92);
          v9 = Microsoft_Windows_RRASEnableBits;
          goto LABEL_34;
        }
        goto LABEL_34;
      }
    }
    v19 = RtmConvertNetAddressToIpv6AddressAndLength(pNetAddress, &v78, v72, 0x10u);
    if ( v19 )
    {
      v20 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v21 = L"Error %d while getting IPV6 address and length";
        goto LABEL_41;
      }
      goto LABEL_45;
    }
    v84 = v78;
    v85 = v72[0];
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v97) = 0;
      LOWORD(v92) = 0;
      v23 = L"Added";
      v73 = v78;
      if ( !a3 )
        v23 = L"Deleted";
      v24 = GetIpv6StringFromAddress(&v73, v96);
      FormatRRASErrorString(&v97, L"Route %hs/%d is getting %ws", v24, v72[0], v23);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v25 = &v76;
        if ( a5 )
          LODWORD(v25) = (_DWORD)a5;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v97,
          (_DWORD)v25,
          0,
          (__int64)&v92);
      }
    }
    if ( !a3 )
    {
      CompartmentIdForRoutingDomain = GetCompartmentIdForRoutingDomain(a5);
      FirstRouteKeyForDestination = GetFirstRouteKeyForDestination(
                                      (__int64)&v83,
                                      (__int64)&v77,
                                      v27,
                                      CompartmentIdForRoutingDomain);
      v19 = FirstRouteKeyForDestination;
      if ( FirstRouteKeyForDestination )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
          return v19;
        LOWORD(v97) = 0;
        LOWORD(v92) = 0;
        FormatRRASErrorString(
          &v97,
          L"AddOrRemoveIpv6Route: Failed to get first route to dest %hs with error %d",
          v96,
          FirstRouteKeyForDestination);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
          return v19;
        v30 = RasRtrMgrParamTraceError;
      }
      else
      {
        if ( v77.m256i_i32[4] <= 4 )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            LOWORD(v97) = 0;
            LOWORD(v92) = 0;
            FormatRRASErrorString(
              &v97,
              L"AddOrRemoveIPv6RouteToStack: The route owned by the stack is not deleted from the stack. Route Type is %d");
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            {
              v32 = &v76;
              if ( a5 )
                LODWORD(v32) = (_DWORD)a5;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasRtrmgrParamTraceInfo,
                (unsigned int)&v97,
                (_DWORD)v32,
                0,
                (__int64)&v92);
            }
          }
          return 0;
        }
        v33 = SetAllParameters(
                v29,
                (unsigned int)&NPI_MS_IPV6_MODULEID,
                v77.m256i_i32[4],
                (unsigned int)&v83,
                72,
                (__int64)&v77);
        v19 = v33;
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
          return v19;
        LOWORD(v97) = 0;
        LOWORD(v92) = 0;
        FormatRRASErrorString(&v97, L"SetAllParameters:NsiSetDelete returns with 0x%hs dwResult %d", v96, v33);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
          return v19;
        v30 = RasRtrmgrParamTraceInfo;
      }
      v31 = &v76;
      if ( a5 )
        LODWORD(v31) = (_DWORD)a5;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (_DWORD)v30,
        (unsigned int)&v97,
        (_DWORD)v31,
        0,
        (__int64)&v92);
      return v19;
    }
    RtmRegistrationHandle = (void *)GetRtmRegistrationHandle(a5, 0x57u, 2u);
    v35 = *(void **)(a2 + 8);
    *(_QWORD *)pAddress.u.Byte = RtmRegistrationHandle;
    v36 = RtmRegistrationHandle;
    v19 = RtmGetEntityInfo(RtmRegistrationHandle, v35, &EntityInfo);
    if ( v19 )
    {
      v20 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v21 = L"Error %d retrieving entity info from RTM";
LABEL_41:
        LOWORD(v97) = 0;
        LOWORD(v92) = 0;
        FormatRRASErrorString(&v97, v21, v19);
        v20 = Microsoft_Windows_RRASEnableBits;
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v22 = &v76;
          if ( a5 )
            LODWORD(v22) = (_DWORD)a5;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v97,
            (_DWORD)v22,
            0,
            (__int64)&v92);
          v20 = Microsoft_Windows_RRASEnableBits;
        }
      }
LABEL_45:
      if ( v20 < 0 )
      {
        LOWORD(v97) = 0;
        FormatRRASErrorString(&v97, L"Leaving: %ws", L"AddOrRemoteIPv6Route");
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v97);
      }
      return v19;
    }
    *(__int64 *)((char *)&v77.m256i_i64[2] + 4) = -1;
    v77.m256i_i32[0] = -1;
    v77.m256i_i32[7] = -1;
    *(__int64 *)((char *)v77.m256i_i64 + 4) = -1;
    v77.m256i_i32[3] = *(_DWORD *)(a2 + 28);
    v77.m256i_i32[4] = EntityInfo.EntityId.EntityProtocolId;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v37 = *(unsigned __int8 *)(a2 + 25);
      LOWORD(v97) = 0;
      LOWORD(v92) = 0;
      FormatRRASErrorString(&v97, L"AddOrRemoteIPv6RouteToStack: RTM Flags1 (%d)  ", v37);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v38 = &v76;
        if ( a5 )
          LODWORD(v38) = (_DWORD)a5;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v97,
          (_DWORD)v38,
          0,
          (__int64)&v92);
      }
    }
    v39 = *(_BYTE *)(a2 + 25);
    v77.m256i_i8[20] = v39 & 1;
    v77.m256i_i8[21] = (v39 & 2) != 0;
    v77.m256i_i8[23] = (v39 & 8) != 0;
    v77.m256i_i8[22] = (v39 & 4) != 0;
    v83 = GetCompartmentIdForRoutingDomain(a5);
    v40 = 0;
    pLength = EntityInfo.EntityId.EntityProtocolId;
    while ( 1 )
    {
      if ( v40 >= *(unsigned __int16 *)(a2 + 48) )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          LOWORD(v97) = 0;
          FormatRRASErrorString(&v97, L"Leaving: %ws", L"AddOrRemoteIPv6Route");
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            goto LABEL_157;
        }
        return 0;
      }
      v41 = RtmGetNextHopInfo(v36, *(RTM_NEXTHOP_HANDLE *)(a2 + 8LL * v40 + 56), &NextHopInfo);
      if ( v41 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
          goto LABEL_103;
        LOWORD(v97) = 0;
        LOWORD(v92) = 0;
        FormatRRASErrorString(&v97, L"Error %d retrieving next hop info from RTM", v41);
LABEL_98:
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
          goto LABEL_103;
        v47 = RasRtrMgrParamTraceError;
LABEL_100:
        v49 = &v76;
        if ( a5 )
          LODWORD(v49) = (_DWORD)a5;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (_DWORD)v47,
          (unsigned int)&v97,
          (_DWORD)v49,
          0,
          (__int64)&v92);
        goto LABEL_103;
      }
      RtmReleaseNextHopInfo(v36, &NextHopInfo);
      RtmConvertNetAddressToIpv6AddressAndLength(&NextHopInfo.NextHopAddress, &v81, v72, 0x10u);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v42 = *(_QWORD *)(a2 + 8LL * v40 + 56);
        v73 = v81;
        LOWORD(v97) = 0;
        LOWORD(v92) = 0;
        v43 = GetIpv6StringFromAddress(&v73, v96);
        FormatRRASErrorString(&v97, L"Next Hop %hs, If 0x%x, handle is 0x%x", v43, NextHopInfo.InterfaceIndex, v42);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v44 = &v76;
          if ( a5 )
            LODWORD(v44) = (_DWORD)a5;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v97,
            (_DWORD)v44,
            0,
            (__int64)&v92);
        }
      }
      RtlAcquireResourceShared(&stru_18008C500, 1u);
      InterfaceBinding = GetInterfaceBinding(NextHopInfo.InterfaceIndex, 0);
      v46 = InterfaceBinding;
      if ( !InterfaceBinding )
      {
        RtlReleaseResource(&stru_18008C500);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
          goto LABEL_103;
        LOWORD(v97) = 0;
        LOWORD(v92) = 0;
        FormatRRASErrorString(
          &v97,
          L"**Warning** tried to %hs route with interface %d which is no longer present",
          "add",
          NextHopInfo.InterfaceIndex);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
          goto LABEL_103;
        v47 = RasRtrmgrParamTraceInfo;
        goto LABEL_100;
      }
      LoopbackIdentifiersFromCompartmentId = GetLoopbackIdentifiersFromCompartmentId(
                                               *(unsigned int *)(InterfaceBinding + 56),
                                               &v82);
      if ( LoopbackIdentifiersFromCompartmentId )
      {
        RtlReleaseResource(&stru_18008C500);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
          goto LABEL_103;
        LOWORD(v97) = 0;
        LOWORD(v92) = 0;
        FormatRRASErrorString(
          &v97,
          L"Error %d retrieving loopback index for compartment %d\n ",
          LoopbackIdentifiersFromCompartmentId,
          *(unsigned int *)(v46 + 56));
        goto LABEL_98;
      }
      if ( *(_DWORD *)(v46 + 16) )
        v50 = *(_DWORD *)(v46 + 24);
      else
        v50 = DWORD2(v82);
      v51 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v97) = 0;
        LOWORD(v92) = 0;
        FormatRRASErrorString(&v97, L"Using %d as the interface index for the route", v50);
        v51 = Microsoft_Windows_RRASEnableBits;
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v52 = &v76;
          if ( a5 )
            LODWORD(v52) = (_DWORD)a5;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v97,
            (_DWORD)v52,
            0,
            (__int64)&v92);
          v51 = Microsoft_Windows_RRASEnableBits;
        }
      }
      if ( ((pLength - 10002) & 0xFFFFFFFB) != 0 || *(_DWORD *)(v46 + 48) != 2 )
      {
        if ( v50 == -1 )
        {
          if ( (v51 & 0x40) != 0 )
          {
            LOWORD(v97) = 0;
            LOWORD(v92) = 0;
            v62 = *(_DWORD *)(v46 + 24);
            v73 = v78;
            v63 = GetIpv6StringFromAddress(&v73, v96);
            LODWORD(v70) = v62;
            FormatRRASErrorString(&v97, L"**Error** Tried to %hs route to %hs over %d as DOD\n", "add", v63, v70);
            if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            {
              v64 = &v76;
              if ( a5 )
                LODWORD(v64) = (_DWORD)a5;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasRtrMgrParamTraceError,
                (unsigned int)&v97,
                (_DWORD)v64,
                0,
                (__int64)&v92);
            }
          }
          RtlReleaseResource(&stru_18008C500);
          goto LABEL_103;
        }
      }
      else if ( v51 < 0 )
      {
        LOWORD(v97) = 0;
        LOWORD(v92) = 0;
        FormatRRASErrorString(&v97, L"route context : ICB == %d\n\n", *(unsigned int *)(v46 + 100));
        v51 = Microsoft_Windows_RRASEnableBits;
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v53 = &v76;
          if ( a5 )
            LODWORD(v53) = (_DWORD)a5;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v97,
            (_DWORD)v53,
            0,
            (__int64)&v92);
          v51 = Microsoft_Windows_RRASEnableBits;
        }
      }
      v54 = *(_DWORD *)(v46 + 48);
      if ( (unsigned int)(v54 - 1) <= 1 || v54 == 7 )
      {
        if ( *(_DWORD *)(v46 + 16) )
        {
          if ( v51 < 0 )
          {
            LOWORD(v97) = 0;
            LOWORD(v92) = 0;
            v55 = *(struct in6_addr *)(v46 + 76);
            v74 = v78;
            v73 = v55;
            v56 = GetIpv6StringFromAddress(&v73, v96);
            v57 = GetIpv6StringFromAddress(&v74, v96);
            FormatRRASErrorString(&v97, L"Next Hop %hs, remote address %hs, bound p2p", v57, v56);
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            {
              v58 = &v76;
              if ( a5 )
                LODWORD(v58) = (_DWORD)a5;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasRtrmgrParamTraceInfo,
                (unsigned int)&v97,
                (_DWORD)v58,
                0,
                (__int64)&v92);
            }
          }
        }
      }
      RtlReleaseResource(&stru_18008C500);
      if ( ConvertInterfaceIndexToLuid(v50, &InterfaceLuid) < 0 && (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v97) = 0;
        LOWORD(v92) = 0;
        FormatRRASErrorString(&v97, L"Failed to convert interface index %d to LUID", v50);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v61 = &v76;
          if ( a5 )
            LODWORD(v61) = (_DWORD)a5;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v97,
            (_DWORD)v61,
            0,
            (__int64)&v92);
        }
      }
      v91 = v85;
      v90 = v84;
      if ( a6 )
      {
        v65 = GetCompartmentIdForRoutingDomain(a5);
        DeleteRTRMgrOwnedRoutesToDestFromStack(v89, 0, v65);
      }
      if ( v77.m256i_i32[4] > 4 )
      {
        v88 = v81;
        v87.Value = InterfaceLuid.Value;
        if ( *(_DWORD *)(v46 + 48) == 2 )
        {
          v77.m256i_i8[22] = 1;
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            v66 = L"interface %d is ROUTER_IF_TYPE_FULL_ROUTER type, hence IPv6 PUBLISH enabled";
LABEL_146:
            LOWORD(v97) = 0;
            LOWORD(v92) = 0;
            FormatRRASErrorString(&v97, v66, *(unsigned int *)(v46 + 24));
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            {
              v67 = &v76;
              if ( a5 )
                LODWORD(v67) = (_DWORD)a5;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasRtrmgrParamTraceInfo,
                (unsigned int)&v97,
                (_DWORD)v67,
                0,
                (__int64)&v92);
            }
          }
        }
        else if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v66 = L"interface %d is NOT ROUTER_IF_TYPE_FULL_ROUTER type, hence IPv6 PUBLISH NOT enabled";
          goto LABEL_146;
        }
        v68 = SetAllParameters(v59, (unsigned int)&NPI_MS_IPV6_MODULEID, v60, (unsigned int)&v83, 72, (__int64)&v77);
        if ( !v68 || (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
          goto LABEL_103;
        v74 = v78;
        LOWORD(v97) = 0;
        LOWORD(v92) = 0;
        v69 = GetIpv6StringFromAddress(&v74, v96);
        FormatRRASErrorString(&v97, L"AddOrRemoteIPv6Route: Failed to add route %hs with error %d", v69, v68);
        goto LABEL_98;
      }
LABEL_103:
      v36 = *(void **)pAddress.u.Byte;
      ++v40;
    }
  }
  if ( v9 < 0 )
  {
    LOWORD(v92) = 0;
    v11 = &v76;
    if ( a5 )
      LODWORD(v11) = (_DWORD)a5;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"AddOrRemoteIPv6Route: SetRoutesToStack is FALSE",
      (_DWORD)v11,
      0,
      (__int64)&v92);
    v9 = Microsoft_Windows_RRASEnableBits;
  }
  if ( v9 < 0 )
  {
    LOWORD(v97) = 0;
    FormatRRASErrorString(&v97, L"Leaving: %ws", L"AddOrRemoteIPv6Route");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
LABEL_157:
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v97);
  }
  return 0;
}

```

## disassembly

```asm
0x180045708  mov     [rsp+arg_10], rbx
0x18004570d  mov     [rsp+arg_18], rsi
0x180045712  push    rdi
0x180045713  push    r12
0x180045715  push    r13
0x180045717  push    r14
0x180045719  push    r15
0x18004571b  sub     rsp, 0A60h
0x180045722  mov     rax, cs:__security_cookie
0x180045729  xor     rax, rsp
0x18004572c  mov     [rsp+0A88h+var_38], rax
0x180045734  mov     rdi, [rsp+0A88h+arg_20]
0x18004573c  xorps   xmm0, xmm0
0x18004573f  xor     eax, eax
0x180045741  mov     esi, r8d
0x180045744  mov     r15, rdx
0x180045747  mov     dword ptr [rsp+0A88h+NextHopInfo.RemoteNextHop], eax
0x18004574e  mov     rbx, rcx
0x180045751  xor     r12d, r12d
0x180045754  xor     edx, edx; Val
0x180045756  mov     [rsp+0A88h+var_A44], r12d
0x18004575b  lea     r14d, [rax+48h]
0x18004575f  mov     r8d, r14d; Size
0x180045762  lea     rcx, [rsp+0A88h+var_958]; void *
0x18004576a  movups  xmmword ptr [rsp+0A88h+EntityInfo.RtmInstanceId], xmm0
0x180045772  movups  xmmword ptr [rsp+0A88h+NextHopInfo.NextHopAddress.AddressFamily], xmm0
0x180045777  movups  xmmword ptr [rsp+0A88h+NextHopInfo.NextHopAddress.AddrBits+0Ch], xmm0
0x18004577f  movups  xmmword ptr [rsp+0A88h+NextHopInfo.InterfaceIndex], xmm0
0x180045787  call    memset_0
0x18004578c  xorps   xmm0, xmm0
0x18004578f  lea     r8d, [r12+41h]; Size
0x180045794  xorps   xmm1, xmm1
0x180045797  lea     rcx, [rsp+0A88h+var_888]; void *
0x18004579f  movups  [rsp+0A88h+var_9D0], xmm0
0x1800457a7  xor     eax, eax
0x1800457a9  xor     edx, edx; Val
0x1800457ab  movups  [rsp+0A88h+var_9D0+0Dh], xmm0
0x1800457b3  movups  xmmword ptr [rsp+0A88h+var_9A8.u], xmm0
0x1800457bb  movups  xmmword ptr [rsp+0A88h+var_978.u], xmm1
0x1800457c3  call    memset_0
0x1800457c8  mov     r8d, r14d; Size
0x1800457cb  lea     rcx, [rsp+0A88h+var_908]; void *
0x1800457d3  xor     edx, edx; Val
0x1800457d5  call    memset_0
0x1800457da  xorps   xmm0, xmm0
0x1800457dd  mov     [rsp+0A88h+var_838], r12d
0x1800457e5  xor     edx, edx; Val
0x1800457e7  lea     rcx, [rsp+0A88h+var_834]; void *
0x1800457ef  mov     r8d, 7FCh; Size
0x1800457f5  movups  [rsp+0A88h+var_968], xmm0
0x1800457fd  call    memset_0
0x180045802  xor     eax, eax
0x180045804  mov     [rsp+0A88h+var_8B8], r12d
0x18004580c  xorps   xmm0, xmm0
0x18004580f  mov     [rsp+0A88h+var_894], eax
0x180045816  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18004581d  lea     r14, RasRtrmgrParamTraceInfo
0x180045824  lea     r13, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004582b  movups  [rsp+0A88h+var_8B4], xmm0
0x180045833  movups  [rsp+0A88h+var_8A4], xmm0
0x18004583b  movups  [rsp+0A88h+var_9E0], xmm0
0x180045843  test    al, al
0x180045845  jns     short loc_1800458BA
0x180045847  lea     r8, aAddorremoteipv; "AddOrRemoteIPv6Route"
0x18004584e  mov     word ptr [rsp+0A88h+var_838], r12w
0x180045857  lea     rdx, aEnteredWs; "Entered: %ws"
0x18004585e  mov     word ptr [rsp+0A88h+var_8B8], r12w
0x180045867  lea     rcx, [rsp+0A88h+var_838]
0x18004586f  call    FormatRRASErrorString
0x180045874  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18004587b  test    al, al
0x18004587d  jns     short loc_1800458BA
0x18004587f  test    rdi, rdi
0x180045882  lea     rax, [rsp+0A88h+var_8B8]
0x18004588a  mov     [rsp+0A88h+var_A60], rax
0x18004588f  lea     r9, [rsp+0A88h+var_9E0]
0x180045897  cmovnz  r9, rdi
0x18004589b  mov     [rsp+0A88h+var_A68], r12
0x1800458a0  lea     r8, [rsp+0A88h+var_838]
0x1800458a8  mov     rdx, r14
0x1800458ab  mov     rcx, r13
0x1800458ae  call    McTemplateU0zjzz_EventWriteTransfer
0x1800458b3  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x1800458ba  cmp     cs:g_bSetRoutesToStack, r12d
0x1800458c1  jnz     loc_18004594F
0x1800458c7  test    al, 80h
0x1800458c9  jz      short loc_18004590E
0x1800458cb  test    rdi, rdi
0x1800458ce  mov     word ptr [rsp+0A88h+var_8B8], r12w
0x1800458d7  lea     rax, [rsp+0A88h+var_8B8]
0x1800458df  mov     rdx, r14
0x1800458e2  mov     [rsp+0A88h+var_A60], rax
0x1800458e7  lea     r9, [rsp+0A88h+var_9E0]
0x1800458ef  cmovnz  r9, rdi
0x1800458f3  mov     [rsp+0A88h+var_A68], r12
0x1800458f8  lea     r8, aAddorremoteipv_0; "AddOrRemoteIPv6Route: SetRoutesToStack "...
0x1800458ff  mov     rcx, r13
0x180045902  call    McTemplateU0zjzz_EventWriteTransfer
0x180045907  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18004590e  test    al, al
0x180045910  jns     loc_180046810
0x180045916  lea     r8, aAddorremoteipv; "AddOrRemoteIPv6Route"
0x18004591d  mov     word ptr [rsp+0A88h+var_838], r12w
0x180045926  lea     rdx, aLeavingWs; "Leaving: %ws"
0x18004592d  lea     rcx, [rsp+0A88h+var_838]
0x180045935  call    FormatRRASErrorString
0x18004593a  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x180045941  jge     loc_180046810
0x180045947  mov     rcx, r13
0x18004594a  jmp     loc_1800467FC
0x18004594f  test    esi, esi
0x180045951  jz      loc_180045B34
0x180045957  test    r15, r15
0x18004595a  jz      loc_180045A97
0x180045960  test    byte ptr [r15+19h], 20h
0x180045965  jz      short loc_180045986
0x180045967  cmp     [r15+30h], r12w
0x18004596c  jnz     loc_180045B34
0x180045972  test    al, 40h
0x180045974  jz      loc_180045AE2
0x18004597a  lea     r8, aErrorAddingRou; "Error adding route, no nexthops"
0x180045981  jmp     loc_180045AA2
0x180045986  mov     [rsp+0A88h+pLength], r12d
0x18004598b  xorps   xmm0, xmm0
0x18004598e  movups  xmmword ptr [rsp+0A88h+pAddress.u], xmm0
0x180045996  test    al, al
0x180045998  jns     short loc_180045A06
0x18004599a  movzx   r8d, byte ptr [r15+19h]
0x18004599f  lea     rdx, aInfoStackBitDI; "INFO: Stack bit(%d) is clear. Route not"...
0x1800459a6  and     r8d, 20h
0x1800459aa  mov     word ptr [rsp+0A88h+var_838], r12w
0x1800459b3  lea     rcx, [rsp+0A88h+var_838]
0x1800459bb  mov     word ptr [rsp+0A88h+var_8B8], r12w
0x1800459c4  call    FormatRRASErrorString
0x1800459c9  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x1800459d0  jge     short loc_180045A06
0x1800459d2  test    rdi, rdi
0x1800459d5  lea     rax, [rsp+0A88h+var_8B8]
0x1800459dd  mov     [rsp+0A88h+var_A60], rax
0x1800459e2  lea     r9, [rsp+0A88h+var_9E0]
0x1800459ea  cmovnz  r9, rdi
0x1800459ee  mov     [rsp+0A88h+var_A68], r12
0x1800459f3  lea     r8, [rsp+0A88h+var_838]
0x1800459fb  mov     rdx, r14
0x1800459fe  mov     rcx, r13
0x180045a01  call    McTemplateU0zjzz_EventWriteTransfer
0x180045a06  mov     r9d, 10h; dwAddressSize
0x180045a0c  lea     r8, [rsp+0A88h+pLength]; pLength
0x180045a11  lea     rdx, [rsp+0A88h+pAddress]; pAddress
0x180045a19  mov     rcx, rbx; pNetAddress
0x180045a1c  call    cs:__imp_RtmConvertNetAddressToIpv6AddressAndLength
0x180045a22  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x180045a29  jge     loc_180045B2A
0x180045a2f  movaps  xmm0, xmmword ptr [rsp+0A88h+pAddress.u]
0x180045a37  lea     rdx, [rsp+0A88h+var_888]
0x180045a3f  lea     rcx, [rsp+0A88h+var_A38]
0x180045a44  movdqa  [rsp+0A88h+var_A38], xmm0
0x180045a4a  mov     word ptr [rsp+0A88h+var_838], r12w
0x180045a53  mov     word ptr [rsp+0A88h+var_8B8], r12w
0x180045a5c  call    GetIpv6StringFromAddress
0x180045a61  mov     r9d, [rsp+0A88h+pLength]
0x180045a66  lea     rdx, aNotAddingRoute; "Not adding route with address: %hs/%d"
0x180045a6d  mov     r8, rax
0x180045a70  lea     rcx, [rsp+0A88h+var_838]
0x180045a78  call    FormatRRASErrorString
0x180045a7d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x180045a84  jge     loc_180045B2A
0x180045a8a  lea     r8, [rsp+0A88h+var_838]
0x180045a92  mov     rdx, r14
0x180045a95  jmp     short loc_180045AB2
0x180045a97  test    al, 40h
0x180045a99  jz      short loc_180045AE2
0x180045a9b  lea     r8, aErrorAddingRou_0; "Error adding route, route == NULL"
0x180045aa2  mov     word ptr [rsp+0A88h+var_8B8], r12w
0x180045aab  lea     rdx, RasRtrMgrParamTraceError
0x180045ab2  test    rdi, rdi
0x180045ab5  lea     rax, [rsp+0A88h+var_8B8]
0x180045abd  mov     [rsp+0A88h+var_A60], rax
0x180045ac2  lea     r9, [rsp+0A88h+var_9E0]
0x180045aca  cmovnz  r9, rdi
0x180045ace  mov     [rsp+0A88h+var_A68], r12
0x180045ad3  mov     rcx, r13
0x180045ad6  call    McTemplateU0zjzz_EventWriteTransfer
0x180045adb  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180045ae2  test    al, al
0x180045ae4  jns     short loc_180045B2A
0x180045ae6  lea     r8, aAddorremoteipv; "AddOrRemoteIPv6Route"
0x180045aed  mov     word ptr [rsp+0A88h+var_838], r12w
0x180045af6  lea     rdx, aLeavingWs; "Leaving: %ws"
0x180045afd  lea     rcx, [rsp+0A88h+var_838]
0x180045b05  call    FormatRRASErrorString
0x180045b0a  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x180045b11  jge     short loc_180045B2A
0x180045b13  lea     r8, [rsp+0A88h+var_838]
0x180045b1b  mov     rcx, r13
0x180045b1e  lea     rdx, RasRtrmgrTraceInfo
0x180045b25  call    McTemplateU0z_EventWriteTransfer
0x180045b2a  mov     eax, 57h ; 'W'
0x180045b2f  jmp     loc_180046812
0x180045b34  mov     r9d, 10h; dwAddressSize
0x180045b3a  lea     r8, [rsp+0A88h+var_A44]; pLength
0x180045b3f  lea     rdx, [rsp+0A88h+var_9A8]; pAddress
0x180045b47  mov     rcx, rbx; pNetAddress
0x180045b4a  call    cs:__imp_RtmConvertNetAddressToIpv6AddressAndLength
0x180045b50  mov     ebx, eax
0x180045b52  test    eax, eax
0x180045b54  jz      loc_180045C2C
0x180045b5a  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180045b61  mov     sil, 40h ; '@'
0x180045b64  test    sil, cl
0x180045b67  jz      short loc_180045BDD
0x180045b69  lea     rdx, aErrorDWhileGet; "Error %d while getting IPV6 address and"...
0x180045b70  mov     r8d, ebx
0x180045b73  mov     word ptr [rsp+0A88h+var_838], r12w
0x180045b7c  lea     rcx, [rsp+0A88h+var_838]
0x180045b84  mov     word ptr [rsp+0A88h+var_8B8], r12w
0x180045b8d  call    FormatRRASErrorString
0x180045b92  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180045b99  test    sil, cl
0x180045b9c  jz      short loc_180045BDD
0x180045b9e  test    rdi, rdi
0x180045ba1  lea     rax, [rsp+0A88h+var_8B8]
0x180045ba9  mov     [rsp+0A88h+var_A60], rax
0x180045bae  lea     r9, [rsp+0A88h+var_9E0]
0x180045bb6  cmovnz  r9, rdi
0x180045bba  mov     [rsp+0A88h+var_A68], r12
0x180045bbf  lea     r8, [rsp+0A88h+var_838]
0x180045bc7  mov     rcx, r13
0x180045bca  lea     rdx, RasRtrMgrParamTraceError
0x180045bd1  call    McTemplateU0zjzz_EventWriteTransfer
0x180045bd6  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180045bdd  test    cl, cl
0x180045bdf  jns     short loc_180045C25
0x180045be1  lea     r8, aAddorremoteipv; "AddOrRemoteIPv6Route"
0x180045be8  mov     word ptr [rsp+0A88h+var_838], r12w
0x180045bf1  lea     rdx, aLeavingWs; "Leaving: %ws"
0x180045bf8  lea     rcx, [rsp+0A88h+var_838]
0x180045c00  call    FormatRRASErrorString
0x180045c05  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x180045c0c  jge     short loc_180045C25
0x180045c0e  lea     r8, [rsp+0A88h+var_838]
0x180045c16  mov     rcx, r13
0x180045c19  lea     rdx, RasRtrmgrTraceInfo
0x180045c20  call    McTemplateU0z_EventWriteTransfer
0x180045c25  mov     eax, ebx
0x180045c27  jmp     loc_180046812
0x180045c2c  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x180045c33  movaps  xmm0, xmmword ptr [rsp+0A88h+var_9A8.u]
0x180045c3b  mov     al, byte ptr [rsp+0A88h+var_A44]
0x180045c3f  movdqu  [rsp+0A88h+var_954], xmm0
0x180045c48  mov     [rsp+0A88h+var_944], al
0x180045c4f  jge     loc_180045CF1
0x180045c55  lea     rax, aDeleted; "Deleted"
0x180045c5c  mov     word ptr [rsp+0A88h+var_838], r12w
0x180045c65  test    esi, esi
0x180045c67  mov     word ptr [rsp+0A88h+var_8B8], r12w
0x180045c70  lea     rbx, aAdded; "Added"
0x180045c77  movdqa  [rsp+0A88h+var_A38], xmm0
0x180045c7d  lea     rdx, [rsp+0A88h+var_888]
0x180045c85  cmovz   rbx, rax
0x180045c89  lea     rcx, [rsp+0A88h+var_A38]
0x180045c8e  call    GetIpv6StringFromAddress
0x180045c93  mov     r9d, [rsp+0A88h+var_A44]
0x180045c98  lea     rdx, aRouteHsDIsGett; "Route %hs/%d is getting %ws"
0x180045c9f  mov     r8, rax
0x180045ca2  mov     [rsp+0A88h+var_A68], rbx
0x180045ca7  lea     rcx, [rsp+0A88h+var_838]
0x180045caf  call    FormatRRASErrorString
0x180045cb4  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x180045cbb  jge     short loc_180045CF1
0x180045cbd  test    rdi, rdi
0x180045cc0  lea     rax, [rsp+0A88h+var_8B8]
0x180045cc8  mov     [rsp+0A88h+var_A60], rax
0x180045ccd  lea     r9, [rsp+0A88h+var_9E0]
0x180045cd5  cmovnz  r9, rdi
0x180045cd9  mov     [rsp+0A88h+var_A68], r12
0x180045cde  lea     r8, [rsp+0A88h+var_838]
0x180045ce6  mov     rdx, r14
0x180045ce9  mov     rcx, r13
0x180045cec  call    McTemplateU0zjzz_EventWriteTransfer
0x180045cf1  mov     rcx, rdi; struct _GUID *
0x180045cf4  test    esi, esi
0x180045cf6  jnz     loc_180045EBB
0x180045cfc  call    GetCompartmentIdForRoutingDomain
0x180045d01  mov     r9d, eax
0x180045d04  lea     rdx, [rsp+0A88h+var_9D0]
0x180045d0c  lea     rcx, [rsp+0A88h+var_958]
0x180045d14  call    GetFirstRouteKeyForDestination
0x180045d19  mov     ebx, eax
0x180045d1b  test    eax, eax
0x180045d1d  jz      loc_180045DAE
0x180045d23  mov     sil, 40h ; '@'
0x180045d26  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x180045d2d  jz      loc_180045C25
0x180045d33  mov     r9d, eax
0x180045d36  mov     word ptr [rsp+0A88h+var_838], r12w
0x180045d3f  lea     r8, [rsp+0A88h+var_888]
0x180045d47  mov     word ptr [rsp+0A88h+var_8B8], r12w
0x180045d50  lea     rdx, aAddorremoveipv; "AddOrRemoveIpv6Route: Failed to get fir"...
0x180045d57  lea     rcx, [rsp+0A88h+var_838]
  ... truncated ...
```

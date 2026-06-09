# ProcessChanges

- ea: `0x18004b844`
- end: `0x18004c947`
- name: `ProcessChanges`
- size: `4355`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004d830`

## callees

- `0x1800010a0`
- `0x18000ac60`
- `0x180011790`
- `0x18003e45c`
- `0x180046848`
- `0x18004b4f0`
- `0x18004b844`
- `0x180051ec8`
- `0x180051ef8`
- `0x180057b34`
- `0x180057c14`
- `0x180057c48`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringA` at `0x18004c7ec`
- `ntdll!RtlIpv6AddressToStringA` at `0x18004c7ec`
- `KERNEL32!HeapFree` at `0x18004bb99`
- `KERNEL32!HeapFree` at `0x18004bc5a`
- `KERNEL32!HeapFree` at `0x18004c18d`
- `KERNEL32!HeapFree` at `0x18004c8a5`
- `KERNEL32!HeapFree` at `0x18004c8bc`
- `KERNEL32!HeapFree` at `0x18004c8ce`
- `KERNEL32!HeapFree` at `0x18004bb99`
- `KERNEL32!HeapFree` at `0x18004bc5a`
- `KERNEL32!HeapFree` at `0x18004c18d`
- `KERNEL32!HeapFree` at `0x18004c8a5`
- `KERNEL32!HeapFree` at `0x18004c8bc`
- `KERNEL32!HeapFree` at `0x18004c8ce`
- `KERNEL32!HeapAlloc` at `0x18004ba85`
- `KERNEL32!HeapAlloc` at `0x18004bbbf`
- `KERNEL32!HeapAlloc` at `0x18004c19f`
- `KERNEL32!HeapAlloc` at `0x18004ba85`
- `KERNEL32!HeapAlloc` at `0x18004bbbf`
- `KERNEL32!HeapAlloc` at `0x18004c19f`
- `rtm!RtmReleaseRoutes` at `0x18004c2d7`
- `rtm!RtmReleaseRoutes` at `0x18004c2d7`
- `rtm!RtmDeleteEnumHandle` at `0x18004c36a`
- `rtm!RtmDeleteEnumHandle` at `0x18004c36a`
- `rtm!RtmReleaseRouteInfo` at `0x18004c2c6`
- `rtm!RtmReleaseRouteInfo` at `0x18004c2c6`
- `rtm!RtmGetRouteInfo` at `0x18004c25c`
- `rtm!RtmGetRouteInfo` at `0x18004c25c`
- `rtm!RtmGetOpaqueInformationPointer` at `0x18004c460`
- `rtm!RtmGetOpaqueInformationPointer` at `0x18004c460`
- `rtm!RtmGetEnumBestRoutes` at `0x18004c210`
- `rtm!RtmGetEnumBestRoutes` at `0x18004c210`
- `rtm!RtmCreateBestRouteEnum` at `0x18004c14f`
- `rtm!RtmCreateBestRouteEnum` at `0x18004c14f`
- `rtm!RtmMarkDestForChangeNotification` at `0x18004bec7`
- `rtm!RtmMarkDestForChangeNotification` at `0x18004bec7`
- `rtm!RtmReleaseChangedDests` at `0x18004bea3`
- `rtm!RtmReleaseChangedDests` at `0x18004c388`
- `rtm!RtmReleaseChangedDests` at `0x18004c887`
- `rtm!RtmReleaseChangedDests` at `0x18004bea3`
- `rtm!RtmReleaseChangedDests` at `0x18004c388`
- `rtm!RtmReleaseChangedDests` at `0x18004c887`
- `rtm!RtmIsMarkedForChangeNotification` at `0x18004be2a`
- `rtm!RtmIsMarkedForChangeNotification` at `0x18004be2a`
- `rtm!RtmGetChangedDests` at `0x18004bd3c`
- `rtm!RtmGetChangedDests` at `0x18004bd3c`
- `rtm!RtmConvertNetAddressToIpv6AddressAndLength` at `0x18004c0e6`
- `rtm!RtmConvertNetAddressToIpv6AddressAndLength` at `0x18004c72d`
- `rtm!RtmConvertNetAddressToIpv6AddressAndLength` at `0x18004c0e6`
- `rtm!RtmConvertNetAddressToIpv6AddressAndLength` at `0x18004c72d`

## string_xrefs

- `0x18004ba0d`: `ProcessChanges : Arithmatic Overflow during memory allocation for route info`
- `0x18004bb7a`: `ProcessChanges : Arithmatic Overflow during memory allocation for dest. info`
- `0x18004be69`: `ProcessChanges : Route 0/0 is already marked`
- `0x18004c05d`: `Error %d while Calling DeleteRTRMgrOwnedRoutesToDestFromStack`
- `0x18004c34b`: `Error %d while Calling RtmCreateBestRouteEnum`
- `0x18004c3e9`: `Route delete notification for %d.%d.%d.%d/%d`
- `0x18004c6a7`: `Error %d while Calling DeleteRTRMgrOwnedRoutesToDestFromStack for destination %d.%d.%d.%d/%d`
- `0x18004c814`: `Error %d while Calling DeleteRTRMgrOwnedRoutesToDestFromStack for destination %hs/%d`

## pseudocode

```c
__int64 __fastcall ProcessChanges(void *a1, int a2, struct _GUID *a3)
{
  __int128 *v5; // r9
  unsigned int v6; // esi
  char v7; // r9
  __int128 *v8; // r9
  PRTM_ROUTE_INFO v10; // r14
  char v11; // al
  __int128 *v12; // r9
  __int128 *v13; // r9
  struct _RTM_DEST_INFO *v14; // rsi
  __int128 *v15; // r9
  void *v16; // r15
  unsigned int v17; // ebx
  int v18; // r14d
  RTM_ENTITY_HANDLE v19; // r13
  unsigned int NumBits; // r10d
  __int128 *v21; // r9
  DWORD v22; // eax
  __int64 v23; // r8
  const wchar_t *v24; // r8
  __int128 *v25; // r9
  DWORD v26; // eax
  const wchar_t *v27; // rdx
  __int128 *v28; // r9
  int v29; // eax
  __int128 *v30; // r9
  NET_IF_COMPARTMENT_ID CompartmentIdForRoutingDomain; // eax
  int v32; // edx
  _BYTE *v33; // rcx
  unsigned int v34; // eax
  const wchar_t *v35; // rdx
  __int64 v36; // r8
  __int128 *v37; // r9
  unsigned int v38; // eax
  UINT v39; // r14d
  void *v40; // r15
  UINT v41; // r14d
  unsigned int EnumBestRoutes; // eax
  UINT v43; // eax
  RTM_ENTITY_HANDLE v44; // r12
  struct _RTM_NET_ADDRESS *p_DestAddress; // r13
  PRTM_ROUTE_INFO v46; // rsi
  RTM_ROUTE_HANDLE *v47; // rbx
  __int64 v48; // rcx
  __int128 *v49; // r9
  RTM_DEST_HANDLE DestHandle; // rdx
  DWORD OpaqueInformationPointer; // eax
  __int64 *v52; // rdx
  const wchar_t *v53; // r8
  __int128 *v54; // r9
  __int128 *v55; // r9
  int v56; // r15d
  unsigned int v57; // r14d
  NET_IF_COMPARTMENT_ID v58; // eax
  unsigned int v59; // eax
  __int128 *v60; // r9
  DWORD v61; // eax
  NET_IF_COMPARTMENT_ID v62; // eax
  unsigned int v63; // r14d
  __int128 *v64; // r9
  int v65[2]; // [rsp+20h] [rbp-A08h]
  struct _GUID *v66; // [rsp+28h] [rbp-A00h]
  __int64 v67; // [rsp+30h] [rbp-9F8h]
  __int64 v68; // [rsp+38h] [rbp-9F0h]
  __int64 v69; // [rsp+40h] [rbp-9E8h]
  __int64 v70; // [rsp+48h] [rbp-9E0h]
  SIZE_T dwBytes; // [rsp+50h] [rbp-9D8h] BYREF
  int v72; // [rsp+58h] [rbp-9D0h]
  DWORD pLength; // [rsp+5Ch] [rbp-9CCh] BYREF
  SIZE_T v74; // [rsp+60h] [rbp-9C8h] BYREF
  UINT MaxHandlesInEnum; // [rsp+68h] [rbp-9C0h] BYREF
  RTM_NOTIFY_HANDLE NotifyHandle; // [rsp+70h] [rbp-9B8h]
  WINBOOL DestMarked; // [rsp+78h] [rbp-9B0h] BYREF
  RTM_ENUM_HANDLE EnumHandle; // [rsp+80h] [rbp-9A8h] BYREF
  LPVOID v79; // [rsp+88h] [rbp-9A0h]
  RTM_ENTITY_HANDLE RtmRegHandle; // [rsp+90h] [rbp-998h]
  RTM_NOTIFY_HANDLE RtmNotificationHandle; // [rsp+98h] [rbp-990h]
  RTM_ENTITY_HANDLE RtmRegistrationHandle; // [rsp+A0h] [rbp-988h]
  PRTM_ROUTE_INFO RouteInfo; // [rsp+A8h] [rbp-980h]
  struct _RTM_DEST_INFO *v84; // [rsp+B0h] [rbp-978h]
  __int128 v85; // [rsp+B8h] [rbp-970h] BYREF
  struct in6_addr pAddress; // [rsp+C8h] [rbp-960h] BYREF
  _OWORD v87[3]; // [rsp+D8h] [rbp-950h] BYREF
  _BYTE v88[4]; // [rsp+110h] [rbp-918h] BYREF
  struct in6_addr v89; // [rsp+114h] [rbp-914h]
  char v90; // [rsp+124h] [rbp-904h]
  int v91; // [rsp+160h] [rbp-8C8h] BYREF
  __int128 v92; // [rsp+164h] [rbp-8C4h]
  __int128 v93; // [rsp+174h] [rbp-8B4h]
  int v94; // [rsp+184h] [rbp-8A4h]
  CHAR S[80]; // [rsp+190h] [rbp-898h] BYREF
  int v96; // [rsp+1E0h] [rbp-848h] BYREF
  char v97[2044]; // [rsp+1E4h] [rbp-844h] BYREF

  v72 = a2;
  NotifyHandle = a1;
  DestMarked = 0;
  dwBytes = 0;
  LODWORD(v74) = 0;
  EnumHandle = 0;
  MaxHandlesInEnum = 0;
  memset(v87, 0, sizeof(v87));
  memset_0(v88, 0, 0x48u);
  pLength = 0;
  pAddress = 0;
  memset_0(S, 0, 0x41u);
  v96 = 0;
  memset_0(v97, 0, sizeof(v97));
  v91 = 0;
  v94 = 0;
  v92 = 0;
  v93 = 0;
  v85 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v96) = 0;
    LOWORD(v91) = 0;
    FormatRRASErrorString(&v96, L"Entered: %ws", L"ProcessChanges");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v5 = &v85;
      if ( a3 )
        LODWORD(v5) = (_DWORD)a3;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v96,
        (_DWORD)v5,
        0,
        (__int64)&v91);
    }
  }
  v6 = RTMSIZEOFROUTEINFO(g_rtmProfile.MaxNextHopsInRoute, &dwBytes);
  if ( v6 )
  {
    if ( (v7 & 0x40) != 0 )
    {
      LOWORD(v91) = 0;
      v8 = &v85;
      if ( a3 )
        LODWORD(v8) = (_DWORD)a3;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrMgrParamTraceError,
        (unsigned int)L"ProcessChanges : Arithmatic Overflow during memory allocation for route info",
        (_DWORD)v8,
        0,
        (__int64)&v91);
      v7 = Microsoft_Windows_RRASEnableBits;
    }
    if ( v7 >= 0 )
      return v6;
    goto LABEL_12;
  }
  RouteInfo = (PRTM_ROUTE_INFO)HeapAlloc(IPRouterHeap, 0, (unsigned int)dwBytes);
  v10 = RouteInfo;
  if ( !RouteInfo )
  {
    v11 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v96) = 0;
      LOWORD(v91) = 0;
      FormatRRASErrorString(&v96, L"ProcessChanges : error allocating %d bytes for route info", (unsigned int)dwBytes);
      v11 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v12 = &v85;
        if ( a3 )
          LODWORD(v12) = (_DWORD)a3;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v96,
          (_DWORD)v12,
          0,
          (__int64)&v91);
        v11 = Microsoft_Windows_RRASEnableBits;
      }
    }
    if ( v11 >= 0 )
      return 8;
    goto LABEL_37;
  }
  v6 = RTMSIZEOFDESTINFO(g_rtmProfile.NumberOfViews, &v74);
  if ( v6 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v91) = 0;
      v13 = &v85;
      if ( a3 )
        LODWORD(v13) = (_DWORD)a3;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrMgrParamTraceError,
        (unsigned int)L"ProcessChanges : Arithmatic Overflow during memory allocation for dest. info",
        (_DWORD)v13,
        0,
        (__int64)&v91);
    }
    HeapFree(IPRouterHeap, 0, v10);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return v6;
LABEL_12:
    LOWORD(v96) = 0;
    FormatRRASErrorString(&v96, L"Leaving: %ws", L"ProcessChanges");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v96);
    return v6;
  }
  v84 = (struct _RTM_DEST_INFO *)HeapAlloc(IPRouterHeap, 0, (unsigned int)v74);
  v14 = v84;
  if ( !v84 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v96) = 0;
      LOWORD(v91) = 0;
      FormatRRASErrorString(&v96, L"ProcessChanges : error allocating %d bytes for dest. info", (unsigned int)v74);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v15 = &v85;
        if ( a3 )
          LODWORD(v15) = (_DWORD)a3;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v96,
          (_DWORD)v15,
          0,
          (__int64)&v91);
      }
    }
    HeapFree(IPRouterHeap, 0, v10);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return 8;
LABEL_37:
    LOWORD(v96) = 0;
    FormatRRASErrorString(&v96, L"Leaving: %ws", L"ProcessChanges");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v96);
    return 8;
  }
  v79 = 0;
  dwBytes = 0x100000000LL;
  v16 = 0;
  v17 = a2 != 0 ? 33 : 87;
  v18 = 0;
  RtmRegistrationHandle = (RTM_ENTITY_HANDLE)GetRtmRegistrationHandle(a3, v17, 2u);
  v19 = RtmRegistrationHandle;
  RtmRegHandle = (RTM_ENTITY_HANDLE)GetRtmRegistrationHandle(a3, v17, 3u);
  RtmNotificationHandle = (RTM_NOTIFY_HANDLE)GetRtmNotificationHandle(a3, v17);
  while ( 1 )
  {
    RtmGetChangedDests(v19, NotifyHandle, (PUINT)&dwBytes + 1, v14);
    if ( !HIDWORD(dwBytes) )
      break;
    if ( v14->DestAddress.NumBits )
      goto LABEL_65;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v96) = 0;
      LOWORD(v91) = 0;
      NumBits = v14->DestAddress.NumBits;
      LODWORD(v70) = 0;
      LODWORD(v69) = 0;
      LODWORD(v68) = NumBits >> 8;
      LODWORD(v67) = (unsigned __int8)NumBits;
      LODWORD(v66) = v14->DestAddress.AddrBits[3];
      v65[0] = v14->DestAddress.AddrBits[2];
      FormatRRASErrorString(
        &v96,
        L"Checking dest %d.%d.%d.%d/%d is marked",
        v14->DestAddress.AddrBits[0],
        v14->DestAddress.AddrBits[1],
        *(_QWORD *)v65,
        v66,
        v67,
        v68,
        v69,
        v70);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v21 = &v85;
        if ( a3 )
          LODWORD(v21) = (_DWORD)a3;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v96,
          (_DWORD)v21,
          0,
          (__int64)&v91);
      }
    }
    v22 = RtmIsMarkedForChangeNotification(RtmRegHandle, RtmNotificationHandle, v14->DestHandle, &DestMarked);
    v23 = v22;
    if ( v22 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        goto LABEL_65;
      v27 = L"ProcessChanges: error %d checking if default route marked";
      goto LABEL_61;
    }
    if ( DestMarked )
    {
      LOBYTE(v74) = Microsoft_Windows_RRASEnableBits & 0x40;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        goto LABEL_55;
      LOWORD(v91) = 0;
      v24 = L"ProcessChanges : Route 0/0 is already marked";
      goto LABEL_52;
    }
    v26 = RtmMarkDestForChangeNotification(RtmRegHandle, RtmNotificationHandle, v14->DestHandle, 1);
    if ( v26 && (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v23 = v26;
      v27 = L"ProcessChanges: error %d marking default route";
LABEL_61:
      LOWORD(v96) = 0;
      LOWORD(v91) = 0;
      FormatRRASErrorString(&v96, v27, v23);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v28 = &v85;
        if ( a3 )
          LODWORD(v28) = (_DWORD)a3;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v96,
          (_DWORD)v28,
          0,
          (__int64)&v91);
      }
    }
LABEL_65:
    if ( (v14->BelongsToViews & 1) != 0 )
    {
      if ( v72 )
      {
        v29 = *(_DWORD *)v14->DestAddress.AddrBits;
        BYTE8(v87[0]) = v14->DestAddress.NumBits;
        DWORD1(v87[0]) = v29;
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          LOWORD(v96) = 0;
          LOWORD(v91) = 0;
          LODWORD(v67) = v14->DestAddress.NumBits;
          LODWORD(v66) = v14->DestAddress.AddrBits[3];
          v65[0] = v14->DestAddress.AddrBits[2];
          FormatRRASErrorString(
            &v96,
            L"Route change notification for destination: %d.%d.%d.%d/%d",
            v14->DestAddress.AddrBits[0],
            v14->DestAddress.AddrBits[1],
            *(_QWORD *)v65,
            v66,
            v67);
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            v30 = &v85;
            if ( a3 )
              LODWORD(v30) = (_DWORD)a3;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrmgrParamTraceInfo,
              (unsigned int)&v96,
              (_DWORD)v30,
              0,
              (__int64)&v91);
          }
        }
        CompartmentIdForRoutingDomain = GetCompartmentIdForRoutingDomain(a3);
        v32 = 1;
        v33 = v87;
LABEL_73:
        v34 = DeleteRTRMgrOwnedRoutesToDestFromStack(v33, v32, CompartmentIdForRoutingDomain);
        if ( v34 )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            v35 = L"Error %d while Calling DeleteRTRMgrOwnedRoutesToDestFromStack";
            goto LABEL_76;
          }
LABEL_109:
          if ( EnumHandle )
          {
            RtmDeleteEnumHandle(v19, EnumHandle);
            EnumHandle = 0;
          }
LABEL_111:
          RtmReleaseChangedDests(v19, NotifyHandle, HIDWORD(dwBytes), v14);
          v16 = v79;
          goto LABEL_112;
        }
        v38 = RtmCreateBestRouteEnum(v19, v14->DestHandle, 1, &EnumHandle);
        v36 = v38;
        if ( v38 || !EnumHandle )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
            goto LABEL_109;
          v35 = L"Error %d while Calling RtmCreateBestRouteEnum";
        }
        else
        {
          v39 = 8 * g_rtmProfile.MaxHandlesInEnum;
          if ( v16 )
            HeapFree(IPRouterHeap, 0, v16);
          v79 = HeapAlloc(IPRouterHeap, 0, v39);
          v40 = v79;
          if ( !v79 )
          {
            if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
              goto LABEL_109;
            LOWORD(v96) = 0;
            LOWORD(v91) = 0;
            FormatRRASErrorString(&v96, L"ProcessChanges : error allocating %d bytes for route handles", v39);
LABEL_78:
            if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            {
              v37 = &v85;
              if ( a3 )
                LODWORD(v37) = (_DWORD)a3;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasRtrMgrParamTraceError,
                (unsigned int)&v96,
                (_DWORD)v37,
                0,
                (__int64)&v91);
            }
            goto LABEL_109;
          }
          v41 = 0;
          while ( 1 )
          {
            MaxHandlesInEnum = g_rtmProfile.MaxHandlesInEnum;
            EnumBestRoutes = RtmGetEnumBestRoutes(v19, EnumHandle, &MaxHandlesInEnum, v40);
            v36 = EnumBestRoutes;
            if ( EnumBestRoutes )
              break;
            v43 = MaxHandlesInEnum;
            if ( MaxHandlesInEnum )
            {
              v44 = RtmRegistrationHandle;
              p_DestAddress = &v14->DestAddress;
              v46 = RouteInfo;
              v47 = (RTM_ROUTE_HANDLE *)v79;
              do
              {
                if ( !RtmGetRouteInfo(v44, v47[v41], v46, 0) )
                {
                  if ( (unsigned int)IsRouteOverDDUnboundInterface(v48, v46, (unsigned int)v72, v44, a3) )
                  {
                    ++v46->PrefInfo.Preference;
                    AddDoDRoute(p_DestAddress);
                  }
                  ChangeRouteWithForwarder(p_DestAddress, v72, a3, 0);
                  RtmReleaseRouteInfo(v44, v46);
                }
                RtmReleaseRoutes(v44, 1u, &v47[v41]);
                v43 = MaxHandlesInEnum;
                ++v41;
              }
              while ( v41 < MaxHandlesInEnum );
              v14 = v84;
              v19 = RtmRegistrationHandle;
              v40 = v79;
              v41 = 0;
            }
            if ( v43 < g_rtmProfile.MaxHandlesInEnum )
              goto LABEL_109;
            memset_0(v40, 0, 8LL * v43);
          }
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
            goto LABEL_109;
          v35 = L"Error %d while Calling RtmGetEnumBestRoutes";
        }
      }
      else
      {
        v34 = RtmConvertNetAddressToIpv6AddressAndLength(&v14->DestAddress, &pAddress, &pLength, 0x10u);
        if ( !v34 )
        {
          v90 = pLength;
          v89 = pAddress;
          CompartmentIdForRoutingDomain = GetCompartmentIdForRoutingDomain(a3);
          v32 = 0;
          v33 = v88;
          goto LABEL_73;
        }
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
          goto LABEL_109;
        v35 = L"Error %d while getting IPV6 address and length";
LABEL_76:
        v36 = v34;
      }
      LOWORD(v91) = 0;
      LOWORD(v96) = 0;
      FormatRRASErrorString(&v96, v35, v36);
      goto LABEL_78;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v96) = 0;
      LOWORD(v91) = 0;
      LODWORD(v67) = v14->DestAddress.NumBits;
      LODWORD(v66) = v14->DestAddress.AddrBits[3];
      v65[0] = v14->DestAddress.AddrBits[2];
      FormatRRASErrorString(
        &v96,
        L"Route delete notification for %d.%d.%d.%d/%d",
        v14->DestAddress.AddrBits[0],
        v14->DestAddress.AddrBits[1],
        *(_QWORD *)v65,
        v66,
        v67);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v49 = &v85;
        if ( a3 )
          LODWORD(v49) = (_DWORD)a3;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v96,
          (_DWORD)v49,
          0,
          (__int64)&v91);
      }
    }
    if ( v14->DestAddress.NumBits != 32 )
    {
      LOBYTE(v74) = Microsoft_Windows_RRASEnableBits & 0x80;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v91) = 0;
        v53 = L"Deleting a subnet route";
LABEL_137:
        v55 = &v85;
        if ( a3 )
          LODWORD(v55) = (_DWORD)a3;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (_DWORD)v53,
          (_DWORD)v55,
          0,
          (__int64)&v91);
      }
LABEL_140:
      v18 = 1;
      LODWORD(dwBytes) = 1;
      goto LABEL_141;
    }
    DestHandle = v14->DestHandle;
    v74 = 0;
    OpaqueInformationPointer = RtmGetOpaqueInformationPointer(RtmRegHandle, DestHandle, (PVOID *)&v74);
    if ( OpaqueInformationPointer )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        goto LABEL_133;
      LOWORD(v96) = 0;
      LOWORD(v91) = 0;
      FormatRRASErrorString(&v96, L"AddRtmRoute : error %d retrieving opaque info", OpaqueInformationPointer);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        goto LABEL_133;
      v52 = RasRtrMgrParamTraceError;
      goto LABEL_130;
    }
    if ( *(_DWORD *)v74 != -65535 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v96) = 0;
        LOWORD(v91) = 0;
        FormatRRASErrorString(&v96, L"Host route with Stack bit 0x%x", *(unsigned int *)v74);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v53 = (const wchar_t *)&v96;
          goto LABEL_137;
        }
      }
      goto LABEL_140;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v96) = 0;
      LOWORD(v91) = 0;
      FormatRRASErrorString(&v96, L"Stack bit not set on host route, Skipping deleting 0x%x", *(unsigned int *)v74);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v52 = RasRtrmgrParamTraceInfo;
LABEL_130:
        v54 = &v85;
        if ( a3 )
          LODWORD(v54) = (_DWORD)a3;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (_DWORD)v52,
          (unsigned int)&v96,
          (_DWORD)v54,
          0,
          (__int64)&v91);
      }
    }
LABEL_133:
    LODWORD(dwBytes) = v18;
    if ( !v18 )
      goto LABEL_111;
LABEL_141:
    if ( v72 )
    {
      v56 = v14->DestAddress.NumBits;
      v57 = *(_DWORD *)v14->DestAddress.AddrBits;
      BYTE8(v87[0]) = v14->DestAddress.NumBits;
      DWORD1(v87[0]) = v57;
      v58 = GetCompartmentIdForRoutingDomain(a3);
      v59 = DeleteRTRMgrOwnedRoutesToDestFromStack(v87, 1, v58);
      if ( v59 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          LODWORD(v68) = v56;
          LOWORD(v96) = 0;
          LOWORD(v91) = 0;
          LODWORD(v67) = HIBYTE(v57);
          LODWORD(v66) = BYTE2(v57);
          v65[0] = BYTE1(v57);
          FormatRRASErrorString(
            &v96,
            L"Error %d while Calling DeleteRTRMgrOwnedRoutesToDestFromStack for destination %d.%d.%d.%d/%d",
            v59,
            (unsigned __int8)v57,
            *(_QWORD *)v65,
            v66,
            v67,
            v68);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            v60 = &v85;
            if ( a3 )
              LODWORD(v60) = (_DWORD)a3;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrMgrParamTraceError,
              (unsigned int)&v96,
              (_DWORD)v60,
              0,
              (__int64)&v91);
          }
        }
      }
      goto LABEL_111;
    }
    v61 = RtmConvertNetAddressToIpv6AddressAndLength(&v14->DestAddress, &pAddress, &pLength, 0x10u);
    if ( v61 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        goto LABEL_55;
      LOWORD(v96) = 0;
      LOWORD(v91) = 0;
      FormatRRASErrorString(&v96, L"Error %d while getting IPV6 address and length", v61);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        goto LABEL_55;
      v24 = (const wchar_t *)&v96;
LABEL_52:
      v25 = &v85;
      if ( a3 )
        LODWORD(v25) = (_DWORD)a3;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrMgrParamTraceError,
        (_DWORD)v24,
        (_DWORD)v25,
        0,
        (__int64)&v91);
LABEL_55:
      RtmReleaseChangedDests(v19, NotifyHandle, HIDWORD(dwBytes), v14);
    }
    else
    {
      v90 = pLength;
      v89 = pAddress;
      v62 = GetCompartmentIdForRoutingDomain(a3);
      v63 = DeleteRTRMgrOwnedRoutesToDestFromStack(v88, 0, v62);
      if ( !v63 )
        goto LABEL_111;
      RtlIpv6AddressToStringA(&pAddress, S);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v65[0] = pLength;
        LOWORD(v96) = 0;
        LOWORD(v91) = 0;
        FormatRRASErrorString(
          &v96,
          L"Error %d while Calling DeleteRTRMgrOwnedRoutesToDestFromStack for destination %hs/%d",
          v63,
          S,
          *(_QWORD *)v65);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v64 = &v85;
          if ( a3 )
            LODWORD(v64) = (_DWORD)a3;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v96,
            (_DWORD)v64,
            0,
            (__int64)&v91);
        }
      }
      RtmReleaseChangedDests(v19, NotifyHandle, HIDWORD(dwBytes), v14);
LABEL_112:
      v18 = dwBytes;
    }
  }
  if ( v16 )
    HeapFree(IPRouterHeap, 0, v16);
  HeapFree(IPRouterHeap, 0, RouteInfo);
  HeapFree(IPRouterHeap, 0, v14);
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v96) = 0;
    FormatRRASErrorString(&v96, L"Leaving: %ws", L"ProcessChanges");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v96);
  }
  return 0;
}

```

## disassembly

```asm
0x18004b844  push    rbx
0x18004b846  push    rsi
0x18004b847  push    rdi
0x18004b848  push    r12
0x18004b84a  push    r13
0x18004b84c  push    r14
0x18004b84e  push    r15
0x18004b850  sub     rsp, 9F0h
0x18004b857  mov     rax, cs:__security_cookie
0x18004b85e  xor     rax, rsp
0x18004b861  mov     [rsp+0A28h+var_48], rax
0x18004b869  xor     r13d, r13d
0x18004b86c  mov     [rsp+0A28h+var_9D0], edx
0x18004b870  xorps   xmm0, xmm0
0x18004b873  mov     [rsp+0A28h+NotifyHandle], rcx
0x18004b878  mov     rdi, r8
0x18004b87b  mov     dword ptr [rsp+0A28h+dwBytes+4], r13d
0x18004b880  mov     ebx, edx
0x18004b882  mov     [rsp+0A28h+DestMarked], r13d
0x18004b887  lea     r8d, [r13+48h]; Size
0x18004b88b  mov     dword ptr [rsp+0A28h+dwBytes], r13d
0x18004b890  xor     edx, edx; Val
0x18004b892  mov     dword ptr [rsp+0A28h+var_9C8], r13d
0x18004b897  lea     rcx, [rsp+0A28h+var_918]; void *
0x18004b89f  mov     [rsp+0A28h+EnumHandle], r13
0x18004b8a7  mov     [rsp+0A28h+var_9C0], r13d
0x18004b8ac  movups  [rsp+0A28h+var_950], xmm0
0x18004b8b4  movups  [rsp+0A28h+var_940], xmm0
0x18004b8bc  movups  [rsp+0A28h+var_930], xmm0
0x18004b8c4  call    memset_0
0x18004b8c9  xorps   xmm0, xmm0
0x18004b8cc  mov     [rsp+0A28h+pLength], r13d
0x18004b8d1  xor     edx, edx; Val
0x18004b8d3  lea     r8d, [r13+41h]; Size
0x18004b8d7  lea     rcx, [rsp+0A28h+S]; void *
0x18004b8df  movups  xmmword ptr [rsp+0A28h+pAddress.u], xmm0
0x18004b8e7  call    memset_0
0x18004b8ec  xor     edx, edx; Val
0x18004b8ee  mov     [rsp+0A28h+var_848], r13d
0x18004b8f6  mov     r8d, 7FCh; Size
0x18004b8fc  lea     rcx, [rsp+0A28h+var_844]; void *
0x18004b904  call    memset_0
0x18004b909  mov     r9, cs:Microsoft_Windows_RRASEnableBits
0x18004b910  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004b917  xorps   xmm0, xmm0
0x18004b91a  mov     [rsp+0A28h+var_8C8], r13d
0x18004b922  xor     eax, eax
0x18004b924  mov     [rsp+0A28h+var_8A4], eax
0x18004b92b  movups  [rsp+0A28h+var_8C4], xmm0
0x18004b933  movups  [rsp+0A28h+var_8B4], xmm0
0x18004b93b  movups  [rsp+0A28h+var_970], xmm0
0x18004b943  test    r9b, r9b
0x18004b946  jns     short loc_18004B9C0
0x18004b948  lea     r8, aProcesschanges_1; "ProcessChanges"
0x18004b94f  mov     word ptr [rsp+0A28h+var_848], r13w
0x18004b958  lea     rdx, aEnteredWs; "Entered: %ws"
0x18004b95f  mov     word ptr [rsp+0A28h+var_8C8], r13w
0x18004b968  lea     rcx, [rsp+0A28h+var_848]
0x18004b970  call    FormatRRASErrorString
0x18004b975  mov     r9, cs:Microsoft_Windows_RRASEnableBits
0x18004b97c  test    r9b, r9b
0x18004b97f  jns     short loc_18004B9C0
0x18004b981  test    rdi, rdi
0x18004b984  lea     rax, [rsp+0A28h+var_8C8]
0x18004b98c  mov     [rsp+0A28h+var_A00], rax
0x18004b991  lea     r9, [rsp+0A28h+var_970]
0x18004b999  cmovnz  r9, rdi
0x18004b99d  mov     qword ptr [rsp+0A28h+var_A08], r13
0x18004b9a2  lea     r8, [rsp+0A28h+var_848]
0x18004b9aa  mov     rcx, r15
0x18004b9ad  lea     rdx, RasRtrmgrParamTraceInfo
0x18004b9b4  call    McTemplateU0zjzz_EventWriteTransfer
0x18004b9b9  mov     r9, cs:Microsoft_Windows_RRASEnableBits
0x18004b9c0  mov     ecx, cs:g_rtmProfile.MaxNextHopsInRoute
0x18004b9c6  lea     rdx, [rsp+0A28h+dwBytes]
0x18004b9cb  call    RTMSIZEOFROUTEINFO
0x18004b9d0  mov     esi, eax
0x18004b9d2  test    eax, eax
0x18004b9d4  jz      loc_18004BA77
0x18004b9da  test    r9b, 40h
0x18004b9de  jz      short loc_18004BA27
0x18004b9e0  test    rdi, rdi
0x18004b9e3  mov     word ptr [rsp+0A28h+var_8C8], r13w
0x18004b9ec  lea     rax, [rsp+0A28h+var_8C8]
0x18004b9f4  mov     rcx, r15
0x18004b9f7  mov     [rsp+0A28h+var_A00], rax
0x18004b9fc  lea     r9, [rsp+0A28h+var_970]
0x18004ba04  cmovnz  r9, rdi
0x18004ba08  mov     qword ptr [rsp+0A28h+var_A08], r13
0x18004ba0d  lea     r8, aProcesschanges_0; "ProcessChanges : Arithmatic Overflow du"...
0x18004ba14  lea     rdx, RasRtrMgrParamTraceError
0x18004ba1b  call    McTemplateU0zjzz_EventWriteTransfer
0x18004ba20  mov     r9, cs:Microsoft_Windows_RRASEnableBits
0x18004ba27  test    r9b, r9b
0x18004ba2a  jns     short loc_18004BA70
0x18004ba2c  lea     r8, aProcesschanges_1; "ProcessChanges"
0x18004ba33  mov     word ptr [rsp+0A28h+var_848], r13w
0x18004ba3c  lea     rdx, aLeavingWs; "Leaving: %ws"
0x18004ba43  lea     rcx, [rsp+0A28h+var_848]
0x18004ba4b  call    FormatRRASErrorString
0x18004ba50  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x18004ba57  jge     short loc_18004BA70
0x18004ba59  lea     r8, [rsp+0A28h+var_848]
0x18004ba61  mov     rcx, r15
0x18004ba64  lea     rdx, RasRtrmgrTraceInfo
0x18004ba6b  call    McTemplateU0z_EventWriteTransfer
0x18004ba70  mov     eax, esi
0x18004ba72  jmp     loc_18004C924
0x18004ba77  mov     r8d, dword ptr [rsp+0A28h+dwBytes]; dwBytes
0x18004ba7c  xor     edx, edx; dwFlags
0x18004ba7e  mov     rcx, cs:IPRouterHeap; hHeap
0x18004ba85  call    cs:__imp_HeapAlloc
0x18004ba8b  mov     [rsp+0A28h+RouteInfo], rax
0x18004ba93  mov     r14, rax
0x18004ba96  test    rax, rax
0x18004ba99  jnz     loc_18004BB2E
0x18004ba9f  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18004baa6  mov     bl, 40h ; '@'
0x18004baa8  test    bl, al
0x18004baaa  jz      short loc_18004BB21
0x18004baac  mov     r8d, dword ptr [rsp+0A28h+dwBytes]
0x18004bab1  lea     rdx, aProcesschanges_3; "ProcessChanges : error allocating %d by"...
0x18004bab8  lea     rcx, [rsp+0A28h+var_848]
0x18004bac0  mov     word ptr [rsp+0A28h+var_848], r13w
0x18004bac9  mov     word ptr [rsp+0A28h+var_8C8], r13w
0x18004bad2  call    FormatRRASErrorString
0x18004bad7  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18004bade  test    bl, al
0x18004bae0  jz      short loc_18004BB21
0x18004bae2  test    rdi, rdi
0x18004bae5  lea     rax, [rsp+0A28h+var_8C8]
0x18004baed  mov     [rsp+0A28h+var_A00], rax
0x18004baf2  lea     r9, [rsp+0A28h+var_970]
0x18004bafa  cmovnz  r9, rdi
0x18004bafe  mov     qword ptr [rsp+0A28h+var_A08], r13
0x18004bb03  lea     r8, [rsp+0A28h+var_848]
0x18004bb0b  mov     rcx, r15
0x18004bb0e  lea     rdx, RasRtrMgrParamTraceError
0x18004bb15  call    McTemplateU0zjzz_EventWriteTransfer
0x18004bb1a  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18004bb21  test    al, al
0x18004bb23  jns     loc_18004BCAD
0x18004bb29  jmp     loc_18004BC69
0x18004bb2e  mov     ecx, cs:g_rtmProfile.NumberOfViews
0x18004bb34  lea     rdx, [rsp+0A28h+var_9C8]
0x18004bb39  call    RTMSIZEOFDESTINFO
0x18004bb3e  mov     esi, eax
0x18004bb40  test    eax, eax
0x18004bb42  jz      short loc_18004BBB1
0x18004bb44  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004bb4b  jz      short loc_18004BB8D
0x18004bb4d  test    rdi, rdi
0x18004bb50  mov     word ptr [rsp+0A28h+var_8C8], r13w
0x18004bb59  lea     rax, [rsp+0A28h+var_8C8]
0x18004bb61  mov     rcx, r15
0x18004bb64  mov     [rsp+0A28h+var_A00], rax
0x18004bb69  lea     r9, [rsp+0A28h+var_970]
0x18004bb71  cmovnz  r9, rdi
0x18004bb75  mov     qword ptr [rsp+0A28h+var_A08], r13
0x18004bb7a  lea     r8, aProcesschanges; "ProcessChanges : Arithmatic Overflow du"...
0x18004bb81  lea     rdx, RasRtrMgrParamTraceError
0x18004bb88  call    McTemplateU0zjzz_EventWriteTransfer
0x18004bb8d  mov     rcx, cs:IPRouterHeap; hHeap
0x18004bb94  mov     r8, r14; lpMem
0x18004bb97  xor     edx, edx; dwFlags
0x18004bb99  call    cs:__imp_HeapFree
0x18004bb9f  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x18004bba6  jge     loc_18004BA70
0x18004bbac  jmp     loc_18004BA2C
0x18004bbb1  mov     r8d, dword ptr [rsp+0A28h+var_9C8]; dwBytes
0x18004bbb6  xor     edx, edx; dwFlags
0x18004bbb8  mov     rcx, cs:IPRouterHeap; hHeap
0x18004bbbf  call    cs:__imp_HeapAlloc
0x18004bbc5  mov     [rsp+0A28h+var_978], rax
0x18004bbcd  mov     rsi, rax
0x18004bbd0  test    rax, rax
0x18004bbd3  jnz     loc_18004BCB7
0x18004bbd9  mov     bl, 40h ; '@'
0x18004bbdb  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18004bbe1  jz      short loc_18004BC4E
0x18004bbe3  mov     r8d, dword ptr [rsp+0A28h+var_9C8]
0x18004bbe8  lea     rdx, aProcesschanges_4; "ProcessChanges : error allocating %d by"...
0x18004bbef  lea     rcx, [rsp+0A28h+var_848]
0x18004bbf7  mov     word ptr [rsp+0A28h+var_848], r13w
0x18004bc00  mov     word ptr [rsp+0A28h+var_8C8], r13w
0x18004bc09  call    FormatRRASErrorString
0x18004bc0e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18004bc14  jz      short loc_18004BC4E
0x18004bc16  test    rdi, rdi
0x18004bc19  lea     rax, [rsp+0A28h+var_8C8]
0x18004bc21  mov     [rsp+0A28h+var_A00], rax
0x18004bc26  lea     r9, [rsp+0A28h+var_970]
0x18004bc2e  cmovnz  r9, rdi
0x18004bc32  mov     qword ptr [rsp+0A28h+var_A08], r13
0x18004bc37  lea     r8, [rsp+0A28h+var_848]
0x18004bc3f  mov     rcx, r15
0x18004bc42  lea     rdx, RasRtrMgrParamTraceError
0x18004bc49  call    McTemplateU0zjzz_EventWriteTransfer
0x18004bc4e  mov     rcx, cs:IPRouterHeap; hHeap
0x18004bc55  mov     r8, r14; lpMem
0x18004bc58  xor     edx, edx; dwFlags
0x18004bc5a  call    cs:__imp_HeapFree
0x18004bc60  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x18004bc67  jge     short loc_18004BCAD
0x18004bc69  lea     r8, aProcesschanges_1; "ProcessChanges"
0x18004bc70  mov     word ptr [rsp+0A28h+var_848], r13w
0x18004bc79  lea     rdx, aLeavingWs; "Leaving: %ws"
0x18004bc80  lea     rcx, [rsp+0A28h+var_848]
0x18004bc88  call    FormatRRASErrorString
0x18004bc8d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x18004bc94  jge     short loc_18004BCAD
0x18004bc96  lea     r8, [rsp+0A28h+var_848]
0x18004bc9e  mov     rcx, r15
0x18004bca1  lea     rdx, RasRtrmgrTraceInfo
0x18004bca8  call    McTemplateU0z_EventWriteTransfer
0x18004bcad  mov     eax, 8
0x18004bcb2  jmp     loc_18004C924
0x18004bcb7  mov     eax, ebx
0x18004bcb9  mov     [rsp+0A28h+var_9A0], r13
0x18004bcc1  neg     eax
0x18004bcc3  mov     dword ptr [rsp+0A28h+dwBytes], r13d
0x18004bcc8  mov     r8d, 2; unsigned int
0x18004bcce  mov     dword ptr [rsp+0A28h+dwBytes+4], 1
0x18004bcd6  sbb     ebx, ebx
0x18004bcd8  mov     rcx, rdi; struct _GUID *
0x18004bcdb  and     ebx, 0FFFFFFCAh
0x18004bcde  mov     r15, r13
0x18004bce1  add     ebx, 57h ; 'W'
0x18004bce4  mov     r14d, r13d
0x18004bce7  mov     edx, ebx; unsigned int
0x18004bce9  call    GetRtmRegistrationHandle
0x18004bcee  mov     r8d, 3; unsigned int
0x18004bcf4  mov     [rsp+0A28h+var_988], rax
0x18004bcfc  mov     edx, ebx; unsigned int
0x18004bcfe  mov     rcx, rdi; struct _GUID *
0x18004bd01  mov     r13, rax
0x18004bd04  call    GetRtmRegistrationHandle
0x18004bd09  mov     edx, ebx; unsigned int
0x18004bd0b  mov     [rsp+0A28h+RtmRegHandle], rax
0x18004bd13  mov     rcx, rdi; struct _GUID *
0x18004bd16  call    GetRtmNotificationHandle
0x18004bd1b  mov     [rsp+0A28h+var_990], rax
0x18004bd23  lea     r12, RasRtrMgrParamTraceError
0x18004bd2a  mov     bl, 40h ; '@'
0x18004bd2c  mov     rdx, [rsp+0A28h+NotifyHandle]; NotifyHandle
0x18004bd31  lea     r8, [rsp+0A28h+dwBytes+4]; NumDests
0x18004bd36  mov     r9, rsi; ChangedDests
0x18004bd39  mov     rcx, r13; RtmRegHandle
0x18004bd3c  call    cs:__imp_RtmGetChangedDests
0x18004bd42  cmp     dword ptr [rsp+0A28h+dwBytes+4], 1
0x18004bd47  jb      loc_18004C892
0x18004bd4d  xor     r11d, r11d
0x18004bd50  cmp     [rsi+0Ah], r11w
0x18004bd55  jnz     loc_18004BF65
0x18004bd5b  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r11b
0x18004bd62  jge     loc_18004BE12
0x18004bd68  mov     word ptr [rsp+0A28h+var_848], r11w
0x18004bd71  mov     word ptr [rsp+0A28h+var_8C8], r11w
0x18004bd7a  movzx   eax, word ptr [rsi+0Ah]
0x18004bd7e  movzx   edx, byte ptr [rsi+0Eh]
0x18004bd82  mov     r10d, eax
0x18004bd85  movzx   r9d, byte ptr [rsi+0Dh]
0x18004bd8a  movzx   r8d, byte ptr [rsi+0Ch]
0x18004bd8f  mov     dword ptr [rsp+0A28h+var_9E0], r11d
0x18004bd94  mov     dword ptr [rsp+0A28h+var_9E8], r11d
0x18004bd99  movzx   ecx, al
0x18004bd9c  movzx   eax, byte ptr [rsi+0Fh]
0x18004bda0  shr     r10d, 8
0x18004bda4  mov     dword ptr [rsp+0A28h+var_9F0], r10d
0x18004bda9  mov     dword ptr [rsp+0A28h+var_9F8], ecx
0x18004bdad  lea     rcx, [rsp+0A28h+var_848]
0x18004bdb5  mov     dword ptr [rsp+0A28h+var_A00], eax
0x18004bdb9  mov     [rsp+0A28h+var_A08], edx
0x18004bdbd  lea     rdx, aCheckingDestDD; "Checking dest %d.%d.%d.%d/%d is marked"
0x18004bdc4  call    FormatRRASErrorString
0x18004bdc9  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18004bdd0  jge     short loc_18004BE12
0x18004bdd2  test    rdi, rdi
0x18004bdd5  lea     rax, [rsp+0A28h+var_8C8]
0x18004bddd  mov     [rsp+0A28h+var_A00], rax
0x18004bde2  lea     r9, [rsp+0A28h+var_970]
0x18004bdea  cmovnz  r9, rdi
0x18004bdee  mov     qword ptr [rsp+0A28h+var_A08], 0
0x18004bdf7  lea     r8, [rsp+0A28h+var_848]
0x18004bdff  lea     rdx, RasRtrmgrParamTraceInfo
0x18004be06  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004be0d  call    McTemplateU0zjzz_EventWriteTransfer
0x18004be12  mov     r8, [rsi]; DestHandle
0x18004be15  lea     r9, [rsp+0A28h+DestMarked]; DestMarked
0x18004be1a  mov     rdx, [rsp+0A28h+var_990]; NotifyHandle
0x18004be22  mov     rcx, [rsp+0A28h+RtmRegHandle]; RtmRegHandle
0x18004be2a  call    cs:__imp_RtmIsMarkedForChangeNotification
0x18004be30  xor     r11d, r11d
0x18004be33  mov     r8d, eax
0x18004be36  test    eax, eax
0x18004be38  jnz     loc_18004BEF0
0x18004be3e  cmp     [rsp+0A28h+DestMarked], r11d
0x18004be43  jz      short loc_18004BEAE
0x18004be45  mov     al, byte ptr cs:Microsoft_Windows_RRASEnableBits
0x18004be4b  and     al, bl
  ... truncated ...
```

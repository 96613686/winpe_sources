# AddRtmRoute

- ea: `0x1800488c0`
- end: `0x180049a01`
- name: `AddRtmRoute`
- size: `4417`
- prototype: `__int64 __fastcall(RTM_ENTITY_HANDLE RtmRegHandle, unsigned __int8 *, int, unsigned int, ULONG, unsigned int, struct _GUID *, HANDLE *)`
- caller_count: `3`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800061e8`
- `0x18000ace0`
- `0x18003f1a4`

## callees

- `0x18000f80c`
- `0x180011790`
- `0x18002ee20`
- `0x1800488c0`
- `0x18004a3d4`
- `0x18004b488`
- `0x180051e88`
- `0x180051ef8`
- `0x180057c14`
- `0x180057c48`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x1800490ba`
- `ntdll!RtlReleaseResource` at `0x180049992`
- `ntdll!RtlReleaseResource` at `0x1800490ba`
- `ntdll!RtlReleaseResource` at `0x180049992`
- `ntdll!RtlAcquireResourceShared` at `0x180048ff7`
- `ntdll!RtlAcquireResourceShared` at `0x180048ff7`
- `KERNEL32!HeapFree` at `0x180048b7b`
- `KERNEL32!HeapFree` at `0x1800499bf`
- `KERNEL32!HeapFree` at `0x1800499d6`
- `KERNEL32!HeapFree` at `0x180048b7b`
- `KERNEL32!HeapFree` at `0x1800499bf`
- `KERNEL32!HeapFree` at `0x1800499d6`
- `KERNEL32!HeapAlloc` at `0x1800489c7`
- `KERNEL32!HeapAlloc` at `0x180048ad7`
- `KERNEL32!HeapAlloc` at `0x1800489c7`
- `KERNEL32!HeapAlloc` at `0x180048ad7`
- `rtm!RtmGetExactMatchDestination` at `0x18004927f`
- `rtm!RtmGetExactMatchDestination` at `0x1800496c4`
- `rtm!RtmGetExactMatchDestination` at `0x18004927f`
- `rtm!RtmGetExactMatchDestination` at `0x1800496c4`
- `rtm!RtmReleaseDestInfo` at `0x180049545`
- `rtm!RtmReleaseDestInfo` at `0x180049871`
- `rtm!RtmReleaseDestInfo` at `0x180049545`
- `rtm!RtmReleaseDestInfo` at `0x180049871`
- `rtm!RtmLockDestination` at `0x180049770`
- `rtm!RtmLockDestination` at `0x1800497e7`
- `rtm!RtmLockDestination` at `0x180049770`
- `rtm!RtmLockDestination` at `0x1800497e7`
- `rtm!RtmAddRouteToDest` at `0x180049092`
- `rtm!RtmAddRouteToDest` at `0x18004940e`
- `rtm!RtmAddRouteToDest` at `0x180049092`
- `rtm!RtmAddRouteToDest` at `0x18004940e`
- `rtm!RtmReleaseNextHops` at `0x1800499ad`
- `rtm!RtmReleaseNextHops` at `0x1800499ad`
- `rtm!RtmAddNextHop` at `0x180048c24`
- `rtm!RtmAddNextHop` at `0x180048c24`
- `rtm!RtmConvertIpv6AddressAndLengthToNetAddress` at `0x180048bdb`
- `rtm!RtmConvertIpv6AddressAndLengthToNetAddress` at `0x180048bdb`
- `rtm!RtmGetOpaqueInformationPointer` at `0x1800497a5`
- `rtm!RtmGetOpaqueInformationPointer` at `0x1800497a5`
- `rtm!RtmMarkDestForChangeNotification` at `0x1800493ac`
- `rtm!RtmMarkDestForChangeNotification` at `0x1800493ac`
- `rtm!RtmIsMarkedForChangeNotification` at `0x18004932c`
- `rtm!RtmIsMarkedForChangeNotification` at `0x18004932c`

## string_xrefs

- `0x180048aaa`: `AddRtmRoute : Arithmatic Overflow during allocation of memory for route info`

## pseudocode

```c
__int64 __fastcall AddRtmRoute(
        RTM_ENTITY_HANDLE RtmRegHandle,
        unsigned __int8 *a2,
        int a3,
        unsigned int a4,
        ULONG a5,
        unsigned int a6,
        struct _GUID *a7,
        HANDLE *a8)
{
  void *v9; // rdi
  struct _RTM_NET_ADDRESS *v10; // r12
  __int128 *v11; // r9
  unsigned int v13; // ebx
  __int128 *v14; // r9
  __int128 *v15; // r9
  IN6_ADDR v16; // xmm0
  DWORD ExactMatchDestination; // edi
  __int128 *v18; // r9
  unsigned int v19; // ebx
  __int64 Ipv6StringFromAddress; // rax
  char v21; // al
  __int128 *v22; // r9
  ULONG v23; // ebx
  __int64 v24; // rax
  __int128 *v25; // r9
  unsigned int v26; // ebx
  RTM_ENTITY_HANDLE v27; // rax
  __int64 InterfaceBinding; // rax
  ULONG v29; // ebx
  unsigned __int8 *v30; // rcx
  unsigned int v31; // r10d
  __int128 *v32; // r9
  unsigned int v33; // ebx
  __int64 v34; // rax
  __int128 *v35; // r9
  __int128 *v36; // r9
  DWORD v37; // eax
  const wchar_t *v38; // rdx
  __int64 *v39; // rdx
  unsigned int v40; // ebx
  __int64 v41; // rax
  __int128 *v42; // r9
  bool v43; // zf
  unsigned int NumBits; // ebx
  __int64 Ipv6StringFromNetAddress; // rax
  __int128 *v46; // r9
  void *v47; // rbx
  char v48; // bl
  __int128 *v49; // r9
  const wchar_t *v50; // rdx
  __int128 *v51; // r9
  unsigned int v52; // ebx
  __int64 v53; // rax
  __int128 *v54; // r9
  ULONG TimeToLive[2]; // [rsp+20h] [rbp-A18h]
  ULONG TimeToLivea[2]; // [rsp+20h] [rbp-A18h]
  ULONG TimeToLiveb[2]; // [rsp+20h] [rbp-A18h]
  ULONG TimeToLivec[2]; // [rsp+20h] [rbp-A18h]
  RTM_ROUTE_LIST_HANDLE RouteListHandle; // [rsp+28h] [rbp-A10h]
  RTM_ROUTE_LIST_HANDLE RouteListHandlea; // [rsp+28h] [rbp-A10h]
  RTM_NOTIFY_FLAGS NotifyType[2]; // [rsp+30h] [rbp-A08h]
  RTM_NOTIFY_FLAGS NotifyTypea[2]; // [rsp+30h] [rbp-A08h]
  RTM_NOTIFY_HANDLE NotifyHandle; // [rsp+38h] [rbp-A00h]
  RTM_NOTIFY_HANDLE NotifyHandlea; // [rsp+38h] [rbp-A00h]
  PRTM_ROUTE_CHANGE_FLAGS v65; // [rsp+40h] [rbp-9F8h]
  PRTM_ROUTE_CHANGE_FLAGS v66; // [rsp+40h] [rbp-9F8h]
  __int64 v67; // [rsp+48h] [rbp-9F0h]
  DWORD ChangeFlags; // [rsp+70h] [rbp-9C8h] BYREF
  SIZE_T dwBytes; // [rsp+78h] [rbp-9C0h] BYREF
  WINBOOL DestMarked[2]; // [rsp+80h] [rbp-9B8h] BYREF
  int v72; // [rsp+88h] [rbp-9B0h]
  HANDLE NextHopHandle; // [rsp+90h] [rbp-9A8h] BYREF
  RTM_ENTITY_HANDLE RtmRegHandlea; // [rsp+98h] [rbp-9A0h]
  PRTM_ROUTE_HANDLE RouteHandle; // [rsp+A0h] [rbp-998h] BYREF
  PRTM_ROUTE_INFO RouteInfo; // [rsp+A8h] [rbp-990h]
  IN6_ADDR Address; // [rsp+B0h] [rbp-988h] BYREF
  struct _RTM_NEXTHOP_INFO pNetAddress; // [rsp+C0h] [rbp-978h] BYREF
  struct _RTM_DEST_INFO DestInfo; // [rsp+100h] [rbp-938h] BYREF
  __int128 v80; // [rsp+160h] [rbp-8D8h] BYREF
  int v81; // [rsp+170h] [rbp-8C8h] BYREF
  __int128 v82; // [rsp+174h] [rbp-8C4h]
  __int128 v83; // [rsp+184h] [rbp-8B4h]
  int v84; // [rsp+194h] [rbp-8A4h]
  _BYTE v85[80]; // [rsp+1A0h] [rbp-898h] BYREF
  int v86; // [rsp+1F0h] [rbp-848h] BYREF
  char v87[2044]; // [rsp+1F4h] [rbp-844h] BYREF

  v9 = (void *)a4;
  v72 = a3;
  RtmRegHandlea = RtmRegHandle;
  DestMarked[0] = a4;
  RouteHandle = a8;
  memset(&pNetAddress, 0, 52);
  ChangeFlags = 0;
  NextHopHandle = 0;
  LODWORD(dwBytes) = 0;
  v86 = 0;
  memset_0(v87, 0, sizeof(v87));
  v81 = 0;
  v84 = 0;
  v82 = 0;
  v83 = 0;
  v80 = 0;
  if ( a8 )
    *a8 = 0;
  v10 = (struct _RTM_NET_ADDRESS *)HeapAlloc(IPRouterHeap, 0, 0x14u);
  if ( v10 )
  {
    v13 = RTMSIZEOFROUTEINFO(g_rtmProfile.MaxNextHopsInRoute, &dwBytes);
    if ( v13 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v81) = 0;
        v14 = &v80;
        if ( a7 )
          LODWORD(v14) = (_DWORD)a7;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)L"AddRtmRoute : Arithmatic Overflow during allocation of memory for route info",
          (_DWORD)v14,
          0,
          (__int64)&v81);
      }
LABEL_22:
      HeapFree(IPRouterHeap, 0, v10);
      return v13;
    }
    RouteInfo = (PRTM_ROUTE_INFO)HeapAlloc(IPRouterHeap, 0, (unsigned int)dwBytes);
    if ( !RouteInfo )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v86) = 0;
        LOWORD(v81) = 0;
        FormatRRASErrorString(&v86, L"AddRtmRoute : error allocating %d bytes for route info", (unsigned int)dwBytes);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v15 = &v80;
          if ( a7 )
            LODWORD(v15) = (_DWORD)a7;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v86,
            (_DWORD)v15,
            0,
            (__int64)&v81);
        }
      }
      v13 = 8;
      goto LABEL_22;
    }
    if ( a6 )
    {
      *(_DWORD *)pNetAddress.NextHopAddress.AddrBits = *((_DWORD *)a2 + 3);
      *(_DWORD *)&pNetAddress.NextHopAddress.AddressFamily = 2097154;
    }
    else
    {
      v16 = *(IN6_ADDR *)(a2 + 20);
      pNetAddress.NextHopAddress.AddressFamily = 23;
      Address = v16;
      RtmConvertIpv6AddressAndLengthToNetAddress(&pNetAddress.NextHopAddress, &Address, 0x80u, 0x10u);
    }
    pNetAddress.InterfaceIndex = *((_DWORD *)a2 + 12);
    pNetAddress.EntitySpecificInfo = v9;
    pNetAddress.Flags = 0;
    pNetAddress.RemoteNextHop = 0;
    NextHopHandle = 0;
    ExactMatchDestination = RtmAddNextHop(RtmRegHandle, &pNetAddress, &NextHopHandle, &ChangeFlags);
    if ( ExactMatchDestination )
    {
LABEL_148:
      HeapFree(IPRouterHeap, 0, v10);
      HeapFree(IPRouterHeap, 0, RouteInfo);
      return ExactMatchDestination;
    }
    if ( a6 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v86) = 0;
        LOWORD(v81) = 0;
        FormatRRASErrorString(
          &v86,
          L"Route to %d.%d.%d.%d/%d.%d.%d.%d",
          *a2,
          a2[1],
          a2[2],
          a2[3],
          a2[4],
          a2[5],
          a2[6],
          a2[7]);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v18 = &v80;
          if ( a7 )
            LODWORD(v18) = (_DWORD)a7;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v86,
            (_DWORD)v18,
            0,
            (__int64)&v81);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            LOWORD(v86) = 0;
            LOWORD(v81) = 0;
            LODWORD(v67) = HIBYTE(DestMarked[0]);
            LODWORD(v65) = BYTE2(DestMarked[0]);
            LODWORD(NotifyHandle) = BYTE1(DestMarked[0]);
            NotifyType[0] = LOBYTE(DestMarked[0]);
            LODWORD(RouteListHandle) = a2[15];
            TimeToLivea[0] = a2[14];
            FormatRRASErrorString(
              &v86,
              L"Next Hop %d.%d.%d.%d/%d.%d.%d.%d, If 0x%x, handle is 0x%x",
              a2[12],
              a2[13],
              *(_QWORD *)TimeToLivea,
              RouteListHandle,
              *(_QWORD *)NotifyType,
              NotifyHandle,
              v65,
              v67,
              *((_DWORD *)a2 + 12),
              NextHopHandle);
            goto LABEL_41;
          }
        }
      }
    }
    else
    {
      memset_0(v85, 0, 0x41u);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v19 = *((_DWORD *)a2 + 4);
        Address = *(IN6_ADDR *)a2;
        LOWORD(v86) = 0;
        LOWORD(v81) = 0;
        Ipv6StringFromAddress = GetIpv6StringFromAddress(&Address, v85);
        FormatRRASErrorString(&v86, L"Route to %hs/%d", Ipv6StringFromAddress, v19);
        v21 = Microsoft_Windows_RRASEnableBits;
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v22 = &v80;
          if ( a7 )
            LODWORD(v22) = (_DWORD)a7;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v86,
            (_DWORD)v22,
            0,
            (__int64)&v81);
          v21 = Microsoft_Windows_RRASEnableBits;
        }
        if ( (v21 & 0x40) != 0 )
        {
          v23 = *((_DWORD *)a2 + 12);
          Address = *(IN6_ADDR *)(a2 + 20);
          LOWORD(v86) = 0;
          LOWORD(v81) = 0;
          v24 = GetIpv6StringFromAddress(&Address, v85);
          TimeToLive[0] = v23;
          FormatRRASErrorString(
            &v86,
            L"Next Hop %hs/%d, If 0x%x, handle is 0x%x",
            v24,
            (unsigned int)DestMarked[0],
            *(_QWORD *)TimeToLive,
            NextHopHandle);
LABEL_41:
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            v25 = &v80;
            if ( a7 )
              LODWORD(v25) = (_DWORD)a7;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrMgrParamTraceError,
              (unsigned int)&v86,
              (_DWORD)v25,
              0,
              (__int64)&v81);
          }
        }
      }
    }
    ExactMatchDestination = ConvertRouteInfoToRtm(
                              (int)RtmRegHandlea,
                              (int)a2,
                              (int)NextHopHandle,
                              v72,
                              a6,
                              a7,
                              v10,
                              RouteInfo);
    if ( ExactMatchDestination )
      goto LABEL_147;
    ExactMatchDestination = 87;
    v26 = a6 != 0 ? 33 : 87;
    *(_QWORD *)DestMarked = GetRtmRegistrationHandle(a7, v26, 0x2717u);
    dwBytes = GetRtmRegistrationHandle(a7, v26, 3u);
    *(_QWORD *)Address.u.Byte = GetRtmNotificationHandle(a7, v26);
    v27 = RtmRegHandlea;
    if ( RtmRegHandlea == *(RTM_ENTITY_HANDLE *)DestMarked || RtmRegHandlea == (RTM_ENTITY_HANDLE)dwBytes )
    {
      RtlAcquireResourceShared(&stru_18008C500, 1u);
      InterfaceBinding = GetInterfaceBinding(*((unsigned int *)a2 + 12), a6);
      if ( !InterfaceBinding || !*(_DWORD *)(InterfaceBinding + 16) )
      {
        RtlReleaseResource(&stru_18008C500);
        goto LABEL_147;
      }
      v27 = RtmRegHandlea;
    }
    v29 = a5;
    if ( a5 != -1 )
    {
      if ( a5 >= 0x418937 )
      {
        v29 = -1;
        a5 = -1;
      }
      else
      {
        v29 = 1000 * a5;
        a5 *= 1000;
      }
    }
    ChangeFlags = 0;
    ExactMatchDestination = RtmAddRouteToDest(v27, RouteHandle, v10, RouteInfo, v29, 0, 0, 0, &ChangeFlags);
    if ( RtmRegHandlea == *(RTM_ENTITY_HANDLE *)DestMarked || RtmRegHandlea == (RTM_ENTITY_HANDLE)dwBytes )
      RtlReleaseResource(&stru_18008C500);
    if ( !(unsigned int)IsDefaultRoute(a2, a6) )
    {
LABEL_101:
      if ( a6 )
        v43 = *((_DWORD *)v30 + 1) == -1;
      else
        v43 = *((_DWORD *)v30 + 4) == 128;
      if ( !v43 || *((_DWORD *)v30 + 14) != 3 || (v72 & 0x20) != 0 )
        goto LABEL_147;
      memset_0(&DestInfo, 0, sizeof(DestInfo));
      RouteHandle = 0;
      if ( a6 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
          goto LABEL_116;
        LOWORD(v86) = 0;
        LOWORD(v81) = 0;
        NotifyTypea[0] = v10->NumBits;
        LODWORD(RouteListHandlea) = v10->AddrBits[3];
        TimeToLiveb[0] = v10->AddrBits[2];
        FormatRRASErrorString(
          &v86,
          L"Non-stack Netmgmt host route %d.%d.%d.%d/%d",
          v10->AddrBits[0],
          v10->AddrBits[1],
          *(_QWORD *)TimeToLiveb,
          RouteListHandlea,
          *(_QWORD *)NotifyTypea);
      }
      else
      {
        memset_0(v85, 0, 0x41u);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
          goto LABEL_116;
        LOWORD(v86) = 0;
        LOWORD(v81) = 0;
        NumBits = v10->NumBits;
        Ipv6StringFromNetAddress = GetIpv6StringFromNetAddress(v10, v85);
        FormatRRASErrorString(&v86, L"Non-stack Netmgmt host route %hs/%d", Ipv6StringFromNetAddress, NumBits);
      }
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v46 = &v80;
        if ( a7 )
          LODWORD(v46) = (_DWORD)a7;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v86,
          (_DWORD)v46,
          0,
          (__int64)&v81);
      }
LABEL_116:
      v47 = (void *)dwBytes;
      ExactMatchDestination = RtmGetExactMatchDestination((RTM_ENTITY_HANDLE)dwBytes, v10, 0xFFFFFFFF, 1u, &DestInfo);
      if ( ExactMatchDestination )
      {
        v48 = Microsoft_Windows_RRASEnableBits;
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0
          || (LOWORD(v86) = 0,
              LOWORD(v81) = 0,
              FormatRRASErrorString(
                &v86,
                L"AddRtmRoute : error %d retriveing host route destination",
                ExactMatchDestination),
              v48 = Microsoft_Windows_RRASEnableBits,
              (Microsoft_Windows_RRASEnableBits & 0x40) == 0) )
        {
LABEL_137:
          if ( a6 )
          {
            if ( v48 < 0 )
            {
              LODWORD(NotifyHandlea) = ExactMatchDestination;
              LOWORD(v86) = 0;
              LOWORD(v81) = 0;
              NotifyTypea[0] = v10->NumBits;
              LODWORD(RouteListHandlea) = v10->AddrBits[3];
              TimeToLivec[0] = v10->AddrBits[2];
              FormatRRASErrorString(
                &v86,
                L"Non-stack Netmgmt host route %d.%d.%d.%d/%d opaq info set, res == %d",
                v10->AddrBits[0],
                v10->AddrBits[1],
                *(_QWORD *)TimeToLivec,
                RouteListHandlea,
                *(_QWORD *)NotifyTypea,
                NotifyHandlea);
              goto LABEL_142;
            }
          }
          else
          {
            memset_0(v85, 0, 0x41u);
            if ( v48 < 0 )
            {
              LOWORD(v86) = 0;
              LOWORD(v81) = 0;
              v52 = v10->NumBits;
              v53 = GetIpv6StringFromNetAddress(v10, v85);
              TimeToLivec[0] = ExactMatchDestination;
              FormatRRASErrorString(
                &v86,
                L"Non-stack Netmgmt host route %hs/%d opaq info set, res == %d",
                v53,
                v52,
                *(_QWORD *)TimeToLivec);
LABEL_142:
              if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
              {
                v54 = &v80;
                if ( a7 )
                  LODWORD(v54) = (_DWORD)a7;
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasRtrmgrParamTraceInfo,
                  (unsigned int)&v86,
                  (_DWORD)v54,
                  0,
                  (__int64)&v81);
              }
            }
          }
LABEL_147:
          RtmReleaseNextHops(RtmRegHandlea, 1u, &NextHopHandle);
          goto LABEL_148;
        }
        v49 = &v80;
        if ( a7 )
          LODWORD(v49) = (_DWORD)a7;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v86,
          (_DWORD)v49,
          0,
          (__int64)&v81);
LABEL_136:
        v48 = Microsoft_Windows_RRASEnableBits;
        goto LABEL_137;
      }
      ExactMatchDestination = RtmLockDestination(v47, DestInfo.DestHandle, 1, 1);
      if ( ExactMatchDestination )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v50 = L"AddRtmRoute : error %d locking host route destination";
          goto LABEL_131;
        }
LABEL_135:
        RtmReleaseDestInfo(v47, &DestInfo);
        goto LABEL_136;
      }
      ExactMatchDestination = RtmGetOpaqueInformationPointer(v47, DestInfo.DestHandle, (PVOID *)&RouteHandle);
      if ( ExactMatchDestination )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
          goto LABEL_135;
        v50 = L"AddRtmRoute : error %d retrieving opaque info";
      }
      else
      {
        *(_DWORD *)RouteHandle = -65535;
        ExactMatchDestination = RtmLockDestination(v47, DestInfo.DestHandle, 1, 0);
        if ( !ExactMatchDestination || (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
          goto LABEL_135;
        v50 = L"AddRtmRoute : error %d unlocking dest";
      }
LABEL_131:
      LOWORD(v86) = 0;
      LOWORD(v81) = 0;
      FormatRRASErrorString(&v86, v50, ExactMatchDestination);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v51 = &v80;
        if ( a7 )
          LODWORD(v51) = (_DWORD)a7;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v86,
          (_DWORD)v51,
          0,
          (__int64)&v81);
      }
      goto LABEL_135;
    }
    memset_0(&DestInfo, 0, sizeof(DestInfo));
    DestMarked[0] = 0;
    if ( a6 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v86) = 0;
        LOWORD(v81) = 0;
        v31 = v10->NumBits;
        LODWORD(v67) = 0;
        LODWORD(v66) = 0;
        LODWORD(NotifyHandlea) = v31 >> 8;
        NotifyTypea[0] = (unsigned __int8)v31;
        LODWORD(RouteListHandlea) = v10->AddrBits[3];
        TimeToLiveb[0] = v10->AddrBits[2];
        FormatRRASErrorString(
          &v86,
          L"Checking dest %d.%d.%d.%d/%d for mark",
          v10->AddrBits[0],
          v10->AddrBits[1],
          *(_QWORD *)TimeToLiveb,
          RouteListHandlea,
          *(_QWORD *)NotifyTypea,
          NotifyHandlea,
          v66,
          v67);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v32 = &v80;
          if ( a7 )
            LODWORD(v32) = (_DWORD)a7;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v86,
            (_DWORD)v32,
            0,
            (__int64)&v81);
        }
      }
    }
    else
    {
      memset_0(v85, 0, 0x41u);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v86) = 0;
        LOWORD(v81) = 0;
        v33 = v10->NumBits;
        v34 = GetIpv6StringFromNetAddress(v10, v85);
        FormatRRASErrorString(&v86, L"Checking dest %hs/%d for mark", v34, v33);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v35 = &v80;
          if ( a7 )
            LODWORD(v35) = (_DWORD)a7;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v86,
            (_DWORD)v35,
            0,
            (__int64)&v81);
        }
        v29 = a5;
      }
    }
    ExactMatchDestination = RtmGetExactMatchDestination((RTM_ENTITY_HANDLE)dwBytes, v10, 0xFFFFFFFF, 1u, &DestInfo);
    if ( ExactMatchDestination )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v86) = 0;
        LOWORD(v81) = 0;
        FormatRRASErrorString(
          &v86,
          L"AddRtmRoute: error %d failed to get destination 0/0 for change notification",
          ExactMatchDestination);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v36 = &v80;
          if ( a7 )
            LODWORD(v36) = (_DWORD)a7;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v86,
            (_DWORD)v36,
            0,
            (__int64)&v81);
        }
      }
      goto LABEL_100;
    }
    v37 = RtmIsMarkedForChangeNotification(
            (RTM_ENTITY_HANDLE)dwBytes,
            *(RTM_NOTIFY_HANDLE *)Address.u.Byte,
            DestInfo.DestHandle,
            DestMarked);
    ExactMatchDestination = v37;
    if ( v37 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        goto LABEL_99;
      v38 = L"AddRtmRoute: error %d failed to check destination 0/0 for change notification";
    }
    else
    {
      if ( DestMarked[0] )
        goto LABEL_99;
      v37 = RtmMarkDestForChangeNotification(
              (RTM_ENTITY_HANDLE)dwBytes,
              *(RTM_NOTIFY_HANDLE *)Address.u.Byte,
              DestInfo.DestHandle,
              1);
      ExactMatchDestination = v37;
      if ( v37 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
          goto LABEL_99;
        v38 = L"AddRtmRoute: error %d failed to nark destination 0/0 for change notification";
      }
      else
      {
        ChangeFlags = 0;
        v37 = RtmAddRouteToDest(RtmRegHandlea, RouteHandle, v10, RouteInfo, v29, 0, 0, 0, &ChangeFlags);
        ExactMatchDestination = v37;
        if ( !v37 )
        {
          if ( a6 )
          {
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
              goto LABEL_99;
            LOWORD(v86) = 0;
            LOWORD(v81) = 0;
            NotifyTypea[0] = v10->NumBits;
            LODWORD(RouteListHandlea) = v10->AddrBits[3];
            TimeToLiveb[0] = v10->AddrBits[2];
            FormatRRASErrorString(
              &v86,
              L"Marked dest %d.%d.%d.%d/%d and added",
              v10->AddrBits[0],
              v10->AddrBits[1],
              *(_QWORD *)TimeToLiveb,
              RouteListHandlea,
              *(_QWORD *)NotifyTypea);
          }
          else
          {
            memset_0(v85, 0, 0x41u);
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
              goto LABEL_99;
            LOWORD(v86) = 0;
            LOWORD(v81) = 0;
            v40 = v10->NumBits;
            v41 = GetIpv6StringFromNetAddress(v10, v85);
            FormatRRASErrorString(&v86, L"Marked dest %hs/%d and added", v41, v40);
          }
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            v39 = RasRtrmgrParamTraceInfo;
            goto LABEL_96;
          }
LABEL_99:
          RtmReleaseDestInfo((RTM_ENTITY_HANDLE)dwBytes, &DestInfo);
LABEL_100:
          v30 = a2;
          goto LABEL_101;
        }
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
          goto LABEL_99;
        v38 = L"AddRtmRoute: error %d added route after marking destination";
      }
    }
    LOWORD(v86) = 0;
    LOWORD(v81) = 0;
    FormatRRASErrorString(&v86, v38, v37);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v39 = RasRtrMgrParamTraceError;
LABEL_96:
      v42 = &v80;
      if ( a7 )
        LODWORD(v42) = (_DWORD)a7;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (_DWORD)v39,
        (unsigned int)&v86,
        (_DWORD)v42,
        0,
        (__int64)&v81);
      goto LABEL_99;
    }
    goto LABEL_99;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
  {
    LOWORD(v86) = 0;
    LOWORD(v81) = 0;
    FormatRRASErrorString(&v86, L"AddRtmRoute : error allocating %d bytes for dest. address", 20);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v11 = &v80;
      if ( a7 )
        LODWORD(v11) = (_DWORD)a7;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrMgrParamTraceError,
        (unsigned int)&v86,
        (_DWORD)v11,
        0,
        (__int64)&v81);
    }
  }
  return 8;
}

```

## disassembly

```asm
0x1800488c0  push    rbx
0x1800488c2  push    rsi
0x1800488c3  push    rdi
0x1800488c4  push    r12
0x1800488c6  push    r13
0x1800488c8  push    r14
0x1800488ca  push    r15
0x1800488cc  sub     rsp, 0A00h
0x1800488d3  mov     rax, cs:__security_cookie
0x1800488da  xor     rax, rsp
0x1800488dd  mov     [rsp+0A38h+var_48], rax
0x1800488e5  mov     rbx, [rsp+0A38h+arg_38]
0x1800488ed  xorps   xmm0, xmm0
0x1800488f0  mov     r14d, [rsp+0A38h+arg_28]
0x1800488f8  xor     r13d, r13d
0x1800488fb  mov     rsi, [rsp+0A38h+arg_30]
0x180048903  mov     r15, rcx
0x180048906  mov     edi, r9d
0x180048909  xor     eax, eax
0x18004890b  mov     [rsp+0A38h+var_9B0], r8d
0x180048913  mov     r8d, 7FCh; Size
0x180048919  mov     qword ptr [rsp+0A38h+var_9D0], rdx
0x18004891e  xor     edx, edx; Val
0x180048920  mov     [rsp+0A38h+RtmRegHandle], rcx
0x180048928  lea     rcx, [rsp+0A38h+var_844]; void *
0x180048930  mov     [rsp+0A38h+DestMarked], edi
0x180048937  mov     [rsp+0A38h+RouteHandle], rbx
0x18004893f  movups  xmmword ptr [rsp+0A38h+pNetAddress.AddressFamily], xmm0
0x180048947  mov     dword ptr [rsp+0A38h+var_948], eax
0x18004894e  movups  xmmword ptr [rsp+0A38h+pNetAddress.AddrBits+0Ch], xmm0
0x180048956  mov     [rsp+0A38h+ChangeFlags], r13d
0x18004895b  movups  [rsp+0A38h+var_958], xmm0
0x180048963  mov     [rsp+0A38h+NextHopHandle], r13
0x18004896b  mov     dword ptr [rsp+0A38h+dwBytes], r13d
0x180048970  mov     [rsp+0A38h+var_848], r13d
0x180048978  mov     [rsp+0A38h+var_9D8], r14d
0x18004897d  call    memset_0
0x180048982  xorps   xmm0, xmm0
0x180048985  mov     [rsp+0A38h+var_8C8], r13d
0x18004898d  xor     eax, eax
0x18004898f  mov     [rsp+0A38h+var_8A4], eax
0x180048996  movups  [rsp+0A38h+var_8C4], xmm0
0x18004899e  movups  [rsp+0A38h+var_8B4], xmm0
0x1800489a6  movups  [rsp+0A38h+var_8D8], xmm0
0x1800489ae  test    rbx, rbx
0x1800489b1  jz      short loc_1800489B6
0x1800489b3  mov     [rbx], r13
0x1800489b6  mov     rcx, cs:IPRouterHeap; hHeap
0x1800489bd  mov     ebx, 14h
0x1800489c2  mov     r8d, ebx; dwBytes
0x1800489c5  xor     edx, edx; dwFlags
0x1800489c7  call    cs:__imp_HeapAlloc
0x1800489cd  mov     r12, rax
0x1800489d0  test    rax, rax
0x1800489d3  jnz     loc_180048A5D
0x1800489d9  mov     r14b, 40h ; '@'
0x1800489dc  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x1800489e3  jz      short loc_180048A53
0x1800489e5  mov     r8d, ebx
0x1800489e8  mov     word ptr [rsp+0A38h+var_848], r13w
0x1800489f1  lea     rdx, aAddrtmrouteErr_3; "AddRtmRoute : error allocating %d bytes"...
0x1800489f8  mov     word ptr [rsp+0A38h+var_8C8], r13w
0x180048a01  lea     rcx, [rsp+0A38h+var_848]
0x180048a09  call    FormatRRASErrorString
0x180048a0e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180048a15  jz      short loc_180048A53
0x180048a17  test    rsi, rsi
0x180048a1a  lea     rax, [rsp+0A38h+var_8C8]
0x180048a22  mov     [rsp+0A38h+RouteListHandle], rax
0x180048a27  lea     r9, [rsp+0A38h+var_8D8]
0x180048a2f  cmovnz  r9, rsi
0x180048a33  mov     qword ptr [rsp+0A38h+TimeToLive], r13
0x180048a38  lea     r8, [rsp+0A38h+var_848]
0x180048a40  lea     rdx, RasRtrMgrParamTraceError
0x180048a47  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180048a4e  call    McTemplateU0zjzz_EventWriteTransfer
0x180048a53  mov     eax, 8
0x180048a58  jmp     loc_1800499DE
0x180048a5d  mov     ecx, cs:g_rtmProfile.MaxNextHopsInRoute
0x180048a63  lea     rdx, [rsp+0A38h+dwBytes]
0x180048a68  call    RTMSIZEOFROUTEINFO
0x180048a6d  mov     ebx, eax
0x180048a6f  test    eax, eax
0x180048a71  jz      short loc_180048AC9
0x180048a73  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180048a7a  jz      loc_180048B6F
0x180048a80  test    rsi, rsi
0x180048a83  mov     word ptr [rsp+0A38h+var_8C8], r13w
0x180048a8c  lea     rax, [rsp+0A38h+var_8C8]
0x180048a94  mov     [rsp+0A38h+RouteListHandle], rax
0x180048a99  lea     r9, [rsp+0A38h+var_8D8]
0x180048aa1  cmovnz  r9, rsi
0x180048aa5  mov     qword ptr [rsp+0A38h+TimeToLive], r13
0x180048aaa  lea     r8, aAddrtmrouteAri; "AddRtmRoute : Arithmatic Overflow durin"...
0x180048ab1  lea     rdx, RasRtrMgrParamTraceError
0x180048ab8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180048abf  call    McTemplateU0zjzz_EventWriteTransfer
0x180048ac4  jmp     loc_180048B6F
0x180048ac9  mov     r8d, dword ptr [rsp+0A38h+dwBytes]; dwBytes
0x180048ace  xor     edx, edx; dwFlags
0x180048ad0  mov     rcx, cs:IPRouterHeap; hHeap
0x180048ad7  call    cs:__imp_HeapAlloc
0x180048add  mov     [rsp+0A38h+RouteInfo], rax
0x180048ae5  test    rax, rax
0x180048ae8  jnz     loc_180048B88
0x180048aee  mov     r14b, 40h ; '@'
0x180048af1  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180048af8  jz      short loc_180048B6A
0x180048afa  mov     r8d, dword ptr [rsp+0A38h+dwBytes]
0x180048aff  lea     rdx, aAddrtmrouteErr_2; "AddRtmRoute : error allocating %d bytes"...
0x180048b06  lea     rcx, [rsp+0A38h+var_848]
0x180048b0e  mov     word ptr [rsp+0A38h+var_848], r13w
0x180048b17  mov     word ptr [rsp+0A38h+var_8C8], r13w
0x180048b20  call    FormatRRASErrorString
0x180048b25  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180048b2c  jz      short loc_180048B6A
0x180048b2e  test    rsi, rsi
0x180048b31  lea     rax, [rsp+0A38h+var_8C8]
0x180048b39  mov     [rsp+0A38h+RouteListHandle], rax
0x180048b3e  lea     r9, [rsp+0A38h+var_8D8]
0x180048b46  cmovnz  r9, rsi
0x180048b4a  mov     qword ptr [rsp+0A38h+TimeToLive], r13
0x180048b4f  lea     r8, [rsp+0A38h+var_848]
0x180048b57  lea     rdx, RasRtrMgrParamTraceError
0x180048b5e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180048b65  call    McTemplateU0zjzz_EventWriteTransfer
0x180048b6a  mov     ebx, 8
0x180048b6f  mov     rcx, cs:IPRouterHeap; hHeap
0x180048b76  mov     r8, r12; lpMem
0x180048b79  xor     edx, edx; dwFlags
0x180048b7b  call    cs:__imp_HeapFree
0x180048b81  mov     eax, ebx
0x180048b83  jmp     loc_1800499DE
0x180048b88  mov     rbx, qword ptr [rsp+0A38h+var_9D0]
0x180048b8d  test    r14d, r14d
0x180048b90  jz      short loc_180048BA9
0x180048b92  mov     eax, [rbx+0Ch]
0x180048b95  mov     dword ptr [rsp+0A38h+pNetAddress.AddrBits], eax
0x180048b9c  mov     dword ptr [rsp+0A38h+pNetAddress.AddressFamily], 200002h
0x180048ba7  jmp     short loc_180048BE1
0x180048ba9  movups  xmm0, xmmword ptr [rbx+14h]
0x180048bad  mov     eax, 17h
0x180048bb2  lea     rdx, [rsp+0A38h+Address]; Address
0x180048bba  lea     rcx, [rsp+0A38h+pNetAddress]; pNetAddress
0x180048bc2  mov     [rsp+0A38h+pNetAddress.AddressFamily], ax
0x180048bca  movdqu  xmmword ptr [rsp+0A38h+Address.u], xmm0
0x180048bd3  lea     r9d, [rax-7]; dwAddressSize
0x180048bd7  lea     r8d, [rax+69h]; dwLength
0x180048bdb  call    cs:__imp_RtmConvertIpv6AddressAndLengthToNetAddress
0x180048be1  mov     eax, [rbx+30h]
0x180048be4  lea     r9, [rsp+0A38h+ChangeFlags]; ChangeFlags
0x180048be9  lea     r8, [rsp+0A38h+NextHopHandle]; NextHopHandle
0x180048bf1  mov     dword ptr [rsp+0A38h+var_958], eax
0x180048bf8  lea     rdx, [rsp+0A38h+pNetAddress]; NextHopInfo
0x180048c00  mov     qword ptr [rsp+0A38h+var_958+8], rdi
0x180048c08  mov     rcx, r15; RtmRegHandle
0x180048c0b  mov     word ptr [rsp+0A38h+var_958+6], r13w
0x180048c14  mov     [rsp+0A38h+var_948], r13
0x180048c1c  mov     [rsp+0A38h+NextHopHandle], r13
0x180048c24  call    cs:__imp_RtmAddNextHop
0x180048c2a  mov     edi, eax
0x180048c2c  test    eax, eax
0x180048c2e  jnz     loc_1800499B3
0x180048c34  test    r14d, r14d
0x180048c37  jz      loc_180048DB8
0x180048c3d  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180048c44  lea     r13, RasRtrMgrParamTraceError
0x180048c4b  mov     r14b, 40h ; '@'
0x180048c4e  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180048c55  test    r14b, al
0x180048c58  jz      loc_180048F3D
0x180048c5e  mov     r8, qword ptr [rsp+0A38h+var_9D0]
0x180048c63  xor     eax, eax
0x180048c65  mov     word ptr [rsp+0A38h+var_848], ax
0x180048c6d  mov     word ptr [rsp+0A38h+var_8C8], ax
0x180048c75  movzx   ecx, byte ptr [r8+3]
0x180048c7a  movzx   edx, byte ptr [r8+2]
0x180048c7f  movzx   r10d, byte ptr [r8+7]
0x180048c84  movzx   r11d, byte ptr [r8+6]
0x180048c89  movzx   ebx, byte ptr [r8+5]
0x180048c8e  movzx   eax, byte ptr [r8+4]
0x180048c93  movzx   r9d, byte ptr [r8+1]
0x180048c98  movzx   r8d, byte ptr [r8]
0x180048c9c  mov     dword ptr [rsp+0A38h+var_9F0], r10d
0x180048ca1  mov     dword ptr [rsp+0A38h+var_9F8], r11d
0x180048ca6  mov     dword ptr [rsp+0A38h+NotifyHandle], ebx
0x180048caa  mov     [rsp+0A38h+NotifyType], eax
0x180048cae  mov     dword ptr [rsp+0A38h+RouteListHandle], ecx
0x180048cb2  lea     rcx, [rsp+0A38h+var_848]
0x180048cba  mov     [rsp+0A38h+TimeToLive], edx
0x180048cbe  lea     rdx, aRouteToDDDDDDD_0; "Route to %d.%d.%d.%d/%d.%d.%d.%d"
0x180048cc5  call    FormatRRASErrorString
0x180048cca  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180048cd1  test    r14b, al
0x180048cd4  jz      loc_180048F3D
0x180048cda  lea     rax, [rsp+0A38h+var_8C8]
0x180048ce2  test    rsi, rsi
0x180048ce5  mov     [rsp+0A38h+RouteListHandle], rax
0x180048cea  lea     r9, [rsp+0A38h+var_8D8]
0x180048cf2  cmovnz  r9, rsi
0x180048cf6  mov     qword ptr [rsp+0A38h+TimeToLive], 0
0x180048cff  lea     r8, [rsp+0A38h+var_848]
0x180048d07  mov     rdx, r13
0x180048d0a  mov     rcx, r15
0x180048d0d  call    McTemplateU0zjzz_EventWriteTransfer
0x180048d12  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180048d19  test    r14b, al
0x180048d1c  jz      loc_180048F3D
0x180048d22  mov     ecx, [rsp+0A38h+DestMarked]
0x180048d29  xor     eax, eax
0x180048d2b  mov     word ptr [rsp+0A38h+var_848], ax
0x180048d33  mov     edi, ecx
0x180048d35  mov     word ptr [rsp+0A38h+var_8C8], ax
0x180048d3d  mov     eax, ecx
0x180048d3f  shr     eax, 10h
0x180048d42  movzx   ebx, al
0x180048d45  mov     eax, ecx
0x180048d47  shr     eax, 8
0x180048d4a  movzx   r11d, al
0x180048d4e  mov     rax, qword ptr [rsp+0A38h+var_9D0]
0x180048d53  movzx   ecx, cl
0x180048d56  shr     edi, 18h
0x180048d59  movzx   edx, byte ptr [rax+0Fh]
0x180048d5d  movzx   r10d, byte ptr [rax+0Eh]
0x180048d62  movzx   r9d, byte ptr [rax+0Dh]
0x180048d67  movzx   r8d, byte ptr [rax+0Ch]
0x180048d6c  mov     rax, [rsp+0A38h+NextHopHandle]
0x180048d74  mov     [rsp+0A38h+var_9E0], rax
0x180048d79  mov     rax, qword ptr [rsp+0A38h+var_9D0]
0x180048d7e  mov     eax, [rax+30h]
0x180048d81  mov     [rsp+0A38h+var_9E8], eax
0x180048d85  mov     dword ptr [rsp+0A38h+var_9F0], edi
0x180048d89  mov     dword ptr [rsp+0A38h+var_9F8], ebx
0x180048d8d  mov     dword ptr [rsp+0A38h+NotifyHandle], r11d
0x180048d92  mov     [rsp+0A38h+NotifyType], ecx
0x180048d96  lea     rcx, [rsp+0A38h+var_848]
0x180048d9e  mov     dword ptr [rsp+0A38h+RouteListHandle], edx
0x180048da2  lea     rdx, aNextHopDDDDDDD; "Next Hop %d.%d.%d.%d/%d.%d.%d.%d, If 0x"...
0x180048da9  mov     [rsp+0A38h+TimeToLive], r10d
0x180048dae  call    FormatRRASErrorString
0x180048db3  jmp     loc_180048EFC
0x180048db8  xor     edx, edx; Val
0x180048dba  lea     rcx, [rsp+0A38h+var_898]; void *
0x180048dc2  lea     r8d, [rdx+41h]; Size
0x180048dc6  call    memset_0
0x180048dcb  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180048dd2  lea     r13, RasRtrMgrParamTraceError
0x180048dd9  mov     r14b, 40h ; '@'
0x180048ddc  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180048de3  test    r14b, al
0x180048de6  jz      loc_180048F3D
0x180048dec  movups  xmm0, xmmword ptr [rbx]
0x180048def  mov     ebx, [rbx+10h]
0x180048df2  lea     rdx, [rsp+0A38h+var_898]
0x180048dfa  xor     eax, eax
0x180048dfc  lea     rcx, [rsp+0A38h+Address]
0x180048e04  movdqu  xmmword ptr [rsp+0A38h+Address.u], xmm0
0x180048e0d  mov     word ptr [rsp+0A38h+var_848], ax
0x180048e15  mov     word ptr [rsp+0A38h+var_8C8], ax
0x180048e1d  call    GetIpv6StringFromAddress
0x180048e22  mov     r8, rax
0x180048e25  lea     rdx, aRouteToHsD; "Route to %hs/%d"
0x180048e2c  mov     r9d, ebx
0x180048e2f  lea     rcx, [rsp+0A38h+var_848]
0x180048e37  call    FormatRRASErrorString
0x180048e3c  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180048e43  test    r14b, al
0x180048e46  jz      short loc_180048E87
0x180048e48  test    rsi, rsi
0x180048e4b  lea     rax, [rsp+0A38h+var_8C8]
0x180048e53  mov     [rsp+0A38h+RouteListHandle], rax
0x180048e58  lea     r9, [rsp+0A38h+var_8D8]
0x180048e60  cmovnz  r9, rsi
0x180048e64  mov     qword ptr [rsp+0A38h+TimeToLive], 0
0x180048e6d  lea     r8, [rsp+0A38h+var_848]
0x180048e75  mov     rdx, r13
0x180048e78  mov     rcx, r15
0x180048e7b  call    McTemplateU0zjzz_EventWriteTransfer
0x180048e80  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180048e87  mov     rbx, qword ptr [rsp+0A38h+var_9D0]
0x180048e8c  test    r14b, al
0x180048e8f  jz      loc_180048F3D
0x180048e95  movups  xmm0, xmmword ptr [rbx+14h]
0x180048e99  mov     ebx, [rbx+30h]
0x180048e9c  lea     rdx, [rsp+0A38h+var_898]
0x180048ea4  xor     eax, eax
0x180048ea6  lea     rcx, [rsp+0A38h+Address]
0x180048eae  movdqu  xmmword ptr [rsp+0A38h+Address.u], xmm0
0x180048eb7  mov     word ptr [rsp+0A38h+var_848], ax
0x180048ebf  mov     word ptr [rsp+0A38h+var_8C8], ax
0x180048ec7  call    GetIpv6StringFromAddress
0x180048ecc  mov     r9d, [rsp+0A38h+DestMarked]
0x180048ed4  lea     rdx, aNextHopHsDIf0x; "Next Hop %hs/%d, If 0x%x, handle is 0x%"...
0x180048edb  mov     r8, rax
0x180048ede  lea     rcx, [rsp+0A38h+var_848]
0x180048ee6  mov     rax, [rsp+0A38h+NextHopHandle]
0x180048eee  mov     [rsp+0A38h+RouteListHandle], rax
0x180048ef3  mov     [rsp+0A38h+TimeToLive], ebx
0x180048ef7  call    FormatRRASErrorString
0x180048efc  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
  ... truncated ...
```

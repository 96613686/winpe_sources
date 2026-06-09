# BlockConvertRoutesToStatic

- ea: `0x180049a08`
- end: `0x18004a11a`
- name: `BlockConvertRoutesToStatic`
- size: `1810`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003fc84`

## callees

- `0x180011790`
- `0x180049a08`
- `0x180051ef8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180049bd3`
- `KERNEL32!SetLastError` at `0x18004a0e8`
- `KERNEL32!SetLastError` at `0x180049bd3`
- `KERNEL32!SetLastError` at `0x18004a0e8`
- `KERNEL32!HeapFree` at `0x180049bcb`
- `KERNEL32!HeapFree` at `0x180049c73`
- `KERNEL32!HeapFree` at `0x180049d10`
- `KERNEL32!HeapFree` at `0x180049ddc`
- `KERNEL32!HeapFree` at `0x180049dee`
- `KERNEL32!HeapFree` at `0x180049e00`
- `KERNEL32!HeapFree` at `0x18004a067`
- `KERNEL32!HeapFree` at `0x18004a079`
- `KERNEL32!HeapFree` at `0x18004a08b`
- `KERNEL32!HeapFree` at `0x180049bcb`
- `KERNEL32!HeapFree` at `0x180049c73`
- `KERNEL32!HeapFree` at `0x180049d10`
- `KERNEL32!HeapFree` at `0x180049ddc`
- `KERNEL32!HeapFree` at `0x180049dee`
- `KERNEL32!HeapFree` at `0x180049e00`
- `KERNEL32!HeapFree` at `0x18004a067`
- `KERNEL32!HeapFree` at `0x18004a079`
- `KERNEL32!HeapFree` at `0x18004a08b`
- `KERNEL32!HeapAlloc` at `0x180049adb`
- `KERNEL32!HeapAlloc` at `0x180049bf1`
- `KERNEL32!HeapAlloc` at `0x180049c8a`
- `KERNEL32!HeapAlloc` at `0x180049adb`
- `KERNEL32!HeapAlloc` at `0x180049bf1`
- `KERNEL32!HeapAlloc` at `0x180049c8a`
- `rtm!RtmDeleteRouteToDest` at `0x180049fe3`
- `rtm!RtmDeleteRouteToDest` at `0x180049fe3`
- `rtm!RtmReleaseRoutes` at `0x18004a02d`
- `rtm!RtmReleaseRoutes` at `0x18004a02d`
- `rtm!RtmGetEnumRoutes` at `0x180049e2b`
- `rtm!RtmGetEnumRoutes` at `0x180049e2b`
- `rtm!RtmCreateRouteEnum` at `0x180049d52`
- `rtm!RtmCreateRouteEnum` at `0x180049d52`
- `rtm!RtmDeleteEnumHandle` at `0x18004a055`
- `rtm!RtmDeleteEnumHandle` at `0x18004a055`
- `rtm!RtmReleaseRouteInfo` at `0x18004a015`
- `rtm!RtmReleaseRouteInfo` at `0x18004a015`
- `rtm!RtmReleaseNextHopInfo` at `0x180049f15`
- `rtm!RtmReleaseNextHopInfo` at `0x180049f78`
- `rtm!RtmReleaseNextHopInfo` at `0x180049f15`
- `rtm!RtmReleaseNextHopInfo` at `0x180049f78`
- `rtm!RtmGetNextHopInfo` at `0x180049edb`
- `rtm!RtmGetNextHopInfo` at `0x180049f35`
- `rtm!RtmGetNextHopInfo` at `0x180049edb`
- `rtm!RtmGetNextHopInfo` at `0x180049f35`
- `rtm!RtmGetEntityInfo` at `0x180049e7a`
- `rtm!RtmGetEntityInfo` at `0x180049e7a`
- `rtm!RtmGetRouteInfo` at `0x180049e5c`
- `rtm!RtmGetRouteInfo` at `0x180049e5c`
- `rtm!RtmAddRouteToDest` at `0x180049fc8`
- `rtm!RtmAddRouteToDest` at `0x180049fc8`
- `rtm!RtmReleaseNextHops` at `0x18004a004`
- `rtm!RtmReleaseNextHops` at `0x18004a004`
- `rtm!RtmAddNextHop` at `0x180049efb`
- `rtm!RtmAddNextHop` at `0x180049f59`
- `rtm!RtmAddNextHop` at `0x180049efb`
- `rtm!RtmAddNextHop` at `0x180049f59`
- `iprtprio!ComputeRouteMetric` at `0x180049ebc`
- `iprtprio!ComputeRouteMetric` at `0x180049ebc`

## pseudocode

```c
__int64 __fastcall BlockConvertRoutesToStatic(__int64 a1, ULONG a2, int a3, __int64 a4)
{
  unsigned __int64 v6; // rax
  RTM_ENTITY_HANDLE v7; // rbx
  UINT v8; // edi
  struct _RTM_ROUTE_INFO *v9; // r15
  __int128 *v10; // r9
  DWORD v11; // ebx
  DWORD v12; // edi
  __int128 *v13; // r9
  SIZE_T v15; // r12
  struct _RTM_ROUTE_INFO *v16; // rdi
  __int128 *v17; // r9
  struct _RTM_ROUTE_INFO *v18; // r8
  struct _RTM_ROUTE_INFO *v19; // r14
  __int128 *v20; // r9
  DWORD v21; // eax
  DWORD v22; // r12d
  __int128 *v23; // r9
  unsigned int v24; // r12d
  DWORD EnumRoutes; // eax
  unsigned int v26; // r13d
  HANDLE *v27; // rsi
  HANDLE v28; // rdx
  RTM_ENTITY_HANDLE RouteOwner; // rdx
  UINT v30; // esi
  __int64 v31; // rcx
  DWORD v32; // eax
  int v33; // ecx
  __int128 *v34; // r9
  SIZE_T dwBytes; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int NumRoutes; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v37; // [rsp+5Ch] [rbp-A4h]
  HANDLE NextHopHandle; // [rsp+60h] [rbp-A0h] BYREF
  int v39; // [rsp+68h] [rbp-98h]
  RTM_ROUTE_HANDLE *v40; // [rsp+70h] [rbp-90h]
  HANDLE EnumHandle; // [rsp+78h] [rbp-88h] BYREF
  __int128 v42; // [rsp+80h] [rbp-80h] BYREF
  struct _RTM_NET_ADDRESS DestAddress; // [rsp+90h] [rbp-70h] BYREF
  struct _RTM_NEXTHOP_INFO NextHopInfo; // [rsp+A8h] [rbp-58h] BYREF
  struct _RTM_ENTITY_INFO EntityInfo; // [rsp+E0h] [rbp-20h] BYREF
  int v46; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v47; // [rsp+F4h] [rbp-Ch]
  __int128 v48; // [rsp+104h] [rbp+4h]
  int v49; // [rsp+114h] [rbp+14h]
  int v50; // [rsp+120h] [rbp+20h] BYREF
  char v51[2044]; // [rsp+124h] [rbp+24h] BYREF

  v39 = a3;
  EnumHandle = 0;
  NextHopHandle = 0;
  NumRoutes = 0;
  dwBytes = 0;
  EntityInfo = 0;
  v50 = 0;
  memset(&DestAddress, 0, sizeof(DestAddress));
  memset(&NextHopInfo, 0, 52);
  memset_0(v51, 0, sizeof(v51));
  v46 = 0;
  v49 = 0;
  v6 = 8LL * g_rtmProfile.MaxHandlesInEnum;
  v47 = 0;
  v48 = 0;
  v42 = 0;
  if ( v6 > 0xFFFFFFFF )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v46) = 0;
      v34 = &v42;
      if ( a4 != -688 )
        LODWORD(v34) = a4 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)L"BlockConvertRoutesToStatic: Integer Overflow",
        (_DWORD)v34,
        *(_QWORD *)(a4 + 72),
        (__int64)&v46);
    }
    v11 = 534;
    goto LABEL_71;
  }
  v7 = g_hAutoStaticRoute;
  v8 = 8 * g_rtmProfile.MaxHandlesInEnum;
  v9 = (struct _RTM_ROUTE_INFO *)HeapAlloc(IPRouterHeap, 0, (unsigned int)v6);
  if ( !v9 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v50) = 0;
      LOWORD(v46) = 0;
      FormatRRASErrorString(&v50, L"BlockConvertRoutesToStatic : error allocating %d bytes for route handes", v8);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v10 = &v42;
        if ( a4 != -688 )
          LODWORD(v10) = a4 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v50,
          (_DWORD)v10,
          *(_QWORD *)(a4 + 72),
          (__int64)&v46);
      }
    }
    goto LABEL_8;
  }
  v12 = RTMSIZEOFROUTEINFO(g_rtmProfile.MaxNextHopsInRoute, &dwBytes);
  if ( v12 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v46) = 0;
      v13 = &v42;
      if ( a4 != -688 )
        LODWORD(v13) = a4 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrMgrParamTraceError,
        (unsigned int)L"BlockConvertRoutesToStatic : Arithmatic Overflow error allocating memory for route info",
        (_DWORD)v13,
        *(_QWORD *)(a4 + 72),
        (__int64)&v46);
    }
    HeapFree(IPRouterHeap, 0, v9);
    SetLastError(v12);
    return v12;
  }
  v15 = (unsigned int)dwBytes;
  v16 = (struct _RTM_ROUTE_INFO *)HeapAlloc(IPRouterHeap, 0, (unsigned int)dwBytes);
  if ( !v16 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v50) = 0;
      LOWORD(v46) = 0;
      FormatRRASErrorString(
        &v50,
        L"BlockConvertRoutesToStatic : error allocating %d bytes for route info",
        (unsigned int)v15);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v17 = &v42;
        if ( a4 != -688 )
          LODWORD(v17) = a4 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v50,
          (_DWORD)v17,
          *(_QWORD *)(a4 + 72),
          (__int64)&v46);
      }
    }
    v18 = v9;
LABEL_22:
    HeapFree(IPRouterHeap, 0, v18);
LABEL_8:
    v11 = 8;
LABEL_71:
    SetLastError(v11);
    return v11;
  }
  v19 = (struct _RTM_ROUTE_INFO *)HeapAlloc(IPRouterHeap, 0, v15);
  if ( !v19 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v50) = 0;
      LOWORD(v46) = 0;
      FormatRRASErrorString(
        &v50,
        L"BlockConvertRoutesToStatic : error allocating %d bytes for route info",
        (unsigned int)v15);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v20 = &v42;
        if ( a4 != -688 )
          LODWORD(v20) = a4 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v50,
          (_DWORD)v20,
          *(_QWORD *)(a4 + 72),
          (__int64)&v46);
      }
    }
    HeapFree(IPRouterHeap, 0, v9);
    v18 = v16;
    goto LABEL_22;
  }
  v21 = RtmCreateRouteEnum(v7, 0, 0, 0, 0, 0x10u, 0, a2, &EnumHandle);
  v22 = v21;
  if ( v21 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v50) = 0;
      LOWORD(v46) = 0;
      FormatRRASErrorString(&v50, L"BlockConvertRoutesToStatic: Error %d creating handle for %d\n", v21, v7);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v23 = &v42;
        if ( a4 != -688 )
          LODWORD(v23) = a4 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v50,
          (_DWORD)v23,
          *(_QWORD *)(a4 + 72),
          (__int64)&v46);
      }
    }
    HeapFree(IPRouterHeap, 0, v9);
    HeapFree(IPRouterHeap, 0, v16);
    HeapFree(IPRouterHeap, 0, v19);
    return v22;
  }
  else
  {
    v24 = 0;
    do
    {
      NumRoutes = g_rtmProfile.MaxHandlesInEnum;
      EnumRoutes = RtmGetEnumRoutes(v7, EnumHandle, &NumRoutes, &v9->DestHandle);
      v26 = 0;
      v37 = EnumRoutes;
      if ( NumRoutes )
      {
        do
        {
          v27 = &v9->DestHandle + v26;
          v28 = *v27;
          v40 = v27;
          if ( RtmGetRouteInfo(v7, v28, v16, &DestAddress) )
            goto LABEL_61;
          RouteOwner = v16->RouteOwner;
          LODWORD(dwBytes) = 0;
          if ( !RtmGetEntityInfo(v7, RouteOwner, &EntityInfo) && EntityInfo.EntityId.EntityProtocolId == v39 )
          {
            *(_OWORD *)&v19->DestHandle = *(_OWORD *)&v16->DestHandle;
            *(_OWORD *)&v19->Neighbour = *(_OWORD *)&v16->Neighbour;
            *(_OWORD *)&v19->PrefInfo.Preference = *(_OWORD *)&v16->PrefInfo.Preference;
            v19->NextHopsList = v16->NextHopsList;
            v19->PrefInfo.Preference = ComputeRouteMetric(10002);
            if ( v16->Neighbour )
            {
              v19->Neighbour = 0;
              if ( !RtmGetNextHopInfo(v7, v16->Neighbour, &NextHopInfo) )
              {
                NextHopHandle = 0;
                if ( !RtmAddNextHop(v7, &NextHopInfo, &NextHopHandle, (PRTM_NEXTHOP_CHANGE_FLAGS)&dwBytes + 1) )
                  v19->Neighbour = NextHopHandle;
                RtmReleaseNextHopInfo(v7, &NextHopInfo);
              }
            }
            v30 = 0;
            if ( v16->NextHopsList.NumNextHops )
            {
              do
              {
                if ( !RtmGetNextHopInfo(v7, v16->NextHopsList.NextHops[v24], &NextHopInfo) )
                {
                  NextHopHandle = 0;
                  if ( !RtmAddNextHop(v7, &NextHopInfo, &NextHopHandle, (PRTM_NEXTHOP_CHANGE_FLAGS)&dwBytes + 1) )
                  {
                    v31 = v30++;
                    v19->NextHopsList.NextHops[v31] = NextHopHandle;
                  }
                  RtmReleaseNextHopInfo(v7, &NextHopInfo);
                }
                ++v24;
              }
              while ( v24 < v16->NextHopsList.NumNextHops );
            }
            v24 = 0;
            v19->NextHopsList.NumNextHops = v30;
            if ( v30 )
            {
              HIDWORD(dwBytes) = 0;
              if ( !RtmAddRouteToDest(
                      v7,
                      0,
                      &DestAddress,
                      v19,
                      0xFFFFFFFF,
                      0,
                      0,
                      0,
                      (PRTM_ROUTE_CHANGE_FLAGS)&dwBytes + 1) )
              {
                v32 = RtmDeleteRouteToDest(v16->RouteOwner, *v40, (PRTM_ROUTE_CHANGE_FLAGS)&dwBytes + 1);
                v33 = dwBytes;
                if ( !v32 )
                  v33 = 1;
                LODWORD(dwBytes) = v33;
              }
              RtmReleaseNextHops(v7, v30, v19->NextHopsList.NextHops);
            }
            v27 = v40;
          }
          RtmReleaseRouteInfo(v7, v16);
          if ( !(_DWORD)dwBytes )
LABEL_61:
            RtmReleaseRoutes(v7, 1u, v27);
          ++v26;
        }
        while ( v26 < NumRoutes );
        EnumRoutes = v37;
      }
    }
    while ( !EnumRoutes );
    RtmDeleteEnumHandle(v7, EnumHandle);
    HeapFree(IPRouterHeap, 0, v9);
    HeapFree(IPRouterHeap, 0, v16);
    HeapFree(IPRouterHeap, 0, v19);
    return 0;
  }
}

```

## disassembly

```asm
0x180049a08  mov     [rsp-8+arg_0], rbx
0x180049a0d  push    rbp
0x180049a0e  push    rsi
0x180049a0f  push    rdi
0x180049a10  push    r12
0x180049a12  push    r13
0x180049a14  push    r14
0x180049a16  push    r15
0x180049a18  lea     rbp, [rsp-830h]
0x180049a20  sub     rsp, 930h
0x180049a27  mov     rax, cs:__security_cookie
0x180049a2e  xor     rax, rsp
0x180049a31  mov     [rbp+860h+var_40], rax
0x180049a38  xor     r14d, r14d
0x180049a3b  mov     [rsp+960h+var_8F8], r8d
0x180049a40  xorps   xmm0, xmm0
0x180049a43  mov     [rsp+960h+EnumHandle], r14
0x180049a48  xor     eax, eax
0x180049a4a  mov     [rsp+960h+NextHopHandle], r14
0x180049a4f  mov     r13d, edx
0x180049a52  mov     dword ptr [rbp+860h+DestAddress.AddrBits+0Ch], eax
0x180049a55  xorps   xmm1, xmm1
0x180049a58  mov     dword ptr [rbp+860h+NextHopInfo.RemoteNextHop], eax
0x180049a5b  xor     edx, edx; Val
0x180049a5d  mov     [rsp+960h+NumRoutes], r14d
0x180049a62  mov     r8d, 7FCh; Size
0x180049a68  mov     dword ptr [rsp+960h+dwBytes+4], r14d
0x180049a6d  lea     rcx, [rbp+860h+var_83C]; void *
0x180049a71  mov     dword ptr [rsp+960h+dwBytes], r14d
0x180049a76  movups  xmmword ptr [rbp+860h+EntityInfo.RtmInstanceId], xmm0
0x180049a7a  mov     [rbp+860h+var_840], r14d
0x180049a7e  mov     rsi, r9
0x180049a81  movups  xmmword ptr [rbp+860h+DestAddress.AddressFamily], xmm1
0x180049a85  movups  xmmword ptr [rbp+860h+NextHopInfo.NextHopAddress.AddressFamily], xmm0
0x180049a89  movups  xmmword ptr [rbp+860h+NextHopInfo.NextHopAddress.AddrBits+0Ch], xmm0
0x180049a8d  movups  xmmword ptr [rbp+860h+NextHopInfo.InterfaceIndex], xmm0
0x180049a91  call    memset_0
0x180049a96  xor     eax, eax
0x180049a98  mov     [rbp+860h+var_870], r14d
0x180049a9c  xorps   xmm0, xmm0
0x180049a9f  mov     [rbp+860h+var_84C], eax
0x180049aa2  mov     eax, cs:g_rtmProfile.MaxHandlesInEnum
0x180049aa8  mov     ecx, 0FFFFFFFFh
0x180049aad  shl     rax, 3
0x180049ab1  movups  [rbp+860h+var_86C], xmm0
0x180049ab5  movups  [rbp+860h+var_85C], xmm0
0x180049ab9  movups  [rbp+860h+var_8E0], xmm0
0x180049abd  cmp     rax, rcx
0x180049ac0  ja      loc_18004A095
0x180049ac6  mov     rcx, cs:IPRouterHeap; hHeap
0x180049acd  xor     edx, edx; dwFlags
0x180049acf  mov     rbx, cs:g_hAutoStaticRoute
0x180049ad6  mov     r8d, eax; dwBytes
0x180049ad9  mov     edi, eax
0x180049adb  call    cs:__imp_HeapAlloc
0x180049ae1  mov     r15, rax
0x180049ae4  test    rax, rax
0x180049ae7  jnz     short loc_180049B5D
0x180049ae9  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180049af0  jz      short loc_180049B53
0x180049af2  mov     r8d, edi
0x180049af5  mov     word ptr [rbp+860h+var_840], r14w
0x180049afa  lea     rdx, aBlockconvertro_3; "BlockConvertRoutesToStatic : error allo"...
0x180049b01  mov     word ptr [rbp+860h+var_870], r14w
0x180049b06  lea     rcx, [rbp+860h+var_840]
0x180049b0a  call    FormatRRASErrorString
0x180049b0f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180049b16  jz      short loc_180049B53
0x180049b18  lea     rax, [rsi+2B0h]
0x180049b1f  test    rax, rax
0x180049b22  lea     r9, [rbp+860h+var_8E0]
0x180049b26  lea     r8, [rbp+860h+var_840]
0x180049b2a  cmovnz  r9, rax
0x180049b2e  lea     rdx, RasRtrMgrParamTraceError
0x180049b35  lea     rax, [rbp+860h+var_870]
0x180049b39  mov     qword ptr [rsp+960h+MatchingFlags], rax
0x180049b3e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180049b45  mov     rax, [rsi+48h]
0x180049b49  mov     [rsp+960h+StartDest], rax
0x180049b4e  call    McTemplateU0zjzz_EventWriteTransfer
0x180049b53  mov     ebx, 8
0x180049b58  jmp     loc_18004A0E6
0x180049b5d  mov     ecx, cs:g_rtmProfile.MaxNextHopsInRoute
0x180049b63  lea     rdx, [rsp+960h+dwBytes]
0x180049b68  call    RTMSIZEOFROUTEINFO
0x180049b6d  mov     edi, eax
0x180049b6f  test    eax, eax
0x180049b71  jz      short loc_180049BE0
0x180049b73  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180049b7a  jz      short loc_180049BBF
0x180049b7c  lea     rcx, [rsi+2B0h]
0x180049b83  mov     word ptr [rbp+860h+var_870], r14w
0x180049b88  test    rcx, rcx
0x180049b8b  lea     rax, [rbp+860h+var_870]
0x180049b8f  mov     qword ptr [rsp+960h+MatchingFlags], rax
0x180049b94  lea     r9, [rbp+860h+var_8E0]
0x180049b98  mov     rax, [rsi+48h]
0x180049b9c  lea     r8, aBlockconvertro_0; "BlockConvertRoutesToStatic : Arithmatic"...
0x180049ba3  cmovnz  r9, rcx
0x180049ba7  mov     [rsp+960h+StartDest], rax
0x180049bac  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180049bb3  lea     rdx, RasRtrMgrParamTraceError
0x180049bba  call    McTemplateU0zjzz_EventWriteTransfer
0x180049bbf  mov     rcx, cs:IPRouterHeap; hHeap
0x180049bc6  mov     r8, r15; lpMem
0x180049bc9  xor     edx, edx; dwFlags
0x180049bcb  call    cs:__imp_HeapFree
0x180049bd1  mov     ecx, edi; dwErrCode
0x180049bd3  call    cs:__imp_SetLastError
0x180049bd9  mov     eax, edi
0x180049bdb  jmp     loc_18004A0F0
0x180049be0  mov     r12d, dword ptr [rsp+960h+dwBytes]
0x180049be5  xor     edx, edx; dwFlags
0x180049be7  mov     rcx, cs:IPRouterHeap; hHeap
0x180049bee  mov     r8d, r12d; dwBytes
0x180049bf1  call    cs:__imp_HeapAlloc
0x180049bf7  mov     rdi, rax
0x180049bfa  test    rax, rax
0x180049bfd  jnz     short loc_180049C7E
0x180049bff  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180049c06  jz      short loc_180049C67
0x180049c08  mov     r8d, r12d
0x180049c0b  mov     word ptr [rbp+860h+var_840], ax
0x180049c0f  lea     rdx, aBlockconvertro; "BlockConvertRoutesToStatic : error allo"...
0x180049c16  mov     word ptr [rbp+860h+var_870], ax
0x180049c1a  lea     rcx, [rbp+860h+var_840]
0x180049c1e  call    FormatRRASErrorString
0x180049c23  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180049c2a  jz      short loc_180049C67
0x180049c2c  lea     rax, [rsi+2B0h]
0x180049c33  test    rax, rax
0x180049c36  lea     r9, [rbp+860h+var_8E0]
0x180049c3a  lea     r8, [rbp+860h+var_840]
0x180049c3e  cmovnz  r9, rax
0x180049c42  lea     rdx, RasRtrMgrParamTraceError
0x180049c49  lea     rax, [rbp+860h+var_870]
0x180049c4d  mov     qword ptr [rsp+960h+MatchingFlags], rax
0x180049c52  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180049c59  mov     rax, [rsi+48h]
0x180049c5d  mov     [rsp+960h+StartDest], rax
0x180049c62  call    McTemplateU0zjzz_EventWriteTransfer
0x180049c67  mov     r8, r15; lpMem
0x180049c6a  mov     rcx, cs:IPRouterHeap; hHeap
0x180049c71  xor     edx, edx; dwFlags
0x180049c73  call    cs:__imp_HeapFree
0x180049c79  jmp     loc_180049B53
0x180049c7e  mov     rcx, cs:IPRouterHeap; hHeap
0x180049c85  mov     r8, r12; dwBytes
0x180049c88  xor     edx, edx; dwFlags
0x180049c8a  call    cs:__imp_HeapAlloc
0x180049c90  mov     r14, rax
0x180049c93  test    rax, rax
0x180049c96  jnz     loc_180049D1E
0x180049c9c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180049ca3  jz      short loc_180049D04
0x180049ca5  mov     r8d, r12d
0x180049ca8  mov     word ptr [rbp+860h+var_840], ax
0x180049cac  lea     rdx, aBlockconvertro; "BlockConvertRoutesToStatic : error allo"...
0x180049cb3  mov     word ptr [rbp+860h+var_870], ax
0x180049cb7  lea     rcx, [rbp+860h+var_840]
0x180049cbb  call    FormatRRASErrorString
0x180049cc0  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180049cc7  jz      short loc_180049D04
0x180049cc9  lea     rax, [rsi+2B0h]
0x180049cd0  test    rax, rax
0x180049cd3  lea     r9, [rbp+860h+var_8E0]
0x180049cd7  lea     r8, [rbp+860h+var_840]
0x180049cdb  cmovnz  r9, rax
0x180049cdf  lea     rdx, RasRtrMgrParamTraceError
0x180049ce6  lea     rax, [rbp+860h+var_870]
0x180049cea  mov     qword ptr [rsp+960h+MatchingFlags], rax
0x180049cef  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180049cf6  mov     rax, [rsi+48h]
0x180049cfa  mov     [rsp+960h+StartDest], rax
0x180049cff  call    McTemplateU0zjzz_EventWriteTransfer
0x180049d04  mov     rcx, cs:IPRouterHeap; hHeap
0x180049d0b  mov     r8, r15; lpMem
0x180049d0e  xor     edx, edx; dwFlags
0x180049d10  call    cs:__imp_HeapFree
0x180049d16  mov     r8, rdi
0x180049d19  jmp     loc_180049C6A
0x180049d1e  lea     rax, [rsp+960h+EnumHandle]
0x180049d23  xor     r9d, r9d; EnumFlags
0x180049d26  mov     [rsp+960h+RtmEnumHandle], rax; RtmEnumHandle
0x180049d2b  xor     r8d, r8d; TargetViews
0x180049d2e  mov     [rsp+960h+CriteriaInterface], r13d; CriteriaInterface
0x180049d33  xor     edx, edx; DestHandle
0x180049d35  mov     [rsp+960h+CriteriaRoute], 0; CriteriaRoute
0x180049d3e  mov     rcx, rbx; RtmRegHandle
0x180049d41  mov     [rsp+960h+MatchingFlags], 10h; MatchingFlags
0x180049d49  mov     [rsp+960h+StartDest], 0; StartDest
0x180049d52  call    cs:__imp_RtmCreateRouteEnum
0x180049d58  mov     r12d, eax
0x180049d5b  test    eax, eax
0x180049d5d  jz      loc_180049E0E
0x180049d63  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180049d6a  jz      short loc_180049DD0
0x180049d6c  xor     ecx, ecx
0x180049d6e  lea     rdx, aBlockconvertro_1; "BlockConvertRoutesToStatic: Error %d cr"...
0x180049d75  mov     word ptr [rbp+860h+var_840], cx
0x180049d79  mov     r9, rbx
0x180049d7c  mov     word ptr [rbp+860h+var_870], cx
0x180049d80  mov     r8d, eax
0x180049d83  lea     rcx, [rbp+860h+var_840]
0x180049d87  call    FormatRRASErrorString
0x180049d8c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180049d93  jz      short loc_180049DD0
0x180049d95  lea     rax, [rsi+2B0h]
0x180049d9c  test    rax, rax
0x180049d9f  lea     r9, [rbp+860h+var_8E0]
0x180049da3  lea     r8, [rbp+860h+var_840]
0x180049da7  cmovnz  r9, rax
0x180049dab  lea     rdx, RasRtrMgrParamTraceError
0x180049db2  lea     rax, [rbp+860h+var_870]
0x180049db6  mov     qword ptr [rsp+960h+MatchingFlags], rax
0x180049dbb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180049dc2  mov     rax, [rsi+48h]
0x180049dc6  mov     [rsp+960h+StartDest], rax
0x180049dcb  call    McTemplateU0zjzz_EventWriteTransfer
0x180049dd0  mov     rcx, cs:IPRouterHeap; hHeap
0x180049dd7  mov     r8, r15; lpMem
0x180049dda  xor     edx, edx; dwFlags
0x180049ddc  call    cs:__imp_HeapFree
0x180049de2  mov     rcx, cs:IPRouterHeap; hHeap
0x180049de9  mov     r8, rdi; lpMem
0x180049dec  xor     edx, edx; dwFlags
0x180049dee  call    cs:__imp_HeapFree
0x180049df4  mov     rcx, cs:IPRouterHeap; hHeap
0x180049dfb  mov     r8, r14; lpMem
0x180049dfe  xor     edx, edx; dwFlags
0x180049e00  call    cs:__imp_HeapFree
0x180049e06  mov     eax, r12d
0x180049e09  jmp     loc_18004A0F0
0x180049e0e  xor     r12d, r12d
0x180049e11  mov     eax, cs:g_rtmProfile.MaxHandlesInEnum
0x180049e17  lea     r8, [rsp+960h+NumRoutes]; NumRoutes
0x180049e1c  mov     rdx, [rsp+960h+EnumHandle]; EnumHandle
0x180049e21  mov     r9, r15; RouteHandles
0x180049e24  mov     rcx, rbx; RtmRegHandle
0x180049e27  mov     [rsp+960h+NumRoutes], eax
0x180049e2b  call    cs:__imp_RtmGetEnumRoutes
0x180049e31  mov     r13d, r12d
0x180049e34  mov     [rsp+960h+var_904], eax
0x180049e38  cmp     [rsp+960h+NumRoutes], r12d
0x180049e3d  jbe     loc_18004A045
0x180049e43  mov     ecx, r13d
0x180049e46  lea     r9, [rbp+860h+DestAddress]; DestAddress
0x180049e4a  mov     r8, rdi; RouteInfo
0x180049e4d  lea     rsi, [r15+rcx*8]
0x180049e51  mov     rcx, rbx; RtmRegHandle
0x180049e54  mov     rdx, [rsi]; RouteHandle
0x180049e57  mov     [rsp+960h+var_8F0], rsi
0x180049e5c  call    cs:__imp_RtmGetRouteInfo
0x180049e62  test    eax, eax
0x180049e64  jnz     loc_18004A022
0x180049e6a  mov     rdx, [rdi+8]; EntityHandle
0x180049e6e  lea     r8, [rbp+860h+EntityInfo]; EntityInfo
0x180049e72  mov     rcx, rbx; RtmRegHandle
0x180049e75  mov     dword ptr [rsp+960h+dwBytes], r12d
0x180049e7a  call    cs:__imp_RtmGetEntityInfo
0x180049e80  test    eax, eax
0x180049e82  jnz     loc_18004A00F
0x180049e88  mov     eax, [rsp+960h+var_8F8]
0x180049e8c  cmp     dword ptr [rbp+860h+EntityInfo.EntityId], eax
0x180049e8f  jnz     loc_18004A00F
0x180049e95  movups  xmm0, xmmword ptr [rdi]
0x180049e98  mov     ecx, 2712h
0x180049e9d  movups  xmmword ptr [r14], xmm0
0x180049ea1  movups  xmm1, xmmword ptr [rdi+10h]
0x180049ea5  movups  xmmword ptr [r14+10h], xmm1
0x180049eaa  movups  xmm0, xmmword ptr [rdi+20h]
0x180049eae  movups  xmmword ptr [r14+20h], xmm0
0x180049eb3  movups  xmm1, xmmword ptr [rdi+30h]
0x180049eb7  movups  xmmword ptr [r14+30h], xmm1
0x180049ebc  call    cs:__imp_ComputeRouteMetric
0x180049ec2  mov     [r14+20h], eax
0x180049ec6  cmp     [rdi+10h], r12
0x180049eca  jz      short loc_180049F1B
0x180049ecc  mov     [r14+10h], r12
0x180049ed0  lea     r8, [rbp+860h+NextHopInfo]; NextHopInfo
0x180049ed4  mov     rdx, [rdi+10h]; NextHopHandle
0x180049ed8  mov     rcx, rbx; RtmRegHandle
0x180049edb  call    cs:__imp_RtmGetNextHopInfo
0x180049ee1  test    eax, eax
0x180049ee3  jnz     short loc_180049F1B
0x180049ee5  lea     r9, [rsp+960h+dwBytes+4]; ChangeFlags
0x180049eea  mov     [rsp+960h+NextHopHandle], r12
0x180049eef  lea     r8, [rsp+960h+NextHopHandle]; NextHopHandle
0x180049ef4  mov     rcx, rbx; RtmRegHandle
0x180049ef7  lea     rdx, [rbp+860h+NextHopInfo]; NextHopInfo
0x180049efb  call    cs:__imp_RtmAddNextHop
0x180049f01  test    eax, eax
0x180049f03  jnz     short loc_180049F0E
0x180049f05  mov     rax, [rsp+960h+NextHopHandle]
0x180049f0a  mov     [r14+10h], rax
0x180049f0e  lea     rdx, [rbp+860h+NextHopInfo]; NextHopInfo
0x180049f12  mov     rcx, rbx; RtmRegHandle
0x180049f15  call    cs:__imp_RtmReleaseNextHopInfo
0x180049f1b  xor     eax, eax
0x180049f1d  mov     esi, r12d
  ... truncated ...
```

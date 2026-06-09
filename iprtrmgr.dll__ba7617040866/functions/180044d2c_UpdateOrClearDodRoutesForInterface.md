# UpdateOrClearDodRoutesForInterface

- ea: `0x180044d2c`
- end: `0x1800456ff`
- name: `UpdateOrClearDodRoutesForInterface`
- size: `2515`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002538c`
- `0x1800401a0`

## callees

- `0x180011790`
- `0x18003e45c`
- `0x180040408`
- `0x180044d2c`
- `0x180051ef8`
- `0x180057c48`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800450be`
- `KERNEL32!HeapFree` at `0x180045651`
- `KERNEL32!HeapFree` at `0x180045663`
- `KERNEL32!HeapFree` at `0x1800456cc`
- `KERNEL32!HeapFree` at `0x1800450be`
- `KERNEL32!HeapFree` at `0x180045651`
- `KERNEL32!HeapFree` at `0x180045663`
- `KERNEL32!HeapFree` at `0x1800456cc`
- `KERNEL32!HeapAlloc` at `0x180044f4d`
- `KERNEL32!HeapAlloc` at `0x180044f9c`
- `KERNEL32!HeapAlloc` at `0x18004501e`
- `KERNEL32!HeapAlloc` at `0x180044f4d`
- `KERNEL32!HeapAlloc` at `0x180044f9c`
- `KERNEL32!HeapAlloc` at `0x18004501e`
- `rtm!RtmReleaseRoutes` at `0x180045610`
- `rtm!RtmReleaseRoutes` at `0x180045610`
- `rtm!RtmGetEnumRoutes` at `0x180045228`
- `rtm!RtmGetEnumRoutes` at `0x180045228`
- `rtm!RtmCreateRouteEnum` at `0x180045161`
- `rtm!RtmCreateRouteEnum` at `0x180045161`
- `rtm!RtmDeleteEnumHandle` at `0x180045638`
- `rtm!RtmDeleteEnumHandle` at `0x180045638`
- `rtm!RtmReleaseRouteInfo` at `0x1800455fa`
- `rtm!RtmReleaseRouteInfo` at `0x1800455fa`
- `rtm!RtmGetRouteInfo` at `0x18004543a`
- `rtm!RtmGetRouteInfo` at `0x18004543a`
- `rtm!RtmIsBestRoute` at `0x180045303`
- `rtm!RtmIsBestRoute` at `0x180045303`

## string_xrefs

- `0x180044e0e`: `UpdateOrClearDodRoutesForInterface (If %d) V4=%d`
- `0x180044ef8`: `UpdateOrClearDodRoutesForInterface : Error  Integer overflow %d`
- `0x180044f6d`: `UpdateOrClearDodRoutesForInterface : Error allocating %d bytes for route info`
- `0x180045682`: `UpdateOrClearDodRoutesForInterface: Integer overflow`
- `0x180044fc8`: `UpdateOrClearDodRoutesForInterface : Error allocating %d bytes for route handles`
- `0x180045046`: `UpdateOrClearDodRoutesForInterface : Error allocating %d bytes for dest. address`
- `0x18004518d`: `UpdateOrClearDodRoutesForInterface : Error %d creating enum handle for %ws routes`
- `0x18004524f`: `UpdateOrClearDodRoutesForInterface : Number of %ws routes available for If %d : %d`
- `0x18004546d`: `DeleteDodLoopbackRoutesForInterface(If=%d, AF=%d)`
- `0x180045506`: `DeleteDoDLoopbackRouteToDestination returned %d`

## pseudocode

```c
int __fastcall UpdateOrClearDodRoutesForInterface(__int64 a1, int a2)
{
  ULONG CriteriaInterface; // r13d
  unsigned int v3; // r15d
  char v5; // r9
  __int128 *v6; // r9
  struct _RTM_ROUTE_INFO *v7; // rax
  const wchar_t *v8; // r8
  __int64 *v9; // rdx
  __int128 *v10; // r9
  char v11; // r9
  __int64 v12; // r8
  const wchar_t *v13; // rdx
  struct _RTM_ROUTE_INFO *v14; // rsi
  unsigned __int64 v15; // rax
  UINT v16; // ebx
  PRTM_ROUTE_HANDLE v17; // r14
  const wchar_t *v18; // r8
  __int64 *v19; // rdx
  __int128 *v20; // r9
  PRTM_NET_ADDRESS v21; // r8
  unsigned int v22; // ebx
  __int64 i; // rbx
  RTM_ENTITY_HANDLE v24; // r12
  DWORD v25; // eax
  const wchar_t *v26; // r9
  __int128 *v27; // r9
  DWORD EnumRoutes; // r14d
  const wchar_t *v29; // r8
  __int128 *v30; // r9
  __int64 j; // r13
  DWORD IsBestRoute; // eax
  __int128 *v33; // r9
  __int128 *v34; // r9
  __int128 *v35; // r9
  const wchar_t *v36; // rdx
  __int128 *v37; // r9
  __int128 *v38; // r9
  bool v39; // zf
  __int128 *v40; // r9
  PRTM_NET_ADDRESS StartDest; // [rsp+20h] [rbp-8E8h]
  SIZE_T dwBytes; // [rsp+50h] [rbp-8B8h] BYREF
  DWORD BestInViews; // [rsp+58h] [rbp-8B0h] BYREF
  ULONG v45; // [rsp+5Ch] [rbp-8ACh]
  unsigned int v46; // [rsp+60h] [rbp-8A8h]
  PRTM_ROUTE_HANDLE RouteHandles; // [rsp+68h] [rbp-8A0h]
  PRTM_NET_ADDRESS DestAddress; // [rsp+70h] [rbp-898h]
  int v49; // [rsp+78h] [rbp-890h]
  HANDLE EnumHandle; // [rsp+80h] [rbp-888h] BYREF
  RTM_ENTITY_HANDLE RtmRegHandle[2]; // [rsp+88h] [rbp-880h]
  __int128 v52; // [rsp+98h] [rbp-870h] BYREF
  int v53; // [rsp+A8h] [rbp-860h] BYREF
  __int128 v54; // [rsp+ACh] [rbp-85Ch]
  __int128 v55; // [rsp+BCh] [rbp-84Ch]
  int v56; // [rsp+CCh] [rbp-83Ch]
  int v57; // [rsp+D0h] [rbp-838h] BYREF
  int v58; // [rsp+D4h] [rbp-834h] BYREF

  CriteriaInterface = *(_DWORD *)(a1 + 16);
  v3 = *(_DWORD *)(a1 + 516);
  v49 = a2;
  RtmRegHandle[0] = 0;
  EnumHandle = 0;
  BestInViews = 0;
  dwBytes = 0;
  v57 = 0;
  v45 = CriteriaInterface;
  v46 = v3;
  memset_0(&v58, 0, 0x7FCu);
  v5 = Microsoft_Windows_RRASEnableBits;
  v53 = 0;
  v56 = 0;
  v54 = 0;
  v55 = 0;
  v52 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v57) = 0;
    LOWORD(v53) = 0;
    FormatRRASErrorString(&v57, L"UpdateOrClearDodRoutesForInterface (If %d) V4=%d", CriteriaInterface, v3);
    v5 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v6 = &v52;
      if ( a1 != -688 )
        LODWORD(v6) = a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v57,
        (_DWORD)v6,
        *(_QWORD *)(a1 + 72),
        (__int64)&v53);
      v5 = Microsoft_Windows_RRASEnableBits;
    }
  }
  LODWORD(v7) = *(_DWORD *)(a1 + 144) - 1;
  if ( (unsigned int)v7 <= 1 )
  {
    LODWORD(v7) = RTMSIZEOFROUTEINFO(g_rtmProfile.MaxNextHopsInRoute, &dwBytes);
    if ( (_DWORD)v7 )
    {
      if ( (v11 & 0x40) == 0 )
        return (int)v7;
      v12 = (unsigned int)v7;
      v13 = L"UpdateOrClearDodRoutesForInterface : Error  Integer overflow %d";
      goto LABEL_15;
    }
    v7 = (struct _RTM_ROUTE_INFO *)HeapAlloc(IPRouterHeap, 0, (unsigned int)dwBytes);
    v14 = v7;
    if ( !v7 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        return (int)v7;
      v12 = (unsigned int)dwBytes;
      v13 = L"UpdateOrClearDodRoutesForInterface : Error allocating %d bytes for route info";
LABEL_15:
      LOWORD(v53) = 0;
      LOWORD(v57) = 0;
      LODWORD(v7) = FormatRRASErrorString(&v57, v13, v12);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        return (int)v7;
      v8 = (const wchar_t *)&v57;
      v9 = RasRtrMgrParamTraceError;
      goto LABEL_9;
    }
    v15 = 8LL * g_rtmProfile.MaxHandlesInEnum;
    if ( v15 > 0xFFFFFFFF )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v53) = 0;
        v18 = L"UpdateOrClearDodRoutesForInterface: Integer overflow";
        v19 = RasRtrmgrParamTraceInfo;
        goto LABEL_91;
      }
LABEL_94:
      v21 = (PRTM_NET_ADDRESS)v14;
      goto LABEL_95;
    }
    v16 = 8 * g_rtmProfile.MaxHandlesInEnum;
    RouteHandles = (PRTM_ROUTE_HANDLE)HeapAlloc(IPRouterHeap, 0, (unsigned int)v15);
    v17 = RouteHandles;
    if ( !RouteHandles )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v57) = 0;
        LOWORD(v53) = 0;
        FormatRRASErrorString(
          &v57,
          L"UpdateOrClearDodRoutesForInterface : Error allocating %d bytes for route handles",
          v16);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v18 = (const wchar_t *)&v57;
          v19 = RasRtrMgrParamTraceError;
LABEL_91:
          v40 = &v52;
          if ( a1 != -688 )
            LODWORD(v40) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (_DWORD)v19,
            (_DWORD)v18,
            (_DWORD)v40,
            *(_QWORD *)(a1 + 72),
            (__int64)&v53);
          goto LABEL_94;
        }
      }
      goto LABEL_94;
    }
    DestAddress = (PRTM_NET_ADDRESS)HeapAlloc(IPRouterHeap, 0, 0x14u);
    if ( !DestAddress )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v57) = 0;
        LOWORD(v53) = 0;
        FormatRRASErrorString(
          &v57,
          L"UpdateOrClearDodRoutesForInterface : Error allocating %d bytes for dest. address",
          20);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v20 = &v52;
          if ( a1 != -688 )
            LODWORD(v20) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v57,
            (_DWORD)v20,
            *(_QWORD *)(a1 + 72),
            (__int64)&v53);
        }
      }
      HeapFree(IPRouterHeap, 0, v14);
      v21 = (PRTM_NET_ADDRESS)v17;
      goto LABEL_95;
    }
    v22 = v3 != 0 ? 0xFFFFFFCA : 0;
    RtmRegHandle[0] = (RTM_ENTITY_HANDLE)GetRtmRegistrationHandle((struct _GUID *)(a1 + 688), v22 + 87, 0x2716u);
    RtmRegHandle[1] = (RTM_ENTITY_HANDLE)GetRtmRegistrationHandle((struct _GUID *)(a1 + 688), v22 + 87, 0x2712u);
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      LODWORD(dwBytes) = i;
      if ( (unsigned int)i >= 2 )
      {
        HeapFree(IPRouterHeap, 0, v14);
        HeapFree(IPRouterHeap, 0, v17);
        v21 = DestAddress;
LABEL_95:
        LODWORD(v7) = HeapFree(IPRouterHeap, 0, v21);
        return (int)v7;
      }
      v24 = RtmRegHandle[i];
      v25 = RtmCreateRouteEnum(v24, 0, 1u, 0x10000u, 0, 0x10u, 0, CriteriaInterface, &EnumHandle);
      if ( !v25 )
        break;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v26 = L"static";
        LOWORD(v57) = 0;
        LOWORD(v53) = 0;
        if ( (_DWORD)i )
          v26 = L"autostatic";
        FormatRRASErrorString(
          &v57,
          L"UpdateOrClearDodRoutesForInterface : Error %d creating enum handle for %ws routes",
          v25,
          v26);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v27 = &v52;
          if ( a1 != -688 )
            LODWORD(v27) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v57,
            (_DWORD)v27,
            *(_QWORD *)(a1 + 72),
            (__int64)&v53);
        }
      }
LABEL_87:
      ;
    }
LABEL_42:
    HIDWORD(dwBytes) = g_rtmProfile.MaxHandlesInEnum;
    EnumRoutes = RtmGetEnumRoutes(v24, EnumHandle, (PUINT)&dwBytes + 1, v17);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v29 = L"static";
      LOWORD(v57) = 0;
      LOWORD(v53) = 0;
      if ( (_DWORD)i )
        v29 = L"autostatic";
      LODWORD(StartDest) = HIDWORD(dwBytes);
      FormatRRASErrorString(
        &v57,
        L"UpdateOrClearDodRoutesForInterface : Number of %ws routes available for If %d : %d",
        v29,
        CriteriaInterface,
        StartDest);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v30 = &v52;
        if ( a1 != -688 )
          LODWORD(v30) = a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v57,
          (_DWORD)v30,
          *(_QWORD *)(a1 + 72),
          (__int64)&v53);
      }
    }
    for ( j = 0; ; j = (unsigned int)(j + 1) )
    {
      if ( (unsigned int)j >= HIDWORD(dwBytes) )
      {
        RtmReleaseRoutes(v24, HIDWORD(dwBytes), RouteHandles);
        LODWORD(i) = dwBytes;
        v39 = EnumRoutes == 0;
        v17 = RouteHandles;
        CriteriaInterface = v45;
        if ( !v39 )
        {
          RtmDeleteEnumHandle(v24, EnumHandle);
          goto LABEL_87;
        }
        goto LABEL_42;
      }
      if ( v24 == RtmRegHandle[0] )
        goto LABEL_99;
      IsBestRoute = RtmIsBestRoute(v24, RouteHandles[j], &BestInViews);
      EnumRoutes = IsBestRoute;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v57) = 0;
        LOWORD(v53) = 0;
        FormatRRASErrorString(&v57, L"Handle[%d]: RtmIsBestRoute returns %d", (unsigned int)j, IsBestRoute);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v33 = &v52;
          if ( a1 != -688 )
            LODWORD(v33) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v57,
            (_DWORD)v33,
            *(_QWORD *)(a1 + 72),
            (__int64)&v53);
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            LOWORD(v57) = 0;
            LOWORD(v53) = 0;
            FormatRRASErrorString(&v57, L"Handle[%d]: BestInView Flags = %d", (unsigned int)j, BestInViews);
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            {
              v34 = &v52;
              if ( a1 != -688 )
                LODWORD(v34) = a1 + 688;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasRtrmgrParamTraceInfo,
                (unsigned int)&v57,
                (_DWORD)v34,
                *(_QWORD *)(a1 + 72),
                (__int64)&v53);
            }
          }
        }
      }
      if ( !EnumRoutes && (BestInViews & 1) != 0 )
      {
LABEL_99:
        if ( !RtmGetRouteInfo(v24, RouteHandles[j], v14, DestAddress) )
          break;
      }
LABEL_84:
      ;
    }
    if ( v49 )
    {
      if ( v24 != RtmRegHandle[0] )
        goto LABEL_83;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v57) = 0;
        LOWORD(v53) = 0;
        FormatRRASErrorString(
          &v57,
          L"DeleteDodLoopbackRoutesForInterface(If=%d, AF=%d)",
          v45,
          DestAddress->AddressFamily);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v35 = &v52;
          if ( a1 != -688 )
            LODWORD(v35) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v57,
            (_DWORD)v35,
            *(_QWORD *)(a1 + 72),
            (__int64)&v53);
        }
      }
      EnumRoutes = DeleteDoDLoopbackRouteToDestination(DestAddress);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        goto LABEL_83;
      v36 = L"DeleteDoDLoopbackRouteToDestination returned %d";
    }
    else
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v37 = &v52;
        LOWORD(v53) = 0;
        if ( a1 != -688 )
          LODWORD(v37) = a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)L"Calling AddDoDRoute...",
          (_DWORD)v37,
          *(_QWORD *)(a1 + 72),
          (__int64)&v53);
      }
      EnumRoutes = AddDoDRoute(DestAddress);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        goto LABEL_83;
      v36 = L"AddDoDRoute returned %d";
    }
    LOWORD(v57) = 0;
    LOWORD(v53) = 0;
    FormatRRASErrorString(&v57, v36, EnumRoutes);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v38 = &v52;
      if ( a1 != -688 )
        LODWORD(v38) = a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v57,
        (_DWORD)v38,
        *(_QWORD *)(a1 + 72),
        (__int64)&v53);
    }
LABEL_83:
    RtmReleaseRouteInfo(v24, v14);
    goto LABEL_84;
  }
  if ( v5 >= 0 )
    return (int)v7;
  LOWORD(v53) = 0;
  v8 = L"Bailing out since this is not a demand dial interface";
  v9 = RasRtrmgrParamTraceInfo;
LABEL_9:
  v10 = &v52;
  if ( a1 != -688 )
    LODWORD(v10) = a1 + 688;
  LODWORD(v7) = McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (_DWORD)v9,
                  (_DWORD)v8,
                  (_DWORD)v10,
                  *(_QWORD *)(a1 + 72),
                  (__int64)&v53);
  return (int)v7;
}

```

## disassembly

```asm
0x180044d2c  mov     r11, rsp
0x180044d2f  mov     [r11+10h], rbx
0x180044d33  mov     [r11+18h], rsi
0x180044d37  push    rdi
0x180044d38  push    r12
0x180044d3a  push    r13
0x180044d3c  push    r14
0x180044d3e  push    r15
0x180044d40  sub     rsp, 8E0h
0x180044d47  mov     rax, cs:__security_cookie
0x180044d4e  xor     rax, rsp
0x180044d51  mov     [rsp+908h+var_38], rax
0x180044d59  mov     r13d, [rcx+10h]
0x180044d5d  xor     r12d, r12d
0x180044d60  mov     r15d, [rcx+204h]
0x180044d67  mov     rdi, rcx
0x180044d6a  mov     [rsp+908h+var_890], edx
0x180044d6e  lea     rcx, [r11-834h]; void *
0x180044d75  xor     edx, edx; Val
0x180044d77  mov     [r11-880h], r12
0x180044d7e  mov     r8d, 7FCh; Size
0x180044d84  mov     [r11-888h], r12
0x180044d8b  mov     [rsp+908h+BestInViews], r12d
0x180044d90  mov     dword ptr [rsp+908h+dwBytes+4], r12d
0x180044d95  mov     dword ptr [rsp+908h+dwBytes], r12d
0x180044d9a  mov     [r11-838h], r12d
0x180044da1  mov     [rsp+908h+var_8AC], r13d
0x180044da6  mov     [rsp+908h+var_8A8], r15d
0x180044dab  call    memset_0
0x180044db0  mov     r9, cs:Microsoft_Windows_RRASEnableBits
0x180044db7  lea     r14, RasRtrmgrParamTraceInfo
0x180044dbe  xorps   xmm0, xmm0
0x180044dc1  mov     [rsp+908h+var_860], r12d
0x180044dc9  xor     eax, eax
0x180044dcb  lea     rbx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180044dd2  mov     [rsp+908h+var_83C], eax
0x180044dd9  movups  [rsp+908h+var_85C], xmm0
0x180044de1  movups  [rsp+908h+var_84C], xmm0
0x180044de9  movups  [rsp+908h+var_870], xmm0
0x180044df1  test    r9b, r9b
0x180044df4  jns     short loc_180044E74
0x180044df6  mov     r9d, r15d
0x180044df9  mov     word ptr [rsp+908h+var_838], r12w
0x180044e02  mov     r8d, r13d
0x180044e05  mov     word ptr [rsp+908h+var_860], r12w
0x180044e0e  lea     rdx, aUpdateorcleard_2; "UpdateOrClearDodRoutesForInterface (If "...
0x180044e15  lea     rcx, [rsp+908h+var_838]
0x180044e1d  call    FormatRRASErrorString
0x180044e22  mov     r9, cs:Microsoft_Windows_RRASEnableBits
0x180044e29  test    r9b, r9b
0x180044e2c  jns     short loc_180044E74
0x180044e2e  lea     rax, [rdi+2B0h]
0x180044e35  mov     rdx, r14
0x180044e38  test    rax, rax
0x180044e3b  lea     r9, [rsp+908h+var_870]
0x180044e43  lea     r8, [rsp+908h+var_838]
0x180044e4b  mov     rcx, rbx
0x180044e4e  cmovnz  r9, rax
0x180044e52  lea     rax, [rsp+908h+var_860]
0x180044e5a  mov     qword ptr [rsp+908h+MatchingFlags], rax
0x180044e5f  mov     rax, [rdi+48h]
0x180044e63  mov     [rsp+908h+StartDest], rax
0x180044e68  call    McTemplateU0zjzz_EventWriteTransfer
0x180044e6d  mov     r9, cs:Microsoft_Windows_RRASEnableBits
0x180044e74  mov     eax, [rdi+90h]
0x180044e7a  dec     eax
0x180044e7c  cmp     eax, 1
0x180044e7f  jbe     short loc_180044ED7
0x180044e81  test    r9b, 80h
0x180044e85  jz      loc_1800456D2
0x180044e8b  mov     word ptr [rsp+908h+var_860], r12w
0x180044e94  lea     r8, aBailingOutSinc_0; "Bailing out since this is not a demand "...
0x180044e9b  mov     rdx, r14
0x180044e9e  lea     rax, [rdi+2B0h]
0x180044ea5  mov     rcx, rbx
0x180044ea8  test    rax, rax
0x180044eab  lea     r9, [rsp+908h+var_870]
0x180044eb3  cmovnz  r9, rax
0x180044eb7  lea     rax, [rsp+908h+var_860]
0x180044ebf  mov     qword ptr [rsp+908h+MatchingFlags], rax
0x180044ec4  mov     rax, [rdi+48h]
0x180044ec8  mov     [rsp+908h+StartDest], rax
0x180044ecd  call    McTemplateU0zjzz_EventWriteTransfer
0x180044ed2  jmp     loc_1800456D2
0x180044ed7  mov     ecx, cs:g_rtmProfile.MaxNextHopsInRoute
0x180044edd  lea     rdx, [rsp+908h+dwBytes]
0x180044ee2  call    RTMSIZEOFROUTEINFO
0x180044ee7  test    eax, eax
0x180044ee9  jz      short loc_180044F3F
0x180044eeb  test    r9b, 40h
0x180044eef  jz      loc_1800456D2
0x180044ef5  mov     r8d, eax
0x180044ef8  lea     rdx, aUpdateorcleard; "UpdateOrClearDodRoutesForInterface : Er"...
0x180044eff  lea     rcx, [rsp+908h+var_838]
0x180044f07  mov     word ptr [rsp+908h+var_860], r12w
0x180044f10  mov     word ptr [rsp+908h+var_838], r12w
0x180044f19  call    FormatRRASErrorString
0x180044f1e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180044f25  jz      loc_1800456D2
0x180044f2b  lea     r8, [rsp+908h+var_838]
0x180044f33  lea     rdx, RasRtrMgrParamTraceError
0x180044f3a  jmp     loc_180044E9E
0x180044f3f  mov     r8d, dword ptr [rsp+908h+dwBytes]; dwBytes
0x180044f44  xor     edx, edx; dwFlags
0x180044f46  mov     rcx, cs:IPRouterHeap; hHeap
0x180044f4d  call    cs:__imp_HeapAlloc
0x180044f53  mov     rsi, rax
0x180044f56  test    rax, rax
0x180044f59  jnz     short loc_180044F76
0x180044f5b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180044f62  jz      loc_1800456D2
0x180044f68  mov     r8d, dword ptr [rsp+908h+dwBytes]
0x180044f6d  lea     rdx, aUpdateorcleard_6; "UpdateOrClearDodRoutesForInterface : Er"...
0x180044f74  jmp     short loc_180044EFF
0x180044f76  mov     eax, cs:g_rtmProfile.MaxHandlesInEnum
0x180044f7c  mov     ecx, 0FFFFFFFFh
0x180044f81  shl     rax, 3
0x180044f85  cmp     rax, rcx
0x180044f88  ja      loc_180045670
0x180044f8e  mov     rcx, cs:IPRouterHeap; hHeap
0x180044f95  xor     edx, edx; dwFlags
0x180044f97  mov     r8d, eax; dwBytes
0x180044f9a  mov     ebx, eax
0x180044f9c  call    cs:__imp_HeapAlloc
0x180044fa2  mov     [rsp+908h+RouteHandles], rax
0x180044fa7  mov     r14, rax
0x180044faa  test    rax, rax
0x180044fad  jnz     short loc_18004500D
0x180044faf  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180044fb6  jz      loc_1800456C0
0x180044fbc  mov     r8d, ebx
0x180044fbf  mov     word ptr [rsp+908h+var_838], r12w
0x180044fc8  lea     rdx, aUpdateorcleard_3; "UpdateOrClearDodRoutesForInterface : Er"...
0x180044fcf  mov     word ptr [rsp+908h+var_860], r12w
0x180044fd8  lea     rcx, [rsp+908h+var_838]
0x180044fe0  call    FormatRRASErrorString
0x180044fe5  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180044fec  jz      loc_1800456C0
0x180044ff2  lea     r8, [rsp+908h+var_838]
0x180044ffa  lea     rdx, RasRtrMgrParamTraceError
0x180045001  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180045008  jmp     loc_18004568F
0x18004500d  mov     rcx, cs:IPRouterHeap; hHeap
0x180045014  mov     ebx, 14h
0x180045019  mov     r8d, ebx; dwBytes
0x18004501c  xor     edx, edx; dwFlags
0x18004501e  call    cs:__imp_HeapAlloc
0x180045024  mov     [rsp+908h+DestAddress], rax
0x180045029  test    rax, rax
0x18004502c  jnz     loc_1800450CC
0x180045032  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180045039  jz      short loc_1800450B2
0x18004503b  mov     r8d, ebx
0x18004503e  mov     word ptr [rsp+908h+var_838], ax
0x180045046  lea     rdx, aUpdateorcleard_4; "UpdateOrClearDodRoutesForInterface : Er"...
0x18004504d  mov     word ptr [rsp+908h+var_860], ax
0x180045055  lea     rcx, [rsp+908h+var_838]
0x18004505d  call    FormatRRASErrorString
0x180045062  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180045069  jz      short loc_1800450B2
0x18004506b  lea     rax, [rdi+2B0h]
0x180045072  test    rax, rax
0x180045075  lea     r9, [rsp+908h+var_870]
0x18004507d  lea     r8, [rsp+908h+var_838]
0x180045085  cmovnz  r9, rax
0x180045089  lea     rdx, RasRtrMgrParamTraceError
0x180045090  lea     rax, [rsp+908h+var_860]
0x180045098  mov     qword ptr [rsp+908h+MatchingFlags], rax
0x18004509d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800450a4  mov     rax, [rdi+48h]
0x1800450a8  mov     [rsp+908h+StartDest], rax
0x1800450ad  call    McTemplateU0zjzz_EventWriteTransfer
0x1800450b2  mov     rcx, cs:IPRouterHeap; hHeap
0x1800450b9  mov     r8, rsi; lpMem
0x1800450bc  xor     edx, edx; dwFlags
0x1800450be  call    cs:__imp_HeapFree
0x1800450c4  mov     r8, r14
0x1800450c7  jmp     loc_1800456C3
0x1800450cc  mov     eax, r15d
0x1800450cf  mov     r8d, 2716h; unsigned int
0x1800450d5  neg     eax
0x1800450d7  lea     r15, [rdi+2B0h]
0x1800450de  mov     rcx, r15; struct _GUID *
0x1800450e1  sbb     ebx, ebx
0x1800450e3  and     ebx, 0FFFFFFCAh
0x1800450e6  lea     edx, [rbx+57h]; unsigned int
0x1800450e9  call    GetRtmRegistrationHandle
0x1800450ee  mov     r8d, 2712h; unsigned int
0x1800450f4  mov     [rsp+908h+RtmRegHandle], rax
0x1800450fc  lea     edx, [rbx+57h]; unsigned int
0x1800450ff  mov     rcx, r15; struct _GUID *
0x180045102  call    GetRtmRegistrationHandle
0x180045107  mov     [rsp+908h+var_878], rax
0x18004510f  xor     ebx, ebx
0x180045111  mov     dword ptr [rsp+908h+dwBytes], ebx
0x180045115  cmp     ebx, 2
0x180045118  jnb     loc_180045645
0x18004511e  mov     r12, [rsp+rbx*8+908h+RtmRegHandle]
0x180045126  lea     rax, [rsp+908h+EnumHandle]
0x18004512e  mov     [rsp+908h+RtmEnumHandle], rax; RtmEnumHandle
0x180045133  xor     edx, edx; DestHandle
0x180045135  mov     [rsp+908h+CriteriaInterface], r13d; CriteriaInterface
0x18004513a  mov     r9d, 10000h; EnumFlags
0x180045140  mov     [rsp+908h+CriteriaRoute], 0; CriteriaRoute
0x180045149  mov     rcx, r12; RtmRegHandle
0x18004514c  mov     [rsp+908h+MatchingFlags], 10h; MatchingFlags
0x180045154  lea     r8d, [rdx+1]; TargetViews
0x180045158  mov     [rsp+908h+StartDest], 0; StartDest
0x180045161  call    cs:__imp_RtmCreateRouteEnum
0x180045167  test    eax, eax
0x180045169  jz      loc_18004520B
0x18004516f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180045176  jz      loc_18004563E
0x18004517c  xor     ecx, ecx
0x18004517e  lea     r9, aStatic; "static"
0x180045185  mov     word ptr [rsp+908h+var_838], cx
0x18004518d  lea     rdx, aUpdateorcleard_5; "UpdateOrClearDodRoutesForInterface : Er"...
0x180045194  mov     word ptr [rsp+908h+var_860], cx
0x18004519c  test    ebx, ebx
0x18004519e  lea     rcx, aAutostatic; "autostatic"
0x1800451a5  mov     r8d, eax
0x1800451a8  cmovnz  r9, rcx
0x1800451ac  lea     rcx, [rsp+908h+var_838]
0x1800451b4  call    FormatRRASErrorString
0x1800451b9  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x1800451c0  jz      loc_18004563E
0x1800451c6  lea     rax, [rsp+908h+var_860]
0x1800451ce  test    r15, r15
0x1800451d1  mov     qword ptr [rsp+908h+MatchingFlags], rax
0x1800451d6  lea     r9, [rsp+908h+var_870]
0x1800451de  mov     rax, [rdi+48h]
0x1800451e2  lea     r8, [rsp+908h+var_838]
0x1800451ea  cmovnz  r9, r15
0x1800451ee  mov     [rsp+908h+StartDest], rax
0x1800451f3  lea     rdx, RasRtrMgrParamTraceError
0x1800451fa  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180045201  call    McTemplateU0zjzz_EventWriteTransfer
0x180045206  jmp     loc_18004563E
0x18004520b  mov     eax, cs:g_rtmProfile.MaxHandlesInEnum
0x180045211  lea     r8, [rsp+908h+dwBytes+4]; NumRoutes
0x180045216  mov     rdx, [rsp+908h+EnumHandle]; EnumHandle
0x18004521e  mov     r9, r14; RouteHandles
0x180045221  mov     rcx, r12; RtmRegHandle
0x180045224  mov     dword ptr [rsp+908h+dwBytes+4], eax
0x180045228  call    cs:__imp_RtmGetEnumRoutes
0x18004522e  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180045235  mov     r14d, eax
0x180045238  jge     loc_1800452CC
0x18004523e  xor     eax, eax
0x180045240  lea     r8, aStatic; "static"
0x180045247  mov     word ptr [rsp+908h+var_838], ax
0x18004524f  lea     rdx, aUpdateorcleard_1; "UpdateOrClearDodRoutesForInterface : Nu"...
0x180045256  mov     word ptr [rsp+908h+var_860], ax
0x18004525e  lea     rcx, [rsp+908h+var_838]
0x180045266  lea     rax, aAutostatic; "autostatic"
0x18004526d  test    ebx, ebx
0x18004526f  mov     r9d, r13d
0x180045272  cmovnz  r8, rax
0x180045276  mov     eax, dword ptr [rsp+908h+dwBytes+4]
0x18004527a  mov     dword ptr [rsp+908h+StartDest], eax
0x18004527e  call    FormatRRASErrorString
0x180045283  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18004528a  jge     short loc_1800452CC
0x18004528c  lea     rax, [rsp+908h+var_860]
0x180045294  test    r15, r15
0x180045297  mov     qword ptr [rsp+908h+MatchingFlags], rax
0x18004529c  lea     r9, [rsp+908h+var_870]
0x1800452a4  mov     rax, [rdi+48h]
0x1800452a8  lea     r8, [rsp+908h+var_838]
0x1800452b0  cmovnz  r9, r15
0x1800452b4  mov     [rsp+908h+StartDest], rax
0x1800452b9  lea     rdx, RasRtrmgrParamTraceInfo
0x1800452c0  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800452c7  call    McTemplateU0zjzz_EventWriteTransfer
0x1800452cc  xor     r13d, r13d
0x1800452cf  mov     edx, dword ptr [rsp+908h+dwBytes+4]; NumRoutes
0x1800452d3  cmp     r13d, edx
0x1800452d6  jnb     loc_180045608
0x1800452dc  lea     rbx, ds:0[r13*8]
0x1800452e4  cmp     r12, [rsp+908h+RtmRegHandle]
0x1800452ec  jz      loc_180045426
0x1800452f2  mov     rax, [rsp+908h+RouteHandles]
0x1800452f7  lea     r8, [rsp+908h+BestInViews]; BestInViews
0x1800452fc  mov     rcx, r12; RtmRegHandle
0x1800452ff  mov     rdx, [rax+rbx]; RouteHandle
0x180045303  call    cs:__imp_RtmIsBestRoute
0x180045309  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180045310  mov     r14d, eax
0x180045313  jge     loc_180045412
0x180045319  xor     ecx, ecx
0x18004531b  lea     rdx, aHandleDRtmisbe; "Handle[%d]: RtmIsBestRoute returns %d"
0x180045322  mov     word ptr [rsp+908h+var_838], cx
0x18004532a  mov     r9d, eax
0x18004532d  mov     word ptr [rsp+908h+var_860], cx
0x180045335  mov     r8d, r13d
0x180045338  lea     rcx, [rsp+908h+var_838]
0x180045340  call    FormatRRASErrorString
0x180045345  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18004534c  jge     loc_180045412
0x180045352  lea     rax, [rsp+908h+var_860]
  ... truncated ...
```

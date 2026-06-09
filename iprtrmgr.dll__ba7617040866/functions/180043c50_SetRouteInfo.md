# SetRouteInfo

- ea: `0x180043c50`
- end: `0x180044d24`
- name: `SetRouteInfo`
- size: `4308`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000b450`

## callees

- `0x180011790`
- `0x18001797c`
- `0x180017aa8`
- `0x18003f1a4`
- `0x18003fb20`
- `0x1800401a0`
- `0x180040408`
- `0x180043c50`
- `0x180051ef8`
- `0x1800533c8`
- `0x180057aa4`
- `0x180057c48`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x180044415`
- `ntdll!NtDeviceIoControlFile` at `0x180044415`
- `KERNEL32!HeapFree` at `0x1800440bb`
- `KERNEL32!HeapFree` at `0x180044195`
- `KERNEL32!HeapFree` at `0x1800441a7`
- `KERNEL32!HeapFree` at `0x1800447d2`
- `KERNEL32!HeapFree` at `0x180044884`
- `KERNEL32!HeapFree` at `0x180044950`
- `KERNEL32!HeapFree` at `0x180044962`
- `KERNEL32!HeapFree` at `0x1800449fa`
- `KERNEL32!HeapFree` at `0x180044a11`
- `KERNEL32!HeapFree` at `0x180044a25`
- `KERNEL32!HeapFree` at `0x180044ac7`
- `KERNEL32!HeapFree` at `0x180044ad9`
- `KERNEL32!HeapFree` at `0x1800440bb`
- `KERNEL32!HeapFree` at `0x180044195`
- `KERNEL32!HeapFree` at `0x1800441a7`
- `KERNEL32!HeapFree` at `0x1800447d2`
- `KERNEL32!HeapFree` at `0x180044884`
- `KERNEL32!HeapFree` at `0x180044950`
- `KERNEL32!HeapFree` at `0x180044962`
- `KERNEL32!HeapFree` at `0x1800449fa`
- `KERNEL32!HeapFree` at `0x180044a11`
- `KERNEL32!HeapFree` at `0x180044a25`
- `KERNEL32!HeapFree` at `0x180044ac7`
- `KERNEL32!HeapFree` at `0x180044ad9`
- `KERNEL32!HeapAlloc` at `0x180043ea8`
- `KERNEL32!HeapAlloc` at `0x180043fab`
- `KERNEL32!HeapAlloc` at `0x1800440ef`
- `KERNEL32!HeapAlloc` at `0x180044697`
- `KERNEL32!HeapAlloc` at `0x1800447eb`
- `KERNEL32!HeapAlloc` at `0x180043ea8`
- `KERNEL32!HeapAlloc` at `0x180043fab`
- `KERNEL32!HeapAlloc` at `0x1800440ef`
- `KERNEL32!HeapAlloc` at `0x180044697`
- `KERNEL32!HeapAlloc` at `0x1800447eb`
- `WS2_32!__imp_htonl` at `0x18004435a`
- `WS2_32!__imp_htonl` at `0x18004436c`
- `WS2_32!__imp_htonl` at `0x18004435a`
- `WS2_32!__imp_htonl` at `0x18004436c`
- `rtm!RtmDeleteRouteToDest` at `0x18004497c`
- `rtm!RtmDeleteRouteToDest` at `0x18004497c`
- `rtm!RtmReleaseRoutes` at `0x180044999`
- `rtm!RtmReleaseRoutes` at `0x1800449e3`
- `rtm!RtmReleaseRoutes` at `0x180044999`
- `rtm!RtmReleaseRoutes` at `0x1800449e3`
- `rtm!RtmGetEnumRoutes` at `0x18004463d`
- `rtm!RtmGetEnumRoutes` at `0x18004463d`
- `rtm!RtmCreateRouteEnum` at `0x18004457a`
- `rtm!RtmCreateRouteEnum` at `0x18004457a`
- `rtm!RtmDeleteEnumHandle` at `0x1800449b7`
- `rtm!RtmDeleteEnumHandle` at `0x1800449b7`
- `rtm!RtmReleaseRouteInfo` at `0x18004493e`
- `rtm!RtmReleaseRouteInfo` at `0x18004493e`
- `rtm!RtmGetRouteInfo` at `0x1800448ad`
- `rtm!RtmGetRouteInfo` at `0x1800448ad`

## string_xrefs

- `0x1800448db`: `SetRouteInfo : DeleteDoDLoopbackRouteToDestination successeded  `
- `0x1800448ed`: `SetRouteInfo : DeleteDoDLoopbackRouteToDestination failed`

## pseudocode

```c
__int64 __fastcall SetRouteInfo(__int64 a1, void *a2)
{
  int v2; // r15d
  DWORD v5; // edx
  char v6; // r11
  __int128 *v7; // r9
  __int64 v8; // r8
  __int128 *v9; // r9
  const wchar_t *v10; // r8
  char v11; // r11
  LPBYTE v12; // r14
  unsigned __int64 v13; // rdi
  unsigned __int64 v14; // rcx
  ULONG InputBufferLength; // r12d
  BYTE *v16; // rax
  LPBYTE InputBuffer; // r13
  char v18; // al
  __int128 *v19; // r9
  bool v20; // zf
  void *v21; // r15
  int v22; // ecx
  PRTM_ROUTE_HANDLE v23; // r15
  char v24; // al
  __int128 *v25; // r9
  __int128 *v26; // r9
  unsigned __int64 v28; // rax
  __int128 *v29; // r9
  __int128 *v30; // r9
  int v31; // ecx
  DWORD v32; // ecx
  __int64 v33; // r15
  __int64 v34; // r13
  DWORD i; // r12d
  __int64 v36; // rdi
  int BestNextHopMaskGivenIndex; // esi
  int v38; // r8d
  int BestNextHopIPv6PrefixLengthGivenICB; // eax
  BYTE *v40; // rdi
  u_long v41; // eax
  _DWORD *v42; // rsi
  _BYTE *v43; // rdx
  __int64 v44; // rcx
  UINT v45; // r15d
  HANDLE v46; // rcx
  unsigned int v47; // eax
  __int64 v48; // r9
  __int128 *v49; // r9
  void *RtmRegistrationHandle; // rax
  bool v51; // cf
  int v52; // r13d
  unsigned int j; // r12d
  RTM_ENTITY_HANDLE v54; // r15
  DWORD v55; // eax
  __int64 v56; // r9
  __int128 *v57; // r9
  HANDLE *v58; // r13
  DWORD EnumRoutes; // esi
  __int64 k; // rax
  __int64 v61; // rdx
  RTM_ROUTE_HANDLE *v62; // r12
  struct _RTM_NET_ADDRESS *v63; // r15
  __int128 *v64; // r9
  __int128 *v65; // r9
  struct _RTM_ROUTE_INFO *v66; // rax
  struct _RTM_ROUTE_INFO *v67; // rsi
  __int128 *v68; // r9
  const wchar_t *v69; // r8
  __int128 *v70; // r9
  __int128 *v71; // r9
  __int128 *v72; // r9
  const wchar_t *v73; // rdx
  __int128 *v74; // r9
  __int128 *v75; // r9
  ULONG v76; // [rsp+50h] [rbp-958h]
  DWORD dwItemSize; // [rsp+54h] [rbp-954h] BYREF
  int v78; // [rsp+58h] [rbp-950h]
  DWORD dwItemCount; // [rsp+5Ch] [rbp-94Ch] BYREF
  UINT v80; // [rsp+60h] [rbp-948h]
  int v81; // [rsp+64h] [rbp-944h]
  RTM_ENTITY_HANDLE v82; // [rsp+68h] [rbp-940h]
  unsigned int v83; // [rsp+70h] [rbp-938h]
  unsigned int NumRoutes; // [rsp+74h] [rbp-934h] BYREF
  LPBYTE lpItemData; // [rsp+78h] [rbp-930h] BYREF
  DWORD ChangeFlags; // [rsp+80h] [rbp-928h] BYREF
  HANDLE RtmEnumHandle; // [rsp+88h] [rbp-920h] BYREF
  PRTM_ROUTE_HANDLE v88; // [rsp+90h] [rbp-918h]
  RTM_ENTITY_HANDLE v89; // [rsp+98h] [rbp-910h]
  PRTM_ROUTE_HANDLE RouteHandles; // [rsp+A0h] [rbp-908h]
  __int128 v91; // [rsp+B0h] [rbp-8F8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C0h] [rbp-8E8h] BYREF
  _DWORD v93[2]; // [rsp+D0h] [rbp-8D8h] BYREF
  _QWORD RtmRegHandle[11]; // [rsp+D8h] [rbp-8D0h]
  __int128 v95; // [rsp+130h] [rbp-878h] BYREF
  int v96; // [rsp+140h] [rbp-868h] BYREF
  __int128 v97; // [rsp+144h] [rbp-864h]
  __int128 v98; // [rsp+154h] [rbp-854h]
  int v99; // [rsp+164h] [rbp-844h]
  int v100; // [rsp+170h] [rbp-838h] BYREF
  _BYTE v101[2044]; // [rsp+174h] [rbp-834h] BYREF

  v2 = *(_DWORD *)(a1 + 516);
  lpItemData = 0;
  RtmEnumHandle = 0;
  NumRoutes = 0;
  ChangeFlags = 0;
  v78 = v2;
  dwItemSize = 0;
  IoStatusBlock = 0;
  dwItemCount = 0;
  memset_0(v93, 0, 0x60u);
  v100 = 0;
  memset_0(v101, 0, sizeof(v101));
  v6 = Microsoft_Windows_RRASEnableBits;
  v96 = 0;
  v99 = 0;
  v97 = 0;
  v98 = 0;
  v95 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v96) = 0;
    v7 = &v95;
    if ( a1 != -688 )
      LODWORD(v7) = a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Entered: SetRouteInfo",
      (_DWORD)v7,
      *(_QWORD *)(a1 + 72),
      (__int64)&v96);
    v6 = Microsoft_Windows_RRASEnableBits;
  }
  if ( *(_DWORD *)(a1 + 168) == 1 )
  {
    if ( v6 >= 0 )
      return 0;
    v8 = *(_QWORD *)(a1 + 72);
    LOWORD(v100) = 0;
    LOWORD(v96) = 0;
    FormatRRASErrorString(&v100, L"SetRouteInfo: %ws is unreachable, not setting routes", v8);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return 0;
    v9 = &v95;
    v10 = (const wchar_t *)&v100;
    if ( a1 != -688 )
      LODWORD(v9) = a1 + 688;
    goto LABEL_178;
  }
  if ( MprInfoBlockFind(a2, v5, &dwItemSize, &dwItemCount, &lpItemData) )
  {
    if ( v11 < 0 )
    {
      v9 = &v95;
      if ( a1 != -688 )
        LODWORD(v9) = a1 + 688;
LABEL_177:
      v10 = L"Leaving: SetRouteInfo";
      LOWORD(v96) = 0;
LABEL_178:
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (_DWORD)v10,
        (_DWORD)v9,
        *(_QWORD *)(a1 + 72),
        (__int64)&v96);
      return 0;
    }
    return 0;
  }
  if ( dwItemSize )
  {
    v12 = lpItemData;
    if ( lpItemData )
    {
      v13 = 8LL * dwItemCount;
      if ( v13 > 0xFFFFFFFF )
      {
        if ( (v11 & 0x40) == 0 )
          goto LABEL_168;
        v73 = L"SetRouteInfo: Arithmetic overflow error allocating %d bytes for added route handles";
      }
      else
      {
        v14 = dwItemCount * ((-(__int64)(v2 != 0) & 0xFFFFFFFFFFFFFFF7uLL) + 17);
        if ( v14 <= 0xFFFFFFFF )
        {
          InputBufferLength = v14 + 12;
          v76 = v14 + 12;
          if ( (int)v14 + 12 >= (unsigned int)v14 )
          {
            v16 = (BYTE *)HeapAlloc(IPRouterHeap, 0, InputBufferLength);
            lpItemData = v16;
            InputBuffer = v16;
            if ( !v16 )
            {
              v18 = Microsoft_Windows_RRASEnableBits;
              if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
              {
                LOWORD(v100) = 0;
                LOWORD(v96) = 0;
                FormatRRASErrorString(
                  &v100,
                  L"SetRouteInfo: Error allocating %d bytes for addded SubnetInfo",
                  InputBufferLength);
                v18 = Microsoft_Windows_RRASEnableBits;
                if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                {
                  v19 = &v95;
                  if ( a1 != -688 )
                    LODWORD(v19) = a1 + 688;
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasRtrmgrParamTraceInfo,
                    (unsigned int)&v100,
                    (_DWORD)v19,
                    *(_QWORD *)(a1 + 72),
                    (__int64)&v96);
                  v18 = Microsoft_Windows_RRASEnableBits;
                }
              }
              v20 = v18 >= 0;
LABEL_50:
              if ( !v20 )
              {
                v30 = &v95;
                LOWORD(v96) = 0;
                if ( a1 != -688 )
                  LODWORD(v30) = a1 + 688;
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasRtrmgrParamTraceInfo,
                  (unsigned int)L"Leaving: SetRouteInfo",
                  (_DWORD)v30,
                  *(_QWORD *)(a1 + 72),
                  (__int64)&v96);
              }
              return 8;
            }
            memset_0(v16, 0, InputBufferLength);
            *(_DWORD *)InputBuffer = 0;
            v21 = 0;
            *((_DWORD *)InputBuffer + 1) = *(_DWORD *)(a1 + 88);
            v22 = *(_DWORD *)(a1 + 516);
            *((_DWORD *)InputBuffer + 2) = v22;
            if ( !v22 )
              v21 = InputBuffer + 12;
            v89 = v21;
            v82 = (RTM_ENTITY_HANDLE)((unsigned __int64)(InputBuffer + 12) & -(__int64)(v22 != 0));
            v88 = (PRTM_ROUTE_HANDLE)HeapAlloc(IPRouterHeap, 0, (unsigned int)v13);
            v23 = v88;
            if ( !v88 )
            {
              v24 = Microsoft_Windows_RRASEnableBits;
              if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
              {
                LOWORD(v100) = 0;
                LOWORD(v96) = 0;
                FormatRRASErrorString(
                  &v100,
                  L"SetRouteInfo: Error allocating %d bytes for addded route handles",
                  (unsigned int)v13);
                v24 = Microsoft_Windows_RRASEnableBits;
                if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                {
                  v25 = &v95;
                  if ( a1 != -688 )
                    LODWORD(v25) = a1 + 688;
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasRtrMgrParamTraceError,
                    (unsigned int)&v100,
                    (_DWORD)v25,
                    *(_QWORD *)(a1 + 72),
                    (__int64)&v96);
                  v24 = Microsoft_Windows_RRASEnableBits;
                }
              }
              if ( v24 < 0 )
              {
                v26 = &v95;
                LOWORD(v96) = 0;
                if ( a1 != -688 )
                  LODWORD(v26) = a1 + 688;
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasRtrmgrParamTraceInfo,
                  (unsigned int)L"Leaving: SetRouteInfo",
                  (_DWORD)v26,
                  *(_QWORD *)(a1 + 72),
                  (__int64)&v96);
              }
              HeapFree(IPRouterHeap, 0, InputBuffer);
              return 8;
            }
            v28 = 8LL * g_rtmProfile.MaxHandlesInEnum;
            if ( v28 <= 0xFFFFFFFF )
            {
              RouteHandles = (PRTM_ROUTE_HANDLE)HeapAlloc(IPRouterHeap, 0, (unsigned int)v28);
              if ( !RouteHandles )
              {
                if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                {
                  LOWORD(v100) = 0;
                  LOWORD(v96) = 0;
                  FormatRRASErrorString(
                    &v100,
                    L"SetRouteInfo: Error allocating %d bytes for route handles",
                    (unsigned int)v13);
                  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                  {
                    v29 = &v95;
                    if ( a1 != -688 )
                      LODWORD(v29) = a1 + 688;
                    McTemplateU0zjzz_EventWriteTransfer(
                      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      (unsigned int)RasRtrMgrParamTraceError,
                      (unsigned int)&v100,
                      (_DWORD)v29,
                      *(_QWORD *)(a1 + 72),
                      (__int64)&v96);
                  }
                }
                HeapFree(IPRouterHeap, 0, InputBuffer);
                HeapFree(IPRouterHeap, 0, v23);
                v20 = (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL;
                goto LABEL_50;
              }
              v31 = *(_DWORD *)(a1 + 144);
              if ( (unsigned int)(v31 - 1) <= 1 || (v20 = v31 == 7, v32 = 0, v20) )
                v32 = 1;
              v33 = 0;
              v80 = 0;
              dwItemSize = v32;
              if ( dwItemCount )
              {
                v34 = 0;
                for ( i = 0; i < dwItemCount; ++i )
                {
                  v36 = 72 * v34;
                  if ( *(_DWORD *)(a1 + 168) != 2 || *(_DWORD *)&v12[v36 + 56] != 10007 )
                  {
                    BestNextHopMaskGivenIndex = 0;
                    v81 = 0;
                    if ( !v32 || *(_DWORD *)(a1 + 144) == 2 )
                    {
                      if ( v78 )
                      {
                        BestNextHopMaskGivenIndex = GetBestNextHopMaskGivenIndex(
                                                      *(unsigned int *)(a1 + 16),
                                                      *(unsigned int *)&v12[v36 + 12]);
                        BestNextHopIPv6PrefixLengthGivenICB = v81;
                      }
                      else
                      {
                        v91 = *(_OWORD *)&v12[v36 + 20];
                        BestNextHopIPv6PrefixLengthGivenICB = GetBestNextHopIPv6PrefixLengthGivenICB(a1, &v91);
                      }
                      v38 = v78;
                    }
                    else
                    {
                      v38 = v78;
                      if ( v78 )
                      {
                        BestNextHopMaskGivenIndex = -1;
                        *(_DWORD *)&v12[v36 + 12] = *(_DWORD *)(a1 + 672);
                        BestNextHopIPv6PrefixLengthGivenICB = v81;
                      }
                      else
                      {
                        BestNextHopIPv6PrefixLengthGivenICB = 128;
                        *(_OWORD *)&v12[v36 + 20] = *(_OWORD *)(a1 + 672);
                      }
                    }
                    v40 = &v12[v36];
                    if ( !v38 )
                      BestNextHopMaskGivenIndex = BestNextHopIPv6PrefixLengthGivenICB;
                    if ( (unsigned int)AddSingleRoute(
                                         *(_DWORD *)(a1 + 16),
                                         (int)v40,
                                         BestNextHopMaskGivenIndex,
                                         0,
                                         1,
                                         1,
                                         dwItemSize,
                                         v78,
                                         (struct _GUID *)(a1 + 688),
                                         (__int64)&v88[v33]) )
                    {
                      v33 = v80;
                    }
                    else
                    {
                      if ( v78 )
                      {
                        v41 = htonl(*(_DWORD *)v40);
                        v42 = v82;
                        *((_DWORD *)v82 + 2 * v33) = v41;
                        v42[2 * v33 + 1] = htonl(*((_DWORD *)v40 + 1));
                      }
                      else
                      {
                        v43 = v89;
                        v44 = 17 * v33;
                        *(_OWORD *)((char *)v89 + v44) = *(_OWORD *)v40;
                        v43[v44 + 16] = v40[16];
                      }
                      v45 = v80;
                      ++*(_DWORD *)lpItemData;
                      v33 = v45 + 1;
                      v80 = v33;
                    }
                  }
                  v32 = dwItemSize;
                  ++v34;
                }
                InputBufferLength = v76;
                InputBuffer = lpItemData;
              }
              v46 = (HANDLE)g_hWanarpWriteV6;
              if ( *(_DWORD *)(a1 + 516) )
                v46 = g_hWanarpWrite;
              v47 = NtDeviceIoControlFile(
                      v46,
                      0,
                      0,
                      0,
                      &IoStatusBlock,
                      0x90018028,
                      InputBuffer,
                      InputBufferLength,
                      0,
                      0);
              if ( v47 )
              {
                if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                {
                  v48 = *(_QWORD *)(a1 + 72);
                  LOWORD(v100) = 0;
                  LOWORD(v96) = 0;
                  FormatRRASErrorString(&v100, L"SetSubnetInfo: Status %x for interface %ws", v47, v48);
                  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                  {
                    v49 = &v95;
                    if ( a1 != -688 )
                      LODWORD(v49) = a1 + 688;
                    McTemplateU0zjzz_EventWriteTransfer(
                      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      (unsigned int)RasRtrmgrParamTraceInfo,
                      (unsigned int)&v100,
                      (_DWORD)v49,
                      *(_QWORD *)(a1 + 72),
                      (__int64)&v96);
                  }
                }
              }
              RtmRegistrationHandle = (void *)GetRtmRegistrationHandle(
                                                (struct _GUID *)(a1 + 688),
                                                *(_DWORD *)(a1 + 516) != 0 ? 33 : 87,
                                                2u);
              v51 = *(_DWORD *)(a1 + 516) != 0;
              v89 = RtmRegistrationHandle;
              GetAllRtmRegistrationHandles(a1 + 688, v51 ? 33 : 87, v93);
              v52 = v78;
              for ( j = 0; ; ++j )
              {
                v83 = j;
                if ( j >= 5 )
                {
                  RtmReleaseRoutes(v89, v80, v88);
                  HeapFree(IPRouterHeap, 0, v88);
                  HeapFree(IPRouterHeap, 0, RouteHandles);
                  HeapFree(IPRouterHeap, 0, lpItemData);
                  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                  {
                    v9 = &v95;
                    LOWORD(v96) = 0;
                    v10 = L"Leaving: SetRouteInfo";
                    if ( a1 != -688 )
                      LODWORD(v9) = a1 + 688;
                    goto LABEL_178;
                  }
                  return 0;
                }
                if ( !v93[4 * j + 1] )
                  continue;
                v54 = (RTM_ENTITY_HANDLE)RtmRegHandle[2 * j];
                v82 = v54;
                v55 = RtmCreateRouteEnum(
                        v54,
                        0,
                        v52 != 0 ? 3 : 1,
                        0x10000u,
                        0,
                        0x10u,
                        0,
                        *(_DWORD *)(a1 + 16),
                        &RtmEnumHandle);
                if ( !v55 )
                  break;
                if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                {
                  v56 = (unsigned int)v93[4 * j];
                  LOWORD(v100) = 0;
                  LOWORD(v96) = 0;
                  FormatRRASErrorString(&v100, L"SetRouteInfo: Error %d creating enum handle for %d", v55, v56);
                  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                  {
                    v57 = &v95;
                    if ( a1 != -688 )
                      LODWORD(v57) = a1 + 688;
                    McTemplateU0zjzz_EventWriteTransfer(
                      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      (unsigned int)RasRtrMgrParamTraceError,
                      (unsigned int)&v100,
                      (_DWORD)v57,
                      *(_QWORD *)(a1 + 72),
                      (__int64)&v96);
                  }
                }
LABEL_142:
                ;
              }
              v58 = RouteHandles;
LABEL_98:
              NumRoutes = g_rtmProfile.MaxHandlesInEnum;
              EnumRoutes = RtmGetEnumRoutes(v54, RtmEnumHandle, &NumRoutes, v58);
              for ( k = 0; ; k = (unsigned int)(v81 + 1) )
              {
                v81 = k;
                if ( (unsigned int)k >= NumRoutes )
                {
                  if ( EnumRoutes )
                  {
                    RtmDeleteEnumHandle(v54, RtmEnumHandle);
                    j = v83;
                    v52 = v78;
                    goto LABEL_142;
                  }
                  goto LABEL_98;
                }
                v61 = 0;
                v62 = &v58[k];
                while ( (unsigned int)v61 < v80 )
                {
                  if ( *v62 == v88[v61] )
                    goto LABEL_139;
                  v61 = (unsigned int)(v61 + 1);
                }
                dwItemSize = 0;
                v63 = (struct _RTM_NET_ADDRESS *)HeapAlloc(IPRouterHeap, 0, 0x14u);
                if ( !v63 )
                {
                  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                  {
                    LOWORD(v100) = 0;
                    LOWORD(v96) = 0;
                    FormatRRASErrorString(&v100, L"SetRouteInfo : Error allocating %d bytes for dest. address", 20);
                    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                    {
                      v64 = &v95;
                      if ( a1 != -688 )
                        LODWORD(v64) = a1 + 688;
                      McTemplateU0zjzz_EventWriteTransfer(
                        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                        (unsigned int)RasRtrMgrParamTraceError,
                        (unsigned int)&v100,
                        (_DWORD)v64,
                        *(_QWORD *)(a1 + 72),
                        (__int64)&v96);
                    }
                  }
LABEL_110:
                  v54 = v82;
                  continue;
                }
                dwItemCount = RTMSIZEOFROUTEINFO(g_rtmProfile.MaxNextHopsInRoute, &dwItemSize);
                EnumRoutes = dwItemCount;
                if ( dwItemCount )
                {
                  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                  {
                    LOWORD(v100) = 0;
                    LOWORD(v96) = 0;
                    FormatRRASErrorString(&v100, L"SetRouteInfo : Error  Integer overflow %d", dwItemCount);
                    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                    {
                      v65 = &v95;
                      if ( a1 != -688 )
                        LODWORD(v65) = a1 + 688;
                      McTemplateU0zjzz_EventWriteTransfer(
                        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                        (unsigned int)RasRtrMgrParamTraceError,
                        (unsigned int)&v100,
                        (_DWORD)v65,
                        *(_QWORD *)(a1 + 72),
                        (__int64)&v96);
                    }
                  }
                  HeapFree(IPRouterHeap, 0, v63);
                  goto LABEL_110;
                }
                v66 = (struct _RTM_ROUTE_INFO *)HeapAlloc(IPRouterHeap, 0, dwItemSize);
                v67 = v66;
                if ( !v66 )
                {
                  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                  {
                    LOWORD(v100) = 0;
                    LOWORD(v96) = 0;
                    FormatRRASErrorString(&v100, L"SetRouteInfo : Error allocating %d bytes for route info", dwItemSize);
                    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                    {
                      v68 = &v95;
                      if ( a1 != -688 )
                        LODWORD(v68) = a1 + 688;
                      McTemplateU0zjzz_EventWriteTransfer(
                        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                        (unsigned int)RasRtrMgrParamTraceError,
                        (unsigned int)&v100,
                        (_DWORD)v68,
                        *(_QWORD *)(a1 + 72),
                        (__int64)&v96);
                    }
                  }
                  HeapFree(IPRouterHeap, 0, v63);
                  v54 = v82;
LABEL_125:
                  EnumRoutes = dwItemCount;
                  continue;
                }
                if ( !RtmGetRouteInfo(v82, *v62, v66, v63) )
                  break;
LABEL_137:
                HeapFree(IPRouterHeap, 0, v63);
                HeapFree(IPRouterHeap, 0, v67);
                v54 = v82;
                if ( !RtmDeleteRouteToDest(v82, *v62, &ChangeFlags) )
                  goto LABEL_125;
                EnumRoutes = dwItemCount;
LABEL_139:
                RtmReleaseRoutes(v54, 1u, v62);
              }
              if ( (unsigned int)DeleteDoDLoopbackRouteToDestination(v63) )
              {
                if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                {
                  v69 = L"SetRouteInfo : DeleteDoDLoopbackRouteToDestination failed";
                  goto LABEL_133;
                }
              }
              else if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
              {
                v69 = L"SetRouteInfo : DeleteDoDLoopbackRouteToDestination successeded  ";
LABEL_133:
                v70 = &v95;
                LOWORD(v96) = 0;
                if ( a1 != -688 )
                  LODWORD(v70) = a1 + 688;
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasRtrmgrParamTraceInfo,
                  (_DWORD)v69,
                  (_DWORD)v70,
                  *(_QWORD *)(a1 + 72),
                  (__int64)&v96);
              }
              RtmReleaseRouteInfo(v82, v67);
              goto LABEL_137;
            }
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            {
              LOWORD(v96) = 0;
              v71 = &v95;
              if ( a1 != -688 )
                LODWORD(v71) = a1 + 688;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasRtrmgrParamTraceInfo,
                (unsigned int)L"SetRouteInfo: Integer overflow",
                (_DWORD)v71,
                *(_QWORD *)(a1 + 72),
                (__int64)&v96);
            }
            HeapFree(IPRouterHeap, 0, InputBuffer);
            HeapFree(IPRouterHeap, 0, v23);
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            {
              LOWORD(v96) = 0;
LABEL_170:
              v75 = &v95;
              if ( a1 != -688 )
                LODWORD(v75) = a1 + 688;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasRtrmgrParamTraceInfo,
                (unsigned int)L"Leaving: SetRouteInfo",
                (_DWORD)v75,
                *(_QWORD *)(a1 + 72),
                (__int64)&v96);
            }
            return 534;
          }
          if ( (v11 & 0x40) != 0 )
          {
            LOWORD(v100) = 0;
            LOWORD(v96) = 0;
            FormatRRASErrorString(
              &v100,
              L"SetRouteInfo: Arithmetic overflow error allocating %d bytes for RtrSubnetBufSize");
            v11 = Microsoft_Windows_RRASEnableBits;
            if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            {
              v72 = &v95;
              if ( a1 != -688 )
                LODWORD(v72) = a1 + 688;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasRtrMgrParamTraceError,
                (unsigned int)&v100,
                (_DWORD)v72,
                *(_QWORD *)(a1 + 72),
                (__int64)&v96);
              v11 = Microsoft_Windows_RRASEnableBits;
            }
          }
          if ( v11 >= 0 )
            return 534;
LABEL_169:
          LOWORD(v96) = 0;
          goto LABEL_170;
        }
        if ( (v11 & 0x40) == 0 )
        {
LABEL_168:
          if ( v11 >= 0 )
            return 534;
          goto LABEL_169;
        }
        v73 = L"SetRouteInfo: Arithmetic overflow error allocating %d bytes for RtrSubnetBufSize";
      }
      LOWORD(v100) = 0;
      LOWORD(v96) = 0;
      FormatRRASErrorString(&v100, v73);
      v11 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v74 = &v95;
        if ( a1 != -688 )
          LODWORD(v74) = a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v100,
          (_DWORD)v74,
          *(_QWORD *)(a1 + 72),
          (__int64)&v96);
        v11 = Microsoft_Windows_RRASEnableBits;
      }
      goto LABEL_168;
    }
  }
  DeleteAllRoutes(a1, 1);
  ClearWfpFiltersForInterfaceFromWanarp(a1);
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v9 = &v95;
    if ( a1 != -688 )
      LODWORD(v9) = a1 + 688;
    goto LABEL_177;
  }
  return 0;
}

```

## disassembly

```asm
0x180043c50  mov     r11, rsp
0x180043c53  mov     [r11+18h], rbx
0x180043c57  mov     [r11+20h], rsi
0x180043c5b  push    rdi
0x180043c5c  push    r12
0x180043c5e  push    r13
0x180043c60  push    r14
0x180043c62  push    r15
0x180043c64  sub     rsp, 980h
0x180043c6b  mov     rax, cs:__security_cookie
0x180043c72  xor     rax, rsp
0x180043c75  mov     [rsp+9A8h+var_38], rax
0x180043c7d  mov     r15d, [rcx+204h]
0x180043c84  xor     r13d, r13d
0x180043c87  mov     rsi, rdx
0x180043c8a  mov     [rsp+9A8h+lpItemData], r13
0x180043c8f  mov     rbx, rcx
0x180043c92  mov     [r11-920h], r13
0x180043c99  xorps   xmm0, xmm0
0x180043c9c  mov     [rsp+9A8h+NumRoutes], r13d
0x180043ca1  lea     r8d, [r13+60h]; Size
0x180043ca5  mov     [r11-928h], r13d
0x180043cac  xor     edx, edx; Val
0x180043cae  mov     [rsp+9A8h+var_950], r15d
0x180043cb3  lea     rcx, [r11-8D8h]; void *
0x180043cba  mov     [rsp+9A8h+dwItemSize], r13d
0x180043cbf  movups  xmmword ptr [rsp+9A8h+IoStatusBlock], xmm0
0x180043cc7  mov     [rsp+9A8h+dwItemCount], r13d
0x180043ccc  call    memset_0
0x180043cd1  xor     edx, edx; Val
0x180043cd3  mov     [rsp+9A8h+var_838], r13d
0x180043cdb  mov     r8d, 7FCh; Size
0x180043ce1  lea     rcx, [rsp+9A8h+var_834]; void *
0x180043ce9  call    memset_0
0x180043cee  mov     r11, cs:Microsoft_Windows_RRASEnableBits
0x180043cf5  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180043cfc  xor     eax, eax
0x180043cfe  mov     [rsp+9A8h+var_868], r13d
0x180043d06  xorps   xmm0, xmm0
0x180043d09  mov     [rsp+9A8h+var_844], eax
0x180043d10  mov     al, r11b
0x180043d13  lea     rdi, [rbx+2B0h]
0x180043d1a  and     al, 80h
0x180043d1c  mov     byte ptr [rsp+9A8h+var_958], al
0x180043d20  movups  [rsp+9A8h+var_864], xmm0
0x180043d28  movups  [rsp+9A8h+var_854], xmm0
0x180043d30  movups  [rsp+9A8h+var_878], xmm0
0x180043d38  jz      short loc_180043D85
0x180043d3a  lea     rax, [rsp+9A8h+var_868]
0x180043d42  mov     word ptr [rsp+9A8h+var_868], r13w
0x180043d4b  mov     qword ptr [rsp+9A8h+IoControlCode], rax
0x180043d50  lea     r9, [rsp+9A8h+var_878]
0x180043d58  mov     rax, [rbx+48h]
0x180043d5c  lea     r8, aEnteredSetrout_0; "Entered: SetRouteInfo"
0x180043d63  test    rdi, rdi
0x180043d66  mov     [rsp+9A8h+lplpItemData], rax
0x180043d6b  lea     rdx, RasRtrmgrParamTraceInfo
0x180043d72  mov     rcx, r12
0x180043d75  cmovnz  r9, rdi
0x180043d79  call    McTemplateU0zjzz_EventWriteTransfer
0x180043d7e  mov     r11, cs:Microsoft_Windows_RRASEnableBits
0x180043d85  cmp     dword ptr [rbx+0A8h], 1
0x180043d8c  jnz     short loc_180043DF1
0x180043d8e  test    r11b, r11b
0x180043d91  jns     loc_180044CF5
0x180043d97  mov     r8, [rbx+48h]
0x180043d9b  lea     rdx, aSetrouteinfoWs; "SetRouteInfo: %ws is unreachable, not s"...
0x180043da2  lea     rcx, [rsp+9A8h+var_838]
0x180043daa  mov     word ptr [rsp+9A8h+var_838], r13w
0x180043db3  mov     word ptr [rsp+9A8h+var_868], r13w
0x180043dbc  call    FormatRRASErrorString
0x180043dc1  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x180043dc8  jge     loc_180044CF5
0x180043dce  lea     rax, [rbx+2B0h]
0x180043dd5  test    rax, rax
0x180043dd8  lea     r9, [rsp+9A8h+var_878]
0x180043de0  lea     r8, [rsp+9A8h+var_838]
0x180043de8  cmovnz  r9, rax
0x180043dec  jmp     loc_180044CD0
0x180043df1  lea     rax, [rsp+9A8h+lpItemData]
0x180043df6  mov     rcx, rsi; lpHeader
0x180043df9  lea     r9, [rsp+9A8h+dwItemCount]; lpdwItemCount
0x180043dfe  mov     [rsp+9A8h+lplpItemData], rax; lplpItemData
0x180043e03  lea     r8, [rsp+9A8h+dwItemSize]; lpdwItemSize
0x180043e08  call    MprInfoBlockFind
0x180043e0d  test    eax, eax
0x180043e0f  jz      short loc_180043E36
0x180043e11  test    r11b, 80h
0x180043e15  jz      loc_180044CF5
0x180043e1b  lea     rax, [rbx+2B0h]
0x180043e22  test    rax, rax
0x180043e25  lea     r9, [rsp+9A8h+var_878]
0x180043e2d  cmovnz  r9, rax
0x180043e31  jmp     loc_180044CC0
0x180043e36  cmp     [rsp+9A8h+dwItemSize], r13d
0x180043e3b  jz      loc_180044C93
0x180043e41  mov     r14, [rsp+9A8h+lpItemData]
0x180043e46  test    r14, r14
0x180043e49  jz      loc_180044C93
0x180043e4f  mov     edx, [rsp+9A8h+dwItemCount]
0x180043e53  mov     r8d, 0FFFFFFFFh
0x180043e59  lea     rdi, ds:0[rdx*8]
0x180043e61  cmp     rdi, r8
0x180043e64  ja      loc_180044BB7
0x180043e6a  mov     eax, r15d
0x180043e6d  neg     eax
0x180043e6f  sbb     rcx, rcx
0x180043e72  and     rcx, 0FFFFFFFFFFFFFFF7h
0x180043e76  add     rcx, 11h
0x180043e7a  imul    rcx, rdx
0x180043e7e  cmp     rcx, r8
0x180043e81  ja      loc_180044BA2
0x180043e87  lea     r12d, [rcx+0Ch]
0x180043e8b  mov     [rsp+9A8h+var_958], r12d
0x180043e90  cmp     r12d, ecx
0x180043e93  jb      loc_180044B00
0x180043e99  mov     rcx, cs:IPRouterHeap; hHeap
0x180043ea0  xor     edx, edx; dwFlags
0x180043ea2  mov     r8d, r12d; dwBytes
0x180043ea5  mov     r15d, r12d
0x180043ea8  call    cs:__imp_HeapAlloc
0x180043eae  mov     [rsp+9A8h+lpItemData], rax
0x180043eb3  mov     r13, rax
0x180043eb6  test    rax, rax
0x180043eb9  jnz     loc_180043F57
0x180043ebf  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180043ec6  test    al, al
0x180043ec8  jns     loc_180043F50
0x180043ece  xor     eax, eax
0x180043ed0  lea     rdx, aSetrouteinfoEr_2; "SetRouteInfo: Error allocating %d bytes"...
0x180043ed7  mov     r8d, r12d
0x180043eda  mov     word ptr [rsp+9A8h+var_838], ax
0x180043ee2  lea     rcx, [rsp+9A8h+var_838]
0x180043eea  mov     word ptr [rsp+9A8h+var_868], ax
0x180043ef2  call    FormatRRASErrorString
0x180043ef7  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180043efe  test    al, al
0x180043f00  jns     short loc_180043F50
0x180043f02  lea     rax, [rbx+2B0h]
0x180043f09  test    rax, rax
0x180043f0c  lea     r9, [rsp+9A8h+var_878]
0x180043f14  lea     r8, [rsp+9A8h+var_838]
0x180043f1c  cmovnz  r9, rax
0x180043f20  lea     rdx, RasRtrmgrParamTraceInfo
0x180043f27  lea     rax, [rsp+9A8h+var_868]
0x180043f2f  mov     qword ptr [rsp+9A8h+IoControlCode], rax
0x180043f34  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180043f3b  mov     rax, [rbx+48h]
0x180043f3f  mov     [rsp+9A8h+lplpItemData], rax
0x180043f44  call    McTemplateU0zjzz_EventWriteTransfer
0x180043f49  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180043f50  test    al, 80h
0x180043f52  jmp     loc_1800441B4
0x180043f57  mov     r8, r15; Size
0x180043f5a  mov     esi, edi
0x180043f5c  xor     edx, edx; Val
0x180043f5e  mov     rcx, r13; void *
0x180043f61  call    memset_0
0x180043f66  xor     edi, edi
0x180043f68  mov     r8d, esi; dwBytes
0x180043f6b  mov     [r13+0], edi
0x180043f6f  mov     r15d, edi
0x180043f72  mov     eax, [rbx+58h]
0x180043f75  mov     [r13+4], eax
0x180043f79  lea     rax, [r13+0Ch]
0x180043f7d  mov     ecx, [rbx+204h]
0x180043f83  test    ecx, ecx
0x180043f85  mov     [r13+8], ecx
0x180043f89  cmovz   r15, rax
0x180043f8d  neg     ecx
0x180043f8f  mov     [rsp+9A8h+var_910], r15
0x180043f97  sbb     rcx, rcx
0x180043f9a  xor     edx, edx; dwFlags
0x180043f9c  and     rcx, rax
0x180043f9f  mov     [rsp+9A8h+var_940], rcx
0x180043fa4  mov     rcx, cs:IPRouterHeap; hHeap
0x180043fab  call    cs:__imp_HeapAlloc
0x180043fb1  mov     [rsp+9A8h+var_918], rax
0x180043fb9  mov     r15, rax
0x180043fbc  test    rax, rax
0x180043fbf  jnz     loc_1800440CB
0x180043fc5  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180043fcc  mov     dil, 40h ; '@'
0x180043fcf  test    dil, al
0x180043fd2  jz      loc_18004405B
0x180043fd8  xor     eax, eax
0x180043fda  lea     rdx, aSetrouteinfoEr_3; "SetRouteInfo: Error allocating %d bytes"...
0x180043fe1  mov     r8d, esi
0x180043fe4  mov     word ptr [rsp+9A8h+var_838], ax
0x180043fec  lea     rcx, [rsp+9A8h+var_838]
0x180043ff4  mov     word ptr [rsp+9A8h+var_868], ax
0x180043ffc  call    FormatRRASErrorString
0x180044001  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180044008  test    dil, al
0x18004400b  jz      short loc_18004405B
0x18004400d  lea     rax, [rbx+2B0h]
0x180044014  test    rax, rax
0x180044017  lea     r9, [rsp+9A8h+var_878]
0x18004401f  lea     r8, [rsp+9A8h+var_838]
0x180044027  cmovnz  r9, rax
0x18004402b  lea     rdx, RasRtrMgrParamTraceError
0x180044032  lea     rax, [rsp+9A8h+var_868]
0x18004403a  mov     qword ptr [rsp+9A8h+IoControlCode], rax
0x18004403f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180044046  mov     rax, [rbx+48h]
0x18004404a  mov     [rsp+9A8h+lplpItemData], rax
0x18004404f  call    McTemplateU0zjzz_EventWriteTransfer
0x180044054  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18004405b  test    al, 80h
0x18004405d  jz      short loc_1800440AF
0x18004405f  xor     eax, eax
0x180044061  lea     r9, [rsp+9A8h+var_878]
0x180044069  mov     word ptr [rsp+9A8h+var_868], ax
0x180044071  lea     r8, aLeavingSetrout_0; "Leaving: SetRouteInfo"
0x180044078  lea     rax, [rbx+2B0h]
0x18004407f  test    rax, rax
0x180044082  lea     rdx, RasRtrmgrParamTraceInfo
0x180044089  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180044090  cmovnz  r9, rax
0x180044094  lea     rax, [rsp+9A8h+var_868]
0x18004409c  mov     qword ptr [rsp+9A8h+IoControlCode], rax
0x1800440a1  mov     rax, [rbx+48h]
0x1800440a5  mov     [rsp+9A8h+lplpItemData], rax
0x1800440aa  call    McTemplateU0zjzz_EventWriteTransfer
0x1800440af  mov     rcx, cs:IPRouterHeap; hHeap
0x1800440b6  mov     r8, r13; lpMem
0x1800440b9  xor     edx, edx; dwFlags
0x1800440bb  call    cs:__imp_HeapFree
0x1800440c1  mov     eax, 8
0x1800440c6  jmp     loc_180044CF7
0x1800440cb  mov     eax, cs:g_rtmProfile.MaxHandlesInEnum
0x1800440d1  mov     ecx, 0FFFFFFFFh
0x1800440d6  shl     rax, 3
0x1800440da  cmp     rax, rcx
0x1800440dd  ja      loc_180044A64
0x1800440e3  mov     rcx, cs:IPRouterHeap; hHeap
0x1800440ea  xor     edx, edx; dwFlags
0x1800440ec  mov     r8d, eax; dwBytes
0x1800440ef  call    cs:__imp_HeapAlloc
0x1800440f5  mov     [rsp+9A8h+RouteHandles], rax
0x1800440fd  test    rax, rax
0x180044100  jnz     loc_18004420F
0x180044106  mov     dil, 40h ; '@'
0x180044109  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180044110  jz      short loc_180044189
0x180044112  mov     r8d, esi
0x180044115  mov     word ptr [rsp+9A8h+var_838], ax
0x18004411d  lea     rdx, aSetrouteinfoEr; "SetRouteInfo: Error allocating %d bytes"...
0x180044124  mov     word ptr [rsp+9A8h+var_868], ax
0x18004412c  lea     rcx, [rsp+9A8h+var_838]
0x180044134  call    FormatRRASErrorString
0x180044139  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180044140  jz      short loc_180044189
0x180044142  lea     rax, [rbx+2B0h]
0x180044149  test    rax, rax
0x18004414c  lea     r9, [rsp+9A8h+var_878]
0x180044154  lea     r8, [rsp+9A8h+var_838]
0x18004415c  cmovnz  r9, rax
0x180044160  lea     rdx, RasRtrMgrParamTraceError
0x180044167  lea     rax, [rsp+9A8h+var_868]
0x18004416f  mov     qword ptr [rsp+9A8h+IoControlCode], rax
0x180044174  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004417b  mov     rax, [rbx+48h]
0x18004417f  mov     [rsp+9A8h+lplpItemData], rax
0x180044184  call    McTemplateU0zjzz_EventWriteTransfer
0x180044189  mov     rcx, cs:IPRouterHeap; hHeap
0x180044190  mov     r8, r13; lpMem
0x180044193  xor     edx, edx; dwFlags
0x180044195  call    cs:__imp_HeapFree
0x18004419b  mov     rcx, cs:IPRouterHeap; hHeap
0x1800441a2  mov     r8, r15; lpMem
0x1800441a5  xor     edx, edx; dwFlags
0x1800441a7  call    cs:__imp_HeapFree
0x1800441ad  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800441b4  jz      loc_1800440C1
0x1800441ba  xor     eax, eax
0x1800441bc  lea     r9, [rsp+9A8h+var_878]
0x1800441c4  mov     word ptr [rsp+9A8h+var_868], ax
0x1800441cc  lea     r8, aLeavingSetrout_0; "Leaving: SetRouteInfo"
0x1800441d3  lea     rax, [rbx+2B0h]
0x1800441da  test    rax, rax
0x1800441dd  lea     rdx, RasRtrmgrParamTraceInfo
0x1800441e4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800441eb  cmovnz  r9, rax
0x1800441ef  lea     rax, [rsp+9A8h+var_868]
0x1800441f7  mov     qword ptr [rsp+9A8h+IoControlCode], rax
0x1800441fc  mov     rax, [rbx+48h]
0x180044200  mov     [rsp+9A8h+lplpItemData], rax
0x180044205  call    McTemplateU0zjzz_EventWriteTransfer
0x18004420a  jmp     loc_1800440C1
0x18004420f  mov     ecx, [rbx+90h]
0x180044215  lea     eax, [rcx-1]
0x180044218  cmp     eax, 1
0x18004421b  jbe     short loc_180044224
0x18004421d  cmp     ecx, 7
0x180044220  mov     ecx, edi
0x180044222  jnz     short loc_180044229
0x180044224  mov     ecx, 1
0x180044229  mov     r15d, edi
0x18004422c  mov     [rsp+9A8h+var_948], r15d
  ... truncated ...
```

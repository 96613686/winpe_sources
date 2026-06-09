# LoadIpForwardTable

- ea: `0x18002cc00`
- end: `0x18002d430`
- name: `LoadIpForwardTable`
- size: `2096`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000baa8`

## callees

- `0x18000ac60`
- `0x18002cc00`
- `0x18004a8d0`
- `0x180051ef8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `msvcrt!qsort` at `0x18002d22c`
- `msvcrt!qsort` at `0x18002d22c`
- `KERNEL32!HeapReAlloc` at `0x18002d120`
- `KERNEL32!HeapReAlloc` at `0x18002d120`
- `KERNEL32!HeapFree` at `0x18002cd95`
- `KERNEL32!HeapFree` at `0x18002cfcf`
- `KERNEL32!HeapFree` at `0x18002d074`
- `KERNEL32!HeapFree` at `0x18002d23e`
- `KERNEL32!HeapFree` at `0x18002d250`
- `KERNEL32!HeapFree` at `0x18002d262`
- `KERNEL32!HeapFree` at `0x18002d2dc`
- `KERNEL32!HeapFree` at `0x18002d332`
- `KERNEL32!HeapFree` at `0x18002d344`
- `KERNEL32!HeapFree` at `0x18002d356`
- `KERNEL32!HeapFree` at `0x18002d3f0`
- `KERNEL32!HeapFree` at `0x18002d402`
- `KERNEL32!HeapFree` at `0x18002cd95`
- `KERNEL32!HeapFree` at `0x18002cfcf`
- `KERNEL32!HeapFree` at `0x18002d074`
- `KERNEL32!HeapFree` at `0x18002d23e`
- `KERNEL32!HeapFree` at `0x18002d250`
- `KERNEL32!HeapFree` at `0x18002d262`
- `KERNEL32!HeapFree` at `0x18002d2dc`
- `KERNEL32!HeapFree` at `0x18002d332`
- `KERNEL32!HeapFree` at `0x18002d344`
- `KERNEL32!HeapFree` at `0x18002d356`
- `KERNEL32!HeapFree` at `0x18002d3f0`
- `KERNEL32!HeapFree` at `0x18002d402`
- `KERNEL32!HeapAlloc` at `0x18002cdb1`
- `KERNEL32!HeapAlloc` at `0x18002ced8`
- `KERNEL32!HeapAlloc` at `0x18002cf59`
- `KERNEL32!HeapAlloc` at `0x18002cffe`
- `KERNEL32!HeapAlloc` at `0x18002cdb1`
- `KERNEL32!HeapAlloc` at `0x18002ced8`
- `KERNEL32!HeapAlloc` at `0x18002cf59`
- `KERNEL32!HeapAlloc` at `0x18002cffe`
- `rtm!RtmGetAddressFamilyInfo` at `0x18002ccaf`
- `rtm!RtmGetAddressFamilyInfo` at `0x18002ccaf`
- `rtm!RtmReleaseRoutes` at `0x18002d1e2`
- `rtm!RtmReleaseRoutes` at `0x18002d30e`
- `rtm!RtmReleaseRoutes` at `0x18002d1e2`
- `rtm!RtmReleaseRoutes` at `0x18002d30e`
- `rtm!RtmGetEnumRoutes` at `0x18002d0a3`
- `rtm!RtmGetEnumRoutes` at `0x18002d0a3`
- `rtm!RtmCreateRouteEnum` at `0x18002cd40`
- `rtm!RtmCreateRouteEnum` at `0x18002cd40`
- `rtm!RtmDeleteEnumHandle` at `0x18002ce24`
- `rtm!RtmDeleteEnumHandle` at `0x18002cea4`
- `rtm!RtmDeleteEnumHandle` at `0x18002cf3c`
- `rtm!RtmDeleteEnumHandle` at `0x18002cfbd`
- `rtm!RtmDeleteEnumHandle` at `0x18002d062`
- `rtm!RtmDeleteEnumHandle` at `0x18002d1ff`
- `rtm!RtmDeleteEnumHandle` at `0x18002d320`
- `rtm!RtmDeleteEnumHandle` at `0x18002d3de`
- `rtm!RtmDeleteEnumHandle` at `0x18002ce24`
- `rtm!RtmDeleteEnumHandle` at `0x18002cea4`
- `rtm!RtmDeleteEnumHandle` at `0x18002cf3c`
- `rtm!RtmDeleteEnumHandle` at `0x18002cfbd`
- `rtm!RtmDeleteEnumHandle` at `0x18002d062`
- `rtm!RtmDeleteEnumHandle` at `0x18002d1ff`
- `rtm!RtmDeleteEnumHandle` at `0x18002d320`
- `rtm!RtmDeleteEnumHandle` at `0x18002d3de`
- `rtm!RtmReleaseRouteInfo` at `0x18002d1d1`
- `rtm!RtmReleaseRouteInfo` at `0x18002d2fa`
- `rtm!RtmReleaseRouteInfo` at `0x18002d1d1`
- `rtm!RtmReleaseRouteInfo` at `0x18002d2fa`
- `rtm!RtmReleaseNextHopInfo` at `0x18002d1b2`
- `rtm!RtmReleaseNextHopInfo` at `0x18002d1b2`
- `rtm!RtmGetNextHopInfo` at `0x18002d16d`
- `rtm!RtmGetNextHopInfo` at `0x18002d16d`
- `rtm!RtmGetEntityInfo` at `0x18002d146`
- `rtm!RtmGetEntityInfo` at `0x18002d146`
- `rtm!RtmGetRouteInfo` at `0x18002d0cd`
- `rtm!RtmGetRouteInfo` at `0x18002d0cd`

## string_xrefs

- `0x18002ce60`: `LoadIpForwardTable: RTMSIZEOFROUTEINFO returned error %d`

## pseudocode

```c
__int64 LoadIpForwardTable()
{
  DWORD AddressFamilyInfo; // ebx
  const wchar_t *v1; // rdx
  const wchar_t *v2; // r8
  __int64 *v3; // rdx
  int v5; // ebx
  unsigned int v6; // ebx
  __int64 v7; // rdi
  DWORD v8; // eax
  struct _RTM_ROUTE_INFO *v9; // rbx
  struct _RTM_NET_ADDRESS *v10; // r14
  void *v11; // r8
  unsigned __int64 v12; // rax
  HANDLE *v13; // r15
  unsigned int v14; // edi
  unsigned int i; // r12d
  unsigned int v16; // ecx
  unsigned int v17; // edx
  void *v18; // rax
  unsigned int j; // esi
  SIZE_T dwBytes; // [rsp+50h] [rbp-8D8h] BYREF
  HANDLE EnumHandle; // [rsp+58h] [rbp-8D0h] BYREF
  int v22; // [rsp+60h] [rbp-8C8h] BYREF
  struct _RTM_ENTITY_INFO EntityInfo; // [rsp+68h] [rbp-8C0h] BYREF
  struct _RTM_NEXTHOP_INFO NextHopInfo; // [rsp+78h] [rbp-8B0h] BYREF
  _OWORD v25[3]; // [rsp+B0h] [rbp-878h] BYREF
  int v26; // [rsp+E0h] [rbp-848h] BYREF
  _BYTE v27[2044]; // [rsp+E4h] [rbp-844h] BYREF

  EnumHandle = 0;
  memset(&NextHopInfo, 0, 52);
  v22 = 0;
  dwBytes = 0;
  v26 = 0;
  EntityInfo = 0;
  memset(v25, 0, 44);
  memset_0(v27, 0, sizeof(v27));
  AddressFamilyInfo = RtmGetAddressFamilyInfo(0, 2, v25, &v22, 0);
  if ( AddressFamilyInfo )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
      return AddressFamilyInfo;
    v1 = L"LoadIpForwardTable: Error %d getting number of destinations";
LABEL_4:
    LOWORD(v26) = 0;
    FormatRRASErrorString(&v26, v1, AddressFamilyInfo);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v2 = (const wchar_t *)&v26;
      v3 = RasRtrMgrTraceError;
LABEL_6:
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v3, v2);
    }
    return AddressFamilyInfo;
  }
  AddressFamilyInfo = RtmCreateRouteEnum(g_hLocalRoute, 0, 1u, 0, 0, 0, 0, 0, &EnumHandle);
  if ( AddressFamilyInfo )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
      return AddressFamilyInfo;
    v1 = L"LoadIpForwardTable: Error %d creating RTM enumeration handle";
    goto LABEL_4;
  }
  v5 = HIDWORD(v25[1]) + 10;
  if ( HIDWORD(v25[1]) + 10 > (unsigned int)dword_18008C7FC || (unsigned int)(dword_18008C7FC - v5) > 0xA )
  {
    if ( qword_18008C7E8 )
      HeapFree(g_hIpForwardHeap, 1u, qword_18008C7E8);
    v6 = v5 + 10;
    v7 = 56LL * v6;
    qword_18008C7E8 = HeapAlloc(g_hIpForwardHeap, 1u, v7 + 12);
    if ( !qword_18008C7E8 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v26) = 0;
        FormatRRASErrorString(&v26, L"LoadIpForwardTable: Error allocating %d bytes for forward table", v7 + 12);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v26);
      }
      dword_18008C7FC = 0;
      RtmDeleteEnumHandle(g_hLocalRoute, EnumHandle);
LABEL_72:
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: LoadIpForwardTable");
      return 8;
    }
    dword_18008C7FC = v6;
  }
  v8 = RTMSIZEOFROUTEINFO(g_rtmProfile.MaxNextHopsInRoute, &dwBytes);
  AddressFamilyInfo = v8;
  if ( v8 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v26) = 0;
      FormatRRASErrorString(&v26, L"LoadIpForwardTable: RTMSIZEOFROUTEINFO returned error %d", v8);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v26);
    }
    RtmDeleteEnumHandle(g_hLocalRoute, EnumHandle);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return AddressFamilyInfo;
    v2 = L"Leaving: LoadIpForwardTable";
    v3 = RasRtrmgrTraceInfo;
    goto LABEL_6;
  }
  v9 = (struct _RTM_ROUTE_INFO *)HeapAlloc(IPRouterHeap, 0, (unsigned int)dwBytes);
  if ( !v9 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"LoadIpForwardTable: pRoute is NULL ");
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: LoadIpForwardTable");
    }
    RtmDeleteEnumHandle(g_hLocalRoute, EnumHandle);
    return 8;
  }
  v10 = (struct _RTM_NET_ADDRESS *)HeapAlloc(IPRouterHeap, 0, 0x14u);
  if ( !v10 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"LoadIpForwardTable: pDestAddr is NULL");
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: LoadIpForwardTable");
    }
    RtmDeleteEnumHandle(g_hLocalRoute, EnumHandle);
    v11 = v9;
LABEL_38:
    HeapFree(IPRouterHeap, 0, v11);
    return 8;
  }
  v12 = 8LL * g_rtmProfile.MaxHandlesInEnum;
  if ( v12 > 0xFFFFFFFF )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"LoadIpForwardTable: Integer overflow");
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: LoadIpForwardTable");
    }
    RtmDeleteEnumHandle(g_hLocalRoute, EnumHandle);
    HeapFree(IPRouterHeap, 0, v9);
    HeapFree(IPRouterHeap, 0, v10);
    return 534;
  }
  else
  {
    v13 = (HANDLE *)HeapAlloc(IPRouterHeap, 0, (unsigned int)v12);
    if ( !v13 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"LoadIpForwardTable: hRoutes is NULL");
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasRtrmgrTraceInfo,
            L"Leaving: LoadIpForwardTable");
      }
      RtmDeleteEnumHandle(g_hLocalRoute, EnumHandle);
      HeapFree(IPRouterHeap, 0, v9);
      v11 = v10;
      goto LABEL_38;
    }
    v14 = 0;
    while ( 2 )
    {
      HIDWORD(dwBytes) = g_rtmProfile.MaxHandlesInEnum;
      RtmGetEnumRoutes(g_hLocalRoute, EnumHandle, (PUINT)&dwBytes + 1, v13);
      for ( i = 0; i < HIDWORD(dwBytes); ++i )
      {
        if ( !RtmGetRouteInfo(g_hLocalRoute, v13[i], v9, v10) )
        {
          if ( v14 + v9->NextHopsList.NumNextHops > dword_18008C7FC )
          {
            v16 = 2 * dword_18008C7FC;
            dword_18008C7FC = v16;
            v17 = v14 + v9->NextHopsList.NumNextHops;
            if ( v16 >= v17 )
              v17 = v16;
            else
              dword_18008C7FC = v14 + v9->NextHopsList.NumNextHops;
            v18 = HeapReAlloc(g_hIpForwardHeap, 1u, qword_18008C7E8, 56LL * v17 + 12);
            if ( !v18 )
            {
              if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
              {
                LOWORD(v26) = 0;
                FormatRRASErrorString(
                  &v26,
                  L"LoadIpForwardTable: Error reallocating %d bytes for forward table",
                  56LL * (unsigned int)dword_18008C7FC + 12);
                if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                  McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v26);
              }
              if ( qword_18008C7E8 )
                HeapFree(g_hIpForwardHeap, 1u, qword_18008C7E8);
              qword_18008C7E8 = 0;
              dword_18008C7FC = 0;
              RtmReleaseRouteInfo(g_hLocalRoute, v9);
              RtmReleaseRoutes(g_hLocalRoute, HIDWORD(dwBytes), v13);
              RtmDeleteEnumHandle(g_hLocalRoute, EnumHandle);
              HeapFree(IPRouterHeap, 0, v9);
              HeapFree(IPRouterHeap, 0, v10);
              HeapFree(IPRouterHeap, 0, v13);
              goto LABEL_72;
            }
            qword_18008C7E8 = v18;
          }
          if ( !RtmGetEntityInfo(g_hLocalRoute, v9->RouteOwner, &EntityInfo) )
          {
            for ( j = 0; j < v9->NextHopsList.NumNextHops; ++j )
            {
              if ( !RtmGetNextHopInfo(g_hLocalRoute, v9->NextHopsList.NextHops[j], &NextHopInfo) )
              {
                ConvertRtmToMibRoute(
                  EntityInfo.EntityId.EntityProtocolId,
                  (_DWORD)v10,
                  (_DWORD)v9,
                  (unsigned int)&NextHopInfo,
                  (__int64)qword_18008C7E8 + 56 * v14++ + 4);
                RtmReleaseNextHopInfo(g_hLocalRoute, &NextHopInfo);
              }
            }
          }
          RtmReleaseRouteInfo(g_hLocalRoute, v9);
        }
      }
      RtmReleaseRoutes(g_hLocalRoute, HIDWORD(dwBytes), v13);
      if ( HIDWORD(dwBytes) )
        continue;
      break;
    }
    RtmDeleteEnumHandle(g_hLocalRoute, EnumHandle);
    *(_DWORD *)qword_18008C7E8 = v14;
    if ( v14 )
      qsort((char *)qword_18008C7E8 + 4, v14, 0x38u, CompareIpForwardRow);
    HeapFree(IPRouterHeap, 0, v9);
    HeapFree(IPRouterHeap, 0, v10);
    HeapFree(IPRouterHeap, 0, v13);
    return 0;
  }
}

```

## disassembly

```asm
0x18002cc00  push    rbx
0x18002cc02  push    rsi
0x18002cc03  push    rdi
0x18002cc04  push    r12
0x18002cc06  push    r13
0x18002cc08  push    r14
0x18002cc0a  push    r15
0x18002cc0c  sub     rsp, 8F0h
0x18002cc13  mov     rax, cs:__security_cookie
0x18002cc1a  xor     rax, rsp
0x18002cc1d  mov     [rsp+928h+var_48], rax
0x18002cc25  xorps   xmm0, xmm0
0x18002cc28  lea     rcx, [rsp+928h+var_844]; void *
0x18002cc30  xor     r13d, r13d
0x18002cc33  xor     eax, eax
0x18002cc35  movups  xmmword ptr [rsp+928h+var_868], xmm0
0x18002cc3d  xor     edx, edx; Val
0x18002cc3f  mov     [rsp+928h+EnumHandle], r13
0x18002cc44  mov     r8d, 7FCh; Size
0x18002cc4a  mov     dword ptr [rsp+928h+NextHopInfo.RemoteNextHop], eax
0x18002cc51  movups  xmmword ptr [rsp+928h+var_868+0Ch], xmm0
0x18002cc59  mov     dword ptr [rsp+928h+dwBytes+4], r13d
0x18002cc5e  movups  xmmword ptr [rsp+928h+NextHopInfo.NextHopAddress.AddressFamily], xmm0
0x18002cc63  mov     [rsp+928h+var_8C8], r13d
0x18002cc68  movups  xmmword ptr [rsp+928h+NextHopInfo.NextHopAddress.AddrBits+0Ch], xmm0
0x18002cc70  mov     dword ptr [rsp+928h+dwBytes], r13d
0x18002cc75  movups  xmmword ptr [rsp+928h+NextHopInfo.InterfaceIndex], xmm0
0x18002cc7d  mov     [rsp+928h+var_848], r13d
0x18002cc85  movups  xmmword ptr [rsp+928h+EntityInfo.RtmInstanceId], xmm0
0x18002cc8a  movups  [rsp+928h+var_878], xmm0
0x18002cc92  call    memset_0
0x18002cc97  lea     edx, [r13+2]
0x18002cc9b  mov     [rsp+928h+StartDest], r13
0x18002cca0  xor     ecx, ecx
0x18002cca2  lea     r9, [rsp+928h+var_8C8]
0x18002cca7  lea     r8, [rsp+928h+var_878]
0x18002ccaf  call    cs:__imp_RtmGetAddressFamilyInfo
0x18002ccb5  mov     ebx, eax
0x18002ccb7  test    eax, eax
0x18002ccb9  jz      short loc_18002CD0F
0x18002ccbb  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002ccc2  jz      short loc_18002CD08
0x18002ccc4  lea     rdx, aLoadipforwardt; "LoadIpForwardTable: Error %d getting nu"...
0x18002cccb  mov     r8d, ebx
0x18002ccce  mov     word ptr [rsp+928h+var_848], r13w
0x18002ccd7  lea     rcx, [rsp+928h+var_848]
0x18002ccdf  call    FormatRRASErrorString
0x18002cce4  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002cceb  jz      short loc_18002CD08
0x18002cced  lea     r8, [rsp+928h+var_848]
0x18002ccf5  lea     rdx, RasRtrMgrTraceError
0x18002ccfc  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002cd03  call    McTemplateU0z_EventWriteTransfer
0x18002cd08  mov     eax, ebx
0x18002cd0a  jmp     loc_18002D40D
0x18002cd0f  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x18002cd16  lea     rax, [rsp+928h+EnumHandle]
0x18002cd1b  mov     [rsp+928h+RtmEnumHandle], rax; RtmEnumHandle
0x18002cd20  xor     r9d, r9d; EnumFlags
0x18002cd23  mov     [rsp+928h+CriteriaInterface], r13d; CriteriaInterface
0x18002cd28  xor     edx, edx; DestHandle
0x18002cd2a  mov     [rsp+928h+CriteriaRoute], r13; CriteriaRoute
0x18002cd2f  mov     [rsp+928h+MatchingFlags], r13d; MatchingFlags
0x18002cd34  lea     esi, [r9+1]
0x18002cd38  mov     [rsp+928h+StartDest], r13; StartDest
0x18002cd3d  mov     r8d, esi; TargetViews
0x18002cd40  call    cs:__imp_RtmCreateRouteEnum
0x18002cd46  mov     ebx, eax
0x18002cd48  test    eax, eax
0x18002cd4a  jz      short loc_18002CD61
0x18002cd4c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002cd53  jz      short loc_18002CD08
0x18002cd55  lea     rdx, aLoadipforwardt_0; "LoadIpForwardTable: Error %d creating R"...
0x18002cd5c  jmp     loc_18002CCCB
0x18002cd61  mov     ebx, dword ptr [rsp+928h+var_868+0Ch]
0x18002cd68  mov     eax, cs:dword_18008C7FC
0x18002cd6e  add     ebx, 0Ah
0x18002cd71  cmp     ebx, eax
0x18002cd73  ja      short loc_18002CD80
0x18002cd75  sub     eax, ebx
0x18002cd77  cmp     eax, 0Ah
0x18002cd7a  jbe     loc_18002CE35
0x18002cd80  mov     r8, cs:qword_18008C7E8; lpMem
0x18002cd87  test    r8, r8
0x18002cd8a  jz      short loc_18002CD9B
0x18002cd8c  mov     rcx, cs:g_hIpForwardHeap; hHeap
0x18002cd93  mov     edx, esi; dwFlags
0x18002cd95  call    cs:__imp_HeapFree
0x18002cd9b  mov     rcx, cs:g_hIpForwardHeap; hHeap
0x18002cda2  add     ebx, 0Ah
0x18002cda5  mov     eax, ebx
0x18002cda7  mov     edx, esi; dwFlags
0x18002cda9  imul    rdi, rax, 38h ; '8'
0x18002cdad  lea     r8, [rdi+0Ch]; dwBytes
0x18002cdb1  call    cs:__imp_HeapAlloc
0x18002cdb7  mov     cs:qword_18008C7E8, rax
0x18002cdbe  test    rax, rax
0x18002cdc1  jnz     short loc_18002CE2F
0x18002cdc3  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002cdca  jz      short loc_18002CE11
0x18002cdcc  lea     r8, [rdi+0Ch]
0x18002cdd0  mov     word ptr [rsp+928h+var_848], r13w
0x18002cdd9  lea     rdx, aLoadipforwardt_4; "LoadIpForwardTable: Error allocating %d"...
0x18002cde0  lea     rcx, [rsp+928h+var_848]
0x18002cde8  call    FormatRRASErrorString
0x18002cded  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002cdf4  jz      short loc_18002CE11
0x18002cdf6  lea     r8, [rsp+928h+var_848]
0x18002cdfe  lea     rdx, RasRtrMgrTraceError
0x18002ce05  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002ce0c  call    McTemplateU0z_EventWriteTransfer
0x18002ce11  mov     rdx, [rsp+928h+EnumHandle]; EnumHandle
0x18002ce16  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x18002ce1d  mov     cs:dword_18008C7FC, r13d
0x18002ce24  call    cs:__imp_RtmDeleteEnumHandle
0x18002ce2a  jmp     loc_18002D35C
0x18002ce2f  mov     cs:dword_18008C7FC, ebx
0x18002ce35  mov     ecx, cs:g_rtmProfile.MaxNextHopsInRoute
0x18002ce3b  lea     rdx, [rsp+928h+dwBytes]
0x18002ce40  call    RTMSIZEOFROUTEINFO
0x18002ce45  mov     ebx, eax
0x18002ce47  test    eax, eax
0x18002ce49  jz      short loc_18002CECA
0x18002ce4b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002ce52  jz      short loc_18002CE98
0x18002ce54  mov     r8d, eax
0x18002ce57  mov     word ptr [rsp+928h+var_848], r13w
0x18002ce60  lea     rdx, aLoadipforwardt_3; "LoadIpForwardTable: RTMSIZEOFROUTEINFO "...
0x18002ce67  lea     rcx, [rsp+928h+var_848]
0x18002ce6f  call    FormatRRASErrorString
0x18002ce74  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002ce7b  jz      short loc_18002CE98
0x18002ce7d  lea     r8, [rsp+928h+var_848]
0x18002ce85  lea     rdx, RasRtrMgrTraceError
0x18002ce8c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002ce93  call    McTemplateU0z_EventWriteTransfer
0x18002ce98  mov     rdx, [rsp+928h+EnumHandle]; EnumHandle
0x18002ce9d  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x18002cea4  call    cs:__imp_RtmDeleteEnumHandle
0x18002ceaa  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18002ceb1  jz      loc_18002CD08
0x18002ceb7  lea     r8, aLeavingLoadipf; "Leaving: LoadIpForwardTable"
0x18002cebe  lea     rdx, RasRtrmgrTraceInfo
0x18002cec5  jmp     loc_18002CCFC
0x18002ceca  mov     r8d, dword ptr [rsp+928h+dwBytes]; dwBytes
0x18002cecf  xor     edx, edx; dwFlags
0x18002ced1  mov     rcx, cs:IPRouterHeap; hHeap
0x18002ced8  call    cs:__imp_HeapAlloc
0x18002cede  mov     rbx, rax
0x18002cee1  test    rax, rax
0x18002cee4  jnz     short loc_18002CF4C
0x18002cee6  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18002ceed  test    al, 80h
0x18002ceef  jz      short loc_18002CF30
0x18002cef1  lea     r8, aLoadipforwardt_2; "LoadIpForwardTable: pRoute is NULL "
0x18002cef8  lea     rdx, RasRtrmgrTraceInfo
0x18002ceff  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002cf06  call    McTemplateU0z_EventWriteTransfer
0x18002cf0b  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18002cf12  test    al, 80h
0x18002cf14  jz      short loc_18002CF30
0x18002cf16  lea     r8, aLeavingLoadipf; "Leaving: LoadIpForwardTable"
0x18002cf1d  lea     rdx, RasRtrmgrTraceInfo
0x18002cf24  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002cf2b  call    McTemplateU0z_EventWriteTransfer
0x18002cf30  mov     rdx, [rsp+928h+EnumHandle]; EnumHandle
0x18002cf35  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x18002cf3c  call    cs:__imp_RtmDeleteEnumHandle
0x18002cf42  mov     eax, 8
0x18002cf47  jmp     loc_18002D40D
0x18002cf4c  mov     rcx, cs:IPRouterHeap; hHeap
0x18002cf53  xor     edx, edx; dwFlags
0x18002cf55  lea     r8d, [rdx+14h]; dwBytes
0x18002cf59  call    cs:__imp_HeapAlloc
0x18002cf5f  mov     r14, rax
0x18002cf62  test    rax, rax
0x18002cf65  jnz     short loc_18002CFDA
0x18002cf67  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18002cf6e  test    al, 80h
0x18002cf70  jz      short loc_18002CFB1
0x18002cf72  lea     r8, aLoadipforwardt_1; "LoadIpForwardTable: pDestAddr is NULL"
0x18002cf79  lea     rdx, RasRtrmgrTraceInfo
0x18002cf80  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002cf87  call    McTemplateU0z_EventWriteTransfer
0x18002cf8c  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18002cf93  test    al, 80h
0x18002cf95  jz      short loc_18002CFB1
0x18002cf97  lea     r8, aLeavingLoadipf; "Leaving: LoadIpForwardTable"
0x18002cf9e  lea     rdx, RasRtrmgrTraceInfo
0x18002cfa5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002cfac  call    McTemplateU0z_EventWriteTransfer
0x18002cfb1  mov     rdx, [rsp+928h+EnumHandle]; EnumHandle
0x18002cfb6  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x18002cfbd  call    cs:__imp_RtmDeleteEnumHandle
0x18002cfc3  mov     r8, rbx; lpMem
0x18002cfc6  mov     rcx, cs:IPRouterHeap; hHeap
0x18002cfcd  xor     edx, edx; dwFlags
0x18002cfcf  call    cs:__imp_HeapFree
0x18002cfd5  jmp     loc_18002CF42
0x18002cfda  mov     eax, cs:g_rtmProfile.MaxHandlesInEnum
0x18002cfe0  mov     ecx, 0FFFFFFFFh
0x18002cfe5  shl     rax, 3
0x18002cfe9  cmp     rax, rcx
0x18002cfec  ja      loc_18002D388
0x18002cff2  mov     rcx, cs:IPRouterHeap; hHeap
0x18002cff9  xor     edx, edx; dwFlags
0x18002cffb  mov     r8d, eax; dwBytes
0x18002cffe  call    cs:__imp_HeapAlloc
0x18002d004  mov     r15, rax
0x18002d007  test    rax, rax
0x18002d00a  jnz     short loc_18002D082
0x18002d00c  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18002d013  test    al, 80h
0x18002d015  jz      short loc_18002D056
0x18002d017  lea     r8, aLoadipforwardt_5; "LoadIpForwardTable: hRoutes is NULL"
0x18002d01e  lea     rdx, RasRtrmgrTraceInfo
0x18002d025  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002d02c  call    McTemplateU0z_EventWriteTransfer
0x18002d031  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18002d038  test    al, 80h
0x18002d03a  jz      short loc_18002D056
0x18002d03c  lea     r8, aLeavingLoadipf; "Leaving: LoadIpForwardTable"
0x18002d043  lea     rdx, RasRtrmgrTraceInfo
0x18002d04a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002d051  call    McTemplateU0z_EventWriteTransfer
0x18002d056  mov     rdx, [rsp+928h+EnumHandle]; EnumHandle
0x18002d05b  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x18002d062  call    cs:__imp_RtmDeleteEnumHandle
0x18002d068  mov     rcx, cs:IPRouterHeap; hHeap
0x18002d06f  mov     r8, rbx; lpMem
0x18002d072  xor     edx, edx; dwFlags
0x18002d074  call    cs:__imp_HeapFree
0x18002d07a  mov     r8, r14
0x18002d07d  jmp     loc_18002CFC6
0x18002d082  mov     edi, r13d
0x18002d085  mov     eax, cs:g_rtmProfile.MaxHandlesInEnum
0x18002d08b  lea     r8, [rsp+928h+dwBytes+4]; NumRoutes
0x18002d090  mov     rdx, [rsp+928h+EnumHandle]; EnumHandle
0x18002d095  mov     r9, r15; RouteHandles
0x18002d098  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x18002d09f  mov     dword ptr [rsp+928h+dwBytes+4], eax
0x18002d0a3  call    cs:__imp_RtmGetEnumRoutes
0x18002d0a9  mov     r12d, r13d
0x18002d0ac  mov     edx, dword ptr [rsp+928h+dwBytes+4]; NumRoutes
0x18002d0b0  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x18002d0b7  cmp     r12d, edx
0x18002d0ba  jnb     loc_18002D1DF
0x18002d0c0  mov     edx, r12d
0x18002d0c3  mov     r9, r14; DestAddress
0x18002d0c6  mov     r8, rbx; RouteInfo
0x18002d0c9  mov     rdx, [r15+rdx*8]; RouteHandle
0x18002d0cd  call    cs:__imp_RtmGetRouteInfo
0x18002d0d3  test    eax, eax
0x18002d0d5  jnz     loc_18002D1D7
0x18002d0db  movzx   eax, word ptr [rbx+30h]
0x18002d0df  mov     ecx, cs:dword_18008C7FC
0x18002d0e5  add     eax, edi
0x18002d0e7  cmp     eax, ecx
0x18002d0e9  jbe     short loc_18002D136
0x18002d0eb  add     ecx, ecx
0x18002d0ed  mov     cs:dword_18008C7FC, ecx
0x18002d0f3  movzx   edx, word ptr [rbx+30h]
0x18002d0f7  add     edx, edi
0x18002d0f9  cmp     ecx, edx
0x18002d0fb  jnb     short loc_18002D103
0x18002d0fd  mov     cs:dword_18008C7FC, edx
0x18002d103  mov     r8, cs:qword_18008C7E8; lpMem
0x18002d10a  cmovnb  edx, ecx
0x18002d10d  mov     rcx, cs:g_hIpForwardHeap; hHeap
0x18002d114  mov     eax, edx
0x18002d116  mov     edx, esi; dwFlags
0x18002d118  imul    r9, rax, 38h ; '8'
0x18002d11c  add     r9, 0Ch; dwBytes
0x18002d120  call    cs:__imp_HeapReAlloc
0x18002d126  test    rax, rax
0x18002d129  jz      loc_18002D26F
0x18002d12f  mov     cs:qword_18008C7E8, rax
0x18002d136  mov     rdx, [rbx+8]; EntityHandle
0x18002d13a  lea     r8, [rsp+928h+EntityInfo]; EntityInfo
0x18002d13f  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x18002d146  call    cs:__imp_RtmGetEntityInfo
0x18002d14c  test    eax, eax
0x18002d14e  jnz     short loc_18002D1C7
0x18002d150  mov     esi, r13d
0x18002d153  cmp     r13w, [rbx+30h]
0x18002d158  jnb     short loc_18002D1C2
0x18002d15a  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x18002d161  lea     r8, [rsp+928h+NextHopInfo]; NextHopInfo
0x18002d166  mov     edx, esi
0x18002d168  mov     rdx, [rbx+rdx*8+38h]; NextHopHandle
0x18002d16d  call    cs:__imp_RtmGetNextHopInfo
0x18002d173  test    eax, eax
0x18002d175  jnz     short loc_18002D1B8
0x18002d177  mov     eax, edi
0x18002d179  lea     r9, [rsp+928h+NextHopInfo]
0x18002d17e  imul    rcx, rax, 38h ; '8'
0x18002d182  mov     rax, cs:qword_18008C7E8
0x18002d189  mov     r8, rbx
0x18002d18c  add     rax, 4
0x18002d190  mov     rdx, r14
  ... truncated ...
```

# ReadAllStaticRoutesIntoBuffer

- ea: `0x180042f3c`
- end: `0x180043399`
- name: `ReadAllStaticRoutesIntoBuffer`
- size: `1117`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180040e14`

## callees

- `0x180011790`
- `0x180042f3c`
- `0x18004aa08`
- `0x180051ef8`
- `0x180057aa4`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180043069`
- `KERNEL32!HeapFree` at `0x180043096`
- `KERNEL32!HeapFree` at `0x1800432e7`
- `KERNEL32!HeapFree` at `0x1800432f9`
- `KERNEL32!HeapFree` at `0x18004330d`
- `KERNEL32!HeapFree` at `0x18004331b`
- `KERNEL32!HeapFree` at `0x180043069`
- `KERNEL32!HeapFree` at `0x180043096`
- `KERNEL32!HeapFree` at `0x1800432e7`
- `KERNEL32!HeapFree` at `0x1800432f9`
- `KERNEL32!HeapFree` at `0x18004330d`
- `KERNEL32!HeapFree` at `0x18004331b`
- `KERNEL32!HeapAlloc` at `0x180043019`
- `KERNEL32!HeapAlloc` at `0x18004304f`
- `KERNEL32!HeapAlloc` at `0x18004307a`
- `KERNEL32!HeapAlloc` at `0x180043019`
- `KERNEL32!HeapAlloc` at `0x18004304f`
- `KERNEL32!HeapAlloc` at `0x18004307a`
- `rtm!RtmReleaseRoutes` at `0x1800432a2`
- `rtm!RtmReleaseRoutes` at `0x1800432a2`
- `rtm!RtmGetEnumRoutes` at `0x1800431e9`
- `rtm!RtmGetEnumRoutes` at `0x1800431e9`
- `rtm!RtmCreateRouteEnum` at `0x18004313f`
- `rtm!RtmCreateRouteEnum` at `0x18004313f`
- `rtm!RtmDeleteEnumHandle` at `0x1800432c0`
- `rtm!RtmDeleteEnumHandle` at `0x1800432c0`
- `rtm!RtmReleaseRouteInfo` at `0x180043288`
- `rtm!RtmReleaseRouteInfo` at `0x180043288`
- `rtm!RtmReleaseNextHopInfo` at `0x18004327c`
- `rtm!RtmReleaseNextHopInfo` at `0x18004327c`
- `rtm!RtmGetNextHopInfo` at `0x180043241`
- `rtm!RtmGetNextHopInfo` at `0x180043241`
- `rtm!RtmGetEntityInfo` at `0x18004322c`
- `rtm!RtmGetEntityInfo` at `0x18004322c`
- `rtm!RtmGetRouteInfo` at `0x180043217`
- `rtm!RtmGetRouteInfo` at `0x180043217`

## string_xrefs

- `0x18004333d`: `ReadAllStaticRoutesIntoBuffer: Integer Overflow`
- `0x18004315b`: `ReadAllStaticRoutesIntoBuffer: Error %d creating handle for %d\n`

## pseudocode

```c
__int64 __fastcall ReadAllStaticRoutesIntoBuffer(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned int v3; // r12d
  unsigned int v4; // esi
  __int64 v5; // r13
  int v6; // r15d
  struct _RTM_ROUTE_INFO *v7; // rbx
  unsigned __int64 v8; // rax
  HANDLE *v9; // rax
  HANDLE v10; // rcx
  HANDLE *v11; // r14
  struct _RTM_ROUTE_INFO *v12; // r8
  unsigned int v13; // r15d
  void *v14; // rdi
  DWORD v15; // eax
  __int64 v16; // r9
  __int128 *v17; // r9
  struct _RTM_NET_ADDRESS *v18; // r13
  unsigned int v19; // r12d
  DWORD EnumRoutes; // eax
  UINT v21; // edx
  __int64 v22; // rsi
  __int128 *v24; // r9
  SIZE_T dwBytes; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v26; // [rsp+58h] [rbp-A8h]
  DWORD i; // [rsp+5Ch] [rbp-A4h]
  int v28; // [rsp+60h] [rbp-A0h]
  HANDLE EnumHandle; // [rsp+68h] [rbp-98h] BYREF
  PRTM_NET_ADDRESS DestAddress; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+78h] [rbp-88h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  _DWORD v33[2]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD RtmRegHandle[11]; // [rsp+98h] [rbp-68h]
  struct _RTM_ENTITY_INFO EntityInfo; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v36; // [rsp+100h] [rbp+0h] BYREF
  struct _RTM_NEXTHOP_INFO NextHopInfo; // [rsp+110h] [rbp+10h] BYREF
  int v38; // [rsp+148h] [rbp+48h] BYREF
  __int128 v39; // [rsp+14Ch] [rbp+4Ch]
  __int128 v40; // [rsp+15Ch] [rbp+5Ch]
  int v41; // [rsp+16Ch] [rbp+6Ch]
  int v42; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v43[2044]; // [rsp+174h] [rbp+74h] BYREF

  v26 = a3;
  v3 = 0;
  v31 = a2;
  v4 = a3;
  v32 = a1;
  v5 = a1;
  EnumHandle = 0;
  dwBytes = 0;
  memset(&NextHopInfo, 0, 52);
  EntityInfo = 0;
  memset_0(v33, 0, 0x60u);
  v42 = 0;
  memset_0(v43, 0, sizeof(v43));
  v38 = 0;
  v39 = 0;
  v41 = 0;
  v40 = 0;
  v36 = 0;
  if ( (unsigned int)RTMSIZEOFROUTEINFO(g_rtmProfile.MaxNextHopsInRoute, &dwBytes) )
    return 0;
  v6 = *(_DWORD *)(v5 + 516);
  v28 = v6;
  v7 = (struct _RTM_ROUTE_INFO *)HeapAlloc(IPRouterHeap, 0, (unsigned int)dwBytes);
  if ( !v7 )
    return 0;
  v8 = 8LL * g_rtmProfile.MaxHandlesInEnum;
  if ( v8 > 0xFFFFFFFF )
  {
    HeapFree(IPRouterHeap, 0, v7);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v38) = 0;
      v24 = &v36;
      if ( v5 != -688 )
        LODWORD(v24) = v5 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)L"ReadAllStaticRoutesIntoBuffer: Integer Overflow",
        (_DWORD)v24,
        *(_QWORD *)(v5 + 72),
        (__int64)&v38);
    }
    return 0;
  }
  v9 = (HANDLE *)HeapAlloc(IPRouterHeap, 0, (unsigned int)v8);
  v10 = IPRouterHeap;
  v11 = v9;
  if ( !v9 )
  {
    v12 = v7;
LABEL_6:
    HeapFree(v10, 0, v12);
    return 0;
  }
  DestAddress = (PRTM_NET_ADDRESS)HeapAlloc(IPRouterHeap, 0, 0x14u);
  if ( !DestAddress )
  {
    HeapFree(IPRouterHeap, 0, v7);
    v10 = IPRouterHeap;
    v12 = (struct _RTM_ROUTE_INFO *)v11;
    goto LABEL_6;
  }
  GetAllRtmRegistrationHandles(v5 + 688, v6 != 0 ? 33 : 87, v33);
  v13 = 0;
  while ( 1 )
  {
    LODWORD(dwBytes) = v3;
    if ( v3 >= 5 || v13 >= v4 )
      break;
    if ( v33[4 * v3 + 1] )
    {
      v14 = (void *)RtmRegHandle[2 * v3];
      v15 = RtmCreateRouteEnum(v14, 0, v28 != 0 ? 3 : 1, 0x10000u, 0, 0x10u, 0, *(_DWORD *)(v5 + 16), &EnumHandle);
      if ( v15 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v16 = (unsigned int)v33[4 * v3];
          LOWORD(v42) = 0;
          LOWORD(v38) = 0;
          FormatRRASErrorString(&v42, L"ReadAllStaticRoutesIntoBuffer: Error %d creating handle for %d\n", v15, v16);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            v17 = &v36;
            if ( v5 != -688 )
              LODWORD(v17) = v5 + 688;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrMgrParamTraceError,
              (unsigned int)&v42,
              (_DWORD)v17,
              *(_QWORD *)(v5 + 72),
              (__int64)&v38);
          }
        }
      }
      else
      {
        v18 = DestAddress;
        v19 = v26;
        do
        {
          HIDWORD(dwBytes) = g_rtmProfile.MaxHandlesInEnum;
          EnumRoutes = RtmGetEnumRoutes(v14, EnumHandle, (PUINT)&dwBytes + 1, v11);
          v21 = HIDWORD(dwBytes);
          v22 = 0;
          for ( i = EnumRoutes; (unsigned int)v22 < HIDWORD(dwBytes); v22 = (unsigned int)(v22 + 1) )
          {
            if ( v13 >= v19 )
              break;
            if ( !RtmGetRouteInfo(v14, v11[v22], v7, v18) )
            {
              if ( !RtmGetEntityInfo(v14, v7->RouteOwner, &EntityInfo)
                && !RtmGetNextHopInfo(v14, v7->NextHopsList.NextHops[0], &NextHopInfo) )
              {
                ConvertRtmToRouteInfo(EntityInfo.EntityId.EntityProtocolId, v18, v7, &NextHopInfo, v31 + 72LL * v13++);
                RtmReleaseNextHopInfo(v14, &NextHopInfo);
              }
              RtmReleaseRouteInfo(v14, v7);
            }
            v21 = HIDWORD(dwBytes);
          }
          RtmReleaseRoutes(v14, v21, v11);
        }
        while ( !i && v13 < v19 );
        RtmDeleteEnumHandle(v14, EnumHandle);
        v5 = v32;
        v3 = dwBytes;
      }
    }
    v4 = v26;
    ++v3;
  }
  HeapFree(IPRouterHeap, 0, v7);
  HeapFree(IPRouterHeap, 0, v11);
  HeapFree(IPRouterHeap, 0, DestAddress);
  return v13;
}

```

## disassembly

```asm
0x180042f3c  mov     [rsp-8+arg_10], rbx
0x180042f41  push    rbp
0x180042f42  push    rsi
0x180042f43  push    rdi
0x180042f44  push    r12
0x180042f46  push    r13
0x180042f48  push    r14
0x180042f4a  push    r15
0x180042f4c  lea     rbp, [rsp-880h]
0x180042f54  sub     rsp, 980h
0x180042f5b  mov     rax, cs:__security_cookie
0x180042f62  xor     rax, rsp
0x180042f65  mov     [rbp+8B0h+var_40], rax
0x180042f6c  xorps   xmm0, xmm0
0x180042f6f  mov     [rsp+9B0h+var_958], r8d
0x180042f74  xor     r12d, r12d
0x180042f77  mov     [rsp+9B0h+var_938], rdx
0x180042f7c  mov     esi, r8d
0x180042f7f  mov     [rbp+8B0h+var_930], rcx
0x180042f83  mov     r13, rcx
0x180042f86  mov     [rsp+9B0h+EnumHandle], r12
0x180042f8b  xor     eax, eax
0x180042f8d  mov     dword ptr [rsp+9B0h+dwBytes+4], r12d
0x180042f92  lea     r8d, [r12+60h]; Size
0x180042f97  mov     dword ptr [rbp+8B0h+NextHopInfo.RemoteNextHop], eax
0x180042f9a  xor     edx, edx; Val
0x180042f9c  mov     dword ptr [rsp+9B0h+dwBytes], r12d
0x180042fa1  lea     rcx, [rbp+8B0h+var_920]; void *
0x180042fa5  movups  xmmword ptr [rbp+8B0h+NextHopInfo.NextHopAddress.AddressFamily], xmm0
0x180042fa9  movups  xmmword ptr [rbp+8B0h+NextHopInfo.NextHopAddress.AddrBits+0Ch], xmm0
0x180042fad  movups  xmmword ptr [rbp+8B0h+NextHopInfo.InterfaceIndex], xmm0
0x180042fb1  movups  xmmword ptr [rbp+8B0h+EntityInfo.RtmInstanceId], xmm0
0x180042fb5  call    memset_0
0x180042fba  xor     edx, edx; Val
0x180042fbc  mov     [rbp+8B0h+var_840], r12d
0x180042fc0  mov     r8d, 7FCh; Size
0x180042fc6  lea     rcx, [rbp+8B0h+var_83C]; void *
0x180042fca  call    memset_0
0x180042fcf  mov     ecx, cs:g_rtmProfile.MaxNextHopsInRoute
0x180042fd5  lea     rdx, [rsp+9B0h+dwBytes]
0x180042fda  xorps   xmm0, xmm0
0x180042fdd  mov     [rbp+8B0h+var_868], r12d
0x180042fe1  xor     eax, eax
0x180042fe3  movups  [rbp+8B0h+var_864], xmm0
0x180042fe7  mov     [rbp+8B0h+var_844], eax
0x180042fea  movups  [rbp+8B0h+var_854], xmm0
0x180042fee  movups  [rbp+8B0h+var_8B0], xmm0
0x180042ff2  call    RTMSIZEOFROUTEINFO
0x180042ff7  test    eax, eax
0x180042ff9  jnz     loc_18004336D
0x180042fff  mov     r15d, [r13+204h]
0x180043006  xor     edx, edx; dwFlags
0x180043008  mov     r8d, dword ptr [rsp+9B0h+dwBytes]; dwBytes
0x18004300d  mov     rcx, cs:IPRouterHeap; hHeap
0x180043014  mov     [rsp+9B0h+var_950], r15d
0x180043019  call    cs:__imp_HeapAlloc
0x18004301f  mov     rbx, rax
0x180043022  test    rax, rax
0x180043025  jz      loc_18004336D
0x18004302b  mov     eax, cs:g_rtmProfile.MaxHandlesInEnum
0x180043031  mov     ecx, 0FFFFFFFFh
0x180043036  shl     rax, 3
0x18004303a  xor     edx, edx; dwFlags
0x18004303c  cmp     rax, rcx
0x18004303f  mov     rcx, cs:IPRouterHeap; hHeap
0x180043046  ja      loc_180043318
0x18004304c  mov     r8d, eax; dwBytes
0x18004304f  call    cs:__imp_HeapAlloc
0x180043055  mov     rcx, cs:IPRouterHeap; hHeap
0x18004305c  xor     edx, edx; dwFlags
0x18004305e  mov     r14, rax
0x180043061  test    rax, rax
0x180043064  jnz     short loc_180043074
0x180043066  mov     r8, rbx; lpMem
0x180043069  call    cs:__imp_HeapFree
0x18004306f  jmp     loc_18004336D
0x180043074  mov     r8d, 14h; dwBytes
0x18004307a  call    cs:__imp_HeapAlloc
0x180043080  mov     [rsp+9B0h+DestAddress], rax
0x180043085  test    rax, rax
0x180043088  jnz     short loc_1800430AA
0x18004308a  mov     rcx, cs:IPRouterHeap; hHeap
0x180043091  mov     r8, rbx; lpMem
0x180043094  xor     edx, edx; dwFlags
0x180043096  call    cs:__imp_HeapFree
0x18004309c  mov     rcx, cs:IPRouterHeap
0x1800430a3  mov     r8, r14
0x1800430a6  xor     edx, edx
0x1800430a8  jmp     short loc_180043069
0x1800430aa  mov     eax, r15d
0x1800430ad  lea     rcx, [r13+2B0h]
0x1800430b4  neg     eax
0x1800430b6  lea     r8, [rbp+8B0h+var_920]
0x1800430ba  sbb     edx, edx
0x1800430bc  and     edx, 0FFFFFFCAh
0x1800430bf  add     edx, 57h ; 'W'
0x1800430c2  call    GetAllRtmRegistrationHandles
0x1800430c7  mov     r15d, r12d
0x1800430ca  mov     dword ptr [rsp+9B0h+dwBytes], r12d
0x1800430cf  cmp     r12d, 5
0x1800430d3  jnb     loc_1800432DB
0x1800430d9  cmp     r15d, esi
0x1800430dc  jnb     loc_1800432DB
0x1800430e2  mov     esi, r12d
0x1800430e5  add     rsi, rsi
0x1800430e8  cmp     [rbp+rsi*8+8B0h+var_91C], 0
0x1800430ed  jz      loc_1800432CF
0x1800430f3  mov     eax, [rsp+9B0h+var_950]
0x1800430f7  mov     r9d, 10000h; EnumFlags
0x1800430fd  mov     rdi, [rbp+rsi*8+8B0h+RtmRegHandle]
0x180043102  neg     eax
0x180043104  lea     rax, [rsp+9B0h+EnumHandle]
0x180043109  mov     rcx, rdi; RtmRegHandle
0x18004310c  mov     [rsp+9B0h+RtmEnumHandle], rax; RtmEnumHandle
0x180043111  sbb     r8d, r8d
0x180043114  mov     eax, [r13+10h]
0x180043118  and     r8d, 2
0x18004311c  mov     [rsp+9B0h+CriteriaInterface], eax; CriteriaInterface
0x180043120  inc     r8d; TargetViews
0x180043123  mov     [rsp+9B0h+CriteriaRoute], 0; CriteriaRoute
0x18004312c  xor     edx, edx; DestHandle
0x18004312e  mov     [rsp+9B0h+MatchingFlags], 10h; MatchingFlags
0x180043136  mov     [rsp+9B0h+StartDest], 0; StartDest
0x18004313f  call    cs:__imp_RtmCreateRouteEnum
0x180043145  test    eax, eax
0x180043147  jz      short loc_1800431C5
0x180043149  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180043150  jz      loc_1800432CF
0x180043156  mov     r9d, [rbp+rsi*8+8B0h+var_920]
0x18004315b  lea     rdx, aReadallstaticr_0; "ReadAllStaticRoutesIntoBuffer: Error %d"...
0x180043162  xor     ecx, ecx
0x180043164  mov     r8d, eax
0x180043167  mov     word ptr [rbp+8B0h+var_840], cx
0x18004316b  mov     word ptr [rbp+8B0h+var_868], cx
0x18004316f  lea     rcx, [rbp+8B0h+var_840]
0x180043173  call    FormatRRASErrorString
0x180043178  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004317f  jz      loc_1800432CF
0x180043185  lea     rax, [r13+2B0h]
0x18004318c  test    rax, rax
0x18004318f  lea     r9, [rbp+8B0h+var_8B0]
0x180043193  lea     r8, [rbp+8B0h+var_840]
0x180043197  cmovnz  r9, rax
0x18004319b  lea     rdx, RasRtrMgrParamTraceError
0x1800431a2  lea     rax, [rbp+8B0h+var_868]
0x1800431a6  mov     qword ptr [rsp+9B0h+MatchingFlags], rax
0x1800431ab  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800431b2  mov     rax, [r13+48h]
0x1800431b6  mov     [rsp+9B0h+StartDest], rax
0x1800431bb  call    McTemplateU0zjzz_EventWriteTransfer
0x1800431c0  jmp     loc_1800432CF
0x1800431c5  mov     r13, [rsp+9B0h+DestAddress]
0x1800431ca  mov     r12d, [rsp+9B0h+var_958]
0x1800431cf  mov     eax, cs:g_rtmProfile.MaxHandlesInEnum
0x1800431d5  lea     r8, [rsp+9B0h+dwBytes+4]; NumRoutes
0x1800431da  mov     rdx, [rsp+9B0h+EnumHandle]; EnumHandle
0x1800431df  mov     r9, r14; RouteHandles
0x1800431e2  mov     rcx, rdi; RtmRegHandle
0x1800431e5  mov     dword ptr [rsp+9B0h+dwBytes+4], eax
0x1800431e9  call    cs:__imp_RtmGetEnumRoutes
0x1800431ef  mov     edx, dword ptr [rsp+9B0h+dwBytes+4]
0x1800431f3  xor     esi, esi
0x1800431f5  mov     [rsp+9B0h+var_954], eax
0x1800431f9  test    edx, edx
0x1800431fb  jz      loc_18004329C
0x180043201  cmp     r15d, r12d
0x180043204  jnb     loc_18004329C
0x18004320a  mov     rdx, [r14+rsi*8]; RouteHandle
0x18004320e  mov     r9, r13; DestAddress
0x180043211  mov     r8, rbx; RouteInfo
0x180043214  mov     rcx, rdi; RtmRegHandle
0x180043217  call    cs:__imp_RtmGetRouteInfo
0x18004321d  test    eax, eax
0x18004321f  jnz     short loc_18004328E
0x180043221  mov     rdx, [rbx+8]; EntityHandle
0x180043225  lea     r8, [rbp+8B0h+EntityInfo]; EntityInfo
0x180043229  mov     rcx, rdi; RtmRegHandle
0x18004322c  call    cs:__imp_RtmGetEntityInfo
0x180043232  test    eax, eax
0x180043234  jnz     short loc_180043282
0x180043236  mov     rdx, [rbx+38h]; NextHopHandle
0x18004323a  lea     r8, [rbp+8B0h+NextHopInfo]; NextHopInfo
0x18004323e  mov     rcx, rdi; RtmRegHandle
0x180043241  call    cs:__imp_RtmGetNextHopInfo
0x180043247  test    eax, eax
0x180043249  jnz     short loc_180043282
0x18004324b  mov     eax, r15d
0x18004324e  lea     r9, [rbp+8B0h+NextHopInfo]
0x180043252  mov     r8, rbx
0x180043255  mov     rdx, r13
0x180043258  lea     rcx, [rax+rax*8]
0x18004325c  mov     rax, [rsp+9B0h+var_938]
0x180043261  lea     rax, [rax+rcx*8]
0x180043265  mov     ecx, dword ptr [rbp+8B0h+EntityInfo.EntityId]
0x180043268  mov     [rsp+9B0h+StartDest], rax
0x18004326d  call    ConvertRtmToRouteInfo
0x180043272  lea     rdx, [rbp+8B0h+NextHopInfo]; NextHopInfo
0x180043276  mov     rcx, rdi; RtmRegHandle
0x180043279  inc     r15d
0x18004327c  call    cs:__imp_RtmReleaseNextHopInfo
0x180043282  mov     rdx, rbx; RouteInfo
0x180043285  mov     rcx, rdi; RtmRegHandle
0x180043288  call    cs:__imp_RtmReleaseRouteInfo
0x18004328e  mov     edx, dword ptr [rsp+9B0h+dwBytes+4]; NumRoutes
0x180043292  inc     esi
0x180043294  cmp     esi, edx
0x180043296  jb      loc_180043201
0x18004329c  mov     r8, r14; RouteHandles
0x18004329f  mov     rcx, rdi; RtmRegHandle
0x1800432a2  call    cs:__imp_RtmReleaseRoutes
0x1800432a8  cmp     [rsp+9B0h+var_954], 0
0x1800432ad  jnz     short loc_1800432B8
0x1800432af  cmp     r15d, r12d
0x1800432b2  jb      loc_1800431CF
0x1800432b8  mov     rdx, [rsp+9B0h+EnumHandle]; EnumHandle
0x1800432bd  mov     rcx, rdi; RtmRegHandle
0x1800432c0  call    cs:__imp_RtmDeleteEnumHandle
0x1800432c6  mov     r13, [rbp+8B0h+var_930]
0x1800432ca  mov     r12d, dword ptr [rsp+9B0h+dwBytes]
0x1800432cf  mov     esi, [rsp+9B0h+var_958]
0x1800432d3  inc     r12d
0x1800432d6  jmp     loc_1800430CA
0x1800432db  mov     rcx, cs:IPRouterHeap; hHeap
0x1800432e2  mov     r8, rbx; lpMem
0x1800432e5  xor     edx, edx; dwFlags
0x1800432e7  call    cs:__imp_HeapFree
0x1800432ed  mov     rcx, cs:IPRouterHeap; hHeap
0x1800432f4  mov     r8, r14; lpMem
0x1800432f7  xor     edx, edx; dwFlags
0x1800432f9  call    cs:__imp_HeapFree
0x1800432ff  mov     r8, [rsp+9B0h+DestAddress]; lpMem
0x180043304  xor     edx, edx; dwFlags
0x180043306  mov     rcx, cs:IPRouterHeap; hHeap
0x18004330d  call    cs:__imp_HeapFree
0x180043313  mov     eax, r15d
0x180043316  jmp     short loc_18004336F
0x180043318  mov     r8, rbx; lpMem
0x18004331b  call    cs:__imp_HeapFree
0x180043321  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180043328  jz      short loc_18004336D
0x18004332a  lea     rax, [r13+2B0h]
0x180043331  mov     word ptr [rbp+8B0h+var_868], r12w
0x180043336  test    rax, rax
0x180043339  lea     r9, [rbp+8B0h+var_8B0]
0x18004333d  lea     r8, aReadallstaticr; "ReadAllStaticRoutesIntoBuffer: Integer "...
0x180043344  cmovnz  r9, rax
0x180043348  lea     rdx, RasRtrmgrParamTraceInfo
0x18004334f  lea     rax, [rbp+8B0h+var_868]
0x180043353  mov     qword ptr [rsp+9B0h+MatchingFlags], rax
0x180043358  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004335f  mov     rax, [r13+48h]
0x180043363  mov     [rsp+9B0h+StartDest], rax
0x180043368  call    McTemplateU0zjzz_EventWriteTransfer
0x18004336d  xor     eax, eax
0x18004336f  mov     rcx, [rbp+8B0h+var_40]
0x180043376  xor     rcx, rsp; StackCookie
0x180043379  call    __security_check_cookie
0x18004337e  mov     rbx, [rsp+9B0h+arg_10]
0x180043386  add     rsp, 980h
0x18004338d  pop     r15
0x18004338f  pop     r14
0x180043391  pop     r13
0x180043393  pop     r12
0x180043395  pop     rdi
0x180043396  pop     rsi
0x180043397  pop     rbp
0x180043398  retn
```

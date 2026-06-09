# DeleteRtmRoute

- ea: `0x18004aeb4`
- end: `0x18004b212`
- name: `DeleteRtmRoute`
- size: `862`
- prototype: `__int64 __fastcall(int, int, int, struct _GUID *)`
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800061e8`
- `0x18000aa9c`
- `0x180040be4`

## callees

- `0x180011790`
- `0x18004a3d4`
- `0x18004aeb4`
- `0x180051ef8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18004b1ce`
- `KERNEL32!HeapFree` at `0x18004b1e0`
- `KERNEL32!HeapFree` at `0x18004b1ce`
- `KERNEL32!HeapFree` at `0x18004b1e0`
- `KERNEL32!HeapAlloc` at `0x18004afb8`
- `KERNEL32!HeapAlloc` at `0x18004b042`
- `KERNEL32!HeapAlloc` at `0x18004afb8`
- `KERNEL32!HeapAlloc` at `0x18004b042`
- `rtm!RtmDeleteRouteToDest` at `0x18004b18a`
- `rtm!RtmDeleteRouteToDest` at `0x18004b18a`
- `rtm!RtmGetExactMatchRoute` at `0x18004b16c`
- `rtm!RtmGetExactMatchRoute` at `0x18004b16c`
- `rtm!RtmReleaseRoutes` at `0x18004b1a0`
- `rtm!RtmReleaseRoutes` at `0x18004b1a0`
- `rtm!RtmReleaseRouteInfo` at `0x18004b1ac`
- `rtm!RtmReleaseRouteInfo` at `0x18004b1ac`
- `rtm!RtmFindNextHop` at `0x18004b116`
- `rtm!RtmFindNextHop` at `0x18004b116`
- `rtm!RtmReleaseNextHops` at `0x18004b1bc`
- `rtm!RtmReleaseNextHops` at `0x18004b1bc`
- `rtm!RtmConvertIpv6AddressAndLengthToNetAddress` at `0x18004b0f5`
- `rtm!RtmConvertIpv6AddressAndLengthToNetAddress` at `0x18004b0f5`

## string_xrefs

- `0x18004af8b`: `DeleteRtmRoute : Arithmatic Overflow during memory allocation for route info`
- `0x18004afd4`: `DeleteRtmRoute : error allocating %d bytes for route info`

## pseudocode

```c
__int64 __fastcall DeleteRtmRoute(void *a1, __int64 a2, int a3, struct _GUID *a4)
{
  DWORD NextHop; // ebx
  __int128 *v9; // r9
  struct _RTM_ROUTE_INFO *v10; // r14
  __int128 *v11; // r9
  struct _RTM_NET_ADDRESS *v13; // r15
  __int128 *v14; // r9
  IN6_ADDR v15; // xmm0
  SIZE_T dwBytes; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE RouteHandles; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE NextHopHandle[2]; // [rsp+50h] [rbp-B0h] BYREF
  IN6_ADDR Address; // [rsp+60h] [rbp-A0h] BYREF
  struct _RTM_NEXTHOP_INFO pNetAddress; // [rsp+70h] [rbp-90h] BYREF
  __int128 v21; // [rsp+A8h] [rbp-58h] BYREF
  int v22; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v23; // [rsp+BCh] [rbp-44h]
  __int128 v24; // [rsp+CCh] [rbp-34h]
  int v25; // [rsp+DCh] [rbp-24h]
  int v26; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v27[2044]; // [rsp+E4h] [rbp-1Ch] BYREF

  RouteHandles = 0;
  NextHopHandle[0] = 0;
  dwBytes = 0;
  v26 = 0;
  memset(&pNetAddress, 0, sizeof(pNetAddress));
  memset_0(v27, 0, sizeof(v27));
  v22 = 0;
  v23 = 0;
  v25 = 0;
  v24 = 0;
  v21 = 0;
  NextHop = RTMSIZEOFROUTEINFO(g_rtmProfile.MaxNextHopsInRoute, &dwBytes);
  if ( NextHop )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v22) = 0;
      v9 = &v21;
      if ( a4 )
        LODWORD(v9) = (_DWORD)a4;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrMgrParamTraceError,
        (unsigned int)L"DeleteRtmRoute : Arithmatic Overflow during memory allocation for route info",
        (_DWORD)v9,
        0,
        (__int64)&v22);
    }
    return NextHop;
  }
  v10 = (struct _RTM_ROUTE_INFO *)HeapAlloc(IPRouterHeap, 0, (unsigned int)dwBytes);
  if ( v10 )
  {
    v13 = (struct _RTM_NET_ADDRESS *)HeapAlloc(IPRouterHeap, 0, 0x14u);
    if ( v13 )
    {
      if ( a3 )
      {
        *(_DWORD *)pNetAddress.NextHopAddress.AddrBits = *(_DWORD *)(a2 + 12);
        *(_DWORD *)&pNetAddress.NextHopAddress.AddressFamily = 2097154;
      }
      else
      {
        v15 = *(IN6_ADDR *)(a2 + 20);
        pNetAddress.NextHopAddress.AddressFamily = 23;
        Address = v15;
        RtmConvertIpv6AddressAndLengthToNetAddress(&pNetAddress.NextHopAddress, &Address, 0x80u, 0x10u);
      }
      pNetAddress.InterfaceIndex = *(_DWORD *)(a2 + 48);
      pNetAddress.NextHopOwner = a1;
      NextHop = RtmFindNextHop(a1, &pNetAddress, NextHopHandle, 0);
      if ( !NextHop )
      {
        ConvertRouteInfoToRtm((int)a1, a2, (int)NextHopHandle[0], 0, a3, a4, v13, v10);
        NextHop = RtmGetExactMatchRoute(a1, v13, 3u, v10, 0, 0, &RouteHandles);
        if ( !NextHop )
        {
          NextHop = RtmDeleteRouteToDest(a1, RouteHandles, (PRTM_ROUTE_CHANGE_FLAGS)&dwBytes + 1);
          if ( NextHop )
            RtmReleaseRoutes(a1, 1u, &RouteHandles);
          RtmReleaseRouteInfo(a1, v10);
        }
        RtmReleaseNextHops(a1, 1u, NextHopHandle);
      }
      HeapFree(IPRouterHeap, 0, v13);
    }
    else
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v26) = 0;
        LOWORD(v22) = 0;
        FormatRRASErrorString(&v26, L"AddRtmRoute : error allocating %d bytes for dest. address", 20);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v14 = &v21;
          if ( a4 )
            LODWORD(v14) = (_DWORD)a4;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v26,
            (_DWORD)v14,
            0,
            (__int64)&v22);
        }
      }
      NextHop = 8;
    }
    HeapFree(IPRouterHeap, 0, v10);
    return NextHop;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
  {
    LOWORD(v26) = 0;
    LOWORD(v22) = 0;
    FormatRRASErrorString(&v26, L"DeleteRtmRoute : error allocating %d bytes for route info", (unsigned int)dwBytes);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v11 = &v21;
      if ( a4 )
        LODWORD(v11) = (_DWORD)a4;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrMgrParamTraceError,
        (unsigned int)&v26,
        (_DWORD)v11,
        0,
        (__int64)&v22);
    }
  }
  return 8;
}

```

## disassembly

```asm
0x18004aeb4  mov     [rsp-8+arg_10], rbx
0x18004aeb9  push    rbp
0x18004aeba  push    rsi
0x18004aebb  push    rdi
0x18004aebc  push    r12
0x18004aebe  push    r13
0x18004aec0  push    r14
0x18004aec2  push    r15
0x18004aec4  lea     rbp, [rsp-7F0h]
0x18004aecc  sub     rsp, 8F0h
0x18004aed3  mov     rax, cs:__security_cookie
0x18004aeda  xor     rax, rsp
0x18004aedd  mov     [rbp+820h+var_40], rax
0x18004aee4  xor     r15d, r15d
0x18004aee7  xorps   xmm0, xmm0
0x18004aeea  mov     r12d, r8d
0x18004aeed  mov     dword ptr [rsp+920h+dwBytes+4], r15d
0x18004aef2  mov     r13, rdx
0x18004aef5  mov     [rsp+920h+RouteHandles], r15
0x18004aefa  mov     rdi, rcx
0x18004aefd  mov     [rsp+920h+NextHopHandle], r15
0x18004af02  xor     eax, eax
0x18004af04  mov     dword ptr [rsp+920h+dwBytes], r15d
0x18004af09  xor     edx, edx; Val
0x18004af0b  mov     [rbp+820h+var_880], rax
0x18004af0f  mov     r8d, 7FCh; Size
0x18004af15  mov     [rbp+820h+var_840], r15d
0x18004af19  lea     rcx, [rbp+820h+var_83C]; void *
0x18004af1d  mov     rsi, r9
0x18004af20  movups  xmmword ptr [rsp+920h+pNetAddress.AddressFamily], xmm0
0x18004af25  movups  xmmword ptr [rbp+820h+pNetAddress.AddrBits+0Ch], xmm0
0x18004af29  movups  [rbp+820h+var_890], xmm0
0x18004af2d  call    memset_0
0x18004af32  mov     ecx, cs:g_rtmProfile.MaxNextHopsInRoute
0x18004af38  lea     rdx, [rsp+920h+dwBytes]
0x18004af3d  xorps   xmm0, xmm0
0x18004af40  mov     [rbp+820h+var_868], r15d
0x18004af44  xor     eax, eax
0x18004af46  movups  [rbp+820h+var_864], xmm0
0x18004af4a  mov     [rbp+820h+var_844], eax
0x18004af4d  movups  [rbp+820h+var_854], xmm0
0x18004af51  movups  [rbp+820h+var_878], xmm0
0x18004af55  call    RTMSIZEOFROUTEINFO
0x18004af5a  mov     ebx, eax
0x18004af5c  test    eax, eax
0x18004af5e  jz      short loc_18004AFAA
0x18004af60  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004af67  jz      loc_18004B1E6
0x18004af6d  test    rsi, rsi
0x18004af70  mov     word ptr [rbp+820h+var_868], r15w
0x18004af75  lea     rax, [rbp+820h+var_868]
0x18004af79  mov     qword ptr [rsp+920h+TargetViews], rax
0x18004af7e  lea     r9, [rbp+820h+var_878]
0x18004af82  cmovnz  r9, rsi
0x18004af86  mov     qword ptr [rsp+920h+InterfaceIndex], r15
0x18004af8b  lea     r8, aDeletertmroute; "DeleteRtmRoute : Arithmatic Overflow du"...
0x18004af92  lea     rdx, RasRtrMgrParamTraceError
0x18004af99  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004afa0  call    McTemplateU0zjzz_EventWriteTransfer
0x18004afa5  jmp     loc_18004B1E6
0x18004afaa  mov     r8d, dword ptr [rsp+920h+dwBytes]; dwBytes
0x18004afaf  xor     edx, edx; dwFlags
0x18004afb1  mov     rcx, cs:IPRouterHeap; hHeap
0x18004afb8  call    cs:__imp_HeapAlloc
0x18004afbe  mov     r14, rax
0x18004afc1  test    rax, rax
0x18004afc4  jnz     short loc_18004B031
0x18004afc6  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004afcd  jz      short loc_18004B027
0x18004afcf  mov     r8d, dword ptr [rsp+920h+dwBytes]
0x18004afd4  lea     rdx, aDeletertmroute_1; "DeleteRtmRoute : error allocating %d by"...
0x18004afdb  lea     rcx, [rbp+820h+var_840]
0x18004afdf  mov     word ptr [rbp+820h+var_840], r15w
0x18004afe4  mov     word ptr [rbp+820h+var_868], r15w
0x18004afe9  call    FormatRRASErrorString
0x18004afee  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004aff5  jz      short loc_18004B027
0x18004aff7  test    rsi, rsi
0x18004affa  lea     rax, [rbp+820h+var_868]
0x18004affe  mov     qword ptr [rsp+920h+TargetViews], rax
0x18004b003  lea     r9, [rbp+820h+var_878]
0x18004b007  cmovnz  r9, rsi
0x18004b00b  mov     qword ptr [rsp+920h+InterfaceIndex], r15
0x18004b010  lea     r8, [rbp+820h+var_840]
0x18004b014  lea     rdx, RasRtrMgrParamTraceError
0x18004b01b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004b022  call    McTemplateU0zjzz_EventWriteTransfer
0x18004b027  mov     eax, 8
0x18004b02c  jmp     loc_18004B1E8
0x18004b031  mov     rcx, cs:IPRouterHeap; hHeap
0x18004b038  mov     ebx, 14h
0x18004b03d  mov     r8d, ebx; dwBytes
0x18004b040  xor     edx, edx; dwFlags
0x18004b042  call    cs:__imp_HeapAlloc
0x18004b048  mov     r15, rax
0x18004b04b  test    rax, rax
0x18004b04e  jnz     short loc_18004B0B7
0x18004b050  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004b057  jz      short loc_18004B0AD
0x18004b059  mov     r8d, ebx
0x18004b05c  mov     word ptr [rbp+820h+var_840], ax
0x18004b060  lea     rdx, aAddrtmrouteErr_3; "AddRtmRoute : error allocating %d bytes"...
0x18004b067  mov     word ptr [rbp+820h+var_868], ax
0x18004b06b  lea     rcx, [rbp+820h+var_840]
0x18004b06f  call    FormatRRASErrorString
0x18004b074  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004b07b  jz      short loc_18004B0AD
0x18004b07d  test    rsi, rsi
0x18004b080  lea     rax, [rbp+820h+var_868]
0x18004b084  mov     qword ptr [rsp+920h+TargetViews], rax
0x18004b089  lea     r9, [rbp+820h+var_878]
0x18004b08d  cmovnz  r9, rsi
0x18004b091  mov     qword ptr [rsp+920h+InterfaceIndex], r15
0x18004b096  lea     r8, [rbp+820h+var_840]
0x18004b09a  lea     rdx, RasRtrMgrParamTraceError
0x18004b0a1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004b0a8  call    McTemplateU0zjzz_EventWriteTransfer
0x18004b0ad  mov     ebx, 8
0x18004b0b2  jmp     loc_18004B1D4
0x18004b0b7  test    r12d, r12d
0x18004b0ba  jz      short loc_18004B0CE
0x18004b0bc  mov     eax, [r13+0Ch]
0x18004b0c0  mov     dword ptr [rsp+920h+pNetAddress.AddrBits], eax
0x18004b0c4  mov     dword ptr [rsp+920h+pNetAddress.AddressFamily], 200002h
0x18004b0cc  jmp     short loc_18004B0FB
0x18004b0ce  movups  xmm0, xmmword ptr [r13+14h]
0x18004b0d3  mov     eax, 17h
0x18004b0d8  lea     rdx, [rsp+920h+Address]; Address
0x18004b0dd  lea     rcx, [rsp+920h+pNetAddress]; pNetAddress
0x18004b0e2  mov     [rsp+920h+pNetAddress.AddressFamily], ax
0x18004b0e7  movdqu  xmmword ptr [rsp+920h+Address.u], xmm0
0x18004b0ed  lea     r9d, [rax-7]; dwAddressSize
0x18004b0f1  lea     r8d, [rax+69h]; dwLength
0x18004b0f5  call    cs:__imp_RtmConvertIpv6AddressAndLengthToNetAddress
0x18004b0fb  mov     eax, [r13+30h]
0x18004b0ff  lea     r8, [rsp+920h+NextHopHandle]; NextHopHandle
0x18004b104  xor     r9d, r9d; NextHopPointer
0x18004b107  mov     dword ptr [rbp+820h+var_890], eax
0x18004b10a  lea     rdx, [rsp+920h+pNetAddress]; NextHopInfo
0x18004b10f  mov     [rbp-78h], rdi
0x18004b113  mov     rcx, rdi; RtmRegHandle
0x18004b116  call    cs:__imp_RtmFindNextHop
0x18004b11c  mov     ebx, eax
0x18004b11e  test    eax, eax
0x18004b120  jnz     loc_18004B1C2
0x18004b126  mov     r8, [rsp+920h+NextHopHandle]; int
0x18004b12b  xor     r9d, r9d; int
0x18004b12e  mov     [rsp+920h+var_8E8], r14; void *
0x18004b133  mov     rdx, r13; int
0x18004b136  mov     [rsp+920h+RouteHandle], r15; pNetAddress
0x18004b13b  mov     rcx, rdi; int
0x18004b13e  mov     qword ptr [rsp+920h+TargetViews], rsi; struct _GUID *
0x18004b143  mov     [rsp+920h+InterfaceIndex], r12d; int
0x18004b148  call    ConvertRouteInfoToRtm
0x18004b14d  lea     rax, [rsp+920h+RouteHandles]
0x18004b152  mov     r9, r14; RouteInfo
0x18004b155  mov     [rsp+920h+RouteHandle], rax; RouteHandle
0x18004b15a  lea     r8d, [rbx+3]; MatchingFlags
0x18004b15e  mov     [rsp+920h+TargetViews], ebx; TargetViews
0x18004b162  mov     rdx, r15; DestAddress
0x18004b165  mov     rcx, rdi; RtmRegHandle
0x18004b168  mov     [rsp+920h+InterfaceIndex], ebx; InterfaceIndex
0x18004b16c  call    cs:__imp_RtmGetExactMatchRoute
0x18004b172  mov     ebx, eax
0x18004b174  mov     esi, 1
0x18004b179  test    eax, eax
0x18004b17b  jnz     short loc_18004B1B2
0x18004b17d  mov     rdx, [rsp+920h+RouteHandles]; RouteHandle
0x18004b182  lea     r8, [rsp+920h+dwBytes+4]; ChangeFlags
0x18004b187  mov     rcx, rdi; RtmRegHandle
0x18004b18a  call    cs:__imp_RtmDeleteRouteToDest
0x18004b190  mov     ebx, eax
0x18004b192  test    eax, eax
0x18004b194  jz      short loc_18004B1A6
0x18004b196  lea     r8, [rsp+920h+RouteHandles]; RouteHandles
0x18004b19b  mov     edx, esi; NumRoutes
0x18004b19d  mov     rcx, rdi; RtmRegHandle
0x18004b1a0  call    cs:__imp_RtmReleaseRoutes
0x18004b1a6  mov     rdx, r14; RouteInfo
0x18004b1a9  mov     rcx, rdi; RtmRegHandle
0x18004b1ac  call    cs:__imp_RtmReleaseRouteInfo
0x18004b1b2  lea     r8, [rsp+920h+NextHopHandle]; NextHopHandles
0x18004b1b7  mov     edx, esi; NumNextHops
0x18004b1b9  mov     rcx, rdi; RtmRegHandle
0x18004b1bc  call    cs:__imp_RtmReleaseNextHops
0x18004b1c2  mov     rcx, cs:IPRouterHeap; hHeap
0x18004b1c9  mov     r8, r15; lpMem
0x18004b1cc  xor     edx, edx; dwFlags
0x18004b1ce  call    cs:__imp_HeapFree
0x18004b1d4  mov     rcx, cs:IPRouterHeap; hHeap
0x18004b1db  mov     r8, r14; lpMem
0x18004b1de  xor     edx, edx; dwFlags
0x18004b1e0  call    cs:__imp_HeapFree
0x18004b1e6  mov     eax, ebx
0x18004b1e8  mov     rcx, [rbp+820h+var_40]
0x18004b1ef  xor     rcx, rsp; StackCookie
0x18004b1f2  call    __security_check_cookie
0x18004b1f7  mov     rbx, [rsp+920h+arg_10]
0x18004b1ff  add     rsp, 8F0h
0x18004b206  pop     r15
0x18004b208  pop     r14
0x18004b20a  pop     r13
0x18004b20c  pop     r12
0x18004b20e  pop     rdi
0x18004b20f  pop     rsi
0x18004b210  pop     rbp
0x18004b211  retn
```

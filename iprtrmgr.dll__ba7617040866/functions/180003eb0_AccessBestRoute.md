# AccessBestRoute

- ea: `0x180003eb0`
- end: `0x1800041c8`
- name: `AccessBestRoute`
- size: `792`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180026f54`
- `0x1800271cc`
- `0x180027444`

## callees

- `0x180003eb0`
- `0x18000ac60`
- `0x18004aa08`
- `0x180051ef8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180004159`
- `KERNEL32!HeapFree` at `0x180004159`
- `KERNEL32!HeapAlloc` at `0x18000409e`
- `KERNEL32!HeapAlloc` at `0x18000409e`
- `rtm!RtmReleaseDestInfo` at `0x180004175`
- `rtm!RtmReleaseDestInfo` at `0x180004175`
- `rtm!RtmReleaseRouteInfo` at `0x180004147`
- `rtm!RtmReleaseRouteInfo` at `0x180004147`
- `rtm!RtmReleaseNextHopInfo` at `0x180004137`
- `rtm!RtmReleaseNextHopInfo` at `0x180004137`
- `rtm!RtmGetNextHopInfo` at `0x1800040fd`
- `rtm!RtmGetNextHopInfo` at `0x1800040fd`
- `rtm!RtmGetEntityInfo` at `0x1800040e1`
- `rtm!RtmGetEntityInfo` at `0x1800040e1`
- `rtm!RtmGetRouteInfo` at `0x1800040c5`
- `rtm!RtmGetRouteInfo` at `0x1800040c5`
- `rtm!RtmGetMostSpecificDestination` at `0x18000404c`
- `rtm!RtmGetMostSpecificDestination` at `0x18000404c`

## string_xrefs

- `0x180003f71`: `AccessBestRoute`
- `0x180003fe1`: `Leaving: AccessBestRoute`
- `0x180004077`: `Leaving: AccessBestRoute`
- `0x180004184`: `Leaving: AccessBestRoute`

## pseudocode

```c
__int64 __fastcall AccessBestRoute(int a1, unsigned int a2, __int64 a3, _DWORD *a4, __int64 a5, int a6, int a7)
{
  char v11; // al
  DWORD MostSpecificDestination; // ebx
  struct _RTM_ROUTE_INFO *v14; // rax
  struct _RTM_ROUTE_INFO *v15; // rdi
  SIZE_T dwBytes; // [rsp+30h] [rbp-908h] BYREF
  struct _RTM_NET_ADDRESS DestAddress; // [rsp+38h] [rbp-900h] BYREF
  _RTM_ENTITY_INFO EntityInfo; // [rsp+50h] [rbp-8E8h] BYREF
  _RTM_NEXTHOP_INFO NextHopInfo; // [rsp+60h] [rbp-8D8h] BYREF
  struct _RTM_DEST_INFO DestInfo; // [rsp+A0h] [rbp-898h] BYREF
  int v21; // [rsp+100h] [rbp-838h] BYREF
  _BYTE v22[2044]; // [rsp+104h] [rbp-834h] BYREF

  LODWORD(dwBytes) = 0;
  memset(&DestAddress, 0, sizeof(DestAddress));
  memset_0(&DestInfo, 0, sizeof(DestInfo));
  memset(&NextHopInfo, 0, 52);
  v21 = 0;
  EntityInfo = 0;
  memset_0(v22, 0, sizeof(v22));
  v11 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v21) = 0;
    FormatRRASErrorString(&v21, L"Entered: %ws", L"AccessBestRoute");
    v11 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v21);
      v11 = Microsoft_Windows_RRASEnableBits;
    }
  }
  if ( a7 == 87 )
    return 50;
  if ( *a4 >= 0x50u )
  {
    if ( (a2 >> 2) - 1 >= 2 && a1 == 1 )
    {
      *a4 = 80;
      *(_DWORD *)DestAddress.AddrBits = *(_DWORD *)(a3 + 4);
      *(_DWORD *)&DestAddress.AddressFamily = 2097154;
      MostSpecificDestination = RtmGetMostSpecificDestination(g_hLocalRoute, &DestAddress, 0, 1u, &DestInfo);
      if ( !MostSpecificDestination )
      {
        MostSpecificDestination = RTMSIZEOFROUTEINFO(g_rtmProfile.MaxNextHopsInRoute, &dwBytes);
        if ( !MostSpecificDestination )
        {
          v14 = (struct _RTM_ROUTE_INFO *)HeapAlloc(IPRouterHeap, 0, (unsigned int)dwBytes);
          v15 = v14;
          if ( v14 )
          {
            MostSpecificDestination = RtmGetRouteInfo(g_hLocalRoute, DestInfo.ViewInfo[0].Route, v14, 0);
            if ( !MostSpecificDestination )
            {
              MostSpecificDestination = RtmGetEntityInfo(g_hLocalRoute, v15->RouteOwner, &EntityInfo);
              if ( !MostSpecificDestination )
              {
                MostSpecificDestination = RtmGetNextHopInfo(g_hLocalRoute, v15->NextHopsList.NextHops[0], &NextHopInfo);
                if ( !MostSpecificDestination )
                {
                  ConvertRtmToRouteInfo(
                    EntityInfo.EntityId.EntityProtocolId,
                    &DestInfo.DestAddress,
                    v15,
                    &NextHopInfo,
                    a5 + 8);
                  RtmReleaseNextHopInfo(g_hLocalRoute, &NextHopInfo);
                }
              }
              RtmReleaseRouteInfo(g_hLocalRoute, v15);
            }
            HeapFree(IPRouterHeap, 0, v15);
          }
          else
          {
            MostSpecificDestination = 8;
          }
          RtmReleaseDestInfo(g_hLocalRoute, &DestInfo);
        }
      }
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: AccessBestRoute");
      return MostSpecificDestination;
    }
    else
    {
      if ( v11 < 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: AccessBestRoute");
      return 87;
    }
  }
  else
  {
    *a4 = 80;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessBestRoute");
    return 122;
  }
}

```

## disassembly

```asm
0x180003eb0  mov     [rsp+arg_0], rbx
0x180003eb5  mov     [rsp+arg_8], rsi
0x180003eba  push    rdi
0x180003ebb  push    r12
0x180003ebd  push    r13
0x180003ebf  push    r14
0x180003ec1  push    r15
0x180003ec3  sub     rsp, 910h
0x180003eca  mov     rax, cs:__security_cookie
0x180003ed1  xor     rax, rsp
0x180003ed4  mov     [rsp+938h+var_38], rax
0x180003edc  mov     r15, [rsp+938h+arg_20]
0x180003ee4  xor     eax, eax
0x180003ee6  mov     r14, r8
0x180003ee9  mov     dword ptr [rsp+938h+dwBytes], 0
0x180003ef1  mov     ebx, edx
0x180003ef3  mov     dword ptr [rsp+938h+DestAddress.AddrBits+0Ch], eax
0x180003ef7  mov     esi, ecx
0x180003ef9  xorps   xmm0, xmm0
0x180003efc  lea     r8d, [rax+58h]; Size
0x180003f00  xor     edx, edx; Val
0x180003f02  lea     rcx, [rsp+938h+var_898]; void *
0x180003f0a  mov     rdi, r9
0x180003f0d  movups  xmmword ptr [rsp+938h+DestAddress.AddressFamily], xmm0
0x180003f12  call    memset_0
0x180003f17  xorps   xmm0, xmm0
0x180003f1a  lea     rcx, [rsp+938h+var_834]; void *
0x180003f22  xor     eax, eax
0x180003f24  xor     edx, edx; Val
0x180003f26  mov     r8d, 7FCh; Size
0x180003f2c  mov     dword ptr [rsp+938h+NextHopInfo.RemoteNextHop], eax
0x180003f33  movups  xmmword ptr [rsp+938h+NextHopInfo.NextHopAddress.AddressFamily], xmm0
0x180003f38  mov     [rsp+938h+var_838], eax
0x180003f3f  movups  xmmword ptr [rsp+938h+NextHopInfo.NextHopAddress.AddrBits+0Ch], xmm0
0x180003f44  movups  xmmword ptr [rsp+938h+NextHopInfo.InterfaceIndex], xmm0
0x180003f4c  movups  xmmword ptr [rsp+938h+EntityInfo.RtmInstanceId], xmm0
0x180003f51  call    memset_0
0x180003f56  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180003f5d  lea     r12, RasRtrmgrTraceInfo
0x180003f64  lea     r13, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003f6b  test    al, al
0x180003f6d  jns     short loc_180003FB9
0x180003f6f  xor     eax, eax
0x180003f71  lea     r8, aAccessbestrout; "AccessBestRoute"
0x180003f78  lea     rdx, aEnteredWs; "Entered: %ws"
0x180003f7f  mov     word ptr [rsp+938h+var_838], ax
0x180003f87  lea     rcx, [rsp+938h+var_838]
0x180003f8f  call    FormatRRASErrorString
0x180003f94  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180003f9b  test    al, al
0x180003f9d  jns     short loc_180003FB9
0x180003f9f  lea     r8, [rsp+938h+var_838]
0x180003fa7  mov     rdx, r12
0x180003faa  mov     rcx, r13
0x180003fad  call    McTemplateU0z_EventWriteTransfer
0x180003fb2  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180003fb9  cmp     [rsp+938h+arg_30], 57h ; 'W'
0x180003fc1  jnz     short loc_180003FCD
0x180003fc3  mov     eax, 32h ; '2'
0x180003fc8  jmp     loc_18000419B
0x180003fcd  mov     ecx, 50h ; 'P'
0x180003fd2  cmp     [rdi], ecx
0x180003fd4  jnb     short loc_180003FFD
0x180003fd6  mov     [rdi], ecx
0x180003fd8  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180003fdf  jz      short loc_180003FF3
0x180003fe1  lea     r8, aLeavingAccessb_0; "Leaving: AccessBestRoute"
0x180003fe8  mov     rdx, r12
0x180003feb  mov     rcx, r13
0x180003fee  call    McTemplateU0z_EventWriteTransfer
0x180003ff3  mov     eax, 7Ah ; 'z'
0x180003ff8  jmp     loc_18000419B
0x180003ffd  mov     r9d, 1; TargetViews
0x180004003  shr     ebx, 2
0x180004006  sub     ebx, r9d
0x180004009  lea     edx, [r9+1]
0x18000400d  cmp     ebx, edx
0x18000400f  jb      loc_180004180
0x180004015  cmp     esi, r9d
0x180004018  jnz     loc_180004180
0x18000401e  mov     [rdi], ecx
0x180004020  lea     rdx, [rsp+938h+DestAddress]; DestAddress
0x180004025  mov     eax, [r14+4]
0x180004029  xor     r8d, r8d; ProtocolId
0x18000402c  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x180004033  mov     dword ptr [rsp+938h+DestAddress.AddrBits], eax
0x180004037  lea     rax, [rsp+938h+var_898]
0x18000403f  mov     [rsp+938h+DestInfo], rax; DestInfo
0x180004044  mov     dword ptr [rsp+938h+DestAddress.AddressFamily], 200002h
0x18000404c  call    cs:__imp_RtmGetMostSpecificDestination
0x180004052  mov     ebx, eax
0x180004054  test    eax, eax
0x180004056  jnz     short loc_18000406E
0x180004058  mov     ecx, cs:g_rtmProfile.MaxNextHopsInRoute
0x18000405e  lea     rdx, [rsp+938h+dwBytes]
0x180004063  call    RTMSIZEOFROUTEINFO
0x180004068  mov     ebx, eax
0x18000406a  test    eax, eax
0x18000406c  jz      short loc_180004090
0x18000406e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180004075  jz      short loc_180004089
0x180004077  lea     r8, aLeavingAccessb_0; "Leaving: AccessBestRoute"
0x18000407e  mov     rdx, r12
0x180004081  mov     rcx, r13
0x180004084  call    McTemplateU0z_EventWriteTransfer
0x180004089  mov     eax, ebx
0x18000408b  jmp     loc_18000419B
0x180004090  mov     r8d, dword ptr [rsp+938h+dwBytes]; dwBytes
0x180004095  xor     edx, edx; dwFlags
0x180004097  mov     rcx, cs:IPRouterHeap; hHeap
0x18000409e  call    cs:__imp_HeapAlloc
0x1800040a4  mov     rdi, rax
0x1800040a7  test    rax, rax
0x1800040aa  jz      loc_180004161
0x1800040b0  mov     rdx, [rsp+938h+var_898.ViewInfo.Route]; RouteHandle
0x1800040b8  xor     r9d, r9d; DestAddress
0x1800040bb  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x1800040c2  mov     r8, rax; RouteInfo
0x1800040c5  call    cs:__imp_RtmGetRouteInfo
0x1800040cb  mov     ebx, eax
0x1800040cd  test    eax, eax
0x1800040cf  jnz     short loc_18000414D
0x1800040d1  mov     rdx, [rdi+8]; EntityHandle
0x1800040d5  lea     r8, [rsp+938h+EntityInfo]; EntityInfo
0x1800040da  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x1800040e1  call    cs:__imp_RtmGetEntityInfo
0x1800040e7  mov     ebx, eax
0x1800040e9  test    eax, eax
0x1800040eb  jnz     short loc_18000413D
0x1800040ed  mov     rdx, [rdi+38h]; NextHopHandle
0x1800040f1  lea     r8, [rsp+938h+NextHopInfo]; NextHopInfo
0x1800040f6  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x1800040fd  call    cs:__imp_RtmGetNextHopInfo
0x180004103  mov     ebx, eax
0x180004105  test    eax, eax
0x180004107  jnz     short loc_18000413D
0x180004109  mov     ecx, dword ptr [rsp+938h+EntityInfo.EntityId]
0x18000410d  lea     rax, [r15+8]
0x180004111  lea     r9, [rsp+938h+NextHopInfo]
0x180004116  mov     [rsp+938h+DestInfo], rax
0x18000411b  mov     r8, rdi
0x18000411e  lea     rdx, [rsp+938h+var_898.DestAddress]
0x180004126  call    ConvertRtmToRouteInfo
0x18000412b  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x180004132  lea     rdx, [rsp+938h+NextHopInfo]; NextHopInfo
0x180004137  call    cs:__imp_RtmReleaseNextHopInfo
0x18000413d  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x180004144  mov     rdx, rdi; RouteInfo
0x180004147  call    cs:__imp_RtmReleaseRouteInfo
0x18000414d  mov     rcx, cs:IPRouterHeap; hHeap
0x180004154  mov     r8, rdi; lpMem
0x180004157  xor     edx, edx; dwFlags
0x180004159  call    cs:__imp_HeapFree
0x18000415f  jmp     short loc_180004166
0x180004161  mov     ebx, 8
0x180004166  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x18000416d  lea     rdx, [rsp+938h+var_898]; DestInfo
0x180004175  call    cs:__imp_RtmReleaseDestInfo
0x18000417b  jmp     loc_18000406E
0x180004180  test    al, 80h
0x180004182  jz      short loc_180004196
0x180004184  lea     r8, aLeavingAccessb_0; "Leaving: AccessBestRoute"
0x18000418b  mov     rdx, r12
0x18000418e  mov     rcx, r13
0x180004191  call    McTemplateU0z_EventWriteTransfer
0x180004196  mov     eax, 57h ; 'W'
0x18000419b  mov     rcx, [rsp+938h+var_38]
0x1800041a3  xor     rcx, rsp; StackCookie
0x1800041a6  call    __security_check_cookie
0x1800041ab  lea     r11, [rsp+938h+var_28]
0x1800041b3  mov     rbx, [r11+30h]
0x1800041b7  mov     rsi, [r11+38h]
0x1800041bb  mov     rsp, r11
0x1800041be  pop     r15
0x1800041c0  pop     r14
0x1800041c2  pop     r13
0x1800041c4  pop     r12
0x1800041c6  pop     rdi
0x1800041c7  retn
```

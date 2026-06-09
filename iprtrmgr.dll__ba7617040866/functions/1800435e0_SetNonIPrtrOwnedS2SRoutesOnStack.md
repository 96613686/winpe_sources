# SetNonIPrtrOwnedS2SRoutesOnStack

- ea: `0x1800435e0`
- end: `0x180043c45`
- name: `SetNonIPrtrOwnedS2SRoutesOnStack`
- size: `1637`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000b450`

## callees

- `0x180011790`
- `0x1800435e0`
- `0x180046848`
- `0x180051ef8`
- `0x180057c48`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180043be2`
- `KERNEL32!HeapFree` at `0x180043bf9`
- `KERNEL32!HeapFree` at `0x180043c10`
- `KERNEL32!HeapFree` at `0x180043be2`
- `KERNEL32!HeapFree` at `0x180043bf9`
- `KERNEL32!HeapFree` at `0x180043c10`
- `KERNEL32!HeapAlloc` at `0x180043887`
- `KERNEL32!HeapAlloc` at `0x1800438dc`
- `KERNEL32!HeapAlloc` at `0x180043952`
- `KERNEL32!HeapAlloc` at `0x180043887`
- `KERNEL32!HeapAlloc` at `0x1800438dc`
- `KERNEL32!HeapAlloc` at `0x180043952`
- `rtm!RtmReleaseRoutes` at `0x180043b54`
- `rtm!RtmReleaseRoutes` at `0x180043b54`
- `rtm!RtmGetEnumRoutes` at `0x180043a92`
- `rtm!RtmGetEnumRoutes` at `0x180043a92`
- `rtm!RtmCreateRouteEnum` at `0x180043a3e`
- `rtm!RtmCreateRouteEnum` at `0x180043a3e`
- `rtm!RtmDeleteEnumHandle` at `0x180043b6a`
- `rtm!RtmDeleteEnumHandle` at `0x180043b6a`
- `rtm!RtmReleaseRouteInfo` at `0x180043b3a`
- `rtm!RtmReleaseRouteInfo` at `0x180043b3a`
- `rtm!RtmGetRouteInfo` at `0x180043adc`
- `rtm!RtmGetRouteInfo` at `0x180043adc`
- `rtm!RtmIsBestRoute` at `0x180043abc`
- `rtm!RtmIsBestRoute` at `0x180043abc`

## pseudocode

```c
__int64 __fastcall SetNonIPrtrOwnedS2SRoutesOnStack(__int64 a1)
{
  ULONG v1; // ebx
  HANDLE *v2; // r14
  unsigned int v3; // r12d
  char v5; // r9
  __int128 *v6; // r9
  __int128 *v7; // r9
  DWORD v8; // esi
  __int128 *v9; // r9
  DWORD v10; // eax
  char v11; // r9
  __int64 v12; // r8
  const wchar_t *v13; // rdx
  __int128 *v14; // r9
  struct _RTM_ROUTE_INFO *v15; // r13
  unsigned __int64 v16; // rax
  struct _RTM_NET_ADDRESS *v17; // r15
  UINT v18; // ebx
  const wchar_t *v19; // r8
  __int64 *v20; // rdx
  unsigned int v21; // ebx
  void *v22; // r12
  DWORD EnumRoutes; // ebx
  UINT v24; // edx
  __int64 i; // rdi
  __int128 *v26; // r9
  unsigned int NumRoutes; // [rsp+50h] [rbp-8A8h] BYREF
  int v29; // [rsp+54h] [rbp-8A4h]
  SIZE_T dwBytes; // [rsp+58h] [rbp-8A0h] BYREF
  DWORD BestInViews; // [rsp+60h] [rbp-898h] BYREF
  ULONG CriteriaInterface; // [rsp+64h] [rbp-894h]
  HANDLE EnumHandle; // [rsp+68h] [rbp-890h] BYREF
  __int64 RtmRegistrationHandle; // [rsp+70h] [rbp-888h]
  __int64 v35; // [rsp+78h] [rbp-880h]
  struct _GUID *v36; // [rsp+80h] [rbp-878h]
  __int128 v37; // [rsp+88h] [rbp-870h] BYREF
  int v38; // [rsp+98h] [rbp-860h] BYREF
  __int128 v39; // [rsp+9Ch] [rbp-85Ch]
  __int128 v40; // [rsp+ACh] [rbp-84Ch]
  int v41; // [rsp+BCh] [rbp-83Ch]
  int v42; // [rsp+C0h] [rbp-838h] BYREF
  int v43; // [rsp+C4h] [rbp-834h] BYREF

  v1 = *(_DWORD *)(a1 + 16);
  v2 = 0;
  v3 = *(_DWORD *)(a1 + 516);
  EnumHandle = 0;
  BestInViews = 0;
  NumRoutes = 0;
  LODWORD(dwBytes) = 0;
  v42 = 0;
  CriteriaInterface = v1;
  v29 = v3;
  memset_0(&v43, 0, 0x7FCu);
  v5 = Microsoft_Windows_RRASEnableBits;
  v38 = 0;
  v41 = 0;
  v39 = 0;
  v40 = 0;
  v37 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v42) = 0;
    LOWORD(v38) = 0;
    FormatRRASErrorString(&v42, L"SetNonIPrtrOwnedS2SRoutesOnStack (If %d) V4=%d", v1, v3);
    v5 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v6 = &v37;
      if ( a1 != -688 )
        LODWORD(v6) = a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v42,
        (_DWORD)v6,
        *(_QWORD *)(a1 + 72),
        (__int64)&v38);
      v5 = Microsoft_Windows_RRASEnableBits;
    }
  }
  if ( *(_DWORD *)(a1 + 144) != 2 )
  {
    if ( v5 < 0 )
    {
      LOWORD(v38) = 0;
      v7 = &v37;
      if ( a1 != -688 )
        LODWORD(v7) = a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)L"Bailing out since this is not a S2S interface",
        (_DWORD)v7,
        *(_QWORD *)(a1 + 72),
        (__int64)&v38);
    }
    return 87;
  }
  if ( *(_DWORD *)(a1 + 168) != 4 )
  {
    if ( v5 < 0 )
    {
      LOWORD(v38) = 0;
      v9 = &v37;
      if ( a1 != -688 )
        LODWORD(v9) = a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)L"Interface not in connected state. Just returning back.",
        (_DWORD)v9,
        *(_QWORD *)(a1 + 72),
        (__int64)&v38);
    }
    return 0;
  }
  v10 = RTMSIZEOFROUTEINFO(g_rtmProfile.MaxNextHopsInRoute, &dwBytes);
  v8 = v10;
  if ( v10 )
  {
    if ( (v11 & 0x40) == 0 )
      return v8;
    v12 = v10;
    v13 = L"SetNonIPrtrOwnedS2SRoutesOnStack : Error  Integer overflow %d";
    goto LABEL_21;
  }
  v15 = (struct _RTM_ROUTE_INFO *)HeapAlloc(IPRouterHeap, 0, (unsigned int)dwBytes);
  if ( !v15 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
      return v8;
    v12 = (unsigned int)dwBytes;
    v13 = L"SetNonIPrtrOwnedS2SRoutesOnStack : Error allocating %d bytes for route info";
LABEL_21:
    LOWORD(v38) = 0;
    LOWORD(v42) = 0;
    FormatRRASErrorString(&v42, v13, v12);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v14 = &v37;
      if ( a1 != -688 )
        LODWORD(v14) = a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrMgrParamTraceError,
        (unsigned int)&v42,
        (_DWORD)v14,
        *(_QWORD *)(a1 + 72),
        (__int64)&v38);
    }
    return v8;
  }
  v16 = 8LL * g_rtmProfile.MaxHandlesInEnum;
  v17 = 0;
  if ( v16 > 0xFFFFFFFF )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v19 = L"SetNonIPrtrOwnedS2SRoutesOnStack: Integer overflow";
      LOWORD(v38) = 0;
      v20 = RasRtrmgrParamTraceInfo;
      goto LABEL_57;
    }
  }
  else
  {
    v18 = 8 * g_rtmProfile.MaxHandlesInEnum;
    v2 = (HANDLE *)HeapAlloc(IPRouterHeap, 0, (unsigned int)v16);
    if ( v2 )
    {
      v17 = (struct _RTM_NET_ADDRESS *)HeapAlloc(IPRouterHeap, 0, 0x14u);
      if ( v17 )
      {
        v36 = (struct _GUID *)(a1 + 688);
        v21 = v3 != 0 ? 33 : 87;
        dwBytes = GetRtmRegistrationHandle((struct _GUID *)(a1 + 688), v21, 0x2716u);
        RtmRegistrationHandle = GetRtmRegistrationHandle((struct _GUID *)(a1 + 688), v21, 0x2717u);
        v35 = GetRtmRegistrationHandle((struct _GUID *)(a1 + 688), v21, 3u);
        v22 = (void *)GetRtmRegistrationHandle((struct _GUID *)(a1 + 688), v21, 2u);
        v8 = RtmCreateRouteEnum(v22, 0, 1u, 0, 0, 0x10u, 0, CriteriaInterface, &EnumHandle);
        if ( !v8 )
        {
          do
          {
            NumRoutes = g_rtmProfile.MaxHandlesInEnum;
            EnumRoutes = RtmGetEnumRoutes(v22, EnumHandle, &NumRoutes, v2);
            if ( EnumRoutes )
              break;
            v24 = NumRoutes;
            for ( i = 0; (unsigned int)i < NumRoutes; i = (unsigned int)(i + 1) )
            {
              EnumRoutes = RtmIsBestRoute(v22, v2[i], &BestInViews);
              if ( !EnumRoutes && (BestInViews & 1) != 0 && !RtmGetRouteInfo(v22, v2[i], v15, v17) )
              {
                if ( v15->RouteOwner != (RTM_ENTITY_HANDLE)dwBytes
                  && v15->RouteOwner != (RTM_ENTITY_HANDLE)RtmRegistrationHandle
                  && v15->RouteOwner != (RTM_ENTITY_HANDLE)v35 )
                {
                  ChangeRouteWithForwarder(v17, v29, v36, 0);
                }
                RtmReleaseRouteInfo(v22, v15);
              }
              v24 = NumRoutes;
            }
            RtmReleaseRoutes(v22, v24, v2);
          }
          while ( !EnumRoutes );
          RtmDeleteEnumHandle(v22, EnumHandle);
          v8 = 0;
          if ( EnumRoutes != 259 )
            v8 = EnumRoutes;
          goto LABEL_60;
        }
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
          goto LABEL_60;
        LOWORD(v42) = 0;
        LOWORD(v38) = 0;
        FormatRRASErrorString(&v42, L"SetNonIPrtrOwnedS2SRoutesOnStack : Error %d creating enum handle", v8);
      }
      else
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
          goto LABEL_60;
        LOWORD(v42) = 0;
        LOWORD(v38) = 0;
        FormatRRASErrorString(
          &v42,
          L"SetNonIPrtrOwnedS2SRoutesOnStack : Error allocating %d bytes for dest. address",
          20);
      }
    }
    else
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        goto LABEL_60;
      LOWORD(v42) = 0;
      LOWORD(v38) = 0;
      FormatRRASErrorString(
        &v42,
        L"SetNonIPrtrOwnedS2SRoutesOnStack : Error allocating %d bytes for route handles",
        v18);
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v19 = (const wchar_t *)&v42;
      v20 = RasRtrMgrParamTraceError;
LABEL_57:
      v26 = &v37;
      if ( a1 != -688 )
        LODWORD(v26) = a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (_DWORD)v20,
        (_DWORD)v19,
        (_DWORD)v26,
        *(_QWORD *)(a1 + 72),
        (__int64)&v38);
    }
  }
LABEL_60:
  HeapFree(IPRouterHeap, 0, v15);
  if ( v2 )
    HeapFree(IPRouterHeap, 0, v2);
  if ( v17 )
    HeapFree(IPRouterHeap, 0, v17);
  return v8;
}

```

## disassembly

```asm
0x1800435e0  mov     r11, rsp
0x1800435e3  mov     [r11+10h], rbx
0x1800435e7  mov     [r11+18h], rsi
0x1800435eb  push    rdi
0x1800435ec  push    r12
0x1800435ee  push    r13
0x1800435f0  push    r14
0x1800435f2  push    r15
0x1800435f4  sub     rsp, 8D0h
0x1800435fb  mov     rax, cs:__security_cookie
0x180043602  xor     rax, rsp
0x180043605  mov     [rsp+8F8h+var_38], rax
0x18004360d  mov     ebx, [rcx+10h]
0x180043610  xor     r14d, r14d
0x180043613  mov     r12d, [rcx+204h]
0x18004361a  mov     rdi, rcx
0x18004361d  lea     rcx, [r11-834h]; void *
0x180043624  mov     [rsp+8F8h+EnumHandle], r14
0x180043629  xor     edx, edx; Val
0x18004362b  mov     [rsp+8F8h+BestInViews], r14d
0x180043630  mov     r8d, 7FCh; Size
0x180043636  mov     [rsp+8F8h+NumRoutes], r14d
0x18004363b  mov     dword ptr [rsp+8F8h+dwBytes], r14d
0x180043640  mov     [r11-838h], r14d
0x180043647  mov     [rsp+8F8h+var_894], ebx
0x18004364b  mov     [rsp+8F8h+var_8A4], r12d
0x180043650  call    memset_0
0x180043655  mov     r9, cs:Microsoft_Windows_RRASEnableBits
0x18004365c  lea     rsi, RasRtrmgrParamTraceInfo
0x180043663  xorps   xmm0, xmm0
0x180043666  mov     [rsp+8F8h+var_860], r14d
0x18004366e  xor     eax, eax
0x180043670  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180043677  mov     [rsp+8F8h+var_83C], eax
0x18004367e  movups  [rsp+8F8h+var_85C], xmm0
0x180043686  movups  [rsp+8F8h+var_84C], xmm0
0x18004368e  movups  [rsp+8F8h+var_870], xmm0
0x180043696  test    r9b, r9b
0x180043699  jns     short loc_180043719
0x18004369b  mov     r9d, r12d
0x18004369e  mov     word ptr [rsp+8F8h+var_838], r14w
0x1800436a7  mov     r8d, ebx
0x1800436aa  mov     word ptr [rsp+8F8h+var_860], r14w
0x1800436b3  lea     rdx, aSetnoniprtrown_2; "SetNonIPrtrOwnedS2SRoutesOnStack (If %d"...
0x1800436ba  lea     rcx, [rsp+8F8h+var_838]
0x1800436c2  call    FormatRRASErrorString
0x1800436c7  mov     r9, cs:Microsoft_Windows_RRASEnableBits
0x1800436ce  test    r9b, r9b
0x1800436d1  jns     short loc_180043719
0x1800436d3  lea     rax, [rdi+2B0h]
0x1800436da  mov     rdx, rsi
0x1800436dd  test    rax, rax
0x1800436e0  lea     r9, [rsp+8F8h+var_870]
0x1800436e8  lea     r8, [rsp+8F8h+var_838]
0x1800436f0  mov     rcx, r15
0x1800436f3  cmovnz  r9, rax
0x1800436f7  lea     rax, [rsp+8F8h+var_860]
0x1800436ff  mov     qword ptr [rsp+8F8h+MatchingFlags], rax
0x180043704  mov     rax, [rdi+48h]
0x180043708  mov     [rsp+8F8h+StartDest], rax
0x18004370d  call    McTemplateU0zjzz_EventWriteTransfer
0x180043712  mov     r9, cs:Microsoft_Windows_RRASEnableBits
0x180043719  cmp     dword ptr [rdi+90h], 2
0x180043720  jz      short loc_180043779
0x180043722  test    r9b, 80h
0x180043726  jz      short loc_18004376F
0x180043728  lea     rax, [rdi+2B0h]
0x18004372f  mov     word ptr [rsp+8F8h+var_860], r14w
0x180043738  test    rax, rax
0x18004373b  lea     r9, [rsp+8F8h+var_870]
0x180043743  lea     r8, aBailingOutSinc; "Bailing out since this is not a S2S int"...
0x18004374a  mov     rdx, rsi
0x18004374d  cmovnz  r9, rax
0x180043751  mov     rcx, r15
0x180043754  lea     rax, [rsp+8F8h+var_860]
0x18004375c  mov     qword ptr [rsp+8F8h+MatchingFlags], rax
0x180043761  mov     rax, [rdi+48h]
0x180043765  mov     [rsp+8F8h+StartDest], rax
0x18004376a  call    McTemplateU0zjzz_EventWriteTransfer
0x18004376f  mov     esi, 57h ; 'W'
0x180043774  jmp     loc_180043C16
0x180043779  cmp     dword ptr [rdi+0A8h], 4
0x180043780  jz      short loc_1800437D7
0x180043782  test    r9b, 80h
0x180043786  jz      short loc_1800437CF
0x180043788  lea     rax, [rdi+2B0h]
0x18004378f  mov     word ptr [rsp+8F8h+var_860], r14w
0x180043798  test    rax, rax
0x18004379b  lea     r9, [rsp+8F8h+var_870]
0x1800437a3  lea     r8, aInterfaceNotIn; "Interface not in connected state. Just "...
0x1800437aa  mov     rdx, rsi
0x1800437ad  cmovnz  r9, rax
0x1800437b1  mov     rcx, r15
0x1800437b4  lea     rax, [rsp+8F8h+var_860]
0x1800437bc  mov     qword ptr [rsp+8F8h+MatchingFlags], rax
0x1800437c1  mov     rax, [rdi+48h]
0x1800437c5  mov     [rsp+8F8h+StartDest], rax
0x1800437ca  call    McTemplateU0zjzz_EventWriteTransfer
0x1800437cf  mov     esi, r14d
0x1800437d2  jmp     loc_180043C16
0x1800437d7  mov     ecx, cs:g_rtmProfile.MaxNextHopsInRoute
0x1800437dd  lea     rdx, [rsp+8F8h+dwBytes]
0x1800437e2  call    RTMSIZEOFROUTEINFO
0x1800437e7  mov     esi, eax
0x1800437e9  test    eax, eax
0x1800437eb  jz      loc_180043879
0x1800437f1  test    r9b, 40h
0x1800437f5  jz      loc_180043C16
0x1800437fb  mov     r8d, eax
0x1800437fe  lea     rdx, aSetnoniprtrown_0; "SetNonIPrtrOwnedS2SRoutesOnStack : Erro"...
0x180043805  lea     rcx, [rsp+8F8h+var_838]
0x18004380d  mov     word ptr [rsp+8F8h+var_860], r14w
0x180043816  mov     word ptr [rsp+8F8h+var_838], r14w
0x18004381f  call    FormatRRASErrorString
0x180043824  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004382b  jz      loc_180043C16
0x180043831  lea     rax, [rdi+2B0h]
0x180043838  mov     rcx, r15
0x18004383b  test    rax, rax
0x18004383e  lea     r9, [rsp+8F8h+var_870]
0x180043846  lea     r8, [rsp+8F8h+var_838]
0x18004384e  cmovnz  r9, rax
0x180043852  lea     rdx, RasRtrMgrParamTraceError
0x180043859  lea     rax, [rsp+8F8h+var_860]
0x180043861  mov     qword ptr [rsp+8F8h+MatchingFlags], rax
0x180043866  mov     rax, [rdi+48h]
0x18004386a  mov     [rsp+8F8h+StartDest], rax
0x18004386f  call    McTemplateU0zjzz_EventWriteTransfer
0x180043874  jmp     loc_180043C16
0x180043879  mov     r8d, dword ptr [rsp+8F8h+dwBytes]; dwBytes
0x18004387e  xor     edx, edx; dwFlags
0x180043880  mov     rcx, cs:IPRouterHeap; hHeap
0x180043887  call    cs:__imp_HeapAlloc
0x18004388d  mov     r13, rax
0x180043890  test    rax, rax
0x180043893  jnz     short loc_1800438B3
0x180043895  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004389c  jz      loc_180043C16
0x1800438a2  mov     r8d, dword ptr [rsp+8F8h+dwBytes]
0x1800438a7  lea     rdx, aSetnoniprtrown_3; "SetNonIPrtrOwnedS2SRoutesOnStack : Erro"...
0x1800438ae  jmp     loc_180043805
0x1800438b3  mov     eax, cs:g_rtmProfile.MaxHandlesInEnum
0x1800438b9  mov     ecx, 0FFFFFFFFh
0x1800438be  shl     rax, 3
0x1800438c2  mov     r15, r14
0x1800438c5  cmp     rax, rcx
0x1800438c8  ja      loc_180043B7D
0x1800438ce  mov     rcx, cs:IPRouterHeap; hHeap
0x1800438d5  xor     edx, edx; dwFlags
0x1800438d7  mov     r8d, eax; dwBytes
0x1800438da  mov     ebx, eax
0x1800438dc  call    cs:__imp_HeapAlloc
0x1800438e2  mov     r14, rax
0x1800438e5  test    rax, rax
0x1800438e8  jnz     short loc_180043941
0x1800438ea  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x1800438f1  jz      loc_180043BD6
0x1800438f7  xor     ecx, ecx
0x1800438f9  lea     rdx, aSetnoniprtrown_4; "SetNonIPrtrOwnedS2SRoutesOnStack : Erro"...
0x180043900  mov     word ptr [rsp+8F8h+var_838], cx
0x180043908  mov     r8d, ebx
0x18004390b  mov     word ptr [rsp+8F8h+var_860], cx
0x180043913  lea     rcx, [rsp+8F8h+var_838]
0x18004391b  call    FormatRRASErrorString
0x180043920  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180043927  jz      loc_180043BD6
0x18004392d  lea     r8, [rsp+8F8h+var_838]
0x180043935  lea     rdx, RasRtrMgrParamTraceError
0x18004393c  jmp     loc_180043B9E
0x180043941  mov     rcx, cs:IPRouterHeap; hHeap
0x180043948  mov     ebx, 14h
0x18004394d  mov     r8d, ebx; dwBytes
0x180043950  xor     edx, edx; dwFlags
0x180043952  call    cs:__imp_HeapAlloc
0x180043958  mov     r15, rax
0x18004395b  test    rax, rax
0x18004395e  jnz     short loc_180043998
0x180043960  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180043967  jz      loc_180043BD6
0x18004396d  xor     ecx, ecx
0x18004396f  lea     rdx, aSetnoniprtrown; "SetNonIPrtrOwnedS2SRoutesOnStack : Erro"...
0x180043976  mov     word ptr [rsp+8F8h+var_838], cx
0x18004397e  mov     r8d, ebx
0x180043981  mov     word ptr [rsp+8F8h+var_860], cx
0x180043989  lea     rcx, [rsp+8F8h+var_838]
0x180043991  call    FormatRRASErrorString
0x180043996  jmp     short loc_180043920
0x180043998  mov     eax, r12d
0x18004399b  lea     rsi, [rdi+2B0h]
0x1800439a2  neg     eax
0x1800439a4  mov     [rsp+8F8h+var_878], rsi
0x1800439ac  mov     r8d, 2716h; unsigned int
0x1800439b2  mov     rcx, rsi; struct _GUID *
0x1800439b5  sbb     ebx, ebx
0x1800439b7  and     ebx, 0FFFFFFCAh
0x1800439ba  add     ebx, 57h ; 'W'
0x1800439bd  mov     edx, ebx; unsigned int
0x1800439bf  call    GetRtmRegistrationHandle
0x1800439c4  mov     r8d, 2717h; unsigned int
0x1800439ca  mov     [rsp+8F8h+dwBytes], rax
0x1800439cf  mov     edx, ebx; unsigned int
0x1800439d1  mov     rcx, rsi; struct _GUID *
0x1800439d4  call    GetRtmRegistrationHandle
0x1800439d9  mov     r8d, 3; unsigned int
0x1800439df  mov     [rsp+8F8h+var_888], rax
0x1800439e4  mov     edx, ebx; unsigned int
0x1800439e6  mov     rcx, rsi; struct _GUID *
0x1800439e9  call    GetRtmRegistrationHandle
0x1800439ee  mov     r8d, 2; unsigned int
0x1800439f4  mov     [rsp+8F8h+var_880], rax
0x1800439f9  mov     edx, ebx; unsigned int
0x1800439fb  mov     rcx, rsi; struct _GUID *
0x1800439fe  call    GetRtmRegistrationHandle
0x180043a03  mov     ecx, [rsp+8F8h+var_894]
0x180043a07  mov     r12, rax
0x180043a0a  lea     rax, [rsp+8F8h+EnumHandle]
0x180043a0f  xor     r9d, r9d; EnumFlags
0x180043a12  mov     [rsp+8F8h+RtmEnumHandle], rax; RtmEnumHandle
0x180043a17  xor     edx, edx; DestHandle
0x180043a19  mov     [rsp+8F8h+CriteriaInterface], ecx; CriteriaInterface
0x180043a1d  mov     rcx, r12; RtmRegHandle
0x180043a20  mov     [rsp+8F8h+CriteriaRoute], 0; CriteriaRoute
0x180043a29  mov     [rsp+8F8h+MatchingFlags], 10h; MatchingFlags
0x180043a31  lea     r8d, [r9+1]; TargetViews
0x180043a35  mov     [rsp+8F8h+StartDest], 0; StartDest
0x180043a3e  call    cs:__imp_RtmCreateRouteEnum
0x180043a44  mov     esi, eax
0x180043a46  test    eax, eax
0x180043a48  jz      short loc_180043A78
0x180043a4a  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180043a51  jz      loc_180043BD6
0x180043a57  xor     eax, eax
0x180043a59  lea     rdx, aSetnoniprtrown_5; "SetNonIPrtrOwnedS2SRoutesOnStack : Erro"...
0x180043a60  mov     word ptr [rsp+8F8h+var_838], ax
0x180043a68  mov     r8d, esi
0x180043a6b  mov     word ptr [rsp+8F8h+var_860], ax
0x180043a73  jmp     loc_180043913
0x180043a78  mov     eax, cs:g_rtmProfile.MaxHandlesInEnum
0x180043a7e  lea     r8, [rsp+8F8h+NumRoutes]; NumRoutes
0x180043a83  mov     rdx, [rsp+8F8h+EnumHandle]; EnumHandle
0x180043a88  mov     r9, r14; RouteHandles
0x180043a8b  mov     rcx, r12; RtmRegHandle
0x180043a8e  mov     [rsp+8F8h+NumRoutes], eax
0x180043a92  call    cs:__imp_RtmGetEnumRoutes
0x180043a98  mov     ebx, eax
0x180043a9a  test    eax, eax
0x180043a9c  jnz     loc_180043B62
0x180043aa2  mov     edx, [rsp+8F8h+NumRoutes]
0x180043aa6  xor     edi, edi
0x180043aa8  test    edx, edx
0x180043aaa  jz      loc_180043B4E
0x180043ab0  mov     rdx, [r14+rdi*8]; RouteHandle
0x180043ab4  lea     r8, [rsp+8F8h+BestInViews]; BestInViews
0x180043ab9  mov     rcx, r12; RtmRegHandle
0x180043abc  call    cs:__imp_RtmIsBestRoute
0x180043ac2  mov     ebx, eax
0x180043ac4  test    eax, eax
0x180043ac6  jnz     short loc_180043B40
0x180043ac8  test    byte ptr [rsp+8F8h+BestInViews], 1
0x180043acd  jz      short loc_180043B40
0x180043acf  mov     rdx, [r14+rdi*8]; RouteHandle
0x180043ad3  mov     r9, r15; DestAddress
0x180043ad6  mov     r8, r13; RouteInfo
0x180043ad9  mov     rcx, r12; RtmRegHandle
0x180043adc  call    cs:__imp_RtmGetRouteInfo
0x180043ae2  test    eax, eax
0x180043ae4  jnz     short loc_180043B40
0x180043ae6  mov     rax, [rsp+8F8h+dwBytes]
0x180043aeb  cmp     [r13+8], rax
0x180043aef  jz      short loc_180043B34
0x180043af1  mov     rax, [rsp+8F8h+var_888]
0x180043af6  cmp     [r13+8], rax
0x180043afa  jz      short loc_180043B34
0x180043afc  mov     rax, [rsp+8F8h+var_880]
0x180043b01  cmp     [r13+8], rax
0x180043b05  jz      short loc_180043B34
0x180043b07  mov     rax, [rsp+8F8h+var_878]
0x180043b0f  mov     rdx, r13
0x180043b12  mov     dword ptr [rsp+8F8h+CriteriaRoute], ebx; int
0x180043b16  mov     rcx, r15; pNetAddress
0x180043b19  mov     qword ptr [rsp+8F8h+MatchingFlags], rax; struct _GUID *
0x180043b1e  mov     eax, [rsp+8F8h+var_8A4]
0x180043b22  mov     dword ptr [rsp+8F8h+StartDest], eax; int
0x180043b26  lea     eax, [rbx+1]
0x180043b29  mov     r9d, eax
0x180043b2c  mov     r8d, eax
0x180043b2f  call    ChangeRouteWithForwarder
0x180043b34  mov     rdx, r13; RouteInfo
0x180043b37  mov     rcx, r12; RtmRegHandle
0x180043b3a  call    cs:__imp_RtmReleaseRouteInfo
0x180043b40  mov     edx, [rsp+8F8h+NumRoutes]; NumRoutes
0x180043b44  inc     edi
0x180043b46  cmp     edi, edx
0x180043b48  jb      loc_180043AB0
0x180043b4e  mov     r8, r14; RouteHandles
0x180043b51  mov     rcx, r12; RtmRegHandle
0x180043b54  call    cs:__imp_RtmReleaseRoutes
0x180043b5a  test    ebx, ebx
0x180043b5c  jz      loc_180043A78
0x180043b62  mov     rdx, [rsp+8F8h+EnumHandle]; EnumHandle
  ... truncated ...
```

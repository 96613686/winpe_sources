# AddNetmgmtDefaultRoutesToForwarder

- ea: `0x1800482a4`
- end: `0x1800488b7`
- name: `AddNetmgmtDefaultRoutesToForwarder`
- size: `1555`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004c950`

## callees

- `0x180011790`
- `0x180046848`
- `0x1800482a4`
- `0x180051ef8`
- `0x180057c48`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800484e0`
- `KERNEL32!HeapFree` at `0x1800486a3`
- `KERNEL32!HeapFree` at `0x1800484e0`
- `KERNEL32!HeapFree` at `0x1800486a3`
- `KERNEL32!HeapAlloc` at `0x180048368`
- `KERNEL32!HeapAlloc` at `0x180048459`
- `KERNEL32!HeapAlloc` at `0x180048368`
- `KERNEL32!HeapAlloc` at `0x180048459`
- `rtm!RtmReleaseRoutes` at `0x1800487f9`
- `rtm!RtmReleaseRoutes` at `0x1800487f9`
- `rtm!RtmGetEnumRoutes` at `0x180048560`
- `rtm!RtmGetEnumRoutes` at `0x180048560`
- `rtm!RtmCreateRouteEnum` at `0x18004851c`
- `rtm!RtmCreateRouteEnum` at `0x18004851c`
- `rtm!RtmDeleteEnumHandle` at `0x180048627`
- `rtm!RtmDeleteEnumHandle` at `0x180048627`
- `rtm!RtmReleaseRouteInfo` at `0x180048709`
- `rtm!RtmReleaseRouteInfo` at `0x180048709`
- `rtm!RtmGetRouteInfo` at `0x1800486cc`
- `rtm!RtmGetRouteInfo` at `0x1800486cc`

## pseudocode

```c
__int64 __fastcall AddNetmgmtDefaultRoutesToForwarder(__int64 a1, int a2, struct _GUID *a3)
{
  void *RtmRegistrationHandle; // r15
  unsigned __int64 v7; // rax
  HANDLE *v8; // r14
  __int128 *v9; // r9
  DWORD v11; // esi
  __int128 *v12; // r9
  struct _RTM_ROUTE_INFO *v13; // r12
  __int128 *v14; // r9
  struct _RTM_ROUTE_INFO *v15; // r8
  DWORD v16; // eax
  DWORD EnumRoutes; // eax
  __int64 v18; // r8
  const wchar_t *v19; // rdx
  __int128 *v20; // r9
  __int128 *v21; // r9
  __int128 *v22; // r9
  __int64 i; // rsi
  UINT v24; // edx
  DWORD RouteInfo; // eax
  DWORD v26; // eax
  __int128 *v27; // r9
  __int128 *v28; // r9
  DWORD v29; // eax
  __int128 *v30; // r9
  unsigned int NumRoutes; // [rsp+50h] [rbp-B0h] BYREF
  int v32; // [rsp+54h] [rbp-ACh]
  SIZE_T dwBytes; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE EnumHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v35; // [rsp+68h] [rbp-98h] BYREF
  int v36; // [rsp+78h] [rbp-88h] BYREF
  __int128 v37; // [rsp+7Ch] [rbp-84h]
  __int128 v38; // [rsp+8Ch] [rbp-74h]
  int v39; // [rsp+9Ch] [rbp-64h]
  int v40; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v41[2044]; // [rsp+A4h] [rbp-5Ch] BYREF

  v32 = a2;
  NumRoutes = 0;
  EnumHandle = 0;
  LODWORD(dwBytes) = 0;
  v40 = 0;
  memset_0(v41, 0, sizeof(v41));
  v36 = 0;
  v39 = 0;
  v37 = 0;
  v38 = 0;
  v35 = 0;
  RtmRegistrationHandle = (void *)GetRtmRegistrationHandle(a3, a2 != 0 ? 33 : 87, 3u);
  NumRoutes = *(_DWORD *)(a1 + 52);
  v7 = 8LL * NumRoutes;
  if ( v7 > 0xFFFFFFFF )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v40) = 0;
      LOWORD(v36) = 0;
      FormatRRASErrorString(
        &v40,
        L"AddNetmgmtDefaultRoutesToForwarder: Arithmetic overflow error allocating %d handles for route handles");
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v30 = &v35;
        if ( a3 )
          LODWORD(v30) = (_DWORD)a3;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v40,
          (_DWORD)v30,
          0,
          (__int64)&v36);
      }
    }
    return 534;
  }
  v8 = (HANDLE *)HeapAlloc(IPRouterHeap, 0, (unsigned int)v7);
  if ( !v8 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v40) = 0;
      LOWORD(v36) = 0;
      FormatRRASErrorString(
        &v40,
        L"AddNetmgmtDefaultRoutesToForwarder: error allocating %d bytes for route handles",
        8LL * NumRoutes);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v9 = &v35;
        if ( a3 )
          LODWORD(v9) = (_DWORD)a3;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v40,
          (_DWORD)v9,
          0,
          (__int64)&v36);
      }
    }
    return 8;
  }
  v11 = RTMSIZEOFROUTEINFO(g_rtmProfile.MaxNextHopsInRoute, &dwBytes);
  if ( v11 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v36) = 0;
      v12 = &v35;
      if ( a3 )
        LODWORD(v12) = (_DWORD)a3;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrMgrParamTraceError,
        (unsigned int)L"AddNetmgmtDefaultRoutesToForwarder: Arithmetic overflow error allocating memory for route info",
        (_DWORD)v12,
        0,
        (__int64)&v36);
    }
LABEL_21:
    v15 = (struct _RTM_ROUTE_INFO *)v8;
    goto LABEL_22;
  }
  v13 = (struct _RTM_ROUTE_INFO *)HeapAlloc(IPRouterHeap, 0, (unsigned int)dwBytes);
  if ( !v13 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v40) = 0;
      LOWORD(v36) = 0;
      FormatRRASErrorString(
        &v40,
        L"AddNetmgmtDefaultRoutesToForwarder: error allocating %d bytes for route info",
        (unsigned int)dwBytes);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v14 = &v35;
        if ( a3 )
          LODWORD(v14) = (_DWORD)a3;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v40,
          (_DWORD)v14,
          0,
          (__int64)&v36);
      }
    }
    v11 = 8;
    goto LABEL_21;
  }
  v16 = RtmCreateRouteEnum(RtmRegistrationHandle, *(RTM_DEST_HANDLE *)a1, 1u, 0x10000u, 0, 0, 0, 0, &EnumHandle);
  v11 = v16;
  if ( v16 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v40) = 0;
      LOWORD(v36) = 0;
      FormatRRASErrorString(&v40, L"AddNetmgmtDefaultRoutesToForwarder: error %d creating route enumeration", v16);
LABEL_40:
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v22 = &v35;
        if ( a3 )
          LODWORD(v22) = (_DWORD)a3;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v40,
          (_DWORD)v22,
          0,
          (__int64)&v36);
      }
    }
    goto LABEL_44;
  }
  EnumRoutes = RtmGetEnumRoutes(RtmRegistrationHandle, EnumHandle, &NumRoutes, v8);
  v18 = EnumRoutes;
  if ( EnumRoutes )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v19 = L"ProcessDefaultRouteChanges:error %d enumerating routes";
      LOWORD(v36) = 0;
LABEL_29:
      LOWORD(v40) = 0;
      FormatRRASErrorString(&v40, v19, v18);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v20 = &v35;
        if ( a3 )
          LODWORD(v20) = (_DWORD)a3;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v40,
          (_DWORD)v20,
          0,
          (__int64)&v36);
      }
    }
    goto LABEL_33;
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v24 = NumRoutes;
    if ( (unsigned int)i >= NumRoutes )
      break;
    RouteInfo = RtmGetRouteInfo(RtmRegistrationHandle, v8[i], v13, 0);
    if ( RouteInfo )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        continue;
      LOWORD(v40) = 0;
      LOWORD(v36) = 0;
      FormatRRASErrorString(
        &v40,
        L"ProcessDefaultRouteChanges: error %d getting route info for route %d",
        RouteInfo,
        (unsigned int)i);
    }
    else
    {
      ChangeRouteWithForwarder((PRTM_NET_ADDRESS)(a1 + 8), v32, a3, 1);
      v26 = RtmReleaseRouteInfo(RtmRegistrationHandle, v13);
      if ( !v26 || (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        continue;
      LOWORD(v40) = 0;
      LOWORD(v36) = 0;
      FormatRRASErrorString(&v40, L"ProcessDefaultRouteChanges: error %d releasing route info ", v26);
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v27 = &v35;
      if ( a3 )
        LODWORD(v27) = (_DWORD)a3;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrMgrParamTraceError,
        (unsigned int)&v40,
        (_DWORD)v27,
        0,
        (__int64)&v36);
    }
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v28 = &v35;
    LOWORD(v36) = 0;
    if ( a3 )
      LODWORD(v28) = (_DWORD)a3;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Releasing routes to 0/0",
      (_DWORD)v28,
      0,
      (__int64)&v36);
    v24 = NumRoutes;
  }
  v29 = RtmReleaseRoutes(RtmRegistrationHandle, v24, v8);
  if ( v29 && (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
  {
    v19 = L"ProcessDefaultRouteChanges: error %d deleting enum handle";
    LOWORD(v36) = 0;
    v18 = v29;
    goto LABEL_29;
  }
LABEL_33:
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v21 = &v35;
    LOWORD(v36) = 0;
    if ( a3 )
      LODWORD(v21) = (_DWORD)a3;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Releasing route enum for 0/0",
      (_DWORD)v21,
      0,
      (__int64)&v36);
  }
  v11 = RtmDeleteEnumHandle(RtmRegistrationHandle, EnumHandle);
  if ( v11 && (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
  {
    LOWORD(v40) = 0;
    LOWORD(v36) = 0;
    FormatRRASErrorString(&v40, L"ProcessDefaultRouteChanges: error %d deleting enum handle", v11);
    goto LABEL_40;
  }
LABEL_44:
  HeapFree(IPRouterHeap, 0, v8);
  v15 = v13;
LABEL_22:
  HeapFree(IPRouterHeap, 0, v15);
  return v11;
}

```

## disassembly

```asm
0x1800482a4  mov     [rsp-8+arg_18], rbx
0x1800482a9  push    rbp
0x1800482aa  push    rsi
0x1800482ab  push    rdi
0x1800482ac  push    r12
0x1800482ae  push    r13
0x1800482b0  push    r14
0x1800482b2  push    r15
0x1800482b4  lea     rbp, [rsp-7B0h]
0x1800482bc  sub     rsp, 8B0h
0x1800482c3  mov     rax, cs:__security_cookie
0x1800482ca  xor     rax, rsp
0x1800482cd  mov     [rbp+7E0h+var_40], rax
0x1800482d4  xor     r12d, r12d
0x1800482d7  mov     [rsp+8E0h+var_88C], edx
0x1800482db  mov     rdi, r8
0x1800482de  mov     [rsp+8E0h+NumRoutes], r12d
0x1800482e3  mov     ebx, edx
0x1800482e5  mov     [rsp+8E0h+EnumHandle], r12
0x1800482ea  mov     r13, rcx
0x1800482ed  mov     dword ptr [rsp+8E0h+dwBytes], r12d
0x1800482f2  xor     edx, edx; Val
0x1800482f4  mov     [rbp+7E0h+var_840], r12d
0x1800482f8  mov     r8d, 7FCh; Size
0x1800482fe  lea     rcx, [rbp+7E0h+var_83C]; void *
0x180048302  call    memset_0
0x180048307  xor     eax, eax
0x180048309  mov     [rsp+8E0h+var_868], r12d
0x18004830e  xorps   xmm0, xmm0
0x180048311  mov     [rbp+7E0h+var_844], eax
0x180048314  mov     eax, ebx
0x180048316  lea     r8d, [r12+3]; unsigned int
0x18004831b  neg     eax
0x18004831d  mov     rcx, rdi; struct _GUID *
0x180048320  movups  [rsp+8E0h+var_864], xmm0
0x180048325  sbb     edx, edx
0x180048327  and     edx, 0FFFFFFCAh
0x18004832a  add     edx, 57h ; 'W'; unsigned int
0x18004832d  movups  [rbp+7E0h+var_854], xmm0
0x180048331  movups  [rsp+8E0h+var_878], xmm0
0x180048336  call    GetRtmRegistrationHandle
0x18004833b  mov     r8d, [r13+34h]
0x18004833f  mov     r15, rax
0x180048342  mov     eax, r8d
0x180048345  mov     [rsp+8E0h+NumRoutes], r8d
0x18004834a  shl     rax, 3
0x18004834e  mov     ecx, 0FFFFFFFFh
0x180048353  cmp     rax, rcx
0x180048356  ja      loc_180048829
0x18004835c  mov     rcx, cs:IPRouterHeap; hHeap
0x180048363  xor     edx, edx; dwFlags
0x180048365  mov     r8d, eax; dwBytes
0x180048368  call    cs:__imp_HeapAlloc
0x18004836e  mov     r14, rax
0x180048371  test    rax, rax
0x180048374  jnz     short loc_1800483E8
0x180048376  mov     bl, 40h ; '@'
0x180048378  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18004837e  jz      short loc_1800483DE
0x180048380  mov     r8d, [rsp+8E0h+NumRoutes]
0x180048385  lea     rdx, aAddnetmgmtdefa_0; "AddNetmgmtDefaultRoutesToForwarder: err"...
0x18004838c  shl     r8, 3
0x180048390  lea     rcx, [rbp+7E0h+var_840]
0x180048394  mov     word ptr [rbp+7E0h+var_840], r12w
0x180048399  mov     word ptr [rsp+8E0h+var_868], r12w
0x18004839f  call    FormatRRASErrorString
0x1800483a4  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x1800483aa  jz      short loc_1800483DE
0x1800483ac  test    rdi, rdi
0x1800483af  lea     rax, [rsp+8E0h+var_868]
0x1800483b4  mov     qword ptr [rsp+8E0h+MatchingFlags], rax
0x1800483b9  lea     r9, [rsp+8E0h+var_878]
0x1800483be  cmovnz  r9, rdi
0x1800483c2  mov     [rsp+8E0h+StartDest], r12
0x1800483c7  lea     r8, [rbp+7E0h+var_840]
0x1800483cb  lea     rdx, RasRtrMgrParamTraceError
0x1800483d2  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800483d9  call    McTemplateU0zjzz_EventWriteTransfer
0x1800483de  mov     eax, 8
0x1800483e3  jmp     loc_18004888D
0x1800483e8  mov     ecx, cs:g_rtmProfile.MaxNextHopsInRoute
0x1800483ee  lea     rdx, [rsp+8E0h+dwBytes]
0x1800483f3  call    RTMSIZEOFROUTEINFO
0x1800483f8  mov     esi, eax
0x1800483fa  test    eax, eax
0x1800483fc  jz      short loc_18004844B
0x1800483fe  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180048405  jz      loc_1800484D4
0x18004840b  test    rdi, rdi
0x18004840e  mov     word ptr [rsp+8E0h+var_868], r12w
0x180048414  lea     rax, [rsp+8E0h+var_868]
0x180048419  mov     qword ptr [rsp+8E0h+MatchingFlags], rax
0x18004841e  lea     r9, [rsp+8E0h+var_878]
0x180048423  cmovnz  r9, rdi
0x180048427  mov     [rsp+8E0h+StartDest], r12
0x18004842c  lea     r8, aAddnetmgmtdefa_1; "AddNetmgmtDefaultRoutesToForwarder: Ari"...
0x180048433  lea     rdx, RasRtrMgrParamTraceError
0x18004843a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180048441  call    McTemplateU0zjzz_EventWriteTransfer
0x180048446  jmp     loc_1800484D4
0x18004844b  mov     r8d, dword ptr [rsp+8E0h+dwBytes]; dwBytes
0x180048450  xor     edx, edx; dwFlags
0x180048452  mov     rcx, cs:IPRouterHeap; hHeap
0x180048459  call    cs:__imp_HeapAlloc
0x18004845f  xor     esi, esi
0x180048461  mov     r12, rax
0x180048464  test    rax, rax
0x180048467  jnz     loc_1800484ED
0x18004846d  mov     bl, 40h ; '@'
0x18004846f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180048475  jz      short loc_1800484CF
0x180048477  mov     r8d, dword ptr [rsp+8E0h+dwBytes]
0x18004847c  lea     rdx, aAddnetmgmtdefa; "AddNetmgmtDefaultRoutesToForwarder: err"...
0x180048483  lea     rcx, [rbp+7E0h+var_840]
0x180048487  mov     word ptr [rbp+7E0h+var_840], si
0x18004848b  mov     word ptr [rsp+8E0h+var_868], si
0x180048490  call    FormatRRASErrorString
0x180048495  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18004849b  jz      short loc_1800484CF
0x18004849d  test    rdi, rdi
0x1800484a0  lea     rax, [rsp+8E0h+var_868]
0x1800484a5  mov     qword ptr [rsp+8E0h+MatchingFlags], rax
0x1800484aa  lea     r9, [rsp+8E0h+var_878]
0x1800484af  cmovnz  r9, rdi
0x1800484b3  mov     [rsp+8E0h+StartDest], rsi
0x1800484b8  lea     r8, [rbp+7E0h+var_840]
0x1800484bc  lea     rdx, RasRtrMgrParamTraceError
0x1800484c3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800484ca  call    McTemplateU0zjzz_EventWriteTransfer
0x1800484cf  mov     esi, 8
0x1800484d4  mov     r8, r14; lpMem
0x1800484d7  mov     rcx, cs:IPRouterHeap; hHeap
0x1800484de  xor     edx, edx; dwFlags
0x1800484e0  call    cs:__imp_HeapFree
0x1800484e6  mov     eax, esi
0x1800484e8  jmp     loc_18004888D
0x1800484ed  mov     rdx, [r13+0]; DestHandle
0x1800484f1  lea     rax, [rsp+8E0h+EnumHandle]
0x1800484f6  mov     [rsp+8E0h+RtmEnumHandle], rax; RtmEnumHandle
0x1800484fb  mov     r9d, 10000h; EnumFlags
0x180048501  mov     [rsp+8E0h+CriteriaInterface], esi; CriteriaInterface
0x180048505  mov     r8d, 1; TargetViews
0x18004850b  mov     [rsp+8E0h+CriteriaRoute], rsi; CriteriaRoute
0x180048510  mov     rcx, r15; RtmRegHandle
0x180048513  mov     [rsp+8E0h+MatchingFlags], esi; MatchingFlags
0x180048517  mov     [rsp+8E0h+StartDest], rsi; StartDest
0x18004851c  call    cs:__imp_RtmCreateRouteEnum
0x180048522  mov     esi, eax
0x180048524  test    eax, eax
0x180048526  jz      short loc_180048550
0x180048528  mov     bl, 40h ; '@'
0x18004852a  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180048530  jz      loc_180048697
0x180048536  xor     ecx, ecx
0x180048538  lea     rdx, aAddnetmgmtdefa_2; "AddNetmgmtDefaultRoutesToForwarder: err"...
0x18004853f  mov     word ptr [rbp+7E0h+var_840], cx
0x180048543  mov     r8d, eax
0x180048546  mov     word ptr [rsp+8E0h+var_868], cx
0x18004854b  jmp     loc_180048650
0x180048550  mov     rdx, [rsp+8E0h+EnumHandle]; EnumHandle
0x180048555  lea     r8, [rsp+8E0h+NumRoutes]; NumRoutes
0x18004855a  mov     r9, r14; RouteHandles
0x18004855d  mov     rcx, r15; RtmRegHandle
0x180048560  call    cs:__imp_RtmGetEnumRoutes
0x180048566  mov     r8d, eax
0x180048569  mov     bl, 40h ; '@'
0x18004856b  test    eax, eax
0x18004856d  jz      loc_1800486B1
0x180048573  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180048579  jz      short loc_1800485D6
0x18004857b  xor     ecx, ecx
0x18004857d  lea     rdx, aProcessdefault_3; "ProcessDefaultRouteChanges:error %d enu"...
0x180048584  xor     eax, eax
0x180048586  mov     word ptr [rsp+8E0h+var_868], ax
0x18004858b  mov     word ptr [rbp+7E0h+var_840], cx
0x18004858f  lea     rcx, [rbp+7E0h+var_840]
0x180048593  call    FormatRRASErrorString
0x180048598  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18004859e  jz      short loc_1800485D6
0x1800485a0  test    rdi, rdi
0x1800485a3  lea     rax, [rsp+8E0h+var_868]
0x1800485a8  mov     qword ptr [rsp+8E0h+MatchingFlags], rax
0x1800485ad  lea     r9, [rsp+8E0h+var_878]
0x1800485b2  cmovnz  r9, rdi
0x1800485b6  mov     [rsp+8E0h+StartDest], 0
0x1800485bf  lea     r8, [rbp+7E0h+var_840]
0x1800485c3  lea     rdx, RasRtrMgrParamTraceError
0x1800485ca  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800485d1  call    McTemplateU0zjzz_EventWriteTransfer
0x1800485d6  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800485dd  jz      short loc_18004861F
0x1800485df  xor     eax, eax
0x1800485e1  lea     r9, [rsp+8E0h+var_878]
0x1800485e6  mov     word ptr [rsp+8E0h+var_868], ax
0x1800485eb  lea     r8, aReleasingRoute; "Releasing route enum for 0/0"
0x1800485f2  test    rdi, rdi
0x1800485f5  lea     rax, [rsp+8E0h+var_868]
0x1800485fa  mov     qword ptr [rsp+8E0h+MatchingFlags], rax
0x1800485ff  lea     rdx, RasRtrmgrParamTraceInfo
0x180048606  cmovnz  r9, rdi
0x18004860a  mov     [rsp+8E0h+StartDest], 0
0x180048613  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004861a  call    McTemplateU0zjzz_EventWriteTransfer
0x18004861f  mov     rdx, [rsp+8E0h+EnumHandle]; EnumHandle
0x180048624  mov     rcx, r15; RtmRegHandle
0x180048627  call    cs:__imp_RtmDeleteEnumHandle
0x18004862d  mov     esi, eax
0x18004862f  test    eax, eax
0x180048631  jz      short loc_180048697
0x180048633  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180048639  jz      short loc_180048697
0x18004863b  xor     eax, eax
0x18004863d  lea     rdx, aProcessdefault; "ProcessDefaultRouteChanges: error %d de"...
0x180048644  mov     word ptr [rbp+7E0h+var_840], ax
0x180048648  mov     r8d, esi
0x18004864b  mov     word ptr [rsp+8E0h+var_868], ax
0x180048650  lea     rcx, [rbp+7E0h+var_840]
0x180048654  call    FormatRRASErrorString
0x180048659  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18004865f  jz      short loc_180048697
0x180048661  test    rdi, rdi
0x180048664  lea     rax, [rsp+8E0h+var_868]
0x180048669  mov     qword ptr [rsp+8E0h+MatchingFlags], rax
0x18004866e  lea     r9, [rsp+8E0h+var_878]
0x180048673  cmovnz  r9, rdi
0x180048677  mov     [rsp+8E0h+StartDest], 0
0x180048680  lea     r8, [rbp+7E0h+var_840]
0x180048684  lea     rdx, RasRtrMgrParamTraceError
0x18004868b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180048692  call    McTemplateU0zjzz_EventWriteTransfer
0x180048697  mov     rcx, cs:IPRouterHeap; hHeap
0x18004869e  mov     r8, r14; lpMem
0x1800486a1  xor     edx, edx; dwFlags
0x1800486a3  call    cs:__imp_HeapFree
0x1800486a9  mov     r8, r12
0x1800486ac  jmp     loc_1800484D7
0x1800486b1  xor     esi, esi
0x1800486b3  mov     edx, [rsp+8E0h+NumRoutes]
0x1800486b7  cmp     esi, edx
0x1800486b9  jnb     loc_1800487A6
0x1800486bf  mov     rdx, [r14+rsi*8]; RouteHandle
0x1800486c3  xor     r9d, r9d; DestAddress
0x1800486c6  mov     r8, r12; RouteInfo
0x1800486c9  mov     rcx, r15; RtmRegHandle
0x1800486cc  call    cs:__imp_RtmGetRouteInfo
0x1800486d2  mov     r8d, eax
0x1800486d5  test    eax, eax
0x1800486d7  jnz     loc_18004877E
0x1800486dd  lea     edx, [rax+1]
0x1800486e0  xor     r9d, r9d
0x1800486e3  mov     eax, [rsp+8E0h+var_88C]
0x1800486e7  lea     rcx, [r13+8]; pNetAddress
0x1800486eb  mov     dword ptr [rsp+8E0h+CriteriaRoute], edx; int
0x1800486ef  mov     r8d, edx
0x1800486f2  mov     qword ptr [rsp+8E0h+MatchingFlags], rdi; struct _GUID *
0x1800486f7  mov     rdx, r12
0x1800486fa  mov     dword ptr [rsp+8E0h+StartDest], eax; int
0x1800486fe  call    ChangeRouteWithForwarder
0x180048703  mov     rdx, r12; RouteInfo
0x180048706  mov     rcx, r15; RtmRegHandle
0x180048709  call    cs:__imp_RtmReleaseRouteInfo
0x18004870f  test    eax, eax
0x180048711  jz      short loc_180048777
0x180048713  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180048719  jz      short loc_180048777
0x18004871b  xor     ecx, ecx
0x18004871d  lea     rdx, aProcessdefault_8; "ProcessDefaultRouteChanges: error %d re"...
0x180048724  mov     word ptr [rbp+7E0h+var_840], cx
0x180048728  mov     r8d, eax
0x18004872b  mov     word ptr [rsp+8E0h+var_868], cx
0x180048730  lea     rcx, [rbp+7E0h+var_840]
0x180048734  call    FormatRRASErrorString
0x180048739  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18004873f  jz      short loc_180048777
0x180048741  test    rdi, rdi
0x180048744  lea     rax, [rsp+8E0h+var_868]
0x180048749  mov     qword ptr [rsp+8E0h+MatchingFlags], rax
0x18004874e  lea     r9, [rsp+8E0h+var_878]
0x180048753  cmovnz  r9, rdi
0x180048757  mov     [rsp+8E0h+StartDest], 0
0x180048760  lea     r8, [rbp+7E0h+var_840]
0x180048764  lea     rdx, RasRtrMgrParamTraceError
0x18004876b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180048772  call    McTemplateU0zjzz_EventWriteTransfer
0x180048777  inc     esi
0x180048779  jmp     loc_1800486B3
0x18004877e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180048784  jz      short loc_180048777
0x180048786  xor     eax, eax
0x180048788  lea     rdx, aProcessdefault_11; "ProcessDefaultRouteChanges: error %d ge"...
0x18004878f  mov     r9d, esi
0x180048792  mov     word ptr [rbp+7E0h+var_840], ax
0x180048796  lea     rcx, [rbp+7E0h+var_840]
0x18004879a  mov     word ptr [rsp+8E0h+var_868], ax
0x18004879f  call    FormatRRASErrorString
0x1800487a4  jmp     short loc_180048739
0x1800487a6  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800487ad  jz      short loc_1800487F3
0x1800487af  xor     eax, eax
0x1800487b1  lea     r9, [rsp+8E0h+var_878]
  ... truncated ...
```

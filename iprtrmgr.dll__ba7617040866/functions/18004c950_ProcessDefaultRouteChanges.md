# ProcessDefaultRouteChanges

- ea: `0x18004c950`
- end: `0x18004d13e`
- name: `ProcessDefaultRouteChanges`
- size: `2030`
- prototype: `__int64 __fastcall(RTM_NOTIFY_HANDLE NotifyHandle, int, struct _GUID *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004d830`

## callees

- `0x18000ac60`
- `0x180011790`
- `0x180046848`
- `0x1800482a4`
- `0x18004c950`
- `0x180051ec8`
- `0x180051ef8`
- `0x180057c48`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18004cbe6`
- `KERNEL32!HeapFree` at `0x18004ccd2`
- `KERNEL32!HeapFree` at `0x18004d0a9`
- `KERNEL32!HeapFree` at `0x18004d0bb`
- `KERNEL32!HeapFree` at `0x18004cbe6`
- `KERNEL32!HeapFree` at `0x18004ccd2`
- `KERNEL32!HeapFree` at `0x18004d0a9`
- `KERNEL32!HeapFree` at `0x18004d0bb`
- `KERNEL32!HeapAlloc` at `0x18004cae2`
- `KERNEL32!HeapAlloc` at `0x18004cc44`
- `KERNEL32!HeapAlloc` at `0x18004cae2`
- `KERNEL32!HeapAlloc` at `0x18004cc44`
- `rtm!RtmReleaseRouteInfo` at `0x18004ce8e`
- `rtm!RtmReleaseRouteInfo` at `0x18004ce8e`
- `rtm!RtmGetRouteInfo` at `0x18004ce55`
- `rtm!RtmGetRouteInfo` at `0x18004ce55`
- `rtm!RtmReleaseChangedDests` at `0x18004cf9c`
- `rtm!RtmReleaseChangedDests` at `0x18004cf9c`
- `rtm!RtmGetChangedDests` at `0x18004cd67`
- `rtm!RtmGetChangedDests` at `0x18004cd67`

## string_xrefs

- `0x18004ca6a`: `ProcessDefaultRouteChanges : Arithmatic Overflow during memory allocation for route info`
- `0x18004cbc0`: `ProcessDefaultRouteChanges : Arithmatic Overflow during memory allocation for dest. info`

## pseudocode

```c
__int64 __fastcall ProcessDefaultRouteChanges(RTM_NOTIFY_HANDLE NotifyHandle, int a2, struct _GUID *a3)
{
  RTM_NOTIFY_HANDLE v5; // r14
  __int128 *v6; // r9
  unsigned int v7; // esi
  char v8; // r9
  __int128 *v9; // r9
  struct _RTM_ROUTE_INFO *v11; // r15
  char v12; // al
  __int128 *v13; // r9
  __int128 *v14; // r9
  unsigned __int16 *v15; // rsi
  __int128 *v16; // r9
  void *RtmRegistrationHandle; // r12
  DWORD ChangedDests; // eax
  DWORD v19; // r14d
  __int128 *v20; // r9
  DWORD v21; // eax
  __int64 *v22; // rdx
  __int128 *v23; // r9
  DWORD v24; // eax
  __int128 *v25; // r9
  __int128 *v26; // r9
  int v27[2]; // [rsp+20h] [rbp-8A8h]
  struct _GUID *v28; // [rsp+28h] [rbp-8A0h]
  __int64 v29; // [rsp+30h] [rbp-898h]
  unsigned int NumDests; // [rsp+40h] [rbp-888h] BYREF
  SIZE_T dwBytes; // [rsp+44h] [rbp-884h] BYREF
  RTM_NOTIFY_HANDLE NotifyHandlea; // [rsp+50h] [rbp-878h]
  __int128 v33; // [rsp+58h] [rbp-870h] BYREF
  int v34; // [rsp+68h] [rbp-860h] BYREF
  __int128 v35; // [rsp+6Ch] [rbp-85Ch]
  __int128 v36; // [rsp+7Ch] [rbp-84Ch]
  int v37; // [rsp+8Ch] [rbp-83Ch]
  int v38; // [rsp+90h] [rbp-838h] BYREF
  _BYTE v39[2044]; // [rsp+94h] [rbp-834h] BYREF

  NotifyHandlea = NotifyHandle;
  NumDests = 0;
  dwBytes = 0;
  v5 = NotifyHandle;
  v38 = 0;
  memset_0(v39, 0, sizeof(v39));
  v34 = 0;
  v37 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v34) = 0;
    v6 = &v33;
    if ( a3 )
      LODWORD(v6) = (_DWORD)a3;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Enter: ProcessDefaultRouteChanges",
      (_DWORD)v6,
      0,
      (__int64)&v34);
  }
  v7 = RTMSIZEOFROUTEINFO(g_rtmProfile.MaxNextHopsInRoute, &dwBytes);
  if ( v7 )
  {
    if ( (v8 & 0x40) != 0 )
    {
      LOWORD(v34) = 0;
      v9 = &v33;
      if ( a3 )
        LODWORD(v9) = (_DWORD)a3;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrMgrParamTraceError,
        (unsigned int)L"ProcessDefaultRouteChanges : Arithmatic Overflow during memory allocation for route info",
        (_DWORD)v9,
        0,
        (__int64)&v34);
      v8 = Microsoft_Windows_RRASEnableBits;
    }
    if ( v8 >= 0 )
      return v7;
    LOWORD(v38) = 0;
    FormatRRASErrorString(&v38, L"Leaving: %ws", L"ProcessDefaultRouteChanges");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return v7;
    goto LABEL_12;
  }
  v11 = (struct _RTM_ROUTE_INFO *)HeapAlloc(IPRouterHeap, 0, (unsigned int)dwBytes);
  if ( !v11 )
  {
    v12 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v38) = 0;
      LOWORD(v34) = 0;
      FormatRRASErrorString(
        &v38,
        L"ProcessDefaultRouteChanges : error allocating %d bytes for route info",
        (unsigned int)dwBytes);
      v12 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v13 = &v33;
        if ( a3 )
          LODWORD(v13) = (_DWORD)a3;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v38,
          (_DWORD)v13,
          0,
          (__int64)&v34);
        v12 = Microsoft_Windows_RRASEnableBits;
      }
    }
    if ( v12 >= 0 )
      return 8;
    goto LABEL_37;
  }
  v7 = RTMSIZEOFDESTINFO(g_rtmProfile.NumberOfViews, (char *)&dwBytes + 4);
  if ( v7 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v34) = 0;
      v14 = &v33;
      if ( a3 )
        LODWORD(v14) = (_DWORD)a3;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrMgrParamTraceError,
        (unsigned int)L"ProcessDefaultRouteChanges : Arithmatic Overflow during memory allocation for dest. info",
        (_DWORD)v14,
        0,
        (__int64)&v34);
    }
    HeapFree(IPRouterHeap, 0, v11);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return v7;
    LOWORD(v38) = 0;
    FormatRRASErrorString(&v38, L"Leaving: %ws", L"ProcessDefaultRouteChanges");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return v7;
LABEL_12:
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v38);
    return v7;
  }
  v15 = (unsigned __int16 *)HeapAlloc(IPRouterHeap, 0, HIDWORD(dwBytes));
  if ( !v15 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v38) = 0;
      LOWORD(v34) = 0;
      FormatRRASErrorString(
        &v38,
        L"ProcessDefaultRouteChanges : error allocating %d bytes for dest. info",
        HIDWORD(dwBytes));
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v16 = &v33;
        if ( a3 )
          LODWORD(v16) = (_DWORD)a3;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v38,
          (_DWORD)v16,
          0,
          (__int64)&v34);
      }
    }
    HeapFree(IPRouterHeap, 0, v11);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return 8;
LABEL_37:
    LOWORD(v38) = 0;
    FormatRRASErrorString(&v38, L"Leaving: %ws", L"ProcessDefaultRouteChanges");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v38);
    return 8;
  }
  RtmRegistrationHandle = (void *)GetRtmRegistrationHandle(a3, a2 != 0 ? 33 : 87, 3u);
  while ( 1 )
  {
    NumDests = 1;
    ChangedDests = RtmGetChangedDests(RtmRegistrationHandle, v5, &NumDests, (PRTM_DEST_INFO)v15);
    v19 = ChangedDests;
    if ( ChangedDests )
    {
      if ( ChangedDests != 259 )
        break;
    }
    if ( !NumDests )
      goto LABEL_77;
    if ( v15[5] || *((_DWORD *)v15 + 3) )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        goto LABEL_66;
      LOWORD(v38) = 0;
      LOWORD(v34) = 0;
      LODWORD(v29) = v15[5];
      LODWORD(v28) = *((unsigned __int8 *)v15 + 15);
      v27[0] = *((unsigned __int8 *)v15 + 14);
      FormatRRASErrorString(
        &v38,
        L"ProcessDefaultRouteChanges: Not default route %d.%d.%d.%d/%d",
        *((unsigned __int8 *)v15 + 12),
        *((unsigned __int8 *)v15 + 13),
        *(_QWORD *)v27,
        v28,
        v29);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        goto LABEL_66;
      v22 = RasRtrmgrParamTraceInfo;
      goto LABEL_63;
    }
    if ( (v15[18] & 1) == 0 )
    {
      ChangeRouteWithForwarder((PRTM_NET_ADDRESS)(v15 + 4), a2, a3, 1);
      goto LABEL_66;
    }
    if ( *((void **)v15 + 8) == RtmRegistrationHandle )
    {
      AddNetmgmtDefaultRoutesToForwarder((__int64)v15, a2, a3);
      goto LABEL_66;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v38) = 0;
      LOWORD(v34) = 0;
      FormatRRASErrorString(
        &v38,
        L"ProcessDefaultRouteChanges: Adding non-NetMgmt route to forwarder, owner RTM handle 0x%x",
        *((_QWORD *)v15 + 8));
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v20 = &v33;
        if ( a3 )
          LODWORD(v20) = (_DWORD)a3;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v38,
          (_DWORD)v20,
          0,
          (__int64)&v34);
      }
    }
    if ( !RtmGetRouteInfo(RtmRegistrationHandle, *((RTM_ROUTE_HANDLE *)v15 + 7), v11, 0) )
    {
      ChangeRouteWithForwarder((PRTM_NET_ADDRESS)(v15 + 4), a2, a3, 1);
      v21 = RtmReleaseRouteInfo(RtmRegistrationHandle, v11);
      if ( v21 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          LOWORD(v38) = 0;
          LOWORD(v34) = 0;
          FormatRRASErrorString(&v38, L"ProcessDefaultRouteChanges: Failed to release route info", v21);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            v22 = RasRtrMgrParamTraceError;
LABEL_63:
            v23 = &v33;
            if ( a3 )
              LODWORD(v23) = (_DWORD)a3;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (_DWORD)v22,
              (unsigned int)&v38,
              (_DWORD)v23,
              0,
              (__int64)&v34);
          }
        }
      }
    }
LABEL_66:
    v5 = NotifyHandlea;
    v24 = RtmReleaseChangedDests(RtmRegistrationHandle, NotifyHandlea, NumDests, (PRTM_DEST_INFO)v15);
    if ( v24 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v38) = 0;
        LOWORD(v34) = 0;
        FormatRRASErrorString(&v38, L"ProcessDefaultRouteChanges: error %d releasing dests ", v24);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v25 = &v33;
          if ( a3 )
            LODWORD(v25) = (_DWORD)a3;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v38,
            (_DWORD)v25,
            0,
            (__int64)&v34);
        }
      }
    }
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
  {
    LOWORD(v38) = 0;
    LOWORD(v34) = 0;
    FormatRRASErrorString(&v38, L"ProcessDefaultRouteChanges: error %d retrieving changed dests", ChangedDests);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v26 = &v33;
      if ( a3 )
        LODWORD(v26) = (_DWORD)a3;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrMgrParamTraceError,
        (unsigned int)&v38,
        (_DWORD)v26,
        0,
        (__int64)&v34);
    }
  }
LABEL_77:
  HeapFree(IPRouterHeap, 0, v11);
  HeapFree(IPRouterHeap, 0, v15);
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v38) = 0;
    FormatRRASErrorString(&v38, L"Leaving: %ws", L"ProcessDefaultRouteChanges");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v38);
  }
  return v19;
}

```

## disassembly

```asm
0x18004c950  mov     [rsp+arg_18], rsi
0x18004c955  push    rdi
0x18004c956  push    r12
0x18004c958  push    r13
0x18004c95a  push    r14
0x18004c95c  push    r15
0x18004c95e  sub     rsp, 8A0h
0x18004c965  mov     rax, cs:__security_cookie
0x18004c96c  xor     rax, rsp
0x18004c96f  mov     [rsp+8C8h+var_38], rax
0x18004c977  xor     r12d, r12d
0x18004c97a  mov     [rsp+8C8h+NotifyHandle], rcx
0x18004c97f  mov     rdi, r8
0x18004c982  mov     [rsp+8C8h+NumDests], r12d
0x18004c987  mov     r13d, edx
0x18004c98a  mov     dword ptr [rsp+8C8h+dwBytes], r12d
0x18004c98f  mov     r14, rcx
0x18004c992  mov     dword ptr [rsp+8C8h+dwBytes+4], r12d
0x18004c997  xor     edx, edx; Val
0x18004c999  mov     [rsp+8C8h+var_838], r12d
0x18004c9a1  mov     r8d, 7FCh; Size
0x18004c9a7  lea     rcx, [rsp+8C8h+var_834]; void *
0x18004c9af  call    memset_0
0x18004c9b4  mov     r9, cs:Microsoft_Windows_RRASEnableBits
0x18004c9bb  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004c9c2  xorps   xmm0, xmm0
0x18004c9c5  mov     [rsp+8C8h+var_860], r12d
0x18004c9ca  xor     eax, eax
0x18004c9cc  mov     [rsp+8C8h+var_83C], eax
0x18004c9d3  movups  [rsp+8C8h+var_85C], xmm0
0x18004c9d8  movups  [rsp+8C8h+var_84C], xmm0
0x18004c9dd  movups  [rsp+8C8h+var_870], xmm0
0x18004c9e2  test    r9b, 80h
0x18004c9e6  jz      short loc_18004CA26
0x18004c9e8  test    rdi, rdi
0x18004c9eb  mov     word ptr [rsp+8C8h+var_860], r12w
0x18004c9f1  lea     rax, [rsp+8C8h+var_860]
0x18004c9f6  mov     rcx, r15
0x18004c9f9  mov     [rsp+8C8h+var_8A0], rax
0x18004c9fe  lea     r9, [rsp+8C8h+var_870]
0x18004ca03  cmovnz  r9, rdi
0x18004ca07  mov     qword ptr [rsp+8C8h+var_8A8], r12
0x18004ca0c  lea     r8, aEnterProcessde; "Enter: ProcessDefaultRouteChanges"
0x18004ca13  lea     rdx, RasRtrmgrParamTraceInfo
0x18004ca1a  call    McTemplateU0zjzz_EventWriteTransfer
0x18004ca1f  mov     r9, cs:Microsoft_Windows_RRASEnableBits
0x18004ca26  mov     ecx, cs:g_rtmProfile.MaxNextHopsInRoute
0x18004ca2c  lea     rdx, [rsp+8C8h+dwBytes]
0x18004ca31  call    RTMSIZEOFROUTEINFO
0x18004ca36  mov     esi, eax
0x18004ca38  test    eax, eax
0x18004ca3a  jz      loc_18004CAD4
0x18004ca40  test    r9b, 40h
0x18004ca44  jz      short loc_18004CA84
0x18004ca46  test    rdi, rdi
0x18004ca49  mov     word ptr [rsp+8C8h+var_860], r12w
0x18004ca4f  lea     rax, [rsp+8C8h+var_860]
0x18004ca54  mov     rcx, r15
0x18004ca57  mov     [rsp+8C8h+var_8A0], rax
0x18004ca5c  lea     r9, [rsp+8C8h+var_870]
0x18004ca61  cmovnz  r9, rdi
0x18004ca65  mov     qword ptr [rsp+8C8h+var_8A8], r12
0x18004ca6a  lea     r8, aProcessdefault_6; "ProcessDefaultRouteChanges : Arithmatic"...
0x18004ca71  lea     rdx, RasRtrMgrParamTraceError
0x18004ca78  call    McTemplateU0zjzz_EventWriteTransfer
0x18004ca7d  mov     r9, cs:Microsoft_Windows_RRASEnableBits
0x18004ca84  test    r9b, r9b
0x18004ca87  jns     short loc_18004CACD
0x18004ca89  lea     r8, aProcessdefault_5; "ProcessDefaultRouteChanges"
0x18004ca90  mov     word ptr [rsp+8C8h+var_838], r12w
0x18004ca99  lea     rdx, aLeavingWs; "Leaving: %ws"
0x18004caa0  lea     rcx, [rsp+8C8h+var_838]
0x18004caa8  call    FormatRRASErrorString
0x18004caad  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18004cab4  jge     short loc_18004CACD
0x18004cab6  mov     rcx, r15
0x18004cab9  lea     rdx, RasRtrmgrTraceInfo
0x18004cac0  lea     r8, [rsp+8C8h+var_838]
0x18004cac8  call    McTemplateU0z_EventWriteTransfer
0x18004cacd  mov     eax, esi
0x18004cacf  jmp     loc_18004D115
0x18004cad4  mov     r8d, dword ptr [rsp+8C8h+dwBytes]; dwBytes
0x18004cad9  xor     edx, edx; dwFlags
0x18004cadb  mov     rcx, cs:IPRouterHeap; hHeap
0x18004cae2  call    cs:__imp_HeapAlloc
0x18004cae8  mov     r15, rax
0x18004caeb  test    rax, rax
0x18004caee  jnz     loc_18004CB7C
0x18004caf4  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18004cafb  test    al, 40h
0x18004cafd  jz      short loc_18004CB6F
0x18004caff  mov     r8d, dword ptr [rsp+8C8h+dwBytes]
0x18004cb04  lea     rdx, aProcessdefault_0; "ProcessDefaultRouteChanges : error allo"...
0x18004cb0b  lea     rcx, [rsp+8C8h+var_838]
0x18004cb13  mov     word ptr [rsp+8C8h+var_838], r12w
0x18004cb1c  mov     word ptr [rsp+8C8h+var_860], r12w
0x18004cb22  call    FormatRRASErrorString
0x18004cb27  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18004cb2e  test    al, 40h
0x18004cb30  jz      short loc_18004CB6F
0x18004cb32  test    rdi, rdi
0x18004cb35  lea     rax, [rsp+8C8h+var_860]
0x18004cb3a  mov     [rsp+8C8h+var_8A0], rax
0x18004cb3f  lea     r9, [rsp+8C8h+var_870]
0x18004cb44  cmovnz  r9, rdi
0x18004cb48  mov     qword ptr [rsp+8C8h+var_8A8], r12
0x18004cb4d  lea     r8, [rsp+8C8h+var_838]
0x18004cb55  lea     rdx, RasRtrMgrParamTraceError
0x18004cb5c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004cb63  call    McTemplateU0zjzz_EventWriteTransfer
0x18004cb68  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18004cb6f  test    al, al
0x18004cb71  jns     loc_18004CD29
0x18004cb77  jmp     loc_18004CCE1
0x18004cb7c  mov     ecx, cs:g_rtmProfile.NumberOfViews
0x18004cb82  lea     rdx, [rsp+8C8h+dwBytes+4]
0x18004cb87  call    RTMSIZEOFDESTINFO
0x18004cb8c  mov     esi, eax
0x18004cb8e  test    eax, eax
0x18004cb90  jz      loc_18004CC36
0x18004cb96  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004cb9d  jz      short loc_18004CBDA
0x18004cb9f  test    rdi, rdi
0x18004cba2  mov     word ptr [rsp+8C8h+var_860], r12w
0x18004cba8  lea     rax, [rsp+8C8h+var_860]
0x18004cbad  mov     [rsp+8C8h+var_8A0], rax
0x18004cbb2  lea     r9, [rsp+8C8h+var_870]
0x18004cbb7  cmovnz  r9, rdi
0x18004cbbb  mov     qword ptr [rsp+8C8h+var_8A8], r12
0x18004cbc0  lea     r8, aProcessdefault_4; "ProcessDefaultRouteChanges : Arithmatic"...
0x18004cbc7  lea     rdx, RasRtrMgrParamTraceError
0x18004cbce  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004cbd5  call    McTemplateU0zjzz_EventWriteTransfer
0x18004cbda  mov     rcx, cs:IPRouterHeap; hHeap
0x18004cbe1  mov     r8, r15; lpMem
0x18004cbe4  xor     edx, edx; dwFlags
0x18004cbe6  call    cs:__imp_HeapFree
0x18004cbec  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18004cbf3  jge     loc_18004CACD
0x18004cbf9  lea     r8, aProcessdefault_5; "ProcessDefaultRouteChanges"
0x18004cc00  mov     word ptr [rsp+8C8h+var_838], r12w
0x18004cc09  lea     rdx, aLeavingWs; "Leaving: %ws"
0x18004cc10  lea     rcx, [rsp+8C8h+var_838]
0x18004cc18  call    FormatRRASErrorString
0x18004cc1d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18004cc24  jge     loc_18004CACD
0x18004cc2a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004cc31  jmp     loc_18004CAB9
0x18004cc36  mov     r8d, dword ptr [rsp+8C8h+dwBytes+4]; dwBytes
0x18004cc3b  xor     edx, edx; dwFlags
0x18004cc3d  mov     rcx, cs:IPRouterHeap; hHeap
0x18004cc44  call    cs:__imp_HeapAlloc
0x18004cc4a  mov     rsi, rax
0x18004cc4d  test    rax, rax
0x18004cc50  jnz     loc_18004CD33
0x18004cc56  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004cc5d  jz      short loc_18004CCC6
0x18004cc5f  mov     r8d, dword ptr [rsp+8C8h+dwBytes+4]
0x18004cc64  lea     rdx, aProcessdefault_2; "ProcessDefaultRouteChanges : error allo"...
0x18004cc6b  lea     rcx, [rsp+8C8h+var_838]
0x18004cc73  mov     word ptr [rsp+8C8h+var_838], r12w
0x18004cc7c  mov     word ptr [rsp+8C8h+var_860], r12w
0x18004cc82  call    FormatRRASErrorString
0x18004cc87  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004cc8e  jz      short loc_18004CCC6
0x18004cc90  test    rdi, rdi
0x18004cc93  lea     rax, [rsp+8C8h+var_860]
0x18004cc98  mov     [rsp+8C8h+var_8A0], rax
0x18004cc9d  lea     r9, [rsp+8C8h+var_870]
0x18004cca2  cmovnz  r9, rdi
0x18004cca6  mov     qword ptr [rsp+8C8h+var_8A8], r12
0x18004ccab  lea     r8, [rsp+8C8h+var_838]
0x18004ccb3  lea     rdx, RasRtrMgrParamTraceError
0x18004ccba  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004ccc1  call    McTemplateU0zjzz_EventWriteTransfer
0x18004ccc6  mov     rcx, cs:IPRouterHeap; hHeap
0x18004cccd  mov     r8, r15; lpMem
0x18004ccd0  xor     edx, edx; dwFlags
0x18004ccd2  call    cs:__imp_HeapFree
0x18004ccd8  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18004ccdf  jge     short loc_18004CD29
0x18004cce1  lea     r8, aProcessdefault_5; "ProcessDefaultRouteChanges"
0x18004cce8  mov     word ptr [rsp+8C8h+var_838], r12w
0x18004ccf1  lea     rdx, aLeavingWs; "Leaving: %ws"
0x18004ccf8  lea     rcx, [rsp+8C8h+var_838]
0x18004cd00  call    FormatRRASErrorString
0x18004cd05  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18004cd0c  jge     short loc_18004CD29
0x18004cd0e  lea     r8, [rsp+8C8h+var_838]
0x18004cd16  lea     rdx, RasRtrmgrTraceInfo
0x18004cd1d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004cd24  call    McTemplateU0z_EventWriteTransfer
0x18004cd29  mov     eax, 8
0x18004cd2e  jmp     loc_18004D115
0x18004cd33  mov     eax, r13d
0x18004cd36  mov     r8d, 3; unsigned int
0x18004cd3c  neg     eax
0x18004cd3e  mov     rcx, rdi; struct _GUID *
0x18004cd41  sbb     edx, edx
0x18004cd43  and     edx, 0FFFFFFCAh
0x18004cd46  add     edx, 57h ; 'W'; unsigned int
0x18004cd49  call    GetRtmRegistrationHandle
0x18004cd4e  mov     r12, rax
0x18004cd51  mov     r9, rsi; ChangedDests
0x18004cd54  mov     [rsp+8C8h+NumDests], 1
0x18004cd5c  lea     r8, [rsp+8C8h+NumDests]; NumDests
0x18004cd61  mov     rdx, r14; NotifyHandle
0x18004cd64  mov     rcx, r12; RtmRegHandle
0x18004cd67  call    cs:__imp_RtmGetChangedDests
0x18004cd6d  mov     r14d, eax
0x18004cd70  test    eax, eax
0x18004cd72  jz      short loc_18004CD7F
0x18004cd74  cmp     eax, 103h
0x18004cd79  jnz     loc_18004D027
0x18004cd7f  mov     eax, 1
0x18004cd84  cmp     [rsp+8C8h+NumDests], eax
0x18004cd88  jb      loc_18004D09A
0x18004cd8e  xor     r14d, r14d
0x18004cd91  cmp     [rsi+0Ah], r14w
0x18004cd96  jnz     loc_18004CEF8
0x18004cd9c  cmp     [rsi+0Ch], r14d
0x18004cda0  jnz     loc_18004CEF8
0x18004cda6  test    [rsi+24h], al
0x18004cda9  jnz     short loc_18004CDCF
0x18004cdab  mov     [rsp+8C8h+var_898], eax; int
0x18004cdaf  lea     rcx, [rsi+8]; pNetAddress
0x18004cdb3  mov     [rsp+8C8h+var_8A0], rdi; struct _GUID *
0x18004cdb8  mov     r9d, eax
0x18004cdbb  xor     r8d, r8d
0x18004cdbe  mov     [rsp+8C8h+var_8A8], r13d; int
0x18004cdc3  xor     edx, edx
0x18004cdc5  call    ChangeRouteWithForwarder
0x18004cdca  jmp     loc_18004CF89
0x18004cdcf  cmp     [rsi+40h], r12
0x18004cdd3  jz      loc_18004CEE5
0x18004cdd9  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18004cde0  jge     short loc_18004CE48
0x18004cde2  mov     word ptr [rsp+8C8h+var_838], r14w
0x18004cdeb  lea     rdx, aProcessdefault_10; "ProcessDefaultRouteChanges: Adding non-"...
0x18004cdf2  mov     word ptr [rsp+8C8h+var_860], r14w
0x18004cdf8  lea     rcx, [rsp+8C8h+var_838]
0x18004ce00  mov     r8, [rsi+40h]
0x18004ce04  call    FormatRRASErrorString
0x18004ce09  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18004ce10  jge     short loc_18004CE48
0x18004ce12  test    rdi, rdi
0x18004ce15  lea     rax, [rsp+8C8h+var_860]
0x18004ce1a  mov     [rsp+8C8h+var_8A0], rax
0x18004ce1f  lea     r9, [rsp+8C8h+var_870]
0x18004ce24  cmovnz  r9, rdi
0x18004ce28  mov     qword ptr [rsp+8C8h+var_8A8], r14
0x18004ce2d  lea     r8, [rsp+8C8h+var_838]
0x18004ce35  lea     rdx, RasRtrmgrParamTraceInfo
0x18004ce3c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004ce43  call    McTemplateU0zjzz_EventWriteTransfer
0x18004ce48  mov     rdx, [rsi+38h]; RouteHandle
0x18004ce4c  xor     r9d, r9d; DestAddress
0x18004ce4f  mov     r8, r15; RouteInfo
0x18004ce52  mov     rcx, r12; RtmRegHandle
0x18004ce55  call    cs:__imp_RtmGetRouteInfo
0x18004ce5b  test    eax, eax
0x18004ce5d  jnz     loc_18004CF89
0x18004ce63  mov     eax, 1
0x18004ce68  lea     rcx, [rsi+8]; pNetAddress
0x18004ce6c  mov     [rsp+8C8h+var_898], eax; int
0x18004ce70  mov     r9d, eax
0x18004ce73  mov     [rsp+8C8h+var_8A0], rdi; struct _GUID *
0x18004ce78  mov     r8d, eax
0x18004ce7b  mov     rdx, r15
0x18004ce7e  mov     [rsp+8C8h+var_8A8], r13d; int
0x18004ce83  call    ChangeRouteWithForwarder
0x18004ce88  mov     rdx, r15; RouteInfo
0x18004ce8b  mov     rcx, r12; RtmRegHandle
0x18004ce8e  call    cs:__imp_RtmReleaseRouteInfo
0x18004ce94  test    eax, eax
0x18004ce96  jz      loc_18004CF89
0x18004ce9c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004cea3  jz      loc_18004CF89
0x18004cea9  mov     r8d, eax
0x18004ceac  mov     word ptr [rsp+8C8h+var_838], r14w
0x18004ceb5  lea     rdx, aProcessdefault_1; "ProcessDefaultRouteChanges: Failed to r"...
0x18004cebc  mov     word ptr [rsp+8C8h+var_860], r14w
0x18004cec2  lea     rcx, [rsp+8C8h+var_838]
0x18004ceca  call    FormatRRASErrorString
0x18004cecf  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004ced6  jz      loc_18004CF89
0x18004cedc  lea     rdx, RasRtrMgrParamTraceError
0x18004cee3  jmp     short loc_18004CF5A
0x18004cee5  mov     r8, rdi
0x18004cee8  mov     edx, r13d
0x18004ceeb  mov     rcx, rsi
0x18004ceee  call    AddNetmgmtDefaultRoutesToForwarder
0x18004cef3  jmp     loc_18004CF89
0x18004cef8  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18004ceff  jge     loc_18004CF89
0x18004cf05  mov     word ptr [rsp+8C8h+var_838], r14w
0x18004cf0e  mov     word ptr [rsp+8C8h+var_860], r14w
0x18004cf14  movzx   ecx, byte ptr [rsi+0Fh]
0x18004cf18  movzx   edx, byte ptr [rsi+0Eh]
0x18004cf1c  movzx   eax, word ptr [rsi+0Ah]
  ... truncated ...
```

# OnRouteChange

- ea: `0x180042620`
- end: `0x180042ca5`
- name: `OnRouteChange`
- size: `1669`
- prototype: `void __stdcall(PVOID CallerContext, PMIB_IPFORWARD_ROW2 Row, MIB_NOTIFICATION_TYPE NotificationType)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001f90`
- `0x180011790`
- `0x18004126c`
- `0x180042620`
- `0x180042cac`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180058600`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18004292a`
- `msvcrt!memcpy_s` at `0x18004292a`
- `IPHLPAPI!GetNetworkInformation` at `0x180042843`
- `IPHLPAPI!GetNetworkInformation` at `0x180042843`
- `IPHLPAPI!GetIfEntry2` at `0x18004275b`
- `IPHLPAPI!GetIfEntry2` at `0x18004275b`
- `IPHLPAPI!GetIpForwardEntry2` at `0x180042976`
- `IPHLPAPI!GetIpForwardEntry2` at `0x180042976`
- `IPHLPAPI!GetCurrentThreadCompartmentScope` at `0x18004271f`
- `IPHLPAPI!GetCurrentThreadCompartmentScope` at `0x18004271f`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18004293d`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18004293d`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18004294b`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180042c7c`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18004294b`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180042c7c`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x180042728`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x1800427d1`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x1800427f8`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x180042728`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x1800427d1`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x1800427f8`

## string_xrefs

- `0x180042747`: `ERROR:OnRouteChange: SetCurrentThreadCompartmentScope failed with error %d`
- `0x18004280c`: `ERROR:OnRouteChange: SetCurrentThreadCompartmentScope failed with error %d`
- `0x180042963`: `ERROR:OnRouteChange: SetCurrentCompartmentId failed with error %d`
- `0x180042b7c`: `OnRouteChange: Route Addition/Update Notification`
- `0x1800427eb`: `ERROR:OnRouteChange: SetCurrentThreadCompartmentScope 2 failed with error %d`

## pseudocode

```c
void __fastcall OnRouteChange(PVOID CallerContext, PMIB_IPFORWARD_ROW2 Row, MIB_NOTIFICATION_TYPE NotificationType)
{
  NET_IFINDEX InterfaceIndex; // r14d
  NTSTATUS NetworkInformation; // eax
  const wchar_t *v7; // rdx
  unsigned int IfEntry2; // eax
  const wchar_t *v9; // rdx
  int v10; // r14d
  unsigned int IpForwardEntry2; // eax
  const wchar_t *v12; // r8
  __int64 *v13; // rdx
  unsigned int v14; // eax
  ULONG Length[2]; // [rsp+20h] [rbp-E0h]
  ULONG Lengtha[2]; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+28h] [rbp-D8h]
  __int64 v18; // [rsp+28h] [rbp-D8h]
  __int64 v19; // [rsp+30h] [rbp-D0h]
  UINT32 CompartmentScope; // [rsp+50h] [rbp-B0h] BYREF
  UINT32 v21; // [rsp+54h] [rbp-ACh] BYREF
  UINT32 CompartmentId; // [rsp+58h] [rbp-A8h] BYREF
  ULONG SiteId; // [rsp+60h] [rbp-A0h] BYREF
  GUID v24; // [rsp+68h] [rbp-98h] BYREF
  NET_IF_NETWORK_GUID NetworkGuid; // [rsp+78h] [rbp-88h] BYREF
  struct _MIB_IPFORWARD_ROW2 Destination; // [rsp+90h] [rbp-70h] BYREF
  __int128 v27; // [rsp+100h] [rbp+0h]
  _MIB_IF_ROW2 Rowa; // [rsp+110h] [rbp+10h] BYREF
  int v29; // [rsp+660h] [rbp+560h] BYREF
  __int128 v30; // [rsp+664h] [rbp+564h]
  __int128 v31; // [rsp+674h] [rbp+574h]
  int v32; // [rsp+684h] [rbp+584h]
  int v33; // [rsp+690h] [rbp+590h] BYREF
  _BYTE v34[2044]; // [rsp+694h] [rbp+594h] BYREF
  WCHAR NetworkName; // [rsp+E90h] [rbp+D90h] BYREF
  _BYTE v36[526]; // [rsp+E92h] [rbp+D92h] BYREF

  memset_0(&Destination, 0, sizeof(Destination));
  v21 = 1;
  CompartmentId = 1;
  SiteId = 0;
  NetworkName = 12080;
  v24 = GUID_NULL;
  memset_0(v36, 0, 0x200u);
  memset_0(&Rowa, 0, sizeof(Rowa));
  CompartmentScope = 0;
  v33 = 0;
  memset_0(v34, 0, sizeof(v34));
  v29 = 0;
  v32 = 0;
  v30 = 0;
  v31 = 0;
  v27 = 0;
  if ( !Row || NotificationType == MibInitialNotification )
    return;
  InterfaceIndex = Row->InterfaceIndex;
  GetCurrentThreadCompartmentScope(&CompartmentScope, &CompartmentId);
  NetworkInformation = SetCurrentThreadCompartmentScope(0xFFFFFFFF);
  if ( NetworkInformation )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
      return;
    v7 = L"ERROR:OnRouteChange: SetCurrentThreadCompartmentScope failed with error %d";
    goto LABEL_20;
  }
  Rowa.InterfaceIndex = InterfaceIndex;
  IfEntry2 = GetIfEntry2(&Rowa);
  if ( !IfEntry2 )
  {
    IfEntry2 = SetCurrentThreadCompartmentScope(CompartmentScope);
    if ( IfEntry2 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        goto LABEL_11;
      v9 = L"ERROR:OnRouteChange: SetCurrentThreadCompartmentScope failed with error %d";
      goto LABEL_9;
    }
    NetworkGuid = Rowa.NetworkGuid;
    NetworkInformation = GetNetworkInformation(&NetworkGuid, &v21, &SiteId, &NetworkName, 0x101u);
    if ( NetworkInformation )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        return;
      v7 = L"ERROR:OnRouteChange: GetNetworkInformation failed with error %d";
      goto LABEL_20;
    }
    if ( v21 != 1 && (unsigned int)NsiGetRoutingDomainIdForCompartment(v21, &v24) )
      return;
    v10 = 0;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v29) = 0;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)L"Entered: OnRouteChange",
        (unsigned int)&v24,
        0,
        (__int64)&v29);
    }
    memcpy_s(&Destination, 0x68u, Row, 0x68u);
    if ( NotificationType != MibDeleteInstance )
    {
      CompartmentId = GetCurrentThreadCompartmentId();
      NetworkInformation = SetCurrentThreadCompartmentId(v21);
      if ( NetworkInformation < 0 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
          return;
        v7 = L"ERROR:OnRouteChange: SetCurrentCompartmentId failed with error %d";
        goto LABEL_20;
      }
      v10 = 1;
      IpForwardEntry2 = GetIpForwardEntry2(&Destination);
      if ( IpForwardEntry2 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          LOWORD(v33) = 0;
          LOWORD(v29) = 0;
          FormatRRASErrorString(&v33, L"OnRouteChange: GetIpForwardEntry2 failed with error %d", IpForwardEntry2);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrMgrParamTraceError,
              (unsigned int)&v33,
              (unsigned int)&v24,
              0,
              (__int64)&v29);
        }
LABEL_57:
        SetCurrentThreadCompartmentId(CompartmentId);
        return;
      }
    }
    if ( Row->DestinationPrefix.Prefix.Ipv4.sin_family == 2 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LODWORD(v17) = HIBYTE(Destination.DestinationPrefix.Prefix.Ipv4.sin_addr.S_un.S_addr);
        Length[0] = Destination.DestinationPrefix.Prefix.Ipv4.sin_addr.S_un.S_un_b.s_b3;
        LOWORD(v33) = 0;
        LOWORD(v29) = 0;
        FormatRRASErrorString(
          &v33,
          L"OnRouteChange: Change for route to %d.%d.%d.%d/%d",
          Destination.DestinationPrefix.Prefix.Ipv4.sin_addr.S_un.S_un_b.s_b1,
          Destination.DestinationPrefix.Prefix.Ipv4.sin_addr.S_un.S_un_b.s_b2,
          *(_QWORD *)Length,
          v17,
          Destination.DestinationPrefix.PrefixLength,
          0,
          0,
          0);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v33,
            (unsigned int)&v24,
            0,
            (__int64)&v29);
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            LODWORD(v19) = HIBYTE(Destination.NextHop.Ipv4.sin_addr.S_un.S_addr);
            LODWORD(v18) = Destination.NextHop.Ipv4.sin_addr.S_un.S_un_b.s_b3;
            Lengtha[0] = Destination.NextHop.Ipv4.sin_addr.S_un.S_un_b.s_b2;
            LOWORD(v33) = 0;
            LOWORD(v29) = 0;
            FormatRRASErrorString(
              &v33,
              L"OnRouteChange: Route via i/f Luid %lx, nexthop %d.%d.%d.%d",
              Destination.InterfaceLuid.Value,
              Destination.NextHop.Ipv4.sin_addr.S_un.S_un_b.s_b1,
              *(_QWORD *)Lengtha,
              v18,
              v19);
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasRtrmgrParamTraceInfo,
                (unsigned int)&v33,
                (unsigned int)&v24,
                0,
                (__int64)&v29);
          }
        }
      }
    }
    else
    {
      PrintIpv6Route("OnRouteChange:", &v24, &Destination);
    }
    if ( NotificationType == MibDeleteInstance )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        goto LABEL_47;
      v12 = L"OnRouteChange: Route Deletion Notification";
    }
    else
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        goto LABEL_47;
      v12 = L"OnRouteChange: Route Addition/Update Notification";
    }
    LOWORD(v29) = 0;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (_DWORD)v12,
      (unsigned int)&v24,
      0,
      (__int64)&v29);
LABEL_47:
    if ( Destination.Protocol <= RouteProtocolIcmp )
    {
      v14 = HandleRouteChangeNotification(&Destination.InterfaceLuid);
      if ( v14 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          LOWORD(v33) = 0;
          LOWORD(v29) = 0;
          FormatRRASErrorString(&v33, L"ERROR: OnRouteChange::HandleRouteChangeNotification failed with error %d", v14);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            v13 = RasRtrMgrParamTraceError;
            goto LABEL_55;
          }
        }
      }
    }
    else if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v33) = 0;
      LOWORD(v29) = 0;
      FormatRRASErrorString(
        &v33,
        L"OnRouteChange: route is owned by RRAS and route change notification is ignored. Route type is %d");
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v13 = RasRtrmgrParamTraceInfo;
LABEL_55:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (_DWORD)v13,
          (unsigned int)&v33,
          (unsigned int)&v24,
          0,
          (__int64)&v29);
      }
    }
    if ( !v10 )
      return;
    goto LABEL_57;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
    goto LABEL_11;
  v9 = L"ERROR:OnRouteChange: GetIfEntry2 failed with error %d";
LABEL_9:
  LOWORD(v33) = 0;
  LOWORD(v29) = 0;
  FormatRRASErrorString(&v33, v9, IfEntry2);
  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrMgrParamTraceError,
      (unsigned int)&v33,
      (unsigned int)&v24,
      0,
      (__int64)&v29);
LABEL_11:
  NetworkInformation = SetCurrentThreadCompartmentScope(CompartmentScope);
  if ( NetworkInformation && (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
  {
    v7 = L"ERROR:OnRouteChange: SetCurrentThreadCompartmentScope 2 failed with error %d";
LABEL_20:
    LOWORD(v29) = 0;
    LOWORD(v33) = 0;
    FormatRRASErrorString(&v33, v7, (unsigned int)NetworkInformation);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrMgrParamTraceError,
        (unsigned int)&v33,
        (unsigned int)&v24,
        0,
        (__int64)&v29);
  }
}

```

## disassembly

```asm
0x180042620  push    rbp
0x180042622  push    rbx
0x180042623  push    rsi
0x180042624  push    rdi
0x180042625  push    r12
0x180042627  push    r13
0x180042629  push    r14
0x18004262b  push    r15
0x18004262d  lea     rbp, [rsp-0FB8h]
0x180042635  mov     eax, 10B8h
0x18004263a  call    _alloca_probe
0x18004263f  sub     rsp, rax
0x180042642  mov     rax, cs:__security_cookie
0x180042649  xor     rax, rsp
0x18004264c  mov     [rbp+0FF0h+var_50], rax
0x180042653  mov     rdi, rdx
0x180042656  lea     rcx, [rbp+0FF0h+Destination]; void *
0x18004265a  xor     edx, edx; Val
0x18004265c  mov     esi, r8d
0x18004265f  lea     r8d, [rdx+68h]; Size
0x180042663  call    memset_0
0x180042668  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004266f  mov     ebx, 1
0x180042674  lea     rcx, [rbp+0FF0h+var_25E]; void *
0x18004267b  mov     eax, 2F30h
0x180042680  mov     [rsp+10F0h+var_109C], ebx
0x180042684  xor     r15d, r15d
0x180042687  mov     [rsp+10F0h+CompartmentId], ebx
0x18004268b  xor     edx, edx; Val
0x18004268d  mov     [rsp+10F0h+SiteId], r15d
0x180042692  mov     r8d, 200h; Size
0x180042698  mov     [rbp+0FF0h+NetworkName], ax
0x18004269f  movdqu  [rsp+10F0h+var_1088], xmm0
0x1800426a5  call    memset_0
0x1800426aa  xor     edx, edx; Val
0x1800426ac  lea     rcx, [rbp+0FF0h+Row]; void *
0x1800426b0  mov     r8d, 548h; Size
0x1800426b6  call    memset_0
0x1800426bb  xor     edx, edx; Val
0x1800426bd  mov     [rsp+10F0h+CompartmentScope], r15d
0x1800426c2  mov     r8d, 7FCh; Size
0x1800426c8  mov     [rbp+0FF0h+var_A60], r15d
0x1800426cf  lea     rcx, [rbp+0FF0h+var_A5C]; void *
0x1800426d6  call    memset_0
0x1800426db  xorps   xmm0, xmm0
0x1800426de  mov     [rbp+0FF0h+var_A90], r15d
0x1800426e5  xor     eax, eax
0x1800426e7  mov     [rbp+0FF0h+var_A6C], eax
0x1800426ed  movups  [rbp+0FF0h+var_A8C], xmm0
0x1800426f4  movups  [rbp+0FF0h+var_A7C], xmm0
0x1800426fb  movups  [rbp+0FF0h+var_FF0], xmm0
0x1800426ff  test    rdi, rdi
0x180042702  jz      loc_180042C82
0x180042708  cmp     esi, 3
0x18004270b  jz      loc_180042C82
0x180042711  mov     r14d, [rdi+8]
0x180042715  lea     rdx, [rsp+10F0h+CompartmentId]; CompartmentId
0x18004271a  lea     rcx, [rsp+10F0h+CompartmentScope]; CompartmentScope
0x18004271f  call    cs:__imp_GetCurrentThreadCompartmentScope
0x180042725  or      ecx, 0FFFFFFFFh; CompartmentScope
0x180042728  call    cs:__imp_SetCurrentThreadCompartmentScope
0x18004272e  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180042735  test    eax, eax
0x180042737  jz      short loc_180042753
0x180042739  mov     bl, 40h ; '@'
0x18004273b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180042741  jz      loc_180042C82
0x180042747  lea     rdx, aErrorOnroutech_2; "ERROR:OnRouteChange: SetCurrentThreadCo"...
0x18004274e  jmp     loc_180042862
0x180042753  lea     rcx, [rbp+0FF0h+Row]; Row
0x180042757  mov     [rbp+0FF0h+Row.InterfaceIndex], r14d
0x18004275b  call    cs:__imp_GetIfEntry2
0x180042761  test    eax, eax
0x180042763  jz      loc_1800427F4
0x180042769  mov     bl, 40h ; '@'
0x18004276b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180042771  jz      short loc_1800427CD
0x180042773  lea     rdx, aErrorOnroutech_3; "ERROR:OnRouteChange: GetIfEntry2 failed"...
0x18004277a  mov     r8d, eax
0x18004277d  mov     word ptr [rbp+0FF0h+var_A60], r15w
0x180042785  lea     rcx, [rbp+0FF0h+var_A60]
0x18004278c  mov     word ptr [rbp+0FF0h+var_A90], r15w
0x180042794  call    FormatRRASErrorString
0x180042799  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18004279f  jz      short loc_1800427CD
0x1800427a1  lea     rax, [rbp+0FF0h+var_A90]
0x1800427a8  mov     rcx, r12
0x1800427ab  mov     [rsp+10F0h+var_10C8], rax
0x1800427b0  lea     r9, [rsp+10F0h+var_1088]
0x1800427b5  lea     r8, [rbp+0FF0h+var_A60]
0x1800427bc  mov     qword ptr [rsp+10F0h+Length], r15
0x1800427c1  lea     rdx, RasRtrMgrParamTraceError
0x1800427c8  call    McTemplateU0zjzz_EventWriteTransfer
0x1800427cd  mov     ecx, [rsp+10F0h+CompartmentScope]; CompartmentScope
0x1800427d1  call    cs:__imp_SetCurrentThreadCompartmentScope
0x1800427d7  test    eax, eax
0x1800427d9  jz      loc_180042C82
0x1800427df  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x1800427e5  jz      loc_180042C82
0x1800427eb  lea     rdx, aErrorOnroutech_1; "ERROR:OnRouteChange: SetCurrentThreadCo"...
0x1800427f2  jmp     short loc_180042862
0x1800427f4  mov     ecx, [rsp+10F0h+CompartmentScope]; CompartmentScope
0x1800427f8  call    cs:__imp_SetCurrentThreadCompartmentScope
0x1800427fe  test    eax, eax
0x180042800  jz      short loc_180042818
0x180042802  mov     bl, 40h ; '@'
0x180042804  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18004280a  jz      short loc_1800427CD
0x18004280c  lea     rdx, aErrorOnroutech_2; "ERROR:OnRouteChange: SetCurrentThreadCo"...
0x180042813  jmp     loc_18004277A
0x180042818  movaps  xmm0, xmmword ptr [rbp+0FF0h+Row.NetworkGuid.Data1]
0x18004281f  lea     r9, [rbp+0FF0h+NetworkName]; NetworkName
0x180042826  lea     r8, [rsp+10F0h+SiteId]; SiteId
0x18004282b  mov     [rsp+10F0h+Length], 101h; Length
0x180042833  lea     rdx, [rsp+10F0h+var_109C]; CompartmentId
0x180042838  lea     rcx, [rsp+10F0h+NetworkGuid]; NetworkGuid
0x18004283d  movdqu  xmmword ptr [rsp+10F0h+NetworkGuid.Data1], xmm0
0x180042843  call    cs:__imp_GetNetworkInformation
0x180042849  test    eax, eax
0x18004284b  jz      short loc_1800428BE
0x18004284d  mov     bl, 40h ; '@'
0x18004284f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180042855  jz      loc_180042C82
0x18004285b  lea     rdx, aErrorOnroutech; "ERROR:OnRouteChange: GetNetworkInformat"...
0x180042862  mov     r8d, eax
0x180042865  mov     word ptr [rbp+0FF0h+var_A90], r15w
0x18004286d  lea     rcx, [rbp+0FF0h+var_A60]
0x180042874  mov     word ptr [rbp+0FF0h+var_A60], r15w
0x18004287c  call    FormatRRASErrorString
0x180042881  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180042887  jz      loc_180042C82
0x18004288d  lea     rax, [rbp+0FF0h+var_A90]
0x180042894  mov     rcx, r12
0x180042897  mov     [rsp+10F0h+var_10C8], rax
0x18004289c  lea     r9, [rsp+10F0h+var_1088]
0x1800428a1  lea     r8, [rbp+0FF0h+var_A60]
0x1800428a8  mov     qword ptr [rsp+10F0h+Length], r15
0x1800428ad  lea     rdx, RasRtrMgrParamTraceError
0x1800428b4  call    McTemplateU0zjzz_EventWriteTransfer
0x1800428b9  jmp     loc_180042C82
0x1800428be  mov     ecx, [rsp+10F0h+var_109C]
0x1800428c2  cmp     ecx, ebx
0x1800428c4  jz      short loc_1800428D8
0x1800428c6  lea     rdx, [rsp+10F0h+var_1088]
0x1800428cb  call    NsiGetRoutingDomainIdForCompartment
0x1800428d0  test    eax, eax
0x1800428d2  jnz     loc_180042C82
0x1800428d8  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800428df  lea     r13, RasRtrmgrParamTraceInfo
0x1800428e6  mov     r14d, r15d
0x1800428e9  jz      short loc_18004291B
0x1800428eb  lea     rax, [rbp+0FF0h+var_A90]
0x1800428f2  mov     word ptr [rbp+0FF0h+var_A90], r15w
0x1800428fa  mov     [rsp+10F0h+var_10C8], rax
0x1800428ff  lea     r9, [rsp+10F0h+var_1088]
0x180042904  lea     r8, aEnteredOnroute; "Entered: OnRouteChange"
0x18004290b  mov     qword ptr [rsp+10F0h+Length], r15
0x180042910  mov     rdx, r13
0x180042913  mov     rcx, r12
0x180042916  call    McTemplateU0zjzz_EventWriteTransfer
0x18004291b  mov     edx, 68h ; 'h'; DestinationSize
0x180042920  lea     rcx, [rbp+0FF0h+Destination]; Destination
0x180042924  mov     r9d, edx; SourceSize
0x180042927  mov     r8, rdi; Source
0x18004292a  call    cs:__imp_memcpy_s
0x180042930  mov     eax, 2
0x180042935  cmp     esi, eax
0x180042937  jz      loc_1800429F6
0x18004293d  call    cs:__imp_GetCurrentThreadCompartmentId
0x180042943  mov     ecx, [rsp+10F0h+var_109C]; CompartmentId
0x180042947  mov     [rsp+10F0h+CompartmentId], eax
0x18004294b  call    cs:__imp_SetCurrentThreadCompartmentId
0x180042951  test    eax, eax
0x180042953  jns     short loc_18004296F
0x180042955  mov     bl, 40h ; '@'
0x180042957  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18004295d  jz      loc_180042C82
0x180042963  lea     rdx, aErrorOnroutech_4; "ERROR:OnRouteChange: SetCurrentCompartm"...
0x18004296a  jmp     loc_180042862
0x18004296f  lea     rcx, [rbp+0FF0h+Destination]; Row
0x180042973  mov     r14d, ebx
0x180042976  call    cs:__imp_GetIpForwardEntry2
0x18004297c  test    eax, eax
0x18004297e  jz      short loc_1800429F1
0x180042980  mov     bl, 40h ; '@'
0x180042982  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180042988  jz      loc_180042C78
0x18004298e  mov     r8d, eax
0x180042991  mov     word ptr [rbp+0FF0h+var_A60], r15w
0x180042999  lea     rdx, aOnroutechangeG; "OnRouteChange: GetIpForwardEntry2 faile"...
0x1800429a0  mov     word ptr [rbp+0FF0h+var_A90], r15w
0x1800429a8  lea     rcx, [rbp+0FF0h+var_A60]
0x1800429af  call    FormatRRASErrorString
0x1800429b4  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x1800429ba  jz      loc_180042C78
0x1800429c0  lea     rax, [rbp+0FF0h+var_A90]
0x1800429c7  mov     rcx, r12
0x1800429ca  mov     [rsp+10F0h+var_10C8], rax
0x1800429cf  lea     r9, [rsp+10F0h+var_1088]
0x1800429d4  lea     r8, [rbp+0FF0h+var_A60]
0x1800429db  mov     qword ptr [rsp+10F0h+Length], r15
0x1800429e0  lea     rdx, RasRtrMgrParamTraceError
0x1800429e7  call    McTemplateU0zjzz_EventWriteTransfer
0x1800429ec  jmp     loc_180042C78
0x1800429f1  mov     eax, 2
0x1800429f6  cmp     [rdi+0Ch], ax
0x1800429fa  jnz     loc_180042B3D
0x180042a00  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x180042a07  mov     edi, ebx
0x180042a09  jge     loc_180042B5A
0x180042a0f  mov     ecx, [rbp+0FF0h+var_1050]
0x180042a12  mov     r10d, ecx
0x180042a15  movzx   r11d, [rbp+0FF0h+var_1038]
0x180042a1a  mov     eax, ecx
0x180042a1c  mov     [rsp+10F0h+var_10A8], r15d
0x180042a21  shr     eax, 10h
0x180042a24  movzx   edx, al
0x180042a27  mov     eax, ecx
0x180042a29  mov     [rsp+10F0h+var_10B0], r15d
0x180042a2e  mov     [rsp+10F0h+var_10B8], r15d
0x180042a33  mov     dword ptr [rsp+10F0h+var_10C0], r11d
0x180042a38  shr     r10d, 18h
0x180042a3c  shr     eax, 8
0x180042a3f  mov     dword ptr [rsp+10F0h+var_10C8], r10d
0x180042a44  movzx   r8d, cl
0x180042a48  lea     rcx, [rbp+0FF0h+var_A60]
0x180042a4f  mov     [rsp+10F0h+Length], edx
0x180042a53  lea     rdx, aOnroutechangeC; "OnRouteChange: Change for route to %d.%"...
0x180042a5a  movzx   r9d, al
0x180042a5e  mov     word ptr [rbp+0FF0h+var_A60], r15w
0x180042a66  mov     word ptr [rbp+0FF0h+var_A90], r15w
0x180042a6e  call    FormatRRASErrorString
0x180042a73  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x180042a7a  jge     loc_180042B55
0x180042a80  lea     rax, [rbp+0FF0h+var_A90]
0x180042a87  mov     rdx, r13
0x180042a8a  mov     [rsp+10F0h+var_10C8], rax
0x180042a8f  lea     r9, [rsp+10F0h+var_1088]
0x180042a94  lea     r8, [rbp+0FF0h+var_A60]
0x180042a9b  mov     qword ptr [rsp+10F0h+Length], r15
0x180042aa0  mov     rcx, r12
0x180042aa3  call    McTemplateU0zjzz_EventWriteTransfer
0x180042aa8  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x180042aaf  jge     loc_180042B55
0x180042ab5  mov     r8d, [rbp+0FF0h+var_1030]
0x180042ab9  mov     r10d, r8d
0x180042abc  mov     eax, r8d
0x180042abf  shr     r10d, 18h
0x180042ac3  shr     eax, 10h
0x180042ac6  movzx   edx, al
0x180042ac9  mov     eax, r8d
0x180042acc  mov     dword ptr [rsp+10F0h+var_10C0], r10d
0x180042ad1  mov     dword ptr [rsp+10F0h+var_10C8], edx
0x180042ad5  lea     rdx, aOnroutechangeR_0; "OnRouteChange: Route via i/f Luid %lx, "...
0x180042adc  shr     eax, 8
0x180042adf  movzx   ecx, al
0x180042ae2  mov     [rsp+10F0h+Length], ecx
0x180042ae6  lea     rcx, [rbp+0FF0h+var_A60]
0x180042aed  movzx   r9d, r8b
0x180042af1  mov     r8, [rbp+0FF0h+Destination]
0x180042af5  mov     word ptr [rbp+0FF0h+var_A60], r15w
0x180042afd  mov     word ptr [rbp+0FF0h+var_A90], r15w
0x180042b05  call    FormatRRASErrorString
0x180042b0a  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x180042b11  jge     short loc_180042B55
0x180042b13  lea     rax, [rbp+0FF0h+var_A90]
0x180042b1a  mov     rdx, r13
0x180042b1d  mov     [rsp+10F0h+var_10C8], rax
0x180042b22  lea     r9, [rsp+10F0h+var_1088]
0x180042b27  lea     r8, [rbp+0FF0h+var_A60]
0x180042b2e  mov     qword ptr [rsp+10F0h+Length], r15
0x180042b33  mov     rcx, r12
0x180042b36  call    McTemplateU0zjzz_EventWriteTransfer
0x180042b3b  jmp     short loc_180042B55
0x180042b3d  lea     r8, [rbp+0FF0h+Destination]
0x180042b41  mov     edi, r15d
0x180042b44  lea     rdx, [rsp+10F0h+var_1088]
0x180042b49  lea     rcx, aOnroutechange; "OnRouteChange:"
0x180042b50  call    PrintIpv6Route
0x180042b55  mov     eax, 2
0x180042b5a  cmp     esi, eax
0x180042b5c  jnz     short loc_180042B70
0x180042b5e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180042b65  jz      short loc_180042BAC
0x180042b67  lea     r8, aOnroutechangeR_1; "OnRouteChange: Route Deletion Notificat"...
0x180042b6e  jmp     short loc_180042B83
0x180042b70  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180042b77  mov     ebx, r15d
0x180042b7a  jz      short loc_180042BAC
0x180042b7c  lea     r8, aOnroutechangeR; "OnRouteChange: Route Addition/Update No"...
0x180042b83  lea     rax, [rbp+0FF0h+var_A90]
0x180042b8a  mov     word ptr [rbp+0FF0h+var_A90], r15w
0x180042b92  mov     [rsp+10F0h+var_10C8], rax
0x180042b97  lea     r9, [rsp+10F0h+var_1088]
0x180042b9c  mov     rdx, r13
0x180042b9f  mov     qword ptr [rsp+10F0h+Length], r15
0x180042ba4  mov     rcx, r12
0x180042ba7  call    McTemplateU0zjzz_EventWriteTransfer
0x180042bac  mov     r8d, [rbp+0FF0h+var_1008]
0x180042bb0  cmp     r8d, 4
  ... truncated ...
```

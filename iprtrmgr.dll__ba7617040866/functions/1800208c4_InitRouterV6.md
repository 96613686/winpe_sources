# InitRouterV6

- ea: `0x1800208c4`
- end: `0x180020bdc`
- name: `InitRouterV6`
- size: `792`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002b4b8`

## callees

- `0x1800023f4`
- `0x18000ac60`
- `0x180011374`
- `0x1800208c4`
- `0x1800213b0`
- `0x1800433a0`
- `0x18004d144`
- `0x1800523a8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180020b04`
- `ntdll!RtlAcquireResourceExclusive` at `0x180020b13`
- `ntdll!RtlAcquireResourceExclusive` at `0x180020b04`
- `ntdll!RtlAcquireResourceExclusive` at `0x180020b13`
- `ntdll!RtlReleaseResource` at `0x180020b2b`
- `ntdll!RtlReleaseResource` at `0x180020b38`
- `ntdll!RtlReleaseResource` at `0x180020b2b`
- `ntdll!RtlReleaseResource` at `0x180020b38`
- `rtutils!RouterLogEventA` at `0x180020a27`
- `rtutils!RouterLogEventA` at `0x180020a27`
- `WS2_32!__imp_closesocket` at `0x180020a52`
- `WS2_32!__imp_closesocket` at `0x180020a52`
- `WS2_32!__imp_socket` at `0x18002099a`
- `WS2_32!__imp_socket` at `0x18002099a`
- `WS2_32!__imp_WSAGetLastError` at `0x1800209b6`
- `WS2_32!__imp_WSAGetLastError` at `0x1800209b6`

## string_xrefs

- `0x1800209c9`: `InitRouterV6: IPv6 initialization failed. This could be because IPv6 is uninstalled in the system. Error %d`
- `0x180020af2`: `InitRouterV6: Couldnt open WanArp driver`

## pseudocode

```c
__int64 __fastcall InitRouterV6(__int64 a1)
{
  char v2; // al
  SOCKET v3; // rax
  unsigned int Error; // eax
  DWORD dwErrorCode; // ebx
  bool v6; // zf
  char v8; // cl
  const wchar_t *v9; // rdx
  const wchar_t *v10; // r8
  LPSTR plpszSubStringArray; // [rsp+38h] [rbp-840h] BYREF
  struct _GUID v12; // [rsp+40h] [rbp-838h] BYREF
  int v13; // [rsp+50h] [rbp-828h] BYREF
  _BYTE v14[2044]; // [rsp+54h] [rbp-824h] BYREF

  v13 = 0;
  v12 = GUID_NULL;
  memset_0(v14, 0, sizeof(v14));
  v2 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v13) = 0;
    FormatRRASErrorString(&v13, L"Entered: %ws", L"InitRouterV6");
    v2 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v13);
      v2 = Microsoft_Windows_RRASEnableBits;
    }
  }
  if ( v2 < 0 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"InitRouterV6: Initializing router for IPv6 transport");
  g_hRouteChangeNotificationV6 = 0;
  v3 = socket(23, 2, 0);
  if ( v3 == -1 )
  {
    plpszSubStringArray = "IPv6";
    Error = WSAGetLastError();
    dwErrorCode = Error;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v13) = 0;
      FormatRRASErrorString(
        &v13,
        L"InitRouterV6: IPv6 initialization failed. This could be because IPv6 is uninstalled in the system. Error %d",
        Error);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v13);
    }
    if ( g_dwLoggingLevel )
      RouterLogEventA(g_hLogHandle, 1u, 0x4EF8u, 1u, &plpszSubStringArray, dwErrorCode);
    v6 = (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL;
    goto LABEL_13;
  }
  closesocket(v3);
  SetPacketFiltersState(a1, 87);
  dwErrorCode = RegisterRtmEntitiesForRoutingDomain(0x57u, &v12);
  if ( dwErrorCode )
  {
    v8 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_22;
    v9 = L"InitRouterV6: Error %d in RegisterRtmEntitiesForRoutingDomain\n";
LABEL_19:
    LOWORD(v13) = 0;
    FormatRRASErrorString(&v13, v9, dwErrorCode);
    v8 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v10 = (const wchar_t *)&v13;
LABEL_21:
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, v10);
      v8 = Microsoft_Windows_RRASEnableBits;
    }
LABEL_22:
    v6 = v8 >= 0;
LABEL_13:
    if ( !v6 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: InitRouterV6");
    return dwErrorCode;
  }
  if ( !RouterRoleLanOnly )
  {
    dwErrorCode = InitializeDemandDial(0);
    if ( dwErrorCode )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        return dwErrorCode;
      v10 = L"InitRouterV6: Couldnt open WanArp driver";
      goto LABEL_21;
    }
  }
  RtlAcquireResourceExclusive(&Resource, 1u);
  RtlAcquireResourceExclusive(&stru_18008C4A0, 1u);
  LoadRoutingProtocols(a1, 0x57u);
  RtlReleaseResource(&stru_18008C4A0);
  RtlReleaseResource(&Resource);
  dwErrorCode = RegisterRouteChangeNotificationForAllRoutingDomains(87);
  if ( dwErrorCode )
  {
    v8 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_22;
    v9 = L"InitRouterV6: RegisterRouteChangeNotificationForAllRoutingDomains failed, returned %d";
    goto LABEL_19;
  }
  dwErrorCode = RegisterIpAddressChangeNotifications(0x57u, &v12);
  if ( dwErrorCode )
  {
    v8 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_22;
    v9 = L"InitRouterV6: RegisterIpAddressChangeNotifications failed, returned %d";
    goto LABEL_19;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"Leaving: InitRouterV6");
  return 0;
}

```

## disassembly

```asm
0x1800208c4  mov     [rsp+arg_8], rbx
0x1800208c9  mov     [rsp+arg_10], rdi
0x1800208ce  push    r13
0x1800208d0  push    r14
0x1800208d2  push    r15
0x1800208d4  sub     rsp, 860h
0x1800208db  mov     rax, cs:__security_cookie
0x1800208e2  xor     rax, rsp
0x1800208e5  mov     [rsp+878h+var_28], rax
0x1800208ed  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800208f4  mov     rdi, rcx
0x1800208f7  xor     eax, eax
0x1800208f9  xor     edx, edx; Val
0x1800208fb  mov     [rsp+878h+var_828], eax
0x1800208ff  mov     r8d, 7FCh; Size
0x180020905  lea     rcx, [rsp+878h+var_824]; void *
0x18002090a  movdqu  xmmword ptr [rsp+878h+var_838.Data1], xmm0
0x180020910  call    memset_0
0x180020915  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18002091c  lea     r14, RasRtrmgrTraceInfo
0x180020923  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002092a  test    al, al
0x18002092c  jns     short loc_18002096F
0x18002092e  xor     eax, eax
0x180020930  lea     r8, aInitrouterv6; "InitRouterV6"
0x180020937  lea     rdx, aEnteredWs; "Entered: %ws"
0x18002093e  mov     word ptr [rsp+878h+var_828], ax
0x180020943  lea     rcx, [rsp+878h+var_828]
0x180020948  call    FormatRRASErrorString
0x18002094d  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180020954  test    al, al
0x180020956  jns     short loc_18002096F
0x180020958  lea     r8, [rsp+878h+var_828]
0x18002095d  mov     rdx, r14
0x180020960  mov     rcx, r15
0x180020963  call    McTemplateU0z_EventWriteTransfer
0x180020968  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18002096f  test    al, 80h
0x180020971  jz      short loc_180020985
0x180020973  lea     r8, aInitrouterv6In; "InitRouterV6: Initializing router for I"...
0x18002097a  mov     rdx, r14
0x18002097d  mov     rcx, r15
0x180020980  call    McTemplateU0z_EventWriteTransfer
0x180020985  xor     r8d, r8d; protocol
0x180020988  mov     cs:g_hRouteChangeNotificationV6, 0
0x180020993  lea     edx, [r8+2]; type
0x180020997  lea     ecx, [rdx+15h]; af
0x18002099a  call    cs:__imp_socket
0x1800209a0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800209a4  jnz     loc_180020A4F
0x1800209aa  lea     rax, aIpv6_0; "IPv6"
0x1800209b1  mov     [rsp+878h+var_840], rax
0x1800209b6  call    cs:__imp_WSAGetLastError
0x1800209bc  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800209c3  mov     ebx, eax
0x1800209c5  jge     short loc_1800209FB
0x1800209c7  xor     ecx, ecx
0x1800209c9  lea     rdx, aInitrouterv6Ip; "InitRouterV6: IPv6 initialization faile"...
0x1800209d0  mov     word ptr [rsp+878h+var_828], cx
0x1800209d5  mov     r8d, eax
0x1800209d8  lea     rcx, [rsp+878h+var_828]
0x1800209dd  call    FormatRRASErrorString
0x1800209e2  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800209e9  jge     short loc_1800209FB
0x1800209eb  lea     r8, [rsp+878h+var_828]
0x1800209f0  mov     rdx, r14
0x1800209f3  mov     rcx, r15
0x1800209f6  call    McTemplateU0z_EventWriteTransfer
0x1800209fb  cmp     cs:g_dwLoggingLevel, 1
0x180020a02  jb      short loc_180020A2D
0x180020a04  mov     rcx, cs:g_hLogHandle; hLogHandle
0x180020a0b  lea     rax, [rsp+878h+var_840]
0x180020a10  mov     edx, 1; dwEventType
0x180020a15  mov     [rsp+878h+dwErrorCode], ebx; dwErrorCode
0x180020a19  mov     r9d, edx; dwSubStringCount
0x180020a1c  mov     [rsp+878h+plpszSubStringArray], rax; plpszSubStringArray
0x180020a21  mov     r8d, 4EF8h; dwMessageId
0x180020a27  call    cs:__imp_RouterLogEventA
0x180020a2d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180020a34  jz      short loc_180020A48
0x180020a36  lea     r8, aLeavingInitrou; "Leaving: InitRouterV6"
0x180020a3d  mov     rdx, r14
0x180020a40  mov     rcx, r15
0x180020a43  call    McTemplateU0z_EventWriteTransfer
0x180020a48  mov     eax, ebx
0x180020a4a  jmp     loc_180020BB2
0x180020a4f  mov     rcx, rax; s
0x180020a52  call    cs:__imp_closesocket
0x180020a58  mov     r13d, 57h ; 'W'
0x180020a5e  mov     rcx, rdi
0x180020a61  mov     edx, r13d
0x180020a64  call    SetPacketFiltersState
0x180020a69  lea     rdx, [rsp+878h+var_838]
0x180020a6e  mov     ecx, r13d
0x180020a71  call    RegisterRtmEntitiesForRoutingDomain
0x180020a76  mov     ebx, eax
0x180020a78  test    eax, eax
0x180020a7a  jz      short loc_180020ACC
0x180020a7c  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180020a83  test    cl, cl
0x180020a85  jns     short loc_180020AC4
0x180020a87  lea     rdx, aInitrouterv6Er; "InitRouterV6: Error %d in RegisterRtmEn"...
0x180020a8e  xor     ecx, ecx
0x180020a90  mov     r8d, ebx
0x180020a93  mov     word ptr [rsp+878h+var_828], cx
0x180020a98  lea     rcx, [rsp+878h+var_828]
0x180020a9d  call    FormatRRASErrorString
0x180020aa2  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180020aa9  test    cl, cl
0x180020aab  jns     short loc_180020AC4
0x180020aad  lea     r8, [rsp+878h+var_828]
0x180020ab2  mov     rdx, r14
0x180020ab5  mov     rcx, r15
0x180020ab8  call    McTemplateU0z_EventWriteTransfer
0x180020abd  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180020ac4  test    cl, 80h
0x180020ac7  jmp     loc_180020A34
0x180020acc  cmp     cs:RouterRoleLanOnly, 0
0x180020ad3  jnz     short loc_180020AFB
0x180020ad5  xor     ecx, ecx
0x180020ad7  call    InitializeDemandDial
0x180020adc  mov     ebx, eax
0x180020ade  test    eax, eax
0x180020ae0  jz      short loc_180020AFB
0x180020ae2  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180020ae9  test    cl, 80h
0x180020aec  jz      loc_180020A48
0x180020af2  lea     r8, aInitrouterv6Co; "InitRouterV6: Couldnt open WanArp drive"...
0x180020af9  jmp     short loc_180020AB2
0x180020afb  mov     dl, 1; Wait
0x180020afd  lea     rcx, Resource; Resource
0x180020b04  call    cs:__imp_RtlAcquireResourceExclusive
0x180020b0a  mov     dl, 1; Wait
0x180020b0c  lea     rcx, stru_18008C4A0; Resource
0x180020b13  call    cs:__imp_RtlAcquireResourceExclusive
0x180020b19  mov     edx, r13d
0x180020b1c  mov     rcx, rdi
0x180020b1f  call    LoadRoutingProtocols
0x180020b24  lea     rcx, stru_18008C4A0; Resource
0x180020b2b  call    cs:__imp_RtlReleaseResource
0x180020b31  lea     rcx, Resource; Resource
0x180020b38  call    cs:__imp_RtlReleaseResource
0x180020b3e  mov     ecx, r13d
0x180020b41  call    RegisterRouteChangeNotificationForAllRoutingDomains
0x180020b46  mov     ebx, eax
0x180020b48  test    eax, eax
0x180020b4a  jz      short loc_180020B67
0x180020b4c  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180020b53  test    cl, cl
0x180020b55  jns     loc_180020AC4
0x180020b5b  lea     rdx, aInitrouterv6Re_0; "InitRouterV6: RegisterRouteChangeNotifi"...
0x180020b62  jmp     loc_180020A8E
0x180020b67  lea     rdx, [rsp+878h+var_838]; struct _GUID *
0x180020b6c  mov     ecx, r13d; unsigned int
0x180020b6f  call    RegisterIpAddressChangeNotifications
0x180020b74  mov     ebx, eax
0x180020b76  test    eax, eax
0x180020b78  jz      short loc_180020B95
0x180020b7a  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180020b81  test    cl, cl
0x180020b83  jns     loc_180020AC4
0x180020b89  lea     rdx, aInitrouterv6Re; "InitRouterV6: RegisterIpAddressChangeNo"...
0x180020b90  jmp     loc_180020A8E
0x180020b95  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180020b9c  jz      short loc_180020BB0
0x180020b9e  lea     r8, aLeavingInitrou; "Leaving: InitRouterV6"
0x180020ba5  mov     rdx, r14
0x180020ba8  mov     rcx, r15
0x180020bab  call    McTemplateU0z_EventWriteTransfer
0x180020bb0  xor     eax, eax
0x180020bb2  mov     rcx, [rsp+878h+var_28]
0x180020bba  xor     rcx, rsp; StackCookie
0x180020bbd  call    __security_check_cookie
0x180020bc2  lea     r11, [rsp+878h+var_18]
0x180020bca  mov     rbx, [r11+28h]
0x180020bce  mov     rdi, [r11+30h]
0x180020bd2  mov     rsp, r11
0x180020bd5  pop     r15
0x180020bd7  pop     r14
0x180020bd9  pop     r13
0x180020bdb  retn
```

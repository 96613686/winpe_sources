# InitRouterV4

- ea: `0x180020238`
- end: `0x1800208bd`
- name: `InitRouterV4`
- size: `1669`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002aef4`

## callees

- `0x1800023f4`
- `0x18000ac60`
- `0x180011374`
- `0x180020238`
- `0x180020be4`
- `0x1800213b0`
- `0x1800219a4`
- `0x180033520`
- `0x180035b58`
- `0x180037e78`
- `0x18003ab6c`
- `0x1800433a0`
- `0x18004d144`
- `0x1800523a8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x1800207e5`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800207f4`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800207e5`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800207f4`
- `ntdll!RtlReleaseResource` at `0x18002080e`
- `ntdll!RtlReleaseResource` at `0x18002081b`
- `ntdll!RtlReleaseResource` at `0x18002080e`
- `ntdll!RtlReleaseResource` at `0x18002081b`
- `KERNEL32!HeapFree` at `0x1800205f6`
- `KERNEL32!HeapFree` at `0x1800205f6`
- `rtutils!RouterLogEventA` at `0x180020410`
- `rtutils!RouterLogEventA` at `0x180020410`
- `WS2_32!__imp_closesocket` at `0x18002043b`
- `WS2_32!__imp_closesocket` at `0x18002043b`
- `WS2_32!__imp_socket` at `0x18002037c`
- `WS2_32!__imp_socket` at `0x18002037c`
- `WS2_32!__imp_WSAGetLastError` at `0x180020398`
- `WS2_32!__imp_WSAGetLastError` at `0x180020398`
- `rtm!MgmInitialize` at `0x1800206d6`
- `rtm!MgmInitialize` at `0x1800206d6`
- `iprtprio!SetPriorityInfo` at `0x180020774`
- `iprtprio!SetPriorityInfo` at `0x180020774`

## string_xrefs

- `0x1800203b4`: `InitRouterV4: IPv4 initialization failed. This could be because IPv4 is uninstalled in the system.Error %d`
- `0x1800207d0`: `InitRouterV4: Couldnt open WanArp driver`

## pseudocode

```c
__int64 __fastcall InitRouterV4(__int64 a1)
{
  char v2; // al
  SOCKET v3; // rax
  unsigned int Error; // eax
  DWORD v5; // ebx
  bool v6; // zf
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int IpForwardTable; // eax
  unsigned int *v11; // rsi
  unsigned int i; // r15d
  __int64 v13; // r12
  char v14; // cl
  const wchar_t *v15; // rdx
  const wchar_t *v16; // r8
  LPSTR *plpszSubStringArray; // [rsp+20h] [rbp-908h]
  __int64 dwErrorCode; // [rsp+28h] [rbp-900h]
  __int64 v19; // [rsp+30h] [rbp-8F8h]
  __int64 v20; // [rsp+38h] [rbp-8F0h]
  __int64 v21; // [rsp+40h] [rbp-8E8h]
  __int64 v22; // [rsp+48h] [rbp-8E0h]
  __int64 v23; // [rsp+50h] [rbp-8D8h]
  LPVOID lpMem; // [rsp+60h] [rbp-8C8h] BYREF
  LPSTR v25; // [rsp+68h] [rbp-8C0h] BYREF
  __int128 v26; // [rsp+70h] [rbp-8B8h] BYREF
  __int128 v27; // [rsp+80h] [rbp-8A8h]
  __int128 v28; // [rsp+90h] [rbp-898h]
  __int128 v29; // [rsp+A0h] [rbp-888h] BYREF
  __int128 v30; // [rsp+B0h] [rbp-878h]
  __int64 v31; // [rsp+C0h] [rbp-868h]
  struct _GUID v32; // [rsp+C8h] [rbp-860h] BYREF
  int v33; // [rsp+E0h] [rbp-848h] BYREF
  _BYTE v34[2044]; // [rsp+E4h] [rbp-844h] BYREF

  v29 = 0;
  v30 = 0;
  v31 = 0;
  v33 = 0;
  v32 = GUID_NULL;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  memset_0(v34, 0, sizeof(v34));
  v2 = Microsoft_Windows_RRASEnableBits;
  LOBYTE(lpMem) = Microsoft_Windows_RRASEnableBits & 0x80;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, L"InitRouterV4");
    v2 = Microsoft_Windows_RRASEnableBits;
  }
  LOBYTE(lpMem) = v2 & 0x80;
  if ( v2 < 0 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"InitRouterV4: Initializing router for IPv4 transport");
  InitializeBoundaryTable();
  g_hRouteChangeNotificationV4 = 0;
  g_pIpHeader = (__int64)g_pdwIpAndIcmpBuf;
  g_wsaIpRcvBuf.buf = (CHAR *)g_pdwIpAndIcmpBuf;
  g_hMcastNotification = 0;
  g_wsaMcRcvBuf.buf = (CHAR *)g_byMcMiscBuffer;
  *(_DWORD *)&g_sinAllSystemsAddr.sa_family = 2;
  *(_DWORD *)&g_sinAllSystemsAddr.sa_data[2] = 16777440;
  g_wsaIpRcvBuf.len = 136;
  g_wsaMcRcvBuf.len = 1500;
  v3 = socket(2, 2, 0);
  if ( v3 == -1 )
  {
    v25 = "IPv4";
    Error = WSAGetLastError();
    v5 = Error;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v33) = 0;
      FormatRRASErrorString(
        &v33,
        L"InitRouterV4: IPv4 initialization failed. This could be because IPv4 is uninstalled in the system.Error %d",
        Error);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v33);
    }
    if ( g_dwLoggingLevel )
      RouterLogEventA(g_hLogHandle, 1u, 0x4EF8u, 1u, &v25, v5);
    v6 = (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL;
    goto LABEL_12;
  }
  closesocket(v3);
  SetPacketFiltersState(a1, 33);
  lpMem = 0;
  IpForwardTable = AllocateAndGetIpForwardTable(&lpMem, v8, v9, 0, 1);
  if ( IpForwardTable )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v33) = 0;
      FormatRRASErrorString(&v33, L"InitRouterV4: Couldnt get initial routes. Error %d", IpForwardTable);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v33);
    }
  }
  else
  {
    v11 = (unsigned int *)lpMem;
    if ( *(_DWORD *)lpMem )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v33) = 0;
        FormatRRASErrorString(&v33, L"%d stack routes on startup\n", *(unsigned int *)lpMem);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v33);
      }
      for ( i = 0; i < *v11; ++i )
      {
        v13 = 14LL * i;
        if ( v11[v13 + 7] == 3 && (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          LOWORD(v33) = 0;
          LODWORD(v23) = v11[v13 + 6];
          LODWORD(v22) = HIBYTE(v11[v13 + 2]);
          LODWORD(v21) = BYTE2(v11[v13 + 2]);
          LODWORD(v20) = BYTE1(v11[v13 + 2]);
          LODWORD(v19) = LOBYTE(v11[v13 + 2]);
          LODWORD(dwErrorCode) = HIBYTE(v11[v13 + 1]);
          LODWORD(plpszSubStringArray) = BYTE2(v11[v13 + 1]);
          FormatRRASErrorString(
            &v33,
            L"NETMGMT route %d.%d.%d.%d/%d.%d.%d.%d, type 0x%x",
            LOBYTE(v11[v13 + 1]),
            BYTE1(v11[v13 + 1]),
            plpszSubStringArray,
            dwErrorCode,
            v19,
            v20,
            v21,
            v22,
            v23);
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v33);
        }
      }
    }
    HeapFree(IPRouterHeap, 0, v11);
  }
  v5 = RegisterRtmEntitiesForRoutingDomain(0x21u, &v32);
  if ( v5 )
  {
    v14 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_37;
    v15 = L"InitRouterV4: Error %d in RegisterRtmEntitiesForRoutingDomain\n";
LABEL_34:
    LOWORD(v33) = 0;
    FormatRRASErrorString(&v33, v15, v5);
    v14 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v16 = (const wchar_t *)&v33;
LABEL_36:
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, v16);
      v14 = Microsoft_Windows_RRASEnableBits;
    }
LABEL_37:
    v6 = v14 >= 0;
LABEL_12:
    if ( !v6 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: InitRouterV4");
    return v5;
  }
  LODWORD(v26) = g_dwLoggingLevel;
  *(_QWORD *)((char *)&v26 + 4) = 0x1010000001DLL;
  HIDWORD(v26) = 257;
  *(_QWORD *)&v27 = SetMfe;
  *((_QWORD *)&v27 + 1) = DeleteMfe;
  *(_QWORD *)&v28 = GetMfe;
  *((_QWORD *)&v28 + 1) = RmHasBoundary;
  v5 = MgmInitialize(&v26, &v29);
  if ( v5 )
  {
    v14 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_37;
    v15 = L"InitRouterV4: Error %d initializing MGM\n";
    goto LABEL_34;
  }
  g_pfnMgmNewPacket = *((_QWORD *)&v29 + 1);
  g_pfnMgmMfeDeleted = v29;
  g_pfnMgmBlockGroups = *((_QWORD *)&v30 + 1);
  g_pfnMgmUnBlockGroups = v31;
  g_pfnMgmWrongIf = v30;
  if ( (unsigned int)StartMulticast() && (Microsoft_Windows_RRASEnableBits & 0x80) != 0 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"InitRouterV4: Could not start multicast");
  StartMcMisc();
  SetPriorityInfo(a1);
  SetScopeInfo(a1);
  v5 = InitializeMibHandler();
  if ( v5 )
  {
    v14 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_37;
    v15 = L"InitRouterV4: InitializeMibHandler failed, returned %d";
    goto LABEL_34;
  }
  if ( !RouterRoleLanOnly )
  {
    v5 = InitializeDemandDial(1);
    if ( v5 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80) == 0 )
        return v5;
      v16 = L"InitRouterV4: Couldnt open WanArp driver";
      goto LABEL_36;
    }
  }
  RtlAcquireResourceExclusive(&Resource, 1u);
  RtlAcquireResourceExclusive(&stru_18008C4A0, 1u);
  LoadRoutingProtocols(a1, 33);
  RtlReleaseResource(&stru_18008C4A0);
  RtlReleaseResource(&Resource);
  v5 = RegisterRouteChangeNotificationForAllRoutingDomains(33);
  if ( v5 )
  {
    v14 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_37;
    v15 = L"InitRouterV4: RegisterRouteChangeNotificationForAllRoutingDomains failed, returned %d";
    goto LABEL_34;
  }
  v5 = RegisterIpAddressChangeNotifications(0x21u, &v32);
  if ( v5 )
  {
    v14 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_37;
    v15 = L"InitRouterV4: RegisterIpAddressChangeNotifications failed, returned %d";
    goto LABEL_34;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80) != 0 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"Leaving: InitRouterV4");
  return 0;
}

```

## disassembly

```asm
0x180020238  push    rbx
0x18002023a  push    rsi
0x18002023b  push    rdi
0x18002023c  push    r12
0x18002023e  push    r13
0x180020240  push    r15
0x180020242  sub     rsp, 8F8h
0x180020249  mov     rax, cs:__security_cookie
0x180020250  xor     rax, rsp
0x180020253  mov     [rsp+928h+var_48], rax
0x18002025b  xorps   xmm0, xmm0
0x18002025e  xorps   xmm1, xmm1
0x180020261  movups  [rsp+928h+var_888], xmm0
0x180020269  mov     r13, rcx
0x18002026c  xor     eax, eax
0x18002026e  movups  [rsp+928h+var_878], xmm0
0x180020276  xor     edi, edi
0x180020278  xor     edx, edx; Val
0x18002027a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180020281  mov     r8d, 7FCh; Size
0x180020287  mov     [rsp+928h+var_868], rax
0x18002028f  lea     rcx, [rsp+928h+var_844]; void *
0x180020297  mov     [rsp+928h+var_848], edi
0x18002029e  movdqu  xmmword ptr [rsp+928h+var_860.Data1], xmm0
0x1800202a7  movups  [rsp+928h+var_8B8], xmm1
0x1800202ac  movups  [rsp+928h+var_8A8], xmm1
0x1800202b4  movups  [rsp+928h+var_898], xmm1
0x1800202bc  call    memset_0
0x1800202c1  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x1800202c8  lea     r15, RasRtrmgrTraceInfo
0x1800202cf  mov     cl, al
0x1800202d1  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800202d8  mov     sil, 80h
0x1800202db  and     cl, sil
0x1800202de  mov     byte ptr [rsp+928h+lpMem], cl
0x1800202e2  jz      short loc_1800202FD
0x1800202e4  lea     r8, aInitrouterv4; "InitRouterV4"
0x1800202eb  mov     rdx, r15
0x1800202ee  mov     rcx, r12
0x1800202f1  call    McTemplateU0z_EventWriteTransfer
0x1800202f6  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x1800202fd  and     al, sil
0x180020300  mov     byte ptr [rsp+928h+lpMem], al
0x180020304  jz      short loc_180020318
0x180020306  lea     r8, aInitrouterv4In; "InitRouterV4: Initializing router for I"...
0x18002030d  mov     rdx, r15
0x180020310  mov     rcx, r12
0x180020313  call    McTemplateU0z_EventWriteTransfer
0x180020318  call    InitializeBoundaryTable
0x18002031d  lea     rax, g_pdwIpAndIcmpBuf
0x180020324  mov     cs:g_hRouteChangeNotificationV4, rdi
0x18002032b  mov     ecx, 2; af
0x180020330  mov     cs:g_pIpHeader, rax
0x180020337  mov     cs:g_wsaIpRcvBuf.buf, rax
0x18002033e  xor     r8d, r8d; protocol
0x180020341  lea     rax, g_byMcMiscBuffer
0x180020348  mov     cs:g_hMcastNotification, rdi
0x18002034f  mov     edx, ecx; type
0x180020351  mov     cs:g_wsaMcRcvBuf.buf, rax
0x180020358  mov     dword ptr cs:g_sinAllSystemsAddr.sa_family, ecx
0x18002035e  mov     dword ptr cs:g_sinAllSystemsAddr.sa_data+2, 10000E0h
0x180020368  mov     cs:g_wsaIpRcvBuf.len, 88h
0x180020372  mov     cs:g_wsaMcRcvBuf.len, 5DCh
0x18002037c  call    cs:__imp_socket
0x180020382  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180020386  jnz     loc_180020438
0x18002038c  lea     rax, aIpv4; "IPv4"
0x180020393  mov     [rsp+928h+var_8C0], rax
0x180020398  call    cs:__imp_WSAGetLastError
0x18002039e  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x1800203a5  mov     ebx, eax
0x1800203a7  jge     short loc_1800203E4
0x1800203a9  mov     r8d, eax
0x1800203ac  mov     word ptr [rsp+928h+var_848], di
0x1800203b4  lea     rdx, aInitrouterv4Ip; "InitRouterV4: IPv4 initialization faile"...
0x1800203bb  lea     rcx, [rsp+928h+var_848]
0x1800203c3  call    FormatRRASErrorString
0x1800203c8  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x1800203cf  jge     short loc_1800203E4
0x1800203d1  lea     r8, [rsp+928h+var_848]
0x1800203d9  mov     rdx, r15
0x1800203dc  mov     rcx, r12
0x1800203df  call    McTemplateU0z_EventWriteTransfer
0x1800203e4  cmp     cs:g_dwLoggingLevel, 1
0x1800203eb  jb      short loc_180020416
0x1800203ed  mov     rcx, cs:g_hLogHandle; hLogHandle
0x1800203f4  lea     rax, [rsp+928h+var_8C0]
0x1800203f9  mov     edx, 1; dwEventType
0x1800203fe  mov     dword ptr [rsp+928h+dwErrorCode], ebx; dwErrorCode
0x180020402  mov     r9d, edx; dwSubStringCount
0x180020405  mov     [rsp+928h+plpszSubStringArray], rax; plpszSubStringArray
0x18002040a  mov     r8d, 4EF8h; dwMessageId
0x180020410  call    cs:__imp_RouterLogEventA
0x180020416  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x18002041d  jz      short loc_180020431
0x18002041f  lea     r8, aLeavingInitrou_1; "Leaving: InitRouterV4"
0x180020426  mov     rdx, r15
0x180020429  mov     rcx, r12
0x18002042c  call    McTemplateU0z_EventWriteTransfer
0x180020431  mov     eax, ebx
0x180020433  jmp     loc_18002089C
0x180020438  mov     rcx, rax; s
0x18002043b  call    cs:__imp_closesocket
0x180020441  mov     edx, 21h ; '!'
0x180020446  mov     rcx, r13
0x180020449  call    SetPacketFiltersState
0x18002044e  xor     r9d, r9d
0x180020451  mov     [rsp+928h+lpMem], rdi
0x180020456  lea     rcx, [rsp+928h+lpMem]
0x18002045b  mov     dword ptr [rsp+928h+plpszSubStringArray], 1
0x180020463  call    AllocateAndGetIpForwardTable
0x180020468  test    eax, eax
0x18002046a  jz      short loc_1800204BD
0x18002046c  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180020473  jge     loc_1800205FF
0x180020479  mov     r8d, eax
0x18002047c  mov     word ptr [rsp+928h+var_848], di
0x180020484  lea     rdx, aInitrouterv4Co; "InitRouterV4: Couldnt get initial route"...
0x18002048b  lea     rcx, [rsp+928h+var_848]
0x180020493  call    FormatRRASErrorString
0x180020498  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x18002049f  jge     loc_1800205FF
0x1800204a5  lea     r8, [rsp+928h+var_848]
0x1800204ad  mov     rdx, r15
0x1800204b0  mov     rcx, r12
0x1800204b3  call    McTemplateU0z_EventWriteTransfer
0x1800204b8  jmp     loc_1800205FF
0x1800204bd  mov     rsi, [rsp+928h+lpMem]
0x1800204c2  cmp     [rsi], edi
0x1800204c4  jz      loc_1800205EA
0x1800204ca  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x1800204d1  jge     short loc_18002050E
0x1800204d3  mov     word ptr [rsp+928h+var_848], di
0x1800204db  lea     rdx, aDStackRoutesOn; "%d stack routes on startup\n"
0x1800204e2  mov     r8d, [rsi]
0x1800204e5  lea     rcx, [rsp+928h+var_848]
0x1800204ed  call    FormatRRASErrorString
0x1800204f2  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x1800204f9  jge     short loc_18002050E
0x1800204fb  lea     r8, [rsp+928h+var_848]
0x180020503  mov     rdx, r15
0x180020506  mov     rcx, r12
0x180020509  call    McTemplateU0z_EventWriteTransfer
0x18002050e  mov     r15d, edi
0x180020511  cmp     r15d, [rsi]
0x180020514  jnb     loc_1800205E3
0x18002051a  mov     eax, r15d
0x18002051d  imul    r12, rax, 38h ; '8'
0x180020521  cmp     dword ptr [r12+rsi+1Ch], 3
0x180020527  jnz     loc_1800205D4
0x18002052d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180020534  jge     loc_1800205D4
0x18002053a  mov     word ptr [rsp+928h+var_848], di
0x180020542  movzx   ecx, byte ptr [r12+rsi+8]
0x180020548  movzx   edx, byte ptr [r12+rsi+7]
0x18002054e  movzx   r11d, byte ptr [r12+rsi+0Bh]
0x180020554  mov     eax, [r12+rsi+18h]
0x180020559  movzx   ebx, byte ptr [r12+rsi+0Ah]
0x18002055f  movzx   edi, byte ptr [r12+rsi+9]
0x180020565  movzx   r10d, byte ptr [r12+rsi+6]
0x18002056b  movzx   r9d, byte ptr [r12+rsi+5]
0x180020571  movzx   r8d, byte ptr [r12+rsi+4]
0x180020577  mov     [rsp+928h+var_8D8], eax
0x18002057b  mov     dword ptr [rsp+928h+var_8E0], r11d
0x180020580  mov     dword ptr [rsp+928h+var_8E8], ebx
0x180020584  mov     dword ptr [rsp+928h+var_8F0], edi
0x180020588  mov     dword ptr [rsp+928h+var_8F8], ecx
0x18002058c  lea     rcx, [rsp+928h+var_848]
0x180020594  mov     dword ptr [rsp+928h+dwErrorCode], edx
0x180020598  lea     rdx, aNetmgmtRouteDD; "NETMGMT route %d.%d.%d.%d/%d.%d.%d.%d, "...
0x18002059f  mov     dword ptr [rsp+928h+plpszSubStringArray], r10d
0x1800205a4  call    FormatRRASErrorString
0x1800205a9  xor     edi, edi
0x1800205ab  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800205b2  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x1800205b9  jge     short loc_1800205DB
0x1800205bb  lea     r8, [rsp+928h+var_848]
0x1800205c3  mov     rcx, r12
0x1800205c6  lea     rdx, RasRtrmgrTraceInfo
0x1800205cd  call    McTemplateU0z_EventWriteTransfer
0x1800205d2  jmp     short loc_1800205DB
0x1800205d4  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800205db  inc     r15d
0x1800205de  jmp     loc_180020511
0x1800205e3  lea     r15, RasRtrmgrTraceInfo
0x1800205ea  mov     rcx, cs:IPRouterHeap; hHeap
0x1800205f1  mov     r8, rsi; lpMem
0x1800205f4  xor     edx, edx; dwFlags
0x1800205f6  call    cs:__imp_HeapFree
0x1800205fc  mov     sil, 80h
0x1800205ff  lea     rdx, [rsp+928h+var_860]
0x180020607  mov     ecx, 21h ; '!'
0x18002060c  call    RegisterRtmEntitiesForRoutingDomain
0x180020611  mov     ebx, eax
0x180020613  test    eax, eax
0x180020615  jz      short loc_18002066E
0x180020617  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18002061e  test    cl, cl
0x180020620  jns     short loc_180020666
0x180020622  lea     rdx, aInitrouterv4Er_0; "InitRouterV4: Error %d in RegisterRtmEn"...
0x180020629  mov     r8d, ebx
0x18002062c  mov     word ptr [rsp+928h+var_848], di
0x180020634  lea     rcx, [rsp+928h+var_848]
0x18002063c  call    FormatRRASErrorString
0x180020641  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180020648  test    cl, cl
0x18002064a  jns     short loc_180020666
0x18002064c  lea     r8, [rsp+928h+var_848]
0x180020654  mov     rdx, r15
0x180020657  mov     rcx, r12
0x18002065a  call    McTemplateU0z_EventWriteTransfer
0x18002065f  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180020666  test    sil, cl
0x180020669  jmp     loc_18002041D
0x18002066e  mov     eax, cs:g_dwLoggingLevel
0x180020674  lea     rdx, [rsp+928h+var_888]
0x18002067c  mov     dword ptr [rsp+928h+var_8B8], eax
0x180020680  lea     rcx, [rsp+928h+var_8B8]
0x180020685  mov     eax, 101h
0x18002068a  mov     dword ptr [rsp+928h+var_8B8+4], 1Dh
0x180020692  mov     dword ptr [rsp+928h+var_8B8+8], eax
0x180020696  mov     dword ptr [rsp+928h+var_8B8+0Ch], eax
0x18002069a  lea     rax, SetMfe
0x1800206a1  mov     qword ptr [rsp+928h+var_8A8], rax
0x1800206a9  lea     rax, DeleteMfe
0x1800206b0  mov     qword ptr [rsp+928h+var_8A8+8], rax
0x1800206b8  lea     rax, GetMfe
0x1800206bf  mov     qword ptr [rsp+928h+var_898], rax
0x1800206c7  lea     rax, RmHasBoundary
0x1800206ce  mov     qword ptr [rsp+928h+var_898+8], rax
0x1800206d6  call    cs:__imp_MgmInitialize
0x1800206dc  mov     ebx, eax
0x1800206de  test    eax, eax
0x1800206e0  jz      short loc_1800206FD
0x1800206e2  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x1800206e9  test    cl, cl
0x1800206eb  jns     loc_180020666
0x1800206f1  lea     rdx, aInitrouterv4Er; "InitRouterV4: Error %d initializing MGM"...
0x1800206f8  jmp     loc_180020629
0x1800206fd  mov     rax, qword ptr [rsp+928h+var_888]
0x180020705  mov     cs:g_pfnMgmMfeDeleted, rax
0x18002070c  mov     rax, qword ptr [rsp+928h+var_888+8]
0x180020714  mov     cs:g_pfnMgmNewPacket, rax
0x18002071b  mov     rax, qword ptr [rsp+928h+var_878+8]
0x180020723  mov     cs:g_pfnMgmBlockGroups, rax
0x18002072a  mov     rax, [rsp+928h+var_868]
0x180020732  mov     cs:g_pfnMgmUnBlockGroups, rax
0x180020739  mov     rax, qword ptr [rsp+928h+var_878]
0x180020741  mov     cs:g_pfnMgmWrongIf, rax
0x180020748  call    StartMulticast
0x18002074d  test    eax, eax
0x18002074f  jz      short loc_18002076C
0x180020751  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x180020758  jz      short loc_18002076C
0x18002075a  lea     r8, aInitrouterv4Co_0; "InitRouterV4: Could not start multicast"
0x180020761  mov     rdx, r15
0x180020764  mov     rcx, r12
0x180020767  call    McTemplateU0z_EventWriteTransfer
0x18002076c  call    StartMcMisc
0x180020771  mov     rcx, r13
0x180020774  call    cs:__imp_SetPriorityInfo
0x18002077a  mov     rcx, r13
0x18002077d  call    SetScopeInfo
0x180020782  call    InitializeMibHandler
0x180020787  mov     ebx, eax
0x180020789  test    eax, eax
0x18002078b  jz      short loc_1800207A8
0x18002078d  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180020794  test    cl, cl
0x180020796  jns     loc_180020666
0x18002079c  lea     rdx, aInitrouterv4In_0; "InitRouterV4: InitializeMibHandler fail"...
0x1800207a3  jmp     loc_180020629
0x1800207a8  cmp     cs:RouterRoleLanOnly, edi
0x1800207ae  jnz     short loc_1800207DC
0x1800207b0  mov     ecx, 1
0x1800207b5  call    InitializeDemandDial
0x1800207ba  mov     ebx, eax
0x1800207bc  test    eax, eax
0x1800207be  jz      short loc_1800207DC
0x1800207c0  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x1800207c7  test    sil, cl
0x1800207ca  jz      loc_180020431
0x1800207d0  lea     r8, aInitrouterv4Co_1; "InitRouterV4: Couldnt open WanArp drive"...
0x1800207d7  jmp     loc_180020654
0x1800207dc  mov     dl, 1; Wait
0x1800207de  lea     rcx, Resource; Resource
0x1800207e5  call    cs:__imp_RtlAcquireResourceExclusive
0x1800207eb  mov     dl, 1; Wait
0x1800207ed  lea     rcx, stru_18008C4A0; Resource
0x1800207f4  call    cs:__imp_RtlAcquireResourceExclusive
0x1800207fa  mov     edx, 21h ; '!'
0x1800207ff  mov     rcx, r13
0x180020802  call    LoadRoutingProtocols
0x180020807  lea     rcx, stru_18008C4A0; Resource
0x18002080e  call    cs:__imp_RtlReleaseResource
0x180020814  lea     rcx, Resource; Resource
0x18002081b  call    cs:__imp_RtlReleaseResource
0x180020821  mov     ecx, 21h ; '!'
0x180020826  call    RegisterRouteChangeNotificationForAllRoutingDomains
0x18002082b  mov     ebx, eax
  ... truncated ...
```

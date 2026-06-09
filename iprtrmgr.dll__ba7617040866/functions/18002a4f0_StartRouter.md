# StartRouter

- ea: `0x18002a4f0`
- end: `0x18002a9aa`
- name: `StartRouter`
- size: `1210`
- prototype: `__int64 __fastcall(__int64, unsigned int, void *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x18000ac60`
- `0x18000c054`
- `0x18000e718`
- `0x18001f194`
- `0x18001f228`
- `0x18002a4f0`
- `0x18002a9b0`
- `0x18002aef4`
- `0x18002b4b8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18002a7d6`
- `KERNEL32!FreeLibrary` at `0x18002a8af`
- `KERNEL32!FreeLibrary` at `0x18002a7d6`
- `KERNEL32!FreeLibrary` at `0x18002a8af`
- `KERNEL32!SetEvent` at `0x18002a805`
- `KERNEL32!SetEvent` at `0x18002a824`
- `KERNEL32!SetEvent` at `0x18002a805`
- `KERNEL32!SetEvent` at `0x18002a824`
- `rtutils!RouterLogEventA` at `0x18002a5f4`
- `rtutils!RouterLogEventA` at `0x18002a5f4`
- `rtutils!TraceRegisterExA` at `0x18002a544`
- `rtutils!TraceRegisterExA` at `0x18002a544`
- `rtutils!RouterLogRegisterA` at `0x18002a560`
- `rtutils!RouterLogRegisterA` at `0x18002a560`

## string_xrefs

- `0x18002a70d`: `StartRouterCommon failed with error %d.`
- `0x18002a7a1`: `Clean-up is done here as no worker thread is running`
- `0x18002a7f0`: `Worker Thread is not running so Iprtrmgr freed in this context`
- `0x18002a8c5`: `Worker Thread Creation failed , so it should be freed here also`
- `0x18002a8ea`: `Worker thread is created`

## pseudocode

```c
__int64 __fastcall StartRouter(__int64 a1, unsigned int a2, void *a3, unsigned int a4, unsigned int a5)
{
  int v8; // r15d
  char v10; // bl
  const wchar_t *v12; // r8
  unsigned int started; // eax
  unsigned int v14; // esi
  unsigned int v15; // eax
  int v16; // ecx
  const wchar_t *v17; // r8
  HANDLE v18; // rcx
  int v19; // [rsp+40h] [rbp-848h] BYREF
  _BYTE v20[2044]; // [rsp+44h] [rbp-844h] BYREF

  v8 = 0;
  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  TraceHandle = TraceRegisterExA("IPRouterManager", 0);
  if ( !g_hLogHandle )
    g_hLogHandle = RouterLogRegisterA("IPRouterManager");
  v10 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v19) = 0;
    FormatRRASErrorString(&v19, L"Entered: %ws", L"StartRouter");
    v10 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v19);
      v10 = Microsoft_Windows_RRASEnableBits;
    }
  }
  if ( !a3 )
  {
    if ( g_dwLoggingLevel )
      RouterLogEventA(g_hLogHandle, 1u, 0x4EB5u, 0, 0, 0xE8u);
    return 87;
  }
  if ( a5 != 33 && a5 != 87 )
  {
    if ( (v10 & 0x40) != 0 )
    {
      LOWORD(v19) = 0;
      FormatRRASErrorString(
        &v19,
        L"StartRouter: Called for TransportId %d which is not supported by this router manager.",
        a5);
      goto LABEL_16;
    }
    return 87;
  }
  if ( !(unsigned int)ValidateRouterInfoBlock(a3, a4) )
  {
    if ( (v10 & 0x40) != 0 )
    {
      LOWORD(v19) = 0;
      FormatRRASErrorString(
        &v19,
        L"StartRouter: Validation Failed for Global Info for transport %d. Info size %d",
        a5,
        a4);
LABEL_16:
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v19);
    }
    return 87;
  }
  if ( v10 < 0 )
  {
    LOWORD(v19) = 0;
    v12 = L"IPv4";
    if ( a5 != 33 )
      v12 = L"IPv6";
    FormatRRASErrorString(&v19, L"StartRouter: Called for TransportId %ws", v12);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v19);
  }
  if ( !g_fRouterManagerInitialized )
  {
    started = StartRouterCommon(a1, a2, a3, a5);
    v14 = started;
    if ( started )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v19) = 0;
        FormatRRASErrorString(&v19, L"StartRouterCommon failed with error %d.", started);
        goto LABEL_28;
      }
      return v14;
    }
    g_fRouterManagerInitialized = 1;
    v8 = 1;
  }
  if ( a5 == 33 )
  {
    v15 = StartRouterV4(a1, a3);
    v16 = g_dwLoadedTransports | 1;
  }
  else
  {
    v15 = StartRouterV6(a1, a3);
    v16 = g_dwLoadedTransports | 2;
  }
  g_dwLoadedTransports = v16;
  v14 = v15;
  if ( v15 )
  {
    if ( fWorkerThreadCreated )
    {
      if ( a5 == 33 )
      {
        SetEvent(g_hStopRouterEvent);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
          goto LABEL_48;
        v17 = L"STOP Event for v4 is set";
      }
      else
      {
        SetEvent(g_hStopRouterEventV6);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
          goto LABEL_48;
        v17 = L"STOP Event for v6 is set";
      }
    }
    else
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Clean-up is done here as no worker thread is running");
      RouterManagerCleanup(a5);
      RouterManagerCleanup(0xFFFFFFFFLL);
      if ( !g_hOwnModule
        || (FreeLibrary(g_hOwnModule), g_hOwnModule = 0, (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL) )
      {
LABEL_48:
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          LOWORD(v19) = 0;
          FormatRRASErrorString(&v19, L"StartRouter for tranport %d failed with error %d.", a5, v14);
LABEL_28:
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v19);
        }
        return v14;
      }
      v17 = L"Worker Thread is not running so Iprtrmgr freed in this context";
    }
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, v17);
    goto LABEL_48;
  }
  if ( v8 )
  {
    if ( (unsigned int)CreateRouterWorkerThread(a3) )
    {
      RouterManagerCleanup(a5);
      RouterManagerCleanup(0xFFFFFFFFLL);
      if ( g_hOwnModule )
      {
        FreeLibrary(g_hOwnModule);
        g_hOwnModule = 0;
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasRtrMgrTraceError,
            L"Worker Thread Creation failed , so it should be freed here also");
      }
    }
    else
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Worker thread is created");
      fWorkerThreadCreated = 1;
    }
  }
  if ( !a2 && *(_DWORD *)(a1 + 272) && !g_fLuidCleanupDone )
  {
    v18 = (HANDLE)g_hWanarpWriteV6;
    if ( a5 == 33 )
      v18 = g_hWanarpWrite;
    CleanupLuids(v18);
    g_fLuidCleanupDone = 1;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v19) = 0;
    FormatRRASErrorString(&v19, L"StartRouter: LAN MODE = %d", (unsigned int)RouterRoleLanOnly);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v19);
  }
  return 0;
}

```

## disassembly

```asm
0x18002a4f0  push    rbx
0x18002a4f2  push    rsi
0x18002a4f3  push    rdi
0x18002a4f4  push    r12
0x18002a4f6  push    r13
0x18002a4f8  push    r14
0x18002a4fa  push    r15
0x18002a4fc  sub     rsp, 850h
0x18002a503  mov     rax, cs:__security_cookie
0x18002a50a  xor     rax, rsp
0x18002a50d  mov     [rsp+888h+var_48], rax
0x18002a515  mov     r14, r8
0x18002a518  mov     r13d, edx
0x18002a51b  mov     r12, rcx
0x18002a51e  xor     r15d, r15d
0x18002a521  xor     edx, edx; Val
0x18002a523  mov     [rsp+888h+var_848], r15d
0x18002a528  mov     r8d, 7FCh; Size
0x18002a52e  lea     rcx, [rsp+888h+var_844]; void *
0x18002a533  mov     esi, r9d
0x18002a536  call    memset_0
0x18002a53b  xor     edx, edx; dwFlags
0x18002a53d  lea     rcx, szSource; "IPRouterManager"
0x18002a544  call    cs:__imp_TraceRegisterExA
0x18002a54a  cmp     cs:g_hLogHandle, r15
0x18002a551  mov     cs:TraceHandle, eax
0x18002a557  jnz     short loc_18002A56D
0x18002a559  lea     rcx, szSource; "IPRouterManager"
0x18002a560  call    cs:__imp_RouterLogRegisterA
0x18002a566  mov     cs:g_hLogHandle, rax
0x18002a56d  mov     rbx, cs:Microsoft_Windows_RRASEnableBits
0x18002a574  test    bl, bl
0x18002a576  jns     short loc_18002A5C0
0x18002a578  lea     r8, aStartrouter_0; "StartRouter"
0x18002a57f  mov     word ptr [rsp+888h+var_848], r15w
0x18002a585  lea     rdx, aEnteredWs; "Entered: %ws"
0x18002a58c  lea     rcx, [rsp+888h+var_848]
0x18002a591  call    FormatRRASErrorString
0x18002a596  mov     rbx, cs:Microsoft_Windows_RRASEnableBits
0x18002a59d  test    bl, bl
0x18002a59f  jns     short loc_18002A5C0
0x18002a5a1  lea     r8, [rsp+888h+var_848]
0x18002a5a6  lea     rdx, RasRtrmgrTraceInfo
0x18002a5ad  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002a5b4  call    McTemplateU0z_EventWriteTransfer
0x18002a5b9  mov     rbx, cs:Microsoft_Windows_RRASEnableBits
0x18002a5c0  test    r14, r14
0x18002a5c3  jnz     short loc_18002A5FF
0x18002a5c5  lea     ebx, [r14+1]
0x18002a5c9  cmp     cs:g_dwLoggingLevel, ebx
0x18002a5cf  jb      loc_18002A682
0x18002a5d5  mov     rcx, cs:g_hLogHandle; hLogHandle
0x18002a5dc  xor     r9d, r9d; dwSubStringCount
0x18002a5df  mov     [rsp+888h+dwErrorCode], 0E8h; dwErrorCode
0x18002a5e7  mov     r8d, 4EB5h; dwMessageId
0x18002a5ed  mov     edx, ebx; dwEventType
0x18002a5ef  mov     [rsp+888h+plpszSubStringArray], r15; plpszSubStringArray
0x18002a5f4  call    cs:__imp_RouterLogEventA
0x18002a5fa  jmp     loc_18002A682
0x18002a5ff  mov     edi, [rsp+888h+arg_20]
0x18002a606  cmp     edi, 21h ; '!'
0x18002a609  jz      short loc_18002A631
0x18002a60b  cmp     edi, 57h ; 'W'
0x18002a60e  jz      short loc_18002A631
0x18002a610  test    bl, 40h
0x18002a613  jz      short loc_18002A682
0x18002a615  mov     r8d, edi
0x18002a618  mov     word ptr [rsp+888h+var_848], r15w
0x18002a61e  lea     rdx, aStartrouterCal_0; "StartRouter: Called for TransportId %d "...
0x18002a625  lea     rcx, [rsp+888h+var_848]
0x18002a62a  call    FormatRRASErrorString
0x18002a62f  jmp     short loc_18002A661
0x18002a631  mov     edx, esi
0x18002a633  mov     rcx, r14
0x18002a636  call    ValidateRouterInfoBlock
0x18002a63b  test    eax, eax
0x18002a63d  jnz     short loc_18002A68C
0x18002a63f  test    bl, 40h
0x18002a642  jz      short loc_18002A682
0x18002a644  mov     r9d, esi
0x18002a647  mov     word ptr [rsp+888h+var_848], r15w
0x18002a64d  mov     r8d, edi
0x18002a650  lea     rdx, aStartrouterVal; "StartRouter: Validation Failed for Glob"...
0x18002a657  lea     rcx, [rsp+888h+var_848]
0x18002a65c  call    FormatRRASErrorString
0x18002a661  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002a668  jz      short loc_18002A682
0x18002a66a  lea     r8, [rsp+888h+var_848]
0x18002a66f  lea     rdx, RasRtrMgrTraceError
0x18002a676  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002a67d  call    McTemplateU0z_EventWriteTransfer
0x18002a682  mov     eax, 57h ; 'W'
0x18002a687  jmp     loc_18002A987
0x18002a68c  test    bl, bl
0x18002a68e  jns     short loc_18002A6DD
0x18002a690  lea     rax, aIpv6; "IPv6"
0x18002a697  mov     word ptr [rsp+888h+var_848], r15w
0x18002a69d  cmp     edi, 21h ; '!'
0x18002a6a0  lea     r8, aIpv4_0; "IPv4"
0x18002a6a7  lea     rdx, aStartrouterCal; "StartRouter: Called for TransportId %ws"
0x18002a6ae  cmovnz  r8, rax
0x18002a6b2  lea     rcx, [rsp+888h+var_848]
0x18002a6b7  call    FormatRRASErrorString
0x18002a6bc  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18002a6c3  jge     short loc_18002A6DD
0x18002a6c5  lea     r8, [rsp+888h+var_848]
0x18002a6ca  lea     rdx, RasRtrmgrTraceInfo
0x18002a6d1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002a6d8  call    McTemplateU0z_EventWriteTransfer
0x18002a6dd  cmp     cs:g_fRouterManagerInitialized, r15d
0x18002a6e4  mov     ebx, 1
0x18002a6e9  jnz     short loc_18002A757
0x18002a6eb  mov     r9d, edi
0x18002a6ee  mov     r8, r14
0x18002a6f1  mov     edx, r13d
0x18002a6f4  mov     rcx, r12
0x18002a6f7  call    StartRouterCommon
0x18002a6fc  mov     esi, eax
0x18002a6fe  test    eax, eax
0x18002a700  jz      short loc_18002A74E
0x18002a702  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002a709  jz      short loc_18002A747
0x18002a70b  xor     ecx, ecx
0x18002a70d  lea     rdx, aStartroutercom; "StartRouterCommon failed with error %d."
0x18002a714  mov     word ptr [rsp+888h+var_848], cx
0x18002a719  mov     r8d, eax
0x18002a71c  lea     rcx, [rsp+888h+var_848]
0x18002a721  call    FormatRRASErrorString
0x18002a726  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002a72d  jz      short loc_18002A747
0x18002a72f  lea     r8, [rsp+888h+var_848]
0x18002a734  lea     rdx, RasRtrMgrTraceError
0x18002a73b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002a742  call    McTemplateU0z_EventWriteTransfer
0x18002a747  mov     eax, esi
0x18002a749  jmp     loc_18002A987
0x18002a74e  mov     cs:g_fRouterManagerInitialized, ebx
0x18002a754  mov     r15d, ebx
0x18002a757  mov     rdx, r14
0x18002a75a  mov     rcx, r12
0x18002a75d  cmp     edi, 21h ; '!'
0x18002a760  jnz     short loc_18002A771
0x18002a762  call    StartRouterV4
0x18002a767  mov     ecx, cs:g_dwLoadedTransports
0x18002a76d  or      ecx, ebx
0x18002a76f  jmp     short loc_18002A77F
0x18002a771  call    StartRouterV6
0x18002a776  mov     ecx, cs:g_dwLoadedTransports
0x18002a77c  or      ecx, 2
0x18002a77f  mov     cs:g_dwLoadedTransports, ecx
0x18002a785  mov     esi, eax
0x18002a787  test    eax, eax
0x18002a789  jz      loc_18002A87D
0x18002a78f  cmp     cs:fWorkerThreadCreated, 0
0x18002a796  jnz     short loc_18002A7F9
0x18002a798  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18002a79f  jz      short loc_18002A7BB
0x18002a7a1  lea     r8, aCleanUpIsDoneH; "Clean-up is done here as no worker thre"...
0x18002a7a8  lea     rdx, RasRtrmgrTraceInfo
0x18002a7af  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002a7b6  call    McTemplateU0z_EventWriteTransfer
0x18002a7bb  mov     ecx, edi
0x18002a7bd  call    RouterManagerCleanup
0x18002a7c2  or      ecx, 0FFFFFFFFh
0x18002a7c5  call    RouterManagerCleanup
0x18002a7ca  mov     rcx, cs:g_hOwnModule; hLibModule
0x18002a7d1  test    rcx, rcx
0x18002a7d4  jz      short loc_18002A84D
0x18002a7d6  call    cs:__imp_FreeLibrary
0x18002a7dc  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18002a7e3  mov     cs:g_hOwnModule, 0
0x18002a7ee  jz      short loc_18002A84D
0x18002a7f0  lea     r8, aWorkerThreadIs_0; "Worker Thread is not running so Iprtrmg"...
0x18002a7f7  jmp     short loc_18002A83A
0x18002a7f9  cmp     edi, 21h ; '!'
0x18002a7fc  jnz     short loc_18002A81D
0x18002a7fe  mov     rcx, cs:g_hStopRouterEvent; hEvent
0x18002a805  call    cs:__imp_SetEvent
0x18002a80b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18002a812  jz      short loc_18002A84D
0x18002a814  lea     r8, aStopEventForV4; "STOP Event for v4 is set"
0x18002a81b  jmp     short loc_18002A83A
0x18002a81d  mov     rcx, cs:g_hStopRouterEventV6; hEvent
0x18002a824  call    cs:__imp_SetEvent
0x18002a82a  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18002a831  jz      short loc_18002A84D
0x18002a833  lea     r8, aStopEventForV6; "STOP Event for v6 is set"
0x18002a83a  lea     rdx, RasRtrmgrTraceInfo
0x18002a841  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002a848  call    McTemplateU0z_EventWriteTransfer
0x18002a84d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002a854  jz      loc_18002A747
0x18002a85a  xor     eax, eax
0x18002a85c  lea     rdx, aStartrouterFor; "StartRouter for tranport %d failed with"...
0x18002a863  mov     r9d, esi
0x18002a866  mov     word ptr [rsp+888h+var_848], ax
0x18002a86b  mov     r8d, edi
0x18002a86e  lea     rcx, [rsp+888h+var_848]
0x18002a873  call    FormatRRASErrorString
0x18002a878  jmp     loc_18002A726
0x18002a87d  xor     esi, esi
0x18002a87f  test    r15d, r15d
0x18002a882  jz      loc_18002A90A
0x18002a888  mov     rcx, r14; lpParameter
0x18002a88b  call    CreateRouterWorkerThread
0x18002a890  test    eax, eax
0x18002a892  jz      short loc_18002A8E1
0x18002a894  mov     ecx, edi
0x18002a896  call    RouterManagerCleanup
0x18002a89b  or      ecx, 0FFFFFFFFh
0x18002a89e  call    RouterManagerCleanup
0x18002a8a3  mov     rcx, cs:g_hOwnModule; hLibModule
0x18002a8aa  test    rcx, rcx
0x18002a8ad  jz      short loc_18002A90A
0x18002a8af  call    cs:__imp_FreeLibrary
0x18002a8b5  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002a8bc  mov     cs:g_hOwnModule, rsi
0x18002a8c3  jz      short loc_18002A90A
0x18002a8c5  lea     r8, aWorkerThreadCr; "Worker Thread Creation failed , so it s"...
0x18002a8cc  lea     rdx, RasRtrMgrTraceError
0x18002a8d3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002a8da  call    McTemplateU0z_EventWriteTransfer
0x18002a8df  jmp     short loc_18002A90A
0x18002a8e1  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18002a8e8  jz      short loc_18002A904
0x18002a8ea  lea     r8, aWorkerThreadIs; "Worker thread is created"
0x18002a8f1  lea     rdx, RasRtrmgrTraceInfo
0x18002a8f8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002a8ff  call    McTemplateU0z_EventWriteTransfer
0x18002a904  mov     cs:fWorkerThreadCreated, ebx
0x18002a90a  test    r13d, r13d
0x18002a90d  jnz     short loc_18002A93E
0x18002a90f  cmp     [r12+110h], esi
0x18002a917  jz      short loc_18002A93E
0x18002a919  cmp     cs:g_fLuidCleanupDone, esi
0x18002a91f  jnz     short loc_18002A93E
0x18002a921  mov     rcx, cs:g_hWanarpWriteV6
0x18002a928  cmp     edi, 21h ; '!'
0x18002a92b  cmovz   rcx, cs:g_hWanarpWrite; hDevice
0x18002a933  call    CleanupLuids
0x18002a938  mov     cs:g_fLuidCleanupDone, ebx
0x18002a93e  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x18002a945  jge     short loc_18002A985
0x18002a947  mov     r8d, cs:RouterRoleLanOnly
0x18002a94e  lea     rdx, aStartrouterLan; "StartRouter: LAN MODE = %d"
0x18002a955  lea     rcx, [rsp+888h+var_848]
0x18002a95a  mov     word ptr [rsp+888h+var_848], si
0x18002a95f  call    FormatRRASErrorString
0x18002a964  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x18002a96b  jge     short loc_18002A985
0x18002a96d  lea     r8, [rsp+888h+var_848]
0x18002a972  lea     rdx, RasRtrmgrTraceInfo
0x18002a979  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002a980  call    McTemplateU0z_EventWriteTransfer
0x18002a985  xor     eax, eax
0x18002a987  mov     rcx, [rsp+888h+var_48]
0x18002a98f  xor     rcx, rsp; StackCookie
0x18002a992  call    __security_check_cookie
0x18002a997  add     rsp, 850h
0x18002a99e  pop     r15
0x18002a9a0  pop     r14
0x18002a9a2  pop     r13
0x18002a9a4  pop     r12
0x18002a9a6  pop     rdi
0x18002a9a7  pop     rsi
0x18002a9a8  pop     rbx
0x18002a9a9  retn
```

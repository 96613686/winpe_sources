# InitRouter

- ea: `0x18001fbc8`
- end: `0x18002022f`
- name: `InitRouter`
- size: `1639`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a9b0`

## callees

- `0x18000ac60`
- `0x18001e490`
- `0x18001fbc8`
- `0x18002ef0c`
- `0x1800525f0`
- `0x180053f50`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlInitializeResource` at `0x18001fca4`
- `ntdll!RtlInitializeResource` at `0x18001fca4`
- `ntdll!RtlDeleteResource` at `0x180020200`
- `ntdll!RtlDeleteResource` at `0x180020200`
- `KERNEL32!CreateWaitableTimerA` at `0x18001ffc0`
- `KERNEL32!CreateWaitableTimerA` at `0x18001ffd4`
- `KERNEL32!CreateWaitableTimerA` at `0x18001ffe8`
- `KERNEL32!CreateWaitableTimerA` at `0x18001ffc0`
- `KERNEL32!CreateWaitableTimerA` at `0x18001ffd4`
- `KERNEL32!CreateWaitableTimerA` at `0x18001ffe8`
- `KERNEL32!CreateEventA` at `0x18001fe81`
- `KERNEL32!CreateEventA` at `0x18001fe98`
- `KERNEL32!CreateEventA` at `0x18001feaf`
- `KERNEL32!CreateEventA` at `0x18001fec6`
- `KERNEL32!CreateEventA` at `0x18001fedd`
- `KERNEL32!CreateEventA` at `0x18001fef4`
- `KERNEL32!CreateEventA` at `0x18001ff0b`
- `KERNEL32!CreateEventA` at `0x18001ff22`
- `KERNEL32!CreateEventA` at `0x18001ff39`
- `KERNEL32!CreateEventA` at `0x18001ff50`
- `KERNEL32!CreateEventA` at `0x18001ff67`
- `KERNEL32!CreateEventA` at `0x18001ff7e`
- `KERNEL32!CreateEventA` at `0x18001ff95`
- `KERNEL32!CreateEventA` at `0x18001ffac`
- `KERNEL32!CreateEventA` at `0x18001fe81`
- `KERNEL32!CreateEventA` at `0x18001fe98`
- `KERNEL32!CreateEventA` at `0x18001feaf`
- `KERNEL32!CreateEventA` at `0x18001fec6`
- `KERNEL32!CreateEventA` at `0x18001fedd`
- `KERNEL32!CreateEventA` at `0x18001fef4`
- `KERNEL32!CreateEventA` at `0x18001ff0b`
- `KERNEL32!CreateEventA` at `0x18001ff22`
- `KERNEL32!CreateEventA` at `0x18001ff39`
- `KERNEL32!CreateEventA` at `0x18001ff50`
- `KERNEL32!CreateEventA` at `0x18001ff67`
- `KERNEL32!CreateEventA` at `0x18001ff7e`
- `KERNEL32!CreateEventA` at `0x18001ff95`
- `KERNEL32!CreateEventA` at `0x18001ffac`
- `KERNEL32!HeapCreate` at `0x18001fdf3`
- `KERNEL32!HeapCreate` at `0x18001fdf3`
- `KERNEL32!GetLastError` at `0x18001fe05`
- `KERNEL32!GetLastError` at `0x18001fe05`
- `rtutils!RouterLogEventA` at `0x180020156`
- `rtutils!RouterLogEventA` at `0x180020156`

## string_xrefs

- `0x180020123`: `InitRouter: Couldnt create the needed events and timer`
- `0x1800200be`: `InitRouter: Created necessary events and timer`
- `0x1800200ea`: `InitRouter: InitializeThreadPool for demand dial failed with error %d`

## pseudocode

```c
__int64 __fastcall InitRouter(__int64 a1, int a2)
{
  unsigned int i; // esi
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 PointerToTocEntry; // rax
  __int64 v9; // rcx
  __int64 v10; // r8
  unsigned int v11; // eax
  InterfaceContainer *v12; // rcx
  DWORD LastError; // esi
  char v14; // cl
  const wchar_t *v15; // rdx
  const wchar_t *v17; // r8
  int v18; // [rsp+40h] [rbp-848h] BYREF
  _BYTE v19[2044]; // [rsp+44h] [rbp-844h] BYREF

  v18 = 0;
  memset_0(v19, 0, sizeof(v19));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v18) = 0;
    FormatRRASErrorString(&v18, L"Entered: %ws", L"InitRouter");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v18);
  }
  g_hIpDevice = 0;
  g_hIpRouteChangeDevice = 0;
  g_hMcastDevice = 0;
  for ( i = 0; i < 0xF; ++i )
    RtlInitializeResource(&g_LockTable + i);
  lpMem = &ICBList;
  ICBList = (__int64)&ICBList;
  qword_18008DB78 = (__int64)&g_leProtoCbListV4;
  g_leProtoCbListV4 = &g_leProtoCbListV4;
  qword_18008EA18 = (__int64)&g_leProtoCbListV6;
  g_leProtoCbListV6 = (__int64)&g_leProtoCbListV6;
  v5 = 0;
  v6 = 0;
  do
  {
    ICBHashLookup[v6 + 1] = (__int64)&ICBHashLookup[v6];
    ICBHashLookup[v6] = (__int64)&ICBHashLookup[v6];
    qword_18008DBE8[v6] = (__int64)&ICBSeqNumLookup[v6];
    ICBSeqNumLookup[v6] = (__int64)&ICBSeqNumLookup[v6];
    ++v5;
    v6 += 2;
  }
  while ( v5 != 57 );
  InitHashTables(v6 * 8, 57, 0x180000000uLL);
  qword_18008EA38 = (__int64)&g_leTimerQueueHead;
  g_leTimerQueueHead = (__int64)&g_leTimerQueueHead;
  v7 = 4294901763LL;
  if ( a2 != 33 )
    v7 = 4294901775LL;
  PointerToTocEntry = GetPointerToTocEntry(v7, a1);
  if ( !PointerToTocEntry || !*(_DWORD *)(PointerToTocEntry + 4) )
    goto LABEL_55;
  v9 = *(unsigned int *)(PointerToTocEntry + 12);
  v10 = a1 + v9;
  if ( (unsigned int)v9 >= *(_DWORD *)(a1 + 4) )
    v10 = 0;
  if ( !v10 )
  {
LABEL_55:
    if ( g_dwLoggingLevel )
      RouterLogEventA(g_hLogHandle, 1u, 0x4EB5u, 0, 0, 0xE8u);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return 1003;
    v17 = L"InitRouter: No Global Info - can not start router";
    goto LABEL_59;
  }
  v11 = *(_DWORD *)(v10 + 4);
  if ( v11 > 3 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v18) = 0;
      FormatRRASErrorString(
        &v18,
        L"InitRouter: Global info has invalid logging level of %d",
        *(unsigned int *)(v10 + 4));
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v18);
    }
    v11 = 3;
  }
  g_dwLoggingLevel = v11;
  g_hNsiRPCHandle = 0;
  IPRouterHeap = HeapCreate(0, 0, 0);
  if ( !IPRouterHeap )
  {
    LastError = GetLastError();
    v14 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v15 = L"InitRouter: Error %d creating IPRouterHeap";
      goto LABEL_24;
    }
    goto LABEL_26;
  }
  InterfaceContainer::InitInterfaceContainer(v12);
  g_hRoutingProtocolEvent = CreateEventA(0, 0, 0, 0);
  g_hRoutingProtocolEventV6 = CreateEventA(0, 0, 0, 0);
  g_hStopRouterEvent = CreateEventA(0, 0, 0, 0);
  g_hStopRouterEventV6 = CreateEventA(0, 0, 0, 0);
  g_hSetForwardingEventV4 = CreateEventA(0, 0, 0, 0);
  g_hSetForwardingEventV6 = CreateEventA(0, 0, 0, 0);
  g_hForwardingChangeEvent = CreateEventA(0, 0, 0, 0);
  g_hDemandDialEvent = CreateEventA(0, 0, 0, 0);
  g_hDemandDialEventV6 = CreateEventA(0, 0, 0, 0);
  g_hStackChangeEvent = CreateEventA(0, 0, 0, 0);
  g_hRtrDiscSocketEvent = CreateEventA(0, 0, 0, 0);
  g_hMHbeatSocketEvent = CreateEventA(0, 0, 0, 0);
  g_hMcMiscSocketEvent = CreateEventA(0, 0, 0, 0);
  g_hMzapSocketEvent = CreateEventA(0, 0, 0, 0);
  g_hRtrDiscTimer = CreateWaitableTimerA(0, 0, 0);
  g_hRasAdvTimer = CreateWaitableTimerA(0, 0, 0);
  g_hMzapTimer = CreateWaitableTimerA(0, 0, 0);
  if ( !g_hRoutingProtocolEvent
    || !g_hRoutingProtocolEventV6
    || !g_hStopRouterEvent
    || !g_hStopRouterEventV6
    || !g_hSetForwardingEventV4
    || !g_hSetForwardingEventV6
    || !g_hForwardingChangeEvent
    || !g_hDemandDialEvent
    || !g_hDemandDialEventV6
    || !g_hStackChangeEvent
    || !g_hRtrDiscSocketEvent
    || !g_hRtrDiscTimer
    || !g_hRasAdvTimer
    || !g_hMcMiscSocketEvent
    || !g_hMzapSocketEvent
    || !g_hMHbeatSocketEvent )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return 1003;
    v17 = L"InitRouter: Couldnt create the needed events and timer";
LABEL_59:
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, v17);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: InitRouter");
    return 1003;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"InitRouter: Created necessary events and timer");
  LastError = InitializeThreadPool();
  if ( LastError )
  {
    v14 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v15 = L"InitRouter: InitializeThreadPool for demand dial failed with error %d";
LABEL_24:
      LOWORD(v18) = 0;
      FormatRRASErrorString(&v18, v15, LastError);
      v14 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v18);
        v14 = Microsoft_Windows_RRASEnableBits;
      }
    }
LABEL_26:
    if ( v14 < 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: InitRouter");
    return LastError;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"Leaving: InitRouter");
  return 0;
}

```

## disassembly

```asm
0x18001fbc8  push    rbx
0x18001fbca  push    rsi
0x18001fbcb  push    rdi
0x18001fbcc  push    r12
0x18001fbce  push    r14
0x18001fbd0  push    r15
0x18001fbd2  sub     rsp, 858h
0x18001fbd9  mov     rax, cs:__security_cookie
0x18001fbe0  xor     rax, rsp
0x18001fbe3  mov     [rsp+888h+var_48], rax
0x18001fbeb  mov     r15d, edx
0x18001fbee  mov     r14, rcx
0x18001fbf1  xor     r12d, r12d
0x18001fbf4  mov     [rsp+888h+var_848], r12d
0x18001fbf9  xor     edx, edx; Val
0x18001fbfb  mov     r8d, 7FCh; Size
0x18001fc01  lea     rcx, [rsp+888h+var_844]; void *
0x18001fc06  call    memset_0
0x18001fc0b  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18001fc12  jge     short loc_18001FC5B
0x18001fc14  mov     word ptr [rsp+888h+var_848], r12w
0x18001fc1a  lea     r8, aInitrouter; "InitRouter"
0x18001fc21  lea     rdx, aEnteredWs; "Entered: %ws"
0x18001fc28  lea     rcx, [rsp+888h+var_848]
0x18001fc2d  call    FormatRRASErrorString
0x18001fc32  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18001fc39  jge     short loc_18001FC5B
0x18001fc3b  lea     r8, [rsp+888h+var_848]
0x18001fc40  lea     rbx, RasRtrmgrTraceInfo
0x18001fc47  mov     rdx, rbx
0x18001fc4a  lea     rdi, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001fc51  mov     rcx, rdi
0x18001fc54  call    McTemplateU0z_EventWriteTransfer
0x18001fc59  jmp     short loc_18001FC69
0x18001fc5b  lea     rbx, RasRtrmgrTraceInfo
0x18001fc62  lea     rdi, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001fc69  mov     [rsp+888h+var_854], r12d
0x18001fc6e  mov     cs:g_hIpDevice, r12
0x18001fc75  mov     cs:g_hIpRouteChangeDevice, r12
0x18001fc7c  mov     cs:g_hMcastDevice, r12
0x18001fc83  mov     esi, r12d
0x18001fc86  mov     [rsp+888h+var_854], r12d
0x18001fc8b  cmp     esi, 0Fh
0x18001fc8e  jnb     short loc_18001FCB2
0x18001fc90  mov     eax, esi
0x18001fc92  lea     rcx, [rax+rax*2]
0x18001fc96  shl     rcx, 5
0x18001fc9a  lea     rax, g_LockTable
0x18001fca1  add     rcx, rax; Resource
0x18001fca4  call    cs:__imp_RtlInitializeResource
0x18001fcaa  inc     esi
0x18001fcac  mov     [rsp+888h+var_854], esi
0x18001fcb0  jmp     short loc_18001FC8B
0x18001fcb2  lea     rax, ICBList
0x18001fcb9  mov     cs:lpMem, rax
0x18001fcc0  mov     cs:ICBList, rax
0x18001fcc7  lea     rax, g_leProtoCbListV4
0x18001fcce  mov     cs:qword_18008DB78, rax
0x18001fcd5  mov     cs:g_leProtoCbListV4, rax
0x18001fcdc  lea     rax, g_leProtoCbListV6
0x18001fce3  mov     cs:qword_18008EA18, rax
0x18001fcea  mov     cs:g_leProtoCbListV6, rax
0x18001fcf1  mov     rdx, r12
0x18001fcf4  mov     rcx, r12
0x18001fcf7  lea     r8, cs:180000000h
0x18001fcfe  lea     rax, rva ICBHashLookup[r8]
0x18001fd05  add     rax, rcx
0x18001fd08  mov     [rcx+r8+8EAC8h], rax
0x18001fd10  mov     [rax], rax
0x18001fd13  lea     rax, rva ICBSeqNumLookup[r8]
0x18001fd1a  add     rax, rcx
0x18001fd1d  mov     [rcx+r8+8DBE8h], rax
0x18001fd25  mov     [rax], rax
0x18001fd28  inc     rdx
0x18001fd2b  add     rcx, 10h
0x18001fd2f  cmp     rdx, 39h ; '9'
0x18001fd33  jnz     short loc_18001FCFE
0x18001fd35  call    InitHashTables
0x18001fd3a  lea     rax, g_leTimerQueueHead
0x18001fd41  mov     cs:qword_18008EA38, rax
0x18001fd48  mov     cs:g_leTimerQueueHead, rax
0x18001fd4f  mov     ecx, 0FFFF0003h
0x18001fd54  mov     eax, 0FFFF000Fh
0x18001fd59  cmp     r15d, 21h ; '!'
0x18001fd5d  cmovnz  ecx, eax
0x18001fd60  mov     rdx, r14
0x18001fd63  call    GetPointerToTocEntry
0x18001fd68  test    rax, rax
0x18001fd6b  jz      loc_18002012C
0x18001fd71  cmp     [rax+4], r12d
0x18001fd75  jz      loc_18002012C
0x18001fd7b  mov     ecx, [rax+0Ch]
0x18001fd7e  cmp     ecx, [r14+4]
0x18001fd82  lea     r8, [r14+rcx]
0x18001fd86  jb      short loc_18001FD8B
0x18001fd88  mov     r8, r12
0x18001fd8b  test    r8, r8
0x18001fd8e  jz      loc_18002012C
0x18001fd94  mov     eax, [r8+4]
0x18001fd98  cmp     eax, 3
0x18001fd9b  jbe     short loc_18001FDDF
0x18001fd9d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18001fda4  jge     short loc_18001FDDA
0x18001fda6  mov     word ptr [rsp+888h+var_848], r12w
0x18001fdac  mov     r8d, [r8+4]
0x18001fdb0  lea     rdx, aInitrouterGlob; "InitRouter: Global info has invalid log"...
0x18001fdb7  lea     rcx, [rsp+888h+var_848]
0x18001fdbc  call    FormatRRASErrorString
0x18001fdc1  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18001fdc8  jge     short loc_18001FDDA
0x18001fdca  lea     r8, [rsp+888h+var_848]
0x18001fdcf  mov     rdx, rbx
0x18001fdd2  mov     rcx, rdi
0x18001fdd5  call    McTemplateU0z_EventWriteTransfer
0x18001fdda  mov     eax, 3
0x18001fddf  mov     cs:g_dwLoggingLevel, eax
0x18001fde5  mov     cs:g_hNsiRPCHandle, r12
0x18001fdec  xor     r8d, r8d; dwMaximumSize
0x18001fdef  xor     edx, edx; dwInitialSize
0x18001fdf1  xor     ecx, ecx; flOptions
0x18001fdf3  call    cs:__imp_HeapCreate
0x18001fdf9  mov     cs:IPRouterHeap, rax
0x18001fe00  test    rax, rax
0x18001fe03  jnz     short loc_18001FE72
0x18001fe05  call    cs:__imp_GetLastError
0x18001fe0b  mov     esi, eax
0x18001fe0d  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18001fe14  test    cl, cl
0x18001fe16  jns     short loc_18001FE54
0x18001fe18  lea     rdx, aInitrouterErro; "InitRouter: Error %d creating IPRouterH"...
0x18001fe1f  mov     word ptr [rsp+888h+var_848], r12w
0x18001fe25  mov     r8d, esi
0x18001fe28  lea     rcx, [rsp+888h+var_848]
0x18001fe2d  call    FormatRRASErrorString
0x18001fe32  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18001fe39  test    cl, cl
0x18001fe3b  jns     short loc_18001FE54
0x18001fe3d  lea     r8, [rsp+888h+var_848]
0x18001fe42  mov     rdx, rbx
0x18001fe45  mov     rcx, rdi
0x18001fe48  call    McTemplateU0z_EventWriteTransfer
0x18001fe4d  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18001fe54  test    cl, 80h
0x18001fe57  jz      short loc_18001FE6B
0x18001fe59  lea     r8, aLeavingInitrou_0; "Leaving: InitRouter"
0x18001fe60  mov     rdx, rbx
0x18001fe63  mov     rcx, rdi
0x18001fe66  call    McTemplateU0z_EventWriteTransfer
0x18001fe6b  mov     eax, esi
0x18001fe6d  jmp     loc_18002020E
0x18001fe72  call    ?InitInterfaceContainer@InterfaceContainer@@QEAAXXZ; InterfaceContainer::InitInterfaceContainer(void)
0x18001fe77  xor     r9d, r9d; lpName
0x18001fe7a  xor     r8d, r8d; bInitialState
0x18001fe7d  xor     edx, edx; bManualReset
0x18001fe7f  xor     ecx, ecx; lpEventAttributes
0x18001fe81  call    cs:__imp_CreateEventA
0x18001fe87  mov     cs:g_hRoutingProtocolEvent, rax
0x18001fe8e  xor     r9d, r9d; lpName
0x18001fe91  xor     r8d, r8d; bInitialState
0x18001fe94  xor     edx, edx; bManualReset
0x18001fe96  xor     ecx, ecx; lpEventAttributes
0x18001fe98  call    cs:__imp_CreateEventA
0x18001fe9e  mov     cs:g_hRoutingProtocolEventV6, rax
0x18001fea5  xor     r9d, r9d; lpName
0x18001fea8  xor     r8d, r8d; bInitialState
0x18001feab  xor     edx, edx; bManualReset
0x18001fead  xor     ecx, ecx; lpEventAttributes
0x18001feaf  call    cs:__imp_CreateEventA
0x18001feb5  mov     cs:g_hStopRouterEvent, rax
0x18001febc  xor     r9d, r9d; lpName
0x18001febf  xor     r8d, r8d; bInitialState
0x18001fec2  xor     edx, edx; bManualReset
0x18001fec4  xor     ecx, ecx; lpEventAttributes
0x18001fec6  call    cs:__imp_CreateEventA
0x18001fecc  mov     cs:g_hStopRouterEventV6, rax
0x18001fed3  xor     r9d, r9d; lpName
0x18001fed6  xor     r8d, r8d; bInitialState
0x18001fed9  xor     edx, edx; bManualReset
0x18001fedb  xor     ecx, ecx; lpEventAttributes
0x18001fedd  call    cs:__imp_CreateEventA
0x18001fee3  mov     cs:g_hSetForwardingEventV4, rax
0x18001feea  xor     r9d, r9d; lpName
0x18001feed  xor     r8d, r8d; bInitialState
0x18001fef0  xor     edx, edx; bManualReset
0x18001fef2  xor     ecx, ecx; lpEventAttributes
0x18001fef4  call    cs:__imp_CreateEventA
0x18001fefa  mov     cs:g_hSetForwardingEventV6, rax
0x18001ff01  xor     r9d, r9d; lpName
0x18001ff04  xor     r8d, r8d; bInitialState
0x18001ff07  xor     edx, edx; bManualReset
0x18001ff09  xor     ecx, ecx; lpEventAttributes
0x18001ff0b  call    cs:__imp_CreateEventA
0x18001ff11  mov     cs:g_hForwardingChangeEvent, rax
0x18001ff18  xor     r9d, r9d; lpName
0x18001ff1b  xor     r8d, r8d; bInitialState
0x18001ff1e  xor     edx, edx; bManualReset
0x18001ff20  xor     ecx, ecx; lpEventAttributes
0x18001ff22  call    cs:__imp_CreateEventA
0x18001ff28  mov     cs:g_hDemandDialEvent, rax
0x18001ff2f  xor     r9d, r9d; lpName
0x18001ff32  xor     r8d, r8d; bInitialState
0x18001ff35  xor     edx, edx; bManualReset
0x18001ff37  xor     ecx, ecx; lpEventAttributes
0x18001ff39  call    cs:__imp_CreateEventA
0x18001ff3f  mov     cs:g_hDemandDialEventV6, rax
0x18001ff46  xor     r9d, r9d; lpName
0x18001ff49  xor     r8d, r8d; bInitialState
0x18001ff4c  xor     edx, edx; bManualReset
0x18001ff4e  xor     ecx, ecx; lpEventAttributes
0x18001ff50  call    cs:__imp_CreateEventA
0x18001ff56  mov     cs:g_hStackChangeEvent, rax
0x18001ff5d  xor     r9d, r9d; lpName
0x18001ff60  xor     r8d, r8d; bInitialState
0x18001ff63  xor     edx, edx; bManualReset
0x18001ff65  xor     ecx, ecx; lpEventAttributes
0x18001ff67  call    cs:__imp_CreateEventA
0x18001ff6d  mov     cs:g_hRtrDiscSocketEvent, rax
0x18001ff74  xor     r9d, r9d; lpName
0x18001ff77  xor     r8d, r8d; bInitialState
0x18001ff7a  xor     edx, edx; bManualReset
0x18001ff7c  xor     ecx, ecx; lpEventAttributes
0x18001ff7e  call    cs:__imp_CreateEventA
0x18001ff84  mov     cs:g_hMHbeatSocketEvent, rax
0x18001ff8b  xor     r9d, r9d; lpName
0x18001ff8e  xor     r8d, r8d; bInitialState
0x18001ff91  xor     edx, edx; bManualReset
0x18001ff93  xor     ecx, ecx; lpEventAttributes
0x18001ff95  call    cs:__imp_CreateEventA
0x18001ff9b  mov     cs:g_hMcMiscSocketEvent, rax
0x18001ffa2  xor     r9d, r9d; lpName
0x18001ffa5  xor     r8d, r8d; bInitialState
0x18001ffa8  xor     edx, edx; bManualReset
0x18001ffaa  xor     ecx, ecx; lpEventAttributes
0x18001ffac  call    cs:__imp_CreateEventA
0x18001ffb2  mov     cs:g_hMzapSocketEvent, rax
0x18001ffb9  xor     r8d, r8d; lpTimerName
0x18001ffbc  xor     edx, edx; bManualReset
0x18001ffbe  xor     ecx, ecx; lpTimerAttributes
0x18001ffc0  call    cs:__imp_CreateWaitableTimerA
0x18001ffc6  mov     cs:g_hRtrDiscTimer, rax
0x18001ffcd  xor     r8d, r8d; lpTimerName
0x18001ffd0  xor     edx, edx; bManualReset
0x18001ffd2  xor     ecx, ecx; lpTimerAttributes
0x18001ffd4  call    cs:__imp_CreateWaitableTimerA
0x18001ffda  mov     cs:g_hRasAdvTimer, rax
0x18001ffe1  xor     r8d, r8d; lpTimerName
0x18001ffe4  xor     edx, edx; bManualReset
0x18001ffe6  xor     ecx, ecx; lpTimerAttributes
0x18001ffe8  call    cs:__imp_CreateWaitableTimerA
0x18001ffee  mov     cs:g_hMzapTimer, rax
0x18001fff5  cmp     cs:g_hRoutingProtocolEvent, r12
0x18001fffc  jz      loc_180020118
0x180020002  cmp     cs:g_hRoutingProtocolEventV6, r12
0x180020009  jz      loc_180020118
0x18002000f  cmp     cs:g_hStopRouterEvent, r12
0x180020016  jz      loc_180020118
0x18002001c  cmp     cs:g_hStopRouterEventV6, r12
0x180020023  jz      loc_180020118
0x180020029  cmp     cs:g_hSetForwardingEventV4, r12
0x180020030  jz      loc_180020118
0x180020036  cmp     cs:g_hSetForwardingEventV6, r12
0x18002003d  jz      loc_180020118
0x180020043  cmp     cs:g_hForwardingChangeEvent, r12
0x18002004a  jz      loc_180020118
0x180020050  cmp     cs:g_hDemandDialEvent, r12
0x180020057  jz      loc_180020118
0x18002005d  cmp     cs:g_hDemandDialEventV6, r12
0x180020064  jz      loc_180020118
0x18002006a  cmp     cs:g_hStackChangeEvent, r12
0x180020071  jz      loc_180020118
0x180020077  cmp     cs:g_hRtrDiscSocketEvent, r12
0x18002007e  jz      loc_180020118
0x180020084  cmp     cs:g_hRtrDiscTimer, r12
0x18002008b  jz      loc_180020118
0x180020091  cmp     cs:g_hRasAdvTimer, r12
0x180020098  jz      short loc_180020118
0x18002009a  cmp     cs:g_hMcMiscSocketEvent, r12
0x1800200a1  jz      short loc_180020118
0x1800200a3  cmp     cs:g_hMzapSocketEvent, r12
0x1800200aa  jz      short loc_180020118
0x1800200ac  cmp     cs:g_hMHbeatSocketEvent, r12
0x1800200b3  jz      short loc_180020118
0x1800200b5  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800200bc  jz      short loc_1800200D0
0x1800200be  lea     r8, aInitrouterCrea; "InitRouter: Created necessary events an"...
0x1800200c5  mov     rdx, rbx
0x1800200c8  mov     rcx, rdi
0x1800200cb  call    McTemplateU0z_EventWriteTransfer
0x1800200d0  call    InitializeThreadPool
0x1800200d5  mov     esi, eax
0x1800200d7  test    eax, eax
0x1800200d9  jz      short loc_1800200F6
0x1800200db  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x1800200e2  test    cl, cl
0x1800200e4  jns     loc_18001FE54
0x1800200ea  lea     rdx, aInitrouterInit; "InitRouter: InitializeThreadPool for de"...
0x1800200f1  jmp     loc_18001FE1F
0x1800200f6  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800200fd  jz      short loc_180020111
0x1800200ff  lea     r8, aLeavingInitrou_0; "Leaving: InitRouter"
  ... truncated ...
```

# RasSrvrUninitialize

- ea: `0x180057498`
- end: `0x18005777f`
- name: `RasSrvrUninitialize`
- size: `743`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001f8e0`
- `0x1800545a4`

## callees

- `0x180051bf0`
- `0x180057498`
- `0x1800594c0`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180057636`
- `KERNEL32!LocalFree` at `0x180057636`
- `KERNEL32!DeleteCriticalSection` at `0x18005765c`
- `KERNEL32!DeleteCriticalSection` at `0x180057669`
- `KERNEL32!DeleteCriticalSection` at `0x180057676`
- `KERNEL32!DeleteCriticalSection` at `0x180057683`
- `KERNEL32!DeleteCriticalSection` at `0x180057690`
- `KERNEL32!DeleteCriticalSection` at `0x18005769d`
- `KERNEL32!DeleteCriticalSection` at `0x1800576aa`
- `KERNEL32!DeleteCriticalSection` at `0x18005765c`
- `KERNEL32!DeleteCriticalSection` at `0x180057669`
- `KERNEL32!DeleteCriticalSection` at `0x180057676`
- `KERNEL32!DeleteCriticalSection` at `0x180057683`
- `KERNEL32!DeleteCriticalSection` at `0x180057690`
- `KERNEL32!DeleteCriticalSection` at `0x18005769d`
- `KERNEL32!DeleteCriticalSection` at `0x1800576aa`
- `KERNEL32!FreeLibrary` at `0x18005754f`
- `KERNEL32!FreeLibrary` at `0x18005754f`
- `KERNEL32!SetConsoleCtrlHandler` at `0x18005753d`
- `KERNEL32!SetConsoleCtrlHandler` at `0x18005753d`
- `KERNEL32!CloseHandle` at `0x1800575a8`
- `KERNEL32!CloseHandle` at `0x1800575c1`
- `KERNEL32!CloseHandle` at `0x1800576fe`
- `KERNEL32!CloseHandle` at `0x18005771b`
- `KERNEL32!CloseHandle` at `0x1800575a8`
- `KERNEL32!CloseHandle` at `0x1800575c1`
- `KERNEL32!CloseHandle` at `0x1800576fe`
- `KERNEL32!CloseHandle` at `0x18005771b`
- `KERNEL32!LeaveCriticalSection` at `0x18005764f`
- `KERNEL32!LeaveCriticalSection` at `0x18005764f`
- `KERNEL32!EnterCriticalSection` at `0x1800575e2`
- `KERNEL32!EnterCriticalSection` at `0x1800575e2`
- `ADVAPI32!CryptReleaseContext` at `0x1800576e1`
- `ADVAPI32!CryptReleaseContext` at `0x1800576e1`
- `rtutils!TraceDeregisterA` at `0x1800576c7`
- `rtutils!TraceDeregisterA` at `0x1800576c7`
- `WS2_32!__imp_closesocket` at `0x18005762d`
- `WS2_32!__imp_closesocket` at `0x18005762d`
- `DNSAPI!DnsDhcpSrvRegisterTerm` at `0x1800574d5`
- `DNSAPI!DnsDhcpSrvRegisterTerm` at `0x1800574d5`

## string_xrefs

- `0x18005773f`: `RasSrvrUnitialize completed`

## pseudocode

```c
void RasSrvrUninitialize()
{
  __int64 v0; // rcx
  unsigned int v1; // eax
  struct _LIST_ENTRY **p_Blink; // rbx
  struct _LIST_ENTRY *Flink; // rdx
  struct _LIST_ENTRY **v4; // rcx
  SOCKET v5; // rcx
  int v6; // [rsp+20h] [rbp-818h] BYREF
  _BYTE v7[2044]; // [rsp+24h] [rbp-814h] BYREF

  v6 = 0;
  memset_0(v7, 0, sizeof(v7));
  v1 = DnsDhcpSrvRegisterTerm(v0);
  if ( v1 && (_QWORD)xmmword_1800C9740 )
  {
    LOWORD(v6) = 0;
    FormatRRASErrorString(&v6, L"DnsDhcpSrvRegisterTerm failed and returned 0x%x", v1);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800C9740,
      &v6);
  }
  if ( PDisableDhcpInformServer )
    PDisableDhcpInformServer();
  SetConsoleCtrlHandler(ShutdownHandlerRoutine, 0);
  if ( HelperIpBootpDll )
  {
    FreeLibrary(HelperIpBootpDll);
    HelperIpBootpDll = 0;
  }
  if ( bDefaultRoutingDomainAdded )
  {
    RasSrvDeleteRoutingDomain(&GUID_NULL);
    bDefaultRoutingDomainAdded = 0;
  }
  RasUnInitializeRdStore();
  memset_0(&HelperRegVal, 0, 0xCCu);
  if ( HelperWanArpHandle != (HANDLE)-1LL )
  {
    CloseHandle(HelperWanArpHandle);
    HelperWanArpHandle = (HANDLE)-1LL;
  }
  if ( HelperWanArpv6Handle != (HANDLE)-1LL )
  {
    CloseHandle(HelperWanArpv6Handle);
    HelperWanArpv6Handle = (HANDLE)-1LL;
  }
  if ( RasSrvrHelperInitialized )
  {
    EnterCriticalSection(&SocketInfoCriticalSection);
    while ( RoutingDomainSocketInfoList.Flink != &RoutingDomainSocketInfoList )
    {
      p_Blink = &RoutingDomainSocketInfoList.Flink[-1].Blink;
      Flink = RoutingDomainSocketInfoList.Flink->Flink;
      if ( RoutingDomainSocketInfoList.Flink->Flink->Blink != RoutingDomainSocketInfoList.Flink
        || (v4 = (struct _LIST_ENTRY **)p_Blink[2], *v4 != RoutingDomainSocketInfoList.Flink) )
      {
        __fastfail(3u);
      }
      *v4 = Flink;
      Flink->Blink = (struct _LIST_ENTRY *)v4;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)p_Blink, 0xFFFFFFFF) == 1 )
      {
        v5 = (SOCKET)p_Blink[5];
        if ( v5 != -1 )
          closesocket(v5);
        LocalFree(p_Blink);
      }
    }
    LeaveCriticalSection(&SocketInfoCriticalSection);
    DeleteCriticalSection(&g_SubInterfaceIndexCriticalSec);
    DeleteCriticalSection(&RasSrvrCriticalSection);
    DeleteCriticalSection(&RasDhcpCriticalSection);
    DeleteCriticalSection(&csRasDhcpv6);
    DeleteCriticalSection(&csRasDhcpTimer);
    DeleteCriticalSection(&csRasDhcpv6Timer);
    DeleteCriticalSection(&SocketInfoCriticalSection);
    RasSrvrHelperInitialized = 0;
  }
  if ( RasIpAddrMgmtTraceId != -1 )
  {
    TraceDeregisterA(RasIpAddrMgmtTraceId);
    RasIpAddrMgmtTraceId = -1;
  }
  if ( g_hCryptProv )
  {
    CryptReleaseContext(g_hCryptProv, 0);
    g_hCryptProv = 0;
  }
  if ( EventDhcpTimerUninitializing )
  {
    CloseHandle(EventDhcpTimerUninitializing);
    EventDhcpTimerUninitializing = 0;
  }
  if ( EventDhcpIpv6TimerUninitializing )
  {
    CloseHandle(EventDhcpIpv6TimerUninitializing);
    EventDhcpIpv6TimerUninitializing = 0;
  }
  if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800C9740 + 1),
      L"RasSrvrUnitialize completed");
}

```

## disassembly

```asm
0x180057498  mov     [rsp+arg_0], rbx
0x18005749d  mov     [rsp+arg_8], rsi
0x1800574a2  push    r14
0x1800574a4  sub     rsp, 830h
0x1800574ab  mov     rax, cs:__security_cookie
0x1800574b2  xor     rax, rsp
0x1800574b5  mov     [rsp+838h+var_18], rax
0x1800574bd  xor     eax, eax
0x1800574bf  lea     rcx, [rsp+838h+var_814]; void *
0x1800574c4  xor     edx, edx; Val
0x1800574c6  mov     [rsp+838h+var_818], eax
0x1800574ca  mov     r8d, 7FCh; Size
0x1800574d0  call    memset_0
0x1800574d5  call    cs:__imp_DnsDhcpSrvRegisterTerm
0x1800574db  test    eax, eax
0x1800574dd  jz      short loc_180057523
0x1800574df  cmp     qword ptr cs:xmmword_1800C9740, 0
0x1800574e7  jz      short loc_180057523
0x1800574e9  xor     ecx, ecx
0x1800574eb  lea     rdx, aDnsdhcpsrvregi; "DnsDhcpSrvRegisterTerm failed and retur"...
0x1800574f2  mov     word ptr [rsp+838h+var_818], cx
0x1800574f7  mov     r8d, eax
0x1800574fa  lea     rcx, [rsp+838h+var_818]
0x1800574ff  call    FormatRRASErrorString
0x180057504  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18005750b  lea     r8, [rsp+838h+var_818]
0x180057510  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180057517  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005751e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057523  mov     rax, cs:?PDisableDhcpInformServer@@3P6AXXZEA; void (*PDisableDhcpInformServer)(void)
0x18005752a  test    rax, rax
0x18005752d  jz      short loc_180057534
0x18005752f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057534  xor     edx, edx; Add
0x180057536  lea     rcx, ?ShutdownHandlerRoutine@@YAHK@Z; HandlerRoutine
0x18005753d  call    cs:__imp_SetConsoleCtrlHandler
0x180057543  mov     rcx, cs:?HelperIpBootpDll@@3PEAUHINSTANCE__@@EA; hLibModule
0x18005754a  test    rcx, rcx
0x18005754d  jz      short loc_180057560
0x18005754f  call    cs:__imp_FreeLibrary
0x180057555  mov     cs:?HelperIpBootpDll@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * HelperIpBootpDll
0x180057560  cmp     cs:?bDefaultRoutingDomainAdded@@3HA, 0; int bDefaultRoutingDomainAdded
0x180057567  jz      short loc_18005757F
0x180057569  lea     rcx, GUID_NULL; struct _GUID *
0x180057570  call    RasSrvDeleteRoutingDomain
0x180057575  mov     cs:?bDefaultRoutingDomainAdded@@3HA, 0; int bDefaultRoutingDomainAdded
0x18005757f  call    RasUnInitializeRdStore
0x180057584  xor     edx, edx; Val
0x180057586  lea     rcx, ?HelperRegVal@@3U_REGISTRY_VALUES@@A; void *
0x18005758d  mov     r8d, 0CCh; Size
0x180057593  call    memset_0
0x180057598  mov     rcx, cs:?HelperWanArpHandle@@3PEAXEA; hObject
0x18005759f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800575a3  cmp     rcx, rsi
0x1800575a6  jz      short loc_1800575B5
0x1800575a8  call    cs:__imp_CloseHandle
0x1800575ae  mov     cs:?HelperWanArpHandle@@3PEAXEA, rsi; void * HelperWanArpHandle
0x1800575b5  mov     rcx, cs:?HelperWanArpv6Handle@@3PEAXEA; hObject
0x1800575bc  cmp     rcx, rsi
0x1800575bf  jz      short loc_1800575CE
0x1800575c1  call    cs:__imp_CloseHandle
0x1800575c7  mov     cs:?HelperWanArpv6Handle@@3PEAXEA, rsi; void * HelperWanArpv6Handle
0x1800575ce  cmp     cs:?RasSrvrHelperInitialized@@3HA, 0; int RasSrvrHelperInitialized
0x1800575d5  jz      loc_1800576BA
0x1800575db  lea     rcx, ?SocketInfoCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800575e2  call    cs:__imp_EnterCriticalSection
0x1800575e8  lea     r14, ?RoutingDomainSocketInfoList@@3U_LIST_ENTRY@@A; _LIST_ENTRY RoutingDomainSocketInfoList
0x1800575ef  jmp     short loc_18005763C
0x1800575f1  lea     rbx, [rax-8]
0x1800575f5  lea     rax, [rbx+8]
0x1800575f9  mov     rdx, [rax]
0x1800575fc  cmp     [rdx+8], rax
0x180057600  jnz     loc_180057778
0x180057606  mov     rcx, [rbx+10h]
0x18005760a  cmp     [rcx], rax
0x18005760d  jnz     loc_180057778
0x180057613  mov     [rcx], rdx
0x180057616  mov     eax, esi
0x180057618  mov     [rdx+8], rcx
0x18005761c  lock xadd [rbx], eax
0x180057620  add     eax, esi
0x180057622  jnz     short loc_18005763C
0x180057624  mov     rcx, [rbx+28h]; s
0x180057628  cmp     rcx, rsi
0x18005762b  jz      short loc_180057633
0x18005762d  call    cs:__imp_closesocket
0x180057633  mov     rcx, rbx; hMem
0x180057636  call    cs:__imp_LocalFree
0x18005763c  mov     rax, cs:?RoutingDomainSocketInfoList@@3U_LIST_ENTRY@@A; _LIST_ENTRY RoutingDomainSocketInfoList
0x180057643  cmp     rax, r14
0x180057646  jnz     short loc_1800575F1
0x180057648  lea     rcx, ?SocketInfoCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005764f  call    cs:__imp_LeaveCriticalSection
0x180057655  lea     rcx, g_SubInterfaceIndexCriticalSec; lpCriticalSection
0x18005765c  call    cs:__imp_DeleteCriticalSection
0x180057662  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180057669  call    cs:__imp_DeleteCriticalSection
0x18005766f  lea     rcx, ?RasDhcpCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180057676  call    cs:__imp_DeleteCriticalSection
0x18005767c  lea     rcx, ?csRasDhcpv6@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180057683  call    cs:__imp_DeleteCriticalSection
0x180057689  lea     rcx, ?csRasDhcpTimer@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180057690  call    cs:__imp_DeleteCriticalSection
0x180057696  lea     rcx, ?csRasDhcpv6Timer@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005769d  call    cs:__imp_DeleteCriticalSection
0x1800576a3  lea     rcx, ?SocketInfoCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800576aa  call    cs:__imp_DeleteCriticalSection
0x1800576b0  mov     cs:?RasSrvrHelperInitialized@@3HA, 0; int RasSrvrHelperInitialized
0x1800576ba  mov     ecx, cs:RasIpAddrMgmtTraceId; dwTraceID
0x1800576c0  or      ebx, 0FFFFFFFFh
0x1800576c3  cmp     ecx, ebx
0x1800576c5  jz      short loc_1800576D3
0x1800576c7  call    cs:__imp_TraceDeregisterA
0x1800576cd  mov     cs:RasIpAddrMgmtTraceId, ebx
0x1800576d3  mov     rcx, cs:?g_hCryptProv@@3_KA; hProv
0x1800576da  test    rcx, rcx
0x1800576dd  jz      short loc_1800576F2
0x1800576df  xor     edx, edx; dwFlags
0x1800576e1  call    cs:__imp_CryptReleaseContext
0x1800576e7  mov     cs:?g_hCryptProv@@3_KA, 0; unsigned __int64 g_hCryptProv
0x1800576f2  mov     rcx, cs:?EventDhcpTimerUninitializing@@3PEAXEA; hObject
0x1800576f9  test    rcx, rcx
0x1800576fc  jz      short loc_18005770F
0x1800576fe  call    cs:__imp_CloseHandle
0x180057704  mov     cs:?EventDhcpTimerUninitializing@@3PEAXEA, 0; void * EventDhcpTimerUninitializing
0x18005770f  mov     rcx, cs:?EventDhcpIpv6TimerUninitializing@@3PEAXEA; hObject
0x180057716  test    rcx, rcx
0x180057719  jz      short loc_18005772C
0x18005771b  call    cs:__imp_CloseHandle
0x180057721  mov     cs:?EventDhcpIpv6TimerUninitializing@@3PEAXEA, 0; void * EventDhcpIpv6TimerUninitializing
0x18005772c  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x180057733  test    rdx, rdx
0x180057736  jz      short loc_180057752
0x180057738  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005773f  lea     r8, aRassrvrunitial; "RasSrvrUnitialize completed"
0x180057746  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005774d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057752  mov     rcx, [rsp+838h+var_18]
0x18005775a  xor     rcx, rsp; StackCookie
0x18005775d  call    __security_check_cookie
0x180057762  lea     r11, [rsp+838h+var_8]
0x18005776a  mov     rbx, [r11+10h]
0x18005776e  mov     rsi, [r11+18h]
0x180057772  mov     rsp, r11
0x180057775  pop     r14
0x180057777  retn
0x180057778  mov     ecx, 3
0x18005777d  int     29h; Win8: RtlFailFast(ecx)
```

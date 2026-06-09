# RasSrvrUninitialize

- ea: `0x1800593c4`
- end: `0x18005965b`
- name: `RasSrvrUninitialize`
- size: `663`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800205b0`
- `0x1800561f4`

## callees

- `0x18004e60c`
- `0x180053638`
- `0x1800593c4`
- `0x18005b3e4`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18005951a`
- `KERNEL32!DeleteCriticalSection` at `0x18005952d`
- `KERNEL32!DeleteCriticalSection` at `0x180059540`
- `KERNEL32!DeleteCriticalSection` at `0x180059553`
- `KERNEL32!DeleteCriticalSection` at `0x180059566`
- `KERNEL32!DeleteCriticalSection` at `0x180059579`
- `KERNEL32!DeleteCriticalSection` at `0x18005958c`
- `KERNEL32!DeleteCriticalSection` at `0x18005951a`
- `KERNEL32!DeleteCriticalSection` at `0x18005952d`
- `KERNEL32!DeleteCriticalSection` at `0x180059540`
- `KERNEL32!DeleteCriticalSection` at `0x180059553`
- `KERNEL32!DeleteCriticalSection` at `0x180059566`
- `KERNEL32!DeleteCriticalSection` at `0x180059579`
- `KERNEL32!DeleteCriticalSection` at `0x18005958c`
- `KERNEL32!FreeLibrary` at `0x18005947a`
- `KERNEL32!FreeLibrary` at `0x18005947a`
- `KERNEL32!SetConsoleCtrlHandler` at `0x180059462`
- `KERNEL32!SetConsoleCtrlHandler` at `0x180059462`
- `KERNEL32!CloseHandle` at `0x1800594cd`
- `KERNEL32!CloseHandle` at `0x1800594ee`
- `KERNEL32!CloseHandle` at `0x1800595e9`
- `KERNEL32!CloseHandle` at `0x180059608`
- `KERNEL32!CloseHandle` at `0x1800594cd`
- `KERNEL32!CloseHandle` at `0x1800594ee`
- `KERNEL32!CloseHandle` at `0x1800595e9`
- `KERNEL32!CloseHandle` at `0x180059608`
- `ADVAPI32!CryptReleaseContext` at `0x1800595ca`
- `ADVAPI32!CryptReleaseContext` at `0x1800595ca`
- `rtutils!TraceDeregisterA` at `0x1800595a9`
- `rtutils!TraceDeregisterA` at `0x1800595a9`
- `DNSAPI!DnsDhcpSrvRegisterTerm` at `0x1800593f7`
- `DNSAPI!DnsDhcpSrvRegisterTerm` at `0x1800593f7`

## string_xrefs

- `0x18005962e`: `RasSrvrUnitialize completed`

## pseudocode

```c
void RasSrvrUninitialize()
{
  __int64 v0; // rcx
  unsigned int v1; // eax
  int v2; // [rsp+20h] [rbp-818h] BYREF
  _BYTE v3[2044]; // [rsp+24h] [rbp-814h] BYREF

  v2 = 0;
  memset_0(v3, 0, sizeof(v3));
  v1 = DnsDhcpSrvRegisterTerm(v0);
  if ( v1 && (_QWORD)xmmword_1800D0740 )
  {
    LOWORD(v2) = 0;
    FormatRRASErrorString(&v2, L"DnsDhcpSrvRegisterTerm failed and returned 0x%x", v1);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800D0740,
      &v2);
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
    CleanupIpv6ProxyArpSockets();
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
  if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800D0740 + 1),
      L"RasSrvrUnitialize completed");
}

```

## disassembly

```asm
0x1800593c4  push    rbx
0x1800593c6  sub     rsp, 830h
0x1800593cd  mov     rax, cs:__security_cookie
0x1800593d4  xor     rax, rsp
0x1800593d7  mov     [rsp+838h+var_18], rax
0x1800593df  xor     ebx, ebx
0x1800593e1  lea     rcx, [rsp+838h+var_814]; void *
0x1800593e6  xor     edx, edx; Val
0x1800593e8  mov     [rsp+838h+var_818], ebx
0x1800593ec  mov     r8d, 7FCh; Size
0x1800593f2  call    memset_0
0x1800593f7  call    cs:__imp_DnsDhcpSrvRegisterTerm
0x1800593fe  nop     dword ptr [rax+rax+00h]
0x180059403  test    eax, eax
0x180059405  jz      short loc_180059448
0x180059407  cmp     qword ptr cs:xmmword_1800D0740, rbx
0x18005940e  jz      short loc_180059448
0x180059410  mov     r8d, eax
0x180059413  mov     word ptr [rsp+838h+var_818], bx
0x180059418  lea     rdx, aDnsdhcpsrvregi; "DnsDhcpSrvRegisterTerm failed and retur"...
0x18005941f  lea     rcx, [rsp+838h+var_818]
0x180059424  call    FormatRRASErrorString
0x180059429  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180059430  lea     r8, [rsp+838h+var_818]
0x180059435  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005943c  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180059443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059448  mov     rax, cs:?PDisableDhcpInformServer@@3P6AXXZEA; void (*PDisableDhcpInformServer)(void)
0x18005944f  test    rax, rax
0x180059452  jz      short loc_180059459
0x180059454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059459  xor     edx, edx; Add
0x18005945b  lea     rcx, ?ShutdownHandlerRoutine@@YAHK@Z; HandlerRoutine
0x180059462  call    cs:__imp_SetConsoleCtrlHandler
0x180059469  nop     dword ptr [rax+rax+00h]
0x18005946e  mov     rcx, cs:?HelperIpBootpDll@@3PEAUHINSTANCE__@@EA; hLibModule
0x180059475  test    rcx, rcx
0x180059478  jz      short loc_18005948D
0x18005947a  call    cs:__imp_FreeLibrary
0x180059481  nop     dword ptr [rax+rax+00h]
0x180059486  mov     cs:?HelperIpBootpDll@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * HelperIpBootpDll
0x18005948d  cmp     cs:?bDefaultRoutingDomainAdded@@3HA, ebx; int bDefaultRoutingDomainAdded
0x180059493  jz      short loc_1800594A7
0x180059495  lea     rcx, GUID_NULL; struct _GUID *
0x18005949c  call    RasSrvDeleteRoutingDomain
0x1800594a1  mov     cs:?bDefaultRoutingDomainAdded@@3HA, ebx; int bDefaultRoutingDomainAdded
0x1800594a7  call    RasUnInitializeRdStore
0x1800594ac  xor     edx, edx; Val
0x1800594ae  lea     rcx, ?HelperRegVal@@3U_REGISTRY_VALUES@@A; void *
0x1800594b5  mov     r8d, 0CCh; Size
0x1800594bb  call    memset_0
0x1800594c0  mov     rcx, cs:?HelperWanArpHandle@@3PEAXEA; hObject
0x1800594c7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800594cb  jz      short loc_1800594E1
0x1800594cd  call    cs:__imp_CloseHandle
0x1800594d4  nop     dword ptr [rax+rax+00h]
0x1800594d9  or      cs:?HelperWanArpHandle@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * HelperWanArpHandle
0x1800594e1  mov     rcx, cs:?HelperWanArpv6Handle@@3PEAXEA; hObject
0x1800594e8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800594ec  jz      short loc_180059502
0x1800594ee  call    cs:__imp_CloseHandle
0x1800594f5  nop     dword ptr [rax+rax+00h]
0x1800594fa  or      cs:?HelperWanArpv6Handle@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * HelperWanArpv6Handle
0x180059502  cmp     cs:?RasSrvrHelperInitialized@@3HA, ebx; int RasSrvrHelperInitialized
0x180059508  jz      loc_18005959E
0x18005950e  call    ?CleanupIpv6ProxyArpSockets@@YAXXZ; CleanupIpv6ProxyArpSockets(void)
0x180059513  lea     rcx, g_SubInterfaceIndexCriticalSec; lpCriticalSection
0x18005951a  call    cs:__imp_DeleteCriticalSection
0x180059521  nop     dword ptr [rax+rax+00h]
0x180059526  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005952d  call    cs:__imp_DeleteCriticalSection
0x180059534  nop     dword ptr [rax+rax+00h]
0x180059539  lea     rcx, ?RasDhcpCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180059540  call    cs:__imp_DeleteCriticalSection
0x180059547  nop     dword ptr [rax+rax+00h]
0x18005954c  lea     rcx, ?csRasDhcpv6@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180059553  call    cs:__imp_DeleteCriticalSection
0x18005955a  nop     dword ptr [rax+rax+00h]
0x18005955f  lea     rcx, ?csRasDhcpTimer@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180059566  call    cs:__imp_DeleteCriticalSection
0x18005956d  nop     dword ptr [rax+rax+00h]
0x180059572  lea     rcx, ?csRasDhcpv6Timer@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180059579  call    cs:__imp_DeleteCriticalSection
0x180059580  nop     dword ptr [rax+rax+00h]
0x180059585  lea     rcx, ?SocketInfoCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005958c  call    cs:__imp_DeleteCriticalSection
0x180059593  nop     dword ptr [rax+rax+00h]
0x180059598  mov     cs:?RasSrvrHelperInitialized@@3HA, ebx; int RasSrvrHelperInitialized
0x18005959e  mov     ecx, cs:RasIpAddrMgmtTraceId; dwTraceID
0x1800595a4  cmp     ecx, 0FFFFFFFFh
0x1800595a7  jz      short loc_1800595BC
0x1800595a9  call    cs:__imp_TraceDeregisterA
0x1800595b0  nop     dword ptr [rax+rax+00h]
0x1800595b5  or      cs:RasIpAddrMgmtTraceId, 0FFFFFFFFh
0x1800595bc  mov     rcx, cs:?g_hCryptProv@@3_KA; hProv
0x1800595c3  test    rcx, rcx
0x1800595c6  jz      short loc_1800595DD
0x1800595c8  xor     edx, edx; dwFlags
0x1800595ca  call    cs:__imp_CryptReleaseContext
0x1800595d1  nop     dword ptr [rax+rax+00h]
0x1800595d6  mov     cs:?g_hCryptProv@@3_KA, rbx; unsigned __int64 g_hCryptProv
0x1800595dd  mov     rcx, cs:?EventDhcpTimerUninitializing@@3PEAXEA; hObject
0x1800595e4  test    rcx, rcx
0x1800595e7  jz      short loc_1800595FC
0x1800595e9  call    cs:__imp_CloseHandle
0x1800595f0  nop     dword ptr [rax+rax+00h]
0x1800595f5  mov     cs:?EventDhcpTimerUninitializing@@3PEAXEA, rbx; void * EventDhcpTimerUninitializing
0x1800595fc  mov     rcx, cs:?EventDhcpIpv6TimerUninitializing@@3PEAXEA; hObject
0x180059603  test    rcx, rcx
0x180059606  jz      short loc_18005961B
0x180059608  call    cs:__imp_CloseHandle
0x18005960f  nop     dword ptr [rax+rax+00h]
0x180059614  mov     cs:?EventDhcpIpv6TimerUninitializing@@3PEAXEA, rbx; void * EventDhcpIpv6TimerUninitializing
0x18005961b  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x180059622  test    rdx, rdx
0x180059625  jz      short loc_180059641
0x180059627  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005962e  lea     r8, aRassrvrunitial; "RasSrvrUnitialize completed"
0x180059635  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005963c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059641  mov     rcx, [rsp+838h+var_18]
0x180059649  xor     rcx, rsp; StackCookie
0x18005964c  call    __security_check_cookie
0x180059651  add     rsp, 830h
0x180059658  pop     rbx
0x180059659  retn
```

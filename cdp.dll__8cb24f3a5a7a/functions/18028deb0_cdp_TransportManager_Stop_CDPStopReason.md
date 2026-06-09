# cdp::TransportManager::Stop(CDPStopReason)

- ea: `0x18028deb0`
- end: `0x18028e0ce`
- name: `?Stop@TransportManager@cdp@@UEAAXW4CDPStopReason@@@Z`
- size: `542`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `service_task`

## callees

- `0x18000f8d0`
- `0x180010ee0`
- `0x1800113bc`
- `0x180030190`
- `0x180089254`
- `0x180089910`
- `0x1800a9aac`
- `0x1800aa1ec`
- `0x1800aa2bc`
- `0x1800dd7fc`
- `0x1801181d4`
- `0x1801f6fb0`
- `0x18028deb0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18028e0c7`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18028e0c7`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18028e032`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18028e032`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18028e000`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18028e000`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18028e0b2`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18028e0b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall cdp::TransportManager::Stop(__int64 a1, int a2)
{
  const char *v4; // rax
  _QWORD *v5; // rbx
  struct std::exception_ptr *v6; // r8
  int v8; // [rsp+30h] [rbp-F8h] BYREF
  const char *v9; // [rsp+38h] [rbp-F0h] BYREF
  __int128 v10; // [rsp+40h] [rbp-E8h] BYREF
  _BYTE v11[16]; // [rsp+50h] [rbp-D8h] BYREF
  _BYTE v12[32]; // [rsp+60h] [rbp-C8h] BYREF
  _QWORD v13[4]; // [rsp+80h] [rbp-A8h] BYREF
  _BYTE v14[96]; // [rsp+A0h] [rbp-88h] BYREF

  std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(v11, a1 + 312);
  if ( *(_BYTE *)(a1 + 296) )
  {
    cdp::detail::StringFormat(v12, "{\"text\":\"Stopping transport, reason = %u\"}", a2);
    shared::LogMessage(3, v12);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v12);
    v8 = 0;
    switch ( a2 )
    {
      case 1:
        v4 = "Error";
        break;
      case 2:
        v4 = "Idle";
        break;
      case 3:
        v4 = "FirstStart";
        break;
      case 4:
        v4 = "Termination";
        break;
      default:
        v4 = "Unspecified";
        break;
    }
    v9 = v4;
    cdp::StringFormat<unsigned __int64 &>(v13, "Reason %s", (const char *)&v9);
    v5 = v13;
    if ( v13[3] > 0xFu )
      LODWORD(v5) = v13[0];
    std::string::string(v12, "TransportManager.Host.Stop");
    shared::TelemetryTask::TelemetryTask(
      (unsigned int)v14,
      (unsigned int)v12,
      0,
      (_DWORD)v5,
      1,
      (__int64)qword_1803986E0);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v12);
    v10 = 0;
    __ExceptionPtrCreate(&v10);
    *(_DWORD *)(a1 + 304) = a2;
    try
    {
      cdp::TransportManager::Uninitialize((cdp::TransportManager *)a1);
      shared::TelemetryTask::Stop((shared::TelemetryTask *)v14, 0, qword_1803986E0);
    }
    catch ( ... )
    {
      cdp::CatchAllStoreHRAndExceptionNoLog((cdp *)&v8, (int *)&v10, v6);
    }
    __ExceptionPtrDestroy(&v10);
    shared::TelemetryTask::~TelemetryTask((shared::TelemetryTask *)v14);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v13);
  }
  return std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v11);
}

```

## disassembly

```asm
0x18028deb0  mov     [rsp+arg_10], rbx
0x18028deb5  push    rsi
0x18028deb6  push    rdi
0x18028deb7  push    r14
0x18028deb9  sub     rsp, 110h
0x18028dec0  mov     rax, cs:__security_cookie
0x18028dec7  xor     rax, rsp
0x18028deca  mov     [rsp+128h+var_28], rax
0x18028ded2  mov     esi, edx
0x18028ded4  mov     rdi, rcx
0x18028ded7  lea     rdx, [rcx+138h]
0x18028dede  lea     rcx, [rsp+128h+var_D8]
0x18028dee3  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x18028dee8  nop
0x18028dee9  mov     al, [rdi+128h]
0x18028deef  nop
0x18028def0  test    al, al
0x18028def2  jz      loc_18028E055
0x18028def8  mov     r8d, esi
0x18028defb  lea     rdx, aTextStoppingTr; "{\"text\":\"Stopping transport, reason "...
0x18028df02  lea     rcx, [rsp+128h+var_C8]
0x18028df07  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x18028df0c  nop
0x18028df0d  lea     rdx, [rsp+128h+var_C8]
0x18028df12  mov     ecx, 3
0x18028df17  call    ?LogMessage@shared@@YAXW4CDPLogLevel@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; shared::LogMessage(CDPLogLevel,std::string &)
0x18028df1c  nop
0x18028df1d  lea     rcx, [rsp+128h+var_C8]; void *
0x18028df22  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18028df27  mov     [rsp+128h+var_F8], 0
0x18028df2f  mov     eax, esi
0x18028df31  sub     eax, 1
0x18028df34  jz      short loc_18028DF69
0x18028df36  sub     eax, 1
0x18028df39  jz      short loc_18028DF60
0x18028df3b  sub     eax, 1
0x18028df3e  jz      short loc_18028DF57
0x18028df40  cmp     eax, 1
0x18028df43  jz      short loc_18028DF4E
0x18028df45  lea     rax, aUnspecified; "Unspecified"
0x18028df4c  jmp     short loc_18028DF70
0x18028df4e  lea     rax, aTermination; "Termination"
0x18028df55  jmp     short loc_18028DF70
0x18028df57  lea     rax, aFirststart; "FirstStart"
0x18028df5e  jmp     short loc_18028DF70
0x18028df60  lea     rax, aIdle; "Idle"
0x18028df67  jmp     short loc_18028DF70
0x18028df69  lea     rax, aError; "Error"
0x18028df70  mov     [rsp+128h+var_F0], rax
0x18028df75  lea     r8, [rsp+128h+var_F0]
0x18028df7a  lea     rdx, aReasonS; "Reason %s"
0x18028df81  lea     rcx, [rsp+128h+var_A8]
0x18028df89  call    ??$StringFormat@AEA_K@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDAEA_K@Z; cdp::StringFormat<unsigned __int64 &>(char const *,unsigned __int64 &)
0x18028df8e  nop
0x18028df8f  lea     rbx, [rsp+128h+var_A8]
0x18028df97  cmp     [rsp+128h+var_90], 0Fh
0x18028dfa0  cmova   rbx, [rsp+128h+var_A8]
0x18028dfa9  lea     rdx, ?TransportManagerStopHost@MetricsIdentifier@shared@@2QBDB; "TransportManager.Host.Stop"
0x18028dfb0  lea     rcx, [rsp+128h+var_C8]
0x18028dfb5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18028dfba  nop
0x18028dfbb  lea     r14, qword_1803986E0
0x18028dfc2  mov     [rsp+128h+var_100], r14
0x18028dfc7  mov     [rsp+128h+var_108], 1
0x18028dfcf  mov     r9, rbx
0x18028dfd2  xor     r8d, r8d
0x18028dfd5  lea     rdx, [rsp+128h+var_C8]
0x18028dfda  lea     rcx, [rsp+128h+var_88]
0x18028dfe2  call    ??0TelemetryTask@shared@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@JPEBDW4MetricsOrigin@1@1@Z; shared::TelemetryTask::TelemetryTask(std::string const &,long,char const *,shared::MetricsOrigin,char const *)
0x18028dfe7  nop
0x18028dfe8  lea     rcx, [rsp+128h+var_C8]; void *
0x18028dfed  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18028dff2  xorps   xmm0, xmm0
0x18028dff5  movdqu  [rsp+128h+var_E8], xmm0
0x18028dffb  lea     rcx, [rsp+128h+var_E8]
0x18028e000  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18028e006  nop
0x18028e007  mov     [rdi+130h], esi
0x18028e00d  lea     rdx, [rsp+128h+var_D8]
0x18028e012  mov     rcx, rdi; this
0x18028e015  call    ?Uninitialize@TransportManager@cdp@@AEAAXAEAV?$unique_lock@Vrecursive_mutex@std@@@std@@@Z; cdp::TransportManager::Uninitialize(std::unique_lock<std::recursive_mutex> &)
0x18028e01a  mov     r8, r14; char *
0x18028e01d  xor     edx, edx; int
0x18028e01f  lea     rcx, [rsp+128h+var_88]; this
0x18028e027  call    ?Stop@TelemetryTask@shared@@QEAAXJPEBD@Z; shared::TelemetryTask::Stop(long,char const *)
0x18028e02c  nop
0x18028e02d  lea     rcx, [rsp+128h+var_E8]
0x18028e032  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18028e038  nop
0x18028e039  lea     rcx, [rsp+128h+var_88]; this
0x18028e041  call    ??1TelemetryTask@shared@@QEAA@XZ; shared::TelemetryTask::~TelemetryTask(void)
0x18028e046  nop
0x18028e047  lea     rcx, [rsp+128h+var_A8]; void *
0x18028e04f  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18028e054  nop
0x18028e055  lea     rcx, [rsp+128h+var_D8]
0x18028e05a  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18028e05f  mov     rcx, [rsp+128h+var_28]
0x18028e067  xor     rcx, rsp; StackCookie
0x18028e06a  call    __security_check_cookie
0x18028e06f  mov     rbx, [rsp+128h+arg_10]
0x18028e077  add     rsp, 110h
0x18028e07e  pop     r14
0x18028e080  pop     rdi
0x18028e081  pop     rsi
0x18028e082  retn
0x18028e083  mov     edx, [rsp+128h+var_F8]; int
0x18028e087  test    edx, edx
0x18028e089  jns     short loc_18028E02D
0x18028e08b  lea     r8, qword_1803986E0; char *
0x18028e092  lea     rcx, [rsp+128h+var_88]; this
0x18028e09a  call    ?Stop@TelemetryTask@shared@@QEAAXJPEBD@Z; shared::TelemetryTask::Stop(long,char const *)
0x18028e09f  xorps   xmm0, xmm0
0x18028e0a2  movdqu  xmmword ptr [rsp+128h+var_C8], xmm0
0x18028e0a8  lea     rdx, [rsp+128h+var_E8]
0x18028e0ad  lea     rcx, [rsp+128h+var_C8]
0x18028e0b2  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18028e0b8  lea     rax, [rsp+128h+var_C8]
0x18028e0bd  mov     [rsp+128h+var_F0], rax
0x18028e0c2  lea     rcx, [rsp+128h+var_C8]
0x18028e0c7  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
```

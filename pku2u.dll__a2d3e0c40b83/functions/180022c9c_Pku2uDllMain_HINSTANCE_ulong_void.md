# Pku2uDllMain(HINSTANCE__ *,ulong,void *)

- ea: `0x180022c9c`
- end: `0x180022e25`
- name: `?Pku2uDllMain@@YAHPEAUHINSTANCE__@@KPEAX@Z`
- size: `393`
- prototype: `__int64 __fastcall(HINSTANCE, unsigned int, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x180022a30`

## callees

- `0x180021a54`
- `0x180022654`
- `0x180022660`
- `0x180022b24`
- `0x180022c9c`
- `0x180023bdc`
- `0x18002ec08`
- `0x18002edcc`
- `0x18002f40c`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180022d31`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180022d31`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180022cb7`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180022cb7`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x180022df2`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x180022df2`

## pseudocode

```c
__int64 __fastcall Pku2uDllMain(HINSTANCE a1, int a2, void *a3)
{
  TraceLoggingCorrelationVector *v3; // rax
  const struct wil::FailureInfo *v4; // rdx
  _QWORD *v5; // rdi
  TRACEHANDLE v6; // rcx
  _BYTE v8[160]; // [rsp+20h] [rbp-A8h] BYREF

  if ( a2 == 1 )
  {
    DisableThreadLibraryCalls(a1);
    qword_1800587D8 = 1;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_Pku2uGlobalDebugTraceControlGuid;
    qword_1800587D0 = 0;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    WPP_MAIN_CB = 0;
    WppInitUm();
    v3 = (TraceLoggingCorrelationVector *)operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v3 )
    {
      Pku2uLogProvider::m_correlationVector = TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v3);
      if ( Pku2uLogProvider::m_correlationVector )
      {
        Pku2uLogProvider::m_initialized = 1;
        QueryPerformanceFrequency(&Pku2uLogProvider::m_perfCtrFreq);
      }
    }
    else
    {
      Pku2uLogProvider::m_correlationVector = 0;
    }
    if ( wil::details::g_pfnTelemetryCallback
      && (void (__fastcall *)(bool, const struct wil::FailureInfo *))wil::details::g_pfnTelemetryCallback != Pku2uLogProvider::FallbackTelemetryCallback )
    {
      memset_0(v8, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v8, v4);
    }
    wil::details::g_pfnTelemetryCallback = (__int64)Pku2uLogProvider::FallbackTelemetryCallback;
  }
  else if ( !a2 )
  {
    if ( Pku2uGlobalBaseSSP )
    {
      basessp::BaseSSP::`scalar deleting destructor'(Pku2uGlobalBaseSSP, 0);
      Pku2uGlobalBaseSSP = 0;
    }
    if ( Pku2uGlobalUserModeContextsInitialized )
    {
      WSTFreeUserModeContextList(0);
      Pku2uGlobalUserModeContextsInitialized = 0;
    }
    if ( Pku2uLogProvider::m_correlationVector )
      operator delete(Pku2uLogProvider::m_correlationVector, 0x90u);
    v5 = WPP_GLOBAL_Control;
    Pku2uLogProvider::m_initialized = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      while ( v5 )
      {
        v6 = v5[1];
        if ( v6 )
        {
          UnregisterTraceGuids(v6);
          v5[1] = 0;
        }
        v5 = (_QWORD *)*v5;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180022c9c  mov     [rsp+arg_0], rbx
0x180022ca1  mov     [rsp+arg_8], rsi
0x180022ca6  push    rdi
0x180022ca7  sub     rsp, 0C0h
0x180022cae  cmp     edx, 1
0x180022cb1  jnz     loc_180022D81
0x180022cb7  call    cs:__imp_DisableThreadLibraryCalls
0x180022cbd  lea     rax, WPP_ThisDir_CTLGUID_Pku2uGlobalDebugTraceControlGuid
0x180022cc4  mov     cs:qword_1800587D8, 1
0x180022ccf  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180022cd6  xor     ebx, ebx
0x180022cd8  lea     rax, WPP_MAIN_CB
0x180022cdf  mov     cs:qword_1800587D0, rbx
0x180022ce6  mov     cs:WPP_GLOBAL_Control, rax
0x180022ced  mov     cs:WPP_MAIN_CB, rbx
0x180022cf4  call    WppInitUm
0x180022cf9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180022d00  mov     ecx, 90h; unsigned __int64
0x180022d05  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180022d0a  test    rax, rax
0x180022d0d  jz      short loc_180022D39
0x180022d0f  mov     rcx, rax; this
0x180022d12  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x180022d17  mov     cs:?m_correlationVector@Pku2uLogProvider@@0PEAVTraceLoggingCorrelationVector@@EA, rax; TraceLoggingCorrelationVector * Pku2uLogProvider::m_correlationVector
0x180022d1e  test    rax, rax
0x180022d21  jz      short loc_180022D40
0x180022d23  lea     rcx, ?m_perfCtrFreq@Pku2uLogProvider@@0T_LARGE_INTEGER@@A; lpFrequency
0x180022d2a  mov     cs:?m_initialized@Pku2uLogProvider@@0_NA, 1; bool Pku2uLogProvider::m_initialized
0x180022d31  call    cs:__imp_QueryPerformanceFrequency
0x180022d37  jmp     short loc_180022D40
0x180022d39  mov     cs:?m_correlationVector@Pku2uLogProvider@@0PEAVTraceLoggingCorrelationVector@@EA, rbx; TraceLoggingCorrelationVector * Pku2uLogProvider::m_correlationVector
0x180022d40  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180022d47  lea     rcx, ?FallbackTelemetryCallback@Pku2uLogProvider@@SAX_NAEBUFailureInfo@wil@@@Z; Pku2uLogProvider::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x180022d4e  test    rax, rax
0x180022d51  jz      short loc_180022D75
0x180022d53  cmp     rax, rcx
0x180022d56  jz      short loc_180022D75
0x180022d58  xor     edx, edx; Val
0x180022d5a  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180022d5f  mov     r8d, 98h; Size
0x180022d65  call    memset_0
0x180022d6a  lea     rcx, [rsp+0C8h+var_A8]; this
0x180022d6f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180022d75  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rcx
0x180022d7c  jmp     loc_180022E0B
0x180022d81  xor     ebx, ebx
0x180022d83  test    edx, edx
0x180022d85  jnz     loc_180022E0B
0x180022d8b  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x180022d92  test    rcx, rcx
0x180022d95  jz      short loc_180022DA3
0x180022d97  call    ??_GBaseSSP@basessp@@QEAAPEAXI@Z; basessp::BaseSSP::`scalar deleting destructor'(uint)
0x180022d9c  mov     cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA, rbx; basessp::BaseSSP * Pku2uGlobalBaseSSP
0x180022da3  cmp     cs:?Pku2uGlobalUserModeContextsInitialized@@3EA, bl; uchar Pku2uGlobalUserModeContextsInitialized
0x180022da9  jz      short loc_180022DB8
0x180022dab  xor     ecx, ecx; unsigned int
0x180022dad  call    ?WSTFreeUserModeContextList@@YAXK@Z; WSTFreeUserModeContextList(ulong)
0x180022db2  mov     cs:?Pku2uGlobalUserModeContextsInitialized@@3EA, bl; uchar Pku2uGlobalUserModeContextsInitialized
0x180022db8  mov     rcx, cs:?m_correlationVector@Pku2uLogProvider@@0PEAVTraceLoggingCorrelationVector@@EA; void *
0x180022dbf  test    rcx, rcx
0x180022dc2  jz      short loc_180022DCE
0x180022dc4  mov     edx, 90h; unsigned __int64
0x180022dc9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180022dce  mov     rdi, cs:WPP_GLOBAL_Control
0x180022dd5  lea     rsi, WPP_GLOBAL_Control
0x180022ddc  mov     cs:?m_initialized@Pku2uLogProvider@@0_NA, bl; bool Pku2uLogProvider::m_initialized
0x180022de2  cmp     rdi, rsi
0x180022de5  jz      short loc_180022E0B
0x180022de7  jmp     short loc_180022DFF
0x180022de9  mov     rcx, [rdi+8]; RegistrationHandle
0x180022ded  test    rcx, rcx
0x180022df0  jz      short loc_180022DFC
0x180022df2  call    cs:__imp_UnregisterTraceGuids
0x180022df8  mov     [rdi+8], rbx
0x180022dfc  mov     rdi, [rdi]
0x180022dff  test    rdi, rdi
0x180022e02  jnz     short loc_180022DE9
0x180022e04  mov     cs:WPP_GLOBAL_Control, rsi
0x180022e0b  lea     r11, [rsp+0C8h+var_8]
0x180022e13  mov     eax, 1
0x180022e18  mov     rbx, [r11+10h]
0x180022e1c  mov     rsi, [r11+18h]
0x180022e20  mov     rsp, r11
0x180022e23  pop     rdi
0x180022e24  retn
```

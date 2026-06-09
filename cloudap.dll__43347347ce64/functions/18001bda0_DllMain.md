# DllMain

- ea: `0x18001bda0`
- end: `0x18001bff4`
- name: `DllMain`
- size: `596`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180042284`

## callees

- `0x18001bda0`
- `0x1800404e8`
- `0x18004317c`
- `0x1800463d8`
- `0x180046ecc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001bef2`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001bef2`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18001bfe9`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18001bfe9`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18001bf17`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18001bf17`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x18001be64`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x18001be64`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18001bfbc`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18001bfbc`
- `ntdll!RtlImageNtHeader` at `0x18001be87`
- `ntdll!RtlImageNtHeader` at `0x18001be87`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  HINSTANCE v3; // rbx
  __int64 SizeOfStackCommit; // rdi
  ULONG64 *v6; // rsi
  const GUID **v7; // r14
  const GUID *v8; // r8
  PIMAGE_NT_HEADERS v9; // rcx
  __int64 GuaranteedStackBytes; // rax
  const struct wil::FailureInfo *v11; // rdx
  void *v12; // rbx
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+40h] [rbp-B8h] BYREF
  _BYTE v14[160]; // [rsp+50h] [rbp-A8h] BYREF

  v3 = hinstDLL;
  if ( fdwReason != 1 )
  {
    if ( !fdwReason )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( WPP_GLOBAL_Control )
        {
          do
          {
            hinstDLL = (HINSTANCE)*((_QWORD *)v12 + 1);
            if ( hinstDLL )
            {
              UnregisterTraceGuids((TRACEHANDLE)hinstDLL);
              *((_QWORD *)v12 + 1) = 0;
            }
            v12 = *(void **)v12;
          }
          while ( v12 );
        }
        WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
      }
      McGenEventUnregister_EventUnregister(hinstDLL, *(_QWORD *)&fdwReason, lpvReserved);
      if ( g_dwTlsCloudAPIndex != -1 )
        TlsFree(g_dwTlsCloudAPIndex);
    }
    return 1;
  }
  SizeOfStackCommit = 0;
  qword_18009AF68 = 1;
  qword_18009AF60 = 0;
  v6 = (ULONG64 *)&WPP_MAIN_CB;
  WPP_MAIN_CB = 0;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CloudAPDebugTraceControlGuid;
  v7 = (const GUID **)&WPP_REGISTRATION_GUIDS;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  do
  {
    v8 = *v7;
    TraceGuidReg.Guid = v8;
    ++v7;
    TraceGuidReg.RegHandle = 0;
    v6[4] = (ULONG64)v8;
    RegisterTraceGuidsW(WppControlCallback, v6, v8, 1u, &TraceGuidReg, 0, 0, v6 + 1);
    v6 = (ULONG64 *)*v6;
  }
  while ( v6 );
  v9 = RtlImageNtHeader(NtCurrentPeb()->ImageBaseAddress);
  if ( NtCurrentPeb()->BeingDebugged || !v9 )
  {
LABEL_14:
    g_ulMaxStackAllocSize = SizeOfStackCommit;
    if ( !v9 )
      goto LABEL_17;
    goto LABEL_15;
  }
  if ( v9->OptionalHeader.SizeOfStackReserve - v9->OptionalHeader.SizeOfStackCommit >= 0x3000 )
  {
    SizeOfStackCommit = v9->OptionalHeader.SizeOfStackCommit;
    goto LABEL_14;
  }
  g_ulMaxStackAllocSize = 0;
LABEL_15:
  GuaranteedStackBytes = NtCurrentTeb()->GuaranteedStackBytes;
  g_ulAdditionalProbeSize = GuaranteedStackBytes;
  if ( !GuaranteedStackBytes )
  {
    g_ulAdditionalProbeSize = 12288;
    goto LABEL_11;
  }
  if ( (unsigned __int64)(GuaranteedStackBytes + 8) >= 8 )
    goto LABEL_11;
LABEL_17:
  g_ulAdditionalProbeSize = -9;
LABEL_11:
  g_pfnAllocate = (__int64)SafeAllocaAllocateFromHeap;
  g_pfnFree = (__int64)SafeAllocaFreeToHeap;
  DisableThreadLibraryCalls(v3);
  McGenEventRegister_EventRegister();
  if ( wil::details::g_pfnTelemetryCallback
    && (char *)wil::details::g_pfnTelemetryCallback != (char *)CloudAPProvider::FallbackTelemetryCallback )
  {
    memset_0(v14, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v14, v11);
  }
  wil::details::g_pfnTelemetryCallback = (__int64 (__fastcall *)(_QWORD, _QWORD))CloudAPProvider::FallbackTelemetryCallback;
  g_dwTlsCloudAPIndex = TlsAlloc();
  return 1;
}

```

## disassembly

```asm
0x18001bda0  mov     [rsp+arg_8], rbx
0x18001bda5  mov     [rsp+arg_10], rsi
0x18001bdaa  push    rdi
0x18001bdab  sub     rsp, 0F0h
0x18001bdb2  mov     rbx, rcx
0x18001bdb5  cmp     edx, 1
0x18001bdb8  jz      short loc_18001BDDC
0x18001bdba  test    edx, edx
0x18001bdbc  jz      loc_18001BF99
0x18001bdc2  lea     r11, [rsp+0F8h+var_8]
0x18001bdca  mov     eax, 1
0x18001bdcf  mov     rbx, [r11+18h]
0x18001bdd3  mov     rsi, [r11+20h]
0x18001bdd7  mov     rsp, r11
0x18001bdda  pop     rdi
0x18001bddb  retn
0x18001bddc  mov     [rsp+0F8h+arg_0], r14
0x18001bde4  xor     edi, edi
0x18001bde6  mov     cs:qword_18009AF68, 1
0x18001bdf1  lea     rax, WPP_ThisDir_CTLGUID_CloudAPDebugTraceControlGuid
0x18001bdf8  mov     cs:qword_18009AF60, rdi
0x18001bdff  lea     rsi, WPP_MAIN_CB
0x18001be06  mov     cs:WPP_MAIN_CB, rdi
0x18001be0d  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18001be14  lea     r14, WPP_REGISTRATION_GUIDS
0x18001be1b  mov     cs:WPP_GLOBAL_Control, rsi
0x18001be22  mov     r8, [r14]; ControlGuid
0x18001be25  lea     rax, [rsi+8]
0x18001be29  mov     [rsp+0F8h+RegistrationHandle], rax; RegistrationHandle
0x18001be2e  lea     rcx, WppControlCallback; RequestAddress
0x18001be35  mov     [rsp+0F8h+MofResourceName], rdi; MofResourceName
0x18001be3a  lea     rax, [rsp+0F8h+var_B8]
0x18001be3f  mov     [rsp+0F8h+var_B8.Guid], r8
0x18001be44  lea     r14, [r14+8]
0x18001be48  mov     [rsp+0F8h+var_B8.RegHandle], rdi
0x18001be4d  mov     r9d, 1; GuidCount
0x18001be53  mov     [rsp+0F8h+MofImagePath], rdi; MofImagePath
0x18001be58  mov     rdx, rsi; RequestContext
0x18001be5b  mov     [rsp+0F8h+TraceGuidReg], rax; TraceGuidReg
0x18001be60  mov     [rsi+20h], r8
0x18001be64  call    cs:__imp_RegisterTraceGuidsW
0x18001be6a  mov     rsi, [rsi]
0x18001be6d  test    rsi, rsi
0x18001be70  jnz     short loc_18001BE22
0x18001be72  mov     rcx, gs:60h
0x18001be7b  mov     r14, [rsp+0F8h+arg_0]
0x18001be83  mov     rcx, [rcx+10h]; BaseAddress
0x18001be87  call    cs:__imp_RtlImageNtHeader
0x18001be8d  mov     rcx, rax
0x18001be90  mov     rax, gs:60h
0x18001be99  cmp     [rax+2], dil
0x18001be9d  jnz     loc_18001BF2C
0x18001bea3  test    rcx, rcx
0x18001bea6  jz      loc_18001BF2C
0x18001beac  mov     rax, [rcx+60h]
0x18001beb0  sub     rax, [rcx+68h]
0x18001beb4  cmp     rax, 3000h
0x18001beba  jnb     short loc_18001BF28
0x18001bebc  mov     cs:g_ulMaxStackAllocSize, rdi
0x18001bec3  jmp     short loc_18001BF38
0x18001bec5  add     rax, 8
0x18001bec9  cmp     rax, 8
0x18001becd  jb      loc_18001BF67
0x18001bed3  lea     rax, SafeAllocaAllocateFromHeap
0x18001beda  mov     rcx, rbx; hLibModule
0x18001bedd  mov     cs:g_pfnAllocate, rax
0x18001bee4  lea     rax, SafeAllocaFreeToHeap
0x18001beeb  mov     cs:g_pfnFree, rax
0x18001bef2  call    cs:__imp_DisableThreadLibraryCalls
0x18001bef8  call    McGenEventRegister_EventRegister
0x18001befd  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18001bf04  lea     rcx, ?FallbackTelemetryCallback@CloudAPProvider@@SAX_NAEBUFailureInfo@wil@@@Z; CloudAPProvider::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x18001bf0b  test    rax, rax
0x18001bf0e  jnz     short loc_18001BF77
0x18001bf10  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rcx
0x18001bf17  call    cs:__imp_TlsAlloc
0x18001bf1d  mov     cs:?g_dwTlsCloudAPIndex@@3KA, eax; ulong g_dwTlsCloudAPIndex
0x18001bf23  jmp     loc_18001BDC2
0x18001bf28  mov     rdi, [rcx+68h]
0x18001bf2c  mov     cs:g_ulMaxStackAllocSize, rdi
0x18001bf33  test    rcx, rcx
0x18001bf36  jz      short loc_18001BF67
0x18001bf38  mov     rax, gs:30h
0x18001bf41  mov     eax, [rax+1748h]
0x18001bf47  mov     cs:g_ulAdditionalProbeSize, rax
0x18001bf4e  test    rax, rax
0x18001bf51  jnz     loc_18001BEC5
0x18001bf57  mov     cs:g_ulAdditionalProbeSize, 3000h
0x18001bf62  jmp     loc_18001BED3
0x18001bf67  mov     cs:g_ulAdditionalProbeSize, 0FFFFFFFFFFFFFFF7h
0x18001bf72  jmp     loc_18001BED3
0x18001bf77  cmp     rax, rcx
0x18001bf7a  jz      short loc_18001BF10
0x18001bf7c  xor     edx, edx; Val
0x18001bf7e  lea     rcx, [rsp+0F8h+var_A8]; void *
0x18001bf83  mov     r8d, 98h; Size
0x18001bf89  call    memset_0
0x18001bf8e  lea     rcx, [rsp+0F8h+var_A8]; this
0x18001bf93  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18001bf99  mov     rbx, cs:WPP_GLOBAL_Control
0x18001bfa0  lea     rsi, WPP_GLOBAL_Control
0x18001bfa7  cmp     rbx, rsi
0x18001bfaa  jz      short loc_18001BFD5
0x18001bfac  test    rbx, rbx
0x18001bfaf  jz      short loc_18001BFCE
0x18001bfb1  xor     edi, edi
0x18001bfb3  mov     rcx, [rbx+8]; RegistrationHandle
0x18001bfb7  test    rcx, rcx
0x18001bfba  jz      short loc_18001BFC6
0x18001bfbc  call    cs:__imp_UnregisterTraceGuids
0x18001bfc2  mov     [rbx+8], rdi
0x18001bfc6  mov     rbx, [rbx]
0x18001bfc9  test    rbx, rbx
0x18001bfcc  jnz     short loc_18001BFB3
0x18001bfce  mov     cs:WPP_GLOBAL_Control, rsi
0x18001bfd5  call    McGenEventUnregister_EventUnregister
0x18001bfda  mov     ecx, cs:?g_dwTlsCloudAPIndex@@3KA; dwTlsIndex
0x18001bfe0  cmp     ecx, 0FFFFFFFFh
0x18001bfe3  jz      loc_18001BDC2
0x18001bfe9  call    cs:__imp_TlsFree
0x18001bfef  jmp     loc_18001BDC2
```

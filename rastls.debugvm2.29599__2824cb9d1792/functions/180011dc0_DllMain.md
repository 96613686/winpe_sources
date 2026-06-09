# DllMain

- ea: `0x180011dc0`
- end: `0x180012085`
- name: `DllMain`
- size: `709`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800354e4`

## callees

- `0x180011dc0`
- `0x18001208c`
- `0x1800120c4`
- `0x1800120f0`
- `0x180035680`
- `0x180036254`
- `0x18003b6e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180011df0`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180011df0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180011dfd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180011e1b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180011dfd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180011e1b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011fd7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012007`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001207a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011fd7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012007`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001207a`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180011f05`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180011f05`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180011f26`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180011f26`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x180011eaa`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x180011eaa`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18001200f`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18001200f`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  ULONG64 *v4; // rbx
  const GUID **v5; // rsi
  const GUID *v6; // r8
  struct _EAPTLS_CONTROL_BLOCK *v8; // rbx
  TRACEHANDLE v9; // rcx
  const struct wil::FailureInfo *v10; // rdx
  const struct wil::FailureInfo *v11; // rdx
  _BYTE v12[160]; // [rsp+40h] [rbp-C8h] BYREF
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+E0h] [rbp-28h] BYREF

  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    InitializeCriticalSection(&g_csPeapInitializationLock);
    g_hInstance = hinstDLL;
    g_csPeapInitLockInitialized = 1;
    InitializeCriticalSection(&g_csPeapInnerMethodInitLock);
    qword_1800A5DD0 = 1;
    qword_1800A5DC8 = 0;
    v4 = (ULONG64 *)&WPP_MAIN_CB;
    WPP_MAIN_CB = 0;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_EapHostCtlGuid;
    v5 = (const GUID **)&WPP_REGISTRATION_GUIDS;
    WPP_GLOBAL_Control = (struct _EAPTLS_CONTROL_BLOCK *)&WPP_MAIN_CB;
    do
    {
      v6 = *v5;
      TraceGuidReg.Guid = v6;
      ++v5;
      TraceGuidReg.RegHandle = 0;
      v4[4] = (ULONG64)v6;
      RegisterTraceGuidsW(WppControlCallback, v4, v6, 1u, &TraceGuidReg, 0, 0, v4 + 1);
      v4 = (ULONG64 *)*v4;
    }
    while ( v4 );
    McGenEventRegister_EventRegister();
    TraceGuidReg = *(struct _TRACE_GUID_REGISTRATION *)&(*off_18009D3E8)[-8];
    if ( RegHandle )
      __fastfail(5u);
    xmmword_18009D408 = 0;
    if ( !EventRegister((LPCGUID)&TraceGuidReg, tlgEnableCallback, &dword_18009D3E0, &RegHandle) )
      EventSetInformation(RegHandle, 2, (__int16 *)off_18009D3E8, *(unsigned __int16 *)off_18009D3E8);
    if ( wil::details::g_pfnTelemetryCallback
      && (void (__fastcall *)(bool, const struct wil::FailureInfo *))wil::details::g_pfnTelemetryCallback != EapTlsTelemetry::FallbackTelemetryCallback )
    {
      memset_0(v12, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v12, v10);
    }
    wil::details::g_pfnTelemetryCallback = (__int64)EapTlsTelemetry::FallbackTelemetryCallback;
    if ( wil::details::g_pfnLoggingCallback
      && (void (__fastcall *)(const struct wil::FailureInfo *))wil::details::g_pfnLoggingCallback != ResultLoggingCallback )
    {
      memset_0(v12, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v12, v11);
    }
    wil::details::g_pfnLoggingCallback = (__int64)ResultLoggingCallback;
  }
  else if ( !fdwReason )
  {
    McGenEventUnregister_EventUnregister(hinstDLL, fdwReason, lpvReserved);
    TraceLoggingUnregister_EventUnregister(&dword_18009D3E0);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      if ( WPP_GLOBAL_Control )
      {
        do
        {
          v9 = *((_QWORD *)v8 + 1);
          if ( v9 )
          {
            UnregisterTraceGuids(v9);
            *((_QWORD *)v8 + 1) = 0;
          }
          v8 = *(struct _EAPTLS_CONTROL_BLOCK **)v8;
        }
        while ( v8 );
      }
      WPP_GLOBAL_Control = (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control;
    }
    if ( g_fProtectCachedCredentialsLockInitialized )
      DeleteCriticalSection(&g_csProtectCachedCredentials);
    if ( g_csPeapInitLockInitialized )
      DeleteCriticalSection(&g_csPeapInitializationLock);
    DeleteCriticalSection(&g_csPeapInnerMethodInitLock);
  }
  return 1;
}

```

## disassembly

```asm
0x180011dc0  mov     [rsp+arg_8], rbx
0x180011dc5  mov     [rsp+arg_10], rsi
0x180011dca  push    rdi
0x180011dcb  sub     rsp, 100h
0x180011dd2  mov     rax, cs:__security_cookie
0x180011dd9  xor     rax, rsp
0x180011ddc  mov     [rsp+108h+var_18], rax
0x180011de4  mov     rbx, rcx
0x180011de7  cmp     edx, 1
0x180011dea  jnz     loc_180011F92
0x180011df0  call    cs:__imp_DisableThreadLibraryCalls
0x180011df6  lea     rcx, ?g_csPeapInitializationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180011dfd  call    cs:__imp_InitializeCriticalSection
0x180011e03  lea     rcx, ?g_csPeapInnerMethodInitLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180011e0a  mov     cs:?g_hInstance@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hInstance
0x180011e11  mov     cs:?g_csPeapInitLockInitialized@@3HA, 1; int g_csPeapInitLockInitialized
0x180011e1b  call    cs:__imp_InitializeCriticalSection
0x180011e21  xor     edi, edi
0x180011e23  mov     cs:qword_1800A5DD0, 1
0x180011e2e  lea     rax, WPP_ThisDir_CTLGUID_EapHostCtlGuid
0x180011e35  mov     cs:qword_1800A5DC8, rdi
0x180011e3c  lea     rbx, WPP_MAIN_CB
0x180011e43  mov     cs:WPP_MAIN_CB, rdi
0x180011e4a  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180011e51  lea     rsi, WPP_REGISTRATION_GUIDS
0x180011e58  mov     cs:WPP_GLOBAL_Control, rbx
0x180011e5f  mov     r8, [rsi]; ControlGuid
0x180011e62  lea     rax, [rbx+8]
0x180011e66  mov     [rsp+108h+RegistrationHandle], rax; RegistrationHandle
0x180011e6b  lea     rcx, WppControlCallback; RequestAddress
0x180011e72  mov     [rsp+108h+MofResourceName], rdi; MofResourceName
0x180011e77  lea     rax, [rsp+108h+var_28]
0x180011e7f  mov     [rsp+108h+var_28.Guid], r8
0x180011e87  lea     rsi, [rsi+8]
0x180011e8b  mov     [rsp+108h+var_28.RegHandle], rdi
0x180011e93  mov     r9d, 1; GuidCount
0x180011e99  mov     [rsp+108h+MofImagePath], rdi; MofImagePath
0x180011e9e  mov     rdx, rbx; RequestContext
0x180011ea1  mov     [rsp+108h+TraceGuidReg], rax; TraceGuidReg
0x180011ea6  mov     [rbx+20h], r8
0x180011eaa  call    cs:__imp_RegisterTraceGuidsW
0x180011eb0  mov     rbx, [rbx]
0x180011eb3  test    rbx, rbx
0x180011eb6  jnz     short loc_180011E5F
0x180011eb8  call    McGenEventRegister_EventRegister
0x180011ebd  cmp     cs:RegHandle, rdi
0x180011ec4  mov     rax, cs:off_18009D3E8
0x180011ecb  movups  xmm0, xmmword ptr [rax-10h]
0x180011ecf  movups  xmmword ptr [rsp+108h+var_28.Guid], xmm0
0x180011ed7  jnz     loc_18001201B
0x180011edd  xorps   xmm0, xmm0
0x180011ee0  lea     r9, RegHandle; RegHandle
0x180011ee7  lea     r8, dword_18009D3E0; CallbackContext
0x180011eee  lea     rdx, _tlgEnableCallback; EnableCallback
0x180011ef5  lea     rcx, [rsp+108h+var_28]; ProviderId
0x180011efd  movdqu  cs:xmmword_18009D408, xmm0
0x180011f05  call    cs:__imp_EventRegister
0x180011f0b  test    eax, eax
0x180011f0d  jnz     short loc_180011F2C
0x180011f0f  mov     r8, cs:off_18009D3E8
0x180011f16  mov     edx, 2
0x180011f1b  mov     rcx, cs:RegHandle
0x180011f22  movzx   r9d, word ptr [r8]
0x180011f26  call    cs:__imp_EventSetInformation
0x180011f2c  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180011f33  lea     rcx, ?FallbackTelemetryCallback@EapTlsTelemetry@@SAX_NAEBUFailureInfo@wil@@@Z; EapTlsTelemetry::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x180011f3a  test    rax, rax
0x180011f3d  jnz     loc_180012027
0x180011f43  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180011f4a  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rcx
0x180011f51  lea     rcx, ?ResultLoggingCallback@@YAXAEBUFailureInfo@wil@@@Z; ResultLoggingCallback(wil::FailureInfo const &)
0x180011f58  test    rax, rax
0x180011f5b  jnz     loc_18001204D
0x180011f61  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, rcx
0x180011f68  mov     eax, 1
0x180011f6d  mov     rcx, [rsp+108h+var_18]
0x180011f75  xor     rcx, rsp; StackCookie
0x180011f78  call    __security_check_cookie
0x180011f7d  lea     r11, [rsp+108h+var_8]
0x180011f85  mov     rbx, [r11+18h]
0x180011f89  mov     rsi, [r11+20h]
0x180011f8d  mov     rsp, r11
0x180011f90  pop     rdi
0x180011f91  retn
0x180011f92  test    edx, edx
0x180011f94  jnz     short loc_180011F68
0x180011f96  call    McGenEventUnregister_EventUnregister
0x180011f9b  lea     rcx, dword_18009D3E0
0x180011fa2  call    TraceLoggingUnregister_EventUnregister
0x180011fa7  mov     rbx, cs:WPP_GLOBAL_Control
0x180011fae  lea     rsi, WPP_GLOBAL_Control
0x180011fb5  cmp     rbx, rsi
0x180011fb8  jnz     short loc_180011FDF
0x180011fba  cmp     cs:?g_fProtectCachedCredentialsLockInitialized@@3HA, 0; int g_fProtectCachedCredentialsLockInitialized
0x180011fc1  jnz     loc_180012073
0x180011fc7  cmp     cs:?g_csPeapInitLockInitialized@@3HA, 0; int g_csPeapInitLockInitialized
0x180011fce  jnz     short loc_180012000
0x180011fd0  lea     rcx, ?g_csPeapInnerMethodInitLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180011fd7  call    cs:__imp_DeleteCriticalSection
0x180011fdd  jmp     short loc_180011F68
0x180011fdf  test    rbx, rbx
0x180011fe2  jz      short loc_180011FF7
0x180011fe4  xor     edi, edi
0x180011fe6  mov     rcx, [rbx+8]; RegistrationHandle
0x180011fea  test    rcx, rcx
0x180011fed  jnz     short loc_18001200F
0x180011fef  mov     rbx, [rbx]
0x180011ff2  test    rbx, rbx
0x180011ff5  jnz     short loc_180011FE6
0x180011ff7  mov     cs:WPP_GLOBAL_Control, rsi
0x180011ffe  jmp     short loc_180011FBA
0x180012000  lea     rcx, ?g_csPeapInitializationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180012007  call    cs:__imp_DeleteCriticalSection
0x18001200d  jmp     short loc_180011FD0
0x18001200f  call    cs:__imp_UnregisterTraceGuids
0x180012015  mov     [rbx+8], rdi
0x180012019  jmp     short loc_180011FEF
0x18001201b  mov     ecx, 5
0x180012020  int     29h; Win8: RtlFailFast(ecx)
0x180012022  jmp     loc_180011EDD
0x180012027  cmp     rax, rcx
0x18001202a  jz      loc_180011F43
0x180012030  xor     edx, edx; Val
0x180012032  lea     rcx, [rsp+108h+var_C8]; void *
0x180012037  mov     r8d, 98h; Size
0x18001203d  call    memset_0
0x180012042  lea     rcx, [rsp+108h+var_C8]; this
0x180012047  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18001204d  cmp     rax, rcx
0x180012050  jz      loc_180011F61
0x180012056  xor     edx, edx; Val
0x180012058  lea     rcx, [rsp+108h+var_C8]; void *
0x18001205d  mov     r8d, 98h; Size
0x180012063  call    memset_0
0x180012068  lea     rcx, [rsp+108h+var_C8]; this
0x18001206d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180012073  lea     rcx, ?g_csProtectCachedCredentials@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001207a  call    cs:__imp_DeleteCriticalSection
0x180012080  jmp     loc_180011FC7
```

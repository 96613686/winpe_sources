# DllMain

- ea: `0x180007d1c`
- end: `0x180007db3`
- name: `DllMain`
- size: `151`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002044`

## callees

- `0x180002b78`
- `0x180007950`
- `0x180007d1c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180007d28`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180007d28`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  const struct wil::FailureInfo *v4; // rdx
  const struct wil::FailureInfo *v5; // rdx
  _BYTE v6[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    if ( wil::details::g_pfnTelemetryCallback
      && (char *)wil::details::g_pfnTelemetryCallback != (char *)winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::FallbackTelemetryCallback )
    {
      memset_0(v6, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v6, v4);
    }
    wil::details::g_pfnTelemetryCallback = (__int64 (__fastcall *)(_QWORD, _QWORD))winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::FallbackTelemetryCallback;
    if ( wil::details::g_pfnEapErrorLoggingCallback
      && (void (__fastcall *)(const struct _EAP_ERROR *))wil::details::g_pfnEapErrorLoggingCallback != winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::EapError )
    {
      memset_0(v6, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v6, v5);
    }
    wil::details::g_pfnEapErrorLoggingCallback = (__int64)winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::EapError;
  }
  return 1;
}

```

## disassembly

```asm
0x180007d1c  sub     rsp, 0C8h
0x180007d23  cmp     edx, 1
0x180007d26  jnz     short loc_180007D6C
0x180007d28  call    cs:__imp_DisableThreadLibraryCalls
0x180007d2e  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180007d35  lea     rcx, ?FallbackTelemetryCallback@EapPrivateUtilTelemetry@implementation@Utility@Eap@Internal@Windows@winrt@@SAX_NAEBUFailureInfo@wil@@@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x180007d3c  test    rax, rax
0x180007d3f  jz      short loc_180007D46
0x180007d41  cmp     rax, rcx
0x180007d44  jnz     short loc_180007D79
0x180007d46  mov     rax, cs:?g_pfnEapErrorLoggingCallback@details@wil@@3P6AXAEBU_EAP_ERROR@@@_EEA
0x180007d4d  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rcx
0x180007d54  lea     rcx, ?EapError@EapPrivateUtilTelemetry@implementation@Utility@Eap@Internal@Windows@winrt@@SAXAEBU_EAP_ERROR@@@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::EapError(_EAP_ERROR const &)
0x180007d5b  test    rax, rax
0x180007d5e  jz      short loc_180007D65
0x180007d60  cmp     rax, rcx
0x180007d63  jnz     short loc_180007D96
0x180007d65  mov     cs:?g_pfnEapErrorLoggingCallback@details@wil@@3P6AXAEBU_EAP_ERROR@@@_EEA, rcx
0x180007d6c  mov     eax, 1
0x180007d71  add     rsp, 0C8h
0x180007d78  retn
0x180007d79  xor     edx, edx; Val
0x180007d7b  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180007d80  mov     r8d, 98h; Size
0x180007d86  call    memset_0
0x180007d8b  lea     rcx, [rsp+0C8h+var_A8]; this
0x180007d90  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180007d96  xor     edx, edx; Val
0x180007d98  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180007d9d  mov     r8d, 98h; Size
0x180007da3  call    memset_0
0x180007da8  lea     rcx, [rsp+0C8h+var_A8]; this
0x180007dad  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```

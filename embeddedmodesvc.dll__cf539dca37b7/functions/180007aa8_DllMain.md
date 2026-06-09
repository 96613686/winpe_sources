# DllMain

- ea: `0x180007aa8`
- end: `0x180007b03`
- name: `DllMain`
- size: `91`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002984`

## callees

- `0x1800035a0`
- `0x1800068e8`
- `0x180007aa8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180007af0`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180007af0`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  const struct wil::FailureInfo *v3; // rdx
  _BYTE v5[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( fdwReason == 1 )
  {
    if ( wil::details::g_pfnTelemetryCallback
      && (void (__fastcall *)(__int64, const struct wil::FailureInfo *))wil::details::g_pfnTelemetryCallback != Microsoft::IoT::ShellExtension::CTelemetryProvider::FallbackTelemetryCallback )
    {
      memset_0(v5, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v5, v3);
    }
    wil::details::g_pfnTelemetryCallback = (__int64)Microsoft::IoT::ShellExtension::CTelemetryProvider::FallbackTelemetryCallback;
    DisableThreadLibraryCalls(hinstDLL);
  }
  return 1;
}

```

## disassembly

```asm
0x180007aa8  sub     rsp, 0C8h
0x180007aaf  cmp     edx, 1
0x180007ab2  jnz     short loc_180007AF6
0x180007ab4  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180007abb  lea     rdx, ?FallbackTelemetryCallback@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAX_NAEBUFailureInfo@wil@@@Z; Microsoft::IoT::ShellExtension::CTelemetryProvider::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x180007ac2  test    rax, rax
0x180007ac5  jz      short loc_180007AE9
0x180007ac7  cmp     rax, rdx
0x180007aca  jz      short loc_180007AE9
0x180007acc  xor     edx, edx; Val
0x180007ace  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180007ad3  mov     r8d, 98h; Size
0x180007ad9  call    memset_0
0x180007ade  lea     rcx, [rsp+0C8h+var_A8]; this
0x180007ae3  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180007ae9  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rdx
0x180007af0  call    cs:__imp_DisableThreadLibraryCalls
0x180007af6  mov     eax, 1
0x180007afb  add     rsp, 0C8h
0x180007b02  retn
```

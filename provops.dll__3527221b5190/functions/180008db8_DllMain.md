# DllMain

- ea: `0x180008db8`
- end: `0x180008e24`
- name: `DllMain`
- size: `108`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180003234`

## callees

- `0x1800083c0`
- `0x180008db8`
- `0x180033e9a`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180008dc8`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180008dc8`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  const struct wil::FailureInfo *v4; // rdx
  _BYTE v5[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      if ( wil::details::g_pfnLoggingCallback
        && (char *)wil::details::g_pfnLoggingCallback != (char *)Windows::Internal::Management::Provisioning::Logging::DefaultResultMacrosLoggingCallback )
      {
        memset_0(v5, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v5, v4);
      }
      wil::details::g_pfnLoggingCallback = (__int64 (__fastcall *)(_QWORD))Windows::Internal::Management::Provisioning::Logging::DefaultResultMacrosLoggingCallback;
    }
  }
  else
  {
    wil::details::g_pfnLoggingCallback = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180008db8  sub     rsp, 0C8h
0x180008dbf  test    edx, edx
0x180008dc1  jz      short loc_180008DEF
0x180008dc3  cmp     edx, 1
0x180008dc6  jnz     short loc_180008DFA
0x180008dc8  call    cs:__imp_DisableThreadLibraryCalls
0x180008dce  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008dd5  lea     rcx, ?DefaultResultMacrosLoggingCallback@Logging@Provisioning@Management@Internal@Windows@@YAXAEBUFailureInfo@wil@@@Z; Windows::Internal::Management::Provisioning::Logging::DefaultResultMacrosLoggingCallback(wil::FailureInfo const &)
0x180008ddc  test    rax, rax
0x180008ddf  jz      short loc_180008DE6
0x180008de1  cmp     rax, rcx
0x180008de4  jnz     short loc_180008E07
0x180008de6  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, rcx
0x180008ded  jmp     short loc_180008DFA
0x180008def  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, 0
0x180008dfa  mov     eax, 1
0x180008dff  add     rsp, 0C8h
0x180008e06  retn
0x180008e07  xor     edx, edx; Val
0x180008e09  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180008e0e  mov     r8d, 98h; Size
0x180008e14  call    memset_0
0x180008e19  lea     rcx, [rsp+0C8h+var_A8]; this
0x180008e1e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```

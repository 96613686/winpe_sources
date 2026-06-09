# DllMain

- ea: `0x18000aa48`
- end: `0x18000aaac`
- name: `DllMain`
- size: `100`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000f884`

## callees

- `0x18000aa48`
- `0x18001039c`
- `0x180011920`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000aa68`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000aa68`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  const struct wil::FailureInfo *v4; // rdx
  _BYTE v5[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( fdwReason == 1 )
  {
    g_hInstance = hinstDLL;
    DisableThreadLibraryCalls(hinstDLL);
    if ( wil::details::g_pfnTelemetryCallback
      && (char *)wil::details::g_pfnTelemetryCallback != (char *)ProfAPITelemetry::FallbackTelemetryCallback )
    {
      memset_0(v5, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v5, v4);
    }
    wil::details::g_pfnTelemetryCallback = (__int64 (__fastcall *)(_QWORD, _QWORD))ProfAPITelemetry::FallbackTelemetryCallback;
  }
  return 1;
}

```

## disassembly

```asm
0x18000aa48  sub     rsp, 0C8h
0x18000aa4f  cmp     edx, 1
0x18000aa52  jz      short loc_18000AA61
0x18000aa54  mov     eax, 1
0x18000aa59  add     rsp, 0C8h
0x18000aa60  retn
0x18000aa61  mov     cs:?g_hInstance@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hInstance
0x18000aa68  call    cs:__imp_DisableThreadLibraryCalls
0x18000aa6e  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000aa75  lea     rcx, ?FallbackTelemetryCallback@ProfAPITelemetry@@SAX_NAEBUFailureInfo@wil@@@Z; ProfAPITelemetry::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x18000aa7c  test    rax, rax
0x18000aa7f  jnz     short loc_18000AA8A
0x18000aa81  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rcx
0x18000aa88  jmp     short loc_18000AA54
0x18000aa8a  cmp     rax, rcx
0x18000aa8d  jz      short loc_18000AA81
0x18000aa8f  xor     edx, edx; Val
0x18000aa91  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000aa96  mov     r8d, 98h; Size
0x18000aa9c  call    memset_0
0x18000aaa1  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000aaa6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```

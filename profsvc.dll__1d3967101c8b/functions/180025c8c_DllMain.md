# DllMain

- ea: `0x180025c8c`
- end: `0x180025d6a`
- name: `DllMain`
- size: `222`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18003a5a4`

## callees

- `0x1800235cc`
- `0x180025c8c`
- `0x18003a730`
- `0x18003b310`
- `0x180042088`
- `0x1800420c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180025cbb`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180025cbb`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180025d31`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180025d31`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  const struct wil::FailureInfo *v4; // rdx
  _BYTE v6[160]; // [rsp+20h] [rbp-1D8h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+C0h] [rbp-138h] BYREF

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      g_hDllInstance = hinstDLL;
      McGenEventRegister_EtwEventRegister();
      if ( wil::details::g_pfnTelemetryCallback
        && (void (__fastcall *)(bool, const struct wil::FailureInfo *))wil::details::g_pfnTelemetryCallback != ProfileTelemetry::FallbackTelemetryCallback )
      {
        memset_0(v6, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v6, v4);
      }
      wil::details::g_pfnTelemetryCallback = (__int64)ProfileTelemetry::FallbackTelemetryCallback;
      memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
      VersionInformation.dwOSVersionInfoSize = 276;
      GetVersionExW(&VersionInformation);
      g_dwBuildNumber = LOWORD(VersionInformation.dwBuildNumber);
    }
  }
  else
  {
    McGenEventUnregister_EtwEventUnregister(hinstDLL, fdwReason, lpvReserved);
  }
  return 1;
}

```

## disassembly

```asm
0x180025c8c  push    rbx
0x180025c8e  sub     rsp, 1F0h
0x180025c95  mov     rax, cs:__security_cookie
0x180025c9c  xor     rax, rsp
0x180025c9f  mov     [rsp+1F8h+var_18], rax
0x180025ca7  mov     rbx, rcx
0x180025caa  test    edx, edx
0x180025cac  jz      loc_180025D47
0x180025cb2  cmp     edx, 1
0x180025cb5  jnz     loc_180025D4C
0x180025cbb  call    cs:__imp_DisableThreadLibraryCalls
0x180025cc1  mov     cs:?g_hDllInstance@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hDllInstance
0x180025cc8  call    McGenEventRegister_EtwEventRegister
0x180025ccd  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180025cd4  lea     rcx, ?FallbackTelemetryCallback@ProfileTelemetry@@SAX_NAEBUFailureInfo@wil@@@Z; ProfileTelemetry::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x180025cdb  test    rax, rax
0x180025cde  jz      short loc_180025D02
0x180025ce0  cmp     rax, rcx
0x180025ce3  jz      short loc_180025D02
0x180025ce5  xor     edx, edx; Val
0x180025ce7  lea     rcx, [rsp+1F8h+var_1D8]; void *
0x180025cec  mov     r8d, 98h; Size
0x180025cf2  call    memset_0
0x180025cf7  lea     rcx, [rsp+1F8h+var_1D8]; this
0x180025cfc  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180025d02  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rcx
0x180025d09  xor     edx, edx; Val
0x180025d0b  lea     rcx, [rsp+1F8h+VersionInformation.dwMajorVersion]; void *
0x180025d13  mov     r8d, 110h; Size
0x180025d19  call    memset_0
0x180025d1e  lea     rcx, [rsp+1F8h+VersionInformation]; lpVersionInformation
0x180025d26  mov     [rsp+1F8h+VersionInformation.dwOSVersionInfoSize], 114h
0x180025d31  call    cs:__imp_GetVersionExW
0x180025d37  movzx   eax, word ptr [rsp+1F8h+VersionInformation.dwBuildNumber]
0x180025d3f  mov     cs:?g_dwBuildNumber@@3KA, eax; ulong g_dwBuildNumber
0x180025d45  jmp     short loc_180025D4C
0x180025d47  call    McGenEventUnregister_EtwEventUnregister
0x180025d4c  mov     eax, 1
0x180025d51  mov     rcx, [rsp+1F8h+var_18]
0x180025d59  xor     rcx, rsp; StackCookie
0x180025d5c  call    __security_check_cookie
0x180025d61  add     rsp, 1F0h
0x180025d68  pop     rbx
0x180025d69  retn
```

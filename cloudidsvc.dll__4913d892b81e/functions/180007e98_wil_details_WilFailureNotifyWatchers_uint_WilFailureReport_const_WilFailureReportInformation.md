# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x180007e98`
- end: `0x180007f1e`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `134`
- prototype: `void __fastcall(wil::details *this, __int64, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006780`

## callees

- `0x180007e98`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007ee8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007ee8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007ecc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007ecc`

## string_xrefs

- `0x180007ec5`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::WilFailureNotifyWatchers(
        wil::details *this,
        __int64 a2,
        const struct WilFailureReport *a3,
        struct WilFailureReportInformation *a4)
{
  FARPROC ProcAddress; // rbx
  HMODULE ModuleHandleW; // rax

  ProcAddress = (FARPROC)`wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers;
  if ( `wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers )
    goto LABEL_6;
  ModuleHandleW = `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle;
  if ( `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle
    || (ModuleHandleW = GetModuleHandleW(L"kernelbase.dll"),
        (`wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle = ModuleHandleW) != 0) )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "WilFailureNotifyWatchers");
  }
  `wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers = (__int64)ProcAddress;
  if ( ProcAddress )
LABEL_6:
    ((void (__fastcall *)(_QWORD, __int64, const struct WilFailureReport *, struct WilFailureReportInformation *))ProcAddress)(
      0,
      a2,
      a3,
      a4);
}

```

## disassembly

```asm
0x180007e98  mov     [rsp+arg_0], rbx
0x180007e9d  mov     [rsp+arg_8], rsi
0x180007ea2  push    rdi
0x180007ea3  sub     rsp, 20h
0x180007ea7  mov     rdi, r8
0x180007eaa  mov     rsi, rdx
0x180007ead  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180007eb4  test    rbx, rbx
0x180007eb7  jnz     short loc_180007EFD
0x180007eb9  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180007ec0  test    rax, rax
0x180007ec3  jnz     short loc_180007EDE
0x180007ec5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180007ecc  call    cs:__imp_GetModuleHandleW
0x180007ed2  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180007ed9  test    rax, rax
0x180007edc  jz      short loc_180007EF1
0x180007ede  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180007ee5  mov     rcx, rax; hModule
0x180007ee8  call    cs:__imp_GetProcAddress
0x180007eee  mov     rbx, rax
0x180007ef1  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x180007ef8  test    rbx, rbx
0x180007efb  jz      short loc_180007F0E
0x180007efd  mov     r8, rdi
0x180007f00  mov     rdx, rsi
0x180007f03  xor     ecx, ecx
0x180007f05  mov     rax, rbx
0x180007f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f0d  nop
0x180007f0e  mov     rbx, [rsp+28h+arg_0]
0x180007f13  mov     rsi, [rsp+28h+arg_8]
0x180007f18  add     rsp, 20h
0x180007f1c  pop     rdi
0x180007f1d  retn
```

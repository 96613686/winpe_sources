# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x180006998`
- end: `0x180006a1e`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `134`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005b00`

## callees

- `0x180006998`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800069e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800069e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800069cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800069cc`

## string_xrefs

- `0x1800069c5`: `kernelbase.dll`

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
0x180006998  mov     [rsp+arg_0], rbx
0x18000699d  mov     [rsp+arg_8], rsi
0x1800069a2  push    rdi
0x1800069a3  sub     rsp, 20h
0x1800069a7  mov     rdi, r8
0x1800069aa  mov     rsi, rdx
0x1800069ad  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1800069b4  test    rbx, rbx
0x1800069b7  jnz     short loc_1800069FD
0x1800069b9  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800069c0  test    rax, rax
0x1800069c3  jnz     short loc_1800069DE
0x1800069c5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800069cc  call    cs:__imp_GetModuleHandleW
0x1800069d2  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800069d9  test    rax, rax
0x1800069dc  jz      short loc_1800069F1
0x1800069de  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x1800069e5  mov     rcx, rax; hModule
0x1800069e8  call    cs:__imp_GetProcAddress
0x1800069ee  mov     rbx, rax
0x1800069f1  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x1800069f8  test    rbx, rbx
0x1800069fb  jz      short loc_180006A0E
0x1800069fd  mov     r8, rdi
0x180006a00  mov     rdx, rsi
0x180006a03  xor     ecx, ecx
0x180006a05  mov     rax, rbx
0x180006a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a0d  nop
0x180006a0e  mov     rbx, [rsp+28h+arg_0]
0x180006a13  mov     rsi, [rsp+28h+arg_8]
0x180006a18  add     rsp, 20h
0x180006a1c  pop     rdi
0x180006a1d  retn
```

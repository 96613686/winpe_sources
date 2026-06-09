# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x180006f28`
- end: `0x180006fad`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `133`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800051f0`

## callees

- `0x180006f28`
- `0x18001c010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180006f5c`
- `KERNEL32!GetModuleHandleW` at `0x180006f5c`
- `KERNEL32!GetProcAddress` at `0x180006f78`
- `KERNEL32!GetProcAddress` at `0x180006f78`

## string_xrefs

- `0x180006f55`: `kernelbase.dll`

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
0x180006f28  mov     [rsp+arg_0], rbx
0x180006f2d  mov     [rsp+arg_8], rsi
0x180006f32  push    rdi
0x180006f33  sub     rsp, 20h
0x180006f37  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180006f3e  mov     rdi, r8
0x180006f41  mov     rsi, rdx
0x180006f44  test    rbx, rbx
0x180006f47  jnz     short loc_180006F8D
0x180006f49  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180006f50  test    rax, rax
0x180006f53  jnz     short loc_180006F6E
0x180006f55  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180006f5c  call    cs:__imp_GetModuleHandleW
0x180006f62  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180006f69  test    rax, rax
0x180006f6c  jz      short loc_180006F81
0x180006f6e  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180006f75  mov     rcx, rax; hModule
0x180006f78  call    cs:__imp_GetProcAddress
0x180006f7e  mov     rbx, rax
0x180006f81  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x180006f88  test    rbx, rbx
0x180006f8b  jz      short loc_180006F9D
0x180006f8d  mov     r8, rdi
0x180006f90  mov     rdx, rsi
0x180006f93  xor     ecx, ecx
0x180006f95  mov     rax, rbx
0x180006f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f9d  mov     rbx, [rsp+28h+arg_0]
0x180006fa2  mov     rsi, [rsp+28h+arg_8]
0x180006fa7  add     rsp, 20h
0x180006fab  pop     rdi
0x180006fac  retn
```

# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x180008a98`
- end: `0x180008b1d`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `133`
- prototype: `void __fastcall(wil::details *this, __int64, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008760`

## callees

- `0x180008a98`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008acc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008acc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008ae8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008ae8`

## string_xrefs

- `0x180008ac5`: `kernelbase.dll`

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
0x180008a98  mov     [rsp+arg_0], rbx
0x180008a9d  mov     [rsp+arg_8], rsi
0x180008aa2  push    rdi
0x180008aa3  sub     rsp, 20h
0x180008aa7  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180008aae  mov     rdi, r8
0x180008ab1  mov     rsi, rdx
0x180008ab4  test    rbx, rbx
0x180008ab7  jnz     short loc_180008AFD
0x180008ab9  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180008ac0  test    rax, rax
0x180008ac3  jnz     short loc_180008ADE
0x180008ac5  lea     rcx, ModuleName; "kernelbase.dll"
0x180008acc  call    cs:__imp_GetModuleHandleW
0x180008ad2  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180008ad9  test    rax, rax
0x180008adc  jz      short loc_180008AF1
0x180008ade  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x180008ae5  mov     rcx, rax; hModule
0x180008ae8  call    cs:__imp_GetProcAddress
0x180008aee  mov     rbx, rax
0x180008af1  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x180008af8  test    rbx, rbx
0x180008afb  jz      short loc_180008B0D
0x180008afd  mov     r8, rdi
0x180008b00  mov     rdx, rsi
0x180008b03  xor     ecx, ecx
0x180008b05  mov     rax, rbx
0x180008b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b0d  mov     rbx, [rsp+28h+arg_0]
0x180008b12  mov     rsi, [rsp+28h+arg_8]
0x180008b17  add     rsp, 20h
0x180008b1b  pop     rdi
0x180008b1c  retn
```

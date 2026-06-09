# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x180009158`
- end: `0x1800091de`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `134`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800082d0`

## callees

- `0x180009158`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000918c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000918c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800091a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800091a8`

## string_xrefs

- `0x180009185`: `kernelbase.dll`

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
0x180009158  mov     [rsp+arg_0], rbx
0x18000915d  mov     [rsp+arg_8], rsi
0x180009162  push    rdi
0x180009163  sub     rsp, 20h
0x180009167  mov     rdi, r8
0x18000916a  mov     rsi, rdx
0x18000916d  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180009174  test    rbx, rbx
0x180009177  jnz     short loc_1800091BD
0x180009179  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009180  test    rax, rax
0x180009183  jnz     short loc_18000919E
0x180009185  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000918c  call    cs:__imp_GetModuleHandleW
0x180009192  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009199  test    rax, rax
0x18000919c  jz      short loc_1800091B1
0x18000919e  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x1800091a5  mov     rcx, rax; hModule
0x1800091a8  call    cs:__imp_GetProcAddress
0x1800091ae  mov     rbx, rax
0x1800091b1  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x1800091b8  test    rbx, rbx
0x1800091bb  jz      short loc_1800091CE
0x1800091bd  mov     r8, rdi
0x1800091c0  mov     rdx, rsi
0x1800091c3  xor     ecx, ecx
0x1800091c5  mov     rax, rbx
0x1800091c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091cd  nop
0x1800091ce  mov     rbx, [rsp+28h+arg_0]
0x1800091d3  mov     rsi, [rsp+28h+arg_8]
0x1800091d8  add     rsp, 20h
0x1800091dc  pop     rdi
0x1800091dd  retn
```

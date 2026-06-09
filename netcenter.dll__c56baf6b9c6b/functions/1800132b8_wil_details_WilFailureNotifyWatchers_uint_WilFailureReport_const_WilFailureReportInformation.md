# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x1800132b8`
- end: `0x18001333e`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `134`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ce80`

## callees

- `0x1800132b8`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013308`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013308`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800132ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800132ec`

## string_xrefs

- `0x1800132e5`: `kernelbase.dll`

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
0x1800132b8  mov     [rsp+arg_0], rbx
0x1800132bd  mov     [rsp+arg_8], rsi
0x1800132c2  push    rdi
0x1800132c3  sub     rsp, 20h
0x1800132c7  mov     rdi, r8
0x1800132ca  mov     rsi, rdx
0x1800132cd  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1800132d4  test    rbx, rbx
0x1800132d7  jnz     short loc_18001331D
0x1800132d9  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800132e0  test    rax, rax
0x1800132e3  jnz     short loc_1800132FE
0x1800132e5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800132ec  call    cs:__imp_GetModuleHandleW
0x1800132f2  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800132f9  test    rax, rax
0x1800132fc  jz      short loc_180013311
0x1800132fe  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180013305  mov     rcx, rax; hModule
0x180013308  call    cs:__imp_GetProcAddress
0x18001330e  mov     rbx, rax
0x180013311  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x180013318  test    rbx, rbx
0x18001331b  jz      short loc_18001332E
0x18001331d  mov     r8, rdi
0x180013320  mov     rdx, rsi
0x180013323  xor     ecx, ecx
0x180013325  mov     rax, rbx
0x180013328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001332d  nop
0x18001332e  mov     rbx, [rsp+28h+arg_0]
0x180013333  mov     rsi, [rsp+28h+arg_8]
0x180013338  add     rsp, 20h
0x18001333c  pop     rdi
0x18001333d  retn
```

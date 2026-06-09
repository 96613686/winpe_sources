# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x180017a98`
- end: `0x180017b1e`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `134`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180015f90`

## callees

- `0x180017a98`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017ae8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017ae8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180017acc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180017acc`

## string_xrefs

- `0x180017ac5`: `kernelbase.dll`

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
0x180017a98  mov     [rsp+arg_0], rbx
0x180017a9d  mov     [rsp+arg_8], rsi
0x180017aa2  push    rdi
0x180017aa3  sub     rsp, 20h
0x180017aa7  mov     rdi, r8
0x180017aaa  mov     rsi, rdx
0x180017aad  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180017ab4  test    rbx, rbx
0x180017ab7  jnz     short loc_180017AFD
0x180017ab9  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180017ac0  test    rax, rax
0x180017ac3  jnz     short loc_180017ADE
0x180017ac5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180017acc  call    cs:__imp_GetModuleHandleW
0x180017ad2  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180017ad9  test    rax, rax
0x180017adc  jz      short loc_180017AF1
0x180017ade  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180017ae5  mov     rcx, rax; hModule
0x180017ae8  call    cs:__imp_GetProcAddress
0x180017aee  mov     rbx, rax
0x180017af1  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x180017af8  test    rbx, rbx
0x180017afb  jz      short loc_180017B0E
0x180017afd  mov     r8, rdi
0x180017b00  mov     rdx, rsi
0x180017b03  xor     ecx, ecx
0x180017b05  mov     rax, rbx
0x180017b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b0d  nop
0x180017b0e  mov     rbx, [rsp+28h+arg_0]
0x180017b13  mov     rsi, [rsp+28h+arg_8]
0x180017b18  add     rsp, 20h
0x180017b1c  pop     rdi
0x180017b1d  retn
```

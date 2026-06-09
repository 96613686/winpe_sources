# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x180003778`
- end: `0x1800037fe`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `134`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800031e0`

## callees

- `0x180003778`
- `0x18002f010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800037c8`
- `KERNEL32!GetProcAddress` at `0x1800037c8`
- `KERNEL32!GetModuleHandleW` at `0x1800037ac`
- `KERNEL32!GetModuleHandleW` at `0x1800037ac`

## string_xrefs

- `0x1800037a5`: `kernelbase.dll`

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
0x180003778  mov     [rsp+arg_0], rbx
0x18000377d  mov     [rsp+arg_8], rsi
0x180003782  push    rdi
0x180003783  sub     rsp, 20h
0x180003787  mov     rdi, r8
0x18000378a  mov     rsi, rdx
0x18000378d  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180003794  test    rbx, rbx
0x180003797  jnz     short loc_1800037DD
0x180003799  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800037a0  test    rax, rax
0x1800037a3  jnz     short loc_1800037BE
0x1800037a5  lea     rcx, ModuleName; "kernelbase.dll"
0x1800037ac  call    cs:__imp_GetModuleHandleW
0x1800037b2  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800037b9  test    rax, rax
0x1800037bc  jz      short loc_1800037D1
0x1800037be  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x1800037c5  mov     rcx, rax; hModule
0x1800037c8  call    cs:__imp_GetProcAddress
0x1800037ce  mov     rbx, rax
0x1800037d1  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x1800037d8  test    rbx, rbx
0x1800037db  jz      short loc_1800037EE
0x1800037dd  mov     r8, rdi
0x1800037e0  mov     rdx, rsi
0x1800037e3  xor     ecx, ecx
0x1800037e5  mov     rax, rbx
0x1800037e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037ed  nop
0x1800037ee  mov     rbx, [rsp+28h+arg_0]
0x1800037f3  mov     rsi, [rsp+28h+arg_8]
0x1800037f8  add     rsp, 20h
0x1800037fc  pop     rdi
0x1800037fd  retn
```

# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x1400051f8`
- end: `0x14000527d`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `133`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400046c0`

## callees

- `0x1400051f8`
- `0x140006010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140005248`
- `KERNEL32!GetProcAddress` at `0x140005248`
- `KERNEL32!GetModuleHandleW` at `0x14000522c`
- `KERNEL32!GetModuleHandleW` at `0x14000522c`

## string_xrefs

- `0x140005225`: `kernelbase.dll`

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
0x1400051f8  mov     [rsp+arg_0], rbx
0x1400051fd  mov     [rsp+arg_8], rsi
0x140005202  push    rdi
0x140005203  sub     rsp, 20h
0x140005207  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x14000520e  mov     rdi, r8
0x140005211  mov     rsi, rdx
0x140005214  test    rbx, rbx
0x140005217  jnz     short loc_14000525D
0x140005219  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140005220  test    rax, rax
0x140005223  jnz     short loc_14000523E
0x140005225  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000522c  call    cs:__imp_GetModuleHandleW
0x140005232  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140005239  test    rax, rax
0x14000523c  jz      short loc_140005251
0x14000523e  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x140005245  mov     rcx, rax; hModule
0x140005248  call    cs:__imp_GetProcAddress
0x14000524e  mov     rbx, rax
0x140005251  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x140005258  test    rbx, rbx
0x14000525b  jz      short loc_14000526D
0x14000525d  mov     r8, rdi
0x140005260  mov     rdx, rsi
0x140005263  xor     ecx, ecx
0x140005265  mov     rax, rbx
0x140005268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000526d  mov     rbx, [rsp+28h+arg_0]
0x140005272  mov     rsi, [rsp+28h+arg_8]
0x140005277  add     rsp, 20h
0x14000527b  pop     rdi
0x14000527c  retn
```

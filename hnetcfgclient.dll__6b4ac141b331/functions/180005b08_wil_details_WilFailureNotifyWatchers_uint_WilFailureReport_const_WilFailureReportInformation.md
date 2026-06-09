# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x180005b08`
- end: `0x180005b8e`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `134`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004c80`

## callees

- `0x180005b08`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005b3c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005b3c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005b58`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005b58`

## string_xrefs

- `0x180005b35`: `kernelbase.dll`

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
0x180005b08  mov     [rsp+arg_0], rbx
0x180005b0d  mov     [rsp+arg_8], rsi
0x180005b12  push    rdi
0x180005b13  sub     rsp, 20h
0x180005b17  mov     rdi, r8
0x180005b1a  mov     rsi, rdx
0x180005b1d  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180005b24  test    rbx, rbx
0x180005b27  jnz     short loc_180005B6D
0x180005b29  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180005b30  test    rax, rax
0x180005b33  jnz     short loc_180005B4E
0x180005b35  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180005b3c  call    cs:__imp_GetModuleHandleW
0x180005b42  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180005b49  test    rax, rax
0x180005b4c  jz      short loc_180005B61
0x180005b4e  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180005b55  mov     rcx, rax; hModule
0x180005b58  call    cs:__imp_GetProcAddress
0x180005b5e  mov     rbx, rax
0x180005b61  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x180005b68  test    rbx, rbx
0x180005b6b  jz      short loc_180005B7E
0x180005b6d  mov     r8, rdi
0x180005b70  mov     rdx, rsi
0x180005b73  xor     ecx, ecx
0x180005b75  mov     rax, rbx
0x180005b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b7d  nop
0x180005b7e  mov     rbx, [rsp+28h+arg_0]
0x180005b83  mov     rsi, [rsp+28h+arg_8]
0x180005b88  add     rsp, 20h
0x180005b8c  pop     rdi
0x180005b8d  retn
```

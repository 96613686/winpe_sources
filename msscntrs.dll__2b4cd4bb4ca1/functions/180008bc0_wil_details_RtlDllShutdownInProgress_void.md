# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180008bc0`
- end: `0x180008c17`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180008bc0`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008bfa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008bfa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008be3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008be3`

## string_xrefs

- `0x180008bdc`: `ntdll.dll`
- `0x180008bf0`: `RtlDllShutdownInProgress`

## pseudocode

```c
FARPROC __fastcall wil::details::RtlDllShutdownInProgress(wil::details *this)
{
  FARPROC result; // rax
  HMODULE ModuleHandleW; // rax

  result = (FARPROC)`wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress;
  if ( `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress )
    return (FARPROC)((__int64 (__fastcall *)(wil::details *))result)(this);
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  result = GetProcAddress(ModuleHandleW, "RtlDllShutdownInProgress");
  `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(wil::details *))result)(this);
  return result;
}

```

## disassembly

```asm
0x180008bc0  sub     rsp, 28h
0x180008bc4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180008bcb  test    rax, rax
0x180008bce  jnz     short loc_180008C0C
0x180008bd0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008bd7  test    rax, rax
0x180008bda  jnz     short loc_180008BF0
0x180008bdc  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180008be3  call    cs:__imp_GetModuleHandleW
0x180008be9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008bf0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180008bf7  mov     rcx, rax; hModule
0x180008bfa  call    cs:__imp_GetProcAddress
0x180008c00  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180008c07  test    rax, rax
0x180008c0a  jz      short loc_180008C12
0x180008c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c11  nop
0x180008c12  add     rsp, 28h
0x180008c16  retn
```

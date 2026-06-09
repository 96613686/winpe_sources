# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1800082a0`
- end: `0x1800082f7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800082a0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800082da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800082da`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800082c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800082c3`

## string_xrefs

- `0x1800082bc`: `ntdll.dll`
- `0x1800082d0`: `RtlDllShutdownInProgress`

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
0x1800082a0  sub     rsp, 28h
0x1800082a4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1800082ab  test    rax, rax
0x1800082ae  jnz     short loc_1800082EC
0x1800082b0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800082b7  test    rax, rax
0x1800082ba  jnz     short loc_1800082D0
0x1800082bc  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800082c3  call    cs:__imp_GetModuleHandleW
0x1800082c9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800082d0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1800082d7  mov     rcx, rax; hModule
0x1800082da  call    cs:__imp_GetProcAddress
0x1800082e0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1800082e7  test    rax, rax
0x1800082ea  jz      short loc_1800082F2
0x1800082ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082f1  nop
0x1800082f2  add     rsp, 28h
0x1800082f6  retn
```

# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1800094a0`
- end: `0x1800094f7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800094a0`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800094c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800094c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800094da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800094da`

## string_xrefs

- `0x1800094bc`: `ntdll.dll`
- `0x1800094d0`: `RtlDllShutdownInProgress`

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
0x1800094a0  sub     rsp, 28h
0x1800094a4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1800094ab  test    rax, rax
0x1800094ae  jnz     short loc_1800094EC
0x1800094b0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800094b7  test    rax, rax
0x1800094ba  jnz     short loc_1800094D0
0x1800094bc  lea     rcx, ModuleName; "ntdll.dll"
0x1800094c3  call    cs:__imp_GetModuleHandleW
0x1800094c9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800094d0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1800094d7  mov     rcx, rax; hModule
0x1800094da  call    cs:__imp_GetProcAddress
0x1800094e0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1800094e7  test    rax, rax
0x1800094ea  jz      short loc_1800094F2
0x1800094ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094f1  nop
0x1800094f2  add     rsp, 28h
0x1800094f6  retn
```

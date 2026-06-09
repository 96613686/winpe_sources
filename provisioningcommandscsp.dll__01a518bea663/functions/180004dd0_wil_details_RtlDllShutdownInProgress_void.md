# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180004dd0`
- end: `0x180004e27`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180004dd0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004df3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004df3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004e0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004e0a`

## string_xrefs

- `0x180004dec`: `ntdll.dll`
- `0x180004e00`: `RtlDllShutdownInProgress`

## pseudocode

```c
FARPROC __fastcall wil::details::RtlDllShutdownInProgress(wil::details *this)
{
  FARPROC result; // rax
  HMODULE ModuleHandleW; // rax

  result = (FARPROC)`wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress;
  if ( `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress )
    return (FARPROC)((__int64 (__fastcall *)(wil::details *))result)(this);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x180004dd0  sub     rsp, 28h
0x180004dd4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180004ddb  test    rax, rax
0x180004dde  jnz     short loc_180004E1C
0x180004de0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004de7  test    rax, rax
0x180004dea  jnz     short loc_180004E00
0x180004dec  lea     rcx, ModuleName; "ntdll.dll"
0x180004df3  call    cs:__imp_GetModuleHandleW
0x180004df9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004e00  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180004e07  mov     rcx, rax; hModule
0x180004e0a  call    cs:__imp_GetProcAddress
0x180004e10  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180004e17  test    rax, rax
0x180004e1a  jz      short loc_180004E22
0x180004e1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e21  nop
0x180004e22  add     rsp, 28h
0x180004e26  retn
```

# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180009c90`
- end: `0x180009cf4`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `100`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180009c90`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009cd0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009cd0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009cb3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009cb3`

## string_xrefs

- `0x180009cac`: `ntdll.dll`
- `0x180009cc6`: `RtlDllShutdownInProgress`

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
0x180009c90  sub     rsp, 28h
0x180009c94  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180009c9b  test    rax, rax
0x180009c9e  jnz     short loc_180009CE8
0x180009ca0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009ca7  test    rax, rax
0x180009caa  jnz     short loc_180009CC6
0x180009cac  lea     rcx, ModuleName; "ntdll.dll"
0x180009cb3  call    cs:__imp_GetModuleHandleW
0x180009cba  nop     dword ptr [rax+rax+00h]
0x180009cbf  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009cc6  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180009ccd  mov     rcx, rax; hModule
0x180009cd0  call    cs:__imp_GetProcAddress
0x180009cd7  nop     dword ptr [rax+rax+00h]
0x180009cdc  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180009ce3  test    rax, rax
0x180009ce6  jz      short loc_180009CEE
0x180009ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ced  nop
0x180009cee  add     rsp, 28h
0x180009cf2  retn
```

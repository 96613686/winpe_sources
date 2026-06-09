# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1800081f0`
- end: `0x180008247`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800081f0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000822a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000822a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008213`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008213`

## string_xrefs

- `0x18000820c`: `ntdll.dll`
- `0x180008220`: `RtlDllShutdownInProgress`

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
0x1800081f0  sub     rsp, 28h
0x1800081f4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1800081fb  test    rax, rax
0x1800081fe  jnz     short loc_18000823C
0x180008200  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008207  test    rax, rax
0x18000820a  jnz     short loc_180008220
0x18000820c  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180008213  call    cs:__imp_GetModuleHandleW
0x180008219  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008220  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180008227  mov     rcx, rax; hModule
0x18000822a  call    cs:__imp_GetProcAddress
0x180008230  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180008237  test    rax, rax
0x18000823a  jz      short loc_180008242
0x18000823c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008241  nop
0x180008242  add     rsp, 28h
0x180008246  retn
```

# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000a5e0`
- end: `0x18000a637`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000a5e0`
- `0x180061010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a603`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a603`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a61a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a61a`

## string_xrefs

- `0x18000a5fc`: `ntdll.dll`
- `0x18000a610`: `RtlDllShutdownInProgress`

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
0x18000a5e0  sub     rsp, 28h
0x18000a5e4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000a5eb  test    rax, rax
0x18000a5ee  jnz     short loc_18000A62C
0x18000a5f0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a5f7  test    rax, rax
0x18000a5fa  jnz     short loc_18000A610
0x18000a5fc  lea     rcx, ModuleName; "ntdll.dll"
0x18000a603  call    cs:__imp_GetModuleHandleW
0x18000a609  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a610  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000a617  mov     rcx, rax; hModule
0x18000a61a  call    cs:__imp_GetProcAddress
0x18000a620  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000a627  test    rax, rax
0x18000a62a  jz      short loc_18000A632
0x18000a62c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a631  nop
0x18000a632  add     rsp, 28h
0x18000a636  retn
```

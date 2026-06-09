# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180006750`
- end: `0x1800067a7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180006750`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000678a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000678a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006773`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006773`

## string_xrefs

- `0x18000676c`: `ntdll.dll`
- `0x180006780`: `RtlDllShutdownInProgress`

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
0x180006750  sub     rsp, 28h
0x180006754  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000675b  test    rax, rax
0x18000675e  jnz     short loc_18000679C
0x180006760  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006767  test    rax, rax
0x18000676a  jnz     short loc_180006780
0x18000676c  lea     rcx, ModuleName; "ntdll.dll"
0x180006773  call    cs:__imp_GetModuleHandleW
0x180006779  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006780  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180006787  mov     rcx, rax; hModule
0x18000678a  call    cs:__imp_GetProcAddress
0x180006790  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180006797  test    rax, rax
0x18000679a  jz      short loc_1800067A2
0x18000679c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067a1  nop
0x1800067a2  add     rsp, 28h
0x1800067a6  retn
```

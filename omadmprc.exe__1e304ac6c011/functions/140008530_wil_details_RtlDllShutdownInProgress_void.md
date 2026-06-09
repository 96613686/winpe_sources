# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x140008530`
- end: `0x140008594`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `100`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140008530`
- `0x140017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008553`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008553`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008570`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008570`

## string_xrefs

- `0x14000854c`: `ntdll.dll`
- `0x140008566`: `RtlDllShutdownInProgress`

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
0x140008530  sub     rsp, 28h
0x140008534  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14000853b  test    rax, rax
0x14000853e  jnz     short loc_140008588
0x140008540  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140008547  test    rax, rax
0x14000854a  jnz     short loc_140008566
0x14000854c  lea     rcx, ModuleName; "ntdll.dll"
0x140008553  call    cs:__imp_GetModuleHandleW
0x14000855a  nop     dword ptr [rax+rax+00h]
0x14000855f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140008566  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x14000856d  mov     rcx, rax; hModule
0x140008570  call    cs:__imp_GetProcAddress
0x140008577  nop     dword ptr [rax+rax+00h]
0x14000857c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x140008583  test    rax, rax
0x140008586  jz      short loc_14000858E
0x140008588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000858d  nop
0x14000858e  add     rsp, 28h
0x140008592  retn
```

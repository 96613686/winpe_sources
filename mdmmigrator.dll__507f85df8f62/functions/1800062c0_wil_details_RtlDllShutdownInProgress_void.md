# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1800062c0`
- end: `0x180006317`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800062c0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800062e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800062e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800062fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800062fa`

## string_xrefs

- `0x1800062dc`: `ntdll.dll`
- `0x1800062f0`: `RtlDllShutdownInProgress`

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
0x1800062c0  sub     rsp, 28h
0x1800062c4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1800062cb  test    rax, rax
0x1800062ce  jnz     short loc_18000630C
0x1800062d0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800062d7  test    rax, rax
0x1800062da  jnz     short loc_1800062F0
0x1800062dc  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800062e3  call    cs:__imp_GetModuleHandleW
0x1800062e9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800062f0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1800062f7  mov     rcx, rax; hModule
0x1800062fa  call    cs:__imp_GetProcAddress
0x180006300  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180006307  test    rax, rax
0x18000630a  jz      short loc_180006312
0x18000630c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006311  nop
0x180006312  add     rsp, 28h
0x180006316  retn
```

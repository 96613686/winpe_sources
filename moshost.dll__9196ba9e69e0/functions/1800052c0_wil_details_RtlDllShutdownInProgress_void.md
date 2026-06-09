# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1800052c0`
- end: `0x180005317`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800052c0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800052fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800052fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800052e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800052e3`

## string_xrefs

- `0x1800052dc`: `ntdll.dll`
- `0x1800052f0`: `RtlDllShutdownInProgress`

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
0x1800052c0  sub     rsp, 28h
0x1800052c4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1800052cb  test    rax, rax
0x1800052ce  jnz     short loc_18000530C
0x1800052d0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800052d7  test    rax, rax
0x1800052da  jnz     short loc_1800052F0
0x1800052dc  lea     rcx, ModuleName; "ntdll.dll"
0x1800052e3  call    cs:__imp_GetModuleHandleW
0x1800052e9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800052f0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1800052f7  mov     rcx, rax; hModule
0x1800052fa  call    cs:__imp_GetProcAddress
0x180005300  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180005307  test    rax, rax
0x18000530a  jz      short loc_180005312
0x18000530c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005311  nop
0x180005312  add     rsp, 28h
0x180005316  retn
```

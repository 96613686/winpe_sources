# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1800056f0`
- end: `0x180005747`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800056f0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005713`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005713`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000572a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000572a`

## string_xrefs

- `0x18000570c`: `ntdll.dll`
- `0x180005720`: `RtlDllShutdownInProgress`

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
0x1800056f0  sub     rsp, 28h
0x1800056f4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1800056fb  test    rax, rax
0x1800056fe  jnz     short loc_18000573C
0x180005700  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005707  test    rax, rax
0x18000570a  jnz     short loc_180005720
0x18000570c  lea     rcx, ModuleName; "ntdll.dll"
0x180005713  call    cs:__imp_GetModuleHandleW
0x180005719  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005720  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180005727  mov     rcx, rax; hModule
0x18000572a  call    cs:__imp_GetProcAddress
0x180005730  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180005737  test    rax, rax
0x18000573a  jz      short loc_180005742
0x18000573c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005741  nop
0x180005742  add     rsp, 28h
0x180005746  retn
```

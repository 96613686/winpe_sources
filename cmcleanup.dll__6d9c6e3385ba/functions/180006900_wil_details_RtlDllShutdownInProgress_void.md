# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180006900`
- end: `0x180006957`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180006900`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000693a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000693a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006923`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006923`

## string_xrefs

- `0x18000691c`: `ntdll.dll`
- `0x180006930`: `RtlDllShutdownInProgress`

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
0x180006900  sub     rsp, 28h
0x180006904  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000690b  test    rax, rax
0x18000690e  jnz     short loc_18000694C
0x180006910  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006917  test    rax, rax
0x18000691a  jnz     short loc_180006930
0x18000691c  lea     rcx, ModuleName; "ntdll.dll"
0x180006923  call    cs:__imp_GetModuleHandleW
0x180006929  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006930  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180006937  mov     rcx, rax; hModule
0x18000693a  call    cs:__imp_GetProcAddress
0x180006940  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180006947  test    rax, rax
0x18000694a  jz      short loc_180006952
0x18000694c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006951  nop
0x180006952  add     rsp, 28h
0x180006956  retn
```

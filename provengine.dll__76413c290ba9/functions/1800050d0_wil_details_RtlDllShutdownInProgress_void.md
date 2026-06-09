# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1800050d0`
- end: `0x180005127`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800050d0`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000510a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000510a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800050f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800050f3`

## string_xrefs

- `0x1800050ec`: `ntdll.dll`
- `0x180005100`: `RtlDllShutdownInProgress`

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
0x1800050d0  sub     rsp, 28h
0x1800050d4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1800050db  test    rax, rax
0x1800050de  jnz     short loc_18000511C
0x1800050e0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800050e7  test    rax, rax
0x1800050ea  jnz     short loc_180005100
0x1800050ec  lea     rcx, ModuleName; "ntdll.dll"
0x1800050f3  call    cs:__imp_GetModuleHandleW
0x1800050f9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005100  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180005107  mov     rcx, rax; hModule
0x18000510a  call    cs:__imp_GetProcAddress
0x180005110  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180005117  test    rax, rax
0x18000511a  jz      short loc_180005122
0x18000511c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005121  nop
0x180005122  add     rsp, 28h
0x180005126  retn
```

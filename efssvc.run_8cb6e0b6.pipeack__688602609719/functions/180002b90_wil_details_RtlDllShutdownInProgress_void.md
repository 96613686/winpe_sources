# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180002b90`
- end: `0x180002bf7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `103`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180002b90`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002bb3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002bb3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002bd0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002bd0`

## string_xrefs

- `0x180002bac`: `ntdll.dll`
- `0x180002bc6`: `RtlDllShutdownInProgress`

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
0x180002b90  sub     rsp, 28h
0x180002b94  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180002b9b  test    rax, rax
0x180002b9e  jnz     short loc_180002BEE
0x180002ba0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180002ba7  test    rax, rax
0x180002baa  jnz     short loc_180002BC6
0x180002bac  lea     rcx, ModuleName; "ntdll.dll"
0x180002bb3  call    cs:__imp_GetModuleHandleW
0x180002bba  nop     dword ptr [rax+rax+00h]
0x180002bbf  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180002bc6  lea     rdx, ProcName; "RtlDllShutdownInProgress"
0x180002bcd  mov     rcx, rax; hModule
0x180002bd0  call    cs:__imp_GetProcAddress
0x180002bd7  nop     dword ptr [rax+rax+00h]
0x180002bdc  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180002be3  test    rax, rax
0x180002be6  jnz     short loc_180002BEE
0x180002be8  add     rsp, 28h
0x180002bec  retn
0x180002bee  add     rsp, 28h
0x180002bf2  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

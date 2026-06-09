# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180006cd0`
- end: `0x180006d37`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `103`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180006cd0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006d10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006d10`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006cf3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006cf3`

## string_xrefs

- `0x180006cec`: `ntdll.dll`
- `0x180006d06`: `RtlDllShutdownInProgress`

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
0x180006cd0  sub     rsp, 28h
0x180006cd4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180006cdb  test    rax, rax
0x180006cde  jnz     short loc_180006D2E
0x180006ce0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006ce7  test    rax, rax
0x180006cea  jnz     short loc_180006D06
0x180006cec  lea     rcx, ModuleName; "ntdll.dll"
0x180006cf3  call    cs:__imp_GetModuleHandleW
0x180006cfa  nop     dword ptr [rax+rax+00h]
0x180006cff  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006d06  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180006d0d  mov     rcx, rax; hModule
0x180006d10  call    cs:__imp_GetProcAddress
0x180006d17  nop     dword ptr [rax+rax+00h]
0x180006d1c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180006d23  test    rax, rax
0x180006d26  jnz     short loc_180006D2E
0x180006d28  add     rsp, 28h
0x180006d2c  retn
0x180006d2e  add     rsp, 28h
0x180006d32  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

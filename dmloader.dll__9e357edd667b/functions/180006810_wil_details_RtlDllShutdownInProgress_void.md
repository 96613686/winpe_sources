# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180006810`
- end: `0x18000686a`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `90`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180006810`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006833`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006833`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000684a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000684a`

## string_xrefs

- `0x18000682c`: `ntdll.dll`
- `0x180006840`: `RtlDllShutdownInProgress`

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
0x180006810  sub     rsp, 28h
0x180006814  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000681b  test    rax, rax
0x18000681e  jnz     short loc_180006861
0x180006820  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006827  test    rax, rax
0x18000682a  jnz     short loc_180006840
0x18000682c  lea     rcx, ModuleName; "ntdll.dll"
0x180006833  call    cs:__imp_GetModuleHandleW
0x180006839  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006840  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180006847  mov     rcx, rax; hModule
0x18000684a  call    cs:__imp_GetProcAddress
0x180006850  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180006857  test    rax, rax
0x18000685a  jnz     short loc_180006861
0x18000685c  add     rsp, 28h
0x180006860  retn
0x180006861  add     rsp, 28h
0x180006865  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

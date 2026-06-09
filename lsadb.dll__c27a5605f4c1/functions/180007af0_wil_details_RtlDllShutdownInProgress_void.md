# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180007af0`
- end: `0x180007b4a`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `90`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180007af0`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007b13`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007b13`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007b2a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007b2a`

## string_xrefs

- `0x180007b0c`: `ntdll.dll`
- `0x180007b20`: `RtlDllShutdownInProgress`

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
0x180007af0  sub     rsp, 28h
0x180007af4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180007afb  test    rax, rax
0x180007afe  jnz     short loc_180007B41
0x180007b00  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007b07  test    rax, rax
0x180007b0a  jnz     short loc_180007B20
0x180007b0c  lea     rcx, ModuleName; "ntdll.dll"
0x180007b13  call    cs:__imp_GetModuleHandleW
0x180007b19  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007b20  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180007b27  mov     rcx, rax; hModule
0x180007b2a  call    cs:__imp_GetProcAddress
0x180007b30  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180007b37  test    rax, rax
0x180007b3a  jnz     short loc_180007B41
0x180007b3c  add     rsp, 28h
0x180007b40  retn
0x180007b41  add     rsp, 28h
0x180007b45  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

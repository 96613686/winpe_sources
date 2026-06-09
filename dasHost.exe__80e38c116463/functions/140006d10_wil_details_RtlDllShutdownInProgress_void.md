# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x140006d10`
- end: `0x140006d67`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140006d10`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006d33`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006d33`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006d4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006d4a`

## string_xrefs

- `0x140006d2c`: `ntdll.dll`
- `0x140006d40`: `RtlDllShutdownInProgress`

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
0x140006d10  sub     rsp, 28h
0x140006d14  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x140006d1b  test    rax, rax
0x140006d1e  jnz     short loc_140006D5C
0x140006d20  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140006d27  test    rax, rax
0x140006d2a  jnz     short loc_140006D40
0x140006d2c  lea     rcx, ModuleName; "ntdll.dll"
0x140006d33  call    cs:__imp_GetModuleHandleW
0x140006d39  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140006d40  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x140006d47  mov     rcx, rax; hModule
0x140006d4a  call    cs:__imp_GetProcAddress
0x140006d50  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x140006d57  test    rax, rax
0x140006d5a  jz      short loc_140006D62
0x140006d5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d61  nop
0x140006d62  add     rsp, 28h
0x140006d66  retn
```

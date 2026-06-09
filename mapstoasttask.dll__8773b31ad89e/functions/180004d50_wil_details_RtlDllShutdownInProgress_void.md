# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180004d50`
- end: `0x180004da7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180004d50`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004d73`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004d73`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004d8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004d8a`

## string_xrefs

- `0x180004d6c`: `ntdll.dll`
- `0x180004d80`: `RtlDllShutdownInProgress`

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
0x180004d50  sub     rsp, 28h
0x180004d54  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180004d5b  test    rax, rax
0x180004d5e  jnz     short loc_180004D9C
0x180004d60  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004d67  test    rax, rax
0x180004d6a  jnz     short loc_180004D80
0x180004d6c  lea     rcx, ModuleName; "ntdll.dll"
0x180004d73  call    cs:__imp_GetModuleHandleW
0x180004d79  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004d80  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180004d87  mov     rcx, rax; hModule
0x180004d8a  call    cs:__imp_GetProcAddress
0x180004d90  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180004d97  test    rax, rax
0x180004d9a  jz      short loc_180004DA2
0x180004d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004da1  nop
0x180004da2  add     rsp, 28h
0x180004da6  retn
```

# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180005c50`
- end: `0x180005cb4`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `100`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180005c50`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005c73`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005c73`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005c90`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005c90`

## string_xrefs

- `0x180005c6c`: `ntdll.dll`
- `0x180005c86`: `RtlDllShutdownInProgress`

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
0x180005c50  sub     rsp, 28h
0x180005c54  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180005c5b  test    rax, rax
0x180005c5e  jnz     short loc_180005CA8
0x180005c60  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005c67  test    rax, rax
0x180005c6a  jnz     short loc_180005C86
0x180005c6c  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180005c73  call    cs:__imp_GetModuleHandleW
0x180005c7a  nop     dword ptr [rax+rax+00h]
0x180005c7f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005c86  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180005c8d  mov     rcx, rax; hModule
0x180005c90  call    cs:__imp_GetProcAddress
0x180005c97  nop     dword ptr [rax+rax+00h]
0x180005c9c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180005ca3  test    rax, rax
0x180005ca6  jz      short loc_180005CAE
0x180005ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cad  nop
0x180005cae  add     rsp, 28h
0x180005cb2  retn
```

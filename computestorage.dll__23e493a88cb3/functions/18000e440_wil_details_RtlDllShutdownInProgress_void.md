# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000e440`
- end: `0x18000e4a4`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `100`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000e440`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e463`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e463`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e480`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e480`

## string_xrefs

- `0x18000e45c`: `ntdll.dll`
- `0x18000e476`: `RtlDllShutdownInProgress`

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
0x18000e440  sub     rsp, 28h
0x18000e444  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000e44b  test    rax, rax
0x18000e44e  jnz     short loc_18000E498
0x18000e450  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e457  test    rax, rax
0x18000e45a  jnz     short loc_18000E476
0x18000e45c  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000e463  call    cs:__imp_GetModuleHandleW
0x18000e46a  nop     dword ptr [rax+rax+00h]
0x18000e46f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e476  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000e47d  mov     rcx, rax; hModule
0x18000e480  call    cs:__imp_GetProcAddress
0x18000e487  nop     dword ptr [rax+rax+00h]
0x18000e48c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000e493  test    rax, rax
0x18000e496  jz      short loc_18000E49E
0x18000e498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e49d  nop
0x18000e49e  add     rsp, 28h
0x18000e4a2  retn
```

# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1800069a0`
- end: `0x180006a04`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `100`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800069a0`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800069e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800069e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800069c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800069c3`

## string_xrefs

- `0x1800069bc`: `ntdll.dll`
- `0x1800069d6`: `RtlDllShutdownInProgress`

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
0x1800069a0  sub     rsp, 28h
0x1800069a4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1800069ab  test    rax, rax
0x1800069ae  jnz     short loc_1800069F8
0x1800069b0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800069b7  test    rax, rax
0x1800069ba  jnz     short loc_1800069D6
0x1800069bc  lea     rcx, ModuleName; "ntdll.dll"
0x1800069c3  call    cs:__imp_GetModuleHandleW
0x1800069ca  nop     dword ptr [rax+rax+00h]
0x1800069cf  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800069d6  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1800069dd  mov     rcx, rax; hModule
0x1800069e0  call    cs:__imp_GetProcAddress
0x1800069e7  nop     dword ptr [rax+rax+00h]
0x1800069ec  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1800069f3  test    rax, rax
0x1800069f6  jz      short loc_1800069FE
0x1800069f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069fd  nop
0x1800069fe  add     rsp, 28h
0x180006a02  retn
```

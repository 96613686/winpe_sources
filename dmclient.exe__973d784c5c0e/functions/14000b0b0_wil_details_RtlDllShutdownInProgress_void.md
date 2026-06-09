# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x14000b0b0`
- end: `0x14000b114`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `100`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x14000b0b0`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b0f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b0f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b0d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b0d3`

## string_xrefs

- `0x14000b0cc`: `ntdll.dll`
- `0x14000b0e6`: `RtlDllShutdownInProgress`

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
0x14000b0b0  sub     rsp, 28h
0x14000b0b4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14000b0bb  test    rax, rax
0x14000b0be  jnz     short loc_14000B108
0x14000b0c0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b0c7  test    rax, rax
0x14000b0ca  jnz     short loc_14000B0E6
0x14000b0cc  lea     rcx, ModuleName; "ntdll.dll"
0x14000b0d3  call    cs:__imp_GetModuleHandleW
0x14000b0da  nop     dword ptr [rax+rax+00h]
0x14000b0df  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b0e6  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x14000b0ed  mov     rcx, rax; hModule
0x14000b0f0  call    cs:__imp_GetProcAddress
0x14000b0f7  nop     dword ptr [rax+rax+00h]
0x14000b0fc  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x14000b103  test    rax, rax
0x14000b106  jz      short loc_14000B10E
0x14000b108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b10d  nop
0x14000b10e  add     rsp, 28h
0x14000b112  retn
```

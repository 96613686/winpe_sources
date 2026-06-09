# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x14000b120`
- end: `0x14000b184`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `100`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x14000b120`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b160`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b160`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b143`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b143`

## string_xrefs

- `0x14000b13c`: `ntdll.dll`
- `0x14000b156`: `RtlDllShutdownInProgress`

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
0x14000b120  sub     rsp, 28h
0x14000b124  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14000b12b  test    rax, rax
0x14000b12e  jnz     short loc_14000B178
0x14000b130  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b137  test    rax, rax
0x14000b13a  jnz     short loc_14000B156
0x14000b13c  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x14000b143  call    cs:__imp_GetModuleHandleW
0x14000b14a  nop     dword ptr [rax+rax+00h]
0x14000b14f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b156  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x14000b15d  mov     rcx, rax; hModule
0x14000b160  call    cs:__imp_GetProcAddress
0x14000b167  nop     dword ptr [rax+rax+00h]
0x14000b16c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x14000b173  test    rax, rax
0x14000b176  jz      short loc_14000B17E
0x14000b178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b17d  nop
0x14000b17e  add     rsp, 28h
0x14000b182  retn
```

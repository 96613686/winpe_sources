# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1400055b0`
- end: `0x140005607`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1400055b0`
- `0x14000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400055d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400055d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400055ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400055ea`

## string_xrefs

- `0x1400055cc`: `ntdll.dll`
- `0x1400055e0`: `RtlDllShutdownInProgress`

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
0x1400055b0  sub     rsp, 28h
0x1400055b4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1400055bb  test    rax, rax
0x1400055be  jnz     short loc_1400055FC
0x1400055c0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400055c7  test    rax, rax
0x1400055ca  jnz     short loc_1400055E0
0x1400055cc  lea     rcx, ModuleName; "ntdll.dll"
0x1400055d3  call    cs:__imp_GetModuleHandleW
0x1400055d9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400055e0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1400055e7  mov     rcx, rax; hModule
0x1400055ea  call    cs:__imp_GetProcAddress
0x1400055f0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1400055f7  test    rax, rax
0x1400055fa  jz      short loc_140005602
0x1400055fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005601  nop
0x140005602  add     rsp, 28h
0x140005606  retn
```

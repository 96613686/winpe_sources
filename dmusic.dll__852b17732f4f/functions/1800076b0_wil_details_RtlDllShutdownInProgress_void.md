# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1800076b0`
- end: `0x180007707`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800076b0`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800076d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800076d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800076ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800076ea`

## string_xrefs

- `0x1800076cc`: `ntdll.dll`
- `0x1800076e0`: `RtlDllShutdownInProgress`

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
0x1800076b0  sub     rsp, 28h
0x1800076b4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1800076bb  test    rax, rax
0x1800076be  jnz     short loc_1800076FC
0x1800076c0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800076c7  test    rax, rax
0x1800076ca  jnz     short loc_1800076E0
0x1800076cc  lea     rcx, ModuleName; "ntdll.dll"
0x1800076d3  call    cs:__imp_GetModuleHandleW
0x1800076d9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800076e0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1800076e7  mov     rcx, rax; hModule
0x1800076ea  call    cs:__imp_GetProcAddress
0x1800076f0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1800076f7  test    rax, rax
0x1800076fa  jz      short loc_180007702
0x1800076fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007701  nop
0x180007702  add     rsp, 28h
0x180007706  retn
```

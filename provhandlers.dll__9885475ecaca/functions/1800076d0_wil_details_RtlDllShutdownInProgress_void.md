# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1800076d0`
- end: `0x180007727`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800076d0`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800076f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800076f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000770a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000770a`

## string_xrefs

- `0x1800076ec`: `ntdll.dll`
- `0x180007700`: `RtlDllShutdownInProgress`

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
0x1800076d0  sub     rsp, 28h
0x1800076d4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1800076db  test    rax, rax
0x1800076de  jnz     short loc_18000771C
0x1800076e0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800076e7  test    rax, rax
0x1800076ea  jnz     short loc_180007700
0x1800076ec  lea     rcx, ModuleName; "ntdll.dll"
0x1800076f3  call    cs:__imp_GetModuleHandleW
0x1800076f9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007700  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180007707  mov     rcx, rax; hModule
0x18000770a  call    cs:__imp_GetProcAddress
0x180007710  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180007717  test    rax, rax
0x18000771a  jz      short loc_180007722
0x18000771c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007721  nop
0x180007722  add     rsp, 28h
0x180007726  retn
```

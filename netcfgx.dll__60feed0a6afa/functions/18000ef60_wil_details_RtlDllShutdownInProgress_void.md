# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000ef60`
- end: `0x18000efb7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000ef60`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ef83`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ef83`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ef9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ef9a`

## string_xrefs

- `0x18000ef7c`: `ntdll.dll`
- `0x18000ef90`: `RtlDllShutdownInProgress`

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
0x18000ef60  sub     rsp, 28h
0x18000ef64  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000ef6b  test    rax, rax
0x18000ef6e  jnz     short loc_18000EFAC
0x18000ef70  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ef77  test    rax, rax
0x18000ef7a  jnz     short loc_18000EF90
0x18000ef7c  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000ef83  call    cs:__imp_GetModuleHandleW
0x18000ef89  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ef90  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000ef97  mov     rcx, rax; hModule
0x18000ef9a  call    cs:__imp_GetProcAddress
0x18000efa0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000efa7  test    rax, rax
0x18000efaa  jz      short loc_18000EFB2
0x18000efac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efb1  nop
0x18000efb2  add     rsp, 28h
0x18000efb6  retn
```

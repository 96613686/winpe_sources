# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180004f10`
- end: `0x180004f74`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `100`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180004f10`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004f33`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004f33`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004f50`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004f50`

## string_xrefs

- `0x180004f2c`: `ntdll.dll`
- `0x180004f46`: `RtlDllShutdownInProgress`

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
0x180004f10  sub     rsp, 28h
0x180004f14  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180004f1b  test    rax, rax
0x180004f1e  jnz     short loc_180004F68
0x180004f20  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004f27  test    rax, rax
0x180004f2a  jnz     short loc_180004F46
0x180004f2c  lea     rcx, ModuleName; "ntdll.dll"
0x180004f33  call    cs:__imp_GetModuleHandleW
0x180004f3a  nop     dword ptr [rax+rax+00h]
0x180004f3f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004f46  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180004f4d  mov     rcx, rax; hModule
0x180004f50  call    cs:__imp_GetProcAddress
0x180004f57  nop     dword ptr [rax+rax+00h]
0x180004f5c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180004f63  test    rax, rax
0x180004f66  jz      short loc_180004F6E
0x180004f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f6d  nop
0x180004f6e  add     rsp, 28h
0x180004f72  retn
```

# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1800074c0`
- end: `0x18000751a`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `90`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800074c0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800074fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800074fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800074e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800074e3`

## string_xrefs

- `0x1800074dc`: `ntdll.dll`
- `0x1800074f0`: `RtlDllShutdownInProgress`

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
0x1800074c0  sub     rsp, 28h
0x1800074c4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1800074cb  test    rax, rax
0x1800074ce  jnz     short loc_180007511
0x1800074d0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800074d7  test    rax, rax
0x1800074da  jnz     short loc_1800074F0
0x1800074dc  lea     rcx, ModuleName; "ntdll.dll"
0x1800074e3  call    cs:__imp_GetModuleHandleW
0x1800074e9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800074f0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1800074f7  mov     rcx, rax; hModule
0x1800074fa  call    cs:__imp_GetProcAddress
0x180007500  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180007507  test    rax, rax
0x18000750a  jnz     short loc_180007511
0x18000750c  add     rsp, 28h
0x180007510  retn
0x180007511  add     rsp, 28h
0x180007515  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

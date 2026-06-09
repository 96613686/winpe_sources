# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180027a80`
- end: `0x180027adc`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `92`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180027a80`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027aba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027aba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180027aa3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180027aa3`

## string_xrefs

- `0x180027a9c`: `ntdll.dll`
- `0x180027ab0`: `RtlDllShutdownInProgress`

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
0x180027a80  sub     rsp, 28h
0x180027a84  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180027a8b  test    rax, rax
0x180027a8e  jnz     short loc_180027AD1
0x180027a90  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180027a97  test    rax, rax
0x180027a9a  jnz     short loc_180027AB0
0x180027a9c  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180027aa3  call    cs:__imp_GetModuleHandleW
0x180027aa9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180027ab0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180027ab7  mov     rcx, rax; hModule
0x180027aba  call    cs:__imp_GetProcAddress
0x180027ac0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180027ac7  test    rax, rax
0x180027aca  jnz     short loc_180027AD1
0x180027acc  add     rsp, 28h
0x180027ad0  retn
0x180027ad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ad6  nop
0x180027ad7  add     rsp, 28h
0x180027adb  retn
```

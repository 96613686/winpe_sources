# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x140016750`
- end: `0x1400167aa`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `90`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140016750`
- `0x140019010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14001678a`
- `KERNEL32!GetProcAddress` at `0x14001678a`
- `KERNEL32!GetModuleHandleW` at `0x140016773`
- `KERNEL32!GetModuleHandleW` at `0x140016773`

## string_xrefs

- `0x14001676c`: `ntdll.dll`
- `0x140016780`: `RtlDllShutdownInProgress`

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
0x140016750  sub     rsp, 28h
0x140016754  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14001675b  test    rax, rax
0x14001675e  jnz     short loc_1400167A1
0x140016760  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140016767  test    rax, rax
0x14001676a  jnz     short loc_140016780
0x14001676c  lea     rcx, ModuleName; "ntdll.dll"
0x140016773  call    cs:__imp_GetModuleHandleW
0x140016779  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140016780  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x140016787  mov     rcx, rax; hModule
0x14001678a  call    cs:__imp_GetProcAddress
0x140016790  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x140016797  test    rax, rax
0x14001679a  jnz     short loc_1400167A1
0x14001679c  add     rsp, 28h
0x1400167a0  retn
0x1400167a1  add     rsp, 28h
0x1400167a5  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

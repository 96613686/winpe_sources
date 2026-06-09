# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180009a20`
- end: `0x180009a7a`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `90`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180009a20`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180009a5a`
- `KERNEL32!GetProcAddress` at `0x180009a5a`
- `KERNEL32!GetModuleHandleW` at `0x180009a43`
- `KERNEL32!GetModuleHandleW` at `0x180009a43`

## string_xrefs

- `0x180009a3c`: `ntdll.dll`
- `0x180009a50`: `RtlDllShutdownInProgress`

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
0x180009a20  sub     rsp, 28h
0x180009a24  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180009a2b  test    rax, rax
0x180009a2e  jnz     short loc_180009A71
0x180009a30  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009a37  test    rax, rax
0x180009a3a  jnz     short loc_180009A50
0x180009a3c  lea     rcx, ModuleName; "ntdll.dll"
0x180009a43  call    cs:__imp_GetModuleHandleW
0x180009a49  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009a50  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180009a57  mov     rcx, rax; hModule
0x180009a5a  call    cs:__imp_GetProcAddress
0x180009a60  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180009a67  test    rax, rax
0x180009a6a  jnz     short loc_180009A71
0x180009a6c  add     rsp, 28h
0x180009a70  retn
0x180009a71  add     rsp, 28h
0x180009a75  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

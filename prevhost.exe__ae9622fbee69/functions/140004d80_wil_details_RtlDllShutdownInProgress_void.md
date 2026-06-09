# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x140004d80`
- end: `0x140004dda`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `90`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140004d80`
- `0x140006010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140004dba`
- `KERNEL32!GetProcAddress` at `0x140004dba`
- `KERNEL32!GetModuleHandleW` at `0x140004da3`
- `KERNEL32!GetModuleHandleW` at `0x140004da3`

## string_xrefs

- `0x140004d9c`: `ntdll.dll`
- `0x140004db0`: `RtlDllShutdownInProgress`

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
0x140004d80  sub     rsp, 28h
0x140004d84  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x140004d8b  test    rax, rax
0x140004d8e  jnz     short loc_140004DD1
0x140004d90  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004d97  test    rax, rax
0x140004d9a  jnz     short loc_140004DB0
0x140004d9c  lea     rcx, ModuleName; "ntdll.dll"
0x140004da3  call    cs:__imp_GetModuleHandleW
0x140004da9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004db0  lea     rdx, ProcName; "RtlDllShutdownInProgress"
0x140004db7  mov     rcx, rax; hModule
0x140004dba  call    cs:__imp_GetProcAddress
0x140004dc0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x140004dc7  test    rax, rax
0x140004dca  jnz     short loc_140004DD1
0x140004dcc  add     rsp, 28h
0x140004dd0  retn
0x140004dd1  add     rsp, 28h
0x140004dd5  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

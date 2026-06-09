# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000cfb0`
- end: `0x18000d00a`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `90`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000cfb0`
- `0x18000e010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000cfea`
- `KERNEL32!GetProcAddress` at `0x18000cfea`
- `KERNEL32!GetModuleHandleW` at `0x18000cfd3`
- `KERNEL32!GetModuleHandleW` at `0x18000cfd3`

## string_xrefs

- `0x18000cfcc`: `ntdll.dll`
- `0x18000cfe0`: `RtlDllShutdownInProgress`

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
0x18000cfb0  sub     rsp, 28h
0x18000cfb4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000cfbb  test    rax, rax
0x18000cfbe  jnz     short loc_18000D001
0x18000cfc0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cfc7  test    rax, rax
0x18000cfca  jnz     short loc_18000CFE0
0x18000cfcc  lea     rcx, ModuleName; "ntdll.dll"
0x18000cfd3  call    cs:__imp_GetModuleHandleW
0x18000cfd9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cfe0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000cfe7  mov     rcx, rax; hModule
0x18000cfea  call    cs:__imp_GetProcAddress
0x18000cff0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000cff7  test    rax, rax
0x18000cffa  jnz     short loc_18000D001
0x18000cffc  add     rsp, 28h
0x18000d000  retn
0x18000d001  add     rsp, 28h
0x18000d005  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

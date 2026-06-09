# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1400059f0`
- end: `0x140005a47`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1400059f0`
- `0x140008010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005a13`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005a13`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005a2a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005a2a`

## string_xrefs

- `0x140005a0c`: `ntdll.dll`
- `0x140005a20`: `RtlDllShutdownInProgress`

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
0x1400059f0  sub     rsp, 28h
0x1400059f4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1400059fb  test    rax, rax
0x1400059fe  jnz     short loc_140005A3C
0x140005a00  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140005a07  test    rax, rax
0x140005a0a  jnz     short loc_140005A20
0x140005a0c  lea     rcx, ModuleName; "ntdll.dll"
0x140005a13  call    cs:__imp_GetModuleHandleW
0x140005a19  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140005a20  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x140005a27  mov     rcx, rax; hModule
0x140005a2a  call    cs:__imp_GetProcAddress
0x140005a30  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x140005a37  test    rax, rax
0x140005a3a  jz      short loc_140005A42
0x140005a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005a41  nop
0x140005a42  add     rsp, 28h
0x140005a46  retn
```

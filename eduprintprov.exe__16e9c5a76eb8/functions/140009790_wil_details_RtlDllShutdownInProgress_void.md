# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x140009790`
- end: `0x1400097e7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140009790`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400097b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400097b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400097ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400097ca`

## string_xrefs

- `0x1400097ac`: `ntdll.dll`
- `0x1400097c0`: `RtlDllShutdownInProgress`

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
0x140009790  sub     rsp, 28h
0x140009794  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14000979b  test    rax, rax
0x14000979e  jnz     short loc_1400097DC
0x1400097a0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400097a7  test    rax, rax
0x1400097aa  jnz     short loc_1400097C0
0x1400097ac  lea     rcx, ModuleName; "ntdll.dll"
0x1400097b3  call    cs:__imp_GetModuleHandleW
0x1400097b9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400097c0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1400097c7  mov     rcx, rax; hModule
0x1400097ca  call    cs:__imp_GetProcAddress
0x1400097d0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1400097d7  test    rax, rax
0x1400097da  jz      short loc_1400097E2
0x1400097dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400097e1  nop
0x1400097e2  add     rsp, 28h
0x1400097e6  retn
```

# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180005570`
- end: `0x1800055d0`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `96`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180005570`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800055b3`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800055b3`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000559c`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000559c`

## string_xrefs

- `0x180005595`: `ntdll.dll`
- `0x1800055a9`: `RtlDllShutdownInProgress`

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
0x180005570  sub     rsp, 38h
0x180005574  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000557d  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180005584  test    rax, rax
0x180005587  jnz     short loc_1800055C5
0x180005589  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005590  test    rax, rax
0x180005593  jnz     short loc_1800055A9
0x180005595  lea     rcx, LibFileName; "ntdll.dll"
0x18000559c  call    cs:__imp_GetModuleHandleW
0x1800055a2  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800055a9  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1800055b0  mov     rcx, rax; hModule
0x1800055b3  call    cs:__imp_GetProcAddress
0x1800055b9  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1800055c0  test    rax, rax
0x1800055c3  jz      short loc_1800055CB
0x1800055c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055ca  nop
0x1800055cb  add     rsp, 38h
0x1800055cf  retn
```

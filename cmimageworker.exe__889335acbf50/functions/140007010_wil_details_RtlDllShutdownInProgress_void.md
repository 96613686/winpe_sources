# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x140007010`
- end: `0x140007074`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `100`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140007010`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007050`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007050`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007033`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007033`

## string_xrefs

- `0x14000702c`: `ntdll.dll`
- `0x140007046`: `RtlDllShutdownInProgress`

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
0x140007010  sub     rsp, 28h
0x140007014  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14000701b  test    rax, rax
0x14000701e  jnz     short loc_140007068
0x140007020  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140007027  test    rax, rax
0x14000702a  jnz     short loc_140007046
0x14000702c  lea     rcx, ModuleName; "ntdll.dll"
0x140007033  call    cs:__imp_GetModuleHandleW
0x14000703a  nop     dword ptr [rax+rax+00h]
0x14000703f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140007046  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x14000704d  mov     rcx, rax; hModule
0x140007050  call    cs:__imp_GetProcAddress
0x140007057  nop     dword ptr [rax+rax+00h]
0x14000705c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x140007063  test    rax, rax
0x140007066  jz      short loc_14000706E
0x140007068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000706d  nop
0x14000706e  add     rsp, 28h
0x140007072  retn
```

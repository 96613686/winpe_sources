# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000bac0`
- end: `0x18000bb1a`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `90`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000bac0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bae3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bae3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bafa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bafa`

## string_xrefs

- `0x18000badc`: `ntdll.dll`
- `0x18000baf0`: `RtlDllShutdownInProgress`

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
0x18000bac0  sub     rsp, 28h
0x18000bac4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000bacb  test    rax, rax
0x18000bace  jnz     short loc_18000BB11
0x18000bad0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bad7  test    rax, rax
0x18000bada  jnz     short loc_18000BAF0
0x18000badc  lea     rcx, ModuleName; "ntdll.dll"
0x18000bae3  call    cs:__imp_GetModuleHandleW
0x18000bae9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000baf0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000baf7  mov     rcx, rax; hModule
0x18000bafa  call    cs:__imp_GetProcAddress
0x18000bb00  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000bb07  test    rax, rax
0x18000bb0a  jnz     short loc_18000BB11
0x18000bb0c  add     rsp, 28h
0x18000bb10  retn
0x18000bb11  add     rsp, 28h
0x18000bb15  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180004940`
- end: `0x1800049a4`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `100`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180004940`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004980`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004980`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004963`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004963`

## string_xrefs

- `0x18000495c`: `ntdll.dll`
- `0x180004976`: `RtlDllShutdownInProgress`

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
0x180004940  sub     rsp, 28h
0x180004944  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000494b  test    rax, rax
0x18000494e  jnz     short loc_180004998
0x180004950  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004957  test    rax, rax
0x18000495a  jnz     short loc_180004976
0x18000495c  lea     rcx, ModuleName; "ntdll.dll"
0x180004963  call    cs:__imp_GetModuleHandleW
0x18000496a  nop     dword ptr [rax+rax+00h]
0x18000496f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004976  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000497d  mov     rcx, rax; hModule
0x180004980  call    cs:__imp_GetProcAddress
0x180004987  nop     dword ptr [rax+rax+00h]
0x18000498c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180004993  test    rax, rax
0x180004996  jz      short loc_18000499E
0x180004998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000499d  nop
0x18000499e  add     rsp, 28h
0x1800049a2  retn
```

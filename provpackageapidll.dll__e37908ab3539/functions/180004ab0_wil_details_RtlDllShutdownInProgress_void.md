# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180004ab0`
- end: `0x180004b07`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180004ab0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004ad3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004ad3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004aea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004aea`

## string_xrefs

- `0x180004acc`: `ntdll.dll`
- `0x180004ae0`: `RtlDllShutdownInProgress`

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
0x180004ab0  sub     rsp, 28h
0x180004ab4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180004abb  test    rax, rax
0x180004abe  jnz     short loc_180004AFC
0x180004ac0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004ac7  test    rax, rax
0x180004aca  jnz     short loc_180004AE0
0x180004acc  lea     rcx, ModuleName; "ntdll.dll"
0x180004ad3  call    cs:__imp_GetModuleHandleW
0x180004ad9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004ae0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180004ae7  mov     rcx, rax; hModule
0x180004aea  call    cs:__imp_GetProcAddress
0x180004af0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180004af7  test    rax, rax
0x180004afa  jz      short loc_180004B02
0x180004afc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b01  nop
0x180004b02  add     rsp, 28h
0x180004b06  retn
```

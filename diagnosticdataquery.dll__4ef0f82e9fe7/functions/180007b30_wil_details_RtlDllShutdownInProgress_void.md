# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180007b30`
- end: `0x180007b87`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180007b30`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007b6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007b6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007b53`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007b53`

## string_xrefs

- `0x180007b4c`: `ntdll.dll`
- `0x180007b60`: `RtlDllShutdownInProgress`

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
0x180007b30  sub     rsp, 28h
0x180007b34  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180007b3b  test    rax, rax
0x180007b3e  jnz     short loc_180007B7C
0x180007b40  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007b47  test    rax, rax
0x180007b4a  jnz     short loc_180007B60
0x180007b4c  lea     rcx, ModuleName; "ntdll.dll"
0x180007b53  call    cs:__imp_GetModuleHandleW
0x180007b59  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007b60  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180007b67  mov     rcx, rax; hModule
0x180007b6a  call    cs:__imp_GetProcAddress
0x180007b70  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180007b77  test    rax, rax
0x180007b7a  jz      short loc_180007B82
0x180007b7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b81  nop
0x180007b82  add     rsp, 28h
0x180007b86  retn
```

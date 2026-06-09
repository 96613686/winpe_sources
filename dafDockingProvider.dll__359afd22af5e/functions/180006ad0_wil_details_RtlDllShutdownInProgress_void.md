# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180006ad0`
- end: `0x180006b27`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180006ad0`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006b0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006b0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006af3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006af3`

## string_xrefs

- `0x180006aec`: `ntdll.dll`
- `0x180006b00`: `RtlDllShutdownInProgress`

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
0x180006ad0  sub     rsp, 28h
0x180006ad4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180006adb  test    rax, rax
0x180006ade  jnz     short loc_180006B1C
0x180006ae0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006ae7  test    rax, rax
0x180006aea  jnz     short loc_180006B00
0x180006aec  lea     rcx, ModuleName; "ntdll.dll"
0x180006af3  call    cs:__imp_GetModuleHandleW
0x180006af9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006b00  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180006b07  mov     rcx, rax; hModule
0x180006b0a  call    cs:__imp_GetProcAddress
0x180006b10  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180006b17  test    rax, rax
0x180006b1a  jz      short loc_180006B22
0x180006b1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b21  nop
0x180006b22  add     rsp, 28h
0x180006b26  retn
```

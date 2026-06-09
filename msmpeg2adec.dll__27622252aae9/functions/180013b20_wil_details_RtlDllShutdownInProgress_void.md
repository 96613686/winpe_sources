# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180013b20`
- end: `0x180013b8b`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `107`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180013b20`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013b43`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013b43`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013b60`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013b60`

## string_xrefs

- `0x180013b3c`: `ntdll.dll`
- `0x180013b56`: `RtlDllShutdownInProgress`

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
0x180013b20  sub     rsp, 28h
0x180013b24  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180013b2b  test    rax, rax
0x180013b2e  jnz     short loc_180013B7E
0x180013b30  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180013b37  test    rax, rax
0x180013b3a  jnz     short loc_180013B56
0x180013b3c  lea     rcx, ModuleName; "ntdll.dll"
0x180013b43  call    cs:__imp_GetModuleHandleW
0x180013b4a  nop     dword ptr [rax+rax+00h]
0x180013b4f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180013b56  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180013b5d  mov     rcx, rax; hModule
0x180013b60  call    cs:__imp_GetProcAddress
0x180013b67  nop     dword ptr [rax+rax+00h]
0x180013b6c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180013b73  test    rax, rax
0x180013b76  jnz     short loc_180013B7E
0x180013b78  add     rsp, 28h
0x180013b7c  retn
0x180013b7e  call    cs:__guard_dispatch_icall_fptr
0x180013b84  nop
0x180013b85  add     rsp, 28h
0x180013b89  retn
```

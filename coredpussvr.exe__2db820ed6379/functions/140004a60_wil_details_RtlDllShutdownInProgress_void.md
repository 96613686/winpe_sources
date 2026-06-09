# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x140004a60`
- end: `0x140004ac4`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `100`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140004a60`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004a83`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004a83`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004aa0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004aa0`

## string_xrefs

- `0x140004a7c`: `ntdll.dll`
- `0x140004a96`: `RtlDllShutdownInProgress`

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
0x140004a60  sub     rsp, 28h
0x140004a64  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x140004a6b  test    rax, rax
0x140004a6e  jnz     short loc_140004AB8
0x140004a70  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004a77  test    rax, rax
0x140004a7a  jnz     short loc_140004A96
0x140004a7c  lea     rcx, ModuleName; "ntdll.dll"
0x140004a83  call    cs:__imp_GetModuleHandleW
0x140004a8a  nop     dword ptr [rax+rax+00h]
0x140004a8f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004a96  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x140004a9d  mov     rcx, rax; hModule
0x140004aa0  call    cs:__imp_GetProcAddress
0x140004aa7  nop     dword ptr [rax+rax+00h]
0x140004aac  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x140004ab3  test    rax, rax
0x140004ab6  jz      short loc_140004ABE
0x140004ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004abd  nop
0x140004abe  add     rsp, 28h
0x140004ac2  retn
```

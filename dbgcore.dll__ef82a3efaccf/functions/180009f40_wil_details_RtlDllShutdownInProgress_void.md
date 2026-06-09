# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180009f40`
- end: `0x180009fa0`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `96`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180009f40`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180009f83`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180009f83`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180009f6c`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180009f6c`

## string_xrefs

- `0x180009f65`: `ntdll.dll`
- `0x180009f79`: `RtlDllShutdownInProgress`

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
0x180009f40  sub     rsp, 38h
0x180009f44  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180009f4d  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180009f54  test    rax, rax
0x180009f57  jnz     short loc_180009F95
0x180009f59  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009f60  test    rax, rax
0x180009f63  jnz     short loc_180009F79
0x180009f65  lea     rcx, ModuleName; "ntdll.dll"
0x180009f6c  call    cs:__imp_GetModuleHandleW
0x180009f72  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009f79  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180009f80  mov     rcx, rax; hModule
0x180009f83  call    cs:__imp_GetProcAddress
0x180009f89  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180009f90  test    rax, rax
0x180009f93  jz      short loc_180009F9B
0x180009f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f9a  nop
0x180009f9b  add     rsp, 38h
0x180009f9f  retn
```

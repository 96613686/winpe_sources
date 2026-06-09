# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180006a80`
- end: `0x180006ad7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180006a80`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006aa3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006aa3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006aba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006aba`

## string_xrefs

- `0x180006a9c`: `ntdll.dll`
- `0x180006ab0`: `RtlDllShutdownInProgress`

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
0x180006a80  sub     rsp, 28h
0x180006a84  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180006a8b  test    rax, rax
0x180006a8e  jnz     short loc_180006ACC
0x180006a90  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006a97  test    rax, rax
0x180006a9a  jnz     short loc_180006AB0
0x180006a9c  lea     rcx, ModuleName; "ntdll.dll"
0x180006aa3  call    cs:__imp_GetModuleHandleW
0x180006aa9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006ab0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180006ab7  mov     rcx, rax; hModule
0x180006aba  call    cs:__imp_GetProcAddress
0x180006ac0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180006ac7  test    rax, rax
0x180006aca  jz      short loc_180006AD2
0x180006acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ad1  nop
0x180006ad2  add     rsp, 28h
0x180006ad6  retn
```

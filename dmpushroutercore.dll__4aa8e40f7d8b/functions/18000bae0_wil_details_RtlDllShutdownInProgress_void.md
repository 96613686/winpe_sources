# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000bae0`
- end: `0x18000bb37`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000bae0`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bb03`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bb03`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bb1a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bb1a`

## string_xrefs

- `0x18000bafc`: `ntdll.dll`
- `0x18000bb10`: `RtlDllShutdownInProgress`

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
0x18000bae0  sub     rsp, 28h
0x18000bae4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000baeb  test    rax, rax
0x18000baee  jnz     short loc_18000BB2C
0x18000baf0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000baf7  test    rax, rax
0x18000bafa  jnz     short loc_18000BB10
0x18000bafc  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000bb03  call    cs:__imp_GetModuleHandleW
0x18000bb09  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bb10  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000bb17  mov     rcx, rax; hModule
0x18000bb1a  call    cs:__imp_GetProcAddress
0x18000bb20  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000bb27  test    rax, rax
0x18000bb2a  jz      short loc_18000BB32
0x18000bb2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb31  nop
0x18000bb32  add     rsp, 28h
0x18000bb36  retn
```

# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180024f90`
- end: `0x180024ffc`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `108`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180024f90`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024fd4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024fd4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180024fb7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180024fb7`

## string_xrefs

- `0x180024fb0`: `ntdll.dll`
- `0x180024fca`: `RtlDllShutdownInProgress`

## pseudocode

```c
char __fastcall wil::details::RtlDllShutdownInProgress(wil::details *this)
{
  FARPROC ProcAddress; // rax
  char v2; // bl
  HMODULE ModuleHandleW; // rax

  ProcAddress = (FARPROC)`wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress;
  v2 = 0;
  if ( `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress )
    return ((__int64 (__fastcall *)(wil::details *))ProcAddress)(this);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "RtlDllShutdownInProgress");
  `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress = (__int64)ProcAddress;
  if ( ProcAddress )
    return ((__int64 (__fastcall *)(wil::details *))ProcAddress)(this);
  return v2;
}

```

## disassembly

```asm
0x180024f90  push    rbx
0x180024f92  sub     rsp, 20h
0x180024f96  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180024f9d  xor     ebx, ebx
0x180024f9f  test    rax, rax
0x180024fa2  jnz     short loc_180024FEC
0x180024fa4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180024fab  test    rax, rax
0x180024fae  jnz     short loc_180024FCA
0x180024fb0  lea     rcx, ModuleName; "ntdll.dll"
0x180024fb7  call    cs:__imp_GetModuleHandleW
0x180024fbe  nop     dword ptr [rax+rax+00h]
0x180024fc3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180024fca  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180024fd1  mov     rcx, rax; hModule
0x180024fd4  call    cs:__imp_GetProcAddress
0x180024fdb  nop     dword ptr [rax+rax+00h]
0x180024fe0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180024fe7  test    rax, rax
0x180024fea  jz      short loc_180024FF3
0x180024fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ff1  mov     bl, al
0x180024ff3  mov     al, bl
0x180024ff5  add     rsp, 20h
0x180024ff9  pop     rbx
0x180024ffa  retn
```

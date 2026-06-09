# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x14000b0e0`
- end: `0x14000b147`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `103`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x14000b0e0`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000b120`
- `KERNEL32!GetProcAddress` at `0x14000b120`
- `KERNEL32!GetModuleHandleW` at `0x14000b103`
- `KERNEL32!GetModuleHandleW` at `0x14000b103`

## string_xrefs

- `0x14000b0fc`: `ntdll.dll`
- `0x14000b116`: `RtlDllShutdownInProgress`

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
0x14000b0e0  sub     rsp, 28h
0x14000b0e4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14000b0eb  test    rax, rax
0x14000b0ee  jnz     short loc_14000B13E
0x14000b0f0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b0f7  test    rax, rax
0x14000b0fa  jnz     short loc_14000B116
0x14000b0fc  lea     rcx, ModuleName; "ntdll.dll"
0x14000b103  call    cs:__imp_GetModuleHandleW
0x14000b10a  nop     dword ptr [rax+rax+00h]
0x14000b10f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b116  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x14000b11d  mov     rcx, rax; hModule
0x14000b120  call    cs:__imp_GetProcAddress
0x14000b127  nop     dword ptr [rax+rax+00h]
0x14000b12c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x14000b133  test    rax, rax
0x14000b136  jnz     short loc_14000B13E
0x14000b138  add     rsp, 28h
0x14000b13c  retn
0x14000b13e  add     rsp, 28h
0x14000b142  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

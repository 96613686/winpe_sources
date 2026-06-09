# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x14000c940`
- end: `0x14000c997`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x14000c940`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000c97a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000c97a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000c963`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000c963`

## string_xrefs

- `0x14000c95c`: `ntdll.dll`
- `0x14000c970`: `RtlDllShutdownInProgress`

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
0x14000c940  sub     rsp, 28h
0x14000c944  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14000c94b  test    rax, rax
0x14000c94e  jnz     short loc_14000C98C
0x14000c950  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c957  test    rax, rax
0x14000c95a  jnz     short loc_14000C970
0x14000c95c  lea     rcx, ModuleName; "ntdll.dll"
0x14000c963  call    cs:__imp_GetModuleHandleW
0x14000c969  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c970  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x14000c977  mov     rcx, rax; hModule
0x14000c97a  call    cs:__imp_GetProcAddress
0x14000c980  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x14000c987  test    rax, rax
0x14000c98a  jz      short loc_14000C992
0x14000c98c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c991  nop
0x14000c992  add     rsp, 28h
0x14000c996  retn
```

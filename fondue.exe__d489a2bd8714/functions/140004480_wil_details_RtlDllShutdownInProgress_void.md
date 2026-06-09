# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x140004480`
- end: `0x1400044da`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `90`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140004480`
- `0x140005010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1400044ba`
- `KERNEL32!GetProcAddress` at `0x1400044ba`
- `KERNEL32!GetModuleHandleW` at `0x1400044a3`
- `KERNEL32!GetModuleHandleW` at `0x1400044a3`

## string_xrefs

- `0x14000449c`: `ntdll.dll`
- `0x1400044b0`: `RtlDllShutdownInProgress`

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
0x140004480  sub     rsp, 28h
0x140004484  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14000448b  test    rax, rax
0x14000448e  jnz     short loc_1400044D1
0x140004490  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004497  test    rax, rax
0x14000449a  jnz     short loc_1400044B0
0x14000449c  lea     rcx, ModuleName; "ntdll.dll"
0x1400044a3  call    cs:__imp_GetModuleHandleW
0x1400044a9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400044b0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1400044b7  mov     rcx, rax; hModule
0x1400044ba  call    cs:__imp_GetProcAddress
0x1400044c0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1400044c7  test    rax, rax
0x1400044ca  jnz     short loc_1400044D1
0x1400044cc  add     rsp, 28h
0x1400044d0  retn
0x1400044d1  add     rsp, 28h
0x1400044d5  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

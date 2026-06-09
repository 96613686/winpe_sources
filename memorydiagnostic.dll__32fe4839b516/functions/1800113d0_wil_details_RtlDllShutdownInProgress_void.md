# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1800113d0`
- end: `0x18001143c`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `108`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800113d0`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800113f7`
- `KERNEL32!GetModuleHandleW` at `0x1800113f7`
- `KERNEL32!GetProcAddress` at `0x180011414`
- `KERNEL32!GetProcAddress` at `0x180011414`

## string_xrefs

- `0x1800113f0`: `ntdll.dll`
- `0x18001140a`: `RtlDllShutdownInProgress`

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
0x1800113d0  push    rbx
0x1800113d2  sub     rsp, 20h
0x1800113d6  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1800113dd  xor     ebx, ebx
0x1800113df  test    rax, rax
0x1800113e2  jnz     short loc_18001142C
0x1800113e4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800113eb  test    rax, rax
0x1800113ee  jnz     short loc_18001140A
0x1800113f0  lea     rcx, ModuleName; "ntdll.dll"
0x1800113f7  call    cs:__imp_GetModuleHandleW
0x1800113fe  nop     dword ptr [rax+rax+00h]
0x180011403  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001140a  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180011411  mov     rcx, rax; hModule
0x180011414  call    cs:__imp_GetProcAddress
0x18001141b  nop     dword ptr [rax+rax+00h]
0x180011420  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180011427  test    rax, rax
0x18001142a  jz      short loc_180011433
0x18001142c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011431  mov     bl, al
0x180011433  mov     al, bl
0x180011435  add     rsp, 20h
0x180011439  pop     rbx
0x18001143a  retn
```

# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x14000a9a0`
- end: `0x14000a9fe`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x14000a9a0`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000a9c7`
- `KERNEL32!GetModuleHandleW` at `0x14000a9c7`
- `KERNEL32!GetProcAddress` at `0x14000a9de`
- `KERNEL32!GetProcAddress` at `0x14000a9de`

## string_xrefs

- `0x14000a9c0`: `ntdll.dll`

## pseudocode

```c
FARPROC __fastcall wil::details::RtlNtStatusToDosErrorNoTeb(wil::details *this)
{
  unsigned int v1; // ebx
  FARPROC result; // rax
  HMODULE ModuleHandleW; // rax

  v1 = (unsigned int)this;
  result = (FARPROC)`wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb;
  if ( `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb )
    return (FARPROC)((__int64 (__fastcall *)(_QWORD))result)(v1);
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  result = GetProcAddress(ModuleHandleW, "RtlNtStatusToDosErrorNoTeb");
  `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(_QWORD))result)(v1);
  return result;
}

```

## disassembly

```asm
0x14000a9a0  push    rbx
0x14000a9a2  sub     rsp, 20h
0x14000a9a6  mov     ebx, ecx
0x14000a9a8  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x14000a9af  test    rax, rax
0x14000a9b2  jnz     short loc_14000A9F0
0x14000a9b4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000a9bb  test    rax, rax
0x14000a9be  jnz     short loc_14000A9D4
0x14000a9c0  lea     rcx, ModuleName; "ntdll.dll"
0x14000a9c7  call    cs:__imp_GetModuleHandleW
0x14000a9cd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000a9d4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x14000a9db  mov     rcx, rax; hModule
0x14000a9de  call    cs:__imp_GetProcAddress
0x14000a9e4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x14000a9eb  test    rax, rax
0x14000a9ee  jz      short loc_14000A9F8
0x14000a9f0  mov     ecx, ebx
0x14000a9f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a9f7  nop
0x14000a9f8  add     rsp, 20h
0x14000a9fc  pop     rbx
0x14000a9fd  retn
```

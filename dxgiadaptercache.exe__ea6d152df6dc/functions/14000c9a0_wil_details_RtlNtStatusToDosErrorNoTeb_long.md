# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x14000c9a0`
- end: `0x14000c9fe`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x14000c9a0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000c9de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000c9de`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000c9c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000c9c7`

## string_xrefs

- `0x14000c9c0`: `ntdll.dll`

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
0x14000c9a0  push    rbx
0x14000c9a2  sub     rsp, 20h
0x14000c9a6  mov     ebx, ecx
0x14000c9a8  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x14000c9af  test    rax, rax
0x14000c9b2  jnz     short loc_14000C9F0
0x14000c9b4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c9bb  test    rax, rax
0x14000c9be  jnz     short loc_14000C9D4
0x14000c9c0  lea     rcx, ModuleName; "ntdll.dll"
0x14000c9c7  call    cs:__imp_GetModuleHandleW
0x14000c9cd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c9d4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x14000c9db  mov     rcx, rax; hModule
0x14000c9de  call    cs:__imp_GetProcAddress
0x14000c9e4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x14000c9eb  test    rax, rax
0x14000c9ee  jz      short loc_14000C9F8
0x14000c9f0  mov     ecx, ebx
0x14000c9f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c9f7  nop
0x14000c9f8  add     rsp, 20h
0x14000c9fc  pop     rbx
0x14000c9fd  retn
```

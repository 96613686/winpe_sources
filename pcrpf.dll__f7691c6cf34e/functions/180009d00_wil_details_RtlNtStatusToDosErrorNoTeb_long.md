# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180009d00`
- end: `0x180009d6b`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `107`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180009d00`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009d44`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009d44`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009d27`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009d27`

## string_xrefs

- `0x180009d20`: `ntdll.dll`

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
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x180009d00  push    rbx
0x180009d02  sub     rsp, 20h
0x180009d06  mov     ebx, ecx
0x180009d08  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180009d0f  test    rax, rax
0x180009d12  jnz     short loc_180009D5C
0x180009d14  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009d1b  test    rax, rax
0x180009d1e  jnz     short loc_180009D3A
0x180009d20  lea     rcx, ModuleName; "ntdll.dll"
0x180009d27  call    cs:__imp_GetModuleHandleW
0x180009d2e  nop     dword ptr [rax+rax+00h]
0x180009d33  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009d3a  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180009d41  mov     rcx, rax; hModule
0x180009d44  call    cs:__imp_GetProcAddress
0x180009d4b  nop     dword ptr [rax+rax+00h]
0x180009d50  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180009d57  test    rax, rax
0x180009d5a  jz      short loc_180009D64
0x180009d5c  mov     ecx, ebx
0x180009d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d63  nop
0x180009d64  add     rsp, 20h
0x180009d68  pop     rbx
0x180009d69  retn
```

# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x18000a3b0`
- end: `0x18000a41b`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `107`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000a3b0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a3d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a3d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a3f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a3f4`

## string_xrefs

- `0x18000a3d0`: `ntdll.dll`

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
0x18000a3b0  push    rbx
0x18000a3b2  sub     rsp, 20h
0x18000a3b6  mov     ebx, ecx
0x18000a3b8  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000a3bf  test    rax, rax
0x18000a3c2  jnz     short loc_18000A40C
0x18000a3c4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a3cb  test    rax, rax
0x18000a3ce  jnz     short loc_18000A3EA
0x18000a3d0  lea     rcx, ModuleName; "ntdll.dll"
0x18000a3d7  call    cs:__imp_GetModuleHandleW
0x18000a3de  nop     dword ptr [rax+rax+00h]
0x18000a3e3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a3ea  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000a3f1  mov     rcx, rax; hModule
0x18000a3f4  call    cs:__imp_GetProcAddress
0x18000a3fb  nop     dword ptr [rax+rax+00h]
0x18000a400  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000a407  test    rax, rax
0x18000a40a  jz      short loc_18000A414
0x18000a40c  mov     ecx, ebx
0x18000a40e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a413  nop
0x18000a414  add     rsp, 20h
0x18000a418  pop     rbx
0x18000a419  retn
```

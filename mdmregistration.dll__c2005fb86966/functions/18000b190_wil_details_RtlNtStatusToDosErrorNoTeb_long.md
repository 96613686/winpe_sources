# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x18000b190`
- end: `0x18000b1fb`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `107`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000b190`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b1b7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b1b7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b1d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b1d4`

## string_xrefs

- `0x18000b1b0`: `ntdll.dll`

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
0x18000b190  push    rbx
0x18000b192  sub     rsp, 20h
0x18000b196  mov     ebx, ecx
0x18000b198  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000b19f  test    rax, rax
0x18000b1a2  jnz     short loc_18000B1EC
0x18000b1a4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b1ab  test    rax, rax
0x18000b1ae  jnz     short loc_18000B1CA
0x18000b1b0  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18000b1b7  call    cs:__imp_GetModuleHandleW
0x18000b1be  nop     dword ptr [rax+rax+00h]
0x18000b1c3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b1ca  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000b1d1  mov     rcx, rax; hModule
0x18000b1d4  call    cs:__imp_GetProcAddress
0x18000b1db  nop     dword ptr [rax+rax+00h]
0x18000b1e0  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000b1e7  test    rax, rax
0x18000b1ea  jz      short loc_18000B1F4
0x18000b1ec  mov     ecx, ebx
0x18000b1ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1f3  nop
0x18000b1f4  add     rsp, 20h
0x18000b1f8  pop     rbx
0x18000b1f9  retn
```

# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180009a10`
- end: `0x180009a6e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180009a10`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009a37`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009a37`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009a4e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009a4e`

## string_xrefs

- `0x180009a30`: `ntdll.dll`

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
0x180009a10  push    rbx
0x180009a12  sub     rsp, 20h
0x180009a16  mov     ebx, ecx
0x180009a18  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180009a1f  test    rax, rax
0x180009a22  jnz     short loc_180009A60
0x180009a24  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009a2b  test    rax, rax
0x180009a2e  jnz     short loc_180009A44
0x180009a30  lea     rcx, ModuleName; "ntdll.dll"
0x180009a37  call    cs:__imp_GetModuleHandleW
0x180009a3d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009a44  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180009a4b  mov     rcx, rax; hModule
0x180009a4e  call    cs:__imp_GetProcAddress
0x180009a54  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180009a5b  test    rax, rax
0x180009a5e  jz      short loc_180009A68
0x180009a60  mov     ecx, ebx
0x180009a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a67  nop
0x180009a68  add     rsp, 20h
0x180009a6c  pop     rbx
0x180009a6d  retn
```

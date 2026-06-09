# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180006c30`
- end: `0x180006c8e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180006c30`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006c57`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006c57`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006c6e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006c6e`

## string_xrefs

- `0x180006c50`: `ntdll.dll`

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
0x180006c30  push    rbx
0x180006c32  sub     rsp, 20h
0x180006c36  mov     ebx, ecx
0x180006c38  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180006c3f  test    rax, rax
0x180006c42  jnz     short loc_180006C80
0x180006c44  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006c4b  test    rax, rax
0x180006c4e  jnz     short loc_180006C64
0x180006c50  lea     rcx, ModuleName; "ntdll.dll"
0x180006c57  call    cs:__imp_GetModuleHandleW
0x180006c5d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006c64  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180006c6b  mov     rcx, rax; hModule
0x180006c6e  call    cs:__imp_GetProcAddress
0x180006c74  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180006c7b  test    rax, rax
0x180006c7e  jz      short loc_180006C88
0x180006c80  mov     ecx, ebx
0x180006c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c87  nop
0x180006c88  add     rsp, 20h
0x180006c8c  pop     rbx
0x180006c8d  retn
```

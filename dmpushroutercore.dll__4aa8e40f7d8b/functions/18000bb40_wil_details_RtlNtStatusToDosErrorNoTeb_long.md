# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x18000bb40`
- end: `0x18000bb9e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000bb40`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bb67`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bb67`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bb7e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bb7e`

## string_xrefs

- `0x18000bb60`: `ntdll.dll`

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
0x18000bb40  push    rbx
0x18000bb42  sub     rsp, 20h
0x18000bb46  mov     ebx, ecx
0x18000bb48  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000bb4f  test    rax, rax
0x18000bb52  jnz     short loc_18000BB90
0x18000bb54  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bb5b  test    rax, rax
0x18000bb5e  jnz     short loc_18000BB74
0x18000bb60  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000bb67  call    cs:__imp_GetModuleHandleW
0x18000bb6d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bb74  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000bb7b  mov     rcx, rax; hModule
0x18000bb7e  call    cs:__imp_GetProcAddress
0x18000bb84  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000bb8b  test    rax, rax
0x18000bb8e  jz      short loc_18000BB98
0x18000bb90  mov     ecx, ebx
0x18000bb92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb97  nop
0x18000bb98  add     rsp, 20h
0x18000bb9c  pop     rbx
0x18000bb9d  retn
```

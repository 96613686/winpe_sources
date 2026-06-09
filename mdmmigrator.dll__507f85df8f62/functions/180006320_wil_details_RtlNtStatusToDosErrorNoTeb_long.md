# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180006320`
- end: `0x18000637e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180006320`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006347`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006347`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000635e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000635e`

## string_xrefs

- `0x180006340`: `ntdll.dll`

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
0x180006320  push    rbx
0x180006322  sub     rsp, 20h
0x180006326  mov     ebx, ecx
0x180006328  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000632f  test    rax, rax
0x180006332  jnz     short loc_180006370
0x180006334  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000633b  test    rax, rax
0x18000633e  jnz     short loc_180006354
0x180006340  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180006347  call    cs:__imp_GetModuleHandleW
0x18000634d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006354  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000635b  mov     rcx, rax; hModule
0x18000635e  call    cs:__imp_GetProcAddress
0x180006364  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000636b  test    rax, rax
0x18000636e  jz      short loc_180006378
0x180006370  mov     ecx, ebx
0x180006372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006377  nop
0x180006378  add     rsp, 20h
0x18000637c  pop     rbx
0x18000637d  retn
```

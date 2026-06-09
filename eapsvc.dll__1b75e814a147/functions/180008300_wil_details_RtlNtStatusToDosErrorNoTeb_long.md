# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180008300`
- end: `0x18000835e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180008300`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000833e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000833e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008327`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008327`

## string_xrefs

- `0x180008320`: `ntdll.dll`

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
0x180008300  push    rbx
0x180008302  sub     rsp, 20h
0x180008306  mov     ebx, ecx
0x180008308  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000830f  test    rax, rax
0x180008312  jnz     short loc_180008350
0x180008314  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000831b  test    rax, rax
0x18000831e  jnz     short loc_180008334
0x180008320  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180008327  call    cs:__imp_GetModuleHandleW
0x18000832d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008334  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000833b  mov     rcx, rax; hModule
0x18000833e  call    cs:__imp_GetProcAddress
0x180008344  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000834b  test    rax, rax
0x18000834e  jz      short loc_180008358
0x180008350  mov     ecx, ebx
0x180008352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008357  nop
0x180008358  add     rsp, 20h
0x18000835c  pop     rbx
0x18000835d  retn
```

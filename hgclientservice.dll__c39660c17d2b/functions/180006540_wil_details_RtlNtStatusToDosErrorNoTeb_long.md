# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180006540`
- end: `0x18000659e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180006540`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000657e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000657e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006567`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006567`

## string_xrefs

- `0x180006560`: `ntdll.dll`

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
0x180006540  push    rbx
0x180006542  sub     rsp, 20h
0x180006546  mov     ebx, ecx
0x180006548  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000654f  test    rax, rax
0x180006552  jnz     short loc_180006590
0x180006554  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000655b  test    rax, rax
0x18000655e  jnz     short loc_180006574
0x180006560  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180006567  call    cs:__imp_GetModuleHandleW
0x18000656d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006574  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000657b  mov     rcx, rax; hModule
0x18000657e  call    cs:__imp_GetProcAddress
0x180006584  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000658b  test    rax, rax
0x18000658e  jz      short loc_180006598
0x180006590  mov     ecx, ebx
0x180006592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006597  nop
0x180006598  add     rsp, 20h
0x18000659c  pop     rbx
0x18000659d  retn
```

# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180010a60`
- end: `0x180010abe`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180010a60`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180010a87`
- `KERNEL32!GetModuleHandleW` at `0x180010a87`
- `KERNEL32!GetProcAddress` at `0x180010a9e`
- `KERNEL32!GetProcAddress` at `0x180010a9e`

## string_xrefs

- `0x180010a80`: `ntdll.dll`

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
0x180010a60  push    rbx
0x180010a62  sub     rsp, 20h
0x180010a66  mov     ebx, ecx
0x180010a68  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180010a6f  test    rax, rax
0x180010a72  jnz     short loc_180010AB0
0x180010a74  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180010a7b  test    rax, rax
0x180010a7e  jnz     short loc_180010A94
0x180010a80  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180010a87  call    cs:__imp_GetModuleHandleW
0x180010a8d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180010a94  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180010a9b  mov     rcx, rax; hModule
0x180010a9e  call    cs:__imp_GetProcAddress
0x180010aa4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180010aab  test    rax, rax
0x180010aae  jz      short loc_180010AB8
0x180010ab0  mov     ecx, ebx
0x180010ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ab7  nop
0x180010ab8  add     rsp, 20h
0x180010abc  pop     rbx
0x180010abd  retn
```

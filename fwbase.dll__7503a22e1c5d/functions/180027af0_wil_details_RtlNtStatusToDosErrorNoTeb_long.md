# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180027af0`
- end: `0x180027b54`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `100`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180027af0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027b2e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027b2e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180027b17`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180027b17`

## string_xrefs

- `0x180027b10`: `ntdll.dll`

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
0x180027af0  push    rbx
0x180027af2  sub     rsp, 20h
0x180027af6  mov     ebx, ecx
0x180027af8  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180027aff  test    rax, rax
0x180027b02  jnz     short loc_180027B46
0x180027b04  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180027b0b  test    rax, rax
0x180027b0e  jnz     short loc_180027B24
0x180027b10  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180027b17  call    cs:__imp_GetModuleHandleW
0x180027b1d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180027b24  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180027b2b  mov     rcx, rax; hModule
0x180027b2e  call    cs:__imp_GetProcAddress
0x180027b34  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180027b3b  test    rax, rax
0x180027b3e  jnz     short loc_180027B46
0x180027b40  add     rsp, 20h
0x180027b44  pop     rbx
0x180027b45  retn
0x180027b46  mov     ecx, ebx
0x180027b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b4d  nop
0x180027b4e  add     rsp, 20h
0x180027b52  pop     rbx
0x180027b53  retn
```

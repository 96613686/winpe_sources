# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180008c20`
- end: `0x180008c7e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180008c20`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008c5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008c5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008c47`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008c47`

## string_xrefs

- `0x180008c40`: `ntdll.dll`

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
0x180008c20  push    rbx
0x180008c22  sub     rsp, 20h
0x180008c26  mov     ebx, ecx
0x180008c28  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180008c2f  test    rax, rax
0x180008c32  jnz     short loc_180008C70
0x180008c34  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008c3b  test    rax, rax
0x180008c3e  jnz     short loc_180008C54
0x180008c40  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180008c47  call    cs:__imp_GetModuleHandleW
0x180008c4d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008c54  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180008c5b  mov     rcx, rax; hModule
0x180008c5e  call    cs:__imp_GetProcAddress
0x180008c64  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180008c6b  test    rax, rax
0x180008c6e  jz      short loc_180008C78
0x180008c70  mov     ecx, ebx
0x180008c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c77  nop
0x180008c78  add     rsp, 20h
0x180008c7c  pop     rbx
0x180008c7d  retn
```

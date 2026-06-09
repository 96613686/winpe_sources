# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180005cc0`
- end: `0x180005d2b`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `107`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180005cc0`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005ce7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005ce7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005d04`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005d04`

## string_xrefs

- `0x180005ce0`: `ntdll.dll`

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
0x180005cc0  push    rbx
0x180005cc2  sub     rsp, 20h
0x180005cc6  mov     ebx, ecx
0x180005cc8  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180005ccf  test    rax, rax
0x180005cd2  jnz     short loc_180005D1C
0x180005cd4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005cdb  test    rax, rax
0x180005cde  jnz     short loc_180005CFA
0x180005ce0  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180005ce7  call    cs:__imp_GetModuleHandleW
0x180005cee  nop     dword ptr [rax+rax+00h]
0x180005cf3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005cfa  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180005d01  mov     rcx, rax; hModule
0x180005d04  call    cs:__imp_GetProcAddress
0x180005d0b  nop     dword ptr [rax+rax+00h]
0x180005d10  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180005d17  test    rax, rax
0x180005d1a  jz      short loc_180005D24
0x180005d1c  mov     ecx, ebx
0x180005d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d23  nop
0x180005d24  add     rsp, 20h
0x180005d28  pop     rbx
0x180005d29  retn
```

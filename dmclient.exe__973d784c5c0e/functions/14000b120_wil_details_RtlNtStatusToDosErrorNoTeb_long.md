# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x14000b120`
- end: `0x14000b18b`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `107`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x14000b120`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b164`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b164`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b147`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b147`

## string_xrefs

- `0x14000b140`: `ntdll.dll`

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
0x14000b120  push    rbx
0x14000b122  sub     rsp, 20h
0x14000b126  mov     ebx, ecx
0x14000b128  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x14000b12f  test    rax, rax
0x14000b132  jnz     short loc_14000B17C
0x14000b134  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b13b  test    rax, rax
0x14000b13e  jnz     short loc_14000B15A
0x14000b140  lea     rcx, ModuleName; "ntdll.dll"
0x14000b147  call    cs:__imp_GetModuleHandleW
0x14000b14e  nop     dword ptr [rax+rax+00h]
0x14000b153  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b15a  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x14000b161  mov     rcx, rax; hModule
0x14000b164  call    cs:__imp_GetProcAddress
0x14000b16b  nop     dword ptr [rax+rax+00h]
0x14000b170  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x14000b177  test    rax, rax
0x14000b17a  jz      short loc_14000B184
0x14000b17c  mov     ecx, ebx
0x14000b17e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b183  nop
0x14000b184  add     rsp, 20h
0x14000b188  pop     rbx
0x14000b189  retn
```

# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180006a10`
- end: `0x180006a7b`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `107`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180006a10`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006a54`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006a54`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006a37`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006a37`

## string_xrefs

- `0x180006a30`: `ntdll.dll`

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
0x180006a10  push    rbx
0x180006a12  sub     rsp, 20h
0x180006a16  mov     ebx, ecx
0x180006a18  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180006a1f  test    rax, rax
0x180006a22  jnz     short loc_180006A6C
0x180006a24  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006a2b  test    rax, rax
0x180006a2e  jnz     short loc_180006A4A
0x180006a30  lea     rcx, ModuleName; "ntdll.dll"
0x180006a37  call    cs:__imp_GetModuleHandleW
0x180006a3e  nop     dword ptr [rax+rax+00h]
0x180006a43  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006a4a  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180006a51  mov     rcx, rax; hModule
0x180006a54  call    cs:__imp_GetProcAddress
0x180006a5b  nop     dword ptr [rax+rax+00h]
0x180006a60  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180006a67  test    rax, rax
0x180006a6a  jz      short loc_180006A74
0x180006a6c  mov     ecx, ebx
0x180006a6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a73  nop
0x180006a74  add     rsp, 20h
0x180006a78  pop     rbx
0x180006a79  retn
```

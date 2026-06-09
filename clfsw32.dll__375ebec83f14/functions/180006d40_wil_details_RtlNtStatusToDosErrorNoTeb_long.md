# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180006d40`
- end: `0x180006daf`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `111`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180006d40`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006d84`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006d84`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006d67`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006d67`

## string_xrefs

- `0x180006d60`: `ntdll.dll`

## pseudocode

```c
FARPROC __fastcall wil::details::RtlNtStatusToDosErrorNoTeb(wil::details *this)
{
  FARPROC result; // rax
  unsigned int v2; // ebx
  HMODULE ModuleHandleW; // rax

  result = (FARPROC)`wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb;
  v2 = (unsigned int)this;
  if ( `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb )
    return (FARPROC)((__int64 (__fastcall *)(_QWORD))result)(v2);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  result = GetProcAddress(ModuleHandleW, "RtlNtStatusToDosErrorNoTeb");
  `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(_QWORD))result)(v2);
  return result;
}

```

## disassembly

```asm
0x180006d40  push    rbx
0x180006d42  sub     rsp, 20h
0x180006d46  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180006d4d  mov     ebx, ecx
0x180006d4f  test    rax, rax
0x180006d52  jnz     short loc_180006DA3
0x180006d54  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006d5b  test    rax, rax
0x180006d5e  jnz     short loc_180006D7A
0x180006d60  lea     rcx, ModuleName; "ntdll.dll"
0x180006d67  call    cs:__imp_GetModuleHandleW
0x180006d6e  nop     dword ptr [rax+rax+00h]
0x180006d73  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006d7a  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180006d81  mov     rcx, rax; hModule
0x180006d84  call    cs:__imp_GetProcAddress
0x180006d8b  nop     dword ptr [rax+rax+00h]
0x180006d90  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180006d97  test    rax, rax
0x180006d9a  jnz     short loc_180006DA3
0x180006d9c  add     rsp, 20h
0x180006da0  pop     rbx
0x180006da1  retn
0x180006da3  mov     ecx, ebx
0x180006da5  add     rsp, 20h
0x180006da9  pop     rbx
0x180006daa  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

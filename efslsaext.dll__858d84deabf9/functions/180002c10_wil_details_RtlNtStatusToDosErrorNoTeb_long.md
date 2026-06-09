# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180002c10`
- end: `0x180002c72`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180002c10`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002c4e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002c4e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002c37`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002c37`

## string_xrefs

- `0x180002c30`: `ntdll.dll`

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
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x180002c10  push    rbx
0x180002c12  sub     rsp, 20h
0x180002c16  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180002c1d  mov     ebx, ecx
0x180002c1f  test    rax, rax
0x180002c22  jnz     short loc_180002C66
0x180002c24  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180002c2b  test    rax, rax
0x180002c2e  jnz     short loc_180002C44
0x180002c30  lea     rcx, ModuleName; "ntdll.dll"
0x180002c37  call    cs:__imp_GetModuleHandleW
0x180002c3d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180002c44  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180002c4b  mov     rcx, rax; hModule
0x180002c4e  call    cs:__imp_GetProcAddress
0x180002c54  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180002c5b  test    rax, rax
0x180002c5e  jnz     short loc_180002C66
0x180002c60  add     rsp, 20h
0x180002c64  pop     rbx
0x180002c65  retn
0x180002c66  mov     ecx, ebx
0x180002c68  add     rsp, 20h
0x180002c6c  pop     rbx
0x180002c6d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

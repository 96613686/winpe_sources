# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180006b30`
- end: `0x180006b8e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180006b30`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006b6e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006b6e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006b57`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006b57`

## string_xrefs

- `0x180006b50`: `ntdll.dll`

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
0x180006b30  push    rbx
0x180006b32  sub     rsp, 20h
0x180006b36  mov     ebx, ecx
0x180006b38  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180006b3f  test    rax, rax
0x180006b42  jnz     short loc_180006B80
0x180006b44  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006b4b  test    rax, rax
0x180006b4e  jnz     short loc_180006B64
0x180006b50  lea     rcx, ModuleName; "ntdll.dll"
0x180006b57  call    cs:__imp_GetModuleHandleW
0x180006b5d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006b64  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180006b6b  mov     rcx, rax; hModule
0x180006b6e  call    cs:__imp_GetProcAddress
0x180006b74  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180006b7b  test    rax, rax
0x180006b7e  jz      short loc_180006B88
0x180006b80  mov     ecx, ebx
0x180006b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b87  nop
0x180006b88  add     rsp, 20h
0x180006b8c  pop     rbx
0x180006b8d  retn
```

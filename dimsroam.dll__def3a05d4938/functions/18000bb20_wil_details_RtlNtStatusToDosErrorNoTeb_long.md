# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x18000bb20`
- end: `0x18000bb82`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000bb20`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bb47`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bb47`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bb5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bb5e`

## string_xrefs

- `0x18000bb40`: `ntdll.dll`

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
0x18000bb20  push    rbx
0x18000bb22  sub     rsp, 20h
0x18000bb26  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000bb2d  mov     ebx, ecx
0x18000bb2f  test    rax, rax
0x18000bb32  jnz     short loc_18000BB76
0x18000bb34  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bb3b  test    rax, rax
0x18000bb3e  jnz     short loc_18000BB54
0x18000bb40  lea     rcx, ModuleName; "ntdll.dll"
0x18000bb47  call    cs:__imp_GetModuleHandleW
0x18000bb4d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bb54  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000bb5b  mov     rcx, rax; hModule
0x18000bb5e  call    cs:__imp_GetProcAddress
0x18000bb64  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000bb6b  test    rax, rax
0x18000bb6e  jnz     short loc_18000BB76
0x18000bb70  add     rsp, 20h
0x18000bb74  pop     rbx
0x18000bb75  retn
0x18000bb76  mov     ecx, ebx
0x18000bb78  add     rsp, 20h
0x18000bb7c  pop     rbx
0x18000bb7d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

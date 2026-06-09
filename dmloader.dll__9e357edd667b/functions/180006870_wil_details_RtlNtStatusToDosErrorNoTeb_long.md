# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180006870`
- end: `0x1800068d2`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180006870`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006897`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006897`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800068ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800068ae`

## string_xrefs

- `0x180006890`: `ntdll.dll`

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
0x180006870  push    rbx
0x180006872  sub     rsp, 20h
0x180006876  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000687d  mov     ebx, ecx
0x18000687f  test    rax, rax
0x180006882  jnz     short loc_1800068C6
0x180006884  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000688b  test    rax, rax
0x18000688e  jnz     short loc_1800068A4
0x180006890  lea     rcx, ModuleName; "ntdll.dll"
0x180006897  call    cs:__imp_GetModuleHandleW
0x18000689d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800068a4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x1800068ab  mov     rcx, rax; hModule
0x1800068ae  call    cs:__imp_GetProcAddress
0x1800068b4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x1800068bb  test    rax, rax
0x1800068be  jnz     short loc_1800068C6
0x1800068c0  add     rsp, 20h
0x1800068c4  pop     rbx
0x1800068c5  retn
0x1800068c6  mov     ecx, ebx
0x1800068c8  add     rsp, 20h
0x1800068cc  pop     rbx
0x1800068cd  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

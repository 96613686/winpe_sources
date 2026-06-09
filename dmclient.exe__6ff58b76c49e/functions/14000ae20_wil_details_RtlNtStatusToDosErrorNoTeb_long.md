# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x14000ae20`
- end: `0x14000ae7e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x14000ae20`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000ae5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000ae5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000ae47`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000ae47`

## string_xrefs

- `0x14000ae40`: `ntdll.dll`

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
0x14000ae20  push    rbx
0x14000ae22  sub     rsp, 20h
0x14000ae26  mov     ebx, ecx
0x14000ae28  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x14000ae2f  test    rax, rax
0x14000ae32  jnz     short loc_14000AE70
0x14000ae34  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000ae3b  test    rax, rax
0x14000ae3e  jnz     short loc_14000AE54
0x14000ae40  lea     rcx, ModuleName; "ntdll.dll"
0x14000ae47  call    cs:__imp_GetModuleHandleW
0x14000ae4d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000ae54  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x14000ae5b  mov     rcx, rax; hModule
0x14000ae5e  call    cs:__imp_GetProcAddress
0x14000ae64  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x14000ae6b  test    rax, rax
0x14000ae6e  jz      short loc_14000AE78
0x14000ae70  mov     ecx, ebx
0x14000ae72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ae77  nop
0x14000ae78  add     rsp, 20h
0x14000ae7c  pop     rbx
0x14000ae7d  retn
```

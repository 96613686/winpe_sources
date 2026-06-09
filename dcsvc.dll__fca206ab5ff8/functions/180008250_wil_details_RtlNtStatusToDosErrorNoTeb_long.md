# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180008250`
- end: `0x1800082ae`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180008250`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000828e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000828e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008277`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008277`

## string_xrefs

- `0x180008270`: `ntdll.dll`

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
0x180008250  push    rbx
0x180008252  sub     rsp, 20h
0x180008256  mov     ebx, ecx
0x180008258  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000825f  test    rax, rax
0x180008262  jnz     short loc_1800082A0
0x180008264  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000826b  test    rax, rax
0x18000826e  jnz     short loc_180008284
0x180008270  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180008277  call    cs:__imp_GetModuleHandleW
0x18000827d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008284  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000828b  mov     rcx, rax; hModule
0x18000828e  call    cs:__imp_GetProcAddress
0x180008294  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000829b  test    rax, rax
0x18000829e  jz      short loc_1800082A8
0x1800082a0  mov     ecx, ebx
0x1800082a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082a7  nop
0x1800082a8  add     rsp, 20h
0x1800082ac  pop     rbx
0x1800082ad  retn
```

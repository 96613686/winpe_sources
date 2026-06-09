# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x1400125e0`
- end: `0x14001263e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1400125e0`
- `0x14003e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001261e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001261e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140012607`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140012607`

## string_xrefs

- `0x140012600`: `ntdll.dll`

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
0x1400125e0  push    rbx
0x1400125e2  sub     rsp, 20h
0x1400125e6  mov     ebx, ecx
0x1400125e8  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x1400125ef  test    rax, rax
0x1400125f2  jnz     short loc_140012630
0x1400125f4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400125fb  test    rax, rax
0x1400125fe  jnz     short loc_140012614
0x140012600  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x140012607  call    cs:__imp_GetModuleHandleW
0x14001260d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140012614  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x14001261b  mov     rcx, rax; hModule
0x14001261e  call    cs:__imp_GetProcAddress
0x140012624  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x14001262b  test    rax, rax
0x14001262e  jz      short loc_140012638
0x140012630  mov     ecx, ebx
0x140012632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012637  nop
0x140012638  add     rsp, 20h
0x14001263c  pop     rbx
0x14001263d  retn
```

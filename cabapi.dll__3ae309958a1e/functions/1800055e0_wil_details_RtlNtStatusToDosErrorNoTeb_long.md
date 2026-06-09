# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x1800055e0`
- end: `0x180005647`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `103`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800055e0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180005627`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180005627`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180005610`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180005610`

## string_xrefs

- `0x180005609`: `ntdll.dll`

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
0x1800055e0  push    rbx
0x1800055e2  sub     rsp, 30h
0x1800055e6  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800055ef  mov     ebx, ecx
0x1800055f1  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x1800055f8  test    rax, rax
0x1800055fb  jnz     short loc_180005639
0x1800055fd  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005604  test    rax, rax
0x180005607  jnz     short loc_18000561D
0x180005609  lea     rcx, LibFileName; "ntdll.dll"
0x180005610  call    cs:__imp_GetModuleHandleW
0x180005616  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000561d  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180005624  mov     rcx, rax; hModule
0x180005627  call    cs:__imp_GetProcAddress
0x18000562d  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180005634  test    rax, rax
0x180005637  jz      short loc_180005641
0x180005639  mov     ecx, ebx
0x18000563b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005640  nop
0x180005641  add     rsp, 30h
0x180005645  pop     rbx
0x180005646  retn
```

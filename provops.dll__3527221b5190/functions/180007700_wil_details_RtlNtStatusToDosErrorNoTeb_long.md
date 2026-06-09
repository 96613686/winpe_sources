# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180007700`
- end: `0x18000775e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180007700`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007727`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007727`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000773e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000773e`

## string_xrefs

- `0x180007720`: `ntdll.dll`

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
0x180007700  push    rbx
0x180007702  sub     rsp, 20h
0x180007706  mov     ebx, ecx
0x180007708  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000770f  test    rax, rax
0x180007712  jnz     short loc_180007750
0x180007714  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000771b  test    rax, rax
0x18000771e  jnz     short loc_180007734
0x180007720  lea     rcx, ModuleName; "ntdll.dll"
0x180007727  call    cs:__imp_GetModuleHandleW
0x18000772d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007734  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000773b  mov     rcx, rax; hModule
0x18000773e  call    cs:__imp_GetProcAddress
0x180007744  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000774b  test    rax, rax
0x18000774e  jz      short loc_180007758
0x180007750  mov     ecx, ebx
0x180007752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007757  nop
0x180007758  add     rsp, 20h
0x18000775c  pop     rbx
0x18000775d  retn
```

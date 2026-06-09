# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x1400077e0`
- end: `0x14000783e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1400077e0`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007807`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007807`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000781e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000781e`

## string_xrefs

- `0x140007800`: `ntdll.dll`

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
0x1400077e0  push    rbx
0x1400077e2  sub     rsp, 20h
0x1400077e6  mov     ebx, ecx
0x1400077e8  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x1400077ef  test    rax, rax
0x1400077f2  jnz     short loc_140007830
0x1400077f4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400077fb  test    rax, rax
0x1400077fe  jnz     short loc_140007814
0x140007800  lea     rcx, ModuleName; "ntdll.dll"
0x140007807  call    cs:__imp_GetModuleHandleW
0x14000780d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140007814  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x14000781b  mov     rcx, rax; hModule
0x14000781e  call    cs:__imp_GetProcAddress
0x140007824  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x14000782b  test    rax, rax
0x14000782e  jz      short loc_140007838
0x140007830  mov     ecx, ebx
0x140007832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007837  nop
0x140007838  add     rsp, 20h
0x14000783c  pop     rbx
0x14000783d  retn
```

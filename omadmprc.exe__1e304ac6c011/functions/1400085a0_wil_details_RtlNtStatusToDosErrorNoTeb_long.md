# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x1400085a0`
- end: `0x14000860b`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `107`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1400085a0`
- `0x140017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400085c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400085c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400085e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400085e4`

## string_xrefs

- `0x1400085c0`: `ntdll.dll`

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
0x1400085a0  push    rbx
0x1400085a2  sub     rsp, 20h
0x1400085a6  mov     ebx, ecx
0x1400085a8  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x1400085af  test    rax, rax
0x1400085b2  jnz     short loc_1400085FC
0x1400085b4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400085bb  test    rax, rax
0x1400085be  jnz     short loc_1400085DA
0x1400085c0  lea     rcx, ModuleName; "ntdll.dll"
0x1400085c7  call    cs:__imp_GetModuleHandleW
0x1400085ce  nop     dword ptr [rax+rax+00h]
0x1400085d3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400085da  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x1400085e1  mov     rcx, rax; hModule
0x1400085e4  call    cs:__imp_GetProcAddress
0x1400085eb  nop     dword ptr [rax+rax+00h]
0x1400085f0  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x1400085f7  test    rax, rax
0x1400085fa  jz      short loc_140008604
0x1400085fc  mov     ecx, ebx
0x1400085fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008603  nop
0x140008604  add     rsp, 20h
0x140008608  pop     rbx
0x140008609  retn
```

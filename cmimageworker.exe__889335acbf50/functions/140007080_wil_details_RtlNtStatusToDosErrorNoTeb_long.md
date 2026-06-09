# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x140007080`
- end: `0x1400070eb`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `107`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140007080`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400070c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400070c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400070a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400070a7`

## string_xrefs

- `0x1400070a0`: `ntdll.dll`

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
0x140007080  push    rbx
0x140007082  sub     rsp, 20h
0x140007086  mov     ebx, ecx
0x140007088  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x14000708f  test    rax, rax
0x140007092  jnz     short loc_1400070DC
0x140007094  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000709b  test    rax, rax
0x14000709e  jnz     short loc_1400070BA
0x1400070a0  lea     rcx, ModuleName; "ntdll.dll"
0x1400070a7  call    cs:__imp_GetModuleHandleW
0x1400070ae  nop     dword ptr [rax+rax+00h]
0x1400070b3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400070ba  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x1400070c1  mov     rcx, rax; hModule
0x1400070c4  call    cs:__imp_GetProcAddress
0x1400070cb  nop     dword ptr [rax+rax+00h]
0x1400070d0  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x1400070d7  test    rax, rax
0x1400070da  jz      short loc_1400070E4
0x1400070dc  mov     ecx, ebx
0x1400070de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400070e3  nop
0x1400070e4  add     rsp, 20h
0x1400070e8  pop     rbx
0x1400070e9  retn
```

# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x140006d70`
- end: `0x140006dce`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140006d70`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006d97`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006d97`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006dae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006dae`

## string_xrefs

- `0x140006d90`: `ntdll.dll`

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
0x140006d70  push    rbx
0x140006d72  sub     rsp, 20h
0x140006d76  mov     ebx, ecx
0x140006d78  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x140006d7f  test    rax, rax
0x140006d82  jnz     short loc_140006DC0
0x140006d84  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140006d8b  test    rax, rax
0x140006d8e  jnz     short loc_140006DA4
0x140006d90  lea     rcx, ModuleName; "ntdll.dll"
0x140006d97  call    cs:__imp_GetModuleHandleW
0x140006d9d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140006da4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x140006dab  mov     rcx, rax; hModule
0x140006dae  call    cs:__imp_GetProcAddress
0x140006db4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x140006dbb  test    rax, rax
0x140006dbe  jz      short loc_140006DC8
0x140006dc0  mov     ecx, ebx
0x140006dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006dc7  nop
0x140006dc8  add     rsp, 20h
0x140006dcc  pop     rbx
0x140006dcd  retn
```

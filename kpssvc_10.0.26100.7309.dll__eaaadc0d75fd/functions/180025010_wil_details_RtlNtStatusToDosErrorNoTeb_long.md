# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180025010`
- end: `0x180025089`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `121`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180025010`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002505a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002505a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002503d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002503d`

## string_xrefs

- `0x180025036`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall wil::details::RtlNtStatusToDosErrorNoTeb(wil::details *this)
{
  FARPROC ProcAddress; // rax
  unsigned int v2; // ebx
  unsigned int v3; // edi
  HMODULE ModuleHandleW; // rax

  ProcAddress = (FARPROC)`wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb;
  v2 = 0;
  v3 = (unsigned int)this;
  if ( `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb )
    return ((unsigned int (__fastcall *)(_QWORD))ProcAddress)(v3);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "RtlNtStatusToDosErrorNoTeb");
  `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb = (__int64)ProcAddress;
  if ( ProcAddress )
    return ((unsigned int (__fastcall *)(_QWORD))ProcAddress)(v3);
  return v2;
}

```

## disassembly

```asm
0x180025010  mov     [rsp+arg_0], rbx
0x180025015  push    rdi
0x180025016  sub     rsp, 20h
0x18002501a  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180025021  xor     ebx, ebx
0x180025023  mov     edi, ecx
0x180025025  test    rax, rax
0x180025028  jnz     short loc_180025072
0x18002502a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180025031  test    rax, rax
0x180025034  jnz     short loc_180025050
0x180025036  lea     rcx, ModuleName; "ntdll.dll"
0x18002503d  call    cs:__imp_GetModuleHandleW
0x180025044  nop     dword ptr [rax+rax+00h]
0x180025049  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180025050  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180025057  mov     rcx, rax; hModule
0x18002505a  call    cs:__imp_GetProcAddress
0x180025061  nop     dword ptr [rax+rax+00h]
0x180025066  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18002506d  test    rax, rax
0x180025070  jz      short loc_18002507B
0x180025072  mov     ecx, edi
0x180025074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025079  mov     ebx, eax
0x18002507b  mov     eax, ebx
0x18002507d  mov     rbx, [rsp+28h+arg_0]
0x180025082  add     rsp, 20h
0x180025086  pop     rdi
0x180025087  retn
```

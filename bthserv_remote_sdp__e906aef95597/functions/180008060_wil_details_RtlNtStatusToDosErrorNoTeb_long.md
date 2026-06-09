# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180008060`
- end: `0x1800080d9`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `121`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180008060`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000808d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000808d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800080aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800080aa`

## string_xrefs

- `0x180008086`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall wil::details::RtlNtStatusToDosErrorNoTeb(wil::details *this)
{
  unsigned int v1; // edi
  FARPROC ProcAddress; // rax
  unsigned int v3; // ebx
  HMODULE ModuleHandleW; // rax

  v1 = (unsigned int)this;
  ProcAddress = (FARPROC)`wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb;
  v3 = 0;
  if ( `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb )
    return ((unsigned int (__fastcall *)(_QWORD))ProcAddress)(v1);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "RtlNtStatusToDosErrorNoTeb");
  `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb = (__int64)ProcAddress;
  if ( ProcAddress )
    return ((unsigned int (__fastcall *)(_QWORD))ProcAddress)(v1);
  return v3;
}

```

## disassembly

```asm
0x180008060  mov     [rsp+arg_0], rbx
0x180008065  push    rdi
0x180008066  sub     rsp, 20h
0x18000806a  mov     edi, ecx
0x18000806c  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180008073  xor     ebx, ebx
0x180008075  test    rax, rax
0x180008078  jnz     short loc_1800080C2
0x18000807a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008081  test    rax, rax
0x180008084  jnz     short loc_1800080A0
0x180008086  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18000808d  call    cs:__imp_GetModuleHandleW
0x180008094  nop     dword ptr [rax+rax+00h]
0x180008099  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800080a0  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x1800080a7  mov     rcx, rax; hModule
0x1800080aa  call    cs:__imp_GetProcAddress
0x1800080b1  nop     dword ptr [rax+rax+00h]
0x1800080b6  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x1800080bd  test    rax, rax
0x1800080c0  jz      short loc_1800080CB
0x1800080c2  mov     ecx, edi
0x1800080c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080c9  mov     ebx, eax
0x1800080cb  mov     eax, ebx
0x1800080cd  mov     rbx, [rsp+28h+arg_0]
0x1800080d2  add     rsp, 20h
0x1800080d6  pop     rdi
0x1800080d7  retn
```

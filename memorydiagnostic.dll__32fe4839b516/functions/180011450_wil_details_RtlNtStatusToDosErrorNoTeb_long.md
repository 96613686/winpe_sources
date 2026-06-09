# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180011450`
- end: `0x1800114c9`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `121`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180011450`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001147d`
- `KERNEL32!GetModuleHandleW` at `0x18001147d`
- `KERNEL32!GetProcAddress` at `0x18001149a`
- `KERNEL32!GetProcAddress` at `0x18001149a`

## string_xrefs

- `0x180011476`: `ntdll.dll`

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
0x180011450  mov     [rsp+arg_0], rbx
0x180011455  push    rdi
0x180011456  sub     rsp, 20h
0x18001145a  mov     edi, ecx
0x18001145c  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180011463  xor     ebx, ebx
0x180011465  test    rax, rax
0x180011468  jnz     short loc_1800114B2
0x18001146a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011471  test    rax, rax
0x180011474  jnz     short loc_180011490
0x180011476  lea     rcx, ModuleName; "ntdll.dll"
0x18001147d  call    cs:__imp_GetModuleHandleW
0x180011484  nop     dword ptr [rax+rax+00h]
0x180011489  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011490  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180011497  mov     rcx, rax; hModule
0x18001149a  call    cs:__imp_GetProcAddress
0x1800114a1  nop     dword ptr [rax+rax+00h]
0x1800114a6  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x1800114ad  test    rax, rax
0x1800114b0  jz      short loc_1800114BB
0x1800114b2  mov     ecx, edi
0x1800114b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114b9  mov     ebx, eax
0x1800114bb  mov     eax, ebx
0x1800114bd  mov     rbx, [rsp+28h+arg_0]
0x1800114c2  add     rsp, 20h
0x1800114c6  pop     rdi
0x1800114c7  retn
```

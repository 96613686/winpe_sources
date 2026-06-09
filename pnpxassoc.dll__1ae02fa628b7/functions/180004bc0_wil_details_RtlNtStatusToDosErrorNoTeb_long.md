# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180004bc0`
- end: `0x180004c22`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180004bc0`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180004bfe`
- `KERNEL32!GetProcAddress` at `0x180004bfe`
- `KERNEL32!GetModuleHandleW` at `0x180004be7`
- `KERNEL32!GetModuleHandleW` at `0x180004be7`

## string_xrefs

- `0x180004be0`: `ntdll.dll`

## pseudocode

```c
FARPROC __fastcall wil::details::RtlNtStatusToDosErrorNoTeb(wil::details *this)
{
  FARPROC result; // rax
  unsigned int v2; // ebx
  HMODULE ModuleHandleW; // rax

  result = (FARPROC)`wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb;
  v2 = (unsigned int)this;
  if ( `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb )
    return (FARPROC)((__int64 (__fastcall *)(_QWORD))result)(v2);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  result = GetProcAddress(ModuleHandleW, "RtlNtStatusToDosErrorNoTeb");
  `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(_QWORD))result)(v2);
  return result;
}

```

## disassembly

```asm
0x180004bc0  push    rbx
0x180004bc2  sub     rsp, 20h
0x180004bc6  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180004bcd  mov     ebx, ecx
0x180004bcf  test    rax, rax
0x180004bd2  jnz     short loc_180004C16
0x180004bd4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004bdb  test    rax, rax
0x180004bde  jnz     short loc_180004BF4
0x180004be0  lea     rcx, ModuleName; "ntdll.dll"
0x180004be7  call    cs:__imp_GetModuleHandleW
0x180004bed  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004bf4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180004bfb  mov     rcx, rax; hModule
0x180004bfe  call    cs:__imp_GetProcAddress
0x180004c04  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180004c0b  test    rax, rax
0x180004c0e  jnz     short loc_180004C16
0x180004c10  add     rsp, 20h
0x180004c14  pop     rbx
0x180004c15  retn
0x180004c16  mov     ecx, ebx
0x180004c18  add     rsp, 20h
0x180004c1c  pop     rbx
0x180004c1d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

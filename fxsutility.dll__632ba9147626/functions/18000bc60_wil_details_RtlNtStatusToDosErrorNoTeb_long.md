# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x18000bc60`
- end: `0x18000bcbe`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000bc60`
- `0x180017010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000bc87`
- `KERNEL32!GetModuleHandleW` at `0x18000bc87`
- `KERNEL32!GetProcAddress` at `0x18000bc9e`
- `KERNEL32!GetProcAddress` at `0x18000bc9e`

## string_xrefs

- `0x18000bc80`: `ntdll.dll`

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
0x18000bc60  push    rbx
0x18000bc62  sub     rsp, 20h
0x18000bc66  mov     ebx, ecx
0x18000bc68  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000bc6f  test    rax, rax
0x18000bc72  jnz     short loc_18000BCB0
0x18000bc74  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bc7b  test    rax, rax
0x18000bc7e  jnz     short loc_18000BC94
0x18000bc80  lea     rcx, aNtdllDll; "ntdll.dll"
0x18000bc87  call    cs:__imp_GetModuleHandleW
0x18000bc8d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bc94  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000bc9b  mov     rcx, rax; hModule
0x18000bc9e  call    cs:__imp_GetProcAddress
0x18000bca4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000bcab  test    rax, rax
0x18000bcae  jz      short loc_18000BCB8
0x18000bcb0  mov     ecx, ebx
0x18000bcb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcb7  nop
0x18000bcb8  add     rsp, 20h
0x18000bcbc  pop     rbx
0x18000bcbd  retn
```

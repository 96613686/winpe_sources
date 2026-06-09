# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x1800095e0`
- end: `0x180009642`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800095e0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000961e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000961e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009607`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009607`

## string_xrefs

- `0x180009600`: `ntdll.dll`

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
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x1800095e0  push    rbx
0x1800095e2  sub     rsp, 20h
0x1800095e6  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x1800095ed  mov     ebx, ecx
0x1800095ef  test    rax, rax
0x1800095f2  jnz     short loc_180009636
0x1800095f4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800095fb  test    rax, rax
0x1800095fe  jnz     short loc_180009614
0x180009600  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180009607  call    cs:__imp_GetModuleHandleW
0x18000960d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009614  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000961b  mov     rcx, rax; hModule
0x18000961e  call    cs:__imp_GetProcAddress
0x180009624  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000962b  test    rax, rax
0x18000962e  jnz     short loc_180009636
0x180009630  add     rsp, 20h
0x180009634  pop     rbx
0x180009635  retn
0x180009636  mov     ecx, ebx
0x180009638  add     rsp, 20h
0x18000963c  pop     rbx
0x18000963d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

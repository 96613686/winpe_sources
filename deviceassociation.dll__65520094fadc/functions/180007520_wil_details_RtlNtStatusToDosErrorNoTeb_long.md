# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180007520`
- end: `0x180007582`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180007520`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000755e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000755e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007547`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007547`

## string_xrefs

- `0x180007540`: `ntdll.dll`

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
0x180007520  push    rbx
0x180007522  sub     rsp, 20h
0x180007526  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000752d  mov     ebx, ecx
0x18000752f  test    rax, rax
0x180007532  jnz     short loc_180007576
0x180007534  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000753b  test    rax, rax
0x18000753e  jnz     short loc_180007554
0x180007540  lea     rcx, ModuleName; "ntdll.dll"
0x180007547  call    cs:__imp_GetModuleHandleW
0x18000754d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007554  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000755b  mov     rcx, rax; hModule
0x18000755e  call    cs:__imp_GetProcAddress
0x180007564  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000756b  test    rax, rax
0x18000756e  jnz     short loc_180007576
0x180007570  add     rsp, 20h
0x180007574  pop     rbx
0x180007575  retn
0x180007576  mov     ecx, ebx
0x180007578  add     rsp, 20h
0x18000757c  pop     rbx
0x18000757d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

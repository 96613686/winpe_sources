# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180005130`
- end: `0x18000518e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180005130`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000516e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000516e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005157`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005157`

## string_xrefs

- `0x180005150`: `ntdll.dll`

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
0x180005130  push    rbx
0x180005132  sub     rsp, 20h
0x180005136  mov     ebx, ecx
0x180005138  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000513f  test    rax, rax
0x180005142  jnz     short loc_180005180
0x180005144  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000514b  test    rax, rax
0x18000514e  jnz     short loc_180005164
0x180005150  lea     rcx, ModuleName; "ntdll.dll"
0x180005157  call    cs:__imp_GetModuleHandleW
0x18000515d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005164  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000516b  mov     rcx, rax; hModule
0x18000516e  call    cs:__imp_GetProcAddress
0x180005174  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000517b  test    rax, rax
0x18000517e  jz      short loc_180005188
0x180005180  mov     ecx, ebx
0x180005182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005187  nop
0x180005188  add     rsp, 20h
0x18000518c  pop     rbx
0x18000518d  retn
```

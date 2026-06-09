# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180007b50`
- end: `0x180007bb2`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180007b50`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007b77`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007b77`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007b8e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007b8e`

## string_xrefs

- `0x180007b70`: `ntdll.dll`

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
0x180007b50  push    rbx
0x180007b52  sub     rsp, 20h
0x180007b56  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180007b5d  mov     ebx, ecx
0x180007b5f  test    rax, rax
0x180007b62  jnz     short loc_180007BA6
0x180007b64  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007b6b  test    rax, rax
0x180007b6e  jnz     short loc_180007B84
0x180007b70  lea     rcx, ModuleName; "ntdll.dll"
0x180007b77  call    cs:__imp_GetModuleHandleW
0x180007b7d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007b84  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180007b8b  mov     rcx, rax; hModule
0x180007b8e  call    cs:__imp_GetProcAddress
0x180007b94  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180007b9b  test    rax, rax
0x180007b9e  jnz     short loc_180007BA6
0x180007ba0  add     rsp, 20h
0x180007ba4  pop     rbx
0x180007ba5  retn
0x180007ba6  mov     ecx, ebx
0x180007ba8  add     rsp, 20h
0x180007bac  pop     rbx
0x180007bad  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

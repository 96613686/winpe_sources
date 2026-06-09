# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180009200`
- end: `0x180009262`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180009200`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009227`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009227`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000923e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000923e`

## string_xrefs

- `0x180009220`: `ntdll.dll`

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
0x180009200  push    rbx
0x180009202  sub     rsp, 20h
0x180009206  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000920d  mov     ebx, ecx
0x18000920f  test    rax, rax
0x180009212  jnz     short loc_180009256
0x180009214  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000921b  test    rax, rax
0x18000921e  jnz     short loc_180009234
0x180009220  lea     rcx, ModuleName; "ntdll.dll"
0x180009227  call    cs:__imp_GetModuleHandleW
0x18000922d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009234  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000923b  mov     rcx, rax; hModule
0x18000923e  call    cs:__imp_GetProcAddress
0x180009244  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000924b  test    rax, rax
0x18000924e  jnz     short loc_180009256
0x180009250  add     rsp, 20h
0x180009254  pop     rbx
0x180009255  retn
0x180009256  mov     ecx, ebx
0x180009258  add     rsp, 20h
0x18000925c  pop     rbx
0x18000925d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

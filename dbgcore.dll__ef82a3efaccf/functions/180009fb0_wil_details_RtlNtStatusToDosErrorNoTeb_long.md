# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180009fb0`
- end: `0x18000a017`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `103`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180009fb0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180009ff7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180009ff7`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180009fe0`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180009fe0`

## string_xrefs

- `0x180009fd9`: `ntdll.dll`

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
0x180009fb0  push    rbx
0x180009fb2  sub     rsp, 30h
0x180009fb6  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180009fbf  mov     ebx, ecx
0x180009fc1  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180009fc8  test    rax, rax
0x180009fcb  jnz     short loc_18000A009
0x180009fcd  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009fd4  test    rax, rax
0x180009fd7  jnz     short loc_180009FED
0x180009fd9  lea     rcx, ModuleName; "ntdll.dll"
0x180009fe0  call    cs:__imp_GetModuleHandleW
0x180009fe6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009fed  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180009ff4  mov     rcx, rax; hModule
0x180009ff7  call    cs:__imp_GetProcAddress
0x180009ffd  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000a004  test    rax, rax
0x18000a007  jz      short loc_18000A011
0x18000a009  mov     ecx, ebx
0x18000a00b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a010  nop
0x18000a011  add     rsp, 30h
0x18000a015  pop     rbx
0x18000a016  retn
```

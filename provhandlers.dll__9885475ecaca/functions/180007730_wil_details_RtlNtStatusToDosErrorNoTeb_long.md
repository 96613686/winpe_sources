# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180007730`
- end: `0x18000778e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180007730`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007757`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007757`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000776e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000776e`

## string_xrefs

- `0x180007750`: `ntdll.dll`

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
0x180007730  push    rbx
0x180007732  sub     rsp, 20h
0x180007736  mov     ebx, ecx
0x180007738  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000773f  test    rax, rax
0x180007742  jnz     short loc_180007780
0x180007744  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000774b  test    rax, rax
0x18000774e  jnz     short loc_180007764
0x180007750  lea     rcx, ModuleName; "ntdll.dll"
0x180007757  call    cs:__imp_GetModuleHandleW
0x18000775d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007764  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000776b  mov     rcx, rax; hModule
0x18000776e  call    cs:__imp_GetProcAddress
0x180007774  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000777b  test    rax, rax
0x18000777e  jz      short loc_180007788
0x180007780  mov     ecx, ebx
0x180007782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007787  nop
0x180007788  add     rsp, 20h
0x18000778c  pop     rbx
0x18000778d  retn
```

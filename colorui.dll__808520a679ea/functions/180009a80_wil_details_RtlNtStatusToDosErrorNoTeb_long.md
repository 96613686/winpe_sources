# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180009a80`
- end: `0x180009ae2`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180009a80`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180009abe`
- `KERNEL32!GetProcAddress` at `0x180009abe`
- `KERNEL32!GetModuleHandleW` at `0x180009aa7`
- `KERNEL32!GetModuleHandleW` at `0x180009aa7`

## string_xrefs

- `0x180009aa0`: `ntdll.dll`

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
0x180009a80  push    rbx
0x180009a82  sub     rsp, 20h
0x180009a86  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180009a8d  mov     ebx, ecx
0x180009a8f  test    rax, rax
0x180009a92  jnz     short loc_180009AD6
0x180009a94  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009a9b  test    rax, rax
0x180009a9e  jnz     short loc_180009AB4
0x180009aa0  lea     rcx, ModuleName; "ntdll.dll"
0x180009aa7  call    cs:__imp_GetModuleHandleW
0x180009aad  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009ab4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180009abb  mov     rcx, rax; hModule
0x180009abe  call    cs:__imp_GetProcAddress
0x180009ac4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180009acb  test    rax, rax
0x180009ace  jnz     short loc_180009AD6
0x180009ad0  add     rsp, 20h
0x180009ad4  pop     rbx
0x180009ad5  retn
0x180009ad6  mov     ecx, ebx
0x180009ad8  add     rsp, 20h
0x180009adc  pop     rbx
0x180009add  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

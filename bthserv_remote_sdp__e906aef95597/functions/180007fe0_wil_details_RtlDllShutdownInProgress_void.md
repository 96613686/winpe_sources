# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180007fe0`
- end: `0x18000804c`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `108`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180007fe0`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008007`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008007`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008024`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008024`

## string_xrefs

- `0x180008000`: `ntdll.dll`
- `0x18000801a`: `RtlDllShutdownInProgress`

## pseudocode

```c
char __fastcall wil::details::RtlDllShutdownInProgress(wil::details *this)
{
  FARPROC ProcAddress; // rax
  char v2; // bl
  HMODULE ModuleHandleW; // rax

  ProcAddress = (FARPROC)`wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress;
  v2 = 0;
  if ( `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress )
    return ((__int64 (__fastcall *)(wil::details *))ProcAddress)(this);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "RtlDllShutdownInProgress");
  `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress = (__int64)ProcAddress;
  if ( ProcAddress )
    return ((__int64 (__fastcall *)(wil::details *))ProcAddress)(this);
  return v2;
}

```

## disassembly

```asm
0x180007fe0  push    rbx
0x180007fe2  sub     rsp, 20h
0x180007fe6  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180007fed  xor     ebx, ebx
0x180007fef  test    rax, rax
0x180007ff2  jnz     short loc_18000803C
0x180007ff4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007ffb  test    rax, rax
0x180007ffe  jnz     short loc_18000801A
0x180008000  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180008007  call    cs:__imp_GetModuleHandleW
0x18000800e  nop     dword ptr [rax+rax+00h]
0x180008013  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000801a  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180008021  mov     rcx, rax; hModule
0x180008024  call    cs:__imp_GetProcAddress
0x18000802b  nop     dword ptr [rax+rax+00h]
0x180008030  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180008037  test    rax, rax
0x18000803a  jz      short loc_180008043
0x18000803c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008041  mov     bl, al
0x180008043  mov     al, bl
0x180008045  add     rsp, 20h
0x180008049  pop     rbx
0x18000804a  retn
```

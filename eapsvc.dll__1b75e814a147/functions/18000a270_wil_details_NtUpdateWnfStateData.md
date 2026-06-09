# wil_details_NtUpdateWnfStateData

- ea: `0x18000a270`
- end: `0x18000a31a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000778c`
- `0x180009da8`

## callees

- `0x18000a270`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a2be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a2be`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a2a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a2a7`

## string_xrefs

- `0x18000a2a0`: `ntdll.dll`
- `0x18000a2b4`: `NtUpdateWnfStateData`

## pseudocode

```c
__int64 __fastcall wil_details_NtUpdateWnfStateData(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        int a6,
        int a7)
{
  __int64 (__fastcall *v7)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int); // r10
  HMODULE ModuleHandleW; // rax

  v7 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int))g_wil_details_pfnNtUpdateWnfStateData;
  if ( g_wil_details_pfnNtUpdateWnfStateData )
    return v7(a1, a2, a3, 0, 0, a6, a7);
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  g_wil_details_pfnNtUpdateWnfStateData = (__int64)GetProcAddress(ModuleHandleW, "NtUpdateWnfStateData");
  v7 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int))g_wil_details_pfnNtUpdateWnfStateData;
  if ( g_wil_details_pfnNtUpdateWnfStateData )
    return v7(a1, a2, a3, 0, 0, a6, a7);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x18000a270  mov     [rsp+arg_0], rbx
0x18000a275  mov     [rsp+arg_8], rsi
0x18000a27a  push    rdi
0x18000a27b  sub     rsp, 40h
0x18000a27f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000a286  mov     ebx, r8d
0x18000a289  mov     rdi, rdx
0x18000a28c  mov     rsi, rcx
0x18000a28f  test    r10, r10
0x18000a292  jnz     short loc_18000A2DA
0x18000a294  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a29b  test    rax, rax
0x18000a29e  jnz     short loc_18000A2B4
0x18000a2a0  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000a2a7  call    cs:__imp_GetModuleHandleW
0x18000a2ad  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a2b4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000a2bb  mov     rcx, rax; hModule
0x18000a2be  call    cs:__imp_GetProcAddress
0x18000a2c4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000a2cb  mov     r10, rax
0x18000a2ce  test    rax, rax
0x18000a2d1  jnz     short loc_18000A2DA
0x18000a2d3  mov     eax, 0C0000139h
0x18000a2d8  jmp     short loc_18000A30A
0x18000a2da  mov     eax, [rsp+48h+arg_30]
0x18000a2e1  xor     r9d, r9d
0x18000a2e4  mov     [rsp+48h+var_18], eax
0x18000a2e8  mov     r8d, ebx
0x18000a2eb  mov     eax, [rsp+48h+arg_28]
0x18000a2ef  mov     rdx, rdi
0x18000a2f2  mov     [rsp+48h+var_20], eax
0x18000a2f6  mov     rcx, rsi
0x18000a2f9  mov     rax, r10
0x18000a2fc  mov     [rsp+48h+var_28], 0
0x18000a305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a30a  mov     rbx, [rsp+48h+arg_0]
0x18000a30f  mov     rsi, [rsp+48h+arg_8]
0x18000a314  add     rsp, 40h
0x18000a318  pop     rdi
0x18000a319  retn
```

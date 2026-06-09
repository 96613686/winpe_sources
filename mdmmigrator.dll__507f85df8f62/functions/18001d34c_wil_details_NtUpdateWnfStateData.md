# wil_details_NtUpdateWnfStateData

- ea: `0x18001d34c`
- end: `0x18001d3f6`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800186d8`
- `0x18001d064`

## callees

- `0x18001d34c`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001d383`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001d383`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d39a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d39a`

## string_xrefs

- `0x18001d37c`: `ntdll.dll`
- `0x18001d390`: `NtUpdateWnfStateData`

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
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x18001d34c  mov     [rsp+arg_0], rbx
0x18001d351  mov     [rsp+arg_8], rsi
0x18001d356  push    rdi
0x18001d357  sub     rsp, 40h
0x18001d35b  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18001d362  mov     ebx, r8d
0x18001d365  mov     rdi, rdx
0x18001d368  mov     rsi, rcx
0x18001d36b  test    r10, r10
0x18001d36e  jnz     short loc_18001D3B6
0x18001d370  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001d377  test    rax, rax
0x18001d37a  jnz     short loc_18001D390
0x18001d37c  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18001d383  call    cs:__imp_GetModuleHandleW
0x18001d389  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001d390  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001d397  mov     rcx, rax; hModule
0x18001d39a  call    cs:__imp_GetProcAddress
0x18001d3a0  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001d3a7  mov     r10, rax
0x18001d3aa  test    rax, rax
0x18001d3ad  jnz     short loc_18001D3B6
0x18001d3af  mov     eax, 0C0000139h
0x18001d3b4  jmp     short loc_18001D3E6
0x18001d3b6  mov     eax, [rsp+48h+arg_30]
0x18001d3bd  xor     r9d, r9d
0x18001d3c0  mov     [rsp+48h+var_18], eax
0x18001d3c4  mov     r8d, ebx
0x18001d3c7  mov     eax, [rsp+48h+arg_28]
0x18001d3cb  mov     rdx, rdi
0x18001d3ce  mov     [rsp+48h+var_20], eax
0x18001d3d2  mov     rcx, rsi
0x18001d3d5  mov     rax, r10
0x18001d3d8  mov     [rsp+48h+var_28], 0
0x18001d3e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3e6  mov     rbx, [rsp+48h+arg_0]
0x18001d3eb  mov     rsi, [rsp+48h+arg_8]
0x18001d3f0  add     rsp, 40h
0x18001d3f4  pop     rdi
0x18001d3f5  retn
```

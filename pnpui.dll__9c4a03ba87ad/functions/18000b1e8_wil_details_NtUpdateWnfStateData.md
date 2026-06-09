# wil_details_NtUpdateWnfStateData

- ea: `0x18000b1e8`
- end: `0x18000b292`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180008eac`
- `0x18000a6c0`

## callees

- `0x18000b1e8`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b236`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b236`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b21f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b21f`

## string_xrefs

- `0x18000b218`: `ntdll.dll`
- `0x18000b22c`: `NtUpdateWnfStateData`

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
0x18000b1e8  mov     [rsp+arg_0], rbx
0x18000b1ed  mov     [rsp+arg_8], rsi
0x18000b1f2  push    rdi
0x18000b1f3  sub     rsp, 40h
0x18000b1f7  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000b1fe  mov     ebx, r8d
0x18000b201  mov     rdi, rdx
0x18000b204  mov     rsi, rcx
0x18000b207  test    r10, r10
0x18000b20a  jnz     short loc_18000B252
0x18000b20c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b213  test    rax, rax
0x18000b216  jnz     short loc_18000B22C
0x18000b218  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000b21f  call    cs:__imp_GetModuleHandleW
0x18000b225  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b22c  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000b233  mov     rcx, rax; hModule
0x18000b236  call    cs:__imp_GetProcAddress
0x18000b23c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000b243  mov     r10, rax
0x18000b246  test    rax, rax
0x18000b249  jnz     short loc_18000B252
0x18000b24b  mov     eax, 0C0000139h
0x18000b250  jmp     short loc_18000B282
0x18000b252  mov     eax, [rsp+48h+arg_30]
0x18000b259  xor     r9d, r9d
0x18000b25c  mov     [rsp+48h+var_18], eax
0x18000b260  mov     r8d, ebx
0x18000b263  mov     eax, [rsp+48h+arg_28]
0x18000b267  mov     rdx, rdi
0x18000b26a  mov     [rsp+48h+var_20], eax
0x18000b26e  mov     rcx, rsi
0x18000b271  mov     rax, r10
0x18000b274  mov     [rsp+48h+var_28], 0
0x18000b27d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b282  mov     rbx, [rsp+48h+arg_0]
0x18000b287  mov     rsi, [rsp+48h+arg_8]
0x18000b28c  add     rsp, 40h
0x18000b290  pop     rdi
0x18000b291  retn
```

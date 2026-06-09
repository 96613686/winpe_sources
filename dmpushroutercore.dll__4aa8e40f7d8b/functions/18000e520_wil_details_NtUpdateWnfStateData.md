# wil_details_NtUpdateWnfStateData

- ea: `0x18000e520`
- end: `0x18000e5ca`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000b298`
- `0x18000d798`

## callees

- `0x18000e520`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e557`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e557`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e56e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e56e`

## string_xrefs

- `0x18000e550`: `ntdll.dll`
- `0x18000e564`: `NtUpdateWnfStateData`

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
0x18000e520  mov     [rsp+arg_0], rbx
0x18000e525  mov     [rsp+arg_8], rsi
0x18000e52a  push    rdi
0x18000e52b  sub     rsp, 40h
0x18000e52f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000e536  mov     ebx, r8d
0x18000e539  mov     rdi, rdx
0x18000e53c  mov     rsi, rcx
0x18000e53f  test    r10, r10
0x18000e542  jnz     short loc_18000E58A
0x18000e544  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e54b  test    rax, rax
0x18000e54e  jnz     short loc_18000E564
0x18000e550  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000e557  call    cs:__imp_GetModuleHandleW
0x18000e55d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e564  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000e56b  mov     rcx, rax; hModule
0x18000e56e  call    cs:__imp_GetProcAddress
0x18000e574  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000e57b  mov     r10, rax
0x18000e57e  test    rax, rax
0x18000e581  jnz     short loc_18000E58A
0x18000e583  mov     eax, 0C0000139h
0x18000e588  jmp     short loc_18000E5BA
0x18000e58a  mov     eax, [rsp+48h+arg_30]
0x18000e591  xor     r9d, r9d
0x18000e594  mov     [rsp+48h+var_18], eax
0x18000e598  mov     r8d, ebx
0x18000e59b  mov     eax, [rsp+48h+arg_28]
0x18000e59f  mov     rdx, rdi
0x18000e5a2  mov     [rsp+48h+var_20], eax
0x18000e5a6  mov     rcx, rsi
0x18000e5a9  mov     rax, r10
0x18000e5ac  mov     [rsp+48h+var_28], 0
0x18000e5b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5ba  mov     rbx, [rsp+48h+arg_0]
0x18000e5bf  mov     rsi, [rsp+48h+arg_8]
0x18000e5c4  add     rsp, 40h
0x18000e5c8  pop     rdi
0x18000e5c9  retn
```

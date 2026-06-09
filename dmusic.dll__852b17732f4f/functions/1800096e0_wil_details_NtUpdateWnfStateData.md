# wil_details_NtUpdateWnfStateData

- ea: `0x1800096e0`
- end: `0x18000978a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180006fbc`
- `0x180009218`

## callees

- `0x1800096e0`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009717`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009717`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000972e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000972e`

## string_xrefs

- `0x180009710`: `ntdll.dll`
- `0x180009724`: `NtUpdateWnfStateData`

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
0x1800096e0  mov     [rsp+arg_0], rbx
0x1800096e5  mov     [rsp+arg_8], rsi
0x1800096ea  push    rdi
0x1800096eb  sub     rsp, 40h
0x1800096ef  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1800096f6  mov     ebx, r8d
0x1800096f9  mov     rdi, rdx
0x1800096fc  mov     rsi, rcx
0x1800096ff  test    r10, r10
0x180009702  jnz     short loc_18000974A
0x180009704  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000970b  test    rax, rax
0x18000970e  jnz     short loc_180009724
0x180009710  lea     rcx, ModuleName; "ntdll.dll"
0x180009717  call    cs:__imp_GetModuleHandleW
0x18000971d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009724  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000972b  mov     rcx, rax; hModule
0x18000972e  call    cs:__imp_GetProcAddress
0x180009734  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000973b  mov     r10, rax
0x18000973e  test    rax, rax
0x180009741  jnz     short loc_18000974A
0x180009743  mov     eax, 0C0000139h
0x180009748  jmp     short loc_18000977A
0x18000974a  mov     eax, [rsp+48h+arg_30]
0x180009751  xor     r9d, r9d
0x180009754  mov     [rsp+48h+var_18], eax
0x180009758  mov     r8d, ebx
0x18000975b  mov     eax, [rsp+48h+arg_28]
0x18000975f  mov     rdx, rdi
0x180009762  mov     [rsp+48h+var_20], eax
0x180009766  mov     rcx, rsi
0x180009769  mov     rax, r10
0x18000976c  mov     [rsp+48h+var_28], 0
0x180009775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000977a  mov     rbx, [rsp+48h+arg_0]
0x18000977f  mov     rsi, [rsp+48h+arg_8]
0x180009784  add     rsp, 40h
0x180009788  pop     rdi
0x180009789  retn
```

# wil_details_NtUpdateWnfStateData

- ea: `0x180025610`
- end: `0x1800256ba`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180023710`
- `0x180024ef8`

## callees

- `0x180025610`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025647`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025647`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002565e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002565e`

## string_xrefs

- `0x180025640`: `ntdll.dll`
- `0x180025654`: `NtUpdateWnfStateData`

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
0x180025610  mov     [rsp+arg_0], rbx
0x180025615  mov     [rsp+arg_8], rsi
0x18002561a  push    rdi
0x18002561b  sub     rsp, 40h
0x18002561f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180025626  mov     ebx, r8d
0x180025629  mov     rdi, rdx
0x18002562c  mov     rsi, rcx
0x18002562f  test    r10, r10
0x180025632  jnz     short loc_18002567A
0x180025634  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002563b  test    rax, rax
0x18002563e  jnz     short loc_180025654
0x180025640  lea     rcx, ModuleName; "ntdll.dll"
0x180025647  call    cs:__imp_GetModuleHandleW
0x18002564d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180025654  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18002565b  mov     rcx, rax; hModule
0x18002565e  call    cs:__imp_GetProcAddress
0x180025664  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18002566b  mov     r10, rax
0x18002566e  test    rax, rax
0x180025671  jnz     short loc_18002567A
0x180025673  mov     eax, 0C0000139h
0x180025678  jmp     short loc_1800256AA
0x18002567a  mov     eax, [rsp+48h+arg_30]
0x180025681  xor     r9d, r9d
0x180025684  mov     [rsp+48h+var_18], eax
0x180025688  mov     r8d, ebx
0x18002568b  mov     eax, [rsp+48h+arg_28]
0x18002568f  mov     rdx, rdi
0x180025692  mov     [rsp+48h+var_20], eax
0x180025696  mov     rcx, rsi
0x180025699  mov     rax, r10
0x18002569c  mov     [rsp+48h+var_28], 0
0x1800256a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800256aa  mov     rbx, [rsp+48h+arg_0]
0x1800256af  mov     rsi, [rsp+48h+arg_8]
0x1800256b4  add     rsp, 40h
0x1800256b8  pop     rdi
0x1800256b9  retn
```

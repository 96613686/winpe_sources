# wil_details_NtUpdateWnfStateData

- ea: `0x180022f34`
- end: `0x180022fde`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18001c1f8`
- `0x180022b44`

## callees

- `0x180022f34`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022f82`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022f82`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022f6b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022f6b`

## string_xrefs

- `0x180022f64`: `ntdll.dll`
- `0x180022f78`: `NtUpdateWnfStateData`

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
0x180022f34  mov     [rsp+arg_0], rbx
0x180022f39  mov     [rsp+arg_8], rsi
0x180022f3e  push    rdi
0x180022f3f  sub     rsp, 40h
0x180022f43  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180022f4a  mov     ebx, r8d
0x180022f4d  mov     rdi, rdx
0x180022f50  mov     rsi, rcx
0x180022f53  test    r10, r10
0x180022f56  jnz     short loc_180022F9E
0x180022f58  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180022f5f  test    rax, rax
0x180022f62  jnz     short loc_180022F78
0x180022f64  lea     rcx, ModuleName; "ntdll.dll"
0x180022f6b  call    cs:__imp_GetModuleHandleW
0x180022f71  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180022f78  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180022f7f  mov     rcx, rax; hModule
0x180022f82  call    cs:__imp_GetProcAddress
0x180022f88  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180022f8f  mov     r10, rax
0x180022f92  test    rax, rax
0x180022f95  jnz     short loc_180022F9E
0x180022f97  mov     eax, 0C0000139h
0x180022f9c  jmp     short loc_180022FCE
0x180022f9e  mov     eax, [rsp+48h+arg_30]
0x180022fa5  xor     r9d, r9d
0x180022fa8  mov     [rsp+48h+var_18], eax
0x180022fac  mov     r8d, ebx
0x180022faf  mov     eax, [rsp+48h+arg_28]
0x180022fb3  mov     rdx, rdi
0x180022fb6  mov     [rsp+48h+var_20], eax
0x180022fba  mov     rcx, rsi
0x180022fbd  mov     rax, r10
0x180022fc0  mov     [rsp+48h+var_28], 0
0x180022fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022fce  mov     rbx, [rsp+48h+arg_0]
0x180022fd3  mov     rsi, [rsp+48h+arg_8]
0x180022fd8  add     rsp, 40h
0x180022fdc  pop     rdi
0x180022fdd  retn
```

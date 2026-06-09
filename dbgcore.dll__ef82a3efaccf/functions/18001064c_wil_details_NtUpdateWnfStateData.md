# wil_details_NtUpdateWnfStateData

- ea: `0x18001064c`
- end: `0x1800106f6`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800098a8`
- `0x18000f6a8`

## callees

- `0x18001064c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18001069a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18001069a`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180010683`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180010683`

## string_xrefs

- `0x18001067c`: `ntdll.dll`
- `0x180010690`: `NtUpdateWnfStateData`

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
0x18001064c  mov     [rsp+arg_0], rbx
0x180010651  mov     [rsp+arg_8], rsi
0x180010656  push    rdi
0x180010657  sub     rsp, 40h
0x18001065b  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180010662  mov     ebx, r8d
0x180010665  mov     rdi, rdx
0x180010668  mov     rsi, rcx
0x18001066b  test    r10, r10
0x18001066e  jnz     short loc_1800106B6
0x180010670  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180010677  test    rax, rax
0x18001067a  jnz     short loc_180010690
0x18001067c  lea     rcx, ModuleName; "ntdll.dll"
0x180010683  call    cs:__imp_GetModuleHandleW
0x180010689  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180010690  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180010697  mov     rcx, rax; hModule
0x18001069a  call    cs:__imp_GetProcAddress
0x1800106a0  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800106a7  mov     r10, rax
0x1800106aa  test    rax, rax
0x1800106ad  jnz     short loc_1800106B6
0x1800106af  mov     eax, 0C0000139h
0x1800106b4  jmp     short loc_1800106E6
0x1800106b6  mov     eax, [rsp+48h+arg_30]
0x1800106bd  xor     r9d, r9d
0x1800106c0  mov     [rsp+48h+var_18], eax
0x1800106c4  mov     r8d, ebx
0x1800106c7  mov     eax, [rsp+48h+arg_28]
0x1800106cb  mov     rdx, rdi
0x1800106ce  mov     [rsp+48h+var_20], eax
0x1800106d2  mov     rcx, rsi
0x1800106d5  mov     rax, r10
0x1800106d8  mov     [rsp+48h+var_28], 0
0x1800106e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106e6  mov     rbx, [rsp+48h+arg_0]
0x1800106eb  mov     rsi, [rsp+48h+arg_8]
0x1800106f0  add     rsp, 40h
0x1800106f4  pop     rdi
0x1800106f5  retn
```

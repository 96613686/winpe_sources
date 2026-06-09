# wil_details_NtUpdateWnfStateData

- ea: `0x180007e78`
- end: `0x180007f22`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800060b4`
- `0x180007994`

## callees

- `0x180007e78`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007eaf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007eaf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007ec6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007ec6`

## string_xrefs

- `0x180007ea8`: `ntdll.dll`
- `0x180007ebc`: `NtUpdateWnfStateData`

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
0x180007e78  mov     [rsp+arg_0], rbx
0x180007e7d  mov     [rsp+arg_8], rsi
0x180007e82  push    rdi
0x180007e83  sub     rsp, 40h
0x180007e87  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180007e8e  mov     ebx, r8d
0x180007e91  mov     rdi, rdx
0x180007e94  mov     rsi, rcx
0x180007e97  test    r10, r10
0x180007e9a  jnz     short loc_180007EE2
0x180007e9c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007ea3  test    rax, rax
0x180007ea6  jnz     short loc_180007EBC
0x180007ea8  lea     rcx, ModuleName; "ntdll.dll"
0x180007eaf  call    cs:__imp_GetModuleHandleW
0x180007eb5  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007ebc  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180007ec3  mov     rcx, rax; hModule
0x180007ec6  call    cs:__imp_GetProcAddress
0x180007ecc  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180007ed3  mov     r10, rax
0x180007ed6  test    rax, rax
0x180007ed9  jnz     short loc_180007EE2
0x180007edb  mov     eax, 0C0000139h
0x180007ee0  jmp     short loc_180007F12
0x180007ee2  mov     eax, [rsp+48h+arg_30]
0x180007ee9  xor     r9d, r9d
0x180007eec  mov     [rsp+48h+var_18], eax
0x180007ef0  mov     r8d, ebx
0x180007ef3  mov     eax, [rsp+48h+arg_28]
0x180007ef7  mov     rdx, rdi
0x180007efa  mov     [rsp+48h+var_20], eax
0x180007efe  mov     rcx, rsi
0x180007f01  mov     rax, r10
0x180007f04  mov     [rsp+48h+var_28], 0
0x180007f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f12  mov     rbx, [rsp+48h+arg_0]
0x180007f17  mov     rsi, [rsp+48h+arg_8]
0x180007f1c  add     rsp, 40h
0x180007f20  pop     rdi
0x180007f21  retn
```

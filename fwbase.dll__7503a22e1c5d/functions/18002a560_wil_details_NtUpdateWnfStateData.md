# wil_details_NtUpdateWnfStateData

- ea: `0x18002a560`
- end: `0x18002a618`
- name: `wil_details_NtUpdateWnfStateData`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800270f0`

## callees

- `0x18002a560`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a5ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a5ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002a597`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002a597`

## string_xrefs

- `0x18002a590`: `ntdll.dll`
- `0x18002a5a4`: `NtUpdateWnfStateData`

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
0x18002a560  mov     [rsp+arg_0], rbx
0x18002a565  mov     [rsp+arg_8], rsi
0x18002a56a  push    rdi
0x18002a56b  sub     rsp, 40h
0x18002a56f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18002a576  mov     ebx, r8d
0x18002a579  mov     rdi, rdx
0x18002a57c  mov     rsi, rcx
0x18002a57f  test    r10, r10
0x18002a582  jnz     short loc_18002A5D8
0x18002a584  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002a58b  test    rax, rax
0x18002a58e  jnz     short loc_18002A5A4
0x18002a590  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18002a597  call    cs:__imp_GetModuleHandleW
0x18002a59d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002a5a4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18002a5ab  mov     rcx, rax; hModule
0x18002a5ae  call    cs:__imp_GetProcAddress
0x18002a5b4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18002a5bb  mov     r10, rax
0x18002a5be  test    rax, rax
0x18002a5c1  jnz     short loc_18002A5D8
0x18002a5c3  mov     eax, 0C0000139h
0x18002a5c8  mov     rbx, [rsp+48h+arg_0]
0x18002a5cd  mov     rsi, [rsp+48h+arg_8]
0x18002a5d2  add     rsp, 40h
0x18002a5d6  pop     rdi
0x18002a5d7  retn
0x18002a5d8  mov     eax, [rsp+48h+arg_30]
0x18002a5df  xor     r9d, r9d
0x18002a5e2  mov     [rsp+48h+var_18], eax
0x18002a5e6  mov     r8d, ebx
0x18002a5e9  mov     eax, [rsp+48h+arg_28]
0x18002a5ed  mov     rdx, rdi
0x18002a5f0  mov     [rsp+48h+var_20], eax
0x18002a5f4  mov     rcx, rsi
0x18002a5f7  mov     rax, r10
0x18002a5fa  mov     [rsp+48h+var_28], 0
0x18002a603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a608  mov     rbx, [rsp+48h+arg_0]
0x18002a60d  mov     rsi, [rsp+48h+arg_8]
0x18002a612  add     rsp, 40h
0x18002a616  pop     rdi
0x18002a617  retn
```

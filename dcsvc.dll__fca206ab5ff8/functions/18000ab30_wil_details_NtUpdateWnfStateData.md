# wil_details_NtUpdateWnfStateData

- ea: `0x18000ab30`
- end: `0x18000abda`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800077bc`
- `0x18000a478`

## callees

- `0x18000ab30`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ab7e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ab7e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ab67`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ab67`

## string_xrefs

- `0x18000ab60`: `ntdll.dll`
- `0x18000ab74`: `NtUpdateWnfStateData`

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
0x18000ab30  mov     [rsp+arg_0], rbx
0x18000ab35  mov     [rsp+arg_8], rsi
0x18000ab3a  push    rdi
0x18000ab3b  sub     rsp, 40h
0x18000ab3f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000ab46  mov     ebx, r8d
0x18000ab49  mov     rdi, rdx
0x18000ab4c  mov     rsi, rcx
0x18000ab4f  test    r10, r10
0x18000ab52  jnz     short loc_18000AB9A
0x18000ab54  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ab5b  test    rax, rax
0x18000ab5e  jnz     short loc_18000AB74
0x18000ab60  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000ab67  call    cs:__imp_GetModuleHandleW
0x18000ab6d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ab74  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000ab7b  mov     rcx, rax; hModule
0x18000ab7e  call    cs:__imp_GetProcAddress
0x18000ab84  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000ab8b  mov     r10, rax
0x18000ab8e  test    rax, rax
0x18000ab91  jnz     short loc_18000AB9A
0x18000ab93  mov     eax, 0C0000139h
0x18000ab98  jmp     short loc_18000ABCA
0x18000ab9a  mov     eax, [rsp+48h+arg_30]
0x18000aba1  xor     r9d, r9d
0x18000aba4  mov     [rsp+48h+var_18], eax
0x18000aba8  mov     r8d, ebx
0x18000abab  mov     eax, [rsp+48h+arg_28]
0x18000abaf  mov     rdx, rdi
0x18000abb2  mov     [rsp+48h+var_20], eax
0x18000abb6  mov     rcx, rsi
0x18000abb9  mov     rax, r10
0x18000abbc  mov     [rsp+48h+var_28], 0
0x18000abc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abca  mov     rbx, [rsp+48h+arg_0]
0x18000abcf  mov     rsi, [rsp+48h+arg_8]
0x18000abd4  add     rsp, 40h
0x18000abd8  pop     rdi
0x18000abd9  retn
```

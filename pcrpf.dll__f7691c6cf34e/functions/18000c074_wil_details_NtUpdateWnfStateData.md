# wil_details_NtUpdateWnfStateData

- ea: `0x18000c074`
- end: `0x18000c12b`
- name: `wil_details_NtUpdateWnfStateData`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180009018`
- `0x18000ba5c`

## callees

- `0x18000c074`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c0c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c0c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c0ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c0ab`

## string_xrefs

- `0x18000c0a4`: `ntdll.dll`
- `0x18000c0be`: `NtUpdateWnfStateData`

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
0x18000c074  mov     [rsp+arg_0], rbx
0x18000c079  mov     [rsp+arg_8], rsi
0x18000c07e  push    rdi
0x18000c07f  sub     rsp, 40h
0x18000c083  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000c08a  mov     ebx, r8d
0x18000c08d  mov     rdi, rdx
0x18000c090  mov     rsi, rcx
0x18000c093  test    r10, r10
0x18000c096  jnz     short loc_18000C0EA
0x18000c098  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c09f  test    rax, rax
0x18000c0a2  jnz     short loc_18000C0BE
0x18000c0a4  lea     rcx, ModuleName; "ntdll.dll"
0x18000c0ab  call    cs:__imp_GetModuleHandleW
0x18000c0b2  nop     dword ptr [rax+rax+00h]
0x18000c0b7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c0be  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000c0c5  mov     rcx, rax; hModule
0x18000c0c8  call    cs:__imp_GetProcAddress
0x18000c0cf  nop     dword ptr [rax+rax+00h]
0x18000c0d4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000c0db  mov     r10, rax
0x18000c0de  test    rax, rax
0x18000c0e1  jnz     short loc_18000C0EA
0x18000c0e3  mov     eax, 0C0000139h
0x18000c0e8  jmp     short loc_18000C11A
0x18000c0ea  mov     eax, [rsp+48h+arg_30]
0x18000c0f1  xor     r9d, r9d
0x18000c0f4  mov     [rsp+48h+var_18], eax
0x18000c0f8  mov     r8d, ebx
0x18000c0fb  mov     eax, [rsp+48h+arg_28]
0x18000c0ff  mov     rdx, rdi
0x18000c102  mov     [rsp+48h+var_20], eax
0x18000c106  mov     rcx, rsi
0x18000c109  mov     rax, r10
0x18000c10c  mov     [rsp+48h+var_28], 0
0x18000c115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c11a  mov     rbx, [rsp+48h+arg_0]
0x18000c11f  mov     rsi, [rsp+48h+arg_8]
0x18000c124  add     rsp, 40h
0x18000c128  pop     rdi
0x18000c129  retn
```

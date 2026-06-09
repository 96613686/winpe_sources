# wil_details_NtUpdateWnfStateData

- ea: `0x180027474`
- end: `0x180027528`
- name: `wil_details_NtUpdateWnfStateData`
- size: `180`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180024484`
- `0x1800266fc`

## callees

- `0x180027474`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800274c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800274c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800274ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800274ab`

## string_xrefs

- `0x1800274a4`: `ntdll.dll`
- `0x1800274be`: `NtUpdateWnfStateData`

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
0x180027474  mov     [rsp+arg_0], rbx
0x180027479  mov     [rsp+arg_8], rsi
0x18002747e  push    rdi
0x18002747f  sub     rsp, 40h
0x180027483  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18002748a  mov     ebx, r8d
0x18002748d  mov     rdi, rdx
0x180027490  mov     rsi, rcx
0x180027493  test    r10, r10
0x180027496  jnz     short loc_1800274EA
0x180027498  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002749f  test    rax, rax
0x1800274a2  jnz     short loc_1800274BE
0x1800274a4  lea     rcx, ModuleName; "ntdll.dll"
0x1800274ab  call    cs:__imp_GetModuleHandleW
0x1800274b2  nop     dword ptr [rax+rax+00h]
0x1800274b7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800274be  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1800274c5  mov     rcx, rax; hModule
0x1800274c8  call    cs:__imp_GetProcAddress
0x1800274cf  nop     dword ptr [rax+rax+00h]
0x1800274d4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800274db  mov     r10, rax
0x1800274de  test    rax, rax
0x1800274e1  jnz     short loc_1800274EA
0x1800274e3  mov     eax, 0C0000139h
0x1800274e8  jmp     short loc_180027517
0x1800274ea  mov     eax, [rsp+48h+arg_30]
0x1800274f1  xor     r9d, r9d
0x1800274f4  mov     [rsp+48h+var_18], eax
0x1800274f8  mov     r8d, ebx
0x1800274fb  mov     eax, [rsp+48h+arg_28]
0x1800274ff  mov     rdx, rdi
0x180027502  mov     [rsp+48h+var_20], eax
0x180027506  mov     rcx, rsi
0x180027509  and     [rsp+48h+var_28], 0
0x18002750f  mov     rax, r10
0x180027512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027517  mov     rbx, [rsp+48h+arg_0]
0x18002751c  mov     rsi, [rsp+48h+arg_8]
0x180027521  add     rsp, 40h
0x180027525  pop     rdi
0x180027526  retn
```

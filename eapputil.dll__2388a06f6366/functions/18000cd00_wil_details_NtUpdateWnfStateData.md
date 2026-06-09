# wil_details_NtUpdateWnfStateData

- ea: `0x18000cd00`
- end: `0x18000cdaa`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000b4ac`
- `0x18000c86c`

## callees

- `0x18000cd00`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cd37`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cd37`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cd4e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cd4e`

## string_xrefs

- `0x18000cd30`: `ntdll.dll`
- `0x18000cd44`: `NtUpdateWnfStateData`

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
0x18000cd00  mov     [rsp+arg_0], rbx
0x18000cd05  mov     [rsp+arg_8], rsi
0x18000cd0a  push    rdi
0x18000cd0b  sub     rsp, 40h
0x18000cd0f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000cd16  mov     ebx, r8d
0x18000cd19  mov     rdi, rdx
0x18000cd1c  mov     rsi, rcx
0x18000cd1f  test    r10, r10
0x18000cd22  jnz     short loc_18000CD6A
0x18000cd24  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cd2b  test    rax, rax
0x18000cd2e  jnz     short loc_18000CD44
0x18000cd30  lea     rcx, ModuleName; "ntdll.dll"
0x18000cd37  call    cs:__imp_GetModuleHandleW
0x18000cd3d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cd44  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000cd4b  mov     rcx, rax; hModule
0x18000cd4e  call    cs:__imp_GetProcAddress
0x18000cd54  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000cd5b  mov     r10, rax
0x18000cd5e  test    rax, rax
0x18000cd61  jnz     short loc_18000CD6A
0x18000cd63  mov     eax, 0C0000139h
0x18000cd68  jmp     short loc_18000CD9A
0x18000cd6a  mov     eax, [rsp+48h+arg_30]
0x18000cd71  xor     r9d, r9d
0x18000cd74  mov     [rsp+48h+var_18], eax
0x18000cd78  mov     r8d, ebx
0x18000cd7b  mov     eax, [rsp+48h+arg_28]
0x18000cd7f  mov     rdx, rdi
0x18000cd82  mov     [rsp+48h+var_20], eax
0x18000cd86  mov     rcx, rsi
0x18000cd89  mov     rax, r10
0x18000cd8c  mov     [rsp+48h+var_28], 0
0x18000cd95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd9a  mov     rbx, [rsp+48h+arg_0]
0x18000cd9f  mov     rsi, [rsp+48h+arg_8]
0x18000cda4  add     rsp, 40h
0x18000cda8  pop     rdi
0x18000cda9  retn
```

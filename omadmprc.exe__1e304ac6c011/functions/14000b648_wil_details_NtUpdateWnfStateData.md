# wil_details_NtUpdateWnfStateData

- ea: `0x14000b648`
- end: `0x14000b6ff`
- name: `wil_details_NtUpdateWnfStateData`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x140007a24`
- `0x14000a87c`

## callees

- `0x14000b648`
- `0x140017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b67f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b67f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b69c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b69c`

## string_xrefs

- `0x14000b678`: `ntdll.dll`
- `0x14000b692`: `NtUpdateWnfStateData`

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
0x14000b648  mov     [rsp+arg_0], rbx
0x14000b64d  mov     [rsp+arg_8], rsi
0x14000b652  push    rdi
0x14000b653  sub     rsp, 40h
0x14000b657  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14000b65e  mov     ebx, r8d
0x14000b661  mov     rdi, rdx
0x14000b664  mov     rsi, rcx
0x14000b667  test    r10, r10
0x14000b66a  jnz     short loc_14000B6BE
0x14000b66c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b673  test    rax, rax
0x14000b676  jnz     short loc_14000B692
0x14000b678  lea     rcx, ModuleName; "ntdll.dll"
0x14000b67f  call    cs:__imp_GetModuleHandleW
0x14000b686  nop     dword ptr [rax+rax+00h]
0x14000b68b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b692  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14000b699  mov     rcx, rax; hModule
0x14000b69c  call    cs:__imp_GetProcAddress
0x14000b6a3  nop     dword ptr [rax+rax+00h]
0x14000b6a8  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14000b6af  mov     r10, rax
0x14000b6b2  test    rax, rax
0x14000b6b5  jnz     short loc_14000B6BE
0x14000b6b7  mov     eax, 0C0000139h
0x14000b6bc  jmp     short loc_14000B6EE
0x14000b6be  mov     eax, [rsp+48h+arg_30]
0x14000b6c5  xor     r9d, r9d
0x14000b6c8  mov     [rsp+48h+var_18], eax
0x14000b6cc  mov     r8d, ebx
0x14000b6cf  mov     eax, [rsp+48h+arg_28]
0x14000b6d3  mov     rdx, rdi
0x14000b6d6  mov     [rsp+48h+var_20], eax
0x14000b6da  mov     rcx, rsi
0x14000b6dd  mov     rax, r10
0x14000b6e0  mov     [rsp+48h+var_28], 0
0x14000b6e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b6ee  mov     rbx, [rsp+48h+arg_0]
0x14000b6f3  mov     rsi, [rsp+48h+arg_8]
0x14000b6f8  add     rsp, 40h
0x14000b6fc  pop     rdi
0x14000b6fd  retn
```

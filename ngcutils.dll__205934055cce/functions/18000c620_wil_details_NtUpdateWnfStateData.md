# wil_details_NtUpdateWnfStateData

- ea: `0x18000c620`
- end: `0x18000c6ca`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180009d58`
- `0x18000c158`

## callees

- `0x18000c620`
- `0x180061010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c657`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c657`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c66e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c66e`

## string_xrefs

- `0x18000c650`: `ntdll.dll`
- `0x18000c664`: `NtUpdateWnfStateData`

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
0x18000c620  mov     [rsp+arg_0], rbx
0x18000c625  mov     [rsp+arg_8], rsi
0x18000c62a  push    rdi
0x18000c62b  sub     rsp, 40h
0x18000c62f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000c636  mov     ebx, r8d
0x18000c639  mov     rdi, rdx
0x18000c63c  mov     rsi, rcx
0x18000c63f  test    r10, r10
0x18000c642  jnz     short loc_18000C68A
0x18000c644  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c64b  test    rax, rax
0x18000c64e  jnz     short loc_18000C664
0x18000c650  lea     rcx, ModuleName; "ntdll.dll"
0x18000c657  call    cs:__imp_GetModuleHandleW
0x18000c65d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c664  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000c66b  mov     rcx, rax; hModule
0x18000c66e  call    cs:__imp_GetProcAddress
0x18000c674  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000c67b  mov     r10, rax
0x18000c67e  test    rax, rax
0x18000c681  jnz     short loc_18000C68A
0x18000c683  mov     eax, 0C0000139h
0x18000c688  jmp     short loc_18000C6BA
0x18000c68a  mov     eax, [rsp+48h+arg_30]
0x18000c691  xor     r9d, r9d
0x18000c694  mov     [rsp+48h+var_18], eax
0x18000c698  mov     r8d, ebx
0x18000c69b  mov     eax, [rsp+48h+arg_28]
0x18000c69f  mov     rdx, rdi
0x18000c6a2  mov     [rsp+48h+var_20], eax
0x18000c6a6  mov     rcx, rsi
0x18000c6a9  mov     rax, r10
0x18000c6ac  mov     [rsp+48h+var_28], 0
0x18000c6b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6ba  mov     rbx, [rsp+48h+arg_0]
0x18000c6bf  mov     rsi, [rsp+48h+arg_8]
0x18000c6c4  add     rsp, 40h
0x18000c6c8  pop     rdi
0x18000c6c9  retn
```

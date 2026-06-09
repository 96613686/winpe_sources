# wil_details_NtUpdateWnfStateData

- ea: `0x180013f54`
- end: `0x18001400b`
- name: `wil_details_NtUpdateWnfStateData`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000a7a8`
- `0x18000d17c`

## callees

- `0x180013f54`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013f8b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013f8b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013fa8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013fa8`

## string_xrefs

- `0x180013f84`: `ntdll.dll`
- `0x180013f9e`: `NtUpdateWnfStateData`

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
0x180013f54  mov     [rsp+arg_0], rbx
0x180013f59  mov     [rsp+arg_8], rsi
0x180013f5e  push    rdi
0x180013f5f  sub     rsp, 40h
0x180013f63  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180013f6a  mov     ebx, r8d
0x180013f6d  mov     rdi, rdx
0x180013f70  mov     rsi, rcx
0x180013f73  test    r10, r10
0x180013f76  jnz     short loc_180013FCA
0x180013f78  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180013f7f  test    rax, rax
0x180013f82  jnz     short loc_180013F9E
0x180013f84  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180013f8b  call    cs:__imp_GetModuleHandleW
0x180013f92  nop     dword ptr [rax+rax+00h]
0x180013f97  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180013f9e  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180013fa5  mov     rcx, rax; hModule
0x180013fa8  call    cs:__imp_GetProcAddress
0x180013faf  nop     dword ptr [rax+rax+00h]
0x180013fb4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180013fbb  mov     r10, rax
0x180013fbe  test    rax, rax
0x180013fc1  jnz     short loc_180013FCA
0x180013fc3  mov     eax, 0C0000139h
0x180013fc8  jmp     short loc_180013FFA
0x180013fca  mov     eax, [rsp+48h+arg_30]
0x180013fd1  xor     r9d, r9d
0x180013fd4  mov     [rsp+48h+var_18], eax
0x180013fd8  mov     r8d, ebx
0x180013fdb  mov     eax, [rsp+48h+arg_28]
0x180013fdf  mov     rdx, rdi
0x180013fe2  mov     [rsp+48h+var_20], eax
0x180013fe6  mov     rcx, rsi
0x180013fe9  mov     rax, r10
0x180013fec  mov     [rsp+48h+var_28], 0
0x180013ff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ffa  mov     rbx, [rsp+48h+arg_0]
0x180013fff  mov     rsi, [rsp+48h+arg_8]
0x180014004  add     rsp, 40h
0x180014008  pop     rdi
0x180014009  retn
```

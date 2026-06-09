# wil_details_NtUpdateWnfStateData

- ea: `0x14000e234`
- end: `0x14000e2eb`
- name: `wil_details_NtUpdateWnfStateData`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x14000a708`
- `0x14000d3cc`

## callees

- `0x14000e234`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000e288`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000e288`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000e26b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000e26b`

## string_xrefs

- `0x14000e264`: `ntdll.dll`
- `0x14000e27e`: `NtUpdateWnfStateData`

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
0x14000e234  mov     [rsp+arg_0], rbx
0x14000e239  mov     [rsp+arg_8], rsi
0x14000e23e  push    rdi
0x14000e23f  sub     rsp, 40h
0x14000e243  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14000e24a  mov     ebx, r8d
0x14000e24d  mov     rdi, rdx
0x14000e250  mov     rsi, rcx
0x14000e253  test    r10, r10
0x14000e256  jnz     short loc_14000E2AA
0x14000e258  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000e25f  test    rax, rax
0x14000e262  jnz     short loc_14000E27E
0x14000e264  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x14000e26b  call    cs:__imp_GetModuleHandleW
0x14000e272  nop     dword ptr [rax+rax+00h]
0x14000e277  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000e27e  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14000e285  mov     rcx, rax; hModule
0x14000e288  call    cs:__imp_GetProcAddress
0x14000e28f  nop     dword ptr [rax+rax+00h]
0x14000e294  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14000e29b  mov     r10, rax
0x14000e29e  test    rax, rax
0x14000e2a1  jnz     short loc_14000E2AA
0x14000e2a3  mov     eax, 0C0000139h
0x14000e2a8  jmp     short loc_14000E2DA
0x14000e2aa  mov     eax, [rsp+48h+arg_30]
0x14000e2b1  xor     r9d, r9d
0x14000e2b4  mov     [rsp+48h+var_18], eax
0x14000e2b8  mov     r8d, ebx
0x14000e2bb  mov     eax, [rsp+48h+arg_28]
0x14000e2bf  mov     rdx, rdi
0x14000e2c2  mov     [rsp+48h+var_20], eax
0x14000e2c6  mov     rcx, rsi
0x14000e2c9  mov     rax, r10
0x14000e2cc  mov     [rsp+48h+var_28], 0
0x14000e2d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e2da  mov     rbx, [rsp+48h+arg_0]
0x14000e2df  mov     rsi, [rsp+48h+arg_8]
0x14000e2e4  add     rsp, 40h
0x14000e2e8  pop     rdi
0x14000e2e9  retn
```

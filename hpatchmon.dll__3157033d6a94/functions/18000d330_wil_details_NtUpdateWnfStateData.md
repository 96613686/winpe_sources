# wil_details_NtUpdateWnfStateData

- ea: `0x18000d330`
- end: `0x18000d3da`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180008f3c`
- `0x18000ca18`

## callees

- `0x18000d330`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d367`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d367`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d37e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d37e`

## string_xrefs

- `0x18000d360`: `ntdll.dll`
- `0x18000d374`: `NtUpdateWnfStateData`

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
0x18000d330  mov     [rsp+arg_0], rbx
0x18000d335  mov     [rsp+arg_8], rsi
0x18000d33a  push    rdi
0x18000d33b  sub     rsp, 40h
0x18000d33f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000d346  mov     ebx, r8d
0x18000d349  mov     rdi, rdx
0x18000d34c  mov     rsi, rcx
0x18000d34f  test    r10, r10
0x18000d352  jnz     short loc_18000D39A
0x18000d354  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d35b  test    rax, rax
0x18000d35e  jnz     short loc_18000D374
0x18000d360  lea     rcx, ModuleName; "ntdll.dll"
0x18000d367  call    cs:__imp_GetModuleHandleW
0x18000d36d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d374  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000d37b  mov     rcx, rax; hModule
0x18000d37e  call    cs:__imp_GetProcAddress
0x18000d384  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000d38b  mov     r10, rax
0x18000d38e  test    rax, rax
0x18000d391  jnz     short loc_18000D39A
0x18000d393  mov     eax, 0C0000139h
0x18000d398  jmp     short loc_18000D3CA
0x18000d39a  mov     eax, [rsp+48h+arg_30]
0x18000d3a1  xor     r9d, r9d
0x18000d3a4  mov     [rsp+48h+var_18], eax
0x18000d3a8  mov     r8d, ebx
0x18000d3ab  mov     eax, [rsp+48h+arg_28]
0x18000d3af  mov     rdx, rdi
0x18000d3b2  mov     [rsp+48h+var_20], eax
0x18000d3b6  mov     rcx, rsi
0x18000d3b9  mov     rax, r10
0x18000d3bc  mov     [rsp+48h+var_28], 0
0x18000d3c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3ca  mov     rbx, [rsp+48h+arg_0]
0x18000d3cf  mov     rsi, [rsp+48h+arg_8]
0x18000d3d4  add     rsp, 40h
0x18000d3d8  pop     rdi
0x18000d3d9  retn
```

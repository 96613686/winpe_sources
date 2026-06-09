# wil_details_NtUpdateWnfStateData

- ea: `0x180019c48`
- end: `0x180019cf2`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000faac`
- `0x1800190c8`

## callees

- `0x180019c48`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180019c7f`
- `KERNEL32!GetModuleHandleW` at `0x180019c7f`
- `KERNEL32!GetProcAddress` at `0x180019c96`
- `KERNEL32!GetProcAddress` at `0x180019c96`

## string_xrefs

- `0x180019c78`: `ntdll.dll`
- `0x180019c8c`: `NtUpdateWnfStateData`

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
0x180019c48  mov     [rsp+arg_0], rbx
0x180019c4d  mov     [rsp+arg_8], rsi
0x180019c52  push    rdi
0x180019c53  sub     rsp, 40h
0x180019c57  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180019c5e  mov     ebx, r8d
0x180019c61  mov     rdi, rdx
0x180019c64  mov     rsi, rcx
0x180019c67  test    r10, r10
0x180019c6a  jnz     short loc_180019CB2
0x180019c6c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180019c73  test    rax, rax
0x180019c76  jnz     short loc_180019C8C
0x180019c78  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180019c7f  call    cs:__imp_GetModuleHandleW
0x180019c85  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180019c8c  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180019c93  mov     rcx, rax; hModule
0x180019c96  call    cs:__imp_GetProcAddress
0x180019c9c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180019ca3  mov     r10, rax
0x180019ca6  test    rax, rax
0x180019ca9  jnz     short loc_180019CB2
0x180019cab  mov     eax, 0C0000139h
0x180019cb0  jmp     short loc_180019CE2
0x180019cb2  mov     eax, [rsp+48h+arg_30]
0x180019cb9  xor     r9d, r9d
0x180019cbc  mov     [rsp+48h+var_18], eax
0x180019cc0  mov     r8d, ebx
0x180019cc3  mov     eax, [rsp+48h+arg_28]
0x180019cc7  mov     rdx, rdi
0x180019cca  mov     [rsp+48h+var_20], eax
0x180019cce  mov     rcx, rsi
0x180019cd1  mov     rax, r10
0x180019cd4  mov     [rsp+48h+var_28], 0
0x180019cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ce2  mov     rbx, [rsp+48h+arg_0]
0x180019ce7  mov     rsi, [rsp+48h+arg_8]
0x180019cec  add     rsp, 40h
0x180019cf0  pop     rdi
0x180019cf1  retn
```

# wil_details_NtUpdateWnfStateData

- ea: `0x140014650`
- end: `0x1400146fa`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x140011d3c`
- `0x140014188`

## callees

- `0x140014650`
- `0x14003e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001469e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001469e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140014687`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140014687`

## string_xrefs

- `0x140014680`: `ntdll.dll`
- `0x140014694`: `NtUpdateWnfStateData`

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
0x140014650  mov     [rsp+arg_0], rbx
0x140014655  mov     [rsp+arg_8], rsi
0x14001465a  push    rdi
0x14001465b  sub     rsp, 40h
0x14001465f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x140014666  mov     ebx, r8d
0x140014669  mov     rdi, rdx
0x14001466c  mov     rsi, rcx
0x14001466f  test    r10, r10
0x140014672  jnz     short loc_1400146BA
0x140014674  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14001467b  test    rax, rax
0x14001467e  jnz     short loc_140014694
0x140014680  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x140014687  call    cs:__imp_GetModuleHandleW
0x14001468d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140014694  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14001469b  mov     rcx, rax; hModule
0x14001469e  call    cs:__imp_GetProcAddress
0x1400146a4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1400146ab  mov     r10, rax
0x1400146ae  test    rax, rax
0x1400146b1  jnz     short loc_1400146BA
0x1400146b3  mov     eax, 0C0000139h
0x1400146b8  jmp     short loc_1400146EA
0x1400146ba  mov     eax, [rsp+48h+arg_30]
0x1400146c1  xor     r9d, r9d
0x1400146c4  mov     [rsp+48h+var_18], eax
0x1400146c8  mov     r8d, ebx
0x1400146cb  mov     eax, [rsp+48h+arg_28]
0x1400146cf  mov     rdx, rdi
0x1400146d2  mov     [rsp+48h+var_20], eax
0x1400146d6  mov     rcx, rsi
0x1400146d9  mov     rax, r10
0x1400146dc  mov     [rsp+48h+var_28], 0
0x1400146e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400146ea  mov     rbx, [rsp+48h+arg_0]
0x1400146ef  mov     rsi, [rsp+48h+arg_8]
0x1400146f4  add     rsp, 40h
0x1400146f8  pop     rdi
0x1400146f9  retn
```

# wil_details_NtUpdateWnfStateData

- ea: `0x140016ed8`
- end: `0x140016f82`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x14001556c`
- `0x140016c98`

## callees

- `0x140016ed8`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140016f26`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140016f26`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140016f0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140016f0f`

## string_xrefs

- `0x140016f08`: `ntdll.dll`
- `0x140016f1c`: `NtUpdateWnfStateData`

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
0x140016ed8  mov     [rsp+arg_0], rbx
0x140016edd  mov     [rsp+arg_8], rsi
0x140016ee2  push    rdi
0x140016ee3  sub     rsp, 40h
0x140016ee7  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x140016eee  mov     ebx, r8d
0x140016ef1  mov     rdi, rdx
0x140016ef4  mov     rsi, rcx
0x140016ef7  test    r10, r10
0x140016efa  jnz     short loc_140016F42
0x140016efc  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140016f03  test    rax, rax
0x140016f06  jnz     short loc_140016F1C
0x140016f08  lea     rcx, ModuleName; "ntdll.dll"
0x140016f0f  call    cs:__imp_GetModuleHandleW
0x140016f15  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140016f1c  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x140016f23  mov     rcx, rax; hModule
0x140016f26  call    cs:__imp_GetProcAddress
0x140016f2c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x140016f33  mov     r10, rax
0x140016f36  test    rax, rax
0x140016f39  jnz     short loc_140016F42
0x140016f3b  mov     eax, 0C0000139h
0x140016f40  jmp     short loc_140016F72
0x140016f42  mov     eax, [rsp+48h+arg_30]
0x140016f49  xor     r9d, r9d
0x140016f4c  mov     [rsp+48h+var_18], eax
0x140016f50  mov     r8d, ebx
0x140016f53  mov     eax, [rsp+48h+arg_28]
0x140016f57  mov     rdx, rdi
0x140016f5a  mov     [rsp+48h+var_20], eax
0x140016f5e  mov     rcx, rsi
0x140016f61  mov     rax, r10
0x140016f64  mov     [rsp+48h+var_28], 0
0x140016f6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016f72  mov     rbx, [rsp+48h+arg_0]
0x140016f77  mov     rsi, [rsp+48h+arg_8]
0x140016f7c  add     rsp, 40h
0x140016f80  pop     rdi
0x140016f81  retn
```

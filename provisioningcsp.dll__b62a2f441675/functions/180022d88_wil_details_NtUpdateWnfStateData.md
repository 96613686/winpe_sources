# wil_details_NtUpdateWnfStateData

- ea: `0x180022d88`
- end: `0x180022e3f`
- name: `wil_details_NtUpdateWnfStateData`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180021794`
- `0x180022b04`

## callees

- `0x180022d88`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022ddc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022ddc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022dbf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022dbf`

## string_xrefs

- `0x180022db8`: `ntdll.dll`
- `0x180022dd2`: `NtUpdateWnfStateData`

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
0x180022d88  mov     [rsp+arg_0], rbx
0x180022d8d  mov     [rsp+arg_8], rsi
0x180022d92  push    rdi
0x180022d93  sub     rsp, 40h
0x180022d97  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180022d9e  mov     ebx, r8d
0x180022da1  mov     rdi, rdx
0x180022da4  mov     rsi, rcx
0x180022da7  test    r10, r10
0x180022daa  jnz     short loc_180022DFE
0x180022dac  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180022db3  test    rax, rax
0x180022db6  jnz     short loc_180022DD2
0x180022db8  lea     rcx, ModuleName; "ntdll.dll"
0x180022dbf  call    cs:__imp_GetModuleHandleW
0x180022dc6  nop     dword ptr [rax+rax+00h]
0x180022dcb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180022dd2  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180022dd9  mov     rcx, rax; hModule
0x180022ddc  call    cs:__imp_GetProcAddress
0x180022de3  nop     dword ptr [rax+rax+00h]
0x180022de8  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180022def  mov     r10, rax
0x180022df2  test    rax, rax
0x180022df5  jnz     short loc_180022DFE
0x180022df7  mov     eax, 0C0000139h
0x180022dfc  jmp     short loc_180022E2E
0x180022dfe  mov     eax, [rsp+48h+arg_30]
0x180022e05  xor     r9d, r9d
0x180022e08  mov     [rsp+48h+var_18], eax
0x180022e0c  mov     r8d, ebx
0x180022e0f  mov     eax, [rsp+48h+arg_28]
0x180022e13  mov     rdx, rdi
0x180022e16  mov     [rsp+48h+var_20], eax
0x180022e1a  mov     rcx, rsi
0x180022e1d  mov     rax, r10
0x180022e20  mov     [rsp+48h+var_28], 0
0x180022e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e2e  mov     rbx, [rsp+48h+arg_0]
0x180022e33  mov     rsi, [rsp+48h+arg_8]
0x180022e38  add     rsp, 40h
0x180022e3c  pop     rdi
0x180022e3d  retn
```

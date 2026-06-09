# wil_details_NtUpdateWnfStateData

- ea: `0x18000b570`
- end: `0x18000b61a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180008c48`
- `0x18000b0a8`

## callees

- `0x18000b570`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b5a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b5a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b5be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b5be`

## string_xrefs

- `0x18000b5a0`: `ntdll.dll`
- `0x18000b5b4`: `NtUpdateWnfStateData`

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
0x18000b570  mov     [rsp+arg_0], rbx
0x18000b575  mov     [rsp+arg_8], rsi
0x18000b57a  push    rdi
0x18000b57b  sub     rsp, 40h
0x18000b57f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000b586  mov     ebx, r8d
0x18000b589  mov     rdi, rdx
0x18000b58c  mov     rsi, rcx
0x18000b58f  test    r10, r10
0x18000b592  jnz     short loc_18000B5DA
0x18000b594  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b59b  test    rax, rax
0x18000b59e  jnz     short loc_18000B5B4
0x18000b5a0  lea     rcx, ModuleName; "ntdll.dll"
0x18000b5a7  call    cs:__imp_GetModuleHandleW
0x18000b5ad  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b5b4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000b5bb  mov     rcx, rax; hModule
0x18000b5be  call    cs:__imp_GetProcAddress
0x18000b5c4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000b5cb  mov     r10, rax
0x18000b5ce  test    rax, rax
0x18000b5d1  jnz     short loc_18000B5DA
0x18000b5d3  mov     eax, 0C0000139h
0x18000b5d8  jmp     short loc_18000B60A
0x18000b5da  mov     eax, [rsp+48h+arg_30]
0x18000b5e1  xor     r9d, r9d
0x18000b5e4  mov     [rsp+48h+var_18], eax
0x18000b5e8  mov     r8d, ebx
0x18000b5eb  mov     eax, [rsp+48h+arg_28]
0x18000b5ef  mov     rdx, rdi
0x18000b5f2  mov     [rsp+48h+var_20], eax
0x18000b5f6  mov     rcx, rsi
0x18000b5f9  mov     rax, r10
0x18000b5fc  mov     [rsp+48h+var_28], 0
0x18000b605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b60a  mov     rbx, [rsp+48h+arg_0]
0x18000b60f  mov     rsi, [rsp+48h+arg_8]
0x18000b614  add     rsp, 40h
0x18000b618  pop     rdi
0x18000b619  retn
```

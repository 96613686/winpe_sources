# wil_details_NtUpdateWnfStateData

- ea: `0x18001c938`
- end: `0x18001c9ef`
- name: `wil_details_NtUpdateWnfStateData`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180011190`
- `0x180014338`

## callees

- `0x18001c938`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c96f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c96f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c98c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c98c`

## string_xrefs

- `0x18001c968`: `ntdll.dll`
- `0x18001c982`: `NtUpdateWnfStateData`

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
0x18001c938  mov     [rsp+arg_0], rbx
0x18001c93d  mov     [rsp+arg_8], rsi
0x18001c942  push    rdi
0x18001c943  sub     rsp, 40h
0x18001c947  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18001c94e  mov     ebx, r8d
0x18001c951  mov     rdi, rdx
0x18001c954  mov     rsi, rcx
0x18001c957  test    r10, r10
0x18001c95a  jnz     short loc_18001C9AE
0x18001c95c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001c963  test    rax, rax
0x18001c966  jnz     short loc_18001C982
0x18001c968  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18001c96f  call    cs:__imp_GetModuleHandleW
0x18001c976  nop     dword ptr [rax+rax+00h]
0x18001c97b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001c982  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001c989  mov     rcx, rax; hModule
0x18001c98c  call    cs:__imp_GetProcAddress
0x18001c993  nop     dword ptr [rax+rax+00h]
0x18001c998  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001c99f  mov     r10, rax
0x18001c9a2  test    rax, rax
0x18001c9a5  jnz     short loc_18001C9AE
0x18001c9a7  mov     eax, 0C0000139h
0x18001c9ac  jmp     short loc_18001C9DE
0x18001c9ae  mov     eax, [rsp+48h+arg_30]
0x18001c9b5  xor     r9d, r9d
0x18001c9b8  mov     [rsp+48h+var_18], eax
0x18001c9bc  mov     r8d, ebx
0x18001c9bf  mov     eax, [rsp+48h+arg_28]
0x18001c9c3  mov     rdx, rdi
0x18001c9c6  mov     [rsp+48h+var_20], eax
0x18001c9ca  mov     rcx, rsi
0x18001c9cd  mov     rax, r10
0x18001c9d0  mov     [rsp+48h+var_28], 0
0x18001c9d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9de  mov     rbx, [rsp+48h+arg_0]
0x18001c9e3  mov     rsi, [rsp+48h+arg_8]
0x18001c9e8  add     rsp, 40h
0x18001c9ec  pop     rdi
0x18001c9ed  retn
```

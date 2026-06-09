# wil_details_NtUpdateWnfStateData

- ea: `0x18000a3ec`
- end: `0x18000a4a0`
- name: `wil_details_NtUpdateWnfStateData`
- size: `180`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800076f4`
- `0x180009e9c`

## callees

- `0x18000a3ec`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a423`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a423`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a440`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a440`

## string_xrefs

- `0x18000a41c`: `ntdll.dll`
- `0x18000a436`: `NtUpdateWnfStateData`

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
0x18000a3ec  mov     [rsp+arg_0], rbx
0x18000a3f1  mov     [rsp+arg_8], rsi
0x18000a3f6  push    rdi
0x18000a3f7  sub     rsp, 40h
0x18000a3fb  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000a402  mov     ebx, r8d
0x18000a405  mov     rdi, rdx
0x18000a408  mov     rsi, rcx
0x18000a40b  test    r10, r10
0x18000a40e  jnz     short loc_18000A462
0x18000a410  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a417  test    rax, rax
0x18000a41a  jnz     short loc_18000A436
0x18000a41c  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18000a423  call    cs:__imp_GetModuleHandleW
0x18000a42a  nop     dword ptr [rax+rax+00h]
0x18000a42f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a436  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000a43d  mov     rcx, rax; hModule
0x18000a440  call    cs:__imp_GetProcAddress
0x18000a447  nop     dword ptr [rax+rax+00h]
0x18000a44c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000a453  mov     r10, rax
0x18000a456  test    rax, rax
0x18000a459  jnz     short loc_18000A462
0x18000a45b  mov     eax, 0C0000139h
0x18000a460  jmp     short loc_18000A48F
0x18000a462  mov     eax, [rsp+48h+arg_30]
0x18000a469  xor     r9d, r9d
0x18000a46c  mov     [rsp+48h+var_18], eax
0x18000a470  mov     r8d, ebx
0x18000a473  mov     eax, [rsp+48h+arg_28]
0x18000a477  mov     rdx, rdi
0x18000a47a  mov     [rsp+48h+var_20], eax
0x18000a47e  mov     rcx, rsi
0x18000a481  and     [rsp+48h+var_28], 0
0x18000a487  mov     rax, r10
0x18000a48a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a48f  mov     rbx, [rsp+48h+arg_0]
0x18000a494  mov     rsi, [rsp+48h+arg_8]
0x18000a499  add     rsp, 40h
0x18000a49d  pop     rdi
0x18000a49e  retn
```

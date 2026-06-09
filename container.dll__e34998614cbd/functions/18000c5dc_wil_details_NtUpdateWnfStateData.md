# wil_details_NtUpdateWnfStateData

- ea: `0x18000c5dc`
- end: `0x18000c693`
- name: `wil_details_NtUpdateWnfStateData`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800095dc`
- `0x18000c2bc`

## callees

- `0x18000c5dc`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c613`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c613`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c630`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c630`

## string_xrefs

- `0x18000c60c`: `ntdll.dll`
- `0x18000c626`: `NtUpdateWnfStateData`

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
0x18000c5dc  mov     [rsp+arg_0], rbx
0x18000c5e1  mov     [rsp+arg_8], rsi
0x18000c5e6  push    rdi
0x18000c5e7  sub     rsp, 40h
0x18000c5eb  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000c5f2  mov     ebx, r8d
0x18000c5f5  mov     rdi, rdx
0x18000c5f8  mov     rsi, rcx
0x18000c5fb  test    r10, r10
0x18000c5fe  jnz     short loc_18000C652
0x18000c600  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c607  test    rax, rax
0x18000c60a  jnz     short loc_18000C626
0x18000c60c  lea     rcx, ModuleName; "ntdll.dll"
0x18000c613  call    cs:__imp_GetModuleHandleW
0x18000c61a  nop     dword ptr [rax+rax+00h]
0x18000c61f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c626  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000c62d  mov     rcx, rax; hModule
0x18000c630  call    cs:__imp_GetProcAddress
0x18000c637  nop     dword ptr [rax+rax+00h]
0x18000c63c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000c643  mov     r10, rax
0x18000c646  test    rax, rax
0x18000c649  jnz     short loc_18000C652
0x18000c64b  mov     eax, 0C0000139h
0x18000c650  jmp     short loc_18000C682
0x18000c652  mov     eax, [rsp+48h+arg_30]
0x18000c659  xor     r9d, r9d
0x18000c65c  mov     [rsp+48h+var_18], eax
0x18000c660  mov     r8d, ebx
0x18000c663  mov     eax, [rsp+48h+arg_28]
0x18000c667  mov     rdx, rdi
0x18000c66a  mov     [rsp+48h+var_20], eax
0x18000c66e  mov     rcx, rsi
0x18000c671  mov     rax, r10
0x18000c674  mov     [rsp+48h+var_28], 0
0x18000c67d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c682  mov     rbx, [rsp+48h+arg_0]
0x18000c687  mov     rsi, [rsp+48h+arg_8]
0x18000c68c  add     rsp, 40h
0x18000c690  pop     rdi
0x18000c691  retn
```

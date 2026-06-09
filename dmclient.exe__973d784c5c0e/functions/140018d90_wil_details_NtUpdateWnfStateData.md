# wil_details_NtUpdateWnfStateData

- ea: `0x140018d90`
- end: `0x140018e47`
- name: `wil_details_NtUpdateWnfStateData`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1400178ac`
- `0x140018b0c`

## callees

- `0x140018d90`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140018de4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140018de4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140018dc7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140018dc7`

## string_xrefs

- `0x140018dc0`: `ntdll.dll`
- `0x140018dda`: `NtUpdateWnfStateData`

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
0x140018d90  mov     [rsp+arg_0], rbx
0x140018d95  mov     [rsp+arg_8], rsi
0x140018d9a  push    rdi
0x140018d9b  sub     rsp, 40h
0x140018d9f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x140018da6  mov     ebx, r8d
0x140018da9  mov     rdi, rdx
0x140018dac  mov     rsi, rcx
0x140018daf  test    r10, r10
0x140018db2  jnz     short loc_140018E06
0x140018db4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140018dbb  test    rax, rax
0x140018dbe  jnz     short loc_140018DDA
0x140018dc0  lea     rcx, ModuleName; "ntdll.dll"
0x140018dc7  call    cs:__imp_GetModuleHandleW
0x140018dce  nop     dword ptr [rax+rax+00h]
0x140018dd3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140018dda  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x140018de1  mov     rcx, rax; hModule
0x140018de4  call    cs:__imp_GetProcAddress
0x140018deb  nop     dword ptr [rax+rax+00h]
0x140018df0  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x140018df7  mov     r10, rax
0x140018dfa  test    rax, rax
0x140018dfd  jnz     short loc_140018E06
0x140018dff  mov     eax, 0C0000139h
0x140018e04  jmp     short loc_140018E36
0x140018e06  mov     eax, [rsp+48h+arg_30]
0x140018e0d  xor     r9d, r9d
0x140018e10  mov     [rsp+48h+var_18], eax
0x140018e14  mov     r8d, ebx
0x140018e17  mov     eax, [rsp+48h+arg_28]
0x140018e1b  mov     rdx, rdi
0x140018e1e  mov     [rsp+48h+var_20], eax
0x140018e22  mov     rcx, rsi
0x140018e25  mov     rax, r10
0x140018e28  mov     [rsp+48h+var_28], 0
0x140018e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018e36  mov     rbx, [rsp+48h+arg_0]
0x140018e3b  mov     rsi, [rsp+48h+arg_8]
0x140018e40  add     rsp, 40h
0x140018e44  pop     rdi
0x140018e45  retn
```

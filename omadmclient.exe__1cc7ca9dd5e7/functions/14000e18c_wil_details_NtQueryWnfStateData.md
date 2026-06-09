# wil_details_NtQueryWnfStateData

- ea: `0x14000e18c`
- end: `0x14000e22d`
- name: `wil_details_NtQueryWnfStateData`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000a708`
- `0x14000d3cc`

## callees

- `0x14000e18c`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000e1d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000e1d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000e1bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000e1bb`

## string_xrefs

- `0x14000e1b4`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall wil_details_NtQueryWnfStateData(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  __int64 (__fastcall *v6)(__int64, _QWORD, _QWORD, __int64, __int64, __int64); // r10
  HMODULE ModuleHandleW; // rax

  v6 = (__int64 (__fastcall *)(__int64, _QWORD, _QWORD, __int64, __int64, __int64))g_wil_details_pfnNtQueryWnfStateData;
  if ( g_wil_details_pfnNtQueryWnfStateData )
    return v6(a1, 0, 0, a4, a5, a6);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  g_wil_details_pfnNtQueryWnfStateData = (__int64)GetProcAddress(ModuleHandleW, "NtQueryWnfStateData");
  v6 = (__int64 (__fastcall *)(__int64, _QWORD, _QWORD, __int64, __int64, __int64))g_wil_details_pfnNtQueryWnfStateData;
  if ( g_wil_details_pfnNtQueryWnfStateData )
    return v6(a1, 0, 0, a4, a5, a6);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x14000e18c  mov     [rsp+arg_0], rbx
0x14000e191  push    rdi
0x14000e192  sub     rsp, 40h
0x14000e196  mov     r10, cs:g_wil_details_pfnNtQueryWnfStateData
0x14000e19d  mov     rbx, r9
0x14000e1a0  mov     rdi, rcx
0x14000e1a3  test    r10, r10
0x14000e1a6  jnz     short loc_14000E1FA
0x14000e1a8  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000e1af  test    rax, rax
0x14000e1b2  jnz     short loc_14000E1CE
0x14000e1b4  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x14000e1bb  call    cs:__imp_GetModuleHandleW
0x14000e1c2  nop     dword ptr [rax+rax+00h]
0x14000e1c7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000e1ce  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14000e1d5  mov     rcx, rax; hModule
0x14000e1d8  call    cs:__imp_GetProcAddress
0x14000e1df  nop     dword ptr [rax+rax+00h]
0x14000e1e4  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x14000e1eb  mov     r10, rax
0x14000e1ee  test    rax, rax
0x14000e1f1  jnz     short loc_14000E1FA
0x14000e1f3  mov     eax, 0C0000139h
0x14000e1f8  jmp     short loc_14000E221
0x14000e1fa  mov     rax, [rsp+48h+arg_28]
0x14000e1ff  mov     r9, rbx
0x14000e202  mov     [rsp+48h+var_20], rax
0x14000e207  xor     r8d, r8d
0x14000e20a  mov     rax, [rsp+48h+arg_20]
0x14000e20f  xor     edx, edx
0x14000e211  mov     [rsp+48h+var_28], rax
0x14000e216  mov     rcx, rdi
0x14000e219  mov     rax, r10
0x14000e21c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e221  mov     rbx, [rsp+48h+arg_0]
0x14000e226  add     rsp, 40h
0x14000e22a  pop     rdi
0x14000e22b  retn
```

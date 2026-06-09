# wil_details_NtQueryWnfStateData

- ea: `0x18000c534`
- end: `0x18000c5d5`
- name: `wil_details_NtQueryWnfStateData`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800095dc`
- `0x18000c2bc`

## callees

- `0x18000c534`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c563`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c563`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c580`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c580`

## string_xrefs

- `0x18000c55c`: `ntdll.dll`

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
0x18000c534  mov     [rsp+arg_0], rbx
0x18000c539  push    rdi
0x18000c53a  sub     rsp, 40h
0x18000c53e  mov     r10, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000c545  mov     rbx, r9
0x18000c548  mov     rdi, rcx
0x18000c54b  test    r10, r10
0x18000c54e  jnz     short loc_18000C5A2
0x18000c550  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c557  test    rax, rax
0x18000c55a  jnz     short loc_18000C576
0x18000c55c  lea     rcx, ModuleName; "ntdll.dll"
0x18000c563  call    cs:__imp_GetModuleHandleW
0x18000c56a  nop     dword ptr [rax+rax+00h]
0x18000c56f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c576  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000c57d  mov     rcx, rax; hModule
0x18000c580  call    cs:__imp_GetProcAddress
0x18000c587  nop     dword ptr [rax+rax+00h]
0x18000c58c  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000c593  mov     r10, rax
0x18000c596  test    rax, rax
0x18000c599  jnz     short loc_18000C5A2
0x18000c59b  mov     eax, 0C0000139h
0x18000c5a0  jmp     short loc_18000C5C9
0x18000c5a2  mov     rax, [rsp+48h+arg_28]
0x18000c5a7  mov     r9, rbx
0x18000c5aa  mov     [rsp+48h+var_20], rax
0x18000c5af  xor     r8d, r8d
0x18000c5b2  mov     rax, [rsp+48h+arg_20]
0x18000c5b7  xor     edx, edx
0x18000c5b9  mov     [rsp+48h+var_28], rax
0x18000c5be  mov     rcx, rdi
0x18000c5c1  mov     rax, r10
0x18000c5c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5c9  mov     rbx, [rsp+48h+arg_0]
0x18000c5ce  add     rsp, 40h
0x18000c5d2  pop     rdi
0x18000c5d3  retn
```

# wil_details_NtQueryWnfStateData

- ea: `0x140018ce8`
- end: `0x140018d89`
- name: `wil_details_NtQueryWnfStateData`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400178ac`
- `0x140018b0c`

## callees

- `0x140018ce8`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140018d34`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140018d34`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140018d17`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140018d17`

## string_xrefs

- `0x140018d10`: `ntdll.dll`

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
0x140018ce8  mov     [rsp+arg_0], rbx
0x140018ced  push    rdi
0x140018cee  sub     rsp, 40h
0x140018cf2  mov     r10, cs:g_wil_details_pfnNtQueryWnfStateData
0x140018cf9  mov     rbx, r9
0x140018cfc  mov     rdi, rcx
0x140018cff  test    r10, r10
0x140018d02  jnz     short loc_140018D56
0x140018d04  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140018d0b  test    rax, rax
0x140018d0e  jnz     short loc_140018D2A
0x140018d10  lea     rcx, ModuleName; "ntdll.dll"
0x140018d17  call    cs:__imp_GetModuleHandleW
0x140018d1e  nop     dword ptr [rax+rax+00h]
0x140018d23  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140018d2a  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x140018d31  mov     rcx, rax; hModule
0x140018d34  call    cs:__imp_GetProcAddress
0x140018d3b  nop     dword ptr [rax+rax+00h]
0x140018d40  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x140018d47  mov     r10, rax
0x140018d4a  test    rax, rax
0x140018d4d  jnz     short loc_140018D56
0x140018d4f  mov     eax, 0C0000139h
0x140018d54  jmp     short loc_140018D7D
0x140018d56  mov     rax, [rsp+48h+arg_28]
0x140018d5b  mov     r9, rbx
0x140018d5e  mov     [rsp+48h+var_20], rax
0x140018d63  xor     r8d, r8d
0x140018d66  mov     rax, [rsp+48h+arg_20]
0x140018d6b  xor     edx, edx
0x140018d6d  mov     [rsp+48h+var_28], rax
0x140018d72  mov     rcx, rdi
0x140018d75  mov     rax, r10
0x140018d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018d7d  mov     rbx, [rsp+48h+arg_0]
0x140018d82  add     rsp, 40h
0x140018d86  pop     rdi
0x140018d87  retn
```

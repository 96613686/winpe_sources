# wil_details_NtQueryWnfStateData

- ea: `0x14000b5a0`
- end: `0x14000b641`
- name: `wil_details_NtQueryWnfStateData`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140007a24`
- `0x14000a87c`

## callees

- `0x14000b5a0`
- `0x140017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b5cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b5cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b5ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b5ec`

## string_xrefs

- `0x14000b5c8`: `ntdll.dll`

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
0x14000b5a0  mov     [rsp+arg_0], rbx
0x14000b5a5  push    rdi
0x14000b5a6  sub     rsp, 40h
0x14000b5aa  mov     r10, cs:g_wil_details_pfnNtQueryWnfStateData
0x14000b5b1  mov     rbx, r9
0x14000b5b4  mov     rdi, rcx
0x14000b5b7  test    r10, r10
0x14000b5ba  jnz     short loc_14000B60E
0x14000b5bc  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b5c3  test    rax, rax
0x14000b5c6  jnz     short loc_14000B5E2
0x14000b5c8  lea     rcx, ModuleName; "ntdll.dll"
0x14000b5cf  call    cs:__imp_GetModuleHandleW
0x14000b5d6  nop     dword ptr [rax+rax+00h]
0x14000b5db  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b5e2  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14000b5e9  mov     rcx, rax; hModule
0x14000b5ec  call    cs:__imp_GetProcAddress
0x14000b5f3  nop     dword ptr [rax+rax+00h]
0x14000b5f8  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x14000b5ff  mov     r10, rax
0x14000b602  test    rax, rax
0x14000b605  jnz     short loc_14000B60E
0x14000b607  mov     eax, 0C0000139h
0x14000b60c  jmp     short loc_14000B635
0x14000b60e  mov     rax, [rsp+48h+arg_28]
0x14000b613  mov     r9, rbx
0x14000b616  mov     [rsp+48h+var_20], rax
0x14000b61b  xor     r8d, r8d
0x14000b61e  mov     rax, [rsp+48h+arg_20]
0x14000b623  xor     edx, edx
0x14000b625  mov     [rsp+48h+var_28], rax
0x14000b62a  mov     rcx, rdi
0x14000b62d  mov     rax, r10
0x14000b630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b635  mov     rbx, [rsp+48h+arg_0]
0x14000b63a  add     rsp, 40h
0x14000b63e  pop     rdi
0x14000b63f  retn
```

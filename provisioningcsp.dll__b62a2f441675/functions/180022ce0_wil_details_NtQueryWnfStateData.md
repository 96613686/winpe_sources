# wil_details_NtQueryWnfStateData

- ea: `0x180022ce0`
- end: `0x180022d81`
- name: `wil_details_NtQueryWnfStateData`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180021794`
- `0x180022b04`

## callees

- `0x180022ce0`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022d2c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022d2c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022d0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022d0f`

## string_xrefs

- `0x180022d08`: `ntdll.dll`

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
0x180022ce0  mov     [rsp+arg_0], rbx
0x180022ce5  push    rdi
0x180022ce6  sub     rsp, 40h
0x180022cea  mov     r10, cs:g_wil_details_pfnNtQueryWnfStateData
0x180022cf1  mov     rbx, r9
0x180022cf4  mov     rdi, rcx
0x180022cf7  test    r10, r10
0x180022cfa  jnz     short loc_180022D4E
0x180022cfc  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180022d03  test    rax, rax
0x180022d06  jnz     short loc_180022D22
0x180022d08  lea     rcx, ModuleName; "ntdll.dll"
0x180022d0f  call    cs:__imp_GetModuleHandleW
0x180022d16  nop     dword ptr [rax+rax+00h]
0x180022d1b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180022d22  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180022d29  mov     rcx, rax; hModule
0x180022d2c  call    cs:__imp_GetProcAddress
0x180022d33  nop     dword ptr [rax+rax+00h]
0x180022d38  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180022d3f  mov     r10, rax
0x180022d42  test    rax, rax
0x180022d45  jnz     short loc_180022D4E
0x180022d47  mov     eax, 0C0000139h
0x180022d4c  jmp     short loc_180022D75
0x180022d4e  mov     rax, [rsp+48h+arg_28]
0x180022d53  mov     r9, rbx
0x180022d56  mov     [rsp+48h+var_20], rax
0x180022d5b  xor     r8d, r8d
0x180022d5e  mov     rax, [rsp+48h+arg_20]
0x180022d63  xor     edx, edx
0x180022d65  mov     [rsp+48h+var_28], rax
0x180022d6a  mov     rcx, rdi
0x180022d6d  mov     rax, r10
0x180022d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d75  mov     rbx, [rsp+48h+arg_0]
0x180022d7a  add     rsp, 40h
0x180022d7e  pop     rdi
0x180022d7f  retn
```

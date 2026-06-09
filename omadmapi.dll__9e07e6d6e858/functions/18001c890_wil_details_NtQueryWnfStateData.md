# wil_details_NtQueryWnfStateData

- ea: `0x18001c890`
- end: `0x18001c931`
- name: `wil_details_NtQueryWnfStateData`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180011190`
- `0x180014338`

## callees

- `0x18001c890`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c8bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c8bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c8dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c8dc`

## string_xrefs

- `0x18001c8b8`: `ntdll.dll`

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
0x18001c890  mov     [rsp+arg_0], rbx
0x18001c895  push    rdi
0x18001c896  sub     rsp, 40h
0x18001c89a  mov     r10, cs:g_wil_details_pfnNtQueryWnfStateData
0x18001c8a1  mov     rbx, r9
0x18001c8a4  mov     rdi, rcx
0x18001c8a7  test    r10, r10
0x18001c8aa  jnz     short loc_18001C8FE
0x18001c8ac  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001c8b3  test    rax, rax
0x18001c8b6  jnz     short loc_18001C8D2
0x18001c8b8  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18001c8bf  call    cs:__imp_GetModuleHandleW
0x18001c8c6  nop     dword ptr [rax+rax+00h]
0x18001c8cb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001c8d2  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18001c8d9  mov     rcx, rax; hModule
0x18001c8dc  call    cs:__imp_GetProcAddress
0x18001c8e3  nop     dword ptr [rax+rax+00h]
0x18001c8e8  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18001c8ef  mov     r10, rax
0x18001c8f2  test    rax, rax
0x18001c8f5  jnz     short loc_18001C8FE
0x18001c8f7  mov     eax, 0C0000139h
0x18001c8fc  jmp     short loc_18001C925
0x18001c8fe  mov     rax, [rsp+48h+arg_28]
0x18001c903  mov     r9, rbx
0x18001c906  mov     [rsp+48h+var_20], rax
0x18001c90b  xor     r8d, r8d
0x18001c90e  mov     rax, [rsp+48h+arg_20]
0x18001c913  xor     edx, edx
0x18001c915  mov     [rsp+48h+var_28], rax
0x18001c91a  mov     rcx, rdi
0x18001c91d  mov     rax, r10
0x18001c920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c925  mov     rbx, [rsp+48h+arg_0]
0x18001c92a  add     rsp, 40h
0x18001c92e  pop     rdi
0x18001c92f  retn
```

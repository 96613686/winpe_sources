# wil_details_NtQueryWnfStateData

- ea: `0x140020714`
- end: `0x1400207b5`
- name: `wil_details_NtQueryWnfStateData`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14001cf68`
- `0x140020538`

## callees

- `0x140020714`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140020760`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140020760`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140020743`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140020743`

## string_xrefs

- `0x14002073c`: `ntdll.dll`

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
0x140020714  mov     [rsp+arg_0], rbx
0x140020719  push    rdi
0x14002071a  sub     rsp, 40h
0x14002071e  mov     r10, cs:g_wil_details_pfnNtQueryWnfStateData
0x140020725  mov     rbx, r9
0x140020728  mov     rdi, rcx
0x14002072b  test    r10, r10
0x14002072e  jnz     short loc_140020782
0x140020730  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140020737  test    rax, rax
0x14002073a  jnz     short loc_140020756
0x14002073c  lea     rcx, ModuleName; "ntdll.dll"
0x140020743  call    cs:__imp_GetModuleHandleW
0x14002074a  nop     dword ptr [rax+rax+00h]
0x14002074f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140020756  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14002075d  mov     rcx, rax; hModule
0x140020760  call    cs:__imp_GetProcAddress
0x140020767  nop     dword ptr [rax+rax+00h]
0x14002076c  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x140020773  mov     r10, rax
0x140020776  test    rax, rax
0x140020779  jnz     short loc_140020782
0x14002077b  mov     eax, 0C0000139h
0x140020780  jmp     short loc_1400207A9
0x140020782  mov     rax, [rsp+48h+arg_28]
0x140020787  mov     r9, rbx
0x14002078a  mov     [rsp+48h+var_20], rax
0x14002078f  xor     r8d, r8d
0x140020792  mov     rax, [rsp+48h+arg_20]
0x140020797  xor     edx, edx
0x140020799  mov     [rsp+48h+var_28], rax
0x14002079e  mov     rcx, rdi
0x1400207a1  mov     rax, r10
0x1400207a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400207a9  mov     rbx, [rsp+48h+arg_0]
0x1400207ae  add     rsp, 40h
0x1400207b2  pop     rdi
0x1400207b3  retn
```

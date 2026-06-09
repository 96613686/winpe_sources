# wil_details_NtQueryWnfStateData

- ea: `0x1800082a4`
- end: `0x180008345`
- name: `wil_details_NtQueryWnfStateData`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000658c`
- `0x1800080bc`

## callees

- `0x1800082a4`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800082f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800082f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800082d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800082d3`

## string_xrefs

- `0x1800082cc`: `ntdll.dll`

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
0x1800082a4  mov     [rsp+arg_0], rbx
0x1800082a9  push    rdi
0x1800082aa  sub     rsp, 40h
0x1800082ae  mov     r10, cs:g_wil_details_pfnNtQueryWnfStateData
0x1800082b5  mov     rbx, r9
0x1800082b8  mov     rdi, rcx
0x1800082bb  test    r10, r10
0x1800082be  jnz     short loc_180008312
0x1800082c0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800082c7  test    rax, rax
0x1800082ca  jnz     short loc_1800082E6
0x1800082cc  lea     rcx, ModuleName; "ntdll.dll"
0x1800082d3  call    cs:__imp_GetModuleHandleW
0x1800082da  nop     dword ptr [rax+rax+00h]
0x1800082df  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800082e6  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1800082ed  mov     rcx, rax; hModule
0x1800082f0  call    cs:__imp_GetProcAddress
0x1800082f7  nop     dword ptr [rax+rax+00h]
0x1800082fc  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180008303  mov     r10, rax
0x180008306  test    rax, rax
0x180008309  jnz     short loc_180008312
0x18000830b  mov     eax, 0C0000139h
0x180008310  jmp     short loc_180008339
0x180008312  mov     rax, [rsp+48h+arg_28]
0x180008317  mov     r9, rbx
0x18000831a  mov     [rsp+48h+var_20], rax
0x18000831f  xor     r8d, r8d
0x180008322  mov     rax, [rsp+48h+arg_20]
0x180008327  xor     edx, edx
0x180008329  mov     [rsp+48h+var_28], rax
0x18000832e  mov     rcx, rdi
0x180008331  mov     rax, r10
0x180008334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008339  mov     rbx, [rsp+48h+arg_0]
0x18000833e  add     rsp, 40h
0x180008342  pop     rdi
0x180008343  retn
```

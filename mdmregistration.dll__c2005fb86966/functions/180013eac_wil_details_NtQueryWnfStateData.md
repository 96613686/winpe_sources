# wil_details_NtQueryWnfStateData

- ea: `0x180013eac`
- end: `0x180013f4d`
- name: `wil_details_NtQueryWnfStateData`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a7a8`
- `0x18000d17c`

## callees

- `0x180013eac`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013edb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013edb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013ef8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013ef8`

## string_xrefs

- `0x180013ed4`: `ntdll.dll`

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
0x180013eac  mov     [rsp+arg_0], rbx
0x180013eb1  push    rdi
0x180013eb2  sub     rsp, 40h
0x180013eb6  mov     r10, cs:g_wil_details_pfnNtQueryWnfStateData
0x180013ebd  mov     rbx, r9
0x180013ec0  mov     rdi, rcx
0x180013ec3  test    r10, r10
0x180013ec6  jnz     short loc_180013F1A
0x180013ec8  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180013ecf  test    rax, rax
0x180013ed2  jnz     short loc_180013EEE
0x180013ed4  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180013edb  call    cs:__imp_GetModuleHandleW
0x180013ee2  nop     dword ptr [rax+rax+00h]
0x180013ee7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180013eee  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180013ef5  mov     rcx, rax; hModule
0x180013ef8  call    cs:__imp_GetProcAddress
0x180013eff  nop     dword ptr [rax+rax+00h]
0x180013f04  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180013f0b  mov     r10, rax
0x180013f0e  test    rax, rax
0x180013f11  jnz     short loc_180013F1A
0x180013f13  mov     eax, 0C0000139h
0x180013f18  jmp     short loc_180013F41
0x180013f1a  mov     rax, [rsp+48h+arg_28]
0x180013f1f  mov     r9, rbx
0x180013f22  mov     [rsp+48h+var_20], rax
0x180013f27  xor     r8d, r8d
0x180013f2a  mov     rax, [rsp+48h+arg_20]
0x180013f2f  xor     edx, edx
0x180013f31  mov     [rsp+48h+var_28], rax
0x180013f36  mov     rcx, rdi
0x180013f39  mov     rax, r10
0x180013f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f41  mov     rbx, [rsp+48h+arg_0]
0x180013f46  add     rsp, 40h
0x180013f4a  pop     rdi
0x180013f4b  retn
```

# wil_details_NtQueryWnfStateData

- ea: `0x18001acf0`
- end: `0x18001ad91`
- name: `wil_details_NtQueryWnfStateData`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800103c4`
- `0x180019f6c`

## callees

- `0x18001acf0`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001ad1f`
- `KERNEL32!GetModuleHandleW` at `0x18001ad1f`
- `KERNEL32!GetProcAddress` at `0x18001ad3c`
- `KERNEL32!GetProcAddress` at `0x18001ad3c`

## string_xrefs

- `0x18001ad18`: `ntdll.dll`

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
0x18001acf0  mov     [rsp+arg_0], rbx
0x18001acf5  push    rdi
0x18001acf6  sub     rsp, 40h
0x18001acfa  mov     r10, cs:g_wil_details_pfnNtQueryWnfStateData
0x18001ad01  mov     rbx, r9
0x18001ad04  mov     rdi, rcx
0x18001ad07  test    r10, r10
0x18001ad0a  jnz     short loc_18001AD5E
0x18001ad0c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001ad13  test    rax, rax
0x18001ad16  jnz     short loc_18001AD32
0x18001ad18  lea     rcx, ModuleName; "ntdll.dll"
0x18001ad1f  call    cs:__imp_GetModuleHandleW
0x18001ad26  nop     dword ptr [rax+rax+00h]
0x18001ad2b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001ad32  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18001ad39  mov     rcx, rax; hModule
0x18001ad3c  call    cs:__imp_GetProcAddress
0x18001ad43  nop     dword ptr [rax+rax+00h]
0x18001ad48  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18001ad4f  mov     r10, rax
0x18001ad52  test    rax, rax
0x18001ad55  jnz     short loc_18001AD5E
0x18001ad57  mov     eax, 0C0000139h
0x18001ad5c  jmp     short loc_18001AD85
0x18001ad5e  mov     rax, [rsp+48h+arg_28]
0x18001ad63  mov     r9, rbx
0x18001ad66  mov     [rsp+48h+var_20], rax
0x18001ad6b  xor     r8d, r8d
0x18001ad6e  mov     rax, [rsp+48h+arg_20]
0x18001ad73  xor     edx, edx
0x18001ad75  mov     [rsp+48h+var_28], rax
0x18001ad7a  mov     rcx, rdi
0x18001ad7d  mov     rax, r10
0x18001ad80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad85  mov     rbx, [rsp+48h+arg_0]
0x18001ad8a  add     rsp, 40h
0x18001ad8e  pop     rdi
0x18001ad8f  retn
```

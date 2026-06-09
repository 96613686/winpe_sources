# wil_details_NtQueryWnfStateData

- ea: `0x18000bfcc`
- end: `0x18000c06d`
- name: `wil_details_NtQueryWnfStateData`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009018`
- `0x18000ba5c`

## callees

- `0x18000bfcc`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c018`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c018`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bffb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bffb`

## string_xrefs

- `0x18000bff4`: `ntdll.dll`

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
0x18000bfcc  mov     [rsp+arg_0], rbx
0x18000bfd1  push    rdi
0x18000bfd2  sub     rsp, 40h
0x18000bfd6  mov     r10, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000bfdd  mov     rbx, r9
0x18000bfe0  mov     rdi, rcx
0x18000bfe3  test    r10, r10
0x18000bfe6  jnz     short loc_18000C03A
0x18000bfe8  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bfef  test    rax, rax
0x18000bff2  jnz     short loc_18000C00E
0x18000bff4  lea     rcx, ModuleName; "ntdll.dll"
0x18000bffb  call    cs:__imp_GetModuleHandleW
0x18000c002  nop     dword ptr [rax+rax+00h]
0x18000c007  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c00e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000c015  mov     rcx, rax; hModule
0x18000c018  call    cs:__imp_GetProcAddress
0x18000c01f  nop     dword ptr [rax+rax+00h]
0x18000c024  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000c02b  mov     r10, rax
0x18000c02e  test    rax, rax
0x18000c031  jnz     short loc_18000C03A
0x18000c033  mov     eax, 0C0000139h
0x18000c038  jmp     short loc_18000C061
0x18000c03a  mov     rax, [rsp+48h+arg_28]
0x18000c03f  mov     r9, rbx
0x18000c042  mov     [rsp+48h+var_20], rax
0x18000c047  xor     r8d, r8d
0x18000c04a  mov     rax, [rsp+48h+arg_20]
0x18000c04f  xor     edx, edx
0x18000c051  mov     [rsp+48h+var_28], rax
0x18000c056  mov     rcx, rdi
0x18000c059  mov     rax, r10
0x18000c05c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c061  mov     rbx, [rsp+48h+arg_0]
0x18000c066  add     rsp, 40h
0x18000c06a  pop     rdi
0x18000c06b  retn
```

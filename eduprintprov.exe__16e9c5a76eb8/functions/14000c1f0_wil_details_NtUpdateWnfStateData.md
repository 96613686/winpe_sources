# wil_details_NtUpdateWnfStateData

- ea: `0x14000c1f0`
- end: `0x14000c29a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x14000905c`
- `0x14000bd38`

## callees

- `0x14000c1f0`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000c227`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000c227`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000c23e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000c23e`

## string_xrefs

- `0x14000c220`: `ntdll.dll`
- `0x14000c234`: `NtUpdateWnfStateData`

## pseudocode

```c
__int64 __fastcall wil_details_NtUpdateWnfStateData(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        int a6,
        int a7)
{
  __int64 (__fastcall *v7)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int); // r10
  HMODULE ModuleHandleW; // rax

  v7 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int))g_wil_details_pfnNtUpdateWnfStateData;
  if ( g_wil_details_pfnNtUpdateWnfStateData )
    return v7(a1, a2, a3, 0, 0, a6, a7);
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  g_wil_details_pfnNtUpdateWnfStateData = (__int64)GetProcAddress(ModuleHandleW, "NtUpdateWnfStateData");
  v7 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int))g_wil_details_pfnNtUpdateWnfStateData;
  if ( g_wil_details_pfnNtUpdateWnfStateData )
    return v7(a1, a2, a3, 0, 0, a6, a7);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x14000c1f0  mov     [rsp+arg_0], rbx
0x14000c1f5  mov     [rsp+arg_8], rsi
0x14000c1fa  push    rdi
0x14000c1fb  sub     rsp, 40h
0x14000c1ff  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14000c206  mov     ebx, r8d
0x14000c209  mov     rdi, rdx
0x14000c20c  mov     rsi, rcx
0x14000c20f  test    r10, r10
0x14000c212  jnz     short loc_14000C25A
0x14000c214  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c21b  test    rax, rax
0x14000c21e  jnz     short loc_14000C234
0x14000c220  lea     rcx, ModuleName; "ntdll.dll"
0x14000c227  call    cs:__imp_GetModuleHandleW
0x14000c22d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c234  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14000c23b  mov     rcx, rax; hModule
0x14000c23e  call    cs:__imp_GetProcAddress
0x14000c244  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14000c24b  mov     r10, rax
0x14000c24e  test    rax, rax
0x14000c251  jnz     short loc_14000C25A
0x14000c253  mov     eax, 0C0000139h
0x14000c258  jmp     short loc_14000C28A
0x14000c25a  mov     eax, [rsp+48h+arg_30]
0x14000c261  xor     r9d, r9d
0x14000c264  mov     [rsp+48h+var_18], eax
0x14000c268  mov     r8d, ebx
0x14000c26b  mov     eax, [rsp+48h+arg_28]
0x14000c26f  mov     rdx, rdi
0x14000c272  mov     [rsp+48h+var_20], eax
0x14000c276  mov     rcx, rsi
0x14000c279  mov     rax, r10
0x14000c27c  mov     [rsp+48h+var_28], 0
0x14000c285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c28a  mov     rbx, [rsp+48h+arg_0]
0x14000c28f  mov     rsi, [rsp+48h+arg_8]
0x14000c294  add     rsp, 40h
0x14000c298  pop     rdi
0x14000c299  retn
```

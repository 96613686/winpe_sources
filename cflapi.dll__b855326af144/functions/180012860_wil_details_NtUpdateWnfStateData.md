# wil_details_NtUpdateWnfStateData

- ea: `0x180012860`
- end: `0x18001290a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000bbf8`
- `0x18000fd6c`

## callees

- `0x180012860`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012897`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012897`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800128ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800128ae`

## string_xrefs

- `0x180012890`: `ntdll.dll`
- `0x1800128a4`: `NtUpdateWnfStateData`

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
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x180012860  mov     [rsp+arg_0], rbx
0x180012865  mov     [rsp+arg_8], rsi
0x18001286a  push    rdi
0x18001286b  sub     rsp, 40h
0x18001286f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180012876  mov     ebx, r8d
0x180012879  mov     rdi, rdx
0x18001287c  mov     rsi, rcx
0x18001287f  test    r10, r10
0x180012882  jnz     short loc_1800128CA
0x180012884  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001288b  test    rax, rax
0x18001288e  jnz     short loc_1800128A4
0x180012890  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180012897  call    cs:__imp_GetModuleHandleW
0x18001289d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800128a4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1800128ab  mov     rcx, rax; hModule
0x1800128ae  call    cs:__imp_GetProcAddress
0x1800128b4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800128bb  mov     r10, rax
0x1800128be  test    rax, rax
0x1800128c1  jnz     short loc_1800128CA
0x1800128c3  mov     eax, 0C0000139h
0x1800128c8  jmp     short loc_1800128FA
0x1800128ca  mov     eax, [rsp+48h+arg_30]
0x1800128d1  xor     r9d, r9d
0x1800128d4  mov     [rsp+48h+var_18], eax
0x1800128d8  mov     r8d, ebx
0x1800128db  mov     eax, [rsp+48h+arg_28]
0x1800128df  mov     rdx, rdi
0x1800128e2  mov     [rsp+48h+var_20], eax
0x1800128e6  mov     rcx, rsi
0x1800128e9  mov     rax, r10
0x1800128ec  mov     [rsp+48h+var_28], 0
0x1800128f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128fa  mov     rbx, [rsp+48h+arg_0]
0x1800128ff  mov     rsi, [rsp+48h+arg_8]
0x180012904  add     rsp, 40h
0x180012908  pop     rdi
0x180012909  retn
```

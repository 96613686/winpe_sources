# wil_details_NtUpdateWnfStateData

- ea: `0x180009490`
- end: `0x18000953a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180007418`
- `0x180008de4`

## callees

- `0x180009490`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800094c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800094c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800094de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800094de`

## string_xrefs

- `0x1800094c0`: `ntdll.dll`
- `0x1800094d4`: `NtUpdateWnfStateData`

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
0x180009490  mov     [rsp+arg_0], rbx
0x180009495  mov     [rsp+arg_8], rsi
0x18000949a  push    rdi
0x18000949b  sub     rsp, 40h
0x18000949f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1800094a6  mov     ebx, r8d
0x1800094a9  mov     rdi, rdx
0x1800094ac  mov     rsi, rcx
0x1800094af  test    r10, r10
0x1800094b2  jnz     short loc_1800094FA
0x1800094b4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800094bb  test    rax, rax
0x1800094be  jnz     short loc_1800094D4
0x1800094c0  lea     rcx, ModuleName; "ntdll.dll"
0x1800094c7  call    cs:__imp_GetModuleHandleW
0x1800094cd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800094d4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1800094db  mov     rcx, rax; hModule
0x1800094de  call    cs:__imp_GetProcAddress
0x1800094e4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800094eb  mov     r10, rax
0x1800094ee  test    rax, rax
0x1800094f1  jnz     short loc_1800094FA
0x1800094f3  mov     eax, 0C0000139h
0x1800094f8  jmp     short loc_18000952A
0x1800094fa  mov     eax, [rsp+48h+arg_30]
0x180009501  xor     r9d, r9d
0x180009504  mov     [rsp+48h+var_18], eax
0x180009508  mov     r8d, ebx
0x18000950b  mov     eax, [rsp+48h+arg_28]
0x18000950f  mov     rdx, rdi
0x180009512  mov     [rsp+48h+var_20], eax
0x180009516  mov     rcx, rsi
0x180009519  mov     rax, r10
0x18000951c  mov     [rsp+48h+var_28], 0
0x180009525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000952a  mov     rbx, [rsp+48h+arg_0]
0x18000952f  mov     rsi, [rsp+48h+arg_8]
0x180009534  add     rsp, 40h
0x180009538  pop     rdi
0x180009539  retn
```

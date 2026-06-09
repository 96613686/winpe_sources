# wil_details_NtUpdateWnfStateData

- ea: `0x18000d734`
- end: `0x18000d7de`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000b500`
- `0x18000d210`

## callees

- `0x18000d734`
- `0x180017010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000d76b`
- `KERNEL32!GetModuleHandleW` at `0x18000d76b`
- `KERNEL32!GetProcAddress` at `0x18000d782`
- `KERNEL32!GetProcAddress` at `0x18000d782`

## string_xrefs

- `0x18000d764`: `ntdll.dll`
- `0x18000d778`: `NtUpdateWnfStateData`

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
0x18000d734  mov     [rsp+arg_0], rbx
0x18000d739  mov     [rsp+arg_8], rsi
0x18000d73e  push    rdi
0x18000d73f  sub     rsp, 40h
0x18000d743  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000d74a  mov     ebx, r8d
0x18000d74d  mov     rdi, rdx
0x18000d750  mov     rsi, rcx
0x18000d753  test    r10, r10
0x18000d756  jnz     short loc_18000D79E
0x18000d758  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d75f  test    rax, rax
0x18000d762  jnz     short loc_18000D778
0x18000d764  lea     rcx, aNtdllDll; "ntdll.dll"
0x18000d76b  call    cs:__imp_GetModuleHandleW
0x18000d771  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d778  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000d77f  mov     rcx, rax; hModule
0x18000d782  call    cs:__imp_GetProcAddress
0x18000d788  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000d78f  mov     r10, rax
0x18000d792  test    rax, rax
0x18000d795  jnz     short loc_18000D79E
0x18000d797  mov     eax, 0C0000139h
0x18000d79c  jmp     short loc_18000D7CE
0x18000d79e  mov     eax, [rsp+48h+arg_30]
0x18000d7a5  xor     r9d, r9d
0x18000d7a8  mov     [rsp+48h+var_18], eax
0x18000d7ac  mov     r8d, ebx
0x18000d7af  mov     eax, [rsp+48h+arg_28]
0x18000d7b3  mov     rdx, rdi
0x18000d7b6  mov     [rsp+48h+var_20], eax
0x18000d7ba  mov     rcx, rsi
0x18000d7bd  mov     rax, r10
0x18000d7c0  mov     [rsp+48h+var_28], 0
0x18000d7c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7ce  mov     rbx, [rsp+48h+arg_0]
0x18000d7d3  mov     rsi, [rsp+48h+arg_8]
0x18000d7d8  add     rsp, 40h
0x18000d7dc  pop     rdi
0x18000d7dd  retn
```

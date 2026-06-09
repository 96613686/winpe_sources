# wil_details_NtUpdateWnfStateData

- ea: `0x18000ae90`
- end: `0x18000af3a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000830c`
- `0x18000a9c8`

## callees

- `0x18000ae90`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aede`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aede`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000aec7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000aec7`

## string_xrefs

- `0x18000aec0`: `ntdll.dll`
- `0x18000aed4`: `NtUpdateWnfStateData`

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
0x18000ae90  mov     [rsp+arg_0], rbx
0x18000ae95  mov     [rsp+arg_8], rsi
0x18000ae9a  push    rdi
0x18000ae9b  sub     rsp, 40h
0x18000ae9f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000aea6  mov     ebx, r8d
0x18000aea9  mov     rdi, rdx
0x18000aeac  mov     rsi, rcx
0x18000aeaf  test    r10, r10
0x18000aeb2  jnz     short loc_18000AEFA
0x18000aeb4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000aebb  test    rax, rax
0x18000aebe  jnz     short loc_18000AED4
0x18000aec0  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18000aec7  call    cs:__imp_GetModuleHandleW
0x18000aecd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000aed4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000aedb  mov     rcx, rax; hModule
0x18000aede  call    cs:__imp_GetProcAddress
0x18000aee4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000aeeb  mov     r10, rax
0x18000aeee  test    rax, rax
0x18000aef1  jnz     short loc_18000AEFA
0x18000aef3  mov     eax, 0C0000139h
0x18000aef8  jmp     short loc_18000AF2A
0x18000aefa  mov     eax, [rsp+48h+arg_30]
0x18000af01  xor     r9d, r9d
0x18000af04  mov     [rsp+48h+var_18], eax
0x18000af08  mov     r8d, ebx
0x18000af0b  mov     eax, [rsp+48h+arg_28]
0x18000af0f  mov     rdx, rdi
0x18000af12  mov     [rsp+48h+var_20], eax
0x18000af16  mov     rcx, rsi
0x18000af19  mov     rax, r10
0x18000af1c  mov     [rsp+48h+var_28], 0
0x18000af25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af2a  mov     rbx, [rsp+48h+arg_0]
0x18000af2f  mov     rsi, [rsp+48h+arg_8]
0x18000af34  add     rsp, 40h
0x18000af38  pop     rdi
0x18000af39  retn
```

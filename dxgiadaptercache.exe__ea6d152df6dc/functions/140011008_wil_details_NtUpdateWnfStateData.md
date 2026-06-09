# wil_details_NtUpdateWnfStateData

- ea: `0x140011008`
- end: `0x1400110b2`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x14000badc`
- `0x140010d38`

## callees

- `0x140011008`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140011056`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140011056`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001103f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001103f`

## string_xrefs

- `0x140011038`: `ntdll.dll`
- `0x14001104c`: `NtUpdateWnfStateData`

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
0x140011008  mov     [rsp+arg_0], rbx
0x14001100d  mov     [rsp+arg_8], rsi
0x140011012  push    rdi
0x140011013  sub     rsp, 40h
0x140011017  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14001101e  mov     ebx, r8d
0x140011021  mov     rdi, rdx
0x140011024  mov     rsi, rcx
0x140011027  test    r10, r10
0x14001102a  jnz     short loc_140011072
0x14001102c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140011033  test    rax, rax
0x140011036  jnz     short loc_14001104C
0x140011038  lea     rcx, ModuleName; "ntdll.dll"
0x14001103f  call    cs:__imp_GetModuleHandleW
0x140011045  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14001104c  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x140011053  mov     rcx, rax; hModule
0x140011056  call    cs:__imp_GetProcAddress
0x14001105c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x140011063  mov     r10, rax
0x140011066  test    rax, rax
0x140011069  jnz     short loc_140011072
0x14001106b  mov     eax, 0C0000139h
0x140011070  jmp     short loc_1400110A2
0x140011072  mov     eax, [rsp+48h+arg_30]
0x140011079  xor     r9d, r9d
0x14001107c  mov     [rsp+48h+var_18], eax
0x140011080  mov     r8d, ebx
0x140011083  mov     eax, [rsp+48h+arg_28]
0x140011087  mov     rdx, rdi
0x14001108a  mov     [rsp+48h+var_20], eax
0x14001108e  mov     rcx, rsi
0x140011091  mov     rax, r10
0x140011094  mov     [rsp+48h+var_28], 0
0x14001109d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400110a2  mov     rbx, [rsp+48h+arg_0]
0x1400110a7  mov     rsi, [rsp+48h+arg_8]
0x1400110ac  add     rsp, 40h
0x1400110b0  pop     rdi
0x1400110b1  retn
```

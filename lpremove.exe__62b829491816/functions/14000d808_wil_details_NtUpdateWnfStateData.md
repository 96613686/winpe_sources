# wil_details_NtUpdateWnfStateData

- ea: `0x14000d808`
- end: `0x14000d8b2`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x140009dac`
- `0x14000d368`

## callees

- `0x14000d808`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000d83f`
- `KERNEL32!GetModuleHandleW` at `0x14000d83f`
- `KERNEL32!GetProcAddress` at `0x14000d856`
- `KERNEL32!GetProcAddress` at `0x14000d856`

## string_xrefs

- `0x14000d838`: `ntdll.dll`
- `0x14000d84c`: `NtUpdateWnfStateData`

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
0x14000d808  mov     [rsp+arg_0], rbx
0x14000d80d  mov     [rsp+arg_8], rsi
0x14000d812  push    rdi
0x14000d813  sub     rsp, 40h
0x14000d817  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14000d81e  mov     ebx, r8d
0x14000d821  mov     rdi, rdx
0x14000d824  mov     rsi, rcx
0x14000d827  test    r10, r10
0x14000d82a  jnz     short loc_14000D872
0x14000d82c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000d833  test    rax, rax
0x14000d836  jnz     short loc_14000D84C
0x14000d838  lea     rcx, ModuleName; "ntdll.dll"
0x14000d83f  call    cs:__imp_GetModuleHandleW
0x14000d845  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000d84c  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14000d853  mov     rcx, rax; hModule
0x14000d856  call    cs:__imp_GetProcAddress
0x14000d85c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14000d863  mov     r10, rax
0x14000d866  test    rax, rax
0x14000d869  jnz     short loc_14000D872
0x14000d86b  mov     eax, 0C0000139h
0x14000d870  jmp     short loc_14000D8A2
0x14000d872  mov     eax, [rsp+48h+arg_30]
0x14000d879  xor     r9d, r9d
0x14000d87c  mov     [rsp+48h+var_18], eax
0x14000d880  mov     r8d, ebx
0x14000d883  mov     eax, [rsp+48h+arg_28]
0x14000d887  mov     rdx, rdi
0x14000d88a  mov     [rsp+48h+var_20], eax
0x14000d88e  mov     rcx, rsi
0x14000d891  mov     rax, r10
0x14000d894  mov     [rsp+48h+var_28], 0
0x14000d89d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d8a2  mov     rbx, [rsp+48h+arg_0]
0x14000d8a7  mov     rsi, [rsp+48h+arg_8]
0x14000d8ac  add     rsp, 40h
0x14000d8b0  pop     rdi
0x14000d8b1  retn
```

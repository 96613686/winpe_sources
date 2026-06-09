# wil_details_NtUpdateWnfStateData

- ea: `0x180011b60`
- end: `0x180011c0a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800107dc`
- `0x18001172c`

## callees

- `0x180011b60`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011bae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011bae`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011b97`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011b97`

## string_xrefs

- `0x180011b90`: `ntdll.dll`
- `0x180011ba4`: `NtUpdateWnfStateData`

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
0x180011b60  mov     [rsp+arg_0], rbx
0x180011b65  mov     [rsp+arg_8], rsi
0x180011b6a  push    rdi
0x180011b6b  sub     rsp, 40h
0x180011b6f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180011b76  mov     ebx, r8d
0x180011b79  mov     rdi, rdx
0x180011b7c  mov     rsi, rcx
0x180011b7f  test    r10, r10
0x180011b82  jnz     short loc_180011BCA
0x180011b84  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011b8b  test    rax, rax
0x180011b8e  jnz     short loc_180011BA4
0x180011b90  lea     rcx, ModuleName; "ntdll.dll"
0x180011b97  call    cs:__imp_GetModuleHandleW
0x180011b9d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011ba4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180011bab  mov     rcx, rax; hModule
0x180011bae  call    cs:__imp_GetProcAddress
0x180011bb4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180011bbb  mov     r10, rax
0x180011bbe  test    rax, rax
0x180011bc1  jnz     short loc_180011BCA
0x180011bc3  mov     eax, 0C0000139h
0x180011bc8  jmp     short loc_180011BFA
0x180011bca  mov     eax, [rsp+48h+arg_30]
0x180011bd1  xor     r9d, r9d
0x180011bd4  mov     [rsp+48h+var_18], eax
0x180011bd8  mov     r8d, ebx
0x180011bdb  mov     eax, [rsp+48h+arg_28]
0x180011bdf  mov     rdx, rdi
0x180011be2  mov     [rsp+48h+var_20], eax
0x180011be6  mov     rcx, rsi
0x180011be9  mov     rax, r10
0x180011bec  mov     [rsp+48h+var_28], 0
0x180011bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bfa  mov     rbx, [rsp+48h+arg_0]
0x180011bff  mov     rsi, [rsp+48h+arg_8]
0x180011c04  add     rsp, 40h
0x180011c08  pop     rdi
0x180011c09  retn
```

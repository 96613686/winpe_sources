# wil_details_NtUpdateWnfStateData

- ea: `0x180008460`
- end: `0x18000850a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800063d0`
- `0x180008220`

## callees

- `0x180008460`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800084ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800084ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008497`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008497`

## string_xrefs

- `0x180008490`: `ntdll.dll`
- `0x1800084a4`: `NtUpdateWnfStateData`

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
0x180008460  mov     [rsp+arg_0], rbx
0x180008465  mov     [rsp+arg_8], rsi
0x18000846a  push    rdi
0x18000846b  sub     rsp, 40h
0x18000846f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180008476  mov     ebx, r8d
0x180008479  mov     rdi, rdx
0x18000847c  mov     rsi, rcx
0x18000847f  test    r10, r10
0x180008482  jnz     short loc_1800084CA
0x180008484  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000848b  test    rax, rax
0x18000848e  jnz     short loc_1800084A4
0x180008490  lea     rcx, ModuleName; "ntdll.dll"
0x180008497  call    cs:__imp_GetModuleHandleW
0x18000849d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800084a4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1800084ab  mov     rcx, rax; hModule
0x1800084ae  call    cs:__imp_GetProcAddress
0x1800084b4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800084bb  mov     r10, rax
0x1800084be  test    rax, rax
0x1800084c1  jnz     short loc_1800084CA
0x1800084c3  mov     eax, 0C0000139h
0x1800084c8  jmp     short loc_1800084FA
0x1800084ca  mov     eax, [rsp+48h+arg_30]
0x1800084d1  xor     r9d, r9d
0x1800084d4  mov     [rsp+48h+var_18], eax
0x1800084d8  mov     r8d, ebx
0x1800084db  mov     eax, [rsp+48h+arg_28]
0x1800084df  mov     rdx, rdi
0x1800084e2  mov     [rsp+48h+var_20], eax
0x1800084e6  mov     rcx, rsi
0x1800084e9  mov     rax, r10
0x1800084ec  mov     [rsp+48h+var_28], 0
0x1800084f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084fa  mov     rbx, [rsp+48h+arg_0]
0x1800084ff  mov     rsi, [rsp+48h+arg_8]
0x180008504  add     rsp, 40h
0x180008508  pop     rdi
0x180008509  retn
```

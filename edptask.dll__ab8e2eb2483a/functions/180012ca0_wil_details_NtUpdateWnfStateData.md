# wil_details_NtUpdateWnfStateData

- ea: `0x180012ca0`
- end: `0x180012d4a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000fdb0`
- `0x180012588`

## callees

- `0x180012ca0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012cd7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012cd7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012cee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012cee`

## string_xrefs

- `0x180012cd0`: `ntdll.dll`
- `0x180012ce4`: `NtUpdateWnfStateData`

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
0x180012ca0  mov     [rsp+arg_0], rbx
0x180012ca5  mov     [rsp+arg_8], rsi
0x180012caa  push    rdi
0x180012cab  sub     rsp, 40h
0x180012caf  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180012cb6  mov     ebx, r8d
0x180012cb9  mov     rdi, rdx
0x180012cbc  mov     rsi, rcx
0x180012cbf  test    r10, r10
0x180012cc2  jnz     short loc_180012D0A
0x180012cc4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180012ccb  test    rax, rax
0x180012cce  jnz     short loc_180012CE4
0x180012cd0  lea     rcx, ModuleName; "ntdll.dll"
0x180012cd7  call    cs:__imp_GetModuleHandleW
0x180012cdd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180012ce4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180012ceb  mov     rcx, rax; hModule
0x180012cee  call    cs:__imp_GetProcAddress
0x180012cf4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180012cfb  mov     r10, rax
0x180012cfe  test    rax, rax
0x180012d01  jnz     short loc_180012D0A
0x180012d03  mov     eax, 0C0000139h
0x180012d08  jmp     short loc_180012D3A
0x180012d0a  mov     eax, [rsp+48h+arg_30]
0x180012d11  xor     r9d, r9d
0x180012d14  mov     [rsp+48h+var_18], eax
0x180012d18  mov     r8d, ebx
0x180012d1b  mov     eax, [rsp+48h+arg_28]
0x180012d1f  mov     rdx, rdi
0x180012d22  mov     [rsp+48h+var_20], eax
0x180012d26  mov     rcx, rsi
0x180012d29  mov     rax, r10
0x180012d2c  mov     [rsp+48h+var_28], 0
0x180012d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d3a  mov     rbx, [rsp+48h+arg_0]
0x180012d3f  mov     rsi, [rsp+48h+arg_8]
0x180012d44  add     rsp, 40h
0x180012d48  pop     rdi
0x180012d49  retn
```

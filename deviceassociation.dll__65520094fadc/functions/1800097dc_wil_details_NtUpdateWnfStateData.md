# wil_details_NtUpdateWnfStateData

- ea: `0x1800097dc`
- end: `0x180009886`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180006de8`
- `0x1800085a8`

## callees

- `0x1800097dc`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000982a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000982a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009813`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009813`

## string_xrefs

- `0x18000980c`: `ntdll.dll`
- `0x180009820`: `NtUpdateWnfStateData`

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
0x1800097dc  mov     [rsp+arg_0], rbx
0x1800097e1  mov     [rsp+arg_8], rsi
0x1800097e6  push    rdi
0x1800097e7  sub     rsp, 40h
0x1800097eb  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1800097f2  mov     ebx, r8d
0x1800097f5  mov     rdi, rdx
0x1800097f8  mov     rsi, rcx
0x1800097fb  test    r10, r10
0x1800097fe  jnz     short loc_180009846
0x180009800  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009807  test    rax, rax
0x18000980a  jnz     short loc_180009820
0x18000980c  lea     rcx, ModuleName; "ntdll.dll"
0x180009813  call    cs:__imp_GetModuleHandleW
0x180009819  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009820  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180009827  mov     rcx, rax; hModule
0x18000982a  call    cs:__imp_GetProcAddress
0x180009830  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180009837  mov     r10, rax
0x18000983a  test    rax, rax
0x18000983d  jnz     short loc_180009846
0x18000983f  mov     eax, 0C0000139h
0x180009844  jmp     short loc_180009876
0x180009846  mov     eax, [rsp+48h+arg_30]
0x18000984d  xor     r9d, r9d
0x180009850  mov     [rsp+48h+var_18], eax
0x180009854  mov     r8d, ebx
0x180009857  mov     eax, [rsp+48h+arg_28]
0x18000985b  mov     rdx, rdi
0x18000985e  mov     [rsp+48h+var_20], eax
0x180009862  mov     rcx, rsi
0x180009865  mov     rax, r10
0x180009868  mov     [rsp+48h+var_28], 0
0x180009871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009876  mov     rbx, [rsp+48h+arg_0]
0x18000987b  mov     rsi, [rsp+48h+arg_8]
0x180009880  add     rsp, 40h
0x180009884  pop     rdi
0x180009885  retn
```

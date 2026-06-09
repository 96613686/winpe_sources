# wil_details_NtUpdateWnfStateData

- ea: `0x18000adf0`
- end: `0x18000ae9a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180008518`
- `0x18000a648`

## callees

- `0x18000adf0`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ae27`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ae27`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ae3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ae3e`

## string_xrefs

- `0x18000ae20`: `ntdll.dll`
- `0x18000ae34`: `NtUpdateWnfStateData`

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
0x18000adf0  mov     [rsp+arg_0], rbx
0x18000adf5  mov     [rsp+arg_8], rsi
0x18000adfa  push    rdi
0x18000adfb  sub     rsp, 40h
0x18000adff  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000ae06  mov     ebx, r8d
0x18000ae09  mov     rdi, rdx
0x18000ae0c  mov     rsi, rcx
0x18000ae0f  test    r10, r10
0x18000ae12  jnz     short loc_18000AE5A
0x18000ae14  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ae1b  test    rax, rax
0x18000ae1e  jnz     short loc_18000AE34
0x18000ae20  lea     rcx, ModuleName; "ntdll.dll"
0x18000ae27  call    cs:__imp_GetModuleHandleW
0x18000ae2d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ae34  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000ae3b  mov     rcx, rax; hModule
0x18000ae3e  call    cs:__imp_GetProcAddress
0x18000ae44  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000ae4b  mov     r10, rax
0x18000ae4e  test    rax, rax
0x18000ae51  jnz     short loc_18000AE5A
0x18000ae53  mov     eax, 0C0000139h
0x18000ae58  jmp     short loc_18000AE8A
0x18000ae5a  mov     eax, [rsp+48h+arg_30]
0x18000ae61  xor     r9d, r9d
0x18000ae64  mov     [rsp+48h+var_18], eax
0x18000ae68  mov     r8d, ebx
0x18000ae6b  mov     eax, [rsp+48h+arg_28]
0x18000ae6f  mov     rdx, rdi
0x18000ae72  mov     [rsp+48h+var_20], eax
0x18000ae76  mov     rcx, rsi
0x18000ae79  mov     rax, r10
0x18000ae7c  mov     [rsp+48h+var_28], 0
0x18000ae85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae8a  mov     rbx, [rsp+48h+arg_0]
0x18000ae8f  mov     rsi, [rsp+48h+arg_8]
0x18000ae94  add     rsp, 40h
0x18000ae98  pop     rdi
0x18000ae99  retn
```

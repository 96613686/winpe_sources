# wil_details_NtUpdateWnfStateData

- ea: `0x18000834c`
- end: `0x180008403`
- name: `wil_details_NtUpdateWnfStateData`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000658c`
- `0x1800080bc`

## callees

- `0x18000834c`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800083a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800083a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008383`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008383`

## string_xrefs

- `0x18000837c`: `ntdll.dll`
- `0x180008396`: `NtUpdateWnfStateData`

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
0x18000834c  mov     [rsp+arg_0], rbx
0x180008351  mov     [rsp+arg_8], rsi
0x180008356  push    rdi
0x180008357  sub     rsp, 40h
0x18000835b  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180008362  mov     ebx, r8d
0x180008365  mov     rdi, rdx
0x180008368  mov     rsi, rcx
0x18000836b  test    r10, r10
0x18000836e  jnz     short loc_1800083C2
0x180008370  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008377  test    rax, rax
0x18000837a  jnz     short loc_180008396
0x18000837c  lea     rcx, ModuleName; "ntdll.dll"
0x180008383  call    cs:__imp_GetModuleHandleW
0x18000838a  nop     dword ptr [rax+rax+00h]
0x18000838f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008396  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000839d  mov     rcx, rax; hModule
0x1800083a0  call    cs:__imp_GetProcAddress
0x1800083a7  nop     dword ptr [rax+rax+00h]
0x1800083ac  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800083b3  mov     r10, rax
0x1800083b6  test    rax, rax
0x1800083b9  jnz     short loc_1800083C2
0x1800083bb  mov     eax, 0C0000139h
0x1800083c0  jmp     short loc_1800083F2
0x1800083c2  mov     eax, [rsp+48h+arg_30]
0x1800083c9  xor     r9d, r9d
0x1800083cc  mov     [rsp+48h+var_18], eax
0x1800083d0  mov     r8d, ebx
0x1800083d3  mov     eax, [rsp+48h+arg_28]
0x1800083d7  mov     rdx, rdi
0x1800083da  mov     [rsp+48h+var_20], eax
0x1800083de  mov     rcx, rsi
0x1800083e1  mov     rax, r10
0x1800083e4  mov     [rsp+48h+var_28], 0
0x1800083ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083f2  mov     rbx, [rsp+48h+arg_0]
0x1800083f7  mov     rsi, [rsp+48h+arg_8]
0x1800083fc  add     rsp, 40h
0x180008400  pop     rdi
0x180008401  retn
```

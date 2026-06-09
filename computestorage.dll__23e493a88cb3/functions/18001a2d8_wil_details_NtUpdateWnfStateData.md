# wil_details_NtUpdateWnfStateData

- ea: `0x18001a2d8`
- end: `0x18001a38f`
- name: `wil_details_NtUpdateWnfStateData`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180018548`
- `0x180019f9c`

## callees

- `0x18001a2d8`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001a30f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001a30f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a32c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a32c`

## string_xrefs

- `0x18001a308`: `ntdll.dll`
- `0x18001a322`: `NtUpdateWnfStateData`

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
0x18001a2d8  mov     [rsp+arg_0], rbx
0x18001a2dd  mov     [rsp+arg_8], rsi
0x18001a2e2  push    rdi
0x18001a2e3  sub     rsp, 40h
0x18001a2e7  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18001a2ee  mov     ebx, r8d
0x18001a2f1  mov     rdi, rdx
0x18001a2f4  mov     rsi, rcx
0x18001a2f7  test    r10, r10
0x18001a2fa  jnz     short loc_18001A34E
0x18001a2fc  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001a303  test    rax, rax
0x18001a306  jnz     short loc_18001A322
0x18001a308  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18001a30f  call    cs:__imp_GetModuleHandleW
0x18001a316  nop     dword ptr [rax+rax+00h]
0x18001a31b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001a322  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001a329  mov     rcx, rax; hModule
0x18001a32c  call    cs:__imp_GetProcAddress
0x18001a333  nop     dword ptr [rax+rax+00h]
0x18001a338  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001a33f  mov     r10, rax
0x18001a342  test    rax, rax
0x18001a345  jnz     short loc_18001A34E
0x18001a347  mov     eax, 0C0000139h
0x18001a34c  jmp     short loc_18001A37E
0x18001a34e  mov     eax, [rsp+48h+arg_30]
0x18001a355  xor     r9d, r9d
0x18001a358  mov     [rsp+48h+var_18], eax
0x18001a35c  mov     r8d, ebx
0x18001a35f  mov     eax, [rsp+48h+arg_28]
0x18001a363  mov     rdx, rdi
0x18001a366  mov     [rsp+48h+var_20], eax
0x18001a36a  mov     rcx, rsi
0x18001a36d  mov     rax, r10
0x18001a370  mov     [rsp+48h+var_28], 0
0x18001a379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a37e  mov     rbx, [rsp+48h+arg_0]
0x18001a383  mov     rsi, [rsp+48h+arg_8]
0x18001a388  add     rsp, 40h
0x18001a38c  pop     rdi
0x18001a38d  retn
```

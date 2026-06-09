# wil_details_NtUpdateWnfStateData(x,x,x,x,x,x,x)

- ea: `0x1000a130`
- end: `0x1000a1a3`
- name: `_wil_details_NtUpdateWnfStateData@28`
- size: `115`
- prototype: `int __fastcall(void *, unsigned int, int, int, int, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1000be30`

## callees

- `0x1000a130`
- `0x1000eb60`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1000a165`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1000a165`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1000a154`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1000a154`

## string_xrefs

- `0x1000a14f`: `ntdll.dll`
- `0x1000a15f`: `NtUpdateWnfStateData`

## pseudocode

```c
int __fastcall wil_details_NtUpdateWnfStateData(void *a1, unsigned int a2, int a3, int a4, int a5, int a6, int a7)
{
  FARPROC NtUpdateWnfStateData; // esi
  HMODULE ModuleHandleW; // eax

  NtUpdateWnfStateData = (FARPROC)g_wil_details_pfnNtUpdateWnfStateData;
  if ( g_wil_details_pfnNtUpdateWnfStateData )
    return ((int (__thiscall *)(FARPROC, void *, unsigned int, int, _DWORD, _DWORD, int, int))NtUpdateWnfStateData)(
             NtUpdateWnfStateData,
             a1,
             a2,
             a3,
             0,
             0,
             a6,
             a7);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  NtUpdateWnfStateData = GetProcAddress(ModuleHandleW, "NtUpdateWnfStateData");
  g_wil_details_pfnNtUpdateWnfStateData = (int)NtUpdateWnfStateData;
  if ( NtUpdateWnfStateData )
    return ((int (__thiscall *)(FARPROC, void *, unsigned int, int, _DWORD, _DWORD, int, int))NtUpdateWnfStateData)(
             NtUpdateWnfStateData,
             a1,
             a2,
             a3,
             0,
             0,
             a6,
             a7);
  else
    return -1073741511;
}

```

## disassembly

```asm
0x1000a130  mov     edi, edi
0x1000a132  push    ebp
0x1000a133  mov     ebp, esp
0x1000a135  push    ebx
0x1000a136  push    esi
0x1000a137  mov     esi, _g_wil_details_pfnNtUpdateWnfStateData
0x1000a13d  mov     ebx, ecx
0x1000a13f  push    edi
0x1000a140  mov     edi, edx
0x1000a142  test    esi, esi
0x1000a144  jnz     short loc_1000A183
0x1000a146  mov     eax, ?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YGPAUHINSTANCE__@@XZ@4PAU2@A; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1000a14b  test    eax, eax
0x1000a14d  jnz     short loc_1000A15F
0x1000a14f  push    offset ModuleName; "ntdll.dll"
0x1000a154  call    ds:__imp__GetModuleHandleW@4; GetModuleHandleW(x)
0x1000a15a  mov     ?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YGPAUHINSTANCE__@@XZ@4PAU2@A, eax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1000a15f  push    offset aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1000a164  push    eax; hModule
0x1000a165  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x1000a16b  mov     esi, eax
0x1000a16d  mov     _g_wil_details_pfnNtUpdateWnfStateData, esi
0x1000a173  test    esi, esi
0x1000a175  jnz     short loc_1000A183
0x1000a177  pop     edi
0x1000a178  pop     esi
0x1000a179  mov     eax, 0C0000139h
0x1000a17e  pop     ebx
0x1000a17f  pop     ebp
0x1000a180  retn    14h
0x1000a183  push    [ebp+arg_10]
0x1000a186  mov     ecx, esi
0x1000a188  push    [ebp+arg_C]
0x1000a18b  push    0
0x1000a18d  push    0
0x1000a18f  push    [ebp+arg_0]
0x1000a192  push    edi; unsigned int
0x1000a193  push    ebx; void *
0x1000a194  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000a19a  call    esi ; _g_wil_details_pfnNtUpdateWnfStateData
0x1000a19c  pop     edi
0x1000a19d  pop     esi
0x1000a19e  pop     ebx
0x1000a19f  pop     ebp
0x1000a1a0  retn    14h
```

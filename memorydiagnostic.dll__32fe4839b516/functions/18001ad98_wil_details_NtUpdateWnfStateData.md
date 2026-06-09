# wil_details_NtUpdateWnfStateData

- ea: `0x18001ad98`
- end: `0x18001ae4c`
- name: `wil_details_NtUpdateWnfStateData`
- size: `180`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800103c4`
- `0x180019f6c`

## callees

- `0x18001ad98`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001adcf`
- `KERNEL32!GetModuleHandleW` at `0x18001adcf`
- `KERNEL32!GetProcAddress` at `0x18001adec`
- `KERNEL32!GetProcAddress` at `0x18001adec`

## string_xrefs

- `0x18001adc8`: `ntdll.dll`
- `0x18001ade2`: `NtUpdateWnfStateData`

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
0x18001ad98  mov     [rsp+arg_0], rbx
0x18001ad9d  mov     [rsp+arg_8], rsi
0x18001ada2  push    rdi
0x18001ada3  sub     rsp, 40h
0x18001ada7  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18001adae  mov     ebx, r8d
0x18001adb1  mov     rdi, rdx
0x18001adb4  mov     rsi, rcx
0x18001adb7  test    r10, r10
0x18001adba  jnz     short loc_18001AE0E
0x18001adbc  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001adc3  test    rax, rax
0x18001adc6  jnz     short loc_18001ADE2
0x18001adc8  lea     rcx, ModuleName; "ntdll.dll"
0x18001adcf  call    cs:__imp_GetModuleHandleW
0x18001add6  nop     dword ptr [rax+rax+00h]
0x18001addb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001ade2  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001ade9  mov     rcx, rax; hModule
0x18001adec  call    cs:__imp_GetProcAddress
0x18001adf3  nop     dword ptr [rax+rax+00h]
0x18001adf8  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001adff  mov     r10, rax
0x18001ae02  test    rax, rax
0x18001ae05  jnz     short loc_18001AE0E
0x18001ae07  mov     eax, 0C0000139h
0x18001ae0c  jmp     short loc_18001AE3B
0x18001ae0e  mov     eax, [rsp+48h+arg_30]
0x18001ae15  xor     r9d, r9d
0x18001ae18  mov     [rsp+48h+var_18], eax
0x18001ae1c  mov     r8d, ebx
0x18001ae1f  mov     eax, [rsp+48h+arg_28]
0x18001ae23  mov     rdx, rdi
0x18001ae26  mov     [rsp+48h+var_20], eax
0x18001ae2a  mov     rcx, rsi
0x18001ae2d  and     [rsp+48h+var_28], 0
0x18001ae33  mov     rax, r10
0x18001ae36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae3b  mov     rbx, [rsp+48h+arg_0]
0x18001ae40  mov     rsi, [rsp+48h+arg_8]
0x18001ae45  add     rsp, 40h
0x18001ae49  pop     rdi
0x18001ae4a  retn
```

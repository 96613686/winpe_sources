# wil_details_NtUpdateWnfStateData

- ea: `0x1400089d8`
- end: `0x140008a82`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1400064cc`
- `0x140008708`

## callees

- `0x1400089d8`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008a0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008a0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008a26`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008a26`

## string_xrefs

- `0x140008a08`: `ntdll.dll`
- `0x140008a1c`: `NtUpdateWnfStateData`

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
0x1400089d8  mov     [rsp+arg_0], rbx
0x1400089dd  mov     [rsp+arg_8], rsi
0x1400089e2  push    rdi
0x1400089e3  sub     rsp, 40h
0x1400089e7  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1400089ee  mov     ebx, r8d
0x1400089f1  mov     rdi, rdx
0x1400089f4  mov     rsi, rcx
0x1400089f7  test    r10, r10
0x1400089fa  jnz     short loc_140008A42
0x1400089fc  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140008a03  test    rax, rax
0x140008a06  jnz     short loc_140008A1C
0x140008a08  lea     rcx, ModuleName; "ntdll.dll"
0x140008a0f  call    cs:__imp_GetModuleHandleW
0x140008a15  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140008a1c  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x140008a23  mov     rcx, rax; hModule
0x140008a26  call    cs:__imp_GetProcAddress
0x140008a2c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x140008a33  mov     r10, rax
0x140008a36  test    rax, rax
0x140008a39  jnz     short loc_140008A42
0x140008a3b  mov     eax, 0C0000139h
0x140008a40  jmp     short loc_140008A72
0x140008a42  mov     eax, [rsp+48h+arg_30]
0x140008a49  xor     r9d, r9d
0x140008a4c  mov     [rsp+48h+var_18], eax
0x140008a50  mov     r8d, ebx
0x140008a53  mov     eax, [rsp+48h+arg_28]
0x140008a57  mov     rdx, rdi
0x140008a5a  mov     [rsp+48h+var_20], eax
0x140008a5e  mov     rcx, rsi
0x140008a61  mov     rax, r10
0x140008a64  mov     [rsp+48h+var_28], 0
0x140008a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008a72  mov     rbx, [rsp+48h+arg_0]
0x140008a77  mov     rsi, [rsp+48h+arg_8]
0x140008a7c  add     rsp, 40h
0x140008a80  pop     rdi
0x140008a81  retn
```

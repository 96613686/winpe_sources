# wil_details_NtUpdateWnfStateData

- ea: `0x18000bcb0`
- end: `0x18000bd5a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180008558`
- `0x18000b540`

## callees

- `0x18000bcb0`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000bcfe`
- `KERNEL32!GetProcAddress` at `0x18000bcfe`
- `KERNEL32!GetModuleHandleW` at `0x18000bce7`
- `KERNEL32!GetModuleHandleW` at `0x18000bce7`

## string_xrefs

- `0x18000bce0`: `ntdll.dll`
- `0x18000bcf4`: `NtUpdateWnfStateData`

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
0x18000bcb0  mov     [rsp+arg_0], rbx
0x18000bcb5  mov     [rsp+arg_8], rsi
0x18000bcba  push    rdi
0x18000bcbb  sub     rsp, 40h
0x18000bcbf  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000bcc6  mov     ebx, r8d
0x18000bcc9  mov     rdi, rdx
0x18000bccc  mov     rsi, rcx
0x18000bccf  test    r10, r10
0x18000bcd2  jnz     short loc_18000BD1A
0x18000bcd4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bcdb  test    rax, rax
0x18000bcde  jnz     short loc_18000BCF4
0x18000bce0  lea     rcx, ModuleName; "ntdll.dll"
0x18000bce7  call    cs:__imp_GetModuleHandleW
0x18000bced  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bcf4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000bcfb  mov     rcx, rax; hModule
0x18000bcfe  call    cs:__imp_GetProcAddress
0x18000bd04  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000bd0b  mov     r10, rax
0x18000bd0e  test    rax, rax
0x18000bd11  jnz     short loc_18000BD1A
0x18000bd13  mov     eax, 0C0000139h
0x18000bd18  jmp     short loc_18000BD4A
0x18000bd1a  mov     eax, [rsp+48h+arg_30]
0x18000bd21  xor     r9d, r9d
0x18000bd24  mov     [rsp+48h+var_18], eax
0x18000bd28  mov     r8d, ebx
0x18000bd2b  mov     eax, [rsp+48h+arg_28]
0x18000bd2f  mov     rdx, rdi
0x18000bd32  mov     [rsp+48h+var_20], eax
0x18000bd36  mov     rcx, rsi
0x18000bd39  mov     rax, r10
0x18000bd3c  mov     [rsp+48h+var_28], 0
0x18000bd45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd4a  mov     rbx, [rsp+48h+arg_0]
0x18000bd4f  mov     rsi, [rsp+48h+arg_8]
0x18000bd54  add     rsp, 40h
0x18000bd58  pop     rdi
0x18000bd59  retn
```

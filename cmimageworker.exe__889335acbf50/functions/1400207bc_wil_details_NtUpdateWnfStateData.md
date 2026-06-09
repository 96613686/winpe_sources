# wil_details_NtUpdateWnfStateData

- ea: `0x1400207bc`
- end: `0x140020873`
- name: `wil_details_NtUpdateWnfStateData`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x14001cf68`
- `0x140020538`

## callees

- `0x1400207bc`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140020810`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140020810`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400207f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400207f3`

## string_xrefs

- `0x1400207ec`: `ntdll.dll`
- `0x140020806`: `NtUpdateWnfStateData`

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
0x1400207bc  mov     [rsp+arg_0], rbx
0x1400207c1  mov     [rsp+arg_8], rsi
0x1400207c6  push    rdi
0x1400207c7  sub     rsp, 40h
0x1400207cb  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1400207d2  mov     ebx, r8d
0x1400207d5  mov     rdi, rdx
0x1400207d8  mov     rsi, rcx
0x1400207db  test    r10, r10
0x1400207de  jnz     short loc_140020832
0x1400207e0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400207e7  test    rax, rax
0x1400207ea  jnz     short loc_140020806
0x1400207ec  lea     rcx, ModuleName; "ntdll.dll"
0x1400207f3  call    cs:__imp_GetModuleHandleW
0x1400207fa  nop     dword ptr [rax+rax+00h]
0x1400207ff  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140020806  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14002080d  mov     rcx, rax; hModule
0x140020810  call    cs:__imp_GetProcAddress
0x140020817  nop     dword ptr [rax+rax+00h]
0x14002081c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x140020823  mov     r10, rax
0x140020826  test    rax, rax
0x140020829  jnz     short loc_140020832
0x14002082b  mov     eax, 0C0000139h
0x140020830  jmp     short loc_140020862
0x140020832  mov     eax, [rsp+48h+arg_30]
0x140020839  xor     r9d, r9d
0x14002083c  mov     [rsp+48h+var_18], eax
0x140020840  mov     r8d, ebx
0x140020843  mov     eax, [rsp+48h+arg_28]
0x140020847  mov     rdx, rdi
0x14002084a  mov     [rsp+48h+var_20], eax
0x14002084e  mov     rcx, rsi
0x140020851  mov     rax, r10
0x140020854  mov     [rsp+48h+var_28], 0
0x14002085d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020862  mov     rbx, [rsp+48h+arg_0]
0x140020867  mov     rsi, [rsp+48h+arg_8]
0x14002086c  add     rsp, 40h
0x140020870  pop     rdi
0x140020871  retn
```

# wil_details_NtQueryWnfStateData

- ea: `0x1800273cc`
- end: `0x18002746d`
- name: `wil_details_NtQueryWnfStateData`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180024484`
- `0x1800266fc`

## callees

- `0x1800273cc`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027418`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027418`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800273fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800273fb`

## string_xrefs

- `0x1800273f4`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall wil_details_NtQueryWnfStateData(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  __int64 (__fastcall *v6)(__int64, _QWORD, _QWORD, __int64, __int64, __int64); // r10
  HMODULE ModuleHandleW; // rax

  v6 = (__int64 (__fastcall *)(__int64, _QWORD, _QWORD, __int64, __int64, __int64))g_wil_details_pfnNtQueryWnfStateData;
  if ( g_wil_details_pfnNtQueryWnfStateData )
    return v6(a1, 0, 0, a4, a5, a6);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  g_wil_details_pfnNtQueryWnfStateData = (__int64)GetProcAddress(ModuleHandleW, "NtQueryWnfStateData");
  v6 = (__int64 (__fastcall *)(__int64, _QWORD, _QWORD, __int64, __int64, __int64))g_wil_details_pfnNtQueryWnfStateData;
  if ( g_wil_details_pfnNtQueryWnfStateData )
    return v6(a1, 0, 0, a4, a5, a6);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x1800273cc  mov     [rsp+arg_0], rbx
0x1800273d1  push    rdi
0x1800273d2  sub     rsp, 40h
0x1800273d6  mov     r10, cs:g_wil_details_pfnNtQueryWnfStateData
0x1800273dd  mov     rbx, r9
0x1800273e0  mov     rdi, rcx
0x1800273e3  test    r10, r10
0x1800273e6  jnz     short loc_18002743A
0x1800273e8  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800273ef  test    rax, rax
0x1800273f2  jnz     short loc_18002740E
0x1800273f4  lea     rcx, ModuleName; "ntdll.dll"
0x1800273fb  call    cs:__imp_GetModuleHandleW
0x180027402  nop     dword ptr [rax+rax+00h]
0x180027407  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002740e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180027415  mov     rcx, rax; hModule
0x180027418  call    cs:__imp_GetProcAddress
0x18002741f  nop     dword ptr [rax+rax+00h]
0x180027424  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18002742b  mov     r10, rax
0x18002742e  test    rax, rax
0x180027431  jnz     short loc_18002743A
0x180027433  mov     eax, 0C0000139h
0x180027438  jmp     short loc_180027461
0x18002743a  mov     rax, [rsp+48h+arg_28]
0x18002743f  mov     r9, rbx
0x180027442  mov     [rsp+48h+var_20], rax
0x180027447  xor     r8d, r8d
0x18002744a  mov     rax, [rsp+48h+arg_20]
0x18002744f  xor     edx, edx
0x180027451  mov     [rsp+48h+var_28], rax
0x180027456  mov     rcx, rdi
0x180027459  mov     rax, r10
0x18002745c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027461  mov     rbx, [rsp+48h+arg_0]
0x180027466  add     rsp, 40h
0x18002746a  pop     rdi
0x18002746b  retn
```

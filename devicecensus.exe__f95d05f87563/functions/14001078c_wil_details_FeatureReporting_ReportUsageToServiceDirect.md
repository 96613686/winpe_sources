# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x14001078c`
- end: `0x140010850`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `196`
- prototype: `_BOOL8 __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x140010660`

## callees

- `0x1400023ba`
- `0x140010388`
- `0x14001078c`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001081d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001081d`

## string_xrefs

- `0x140010800`: `ntdll.dll`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, int a3)
{
  __int16 v3; // bx
  int v6; // ebp
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW_0; // rax
  int v10; // [rsp+30h] [rbp-38h] BYREF
  int v11; // [rsp+34h] [rbp-34h]
  _BYTE v12[48]; // [rsp+38h] [rbp-30h] BYREF

  v3 = a2;
  v6 = *(_DWORD *)(wil_details_FeatureReporting_RecordUsageInCache(
                     (__int64)v12,
                     *(volatile signed __int32 **)(a1 + 8),
                     a3,
                     SHIDWORD(a2))
                 + 16);
  if ( (v3 & 0x400) != 0 && a3 != 254 )
  {
    v10 = *(_DWORD *)(a1 + 24);
    v11 = (unsigned __int16)a3;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v11) |= 1u;
    ProcAddress = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
    if ( g_wil_details_pfnRtlNotifyFeatureUsage )
      goto LABEL_9;
    ModuleHandleW_0 = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW_0 = GetModuleHandleW_0(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW_0;
    }
    ProcAddress = GetProcAddress(ModuleHandleW_0, "RtlNotifyFeatureUsage");
    g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)ProcAddress;
    if ( ProcAddress )
LABEL_9:
      ((void (__fastcall *)(int *))ProcAddress)(&v10);
  }
  return v6 == 0;
}

```

## disassembly

```asm
0x14001078c  mov     [rsp+arg_18], rbx
0x140010791  push    rbp
0x140010792  push    rsi
0x140010793  push    rdi
0x140010794  sub     rsp, 50h
0x140010798  mov     r9, rdx
0x14001079b  mov     rbx, rdx
0x14001079e  mov     rdx, [rcx+8]
0x1400107a2  mov     rsi, rcx
0x1400107a5  shr     r9, 20h
0x1400107a9  lea     rcx, [rsp+68h+var_30]
0x1400107ae  mov     edi, r8d
0x1400107b1  call    wil_details_FeatureReporting_RecordUsageInCache
0x1400107b6  mov     ebp, [rax+10h]
0x1400107b9  bt      ebx, 0Ah
0x1400107bd  jnb     short loc_140010839
0x1400107bf  cmp     edi, 0FEh
0x1400107c5  jz      short loc_140010839
0x1400107c7  mov     eax, [rsi+18h]
0x1400107ca  mov     [rsp+68h+var_38], 0
0x1400107d3  mov     dword ptr [rsp+68h+var_38], eax
0x1400107d7  mov     word ptr [rsp+68h+var_38+4], di
0x1400107dc  bt      ebx, 0Bh
0x1400107e0  jnb     short loc_1400107E8
0x1400107e2  or      word ptr [rsp+68h+var_38+6], 1
0x1400107e8  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1400107ef  test    rax, rax
0x1400107f2  jnz     short loc_14001082F
0x1400107f4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x1400107fb  test    rax, rax
0x1400107fe  jnz     short loc_140010813
0x140010800  lea     rcx, LibFileName; "ntdll.dll"
0x140010807  call    GetModuleHandleW_0
0x14001080c  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x140010813  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x14001081a  mov     rcx, rax; hModule
0x14001081d  call    cs:__imp_GetProcAddress
0x140010823  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14001082a  test    rax, rax
0x14001082d  jz      short loc_140010839
0x14001082f  lea     rcx, [rsp+68h+var_38]
0x140010834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010839  mov     rbx, [rsp+68h+arg_18]
0x140010841  xor     eax, eax
0x140010843  test    ebp, ebp
0x140010845  setz    al
0x140010848  add     rsp, 50h
0x14001084c  pop     rdi
0x14001084d  pop     rsi
0x14001084e  pop     rbp
0x14001084f  retn
```

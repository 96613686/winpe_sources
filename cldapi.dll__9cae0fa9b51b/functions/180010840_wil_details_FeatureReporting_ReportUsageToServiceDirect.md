# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x180010840`
- end: `0x18001091e`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180010720`

## callees

- `0x180010444`
- `0x180010840`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800108e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800108e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800108c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800108c7`

## string_xrefs

- `0x1800108c0`: `ntdll.dll`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, unsigned __int64 a2, __int64 a3)
{
  __int16 v3; // bx
  int v4; // edi
  int v5; // esi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  __int64 v9; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v10[32]; // [rsp+38h] [rbp-20h] BYREF

  v3 = a2;
  v4 = a3;
  v5 = *(_DWORD *)(wil_details_FeatureReporting_RecordUsageInCache(
                     v10,
                     &Feature_57207774__private_reporting,
                     a3,
                     HIDWORD(a2))
                 + 16);
  if ( (v3 & 0x400) != 0 && v4 != 254 )
  {
    v9 = 57207774;
    WORD2(v9) = v4;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v9) |= 1u;
    ProcAddress = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
    if ( g_wil_details_pfnRtlNotifyFeatureUsage )
      goto LABEL_9;
    ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlNotifyFeatureUsage");
    g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)ProcAddress;
    if ( ProcAddress )
LABEL_9:
      ((void (__fastcall *)(__int64 *))ProcAddress)(&v9);
  }
  return v5 == 0;
}

```

## disassembly

```asm
0x180010840  mov     [rsp+arg_0], rbx
0x180010845  mov     [rsp+arg_18], rsi
0x18001084a  push    rdi
0x18001084b  sub     rsp, 50h
0x18001084f  mov     r9, rdx
0x180010852  lea     rcx, [rsp+58h+var_20]
0x180010857  mov     rbx, rdx
0x18001085a  shr     r9, 20h
0x18001085e  mov     rdx, cs:off_180027E58
0x180010865  mov     edi, r8d
0x180010868  call    wil_details_FeatureReporting_RecordUsageInCache
0x18001086d  mov     esi, [rax+10h]
0x180010870  bt      ebx, 0Ah
0x180010874  jnb     loc_180010906
0x18001087a  cmp     edi, 0FEh
0x180010880  jz      loc_180010906
0x180010886  mov     [rsp+58h+var_28], 0
0x18001088f  mov     dword ptr [rsp+58h+var_28], 368EBDEh
0x180010897  mov     word ptr [rsp+58h+var_28+4], di
0x18001089c  bt      ebx, 0Bh
0x1800108a0  jnb     short loc_1800108A8
0x1800108a2  or      word ptr [rsp+58h+var_28+6], 1
0x1800108a8  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1800108af  test    rax, rax
0x1800108b2  jnz     short loc_1800108FC
0x1800108b4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x1800108bb  test    rax, rax
0x1800108be  jnz     short loc_1800108DA
0x1800108c0  lea     rcx, ModuleName; "ntdll.dll"
0x1800108c7  call    cs:__imp_GetModuleHandleW
0x1800108ce  nop     dword ptr [rax+rax+00h]
0x1800108d3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x1800108da  lea     rdx, ProcName; "RtlNotifyFeatureUsage"
0x1800108e1  mov     rcx, rax; hModule
0x1800108e4  call    cs:__imp_GetProcAddress
0x1800108eb  nop     dword ptr [rax+rax+00h]
0x1800108f0  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1800108f7  test    rax, rax
0x1800108fa  jz      short loc_180010906
0x1800108fc  lea     rcx, [rsp+58h+var_28]
0x180010901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010906  mov     rbx, [rsp+58h+arg_0]
0x18001090b  xor     eax, eax
0x18001090d  test    esi, esi
0x18001090f  mov     rsi, [rsp+58h+arg_18]
0x180010914  setz    al
0x180010917  add     rsp, 50h
0x18001091b  pop     rdi
0x18001091c  retn
```

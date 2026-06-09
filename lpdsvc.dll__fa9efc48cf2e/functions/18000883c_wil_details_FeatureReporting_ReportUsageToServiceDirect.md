# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x18000883c`
- end: `0x180008905`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `201`
- prototype: `_BOOL8 __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180008720`

## callees

- `0x180008448`
- `0x18000883c`
- `0x18000e010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800088d2`
- `KERNEL32!GetProcAddress` at `0x1800088d2`
- `KERNEL32!GetModuleHandleW` at `0x1800088bb`
- `KERNEL32!GetModuleHandleW` at `0x1800088bb`

## string_xrefs

- `0x1800088b4`: `ntdll.dll`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, int a3)
{
  __int16 v3; // bx
  int v5; // esi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  __int64 v9; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v10[32]; // [rsp+38h] [rbp-20h] BYREF

  v3 = a2;
  v5 = *(_DWORD *)(wil_details_FeatureReporting_RecordUsageInCache(
                     (__int64)v10,
                     (volatile signed __int32 *)&Feature_LpdDeprecationAndRemoval__private_reporting,
                     a3,
                     SHIDWORD(a2))
                 + 16);
  if ( (v3 & 0x400) != 0 && a3 != 254 )
  {
    v9 = 57118291;
    WORD2(v9) = a3;
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
0x18000883c  mov     [rsp+arg_0], rbx
0x180008841  mov     [rsp+arg_18], rsi
0x180008846  push    rdi
0x180008847  sub     rsp, 50h
0x18000884b  mov     r9, rdx
0x18000884e  lea     rcx, [rsp+58h+var_20]
0x180008853  mov     rbx, rdx
0x180008856  shr     r9, 20h
0x18000885a  mov     rdx, cs:off_180010EE0
0x180008861  mov     edi, r8d
0x180008864  call    wil_details_FeatureReporting_RecordUsageInCache
0x180008869  mov     esi, [rax+10h]
0x18000886c  bt      ebx, 0Ah
0x180008870  jnb     short loc_1800088EE
0x180008872  cmp     edi, 0FEh
0x180008878  jz      short loc_1800088EE
0x18000887a  mov     [rsp+58h+var_28], 0
0x180008883  mov     dword ptr [rsp+58h+var_28], 3678E53h
0x18000888b  mov     word ptr [rsp+58h+var_28+4], di
0x180008890  bt      ebx, 0Bh
0x180008894  jnb     short loc_18000889C
0x180008896  or      word ptr [rsp+58h+var_28+6], 1
0x18000889c  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1800088a3  test    rax, rax
0x1800088a6  jnz     short loc_1800088E4
0x1800088a8  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x1800088af  test    rax, rax
0x1800088b2  jnz     short loc_1800088C8
0x1800088b4  lea     rcx, ModuleName; "ntdll.dll"
0x1800088bb  call    cs:__imp_GetModuleHandleW
0x1800088c1  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x1800088c8  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1800088cf  mov     rcx, rax; hModule
0x1800088d2  call    cs:__imp_GetProcAddress
0x1800088d8  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1800088df  test    rax, rax
0x1800088e2  jz      short loc_1800088EE
0x1800088e4  lea     rcx, [rsp+58h+var_28]
0x1800088e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088ee  mov     rbx, [rsp+58h+arg_0]
0x1800088f3  xor     eax, eax
0x1800088f5  test    esi, esi
0x1800088f7  mov     rsi, [rsp+58h+arg_18]
0x1800088fc  setz    al
0x1800088ff  add     rsp, 50h
0x180008903  pop     rdi
0x180008904  retn
```

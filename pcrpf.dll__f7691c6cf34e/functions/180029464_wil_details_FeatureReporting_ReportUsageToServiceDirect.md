# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x180029464`
- end: `0x180029542`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180029808`

## callees

- `0x18001c110`
- `0x180029464`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029508`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029508`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800294eb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800294eb`

## string_xrefs

- `0x1800294e4`: `ntdll.dll`

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
                     &Feature_Ppf_PilotFish_Integration__private_reporting,
                     a3,
                     HIDWORD(a2))
                 + 16);
  if ( (v3 & 0x400) != 0 && v4 != 254 )
  {
    v9 = 53100131;
    WORD2(v9) = v4;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v9) |= 1u;
    ProcAddress = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
    if ( g_wil_details_pfnRtlNotifyFeatureUsage )
      goto LABEL_9;
    ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x180029464  mov     [rsp+arg_0], rbx
0x180029469  mov     [rsp+arg_18], rsi
0x18002946e  push    rdi
0x18002946f  sub     rsp, 50h
0x180029473  mov     r9, rdx
0x180029476  lea     rcx, [rsp+58h+var_20]
0x18002947b  mov     rbx, rdx
0x18002947e  shr     r9, 20h
0x180029482  mov     rdx, cs:off_18006F778
0x180029489  mov     edi, r8d
0x18002948c  call    wil_details_FeatureReporting_RecordUsageInCache
0x180029491  mov     esi, [rax+10h]
0x180029494  bt      ebx, 0Ah
0x180029498  jnb     loc_18002952A
0x18002949e  cmp     edi, 0FEh
0x1800294a4  jz      loc_18002952A
0x1800294aa  mov     [rsp+58h+var_28], 0
0x1800294b3  mov     dword ptr [rsp+58h+var_28], 32A3E63h
0x1800294bb  mov     word ptr [rsp+58h+var_28+4], di
0x1800294c0  bt      ebx, 0Bh
0x1800294c4  jnb     short loc_1800294CC
0x1800294c6  or      word ptr [rsp+58h+var_28+6], 1
0x1800294cc  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1800294d3  test    rax, rax
0x1800294d6  jnz     short loc_180029520
0x1800294d8  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800294df  test    rax, rax
0x1800294e2  jnz     short loc_1800294FE
0x1800294e4  lea     rcx, ModuleName; "ntdll.dll"
0x1800294eb  call    cs:__imp_GetModuleHandleW
0x1800294f2  nop     dword ptr [rax+rax+00h]
0x1800294f7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800294fe  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180029505  mov     rcx, rax; hModule
0x180029508  call    cs:__imp_GetProcAddress
0x18002950f  nop     dword ptr [rax+rax+00h]
0x180029514  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18002951b  test    rax, rax
0x18002951e  jz      short loc_18002952A
0x180029520  lea     rcx, [rsp+58h+var_28]
0x180029525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002952a  mov     rbx, [rsp+58h+arg_0]
0x18002952f  xor     eax, eax
0x180029531  test    esi, esi
0x180029533  mov     rsi, [rsp+58h+arg_18]
0x180029538  setz    al
0x18002953b  add     rsp, 50h
0x18002953f  pop     rdi
0x180029540  retn
```

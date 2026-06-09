# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x18000c754`
- end: `0x18000c81d`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x18000c638`

## callees

- `0x18000af10`
- `0x18000c754`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c7ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c7ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c7d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c7d3`

## string_xrefs

- `0x18000c7cc`: `ntdll.dll`

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
                     &Feature_ShadowAdmin__private_reporting,
                     a3,
                     HIDWORD(a2))
                 + 16);
  if ( (v3 & 0x400) != 0 && v4 != 254 )
  {
    v9 = 60288851;
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
0x18000c754  mov     [rsp+arg_0], rbx
0x18000c759  mov     [rsp+arg_18], rsi
0x18000c75e  push    rdi
0x18000c75f  sub     rsp, 50h
0x18000c763  mov     r9, rdx
0x18000c766  lea     rcx, [rsp+58h+var_20]
0x18000c76b  mov     rbx, rdx
0x18000c76e  shr     r9, 20h
0x18000c772  mov     rdx, cs:off_180011B08
0x18000c779  mov     edi, r8d
0x18000c77c  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000c781  mov     esi, [rax+10h]
0x18000c784  bt      ebx, 0Ah
0x18000c788  jnb     short loc_18000C806
0x18000c78a  cmp     edi, 0FEh
0x18000c790  jz      short loc_18000C806
0x18000c792  mov     [rsp+58h+var_28], 0
0x18000c79b  mov     dword ptr [rsp+58h+var_28], 397EF53h
0x18000c7a3  mov     word ptr [rsp+58h+var_28+4], di
0x18000c7a8  bt      ebx, 0Bh
0x18000c7ac  jnb     short loc_18000C7B4
0x18000c7ae  or      word ptr [rsp+58h+var_28+6], 1
0x18000c7b4  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000c7bb  test    rax, rax
0x18000c7be  jnz     short loc_18000C7FC
0x18000c7c0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c7c7  test    rax, rax
0x18000c7ca  jnz     short loc_18000C7E0
0x18000c7cc  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000c7d3  call    cs:__imp_GetModuleHandleW
0x18000c7d9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c7e0  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000c7e7  mov     rcx, rax; hModule
0x18000c7ea  call    cs:__imp_GetProcAddress
0x18000c7f0  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000c7f7  test    rax, rax
0x18000c7fa  jz      short loc_18000C806
0x18000c7fc  lea     rcx, [rsp+58h+var_28]
0x18000c801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c806  mov     rbx, [rsp+58h+arg_0]
0x18000c80b  xor     eax, eax
0x18000c80d  test    esi, esi
0x18000c80f  mov     rsi, [rsp+58h+arg_18]
0x18000c814  setz    al
0x18000c817  add     rsp, 50h
0x18000c81b  pop     rdi
0x18000c81c  retn
```

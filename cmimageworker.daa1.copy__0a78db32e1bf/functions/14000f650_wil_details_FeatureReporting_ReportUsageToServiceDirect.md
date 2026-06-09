# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x14000f650`
- end: `0x14000f72e`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x14000f530`

## callees

- `0x14000f254`
- `0x14000f650`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000f6f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000f6f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000f6d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000f6d7`

## string_xrefs

- `0x14000f6d0`: `ntdll.dll`

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
                     &Feature_WcRemoveFileOwnershipTOCTOU__private_reporting,
                     a3,
                     HIDWORD(a2))
                 + 16);
  if ( (v3 & 0x400) != 0 && v4 != 254 )
  {
    v9 = 50974410;
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
0x14000f650  mov     [rsp+arg_0], rbx
0x14000f655  mov     [rsp+arg_18], rsi
0x14000f65a  push    rdi
0x14000f65b  sub     rsp, 50h
0x14000f65f  mov     r9, rdx
0x14000f662  lea     rcx, [rsp+58h+var_20]
0x14000f667  mov     rbx, rdx
0x14000f66a  shr     r9, 20h
0x14000f66e  mov     rdx, cs:off_14003BBD0
0x14000f675  mov     edi, r8d
0x14000f678  call    wil_details_FeatureReporting_RecordUsageInCache
0x14000f67d  mov     esi, [rax+10h]
0x14000f680  bt      ebx, 0Ah
0x14000f684  jnb     loc_14000F716
0x14000f68a  cmp     edi, 0FEh
0x14000f690  jz      loc_14000F716
0x14000f696  mov     [rsp+58h+var_28], 0
0x14000f69f  mov     dword ptr [rsp+58h+var_28], 309CECAh
0x14000f6a7  mov     word ptr [rsp+58h+var_28+4], di
0x14000f6ac  bt      ebx, 0Bh
0x14000f6b0  jnb     short loc_14000F6B8
0x14000f6b2  or      word ptr [rsp+58h+var_28+6], 1
0x14000f6b8  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14000f6bf  test    rax, rax
0x14000f6c2  jnz     short loc_14000F70C
0x14000f6c4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x14000f6cb  test    rax, rax
0x14000f6ce  jnz     short loc_14000F6EA
0x14000f6d0  lea     rcx, ModuleName; "ntdll.dll"
0x14000f6d7  call    cs:__imp_GetModuleHandleW
0x14000f6de  nop     dword ptr [rax+rax+00h]
0x14000f6e3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x14000f6ea  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x14000f6f1  mov     rcx, rax; hModule
0x14000f6f4  call    cs:__imp_GetProcAddress
0x14000f6fb  nop     dword ptr [rax+rax+00h]
0x14000f700  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14000f707  test    rax, rax
0x14000f70a  jz      short loc_14000F716
0x14000f70c  lea     rcx, [rsp+58h+var_28]
0x14000f711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f716  mov     rbx, [rsp+58h+arg_0]
0x14000f71b  xor     eax, eax
0x14000f71d  test    esi, esi
0x14000f71f  mov     rsi, [rsp+58h+arg_18]
0x14000f724  setz    al
0x14000f727  add     rsp, 50h
0x14000f72b  pop     rdi
0x14000f72c  retn
```

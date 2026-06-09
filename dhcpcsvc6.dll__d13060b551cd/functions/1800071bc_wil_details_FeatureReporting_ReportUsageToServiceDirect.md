# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x1800071bc`
- end: `0x18000725d`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `161`
- prototype: `_BOOL8 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180007090`

## callees

- `0x180002ad0`
- `0x1800071bc`
- `0x1800072b8`
- `0x180009010`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, __int64 a3)
{
  __int16 v3; // bx
  int v5; // edi
  int v6; // ebp
  void (__fastcall *NtDllProcedureAddress)(int *); // rax
  int v9; // [rsp+30h] [rbp-38h] BYREF
  int v10; // [rsp+34h] [rbp-34h]
  _BYTE v11[48]; // [rsp+38h] [rbp-30h] BYREF

  v3 = a2;
  v5 = a3;
  v6 = *(_DWORD *)(wil_details_FeatureReporting_RecordUsageInCache(
                     (__int64)v11,
                     *(volatile signed __int32 **)(a1 + 8),
                     a3,
                     SHIDWORD(a2))
                 + 16);
  if ( (v3 & 0x400) != 0 && v5 != 254 )
  {
    v9 = *(_DWORD *)(a1 + 24);
    v10 = (unsigned __int16)v5;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v10) |= 1u;
    NtDllProcedureAddress = (void (__fastcall *)(int *))g_wil_details_pfnRtlNotifyFeatureUsage;
    if ( g_wil_details_pfnRtlNotifyFeatureUsage
      || (NtDllProcedureAddress = (void (__fastcall *)(int *))wil_details_GetNtDllProcedureAddress("RtlNotifyFeatureUsage"),
          (g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)NtDllProcedureAddress) != 0) )
    {
      NtDllProcedureAddress(&v9);
    }
  }
  return v6 == 0;
}

```

## disassembly

```asm
0x1800071bc  mov     [rsp+arg_18], rbx
0x1800071c1  push    rbp
0x1800071c2  push    rsi
0x1800071c3  push    rdi
0x1800071c4  sub     rsp, 50h
0x1800071c8  mov     r9, rdx
0x1800071cb  mov     rbx, rdx
0x1800071ce  mov     rdx, [rcx+8]
0x1800071d2  mov     rsi, rcx
0x1800071d5  shr     r9, 20h
0x1800071d9  lea     rcx, [rsp+68h+var_30]
0x1800071de  mov     edi, r8d
0x1800071e1  call    wil_details_FeatureReporting_RecordUsageInCache
0x1800071e6  mov     ebp, [rax+10h]
0x1800071e9  bt      ebx, 0Ah
0x1800071ed  jnb     short loc_180007246
0x1800071ef  cmp     edi, 0FEh
0x1800071f5  jz      short loc_180007246
0x1800071f7  mov     eax, [rsi+18h]
0x1800071fa  mov     [rsp+68h+var_38], 0
0x180007203  mov     dword ptr [rsp+68h+var_38], eax
0x180007207  mov     word ptr [rsp+68h+var_38+4], di
0x18000720c  bt      ebx, 0Bh
0x180007210  jnb     short loc_180007218
0x180007212  or      word ptr [rsp+68h+var_38+6], 1
0x180007218  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000721f  test    rax, rax
0x180007222  jnz     short loc_18000723C
0x180007224  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000722b  call    wil_details_GetNtDllProcedureAddress
0x180007230  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180007237  test    rax, rax
0x18000723a  jz      short loc_180007246
0x18000723c  lea     rcx, [rsp+68h+var_38]
0x180007241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007246  mov     rbx, [rsp+68h+arg_18]
0x18000724e  xor     eax, eax
0x180007250  test    ebp, ebp
0x180007252  setz    al
0x180007255  add     rsp, 50h
0x180007259  pop     rdi
0x18000725a  pop     rsi
0x18000725b  pop     rbp
0x18000725c  retn
```

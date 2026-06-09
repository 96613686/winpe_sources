# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x18002d580`
- end: `0x18002d622`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x18002d4f8`

## callees

- `0x1800186f4`
- `0x18002d374`
- `0x18002d580`
- `0x180035010`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, unsigned int a3)
{
  __int16 v3; // bx
  int v6; // ebp
  FARPROC NtDllProcedureAddress; // rax
  int v9; // [rsp+30h] [rbp-38h] BYREF
  int v10; // [rsp+34h] [rbp-34h]
  _BYTE v11[48]; // [rsp+38h] [rbp-30h] BYREF

  v3 = a2;
  v6 = wil_details_FeatureReporting_RecordUsageInCache(
         (__int64)v11,
         *(volatile signed __int32 **)(a1 + 8),
         a3,
         SHIDWORD(a2))[4];
  if ( (v3 & 0x400) != 0 && a3 != 254 )
  {
    v9 = *(_DWORD *)(a1 + 24);
    v10 = (unsigned __int16)a3;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v10) |= 1u;
    NtDllProcedureAddress = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
    if ( g_wil_details_pfnRtlNotifyFeatureUsage
      || (NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlNotifyFeatureUsage"),
          (g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)NtDllProcedureAddress) != 0) )
    {
      ((void (__fastcall *)(int *))NtDllProcedureAddress)(&v9);
    }
  }
  return v6 == 0;
}

```

## disassembly

```asm
0x18002d580  mov     [rsp+arg_18], rbx
0x18002d585  push    rbp
0x18002d586  push    rsi
0x18002d587  push    rdi
0x18002d588  sub     rsp, 50h
0x18002d58c  mov     r9, rdx
0x18002d58f  mov     rbx, rdx
0x18002d592  mov     rdx, [rcx+8]
0x18002d596  mov     rsi, rcx
0x18002d599  shr     r9, 20h
0x18002d59d  lea     rcx, [rsp+68h+var_30]
0x18002d5a2  mov     edi, r8d
0x18002d5a5  call    wil_details_FeatureReporting_RecordUsageInCache
0x18002d5aa  mov     ebp, [rax+10h]
0x18002d5ad  bt      ebx, 0Ah
0x18002d5b1  jnb     short loc_18002D60A
0x18002d5b3  cmp     edi, 0FEh
0x18002d5b9  jz      short loc_18002D60A
0x18002d5bb  mov     eax, [rsi+18h]
0x18002d5be  mov     [rsp+68h+var_38], 0
0x18002d5c7  mov     dword ptr [rsp+68h+var_38], eax
0x18002d5cb  mov     word ptr [rsp+68h+var_38+4], di
0x18002d5d0  bt      ebx, 0Bh
0x18002d5d4  jnb     short loc_18002D5DC
0x18002d5d6  or      word ptr [rsp+68h+var_38+6], 1
0x18002d5dc  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18002d5e3  test    rax, rax
0x18002d5e6  jnz     short loc_18002D600
0x18002d5e8  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18002d5ef  call    wil_details_GetNtDllProcedureAddress
0x18002d5f4  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18002d5fb  test    rax, rax
0x18002d5fe  jz      short loc_18002D60A
0x18002d600  lea     rcx, [rsp+68h+var_38]
0x18002d605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d60a  mov     rbx, [rsp+68h+arg_18]
0x18002d612  xor     eax, eax
0x18002d614  test    ebp, ebp
0x18002d616  setz    al
0x18002d619  add     rsp, 50h
0x18002d61d  pop     rdi
0x18002d61e  pop     rsi
0x18002d61f  pop     rbp
0x18002d620  retn
```

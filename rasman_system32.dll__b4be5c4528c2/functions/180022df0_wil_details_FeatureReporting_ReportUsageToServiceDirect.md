# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x180022df0`
- end: `0x180022e92`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180022d68`

## callees

- `0x180022be4`
- `0x180022df0`
- `0x180023154`
- `0x180028010`

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
0x180022df0  mov     [rsp+arg_18], rbx
0x180022df5  push    rbp
0x180022df6  push    rsi
0x180022df7  push    rdi
0x180022df8  sub     rsp, 50h
0x180022dfc  mov     r9, rdx
0x180022dff  mov     rbx, rdx
0x180022e02  mov     rdx, [rcx+8]
0x180022e06  mov     rsi, rcx
0x180022e09  shr     r9, 20h
0x180022e0d  lea     rcx, [rsp+68h+var_30]
0x180022e12  mov     edi, r8d
0x180022e15  call    wil_details_FeatureReporting_RecordUsageInCache
0x180022e1a  mov     ebp, [rax+10h]
0x180022e1d  bt      ebx, 0Ah
0x180022e21  jnb     short loc_180022E7A
0x180022e23  cmp     edi, 0FEh
0x180022e29  jz      short loc_180022E7A
0x180022e2b  mov     eax, [rsi+18h]
0x180022e2e  mov     [rsp+68h+var_38], 0
0x180022e37  mov     dword ptr [rsp+68h+var_38], eax
0x180022e3b  mov     word ptr [rsp+68h+var_38+4], di
0x180022e40  bt      ebx, 0Bh
0x180022e44  jnb     short loc_180022E4C
0x180022e46  or      word ptr [rsp+68h+var_38+6], 1
0x180022e4c  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180022e53  test    rax, rax
0x180022e56  jnz     short loc_180022E70
0x180022e58  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180022e5f  call    wil_details_GetNtDllProcedureAddress
0x180022e64  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180022e6b  test    rax, rax
0x180022e6e  jz      short loc_180022E7A
0x180022e70  lea     rcx, [rsp+68h+var_38]
0x180022e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e7a  mov     rbx, [rsp+68h+arg_18]
0x180022e82  xor     eax, eax
0x180022e84  test    ebp, ebp
0x180022e86  setz    al
0x180022e89  add     rsp, 50h
0x180022e8d  pop     rdi
0x180022e8e  pop     rsi
0x180022e8f  pop     rbp
0x180022e90  retn
```

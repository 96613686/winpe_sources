# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x18002233c`
- end: `0x1800223dd`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180022210`

## callees

- `0x18002208c`
- `0x18002233c`
- `0x180022664`
- `0x180027010`

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
0x18002233c  mov     [rsp+arg_18], rbx
0x180022341  push    rbp
0x180022342  push    rsi
0x180022343  push    rdi
0x180022344  sub     rsp, 50h
0x180022348  mov     r9, rdx
0x18002234b  mov     rbx, rdx
0x18002234e  mov     rdx, [rcx+8]
0x180022352  mov     rsi, rcx
0x180022355  shr     r9, 20h
0x180022359  lea     rcx, [rsp+68h+var_30]
0x18002235e  mov     edi, r8d
0x180022361  call    wil_details_FeatureReporting_RecordUsageInCache
0x180022366  mov     ebp, [rax+10h]
0x180022369  bt      ebx, 0Ah
0x18002236d  jnb     short loc_1800223C6
0x18002236f  cmp     edi, 0FEh
0x180022375  jz      short loc_1800223C6
0x180022377  mov     eax, [rsi+18h]
0x18002237a  mov     [rsp+68h+var_38], 0
0x180022383  mov     dword ptr [rsp+68h+var_38], eax
0x180022387  mov     word ptr [rsp+68h+var_38+4], di
0x18002238c  bt      ebx, 0Bh
0x180022390  jnb     short loc_180022398
0x180022392  or      word ptr [rsp+68h+var_38+6], 1
0x180022398  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18002239f  test    rax, rax
0x1800223a2  jnz     short loc_1800223BC
0x1800223a4  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1800223ab  call    wil_details_GetNtDllProcedureAddress
0x1800223b0  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1800223b7  test    rax, rax
0x1800223ba  jz      short loc_1800223C6
0x1800223bc  lea     rcx, [rsp+68h+var_38]
0x1800223c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223c6  mov     rbx, [rsp+68h+arg_18]
0x1800223ce  xor     eax, eax
0x1800223d0  test    ebp, ebp
0x1800223d2  setz    al
0x1800223d5  add     rsp, 50h
0x1800223d9  pop     rdi
0x1800223da  pop     rsi
0x1800223db  pop     rbp
0x1800223dc  retn
```

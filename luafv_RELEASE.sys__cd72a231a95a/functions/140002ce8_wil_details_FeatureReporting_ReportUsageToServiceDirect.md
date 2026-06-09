# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x140002ce8`
- end: `0x140002dc2`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `218`
- prototype: `_BOOL8 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140002c60`

## callees

- `0x140002adc`
- `0x140002ce8`
- `0x140005bb0`
- `0x140005c90`

## import_xrefs

- `ntoskrnl!RtlNotifyFeatureUsage` at `0x140002d94`
- `ntoskrnl!RtlNotifyFeatureUsage` at `0x140002d94`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, __int64 a3)
{
  __int16 v3; // bx
  unsigned int v5; // esi
  _DWORD *v6; // rax
  int v8; // [rsp+30h] [rbp-68h] BYREF
  int v9; // [rsp+34h] [rbp-64h]
  _BYTE v10[24]; // [rsp+38h] [rbp-60h] BYREF
  __int128 v11; // [rsp+50h] [rbp-48h] BYREF
  __int64 v12; // [rsp+60h] [rbp-38h]

  v3 = a2;
  v5 = a3;
  v6 = wil_details_FeatureReporting_RecordUsageInCache(
         (__int64)v10,
         *(volatile signed __int32 **)(a1 + 8),
         a3,
         SHIDWORD(a2));
  v11 = *(_OWORD *)v6;
  v12 = *((_QWORD *)v6 + 2);
  if ( g_wil_details_recordFeatureUsage )
    g_wil_details_recordFeatureUsage(*(unsigned int *)(a1 + 24), v5, 1, *(_QWORD *)(a1 + 8), &v11);
  if ( (v3 & 0x400) != 0 && v5 != 254 )
  {
    v8 = *(_DWORD *)(a1 + 24);
    v9 = (unsigned __int16)v5;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v9) |= 1u;
    RtlNotifyFeatureUsage(&v8);
  }
  return (_DWORD)v12 == 0;
}

```

## disassembly

```asm
0x140002ce8  push    rbx
0x140002cea  push    rbp
0x140002ceb  push    rsi
0x140002cec  push    rdi
0x140002ced  push    r14
0x140002cef  sub     rsp, 70h
0x140002cf3  mov     rax, cs:__security_cookie
0x140002cfa  xor     rax, rsp
0x140002cfd  mov     [rsp+98h+var_30], rax
0x140002d02  mov     r9, rdx
0x140002d05  mov     rbx, rdx
0x140002d08  mov     rdx, [rcx+8]
0x140002d0c  mov     rbp, rcx
0x140002d0f  shr     r9, 20h
0x140002d13  lea     rcx, [rsp+98h+var_60]
0x140002d18  mov     esi, r8d
0x140002d1b  call    wil_details_FeatureReporting_RecordUsageInCache
0x140002d20  mov     r14d, 1
0x140002d26  movups  xmm1, xmmword ptr [rax]
0x140002d29  movups  [rsp+98h+var_48], xmm1
0x140002d2e  movsd   xmm0, qword ptr [rax+10h]
0x140002d33  mov     rax, cs:g_wil_details_recordFeatureUsage
0x140002d3a  movsd   [rsp+98h+var_38], xmm0
0x140002d40  test    rax, rax
0x140002d43  jz      short loc_140002D60
0x140002d45  mov     r9, [rbp+8]
0x140002d49  lea     rcx, [rsp+98h+var_48]
0x140002d4e  mov     [rsp+98h+var_78], rcx
0x140002d53  mov     r8d, r14d
0x140002d56  mov     ecx, [rbp+18h]
0x140002d59  mov     edx, esi
0x140002d5b  call    _guard_dispatch_icall
0x140002d60  bt      ebx, 0Ah
0x140002d64  jnb     short loc_140002DA0
0x140002d66  cmp     esi, 0FEh
0x140002d6c  jz      short loc_140002DA0
0x140002d6e  mov     eax, [rbp+18h]
0x140002d71  mov     [rsp+98h+var_68], 0
0x140002d7a  mov     dword ptr [rsp+98h+var_68], eax
0x140002d7e  mov     word ptr [rsp+98h+var_68+4], si
0x140002d83  bt      ebx, 0Bh
0x140002d87  jnb     short loc_140002D8F
0x140002d89  or      word ptr [rsp+98h+var_68+6], r14w
0x140002d8f  lea     rcx, [rsp+98h+var_68]
0x140002d94  call    cs:__imp_RtlNotifyFeatureUsage
0x140002d9b  nop     dword ptr [rax+rax+00h]
0x140002da0  xor     eax, eax
0x140002da2  cmp     dword ptr [rsp+98h+var_38], eax
0x140002da6  setz    al
0x140002da9  mov     rcx, [rsp+98h+var_30]
0x140002dae  xor     rcx, rsp; StackCookie
0x140002db1  call    __security_check_cookie
0x140002db6  add     rsp, 70h
0x140002dba  pop     r14
0x140002dbc  pop     rdi
0x140002dbd  pop     rsi
0x140002dbe  pop     rbp
0x140002dbf  pop     rbx
0x140002dc0  retn
```

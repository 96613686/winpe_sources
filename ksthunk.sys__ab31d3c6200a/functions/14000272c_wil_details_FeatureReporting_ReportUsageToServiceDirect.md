# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x14000272c`
- end: `0x140002806`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `218`
- prototype: `_BOOL8 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140002600`

## callees

- `0x140002324`
- `0x14000272c`
- `0x140004110`
- `0x1400041f0`

## import_xrefs

- `ntoskrnl!RtlNotifyFeatureUsage` at `0x1400027d8`
- `ntoskrnl!RtlNotifyFeatureUsage` at `0x1400027d8`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, unsigned int a3)
{
  __int16 v3; // bx
  __int64 v6; // rax
  int v8; // [rsp+30h] [rbp-68h] BYREF
  int v9; // [rsp+34h] [rbp-64h]
  _BYTE v10[24]; // [rsp+38h] [rbp-60h] BYREF
  __int128 v11; // [rsp+50h] [rbp-48h] BYREF
  __int64 v12; // [rsp+60h] [rbp-38h]

  v3 = a2;
  v6 = wil_details_FeatureReporting_RecordUsageInCache(
         (__int64)v10,
         *(volatile signed __int32 **)(a1 + 8),
         a3,
         SHIDWORD(a2));
  v11 = *(_OWORD *)v6;
  v12 = *(_QWORD *)(v6 + 16);
  if ( g_wil_details_recordFeatureUsage )
    g_wil_details_recordFeatureUsage(*(unsigned int *)(a1 + 24), a3, 1, *(_QWORD *)(a1 + 8), &v11);
  if ( (v3 & 0x400) != 0 && a3 != 254 )
  {
    v8 = *(_DWORD *)(a1 + 24);
    v9 = (unsigned __int16)a3;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v9) |= 1u;
    RtlNotifyFeatureUsage(&v8);
  }
  return (_DWORD)v12 == 0;
}

```

## disassembly

```asm
0x14000272c  push    rbx
0x14000272e  push    rbp
0x14000272f  push    rsi
0x140002730  push    rdi
0x140002731  push    r14
0x140002733  sub     rsp, 70h
0x140002737  mov     rax, cs:__security_cookie
0x14000273e  xor     rax, rsp
0x140002741  mov     [rsp+98h+var_30], rax
0x140002746  mov     r9, rdx
0x140002749  mov     rbx, rdx
0x14000274c  mov     rdx, [rcx+8]
0x140002750  mov     rbp, rcx
0x140002753  shr     r9, 20h
0x140002757  lea     rcx, [rsp+98h+var_60]
0x14000275c  mov     esi, r8d
0x14000275f  call    wil_details_FeatureReporting_RecordUsageInCache
0x140002764  mov     r14d, 1
0x14000276a  movups  xmm1, xmmword ptr [rax]
0x14000276d  movups  [rsp+98h+var_48], xmm1
0x140002772  movsd   xmm0, qword ptr [rax+10h]
0x140002777  mov     rax, cs:g_wil_details_recordFeatureUsage
0x14000277e  movsd   [rsp+98h+var_38], xmm0
0x140002784  test    rax, rax
0x140002787  jz      short loc_1400027A4
0x140002789  mov     r9, [rbp+8]
0x14000278d  lea     rcx, [rsp+98h+var_48]
0x140002792  mov     [rsp+98h+var_78], rcx
0x140002797  mov     r8d, r14d
0x14000279a  mov     ecx, [rbp+18h]
0x14000279d  mov     edx, esi
0x14000279f  call    _guard_dispatch_icall
0x1400027a4  bt      ebx, 0Ah
0x1400027a8  jnb     short loc_1400027E4
0x1400027aa  cmp     esi, 0FEh
0x1400027b0  jz      short loc_1400027E4
0x1400027b2  mov     eax, [rbp+18h]
0x1400027b5  mov     [rsp+98h+var_68], 0
0x1400027be  mov     dword ptr [rsp+98h+var_68], eax
0x1400027c2  mov     word ptr [rsp+98h+var_68+4], si
0x1400027c7  bt      ebx, 0Bh
0x1400027cb  jnb     short loc_1400027D3
0x1400027cd  or      word ptr [rsp+98h+var_68+6], r14w
0x1400027d3  lea     rcx, [rsp+98h+var_68]
0x1400027d8  call    cs:__imp_RtlNotifyFeatureUsage
0x1400027df  nop     dword ptr [rax+rax+00h]
0x1400027e4  xor     eax, eax
0x1400027e6  cmp     dword ptr [rsp+98h+var_38], eax
0x1400027ea  setz    al
0x1400027ed  mov     rcx, [rsp+98h+var_30]
0x1400027f2  xor     rcx, rsp; StackCookie
0x1400027f5  call    __security_check_cookie
0x1400027fa  add     rsp, 70h
0x1400027fe  pop     r14
0x140002800  pop     rdi
0x140002801  pop     rsi
0x140002802  pop     rbp
0x140002803  pop     rbx
0x140002804  retn
```

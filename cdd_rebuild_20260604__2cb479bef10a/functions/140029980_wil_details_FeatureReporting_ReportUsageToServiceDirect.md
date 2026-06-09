# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x140029980`
- end: `0x140029a5a`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1400298f8`

## callees

- `0x140029774`
- `0x140029980`
- `0x1400371f0`
- `0x1400372d0`

## import_xrefs

- `ntoskrnl!RtlNotifyFeatureUsage` at `0x140029a2c`
- `ntoskrnl!RtlNotifyFeatureUsage` at `0x140029a2c`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, unsigned int a3)
{
  __int16 v3; // bx
  _DWORD *v6; // rax
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
  v12 = *((_QWORD *)v6 + 2);
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
0x140029980  push    rbx
0x140029982  push    rbp
0x140029983  push    rsi
0x140029984  push    rdi
0x140029985  push    r14
0x140029987  sub     rsp, 70h
0x14002998b  mov     rax, cs:__security_cookie
0x140029992  xor     rax, rsp
0x140029995  mov     [rsp+98h+var_30], rax
0x14002999a  mov     r9, rdx
0x14002999d  mov     rbx, rdx
0x1400299a0  mov     rdx, [rcx+8]
0x1400299a4  mov     rbp, rcx
0x1400299a7  shr     r9, 20h
0x1400299ab  lea     rcx, [rsp+98h+var_60]
0x1400299b0  mov     esi, r8d
0x1400299b3  call    wil_details_FeatureReporting_RecordUsageInCache
0x1400299b8  mov     r14d, 1
0x1400299be  movups  xmm1, xmmword ptr [rax]
0x1400299c1  movups  [rsp+98h+var_48], xmm1
0x1400299c6  movsd   xmm0, qword ptr [rax+10h]
0x1400299cb  mov     rax, cs:g_wil_details_recordFeatureUsage
0x1400299d2  movsd   [rsp+98h+var_38], xmm0
0x1400299d8  test    rax, rax
0x1400299db  jz      short loc_1400299F8
0x1400299dd  mov     r9, [rbp+8]
0x1400299e1  lea     rcx, [rsp+98h+var_48]
0x1400299e6  mov     [rsp+98h+var_78], rcx
0x1400299eb  mov     r8d, r14d
0x1400299ee  mov     ecx, [rbp+18h]
0x1400299f1  mov     edx, esi
0x1400299f3  call    _guard_dispatch_icall
0x1400299f8  bt      ebx, 0Ah
0x1400299fc  jnb     short loc_140029A38
0x1400299fe  cmp     esi, 0FEh
0x140029a04  jz      short loc_140029A38
0x140029a06  mov     eax, [rbp+18h]
0x140029a09  mov     [rsp+98h+var_68], 0
0x140029a12  mov     dword ptr [rsp+98h+var_68], eax
0x140029a16  mov     word ptr [rsp+98h+var_68+4], si
0x140029a1b  bt      ebx, 0Bh
0x140029a1f  jnb     short loc_140029A27
0x140029a21  or      word ptr [rsp+98h+var_68+6], r14w
0x140029a27  lea     rcx, [rsp+98h+var_68]
0x140029a2c  call    cs:__imp_RtlNotifyFeatureUsage
0x140029a33  nop     dword ptr [rax+rax+00h]
0x140029a38  xor     eax, eax
0x140029a3a  cmp     dword ptr [rsp+98h+var_38], eax
0x140029a3e  setz    al
0x140029a41  mov     rcx, [rsp+98h+var_30]
0x140029a46  xor     rcx, rsp; StackCookie
0x140029a49  call    __security_check_cookie
0x140029a4e  add     rsp, 70h
0x140029a52  pop     r14
0x140029a54  pop     rdi
0x140029a55  pop     rsi
0x140029a56  pop     rbp
0x140029a57  pop     rbx
0x140029a58  retn
```

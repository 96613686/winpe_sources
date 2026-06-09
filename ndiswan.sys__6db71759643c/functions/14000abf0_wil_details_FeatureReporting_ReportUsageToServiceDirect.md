# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x14000abf0`
- end: `0x14000acca`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14000ab68`

## callees

- `0x14000a9e4`
- `0x14000abf0`
- `0x1400161f0`
- `0x140016230`

## import_xrefs

- `ntoskrnl!RtlNotifyFeatureUsage` at `0x14000ac9c`
- `ntoskrnl!RtlNotifyFeatureUsage` at `0x14000ac9c`

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
0x14000abf0  push    rbx
0x14000abf2  push    rbp
0x14000abf3  push    rsi
0x14000abf4  push    rdi
0x14000abf5  push    r14
0x14000abf7  sub     rsp, 70h
0x14000abfb  mov     rax, cs:__security_cookie
0x14000ac02  xor     rax, rsp
0x14000ac05  mov     [rsp+98h+var_30], rax
0x14000ac0a  mov     r9, rdx
0x14000ac0d  mov     rbx, rdx
0x14000ac10  mov     rdx, [rcx+8]
0x14000ac14  mov     rbp, rcx
0x14000ac17  shr     r9, 20h
0x14000ac1b  lea     rcx, [rsp+98h+var_60]
0x14000ac20  mov     esi, r8d
0x14000ac23  call    wil_details_FeatureReporting_RecordUsageInCache
0x14000ac28  mov     r14d, 1
0x14000ac2e  movups  xmm1, xmmword ptr [rax]
0x14000ac31  movups  [rsp+98h+var_48], xmm1
0x14000ac36  movsd   xmm0, qword ptr [rax+10h]
0x14000ac3b  mov     rax, cs:g_wil_details_recordFeatureUsage
0x14000ac42  movsd   [rsp+98h+var_38], xmm0
0x14000ac48  test    rax, rax
0x14000ac4b  jz      short loc_14000AC68
0x14000ac4d  mov     r9, [rbp+8]
0x14000ac51  lea     rcx, [rsp+98h+var_48]
0x14000ac56  mov     [rsp+98h+var_78], rcx
0x14000ac5b  mov     r8d, r14d
0x14000ac5e  mov     ecx, [rbp+18h]
0x14000ac61  mov     edx, esi
0x14000ac63  call    _guard_dispatch_icall
0x14000ac68  bt      ebx, 0Ah
0x14000ac6c  jnb     short loc_14000ACA8
0x14000ac6e  cmp     esi, 0FEh
0x14000ac74  jz      short loc_14000ACA8
0x14000ac76  mov     eax, [rbp+18h]
0x14000ac79  mov     [rsp+98h+var_68], 0
0x14000ac82  mov     dword ptr [rsp+98h+var_68], eax
0x14000ac86  mov     word ptr [rsp+98h+var_68+4], si
0x14000ac8b  bt      ebx, 0Bh
0x14000ac8f  jnb     short loc_14000AC97
0x14000ac91  or      word ptr [rsp+98h+var_68+6], r14w
0x14000ac97  lea     rcx, [rsp+98h+var_68]
0x14000ac9c  call    cs:__imp_RtlNotifyFeatureUsage
0x14000aca3  nop     dword ptr [rax+rax+00h]
0x14000aca8  xor     eax, eax
0x14000acaa  cmp     dword ptr [rsp+98h+var_38], eax
0x14000acae  setz    al
0x14000acb1  mov     rcx, [rsp+98h+var_30]
0x14000acb6  xor     rcx, rsp; StackCookie
0x14000acb9  call    __security_check_cookie
0x14000acbe  add     rsp, 70h
0x14000acc2  pop     r14
0x14000acc4  pop     rdi
0x14000acc5  pop     rsi
0x14000acc6  pop     rbp
0x14000acc7  pop     rbx
0x14000acc8  retn
```

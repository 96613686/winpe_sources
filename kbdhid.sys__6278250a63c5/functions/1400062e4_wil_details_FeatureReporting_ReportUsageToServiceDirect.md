# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x1400062e4`
- end: `0x1400063cd`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140006268`

## callees

- `0x1400060e4`
- `0x1400062e4`
- `0x140007130`
- `0x140007170`

## import_xrefs

- `ntoskrnl!RtlNotifyFeatureUsage` at `0x140006398`
- `ntoskrnl!RtlNotifyFeatureUsage` at `0x140006398`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, unsigned int a3)
{
  __int16 v3; // bx
  int *v5; // rax
  __int64 v7; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v8[24]; // [rsp+38h] [rbp-40h] BYREF
  __int128 v9; // [rsp+50h] [rbp-28h] BYREF
  __int64 v10; // [rsp+60h] [rbp-18h]

  v3 = a2;
  v5 = wil_details_FeatureReporting_RecordUsageInCache(
         (__int64)v8,
         (volatile signed __int32 *)&Feature_DefaultCrashHotKey__private_reporting,
         a3,
         SHIDWORD(a2));
  v9 = *(_OWORD *)v5;
  v10 = *((_QWORD *)v5 + 2);
  if ( g_wil_details_recordFeatureUsage )
    g_wil_details_recordFeatureUsage(24586078, a3, 1, &Feature_DefaultCrashHotKey__private_reporting, &v9);
  if ( (v3 & 0x400) != 0 && a3 != 254 )
  {
    v7 = 24586078;
    WORD2(v7) = a3;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v7) |= 1u;
    RtlNotifyFeatureUsage(&v7);
  }
  return (_DWORD)v10 == 0;
}

```

## disassembly

```asm
0x1400062e4  mov     [rsp+arg_0], rbx
0x1400062e9  mov     [rsp+arg_18], rsi
0x1400062ee  push    rdi
0x1400062ef  sub     rsp, 70h
0x1400062f3  mov     rax, cs:__security_cookie
0x1400062fa  xor     rax, rsp
0x1400062fd  mov     [rsp+78h+var_10], rax
0x140006302  mov     r9, rdx
0x140006305  lea     rcx, [rsp+78h+var_40]
0x14000630a  mov     rbx, rdx
0x14000630d  shr     r9, 20h
0x140006311  mov     rdx, cs:off_14000A2A0
0x140006318  mov     edi, r8d
0x14000631b  call    wil_details_FeatureReporting_RecordUsageInCache
0x140006320  mov     esi, 1
0x140006325  movups  xmm1, xmmword ptr [rax]
0x140006328  movups  [rsp+78h+var_28], xmm1
0x14000632d  movsd   xmm0, qword ptr [rax+10h]
0x140006332  mov     rax, cs:g_wil_details_recordFeatureUsage
0x140006339  movsd   [rsp+78h+var_18], xmm0
0x14000633f  test    rax, rax
0x140006342  jz      short loc_140006364
0x140006344  mov     r9, cs:off_14000A2A0
0x14000634b  lea     rcx, [rsp+78h+var_28]
0x140006350  mov     [rsp+78h+var_58], rcx
0x140006355  mov     r8d, esi
0x140006358  mov     ecx, 177275Eh
0x14000635d  mov     edx, edi
0x14000635f  call    _guard_dispatch_icall
0x140006364  bt      ebx, 0Ah
0x140006368  jnb     short loc_1400063A4
0x14000636a  cmp     edi, 0FEh
0x140006370  jz      short loc_1400063A4
0x140006372  mov     [rsp+78h+var_48], 0
0x14000637b  mov     dword ptr [rsp+78h+var_48], 177275Eh
0x140006383  mov     word ptr [rsp+78h+var_48+4], di
0x140006388  bt      ebx, 0Bh
0x14000638c  jnb     short loc_140006393
0x14000638e  or      word ptr [rsp+78h+var_48+6], si
0x140006393  lea     rcx, [rsp+78h+var_48]
0x140006398  call    cs:__imp_RtlNotifyFeatureUsage
0x14000639f  nop     dword ptr [rax+rax+00h]
0x1400063a4  xor     eax, eax
0x1400063a6  cmp     dword ptr [rsp+78h+var_18], eax
0x1400063aa  setz    al
0x1400063ad  mov     rcx, [rsp+78h+var_10]
0x1400063b2  xor     rcx, rsp; StackCookie
0x1400063b5  call    __security_check_cookie
0x1400063ba  lea     r11, [rsp+78h+var_8]
0x1400063bf  mov     rbx, [r11+10h]
0x1400063c3  mov     rsi, [r11+28h]
0x1400063c7  mov     rsp, r11
0x1400063ca  pop     rdi
0x1400063cb  retn
```

# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x18000efe0`
- end: `0x18000f0c9`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x18000ef64`

## callees

- `0x18000ede0`
- `0x18000efe0`
- `0x1800108a0`
- `0x180010980`

## import_xrefs

- `ntoskrnl!RtlNotifyFeatureUsage` at `0x18000f094`
- `ntoskrnl!RtlNotifyFeatureUsage` at `0x18000f094`

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
         (volatile signed __int32 *)&Feature_Schannel_SslCopyTlsExtensions__private_reporting,
         a3,
         SHIDWORD(a2));
  v9 = *(_OWORD *)v5;
  v10 = *((_QWORD *)v5 + 2);
  if ( g_wil_details_recordFeatureUsage )
    g_wil_details_recordFeatureUsage(53571081, a3, 1, &Feature_Schannel_SslCopyTlsExtensions__private_reporting, &v9);
  if ( (v3 & 0x400) != 0 && a3 != 254 )
  {
    v7 = 53571081;
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
0x18000efe0  mov     [rsp+arg_0], rbx
0x18000efe5  mov     [rsp+arg_18], rsi
0x18000efea  push    rdi
0x18000efeb  sub     rsp, 70h
0x18000efef  mov     rax, cs:__security_cookie
0x18000eff6  xor     rax, rsp
0x18000eff9  mov     [rsp+78h+var_10], rax
0x18000effe  mov     r9, rdx
0x18000f001  lea     rcx, [rsp+78h+var_40]
0x18000f006  mov     rbx, rdx
0x18000f009  shr     r9, 20h
0x18000f00d  mov     rdx, cs:off_180018DA8
0x18000f014  mov     edi, r8d
0x18000f017  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000f01c  mov     esi, 1
0x18000f021  movups  xmm1, xmmword ptr [rax]
0x18000f024  movups  [rsp+78h+var_28], xmm1
0x18000f029  movsd   xmm0, qword ptr [rax+10h]
0x18000f02e  mov     rax, cs:g_wil_details_recordFeatureUsage
0x18000f035  movsd   [rsp+78h+var_18], xmm0
0x18000f03b  test    rax, rax
0x18000f03e  jz      short loc_18000F060
0x18000f040  mov     r9, cs:off_180018DA8
0x18000f047  lea     rcx, [rsp+78h+var_28]
0x18000f04c  mov     [rsp+78h+var_58], rcx
0x18000f051  mov     r8d, esi
0x18000f054  mov     ecx, 3316E09h
0x18000f059  mov     edx, edi
0x18000f05b  call    _guard_dispatch_icall
0x18000f060  bt      ebx, 0Ah
0x18000f064  jnb     short loc_18000F0A0
0x18000f066  cmp     edi, 0FEh
0x18000f06c  jz      short loc_18000F0A0
0x18000f06e  mov     [rsp+78h+var_48], 0
0x18000f077  mov     dword ptr [rsp+78h+var_48], 3316E09h
0x18000f07f  mov     word ptr [rsp+78h+var_48+4], di
0x18000f084  bt      ebx, 0Bh
0x18000f088  jnb     short loc_18000F08F
0x18000f08a  or      word ptr [rsp+78h+var_48+6], si
0x18000f08f  lea     rcx, [rsp+78h+var_48]
0x18000f094  call    cs:__imp_RtlNotifyFeatureUsage
0x18000f09b  nop     dword ptr [rax+rax+00h]
0x18000f0a0  xor     eax, eax
0x18000f0a2  cmp     dword ptr [rsp+78h+var_18], eax
0x18000f0a6  setz    al
0x18000f0a9  mov     rcx, [rsp+78h+var_10]
0x18000f0ae  xor     rcx, rsp; StackCookie
0x18000f0b1  call    __security_check_cookie
0x18000f0b6  lea     r11, [rsp+78h+var_8]
0x18000f0bb  mov     rbx, [r11+10h]
0x18000f0bf  mov     rsi, [r11+28h]
0x18000f0c3  mov     rsp, r11
0x18000f0c6  pop     rdi
0x18000f0c7  retn
```

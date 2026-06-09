# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x18000ef40`
- end: `0x18000f029`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x18000eec4`

## callees

- `0x18000ed40`
- `0x18000ef40`
- `0x180010840`
- `0x180010920`

## import_xrefs

- `ntoskrnl!RtlNotifyFeatureUsage` at `0x18000eff4`
- `ntoskrnl!RtlNotifyFeatureUsage` at `0x18000eff4`

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
0x18000ef40  mov     [rsp+arg_0], rbx
0x18000ef45  mov     [rsp+arg_18], rsi
0x18000ef4a  push    rdi
0x18000ef4b  sub     rsp, 70h
0x18000ef4f  mov     rax, cs:__security_cookie
0x18000ef56  xor     rax, rsp
0x18000ef59  mov     [rsp+78h+var_10], rax
0x18000ef5e  mov     r9, rdx
0x18000ef61  lea     rcx, [rsp+78h+var_40]
0x18000ef66  mov     rbx, rdx
0x18000ef69  shr     r9, 20h
0x18000ef6d  mov     rdx, cs:off_180018D88
0x18000ef74  mov     edi, r8d
0x18000ef77  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000ef7c  mov     esi, 1
0x18000ef81  movups  xmm1, xmmword ptr [rax]
0x18000ef84  movups  [rsp+78h+var_28], xmm1
0x18000ef89  movsd   xmm0, qword ptr [rax+10h]
0x18000ef8e  mov     rax, cs:g_wil_details_recordFeatureUsage
0x18000ef95  movsd   [rsp+78h+var_18], xmm0
0x18000ef9b  test    rax, rax
0x18000ef9e  jz      short loc_18000EFC0
0x18000efa0  mov     r9, cs:off_180018D88
0x18000efa7  lea     rcx, [rsp+78h+var_28]
0x18000efac  mov     [rsp+78h+var_58], rcx
0x18000efb1  mov     r8d, esi
0x18000efb4  mov     ecx, 3316E09h
0x18000efb9  mov     edx, edi
0x18000efbb  call    _guard_dispatch_icall
0x18000efc0  bt      ebx, 0Ah
0x18000efc4  jnb     short loc_18000F000
0x18000efc6  cmp     edi, 0FEh
0x18000efcc  jz      short loc_18000F000
0x18000efce  mov     [rsp+78h+var_48], 0
0x18000efd7  mov     dword ptr [rsp+78h+var_48], 3316E09h
0x18000efdf  mov     word ptr [rsp+78h+var_48+4], di
0x18000efe4  bt      ebx, 0Bh
0x18000efe8  jnb     short loc_18000EFEF
0x18000efea  or      word ptr [rsp+78h+var_48+6], si
0x18000efef  lea     rcx, [rsp+78h+var_48]
0x18000eff4  call    cs:__imp_RtlNotifyFeatureUsage
0x18000effb  nop     dword ptr [rax+rax+00h]
0x18000f000  xor     eax, eax
0x18000f002  cmp     dword ptr [rsp+78h+var_18], eax
0x18000f006  setz    al
0x18000f009  mov     rcx, [rsp+78h+var_10]
0x18000f00e  xor     rcx, rsp; StackCookie
0x18000f011  call    __security_check_cookie
0x18000f016  lea     r11, [rsp+78h+var_8]
0x18000f01b  mov     rbx, [r11+10h]
0x18000f01f  mov     rsi, [r11+28h]
0x18000f023  mov     rsp, r11
0x18000f026  pop     rdi
0x18000f027  retn
```

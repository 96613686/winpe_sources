# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x14000afe8`
- end: `0x14000b0d1`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14000af6c`

## callees

- `0x14000ade8`
- `0x14000afe8`
- `0x14000da60`
- `0x14000daa0`

## import_xrefs

- `ntoskrnl!RtlNotifyFeatureUsage` at `0x14000b09c`
- `ntoskrnl!RtlNotifyFeatureUsage` at `0x14000b09c`

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
0x14000afe8  mov     [rsp+arg_0], rbx
0x14000afed  mov     [rsp+arg_18], rsi
0x14000aff2  push    rdi
0x14000aff3  sub     rsp, 70h
0x14000aff7  mov     rax, cs:__security_cookie
0x14000affe  xor     rax, rsp
0x14000b001  mov     [rsp+78h+var_10], rax
0x14000b006  mov     r9, rdx
0x14000b009  lea     rcx, [rsp+78h+var_40]
0x14000b00e  mov     rbx, rdx
0x14000b011  shr     r9, 20h
0x14000b015  mov     rdx, cs:off_140012468
0x14000b01c  mov     edi, r8d
0x14000b01f  call    wil_details_FeatureReporting_RecordUsageInCache
0x14000b024  mov     esi, 1
0x14000b029  movups  xmm1, xmmword ptr [rax]
0x14000b02c  movups  [rsp+78h+var_28], xmm1
0x14000b031  movsd   xmm0, qword ptr [rax+10h]
0x14000b036  mov     rax, cs:g_wil_details_recordFeatureUsage
0x14000b03d  movsd   [rsp+78h+var_18], xmm0
0x14000b043  test    rax, rax
0x14000b046  jz      short loc_14000B068
0x14000b048  mov     r9, cs:off_140012468
0x14000b04f  lea     rcx, [rsp+78h+var_28]
0x14000b054  mov     [rsp+78h+var_58], rcx
0x14000b059  mov     r8d, esi
0x14000b05c  mov     ecx, 177275Eh
0x14000b061  mov     edx, edi
0x14000b063  call    _guard_dispatch_icall
0x14000b068  bt      ebx, 0Ah
0x14000b06c  jnb     short loc_14000B0A8
0x14000b06e  cmp     edi, 0FEh
0x14000b074  jz      short loc_14000B0A8
0x14000b076  mov     [rsp+78h+var_48], 0
0x14000b07f  mov     dword ptr [rsp+78h+var_48], 177275Eh
0x14000b087  mov     word ptr [rsp+78h+var_48+4], di
0x14000b08c  bt      ebx, 0Bh
0x14000b090  jnb     short loc_14000B097
0x14000b092  or      word ptr [rsp+78h+var_48+6], si
0x14000b097  lea     rcx, [rsp+78h+var_48]
0x14000b09c  call    cs:__imp_RtlNotifyFeatureUsage
0x14000b0a3  nop     dword ptr [rax+rax+00h]
0x14000b0a8  xor     eax, eax
0x14000b0aa  cmp     dword ptr [rsp+78h+var_18], eax
0x14000b0ae  setz    al
0x14000b0b1  mov     rcx, [rsp+78h+var_10]
0x14000b0b6  xor     rcx, rsp; StackCookie
0x14000b0b9  call    __security_check_cookie
0x14000b0be  lea     r11, [rsp+78h+var_8]
0x14000b0c3  mov     rbx, [r11+10h]
0x14000b0c7  mov     rsi, [r11+28h]
0x14000b0cb  mov     rsp, r11
0x14000b0ce  pop     rdi
0x14000b0cf  retn
```

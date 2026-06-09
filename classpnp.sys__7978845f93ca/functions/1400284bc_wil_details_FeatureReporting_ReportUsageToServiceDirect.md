# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x1400284bc`
- end: `0x1400285a5`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140028440`

## callees

- `0x1400282bc`
- `0x1400284bc`
- `0x14003e430`
- `0x14003e470`

## import_xrefs

- `ntoskrnl!RtlNotifyFeatureUsage` at `0x140028570`
- `ntoskrnl!RtlNotifyFeatureUsage` at `0x140028570`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, unsigned int a3)
{
  __int16 v3; // bx
  _DWORD *v5; // rax
  __int64 v7; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v8[24]; // [rsp+38h] [rbp-40h] BYREF
  __int128 v9; // [rsp+50h] [rbp-28h] BYREF
  __int64 v10; // [rsp+60h] [rbp-18h]

  v3 = a2;
  v5 = wil_details_FeatureReporting_RecordUsageInCache(
         (__int64)v8,
         (volatile signed __int32 *)&Feature_SteelixInlineNvmeCryptoEngine__private_reporting,
         a3,
         SHIDWORD(a2));
  v9 = *(_OWORD *)v5;
  v10 = *((_QWORD *)v5 + 2);
  if ( g_wil_details_recordFeatureUsage )
    g_wil_details_recordFeatureUsage(48799070, a3, 1, &Feature_SteelixInlineNvmeCryptoEngine__private_reporting, &v9);
  if ( (v3 & 0x400) != 0 && a3 != 254 )
  {
    v7 = 48799070;
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
0x1400284bc  mov     [rsp+arg_0], rbx
0x1400284c1  mov     [rsp+arg_18], rsi
0x1400284c6  push    rdi
0x1400284c7  sub     rsp, 70h
0x1400284cb  mov     rax, cs:__security_cookie
0x1400284d2  xor     rax, rsp
0x1400284d5  mov     [rsp+78h+var_10], rax
0x1400284da  mov     r9, rdx
0x1400284dd  lea     rcx, [rsp+78h+var_40]
0x1400284e2  mov     rbx, rdx
0x1400284e5  shr     r9, 20h
0x1400284e9  mov     rdx, cs:off_14004CF40
0x1400284f0  mov     edi, r8d
0x1400284f3  call    wil_details_FeatureReporting_RecordUsageInCache
0x1400284f8  mov     esi, 1
0x1400284fd  movups  xmm1, xmmword ptr [rax]
0x140028500  movups  [rsp+78h+var_28], xmm1
0x140028505  movsd   xmm0, qword ptr [rax+10h]
0x14002850a  mov     rax, cs:g_wil_details_recordFeatureUsage
0x140028511  movsd   [rsp+78h+var_18], xmm0
0x140028517  test    rax, rax
0x14002851a  jz      short loc_14002853C
0x14002851c  mov     r9, cs:off_14004CF40
0x140028523  lea     rcx, [rsp+78h+var_28]
0x140028528  mov     [rsp+78h+var_58], rcx
0x14002852d  mov     r8d, esi
0x140028530  mov     ecx, 2E89D5Eh
0x140028535  mov     edx, edi
0x140028537  call    _guard_dispatch_icall
0x14002853c  bt      ebx, 0Ah
0x140028540  jnb     short loc_14002857C
0x140028542  cmp     edi, 0FEh
0x140028548  jz      short loc_14002857C
0x14002854a  mov     [rsp+78h+var_48], 0
0x140028553  mov     dword ptr [rsp+78h+var_48], 2E89D5Eh
0x14002855b  mov     word ptr [rsp+78h+var_48+4], di
0x140028560  bt      ebx, 0Bh
0x140028564  jnb     short loc_14002856B
0x140028566  or      word ptr [rsp+78h+var_48+6], si
0x14002856b  lea     rcx, [rsp+78h+var_48]
0x140028570  call    cs:__imp_RtlNotifyFeatureUsage
0x140028577  nop     dword ptr [rax+rax+00h]
0x14002857c  xor     eax, eax
0x14002857e  cmp     dword ptr [rsp+78h+var_18], eax
0x140028582  setz    al
0x140028585  mov     rcx, [rsp+78h+var_10]
0x14002858a  xor     rcx, rsp; StackCookie
0x14002858d  call    __security_check_cookie
0x140028592  lea     r11, [rsp+78h+var_8]
0x140028597  mov     rbx, [r11+10h]
0x14002859b  mov     rsi, [r11+28h]
0x14002859f  mov     rsp, r11
0x1400285a2  pop     rdi
0x1400285a3  retn
```

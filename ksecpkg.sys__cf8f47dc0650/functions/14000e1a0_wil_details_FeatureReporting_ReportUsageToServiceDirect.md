# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x14000e1a0`
- end: `0x14000e289`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14000e120`

## callees

- `0x14000df9c`
- `0x14000e1a0`
- `0x140010160`
- `0x140010240`

## import_xrefs

- `ntoskrnl!RtlNotifyFeatureUsage` at `0x14000e254`
- `ntoskrnl!RtlNotifyFeatureUsage` at `0x14000e254`

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
         (volatile signed __int32 *)&Feature_NegoexPassesStructuredExceptions__private_reporting,
         a3,
         SHIDWORD(a2));
  v9 = *(_OWORD *)v5;
  v10 = *((_QWORD *)v5 + 2);
  if ( g_wil_details_recordFeatureUsage )
    g_wil_details_recordFeatureUsage(29204454, a3, 1, &Feature_NegoexPassesStructuredExceptions__private_reporting, &v9);
  if ( (v3 & 0x400) != 0 && a3 != 254 )
  {
    v7 = 29204454;
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
0x14000e1a0  mov     [rsp+arg_0], rbx
0x14000e1a5  mov     [rsp+arg_18], rsi
0x14000e1aa  push    rdi
0x14000e1ab  sub     rsp, 70h
0x14000e1af  mov     rax, cs:__security_cookie
0x14000e1b6  xor     rax, rsp
0x14000e1b9  mov     [rsp+78h+var_10], rax
0x14000e1be  mov     r9, rdx
0x14000e1c1  lea     rcx, [rsp+78h+var_40]
0x14000e1c6  mov     rbx, rdx
0x14000e1c9  shr     r9, 20h
0x14000e1cd  mov     rdx, cs:off_140017890
0x14000e1d4  mov     edi, r8d
0x14000e1d7  call    wil_details_FeatureReporting_RecordUsageInCache
0x14000e1dc  mov     esi, 1
0x14000e1e1  movups  xmm1, xmmword ptr [rax]
0x14000e1e4  movups  [rsp+78h+var_28], xmm1
0x14000e1e9  movsd   xmm0, qword ptr [rax+10h]
0x14000e1ee  mov     rax, cs:g_wil_details_recordFeatureUsage
0x14000e1f5  movsd   [rsp+78h+var_18], xmm0
0x14000e1fb  test    rax, rax
0x14000e1fe  jz      short loc_14000E220
0x14000e200  mov     r9, cs:off_140017890
0x14000e207  lea     rcx, [rsp+78h+var_28]
0x14000e20c  mov     [rsp+78h+var_58], rcx
0x14000e211  mov     r8d, esi
0x14000e214  mov     ecx, 1BD9FE6h
0x14000e219  mov     edx, edi
0x14000e21b  call    _guard_dispatch_icall
0x14000e220  bt      ebx, 0Ah
0x14000e224  jnb     short loc_14000E260
0x14000e226  cmp     edi, 0FEh
0x14000e22c  jz      short loc_14000E260
0x14000e22e  mov     [rsp+78h+var_48], 0
0x14000e237  mov     dword ptr [rsp+78h+var_48], 1BD9FE6h
0x14000e23f  mov     word ptr [rsp+78h+var_48+4], di
0x14000e244  bt      ebx, 0Bh
0x14000e248  jnb     short loc_14000E24F
0x14000e24a  or      word ptr [rsp+78h+var_48+6], si
0x14000e24f  lea     rcx, [rsp+78h+var_48]
0x14000e254  call    cs:__imp_RtlNotifyFeatureUsage
0x14000e25b  nop     dword ptr [rax+rax+00h]
0x14000e260  xor     eax, eax
0x14000e262  cmp     dword ptr [rsp+78h+var_18], eax
0x14000e266  setz    al
0x14000e269  mov     rcx, [rsp+78h+var_10]
0x14000e26e  xor     rcx, rsp; StackCookie
0x14000e271  call    __security_check_cookie
0x14000e276  lea     r11, [rsp+78h+var_8]
0x14000e27b  mov     rbx, [r11+10h]
0x14000e27f  mov     rsi, [r11+28h]
0x14000e283  mov     rsp, r11
0x14000e286  pop     rdi
0x14000e287  retn
```

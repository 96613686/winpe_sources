# wil::details_abi::UsageIndexes::Record(void)

- ea: `0x18000ac2c`
- end: `0x18000ad31`
- name: `?Record@UsageIndexes@details_abi@wil@@QEAAXXZ`
- size: `261`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000824c`
- `0x18000af30`
- `0x18000b9f4`

## callees

- `0x18000ac2c`
- `0x18000b500`
- `0x180015cf0`

## pseudocode

```c
void __fastcall wil::details_abi::UsageIndexes::Record(
        wil::details_abi::UsageIndexes *this,
        __int64 a2,
        __int64 a3,
        const struct wil::details_abi::RawUsageIndex *a4)
{
  __int64 v5; // [rsp+20h] [rbp-40h] BYREF
  __int64 v6; // [rsp+28h] [rbp-38h]
  __int64 v7; // [rsp+30h] [rbp-30h]
  __int64 v8; // [rsp+38h] [rbp-28h]
  __int64 v9; // [rsp+40h] [rbp-20h]
  __int64 v10; // [rsp+48h] [rbp-18h]

  if ( *((_BYTE *)this + 56) )
  {
    v5 = __WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_1;
    v6 = __WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_2;
    v7 = __WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_3;
    wil::details_abi::RecordWnfUsageIndex(
      (wil::details_abi *)&v5,
      (const struct __WIL__WNF_STATE_NAME *)3,
      (__int64)this,
      a4);
  }
  if ( *((_BYTE *)this + 120) )
  {
    v5 = __WIL_WNF_WIL_FEATURE_USAGE_TRACKING_1;
    v6 = __WIL_WNF_WIL_FEATURE_USAGE_TRACKING_2;
    v7 = __WIL_WNF_WIL_FEATURE_USAGE_TRACKING_3;
    wil::details_abi::RecordWnfUsageIndex(
      (wil::details_abi *)&v5,
      (const struct __WIL__WNF_STATE_NAME *)3,
      (__int64)this + 64,
      a4);
  }
  if ( *((_BYTE *)this + 184) )
  {
    v5 = __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_1;
    v6 = __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_2;
    v7 = __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_3;
    v8 = __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_4;
    v9 = __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_5;
    v10 = __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_6;
    wil::details_abi::RecordWnfUsageIndex(
      (wil::details_abi *)&v5,
      (const struct __WIL__WNF_STATE_NAME *)6,
      (__int64)this + 128,
      a4);
  }
}

```

## disassembly

```asm
0x18000ac2c  mov     [rsp-8+arg_8], rbx
0x18000ac31  push    rbp
0x18000ac32  mov     rbp, rsp
0x18000ac35  sub     rsp, 60h
0x18000ac39  mov     rax, cs:__security_cookie
0x18000ac40  xor     rax, rsp
0x18000ac43  mov     [rbp+var_10], rax
0x18000ac47  cmp     byte ptr [rcx+38h], 0
0x18000ac4b  mov     rbx, rcx
0x18000ac4e  jz      short loc_18000AC82
0x18000ac50  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_1@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_1
0x18000ac57  mov     r8, rcx; unsigned __int64
0x18000ac5a  mov     [rbp+var_40], rax
0x18000ac5e  lea     rcx, [rbp+var_40]; this
0x18000ac62  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_2@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_2
0x18000ac69  mov     edx, 3; struct __WIL__WNF_STATE_NAME *
0x18000ac6e  mov     [rbp+var_38], rax
0x18000ac72  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_3@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_3
0x18000ac79  mov     [rbp+var_30], rax
0x18000ac7d  call    ?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z; wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)
0x18000ac82  lea     r8, [rbx+40h]; unsigned __int64
0x18000ac86  cmp     byte ptr [r8+38h], 0
0x18000ac8b  jz      short loc_18000ACBC
0x18000ac8d  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_USAGE_TRACKING_1@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_TRACKING_1
0x18000ac94  lea     rcx, [rbp+var_40]; this
0x18000ac98  mov     [rbp+var_40], rax
0x18000ac9c  mov     edx, 3; struct __WIL__WNF_STATE_NAME *
0x18000aca1  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_USAGE_TRACKING_2@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_TRACKING_2
0x18000aca8  mov     [rbp+var_38], rax
0x18000acac  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_USAGE_TRACKING_3@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_TRACKING_3
0x18000acb3  mov     [rbp+var_30], rax
0x18000acb7  call    ?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z; wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)
0x18000acbc  lea     r8, [rbx+80h]; unsigned __int64
0x18000acc3  cmp     byte ptr [r8+38h], 0
0x18000acc8  jz      short loc_18000AD1A
0x18000acca  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_1@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_1
0x18000acd1  lea     rcx, [rbp+var_40]; this
0x18000acd5  mov     [rbp+var_40], rax
0x18000acd9  mov     edx, 6; struct __WIL__WNF_STATE_NAME *
0x18000acde  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_2@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_2
0x18000ace5  mov     [rbp+var_38], rax
0x18000ace9  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_3@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_3
0x18000acf0  mov     [rbp+var_30], rax
0x18000acf4  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_4@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_4
0x18000acfb  mov     [rbp+var_28], rax
0x18000acff  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_5@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_5
0x18000ad06  mov     [rbp+var_20], rax
0x18000ad0a  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_6@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_6
0x18000ad11  mov     [rbp+var_18], rax
0x18000ad15  call    ?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z; wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)
0x18000ad1a  mov     rcx, [rbp+var_10]
0x18000ad1e  xor     rcx, rsp; StackCookie
0x18000ad21  call    __security_check_cookie
0x18000ad26  mov     rbx, [rsp+60h+arg_8]
0x18000ad2b  add     rsp, 60h
0x18000ad2f  pop     rbp
0x18000ad30  retn
```

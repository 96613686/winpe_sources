# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x18000ff88`
- end: `0x18000fff2`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000ff0c`

## callees

- `0x18000fadc`
- `0x18000fd88`
- `0x18000ff88`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned int v3; // ebx
  int v5; // esi
  _BYTE v7[40]; // [rsp+30h] [rbp-28h] BYREF

  v3 = a2;
  v5 = wil_details_FeatureReporting_RecordUsageInCache(
         (__int64)v7,
         (volatile signed __int32 *)&Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__private_reporting,
         a3,
         SHIDWORD(a2))[4];
  if ( (v3 & 0x400) != 0 && a3 != 254 )
    wil_RtlStagingConfig_RecordFeatureUsage(52061724, a3, (v3 >> 11) & 1);
  return v5 == 0;
}

```

## disassembly

```asm
0x18000ff88  mov     [rsp+arg_0], rbx
0x18000ff8d  mov     [rsp+arg_18], rsi
0x18000ff92  push    rdi
0x18000ff93  sub     rsp, 50h
0x18000ff97  mov     r9, rdx
0x18000ff9a  lea     rcx, [rsp+58h+var_28]
0x18000ff9f  mov     rbx, rdx
0x18000ffa2  shr     r9, 20h
0x18000ffa6  mov     rdx, cs:off_180023438
0x18000ffad  mov     edi, r8d
0x18000ffb0  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000ffb5  mov     esi, [rax+10h]
0x18000ffb8  bt      ebx, 0Ah
0x18000ffbc  jnb     short loc_18000FFDB
0x18000ffbe  cmp     edi, 0FEh
0x18000ffc4  jz      short loc_18000FFDB
0x18000ffc6  shr     ebx, 0Bh
0x18000ffc9  mov     edx, edi
0x18000ffcb  and     ebx, 1
0x18000ffce  mov     ecx, 31A661Ch
0x18000ffd3  mov     r8d, ebx
0x18000ffd6  call    wil_RtlStagingConfig_RecordFeatureUsage
0x18000ffdb  mov     rbx, [rsp+58h+arg_0]
0x18000ffe0  xor     eax, eax
0x18000ffe2  test    esi, esi
0x18000ffe4  mov     rsi, [rsp+58h+arg_18]
0x18000ffe9  setz    al
0x18000ffec  add     rsp, 50h
0x18000fff0  pop     rdi
0x18000fff1  retn
```

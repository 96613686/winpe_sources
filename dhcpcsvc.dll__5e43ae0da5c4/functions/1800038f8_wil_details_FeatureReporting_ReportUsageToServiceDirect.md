# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x1800038f8`
- end: `0x18000395d`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800037dc`

## callees

- `0x1800038f8`
- `0x180003964`
- `0x1800105e0`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned int v3; // ebx
  int v6; // esi
  _BYTE v8[56]; // [rsp+30h] [rbp-38h] BYREF

  v3 = a2;
  v6 = wil_details_FeatureReporting_RecordUsageInCache(
         (__int64)v8,
         *(volatile signed __int32 **)(a1 + 8),
         a3,
         SHIDWORD(a2))[4];
  if ( (v3 & 0x400) != 0 && a3 != 254 )
    wil_RtlStagingConfig_RecordFeatureUsage(*(unsigned int *)(a1 + 24), a3, (v3 >> 11) & 1);
  return v6 == 0;
}

```

## disassembly

```asm
0x1800038f8  mov     [rsp+arg_18], rbx
0x1800038fd  push    rbp
0x1800038fe  push    rsi
0x1800038ff  push    rdi
0x180003900  sub     rsp, 50h
0x180003904  mov     r9, rdx
0x180003907  mov     rbx, rdx
0x18000390a  mov     rdx, [rcx+8]
0x18000390e  mov     rbp, rcx
0x180003911  shr     r9, 20h
0x180003915  lea     rcx, [rsp+68h+var_38]
0x18000391a  mov     edi, r8d
0x18000391d  call    wil_details_FeatureReporting_RecordUsageInCache
0x180003922  mov     esi, [rax+10h]
0x180003925  bt      ebx, 0Ah
0x180003929  jnb     short loc_180003946
0x18000392b  cmp     edi, 0FEh
0x180003931  jz      short loc_180003946
0x180003933  mov     ecx, [rbp+18h]
0x180003936  mov     edx, edi
0x180003938  shr     ebx, 0Bh
0x18000393b  and     ebx, 1
0x18000393e  mov     r8d, ebx
0x180003941  call    wil_RtlStagingConfig_RecordFeatureUsage
0x180003946  mov     rbx, [rsp+68h+arg_18]
0x18000394e  xor     eax, eax
0x180003950  test    esi, esi
0x180003952  setz    al
0x180003955  add     rsp, 50h
0x180003959  pop     rdi
0x18000395a  pop     rsi
0x18000395b  pop     rbp
0x18000395c  retn
```

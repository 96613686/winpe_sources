# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x1800199e8`
- end: `0x180019a4d`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180016878`

## callees

- `0x1800169d8`
- `0x1800199e8`
- `0x18001ba18`

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
0x1800199e8  mov     [rsp+arg_18], rbx
0x1800199ed  push    rbp
0x1800199ee  push    rsi
0x1800199ef  push    rdi
0x1800199f0  sub     rsp, 50h
0x1800199f4  mov     r9, rdx
0x1800199f7  mov     rbx, rdx
0x1800199fa  mov     rdx, [rcx+8]
0x1800199fe  mov     rbp, rcx
0x180019a01  shr     r9, 20h
0x180019a05  lea     rcx, [rsp+68h+var_38]
0x180019a0a  mov     edi, r8d
0x180019a0d  call    wil_details_FeatureReporting_RecordUsageInCache
0x180019a12  mov     esi, [rax+10h]
0x180019a15  bt      ebx, 0Ah
0x180019a19  jnb     short loc_180019A36
0x180019a1b  cmp     edi, 0FEh
0x180019a21  jz      short loc_180019A36
0x180019a23  mov     ecx, [rbp+18h]
0x180019a26  mov     edx, edi
0x180019a28  shr     ebx, 0Bh
0x180019a2b  and     ebx, 1
0x180019a2e  mov     r8d, ebx
0x180019a31  call    wil_RtlStagingConfig_RecordFeatureUsage
0x180019a36  mov     rbx, [rsp+68h+arg_18]
0x180019a3e  xor     eax, eax
0x180019a40  test    esi, esi
0x180019a42  setz    al
0x180019a45  add     rsp, 50h
0x180019a49  pop     rdi
0x180019a4a  pop     rsi
0x180019a4b  pop     rbp
0x180019a4c  retn
```

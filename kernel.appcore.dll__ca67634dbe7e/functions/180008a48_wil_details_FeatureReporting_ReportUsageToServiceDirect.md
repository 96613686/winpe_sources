# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x180008a48`
- end: `0x180008aad`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000891c`

## callees

- `0x1800084ec`
- `0x180008798`
- `0x180008a48`

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
0x180008a48  mov     [rsp+arg_18], rbx
0x180008a4d  push    rbp
0x180008a4e  push    rsi
0x180008a4f  push    rdi
0x180008a50  sub     rsp, 50h
0x180008a54  mov     r9, rdx
0x180008a57  mov     rbx, rdx
0x180008a5a  mov     rdx, [rcx+8]
0x180008a5e  mov     rbp, rcx
0x180008a61  shr     r9, 20h
0x180008a65  lea     rcx, [rsp+68h+var_38]
0x180008a6a  mov     edi, r8d
0x180008a6d  call    wil_details_FeatureReporting_RecordUsageInCache
0x180008a72  mov     esi, [rax+10h]
0x180008a75  bt      ebx, 0Ah
0x180008a79  jnb     short loc_180008A96
0x180008a7b  cmp     edi, 0FEh
0x180008a81  jz      short loc_180008A96
0x180008a83  mov     ecx, [rbp+18h]
0x180008a86  mov     edx, edi
0x180008a88  shr     ebx, 0Bh
0x180008a8b  and     ebx, 1
0x180008a8e  mov     r8d, ebx
0x180008a91  call    wil_RtlStagingConfig_RecordFeatureUsage
0x180008a96  mov     rbx, [rsp+68h+arg_18]
0x180008a9e  xor     eax, eax
0x180008aa0  test    esi, esi
0x180008aa2  setz    al
0x180008aa5  add     rsp, 50h
0x180008aa9  pop     rdi
0x180008aaa  pop     rsi
0x180008aab  pop     rbp
0x180008aac  retn
```

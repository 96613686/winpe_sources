# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x1800185bc`
- end: `0x180018621`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180018534`

## callees

- `0x180018104`
- `0x1800183b0`
- `0x1800185bc`

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
    wil_RtlStagingConfig_RecordFeatureUsage(*(_DWORD *)(a1 + 24), a3, (v3 >> 11) & 1);
  return v6 == 0;
}

```

## disassembly

```asm
0x1800185bc  mov     [rsp+arg_18], rbx
0x1800185c1  push    rbp
0x1800185c2  push    rsi
0x1800185c3  push    rdi
0x1800185c4  sub     rsp, 50h
0x1800185c8  mov     r9, rdx
0x1800185cb  mov     rbx, rdx
0x1800185ce  mov     rdx, [rcx+8]
0x1800185d2  mov     rbp, rcx
0x1800185d5  shr     r9, 20h
0x1800185d9  lea     rcx, [rsp+68h+var_38]
0x1800185de  mov     edi, r8d
0x1800185e1  call    wil_details_FeatureReporting_RecordUsageInCache
0x1800185e6  mov     esi, [rax+10h]
0x1800185e9  bt      ebx, 0Ah
0x1800185ed  jnb     short loc_18001860A
0x1800185ef  cmp     edi, 0FEh
0x1800185f5  jz      short loc_18001860A
0x1800185f7  mov     ecx, [rbp+18h]
0x1800185fa  mov     edx, edi
0x1800185fc  shr     ebx, 0Bh
0x1800185ff  and     ebx, 1
0x180018602  mov     r8d, ebx
0x180018605  call    wil_RtlStagingConfig_RecordFeatureUsage
0x18001860a  mov     rbx, [rsp+68h+arg_18]
0x180018612  xor     eax, eax
0x180018614  test    esi, esi
0x180018616  setz    al
0x180018619  add     rsp, 50h
0x18001861d  pop     rdi
0x18001861e  pop     rsi
0x18001861f  pop     rbp
0x180018620  retn
```

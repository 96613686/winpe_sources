# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x18002339c`
- end: `0x1800233fe`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18002326c`

## callees

- `0x180022e44`
- `0x1800230d4`
- `0x18002339c`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4)
{
  unsigned int v4; // ebx
  int v7; // esi
  _BYTE v9[72]; // [rsp+30h] [rbp-48h] BYREF

  v4 = a2;
  v7 = wil_details_FeatureReporting_RecordUsageInCache(
         (__int64)v9,
         *(volatile signed __int32 **)(a1 + 8),
         a3,
         SHIDWORD(a2),
         a4)[4];
  if ( (v4 & 0x400) != 0 && a3 != 254 )
    wil_RtlStagingConfig_RecordFeatureUsage(*(_DWORD *)(a1 + 24), a3, (v4 >> 11) & 1);
  return v7 == 0;
}

```

## disassembly

```asm
0x18002339c  push    rbx
0x18002339e  push    rbp
0x18002339f  push    rsi
0x1800233a0  push    rdi
0x1800233a1  sub     rsp, 58h
0x1800233a5  mov     rax, r9
0x1800233a8  mov     rbx, rdx
0x1800233ab  mov     r9, rdx
0x1800233ae  mov     [rsp+78h+var_58], eax
0x1800233b2  mov     rdx, [rcx+8]
0x1800233b6  mov     rbp, rcx
0x1800233b9  shr     r9, 20h
0x1800233bd  lea     rcx, [rsp+78h+var_48]
0x1800233c2  mov     edi, r8d
0x1800233c5  call    wil_details_FeatureReporting_RecordUsageInCache
0x1800233ca  mov     esi, [rax+10h]
0x1800233cd  bt      ebx, 0Ah
0x1800233d1  jnb     short loc_1800233EE
0x1800233d3  cmp     edi, 0FEh
0x1800233d9  jz      short loc_1800233EE
0x1800233db  mov     ecx, [rbp+18h]
0x1800233de  mov     edx, edi
0x1800233e0  shr     ebx, 0Bh
0x1800233e3  and     ebx, 1
0x1800233e6  mov     r8d, ebx
0x1800233e9  call    wil_RtlStagingConfig_RecordFeatureUsage
0x1800233ee  xor     eax, eax
0x1800233f0  test    esi, esi
0x1800233f2  setz    al
0x1800233f5  add     rsp, 58h
0x1800233f9  pop     rdi
0x1800233fa  pop     rsi
0x1800233fb  pop     rbp
0x1800233fc  pop     rbx
0x1800233fd  retn
```

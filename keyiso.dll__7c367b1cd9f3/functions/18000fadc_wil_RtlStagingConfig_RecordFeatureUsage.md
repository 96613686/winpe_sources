# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x18000fadc`
- end: `0x18000fb36`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000ff88`
- `0x1800162f0`

## callees

- `0x18000fadc`
- `0x180010268`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_RecordFeatureUsage(int a1, __int16 a2, int a3)
{
  FARPROC NtDllProcedureAddress; // rax
  int v5; // [rsp+48h] [rbp+20h] BYREF
  __int16 v6; // [rsp+4Ch] [rbp+24h]
  __int16 v7; // [rsp+4Eh] [rbp+26h]

  v7 = 0;
  v5 = a1;
  v6 = a2;
  if ( a3 )
    v7 |= 1u;
  NtDllProcedureAddress = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
  if ( g_wil_details_pfnRtlNotifyFeatureUsage )
    return ((__int64 (__fastcall *)(int *))NtDllProcedureAddress)(&v5);
  NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlNotifyFeatureUsage");
  g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)NtDllProcedureAddress;
  if ( NtDllProcedureAddress )
    return ((__int64 (__fastcall *)(int *))NtDllProcedureAddress)(&v5);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x18000fadc  mov     rax, rsp
0x18000fadf  sub     rsp, 28h
0x18000fae3  mov     qword ptr [rax+20h], 0
0x18000faeb  mov     [rax+20h], ecx
0x18000faee  mov     [rax+24h], dx
0x18000faf2  test    r8d, r8d
0x18000faf5  jz      short loc_18000FAFC
0x18000faf7  or      word ptr [rax+26h], 1
0x18000fafc  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000fb03  test    rax, rax
0x18000fb06  jnz     short loc_18000FB27
0x18000fb08  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000fb0f  call    wil_details_GetNtDllProcedureAddress
0x18000fb14  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000fb1b  test    rax, rax
0x18000fb1e  jnz     short loc_18000FB27
0x18000fb20  mov     eax, 0C0000139h
0x18000fb25  jmp     short loc_18000FB31
0x18000fb27  lea     rcx, [rsp+28h+arg_18]
0x18000fb2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb31  add     rsp, 28h
0x18000fb35  retn
```

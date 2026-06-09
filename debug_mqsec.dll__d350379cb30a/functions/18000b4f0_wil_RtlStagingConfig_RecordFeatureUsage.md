# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x18000b4f0`
- end: `0x18000b54a`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a8b0`

## callees

- `0x18000b298`
- `0x18000b4f0`
- `0x180031010`

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
0x18000b4f0  mov     rax, rsp
0x18000b4f3  sub     rsp, 28h
0x18000b4f7  mov     qword ptr [rax+20h], 0
0x18000b4ff  mov     [rax+20h], ecx
0x18000b502  mov     [rax+24h], dx
0x18000b506  test    r8d, r8d
0x18000b509  jz      short loc_18000B510
0x18000b50b  or      word ptr [rax+26h], 1
0x18000b510  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000b517  test    rax, rax
0x18000b51a  jnz     short loc_18000B53B
0x18000b51c  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000b523  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000b528  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000b52f  test    rax, rax
0x18000b532  jnz     short loc_18000B53B
0x18000b534  mov     eax, 0C0000139h
0x18000b539  jmp     short loc_18000B545
0x18000b53b  lea     rcx, [rsp+28h+arg_18]
0x18000b540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b545  add     rsp, 28h
0x18000b549  retn
```

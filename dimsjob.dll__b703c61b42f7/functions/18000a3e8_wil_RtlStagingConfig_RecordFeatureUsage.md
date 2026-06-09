# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x18000a3e8`
- end: `0x18000a442`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: `__int64 __fastcall(int, __int16, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180009620`

## callees

- `0x18000a140`
- `0x18000a3e8`
- `0x18000c010`

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
0x18000a3e8  mov     rax, rsp
0x18000a3eb  sub     rsp, 28h
0x18000a3ef  mov     qword ptr [rax+20h], 0
0x18000a3f7  mov     [rax+20h], ecx
0x18000a3fa  mov     [rax+24h], dx
0x18000a3fe  test    r8d, r8d
0x18000a401  jz      short loc_18000A408
0x18000a403  or      word ptr [rax+26h], 1
0x18000a408  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000a40f  test    rax, rax
0x18000a412  jnz     short loc_18000A433
0x18000a414  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000a41b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000a420  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000a427  test    rax, rax
0x18000a42a  jnz     short loc_18000A433
0x18000a42c  mov     eax, 0C0000139h
0x18000a431  jmp     short loc_18000A43D
0x18000a433  lea     rcx, [rsp+28h+arg_18]
0x18000a438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a43d  add     rsp, 28h
0x18000a441  retn
```

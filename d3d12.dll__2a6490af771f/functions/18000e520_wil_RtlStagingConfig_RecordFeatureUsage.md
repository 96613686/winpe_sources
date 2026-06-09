# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x18000e520`
- end: `0x18000e57a`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180009ae0`

## callees

- `0x18000a398`
- `0x18000e520`
- `0x180015010`

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
0x18000e520  mov     rax, rsp
0x18000e523  sub     rsp, 28h
0x18000e527  mov     qword ptr [rax+20h], 0
0x18000e52f  mov     [rax+20h], ecx
0x18000e532  mov     [rax+24h], dx
0x18000e536  test    r8d, r8d
0x18000e539  jz      short loc_18000E540
0x18000e53b  or      word ptr [rax+26h], 1
0x18000e540  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000e547  test    rax, rax
0x18000e54a  jnz     short loc_18000E56B
0x18000e54c  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000e553  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000e558  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000e55f  test    rax, rax
0x18000e562  jnz     short loc_18000E56B
0x18000e564  mov     eax, 0C0000139h
0x18000e569  jmp     short loc_18000E575
0x18000e56b  lea     rcx, [rsp+28h+arg_18]
0x18000e570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e575  add     rsp, 28h
0x18000e579  retn
```

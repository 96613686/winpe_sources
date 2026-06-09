# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x180015da0`
- end: `0x180015dfa`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000ce40`

## callees

- `0x180015a54`
- `0x180015da0`
- `0x180018010`

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
0x180015da0  mov     rax, rsp
0x180015da3  sub     rsp, 28h
0x180015da7  mov     qword ptr [rax+20h], 0
0x180015daf  mov     [rax+20h], ecx
0x180015db2  mov     [rax+24h], dx
0x180015db6  test    r8d, r8d
0x180015db9  jz      short loc_180015DC0
0x180015dbb  or      word ptr [rax+26h], 1
0x180015dc0  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180015dc7  test    rax, rax
0x180015dca  jnz     short loc_180015DEB
0x180015dcc  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180015dd3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180015dd8  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180015ddf  test    rax, rax
0x180015de2  jnz     short loc_180015DEB
0x180015de4  mov     eax, 0C0000139h
0x180015de9  jmp     short loc_180015DF5
0x180015deb  lea     rcx, [rsp+28h+arg_18]
0x180015df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015df5  add     rsp, 28h
0x180015df9  retn
```

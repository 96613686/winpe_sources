# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x180015f38`
- end: `0x180015f92`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180015630`

## callees

- `0x18000bd6c`
- `0x180015f38`
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
0x180015f38  mov     rax, rsp
0x180015f3b  sub     rsp, 28h
0x180015f3f  mov     qword ptr [rax+20h], 0
0x180015f47  mov     [rax+20h], ecx
0x180015f4a  mov     [rax+24h], dx
0x180015f4e  test    r8d, r8d
0x180015f51  jz      short loc_180015F58
0x180015f53  or      word ptr [rax+26h], 1
0x180015f58  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180015f5f  test    rax, rax
0x180015f62  jnz     short loc_180015F83
0x180015f64  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180015f6b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180015f70  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180015f77  test    rax, rax
0x180015f7a  jnz     short loc_180015F83
0x180015f7c  mov     eax, 0C0000139h
0x180015f81  jmp     short loc_180015F8D
0x180015f83  lea     rcx, [rsp+28h+arg_18]
0x180015f88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f8d  add     rsp, 28h
0x180015f91  retn
```

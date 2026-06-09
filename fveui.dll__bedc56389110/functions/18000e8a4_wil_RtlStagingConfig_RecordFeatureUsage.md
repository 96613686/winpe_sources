# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x18000e8a4`
- end: `0x18000e8fe`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000c4e0`

## callees

- `0x18000dd70`
- `0x18000e8a4`
- `0x18002d010`

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
0x18000e8a4  mov     rax, rsp
0x18000e8a7  sub     rsp, 28h
0x18000e8ab  mov     qword ptr [rax+20h], 0
0x18000e8b3  mov     [rax+20h], ecx
0x18000e8b6  mov     [rax+24h], dx
0x18000e8ba  test    r8d, r8d
0x18000e8bd  jz      short loc_18000E8C4
0x18000e8bf  or      word ptr [rax+26h], 1
0x18000e8c4  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000e8cb  test    rax, rax
0x18000e8ce  jnz     short loc_18000E8EF
0x18000e8d0  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000e8d7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000e8dc  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000e8e3  test    rax, rax
0x18000e8e6  jnz     short loc_18000E8EF
0x18000e8e8  mov     eax, 0C0000139h
0x18000e8ed  jmp     short loc_18000E8F9
0x18000e8ef  lea     rcx, [rsp+28h+arg_18]
0x18000e8f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8f9  add     rsp, 28h
0x18000e8fd  retn
```

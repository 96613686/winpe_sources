# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x180024810`
- end: `0x18002486a`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180023ea0`

## callees

- `0x180024618`
- `0x180024810`
- `0x180027010`

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
0x180024810  mov     rax, rsp
0x180024813  sub     rsp, 28h
0x180024817  mov     qword ptr [rax+20h], 0
0x18002481f  mov     [rax+20h], ecx
0x180024822  mov     [rax+24h], dx
0x180024826  test    r8d, r8d
0x180024829  jz      short loc_180024830
0x18002482b  or      word ptr [rax+26h], 1
0x180024830  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180024837  test    rax, rax
0x18002483a  jnz     short loc_18002485B
0x18002483c  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180024843  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180024848  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18002484f  test    rax, rax
0x180024852  jnz     short loc_18002485B
0x180024854  mov     eax, 0C0000139h
0x180024859  jmp     short loc_180024865
0x18002485b  lea     rcx, [rsp+28h+arg_18]
0x180024860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024865  add     rsp, 28h
0x180024869  retn
```

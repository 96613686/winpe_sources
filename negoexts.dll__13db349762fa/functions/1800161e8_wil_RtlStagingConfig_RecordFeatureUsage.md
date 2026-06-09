# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x1800161e8`
- end: `0x180016242`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180014c90`

## callees

- `0x180015410`
- `0x1800161e8`
- `0x180020010`

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
0x1800161e8  mov     rax, rsp
0x1800161eb  sub     rsp, 28h
0x1800161ef  mov     qword ptr [rax+20h], 0
0x1800161f7  mov     [rax+20h], ecx
0x1800161fa  mov     [rax+24h], dx
0x1800161fe  test    r8d, r8d
0x180016201  jz      short loc_180016208
0x180016203  or      word ptr [rax+26h], 1
0x180016208  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18001620f  test    rax, rax
0x180016212  jnz     short loc_180016233
0x180016214  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18001621b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180016220  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180016227  test    rax, rax
0x18001622a  jnz     short loc_180016233
0x18001622c  mov     eax, 0C0000139h
0x180016231  jmp     short loc_18001623D
0x180016233  lea     rcx, [rsp+28h+arg_18]
0x180016238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001623d  add     rsp, 28h
0x180016241  retn
```

# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x180018104`
- end: `0x18001815e`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800185bc`
- `0x180022920`

## callees

- `0x180018104`
- `0x1800188ac`
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
0x180018104  mov     rax, rsp
0x180018107  sub     rsp, 28h
0x18001810b  mov     qword ptr [rax+20h], 0
0x180018113  mov     [rax+20h], ecx
0x180018116  mov     [rax+24h], dx
0x18001811a  test    r8d, r8d
0x18001811d  jz      short loc_180018124
0x18001811f  or      word ptr [rax+26h], 1
0x180018124  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18001812b  test    rax, rax
0x18001812e  jnz     short loc_18001814F
0x180018130  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180018137  call    wil_details_GetNtDllProcedureAddress
0x18001813c  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180018143  test    rax, rax
0x180018146  jnz     short loc_18001814F
0x180018148  mov     eax, 0C0000139h
0x18001814d  jmp     short loc_180018159
0x18001814f  lea     rcx, [rsp+28h+arg_18]
0x180018154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018159  add     rsp, 28h
0x18001815d  retn
```

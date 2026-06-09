# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x18001b060`
- end: `0x18001b0ba`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001a220`

## callees

- `0x18001aca0`
- `0x18001b060`
- `0x180025010`

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
0x18001b060  mov     rax, rsp
0x18001b063  sub     rsp, 28h
0x18001b067  mov     qword ptr [rax+20h], 0
0x18001b06f  mov     [rax+20h], ecx
0x18001b072  mov     [rax+24h], dx
0x18001b076  test    r8d, r8d
0x18001b079  jz      short loc_18001B080
0x18001b07b  or      word ptr [rax+26h], 1
0x18001b080  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18001b087  test    rax, rax
0x18001b08a  jnz     short loc_18001B0AB
0x18001b08c  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18001b093  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001b098  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18001b09f  test    rax, rax
0x18001b0a2  jnz     short loc_18001B0AB
0x18001b0a4  mov     eax, 0C0000139h
0x18001b0a9  jmp     short loc_18001B0B5
0x18001b0ab  lea     rcx, [rsp+28h+arg_18]
0x18001b0b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0b5  add     rsp, 28h
0x18001b0b9  retn
```

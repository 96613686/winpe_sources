# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x14000f090`
- end: `0x14000f0ea`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14000d4b0`

## callees

- `0x14000ed40`
- `0x14000f090`
- `0x14001a010`

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
0x14000f090  mov     rax, rsp
0x14000f093  sub     rsp, 28h
0x14000f097  mov     qword ptr [rax+20h], 0
0x14000f09f  mov     [rax+20h], ecx
0x14000f0a2  mov     [rax+24h], dx
0x14000f0a6  test    r8d, r8d
0x14000f0a9  jz      short loc_14000F0B0
0x14000f0ab  or      word ptr [rax+26h], 1
0x14000f0b0  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14000f0b7  test    rax, rax
0x14000f0ba  jnz     short loc_14000F0DB
0x14000f0bc  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x14000f0c3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000f0c8  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14000f0cf  test    rax, rax
0x14000f0d2  jnz     short loc_14000F0DB
0x14000f0d4  mov     eax, 0C0000139h
0x14000f0d9  jmp     short loc_14000F0E5
0x14000f0db  lea     rcx, [rsp+28h+arg_18]
0x14000f0e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f0e5  add     rsp, 28h
0x14000f0e9  retn
```

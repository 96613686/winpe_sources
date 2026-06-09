# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x18000d6a0`
- end: `0x18000d6fa`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: `__int64 __fastcall(int, __int16, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000be90`

## callees

- `0x180006060`
- `0x18000d6a0`
- `0x180012010`

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
0x18000d6a0  mov     rax, rsp
0x18000d6a3  sub     rsp, 28h
0x18000d6a7  mov     qword ptr [rax+20h], 0
0x18000d6af  mov     [rax+20h], ecx
0x18000d6b2  mov     [rax+24h], dx
0x18000d6b6  test    r8d, r8d
0x18000d6b9  jz      short loc_18000D6C0
0x18000d6bb  or      word ptr [rax+26h], 1
0x18000d6c0  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000d6c7  test    rax, rax
0x18000d6ca  jnz     short loc_18000D6EB
0x18000d6cc  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000d6d3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000d6d8  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000d6df  test    rax, rax
0x18000d6e2  jnz     short loc_18000D6EB
0x18000d6e4  mov     eax, 0C0000139h
0x18000d6e9  jmp     short loc_18000D6F5
0x18000d6eb  lea     rcx, [rsp+28h+arg_18]
0x18000d6f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6f5  add     rsp, 28h
0x18000d6f9  retn
```

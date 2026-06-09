# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x18002ece8`
- end: `0x18002ed42`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18002de20`

## callees

- `0x18002e9b8`
- `0x18002ece8`
- `0x180034010`

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
0x18002ece8  mov     rax, rsp
0x18002eceb  sub     rsp, 28h
0x18002ecef  mov     qword ptr [rax+20h], 0
0x18002ecf7  mov     [rax+20h], ecx
0x18002ecfa  mov     [rax+24h], dx
0x18002ecfe  test    r8d, r8d
0x18002ed01  jz      short loc_18002ED08
0x18002ed03  or      word ptr [rax+26h], 1
0x18002ed08  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18002ed0f  test    rax, rax
0x18002ed12  jnz     short loc_18002ED33
0x18002ed14  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18002ed1b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002ed20  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18002ed27  test    rax, rax
0x18002ed2a  jnz     short loc_18002ED33
0x18002ed2c  mov     eax, 0C0000139h
0x18002ed31  jmp     short loc_18002ED3D
0x18002ed33  lea     rcx, [rsp+28h+arg_18]
0x18002ed38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed3d  add     rsp, 28h
0x18002ed41  retn
```

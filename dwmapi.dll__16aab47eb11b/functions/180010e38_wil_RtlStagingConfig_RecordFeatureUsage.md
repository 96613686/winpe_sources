# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x180010e38`
- end: `0x180010e92`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180010590`

## callees

- `0x180009b4c`
- `0x180010e38`
- `0x180017010`

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
0x180010e38  mov     rax, rsp
0x180010e3b  sub     rsp, 28h
0x180010e3f  mov     qword ptr [rax+20h], 0
0x180010e47  mov     [rax+20h], ecx
0x180010e4a  mov     [rax+24h], dx
0x180010e4e  test    r8d, r8d
0x180010e51  jz      short loc_180010E58
0x180010e53  or      word ptr [rax+26h], 1
0x180010e58  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180010e5f  test    rax, rax
0x180010e62  jnz     short loc_180010E83
0x180010e64  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180010e6b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180010e70  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180010e77  test    rax, rax
0x180010e7a  jnz     short loc_180010E83
0x180010e7c  mov     eax, 0C0000139h
0x180010e81  jmp     short loc_180010E8D
0x180010e83  lea     rcx, [rsp+28h+arg_18]
0x180010e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e8d  add     rsp, 28h
0x180010e91  retn
```

# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x180022e44`
- end: `0x180022e9e`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18002339c`
- `0x1800297e0`

## callees

- `0x180022e44`
- `0x1800236b4`
- `0x18002f010`

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
0x180022e44  mov     rax, rsp
0x180022e47  sub     rsp, 28h
0x180022e4b  mov     qword ptr [rax+20h], 0
0x180022e53  mov     [rax+20h], ecx
0x180022e56  mov     [rax+24h], dx
0x180022e5a  test    r8d, r8d
0x180022e5d  jz      short loc_180022E64
0x180022e5f  or      word ptr [rax+26h], 1
0x180022e64  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180022e6b  test    rax, rax
0x180022e6e  jnz     short loc_180022E8F
0x180022e70  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180022e77  call    wil_details_GetNtDllProcedureAddress
0x180022e7c  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180022e83  test    rax, rax
0x180022e86  jnz     short loc_180022E8F
0x180022e88  mov     eax, 0C0000139h
0x180022e8d  jmp     short loc_180022E99
0x180022e8f  lea     rcx, [rsp+28h+arg_18]
0x180022e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e99  add     rsp, 28h
0x180022e9d  retn
```

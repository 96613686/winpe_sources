# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x180008890`
- end: `0x1800088ea`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180007780`

## callees

- `0x180008288`
- `0x180008890`
- `0x180026010`

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
0x180008890  mov     rax, rsp
0x180008893  sub     rsp, 28h
0x180008897  mov     qword ptr [rax+20h], 0
0x18000889f  mov     [rax+20h], ecx
0x1800088a2  mov     [rax+24h], dx
0x1800088a6  test    r8d, r8d
0x1800088a9  jz      short loc_1800088B0
0x1800088ab  or      word ptr [rax+26h], 1
0x1800088b0  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1800088b7  test    rax, rax
0x1800088ba  jnz     short loc_1800088DB
0x1800088bc  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1800088c3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800088c8  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1800088cf  test    rax, rax
0x1800088d2  jnz     short loc_1800088DB
0x1800088d4  mov     eax, 0C0000139h
0x1800088d9  jmp     short loc_1800088E5
0x1800088db  lea     rcx, [rsp+28h+arg_18]
0x1800088e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088e5  add     rsp, 28h
0x1800088e9  retn
```

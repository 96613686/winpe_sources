# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x18001ba18`
- end: `0x18001ba72`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800199e8`

## callees

- `0x180019a54`
- `0x18001ba18`
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
0x18001ba18  mov     rax, rsp
0x18001ba1b  sub     rsp, 28h
0x18001ba1f  mov     qword ptr [rax+20h], 0
0x18001ba27  mov     [rax+20h], ecx
0x18001ba2a  mov     [rax+24h], dx
0x18001ba2e  test    r8d, r8d
0x18001ba31  jz      short loc_18001BA38
0x18001ba33  or      word ptr [rax+26h], 1
0x18001ba38  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18001ba3f  test    rax, rax
0x18001ba42  jnz     short loc_18001BA63
0x18001ba44  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18001ba4b  call    wil_details_GetNtDllProcedureAddress
0x18001ba50  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18001ba57  test    rax, rax
0x18001ba5a  jnz     short loc_18001BA63
0x18001ba5c  mov     eax, 0C0000139h
0x18001ba61  jmp     short loc_18001BA6D
0x18001ba63  lea     rcx, [rsp+28h+arg_18]
0x18001ba68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba6d  add     rsp, 28h
0x18001ba71  retn
```

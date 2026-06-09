# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x1800084ec`
- end: `0x180008546`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180008a48`

## callees

- `0x1800084ec`
- `0x180008d34`
- `0x18000a010`

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
0x1800084ec  mov     rax, rsp
0x1800084ef  sub     rsp, 28h
0x1800084f3  mov     qword ptr [rax+20h], 0
0x1800084fb  mov     [rax+20h], ecx
0x1800084fe  mov     [rax+24h], dx
0x180008502  test    r8d, r8d
0x180008505  jz      short loc_18000850C
0x180008507  or      word ptr [rax+26h], 1
0x18000850c  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180008513  test    rax, rax
0x180008516  jnz     short loc_180008537
0x180008518  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000851f  call    wil_details_GetNtDllProcedureAddress
0x180008524  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000852b  test    rax, rax
0x18000852e  jnz     short loc_180008537
0x180008530  mov     eax, 0C0000139h
0x180008535  jmp     short loc_180008541
0x180008537  lea     rcx, [rsp+28h+arg_18]
0x18000853c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008541  add     rsp, 28h
0x180008545  retn
```

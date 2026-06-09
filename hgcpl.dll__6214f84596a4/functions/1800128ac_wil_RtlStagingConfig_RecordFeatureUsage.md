# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x1800128ac`
- end: `0x180012906`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800121a0`

## callees

- `0x180006b70`
- `0x1800128ac`
- `0x18001a010`

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
0x1800128ac  mov     rax, rsp
0x1800128af  sub     rsp, 28h
0x1800128b3  mov     qword ptr [rax+20h], 0
0x1800128bb  mov     [rax+20h], ecx
0x1800128be  mov     [rax+24h], dx
0x1800128c2  test    r8d, r8d
0x1800128c5  jz      short loc_1800128CC
0x1800128c7  or      word ptr [rax+26h], 1
0x1800128cc  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1800128d3  test    rax, rax
0x1800128d6  jnz     short loc_1800128F7
0x1800128d8  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1800128df  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800128e4  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1800128eb  test    rax, rax
0x1800128ee  jnz     short loc_1800128F7
0x1800128f0  mov     eax, 0C0000139h
0x1800128f5  jmp     short loc_180012901
0x1800128f7  lea     rcx, [rsp+28h+arg_18]
0x1800128fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012901  add     rsp, 28h
0x180012905  retn
```

# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x140018380`
- end: `0x1400183da`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14000d7c0`
- `0x14001d178`

## callees

- `0x14000e99c`
- `0x140018380`
- `0x14001f010`

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
0x140018380  mov     rax, rsp
0x140018383  sub     rsp, 28h
0x140018387  mov     qword ptr [rax+20h], 0
0x14001838f  mov     [rax+20h], ecx
0x140018392  mov     [rax+24h], dx
0x140018396  test    r8d, r8d
0x140018399  jz      short loc_1400183A0
0x14001839b  or      word ptr [rax+26h], 1
0x1400183a0  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1400183a7  test    rax, rax
0x1400183aa  jnz     short loc_1400183CB
0x1400183ac  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1400183b3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1400183b8  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1400183bf  test    rax, rax
0x1400183c2  jnz     short loc_1400183CB
0x1400183c4  mov     eax, 0C0000139h
0x1400183c9  jmp     short loc_1400183D5
0x1400183cb  lea     rcx, [rsp+28h+arg_18]
0x1400183d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400183d5  add     rsp, 28h
0x1400183d9  retn
```

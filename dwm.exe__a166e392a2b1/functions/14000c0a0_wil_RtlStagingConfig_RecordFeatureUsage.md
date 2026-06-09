# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x14000c0a0`
- end: `0x14000c0fa`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14000b390`

## callees

- `0x14000bcc4`
- `0x14000c0a0`
- `0x140010010`

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
0x14000c0a0  mov     rax, rsp
0x14000c0a3  sub     rsp, 28h
0x14000c0a7  mov     qword ptr [rax+20h], 0
0x14000c0af  mov     [rax+20h], ecx
0x14000c0b2  mov     [rax+24h], dx
0x14000c0b6  test    r8d, r8d
0x14000c0b9  jz      short loc_14000C0C0
0x14000c0bb  or      word ptr [rax+26h], 1
0x14000c0c0  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14000c0c7  test    rax, rax
0x14000c0ca  jnz     short loc_14000C0EB
0x14000c0cc  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x14000c0d3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000c0d8  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14000c0df  test    rax, rax
0x14000c0e2  jnz     short loc_14000C0EB
0x14000c0e4  mov     eax, 0C0000139h
0x14000c0e9  jmp     short loc_14000C0F5
0x14000c0eb  lea     rcx, [rsp+28h+arg_18]
0x14000c0f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c0f5  add     rsp, 28h
0x14000c0f9  retn
```

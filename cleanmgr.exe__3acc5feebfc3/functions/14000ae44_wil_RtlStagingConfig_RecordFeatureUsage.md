# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x14000ae44`
- end: `0x14000ae9e`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: `__int64 __fastcall(int, __int16, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140009b50`

## callees

- `0x140006980`
- `0x14000ae44`
- `0x140018010`

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
0x14000ae44  mov     rax, rsp
0x14000ae47  sub     rsp, 28h
0x14000ae4b  mov     qword ptr [rax+20h], 0
0x14000ae53  mov     [rax+20h], ecx
0x14000ae56  mov     [rax+24h], dx
0x14000ae5a  test    r8d, r8d
0x14000ae5d  jz      short loc_14000AE64
0x14000ae5f  or      word ptr [rax+26h], 1
0x14000ae64  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14000ae6b  test    rax, rax
0x14000ae6e  jnz     short loc_14000AE8F
0x14000ae70  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x14000ae77  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000ae7c  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14000ae83  test    rax, rax
0x14000ae86  jnz     short loc_14000AE8F
0x14000ae88  mov     eax, 0C0000139h
0x14000ae8d  jmp     short loc_14000AE99
0x14000ae8f  lea     rcx, [rsp+28h+arg_18]
0x14000ae94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ae99  add     rsp, 28h
0x14000ae9d  retn
```

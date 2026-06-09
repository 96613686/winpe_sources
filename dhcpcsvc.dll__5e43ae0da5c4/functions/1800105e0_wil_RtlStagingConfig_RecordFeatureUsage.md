# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x1800105e0`
- end: `0x18001063a`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800038f8`

## callees

- `0x180003c34`
- `0x1800105e0`
- `0x180014010`

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
0x1800105e0  mov     rax, rsp
0x1800105e3  sub     rsp, 28h
0x1800105e7  mov     qword ptr [rax+20h], 0
0x1800105ef  mov     [rax+20h], ecx
0x1800105f2  mov     [rax+24h], dx
0x1800105f6  test    r8d, r8d
0x1800105f9  jz      short loc_180010600
0x1800105fb  or      word ptr [rax+26h], 1
0x180010600  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180010607  test    rax, rax
0x18001060a  jnz     short loc_18001062B
0x18001060c  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180010613  call    wil_details_GetNtDllProcedureAddress
0x180010618  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18001061f  test    rax, rax
0x180010622  jnz     short loc_18001062B
0x180010624  mov     eax, 0C0000139h
0x180010629  jmp     short loc_180010635
0x18001062b  lea     rcx, [rsp+28h+arg_18]
0x180010630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010635  add     rsp, 28h
0x180010639  retn
```

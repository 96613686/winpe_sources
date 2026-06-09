# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x18000a62c`
- end: `0x18000a6a3`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `119`
- prototype: `__int64 __fastcall(int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180009ae0`

## callees

- `0x180004310`
- `0x18000a380`
- `0x18000a62c`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_RecordFeatureUsage(int a1, unsigned __int16 a2, int a3)
{
  FARPROC NtDllProcedureAddress; // rax
  int v5; // [rsp+20h] [rbp-18h] BYREF
  int v6; // [rsp+24h] [rbp-14h]

  v5 = a1;
  v6 = a2;
  if ( a3 )
    HIWORD(v6) |= 1u;
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
0x18000a62c  sub     rsp, 38h
0x18000a630  mov     rax, cs:__security_cookie
0x18000a637  xor     rax, rsp
0x18000a63a  mov     [rsp+38h+var_10], rax
0x18000a63f  mov     [rsp+38h+var_18], 0
0x18000a648  mov     dword ptr [rsp+38h+var_18], ecx
0x18000a64c  mov     word ptr [rsp+38h+var_18+4], dx
0x18000a651  test    r8d, r8d
0x18000a654  jz      short loc_18000A65C
0x18000a656  or      word ptr [rsp+38h+var_18+6], 1
0x18000a65c  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000a663  test    rax, rax
0x18000a666  jnz     short loc_18000A687
0x18000a668  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000a66f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000a674  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000a67b  test    rax, rax
0x18000a67e  jnz     short loc_18000A687
0x18000a680  mov     eax, 0C0000139h
0x18000a685  jmp     short loc_18000A691
0x18000a687  lea     rcx, [rsp+38h+var_18]
0x18000a68c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a691  mov     rcx, [rsp+38h+var_10]
0x18000a696  xor     rcx, rsp; StackCookie
0x18000a699  call    __security_check_cookie
0x18000a69e  add     rsp, 38h
0x18000a6a2  retn
```

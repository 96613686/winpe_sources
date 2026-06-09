# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x18000a550`
- end: `0x18000a5c7`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180009470`

## callees

- `0x180002620`
- `0x18000a118`
- `0x18000a550`
- `0x180013010`

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
0x18000a550  sub     rsp, 38h
0x18000a554  mov     rax, cs:__security_cookie
0x18000a55b  xor     rax, rsp
0x18000a55e  mov     [rsp+38h+var_10], rax
0x18000a563  mov     [rsp+38h+var_18], 0
0x18000a56c  mov     dword ptr [rsp+38h+var_18], ecx
0x18000a570  mov     word ptr [rsp+38h+var_18+4], dx
0x18000a575  test    r8d, r8d
0x18000a578  jz      short loc_18000A580
0x18000a57a  or      word ptr [rsp+38h+var_18+6], 1
0x18000a580  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000a587  test    rax, rax
0x18000a58a  jnz     short loc_18000A5AB
0x18000a58c  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000a593  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000a598  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000a59f  test    rax, rax
0x18000a5a2  jnz     short loc_18000A5AB
0x18000a5a4  mov     eax, 0C0000139h
0x18000a5a9  jmp     short loc_18000A5B5
0x18000a5ab  lea     rcx, [rsp+38h+var_18]
0x18000a5b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5b5  mov     rcx, [rsp+38h+var_10]
0x18000a5ba  xor     rcx, rsp; StackCookie
0x18000a5bd  call    __security_check_cookie
0x18000a5c2  add     rsp, 38h
0x18000a5c6  retn
```

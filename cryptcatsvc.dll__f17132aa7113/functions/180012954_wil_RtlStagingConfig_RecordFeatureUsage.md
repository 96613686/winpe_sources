# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x180012954`
- end: `0x1800129cb`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180011990`

## callees

- `0x18000be40`
- `0x180012410`
- `0x180012954`
- `0x180022010`

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
0x180012954  sub     rsp, 38h
0x180012958  mov     rax, cs:__security_cookie
0x18001295f  xor     rax, rsp
0x180012962  mov     [rsp+38h+var_10], rax
0x180012967  mov     [rsp+38h+var_18], 0
0x180012970  mov     dword ptr [rsp+38h+var_18], ecx
0x180012974  mov     word ptr [rsp+38h+var_18+4], dx
0x180012979  test    r8d, r8d
0x18001297c  jz      short loc_180012984
0x18001297e  or      word ptr [rsp+38h+var_18+6], 1
0x180012984  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18001298b  test    rax, rax
0x18001298e  jnz     short loc_1800129AF
0x180012990  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180012997  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001299c  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1800129a3  test    rax, rax
0x1800129a6  jnz     short loc_1800129AF
0x1800129a8  mov     eax, 0C0000139h
0x1800129ad  jmp     short loc_1800129B9
0x1800129af  lea     rcx, [rsp+38h+var_18]
0x1800129b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129b9  mov     rcx, [rsp+38h+var_10]
0x1800129be  xor     rcx, rsp; StackCookie
0x1800129c1  call    __security_check_cookie
0x1800129c6  add     rsp, 38h
0x1800129ca  retn
```

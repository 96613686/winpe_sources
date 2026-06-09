# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180010ea0`
- end: `0x180010ef6`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180007a74`
- `0x180010ea0`
- `0x180017010`

## pseudocode

```c
FARPROC __fastcall wil_StagingConfig_LogStagedFeatureUsage(unsigned int a1, unsigned int a2, __int64 a3)
{
  FARPROC result; // rax
  char v4; // bl

  result = (FARPROC)g_wil_details_pfnLogStagedFeatureUsage;
  v4 = a3;
  if ( g_wil_details_pfnLogStagedFeatureUsage
    || (result = wil_details_GetKernelBaseProcAddress("LogStagedFeatureUsage"),
        (g_wil_details_pfnLogStagedFeatureUsage = (__int64)result) != 0) )
  {
    LOBYTE(a3) = v4;
    return (FARPROC)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))result)(a1, a2, a3);
  }
  return result;
}

```

## disassembly

```asm
0x180010ea0  mov     [rsp+arg_0], rbx
0x180010ea5  mov     [rsp+arg_8], rsi
0x180010eaa  push    rdi
0x180010eab  sub     rsp, 20h
0x180010eaf  mov     rax, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180010eb6  mov     bl, r8b
0x180010eb9  mov     edi, edx
0x180010ebb  mov     esi, ecx
0x180010ebd  test    rax, rax
0x180010ec0  jnz     short loc_180010EDA
0x180010ec2  lea     rcx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180010ec9  call    ?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z; wil_details_GetKernelBaseProcAddress(char const *)
0x180010ece  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rax
0x180010ed5  test    rax, rax
0x180010ed8  jz      short loc_180010EE6
0x180010eda  mov     r8b, bl
0x180010edd  mov     edx, edi
0x180010edf  mov     ecx, esi
0x180010ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ee6  mov     rbx, [rsp+28h+arg_0]
0x180010eeb  mov     rsi, [rsp+28h+arg_8]
0x180010ef0  add     rsp, 20h
0x180010ef4  pop     rdi
0x180010ef5  retn
```

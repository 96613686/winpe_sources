# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000d700`
- end: `0x18000d756`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `86`
- prototype: `FARPROC __fastcall(unsigned int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180005fd8`
- `0x18000d700`
- `0x180012010`

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
0x18000d700  mov     [rsp+arg_0], rbx
0x18000d705  mov     [rsp+arg_8], rsi
0x18000d70a  push    rdi
0x18000d70b  sub     rsp, 20h
0x18000d70f  mov     rax, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000d716  mov     bl, r8b
0x18000d719  mov     edi, edx
0x18000d71b  mov     esi, ecx
0x18000d71d  test    rax, rax
0x18000d720  jnz     short loc_18000D73A
0x18000d722  lea     rcx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000d729  call    ?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z; wil_details_GetKernelBaseProcAddress(char const *)
0x18000d72e  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rax
0x18000d735  test    rax, rax
0x18000d738  jz      short loc_18000D746
0x18000d73a  mov     r8b, bl
0x18000d73d  mov     edx, edi
0x18000d73f  mov     ecx, esi
0x18000d741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d746  mov     rbx, [rsp+28h+arg_0]
0x18000d74b  mov     rsi, [rsp+28h+arg_8]
0x18000d750  add     rsp, 20h
0x18000d754  pop     rdi
0x18000d755  retn
```

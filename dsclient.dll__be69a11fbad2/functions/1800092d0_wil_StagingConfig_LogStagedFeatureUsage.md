# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x1800092d0`
- end: `0x180009326`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `86`
- prototype: `FARPROC __fastcall(unsigned int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180008eb8`
- `0x1800092d0`
- `0x18000a010`

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
0x1800092d0  mov     [rsp+arg_0], rbx
0x1800092d5  mov     [rsp+arg_8], rsi
0x1800092da  push    rdi
0x1800092db  sub     rsp, 20h
0x1800092df  mov     rax, cs:g_wil_details_pfnLogStagedFeatureUsage
0x1800092e6  mov     bl, r8b
0x1800092e9  mov     edi, edx
0x1800092eb  mov     esi, ecx
0x1800092ed  test    rax, rax
0x1800092f0  jnz     short loc_18000930A
0x1800092f2  lea     rcx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x1800092f9  call    ?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z; wil_details_GetKernelBaseProcAddress(char const *)
0x1800092fe  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rax
0x180009305  test    rax, rax
0x180009308  jz      short loc_180009316
0x18000930a  mov     r8b, bl
0x18000930d  mov     edx, edi
0x18000930f  mov     ecx, esi
0x180009311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009316  mov     rbx, [rsp+28h+arg_0]
0x18000931b  mov     rsi, [rsp+28h+arg_8]
0x180009320  add     rsp, 20h
0x180009324  pop     rdi
0x180009325  retn
```

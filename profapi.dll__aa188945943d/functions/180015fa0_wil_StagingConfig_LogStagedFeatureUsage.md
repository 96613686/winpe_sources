# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180015fa0`
- end: `0x180015ff6`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000dc54`
- `0x180015fa0`
- `0x180018010`

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
0x180015fa0  mov     [rsp+arg_0], rbx
0x180015fa5  mov     [rsp+arg_8], rsi
0x180015faa  push    rdi
0x180015fab  sub     rsp, 20h
0x180015faf  mov     rax, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180015fb6  mov     bl, r8b
0x180015fb9  mov     edi, edx
0x180015fbb  mov     esi, ecx
0x180015fbd  test    rax, rax
0x180015fc0  jnz     short loc_180015FDA
0x180015fc2  lea     rcx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180015fc9  call    ?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z; wil_details_GetKernelBaseProcAddress(char const *)
0x180015fce  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rax
0x180015fd5  test    rax, rax
0x180015fd8  jz      short loc_180015FE6
0x180015fda  mov     r8b, bl
0x180015fdd  mov     edx, edi
0x180015fdf  mov     ecx, esi
0x180015fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fe6  mov     rbx, [rsp+28h+arg_0]
0x180015feb  mov     rsi, [rsp+28h+arg_8]
0x180015ff0  add     rsp, 20h
0x180015ff4  pop     rdi
0x180015ff5  retn
```

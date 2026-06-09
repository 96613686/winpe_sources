# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180015e00`
- end: `0x180015e56`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1800159cc`
- `0x180015e00`
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
0x180015e00  mov     [rsp+arg_0], rbx
0x180015e05  mov     [rsp+arg_8], rsi
0x180015e0a  push    rdi
0x180015e0b  sub     rsp, 20h
0x180015e0f  mov     rax, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180015e16  mov     bl, r8b
0x180015e19  mov     edi, edx
0x180015e1b  mov     esi, ecx
0x180015e1d  test    rax, rax
0x180015e20  jnz     short loc_180015E3A
0x180015e22  lea     rcx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180015e29  call    ?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z; wil_details_GetKernelBaseProcAddress(char const *)
0x180015e2e  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rax
0x180015e35  test    rax, rax
0x180015e38  jz      short loc_180015E46
0x180015e3a  mov     r8b, bl
0x180015e3d  mov     edx, edi
0x180015e3f  mov     ecx, esi
0x180015e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e46  mov     rbx, [rsp+28h+arg_0]
0x180015e4b  mov     rsi, [rsp+28h+arg_8]
0x180015e50  add     rsp, 20h
0x180015e54  pop     rdi
0x180015e55  retn
```

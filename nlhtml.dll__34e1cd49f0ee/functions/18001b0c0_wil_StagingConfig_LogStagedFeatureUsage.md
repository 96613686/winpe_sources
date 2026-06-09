# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18001b0c0`
- end: `0x18001b116`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18001ac18`
- `0x18001b0c0`
- `0x180025010`

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
0x18001b0c0  mov     [rsp+arg_0], rbx
0x18001b0c5  mov     [rsp+arg_8], rsi
0x18001b0ca  push    rdi
0x18001b0cb  sub     rsp, 20h
0x18001b0cf  mov     rax, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18001b0d6  mov     bl, r8b
0x18001b0d9  mov     edi, edx
0x18001b0db  mov     esi, ecx
0x18001b0dd  test    rax, rax
0x18001b0e0  jnz     short loc_18001B0FA
0x18001b0e2  lea     rcx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18001b0e9  call    ?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z; wil_details_GetKernelBaseProcAddress(char const *)
0x18001b0ee  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rax
0x18001b0f5  test    rax, rax
0x18001b0f8  jz      short loc_18001B106
0x18001b0fa  mov     r8b, bl
0x18001b0fd  mov     edx, edi
0x18001b0ff  mov     ecx, esi
0x18001b101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b106  mov     rbx, [rsp+28h+arg_0]
0x18001b10b  mov     rsi, [rsp+28h+arg_8]
0x18001b110  add     rsp, 20h
0x18001b114  pop     rdi
0x18001b115  retn
```

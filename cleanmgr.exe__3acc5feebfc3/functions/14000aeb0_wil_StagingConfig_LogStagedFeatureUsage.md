# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x14000aeb0`
- end: `0x14000af06`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `86`
- prototype: `FARPROC __fastcall(unsigned int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1400068f8`
- `0x14000aeb0`
- `0x140018010`

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
0x14000aeb0  mov     [rsp+arg_0], rbx
0x14000aeb5  mov     [rsp+arg_8], rsi
0x14000aeba  push    rdi
0x14000aebb  sub     rsp, 20h
0x14000aebf  mov     rax, cs:g_wil_details_pfnLogStagedFeatureUsage
0x14000aec6  mov     bl, r8b
0x14000aec9  mov     edi, edx
0x14000aecb  mov     esi, ecx
0x14000aecd  test    rax, rax
0x14000aed0  jnz     short loc_14000AEEA
0x14000aed2  lea     rcx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x14000aed9  call    ?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z; wil_details_GetKernelBaseProcAddress(char const *)
0x14000aede  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rax
0x14000aee5  test    rax, rax
0x14000aee8  jz      short loc_14000AEF6
0x14000aeea  mov     r8b, bl
0x14000aeed  mov     edx, edi
0x14000aeef  mov     ecx, esi
0x14000aef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aef6  mov     rbx, [rsp+28h+arg_0]
0x14000aefb  mov     rsi, [rsp+28h+arg_8]
0x14000af00  add     rsp, 20h
0x14000af04  pop     rdi
0x14000af05  retn
```

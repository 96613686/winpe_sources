# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x14000ab00`
- end: `0x14000ab56`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x14000ab00`
- `0x14000f6e4`
- `0x14001f010`

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
0x14000ab00  mov     [rsp+arg_0], rbx
0x14000ab05  mov     [rsp+arg_8], rsi
0x14000ab0a  push    rdi
0x14000ab0b  sub     rsp, 20h
0x14000ab0f  mov     rax, cs:g_wil_details_pfnLogStagedFeatureUsage
0x14000ab16  mov     bl, r8b
0x14000ab19  mov     edi, edx
0x14000ab1b  mov     esi, ecx
0x14000ab1d  test    rax, rax
0x14000ab20  jnz     short loc_14000AB3A
0x14000ab22  lea     rcx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x14000ab29  call    ?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z; wil_details_GetKernelBaseProcAddress(char const *)
0x14000ab2e  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rax
0x14000ab35  test    rax, rax
0x14000ab38  jz      short loc_14000AB46
0x14000ab3a  mov     r8b, bl
0x14000ab3d  mov     edx, edi
0x14000ab3f  mov     ecx, esi
0x14000ab41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ab46  mov     rbx, [rsp+28h+arg_0]
0x14000ab4b  mov     rsi, [rsp+28h+arg_8]
0x14000ab50  add     rsp, 20h
0x14000ab54  pop     rdi
0x14000ab55  retn
```

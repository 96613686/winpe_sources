# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180016250`
- end: `0x1800162a6`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180015388`
- `0x180016250`
- `0x180020010`

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
0x180016250  mov     [rsp+arg_0], rbx
0x180016255  mov     [rsp+arg_8], rsi
0x18001625a  push    rdi
0x18001625b  sub     rsp, 20h
0x18001625f  mov     rax, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180016266  mov     bl, r8b
0x180016269  mov     edi, edx
0x18001626b  mov     esi, ecx
0x18001626d  test    rax, rax
0x180016270  jnz     short loc_18001628A
0x180016272  lea     rcx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180016279  call    ?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z; wil_details_GetKernelBaseProcAddress(char const *)
0x18001627e  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rax
0x180016285  test    rax, rax
0x180016288  jz      short loc_180016296
0x18001628a  mov     r8b, bl
0x18001628d  mov     edx, edi
0x18001628f  mov     ecx, esi
0x180016291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016296  mov     rbx, [rsp+28h+arg_0]
0x18001629b  mov     rsi, [rsp+28h+arg_8]
0x1800162a0  add     rsp, 20h
0x1800162a4  pop     rdi
0x1800162a5  retn
```

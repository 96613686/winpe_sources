# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000a5d0`
- end: `0x18000a626`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000a090`
- `0x18000a5d0`
- `0x180013010`

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
0x18000a5d0  mov     [rsp+arg_0], rbx
0x18000a5d5  mov     [rsp+arg_8], rsi
0x18000a5da  push    rdi
0x18000a5db  sub     rsp, 20h
0x18000a5df  mov     rax, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000a5e6  mov     bl, r8b
0x18000a5e9  mov     edi, edx
0x18000a5eb  mov     esi, ecx
0x18000a5ed  test    rax, rax
0x18000a5f0  jnz     short loc_18000A60A
0x18000a5f2  lea     rcx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000a5f9  call    ?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z; wil_details_GetKernelBaseProcAddress(char const *)
0x18000a5fe  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rax
0x18000a605  test    rax, rax
0x18000a608  jz      short loc_18000A616
0x18000a60a  mov     r8b, bl
0x18000a60d  mov     edx, edi
0x18000a60f  mov     ecx, esi
0x18000a611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a616  mov     rbx, [rsp+28h+arg_0]
0x18000a61b  mov     rsi, [rsp+28h+arg_8]
0x18000a620  add     rsp, 20h
0x18000a624  pop     rdi
0x18000a625  retn
```

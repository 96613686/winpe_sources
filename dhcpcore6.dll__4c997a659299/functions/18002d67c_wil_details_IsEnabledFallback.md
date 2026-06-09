# wil_details_IsEnabledFallback

- ea: `0x18002d67c`
- end: `0x18002d6f5`
- name: `wil_details_IsEnabledFallback`
- size: `121`
- prototype: `__int64 __fastcall(__int64, unsigned int, _QWORD *)`
- caller_count: `13`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18002c4c4`
- `0x18002d8ac`
- `0x18002d8f4`
- `0x18002d93c`
- `0x18002d984`
- `0x18002d9cc`
- `0x18002da14`
- `0x18002da5c`
- `0x18002daa4`
- `0x18002daec`
- `0x18002db34`
- `0x18002db7c`
- `0x18002f634`

## callees

- `0x18000f040`
- `0x18002d4f8`
- `0x18002d628`
- `0x18002d67c`

## pseudocode

```c
__int64 __fastcall wil_details_IsEnabledFallback(__int64 a1, unsigned int a2, _QWORD *a3)
{
  char v5; // bl
  __int64 v6; // rdi

  v5 = a1;
  if ( (a1 & 2) != 0 )
  {
    v6 = (unsigned int)a1;
  }
  else
  {
    v6 = wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(*a3, a1);
    v5 = v6;
  }
  if ( a2 )
  {
    wil_details_FeatureReporting_ReportUsageToService(a3, v6, a2);
    if ( a2 - 3 <= 1 )
      wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(v6, a2, a3);
  }
  return v5 & 1;
}

```

## disassembly

```asm
0x18002d67c  push    rbx
0x18002d67e  push    rsi
0x18002d67f  push    rdi
0x18002d680  push    r14
0x18002d682  sub     rsp, 28h
0x18002d686  mov     [rsp+48h+arg_0], 0
0x18002d68f  mov     r14, r8
0x18002d692  mov     dword ptr [rsp+48h+arg_0], ecx
0x18002d696  mov     esi, edx
0x18002d698  mov     rbx, rcx
0x18002d69b  test    cl, 2
0x18002d69e  jnz     short loc_18002D6B9
0x18002d6a0  mov     rdx, rcx
0x18002d6a3  mov     rcx, [r8]
0x18002d6a6  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x18002d6ab  mov     [rsp+48h+arg_0], rax
0x18002d6b0  mov     rdi, rax
0x18002d6b3  mov     ebx, dword ptr [rsp+48h+arg_0]
0x18002d6b7  jmp     short loc_18002D6BE
0x18002d6b9  mov     rdi, [rsp+48h+arg_0]
0x18002d6be  test    esi, esi
0x18002d6c0  jz      short loc_18002D6E5
0x18002d6c2  mov     r8d, esi
0x18002d6c5  mov     rdx, rdi
0x18002d6c8  mov     rcx, r14
0x18002d6cb  call    wil_details_FeatureReporting_ReportUsageToService
0x18002d6d0  lea     eax, [rsi-3]
0x18002d6d3  cmp     eax, 1
0x18002d6d6  ja      short loc_18002D6E5
0x18002d6d8  mov     r8, r14
0x18002d6db  mov     edx, esi
0x18002d6dd  mov     rcx, rdi
0x18002d6e0  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x18002d6e5  and     ebx, 1
0x18002d6e8  mov     eax, ebx
0x18002d6ea  add     rsp, 28h
0x18002d6ee  pop     r14
0x18002d6f0  pop     rdi
0x18002d6f1  pop     rsi
0x18002d6f2  pop     rbx
0x18002d6f3  retn
```

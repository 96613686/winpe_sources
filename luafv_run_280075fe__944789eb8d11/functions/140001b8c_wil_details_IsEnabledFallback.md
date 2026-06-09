# wil_details_IsEnabledFallback

- ea: `0x140001b8c`
- end: `0x140001c05`
- name: `wil_details_IsEnabledFallback`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140001ac0`
- `0x140001b18`
- `0x140001b70`

## callees

- `0x140001b8c`
- `0x140002a70`
- `0x140002bd8`
- `0x140002cf0`

## pseudocode

```c
__int64 __fastcall wil_details_IsEnabledFallback(__int64 a1, unsigned int a2, volatile signed __int32 **a3)
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
    v6 = wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(*a3, a1, (__int64)a3);
    v5 = v6;
  }
  if ( a2 )
  {
    wil_details_FeatureReporting_ReportUsageToService((__int64)a3, v6, a2);
    if ( a2 - 3 <= 1 )
      wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(v6, a2, (__int64)a3);
  }
  return v5 & 1;
}

```

## disassembly

```asm
0x140001b8c  push    rbx
0x140001b8e  push    rsi
0x140001b8f  push    rdi
0x140001b90  push    r14
0x140001b92  sub     rsp, 28h
0x140001b96  mov     [rsp+48h+arg_0], 0
0x140001b9f  mov     r14, r8
0x140001ba2  mov     dword ptr [rsp+48h+arg_0], ecx
0x140001ba6  mov     esi, edx
0x140001ba8  mov     rbx, rcx
0x140001bab  test    cl, 2
0x140001bae  jnz     short loc_140001BC9
0x140001bb0  mov     rdx, rcx
0x140001bb3  mov     rcx, [r8]
0x140001bb6  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x140001bbb  mov     [rsp+48h+arg_0], rax
0x140001bc0  mov     rdi, rax
0x140001bc3  mov     ebx, dword ptr [rsp+48h+arg_0]
0x140001bc7  jmp     short loc_140001BCE
0x140001bc9  mov     rdi, [rsp+48h+arg_0]
0x140001bce  test    esi, esi
0x140001bd0  jz      short loc_140001BF5
0x140001bd2  mov     r8d, esi
0x140001bd5  mov     rdx, rdi
0x140001bd8  mov     rcx, r14
0x140001bdb  call    wil_details_FeatureReporting_ReportUsageToService
0x140001be0  lea     eax, [rsi-3]
0x140001be3  cmp     eax, 1
0x140001be6  ja      short loc_140001BF5
0x140001be8  mov     r8, r14
0x140001beb  mov     edx, esi
0x140001bed  mov     rcx, rdi
0x140001bf0  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x140001bf5  and     ebx, 1
0x140001bf8  mov     eax, ebx
0x140001bfa  add     rsp, 28h
0x140001bfe  pop     r14
0x140001c00  pop     rdi
0x140001c01  pop     rsi
0x140001c02  pop     rbx
0x140001c03  retn
```

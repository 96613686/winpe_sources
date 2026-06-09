# wil_details_IsEnabledFallback

- ea: `0x180005dc4`
- end: `0x180005e3c`
- name: `wil_details_IsEnabledFallback`
- size: `120`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180005db0`
- `0x18000832c`

## callees

- `0x180005dc4`
- `0x18000891c`
- `0x180008ab4`
- `0x180008bcc`

## pseudocode

```c
__int64 __fastcall wil_details_IsEnabledFallback(__int64 a1, int a2, volatile signed __int32 **a3)
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
    if ( (unsigned int)(a2 - 3) <= 1 )
      wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(v6, a2, (__int64)a3);
  }
  return v5 & 1;
}

```

## disassembly

```asm
0x180005dc4  push    rbx
0x180005dc6  push    rsi
0x180005dc7  push    rdi
0x180005dc8  push    r14
0x180005dca  sub     rsp, 28h
0x180005dce  mov     [rsp+48h+arg_0], 0
0x180005dd7  mov     r14, r8
0x180005dda  mov     dword ptr [rsp+48h+arg_0], ecx
0x180005dde  mov     esi, edx
0x180005de0  mov     rbx, rcx
0x180005de3  test    cl, 2
0x180005de6  jnz     short loc_180005E01
0x180005de8  mov     rdx, rcx
0x180005deb  mov     rcx, [r8]
0x180005dee  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x180005df3  mov     [rsp+48h+arg_0], rax
0x180005df8  mov     rdi, rax
0x180005dfb  mov     ebx, dword ptr [rsp+48h+arg_0]
0x180005dff  jmp     short loc_180005E06
0x180005e01  mov     rdi, [rsp+48h+arg_0]
0x180005e06  test    esi, esi
0x180005e08  jz      short loc_180005E2D
0x180005e0a  mov     r8d, esi
0x180005e0d  mov     rdx, rdi
0x180005e10  mov     rcx, r14
0x180005e13  call    wil_details_FeatureReporting_ReportUsageToService
0x180005e18  lea     eax, [rsi-3]
0x180005e1b  cmp     eax, 1
0x180005e1e  ja      short loc_180005E2D
0x180005e20  mov     r8, r14
0x180005e23  mov     edx, esi
0x180005e25  mov     rcx, rdi
0x180005e28  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x180005e2d  and     ebx, 1
0x180005e30  mov     eax, ebx
0x180005e32  add     rsp, 28h
0x180005e36  pop     r14
0x180005e38  pop     rdi
0x180005e39  pop     rsi
0x180005e3a  pop     rbx
0x180005e3b  retn
```

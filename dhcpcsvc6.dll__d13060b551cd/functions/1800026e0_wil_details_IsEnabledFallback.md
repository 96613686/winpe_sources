# wil_details_IsEnabledFallback

- ea: `0x1800026e0`
- end: `0x180002751`
- name: `wil_details_IsEnabledFallback`
- size: `113`
- prototype: `__int64 __fastcall(__int64, int, volatile signed __int32 **)`
- caller_count: `13`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180002e30`
- `0x180003094`
- `0x1800030d8`
- `0x18000311c`
- `0x180003160`
- `0x1800031a4`
- `0x1800031e8`
- `0x18000322c`
- `0x180006e9c`
- `0x180006ee0`
- `0x180006f24`
- `0x180006f68`
- `0x180006fac`

## callees

- `0x1800026e0`
- `0x180002760`
- `0x180007090`
- `0x180007264`

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
0x1800026e0  push    rbx
0x1800026e2  push    rsi
0x1800026e3  push    rdi
0x1800026e4  push    r14
0x1800026e6  sub     rsp, 28h
0x1800026ea  mov     [rsp+48h+arg_0], 0
0x1800026f3  mov     r14, r8
0x1800026f6  mov     dword ptr [rsp+48h+arg_0], ecx
0x1800026fa  mov     esi, edx
0x1800026fc  mov     rbx, rcx
0x1800026ff  test    cl, 2
0x180002702  jnz     short loc_180002716
0x180002704  mov     rdx, rcx
0x180002707  mov     rcx, [r8]
0x18000270a  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x18000270f  mov     rdi, rax
0x180002712  mov     ebx, eax
0x180002714  jmp     short loc_18000271B
0x180002716  mov     rdi, [rsp+48h+arg_0]
0x18000271b  test    esi, esi
0x18000271d  jz      short loc_180002742
0x18000271f  mov     r8d, esi
0x180002722  mov     rdx, rdi
0x180002725  mov     rcx, r14
0x180002728  call    wil_details_FeatureReporting_ReportUsageToService
0x18000272d  lea     eax, [rsi-3]
0x180002730  cmp     eax, 1
0x180002733  ja      short loc_180002742
0x180002735  mov     r8, r14
0x180002738  mov     edx, esi
0x18000273a  mov     rcx, rdi
0x18000273d  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x180002742  and     ebx, 1
0x180002745  mov     eax, ebx
0x180002747  add     rsp, 28h
0x18000274b  pop     r14
0x18000274d  pop     rdi
0x18000274e  pop     rsi
0x18000274f  pop     rbx
0x180002750  retn
```

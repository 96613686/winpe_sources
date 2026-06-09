# wil_details_IsEnabledFallback

- ea: `0x140002ac4`
- end: `0x140002b3d`
- name: `wil_details_IsEnabledFallback`
- size: `121`
- prototype: `__int64 __fastcall(__int64, int, volatile signed __int32 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140002308`
- `0x140002f98`

## callees

- `0x140002600`
- `0x14000280c`
- `0x140002a6c`
- `0x140002ac4`

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
0x140002ac4  push    rbx
0x140002ac6  push    rsi
0x140002ac7  push    rdi
0x140002ac8  push    r14
0x140002aca  sub     rsp, 28h
0x140002ace  mov     [rsp+48h+arg_0], 0
0x140002ad7  mov     r14, r8
0x140002ada  mov     dword ptr [rsp+48h+arg_0], ecx
0x140002ade  mov     esi, edx
0x140002ae0  mov     rbx, rcx
0x140002ae3  test    cl, 2
0x140002ae6  jnz     short loc_140002B01
0x140002ae8  mov     rdx, rcx
0x140002aeb  mov     rcx, [r8]
0x140002aee  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x140002af3  mov     [rsp+48h+arg_0], rax
0x140002af8  mov     rdi, rax
0x140002afb  mov     ebx, dword ptr [rsp+48h+arg_0]
0x140002aff  jmp     short loc_140002B06
0x140002b01  mov     rdi, [rsp+48h+arg_0]
0x140002b06  test    esi, esi
0x140002b08  jz      short loc_140002B2D
0x140002b0a  mov     r8d, esi
0x140002b0d  mov     rdx, rdi
0x140002b10  mov     rcx, r14
0x140002b13  call    wil_details_FeatureReporting_ReportUsageToService
0x140002b18  lea     eax, [rsi-3]
0x140002b1b  cmp     eax, 1
0x140002b1e  ja      short loc_140002B2D
0x140002b20  mov     r8, r14
0x140002b23  mov     edx, esi
0x140002b25  mov     rcx, rdi
0x140002b28  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x140002b2d  and     ebx, 1
0x140002b30  mov     eax, ebx
0x140002b32  add     rsp, 28h
0x140002b36  pop     r14
0x140002b38  pop     rdi
0x140002b39  pop     rsi
0x140002b3a  pop     rbx
0x140002b3b  retn
```

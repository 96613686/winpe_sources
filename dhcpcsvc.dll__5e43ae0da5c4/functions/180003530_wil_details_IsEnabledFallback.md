# wil_details_IsEnabledFallback

- ea: `0x180003530`
- end: `0x1800035a8`
- name: `wil_details_IsEnabledFallback`
- size: `120`
- prototype: ``
- caller_count: `13`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180003370`
- `0x180003414`
- `0x180003428`
- `0x18000343c`
- `0x180003480`
- `0x1800034c4`
- `0x180003508`
- `0x18000351c`
- `0x1800104bc`
- `0x180010500`
- `0x180010544`
- `0x180010588`
- `0x1800105cc`

## callees

- `0x180003530`
- `0x1800035b0`
- `0x1800037dc`
- `0x180003ae8`

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
0x180003530  push    rbx
0x180003532  push    rsi
0x180003533  push    rdi
0x180003534  push    r14
0x180003536  sub     rsp, 28h
0x18000353a  mov     [rsp+48h+arg_0], 0
0x180003543  mov     r14, r8
0x180003546  mov     dword ptr [rsp+48h+arg_0], ecx
0x18000354a  mov     esi, edx
0x18000354c  mov     rbx, rcx
0x18000354f  test    cl, 2
0x180003552  jnz     short loc_18000356D
0x180003554  mov     rdx, rcx
0x180003557  mov     rcx, [r8]
0x18000355a  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x18000355f  mov     [rsp+48h+arg_0], rax
0x180003564  mov     rdi, rax
0x180003567  mov     ebx, dword ptr [rsp+48h+arg_0]
0x18000356b  jmp     short loc_180003572
0x18000356d  mov     rdi, [rsp+48h+arg_0]
0x180003572  test    esi, esi
0x180003574  jz      short loc_180003599
0x180003576  mov     r8d, esi
0x180003579  mov     rdx, rdi
0x18000357c  mov     rcx, r14
0x18000357f  call    wil_details_FeatureReporting_ReportUsageToService
0x180003584  lea     eax, [rsi-3]
0x180003587  cmp     eax, 1
0x18000358a  ja      short loc_180003599
0x18000358c  mov     r8, r14
0x18000358f  mov     edx, esi
0x180003591  mov     rcx, rdi
0x180003594  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x180003599  and     ebx, 1
0x18000359c  mov     eax, ebx
0x18000359e  add     rsp, 28h
0x1800035a2  pop     r14
0x1800035a4  pop     rdi
0x1800035a5  pop     rsi
0x1800035a6  pop     rbx
0x1800035a7  retn
```

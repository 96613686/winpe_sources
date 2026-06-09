# Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_IsEnabledDeviceUsageNoInline

- ea: `0x1800031fc`
- end: `0x180003226`
- name: `Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_IsEnabledDeviceUsageNoInline`
- size: `42`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000456c`

## callees

- `0x1800031fc`
- `0x18000322c`

## pseudocode

```c
__int64 Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_IsEnabledDeviceUsageNoInline()
{
  if ( (Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_featureState & 0x10) != 0 )
    return Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_featureState & 1;
  else
    return Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_IsEnabledFallback(
             (unsigned int)Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_featureState,
             3);
}

```

## disassembly

```asm
0x1800031fc  mov     eax, cs:Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_featureState
0x180003202  mov     [rsp+arg_0], 0
0x18000320b  mov     dword ptr [rsp+arg_0], eax
0x18000320f  test    al, 10h
0x180003211  jz      short loc_180003217
0x180003213  and     eax, 1
0x180003216  retn
0x180003217  mov     rcx, [rsp+arg_0]
0x18000321c  mov     edx, 3
0x180003221  jmp     Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_IsEnabledFallback
```

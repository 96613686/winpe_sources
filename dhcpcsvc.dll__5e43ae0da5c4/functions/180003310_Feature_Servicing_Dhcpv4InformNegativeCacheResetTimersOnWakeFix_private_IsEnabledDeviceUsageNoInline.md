# Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_IsEnabledDeviceUsageNoInline

- ea: `0x180003310`
- end: `0x18000333a`
- name: `Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_IsEnabledDeviceUsageNoInline`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180004014`

## callees

- `0x180003310`
- `0x180003428`

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
0x180003310  mov     eax, cs:Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_featureState
0x180003316  mov     [rsp+arg_0], 0
0x18000331f  mov     dword ptr [rsp+arg_0], eax
0x180003323  test    al, 10h
0x180003325  jz      short loc_18000332B
0x180003327  and     eax, 1
0x18000332a  retn
0x18000332b  mov     rcx, [rsp+arg_0]
0x180003330  mov     edx, 3
0x180003335  jmp     Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_IsEnabledFallback
```

# Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_IsEnabledDeviceUsageNoInline

- ea: `0x18002db48`
- end: `0x18002db73`
- name: `Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_IsEnabledDeviceUsageNoInline`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18002d7d8`

## callees

- `0x18002db48`
- `0x18002db7c`

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
0x18002db48  mov     eax, cs:Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_featureState
0x18002db4e  mov     [rsp+arg_0], 0
0x18002db57  mov     dword ptr [rsp+arg_0], eax
0x18002db5b  test    al, 10h
0x18002db5d  jz      short loc_18002DB64
0x18002db5f  and     eax, 1
0x18002db62  retn
0x18002db64  mov     rcx, [rsp+arg_0]
0x18002db69  mov     edx, 3
0x18002db6e  jmp     Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_IsEnabledFallback
```

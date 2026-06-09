# Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_IsEnabledFallback

- ea: `0x18000322c`
- end: `0x180003238`
- name: `Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_IsEnabledFallback`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800031fc`

## callees

- `0x1800026e0`

## pseudocode

```c
__int64 __fastcall Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_IsEnabledFallback(
        __int64 a1,
        __int64 a2)
{
  return wil_details_IsEnabledFallback(
           a1,
           a2,
           Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_descriptor);
}

```

## disassembly

```asm
0x18000322c  lea     r8, Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_descriptor
0x180003233  jmp     wil_details_IsEnabledFallback
```

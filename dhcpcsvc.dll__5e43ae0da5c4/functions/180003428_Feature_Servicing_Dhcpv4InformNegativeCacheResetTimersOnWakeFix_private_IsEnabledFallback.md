# Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_IsEnabledFallback

- ea: `0x180003428`
- end: `0x180003434`
- name: `Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_IsEnabledFallback`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180003310`

## callees

- `0x180003530`

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
0x180003428  lea     r8, Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_descriptor
0x18000342f  jmp     wil_details_IsEnabledFallback
```

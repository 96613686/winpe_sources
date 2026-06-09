# Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_IsEnabledFallback

- ea: `0x18002db7c`
- end: `0x18002db88`
- name: `Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_IsEnabledFallback`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18002db48`

## callees

- `0x18002d67c`

## pseudocode

```c
__int64 __fastcall Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_IsEnabledFallback(
        __int64 a1,
        unsigned int a2)
{
  return wil_details_IsEnabledFallback(
           a1,
           a2,
           Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_descriptor);
}

```

## disassembly

```asm
0x18002db7c  lea     r8, Feature_Servicing_Dhcpv4InformNegativeCacheResetTimersOnWakeFix__private_descriptor
0x18002db83  jmp     wil_details_IsEnabledFallback
```

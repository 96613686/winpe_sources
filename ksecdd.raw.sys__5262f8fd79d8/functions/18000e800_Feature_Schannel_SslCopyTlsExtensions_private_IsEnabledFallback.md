# Feature_Schannel_SslCopyTlsExtensions__private_IsEnabledFallback

- ea: `0x18000e800`
- end: `0x18000e80f`
- name: `Feature_Schannel_SslCopyTlsExtensions__private_IsEnabledFallback`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000e7c4`

## callees

- `0x18000f348`

## pseudocode

```c
__int64 Feature_Schannel_SslCopyTlsExtensions__private_IsEnabledFallback()
{
  return wil_details_IsEnabledFallback();
}

```

## disassembly

```asm
0x18000e800  sub     rsp, 28h
0x18000e804  call    wil_details_IsEnabledFallback
0x18000e809  add     rsp, 28h
0x18000e80d  retn
```

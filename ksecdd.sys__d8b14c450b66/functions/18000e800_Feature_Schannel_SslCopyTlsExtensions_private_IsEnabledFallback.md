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

- `0x18000f2e0`

## pseudocode

```c
__int64 __fastcall Feature_Schannel_SslCopyTlsExtensions__private_IsEnabledFallback(__int64 a1, unsigned int a2)
{
  return wil_details_IsEnabledFallback(a1, a2);
}

```

## disassembly

```asm
0x18000e800  sub     rsp, 28h
0x18000e804  call    wil_details_IsEnabledFallback
0x18000e809  add     rsp, 28h
0x18000e80d  retn
```

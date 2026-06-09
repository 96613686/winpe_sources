# Feature_ShadowAdminAppCompat__private_IsEnabledFallback

- ea: `0x140001b18`
- end: `0x140001b2e`
- name: `Feature_ShadowAdminAppCompat__private_IsEnabledFallback`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001adc`

## callees

- `0x140001b8c`

## pseudocode

```c
__int64 __fastcall Feature_ShadowAdminAppCompat__private_IsEnabledFallback(__int64 a1, __int64 a2)
{
  return wil_details_IsEnabledFallback(a1, a2, Feature_ShadowAdminAppCompat__private_descriptor);
}

```

## disassembly

```asm
0x140001b18  sub     rsp, 28h
0x140001b1c  lea     r8, Feature_ShadowAdminAppCompat__private_descriptor
0x140001b23  call    wil_details_IsEnabledFallback
0x140001b28  add     rsp, 28h
0x140001b2c  retn
```

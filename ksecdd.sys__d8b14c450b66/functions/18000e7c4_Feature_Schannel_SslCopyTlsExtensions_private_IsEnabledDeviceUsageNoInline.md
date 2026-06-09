# Feature_Schannel_SslCopyTlsExtensions__private_IsEnabledDeviceUsageNoInline

- ea: `0x18000e7c4`
- end: `0x18000e7f9`
- name: `Feature_Schannel_SslCopyTlsExtensions__private_IsEnabledDeviceUsageNoInline`
- size: `53`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000e820`

## callees

- `0x18000e7c4`
- `0x18000e800`

## pseudocode

```c
__int64 Feature_Schannel_SslCopyTlsExtensions__private_IsEnabledDeviceUsageNoInline()
{
  if ( (Feature_Schannel_SslCopyTlsExtensions__private_featureState & 0x10) != 0 )
    return Feature_Schannel_SslCopyTlsExtensions__private_featureState & 1;
  else
    return Feature_Schannel_SslCopyTlsExtensions__private_IsEnabledFallback(
             (unsigned int)Feature_Schannel_SslCopyTlsExtensions__private_featureState,
             3);
}

```

## disassembly

```asm
0x18000e7c4  sub     rsp, 28h
0x18000e7c8  mov     eax, cs:Feature_Schannel_SslCopyTlsExtensions__private_featureState
0x18000e7ce  mov     [rsp+28h+arg_0], 0
0x18000e7d7  mov     dword ptr [rsp+28h+arg_0], eax
0x18000e7db  test    al, 10h
0x18000e7dd  jz      short loc_18000E7E4
0x18000e7df  and     eax, 1
0x18000e7e2  jmp     short loc_18000E7F3
0x18000e7e4  mov     rcx, [rsp+28h+arg_0]
0x18000e7e9  mov     edx, 3
0x18000e7ee  call    Feature_Schannel_SslCopyTlsExtensions__private_IsEnabledFallback
0x18000e7f3  add     rsp, 28h
0x18000e7f7  retn
```

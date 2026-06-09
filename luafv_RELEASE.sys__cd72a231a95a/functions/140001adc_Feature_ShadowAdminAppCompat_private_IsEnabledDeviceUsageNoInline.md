# Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline

- ea: `0x140001adc`
- end: `0x140001b11`
- name: `Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline`
- size: `53`
- prototype: `__int64()`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001440`
- `0x140003290`
- `0x1400164f0`
- `0x140017850`
- `0x140018220`
- `0x140019730`
- `0x140019f40`
- `0x140021a20`
- `0x140025300`
- `0x140025820`

## callees

- `0x140001adc`
- `0x140001b18`

## pseudocode

```c
__int64 Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline()
{
  if ( (Feature_ShadowAdminAppCompat__private_featureState & 0x10) != 0 )
    return Feature_ShadowAdminAppCompat__private_featureState & 1;
  else
    return Feature_ShadowAdminAppCompat__private_IsEnabledFallback(
             (unsigned int)Feature_ShadowAdminAppCompat__private_featureState,
             3);
}

```

## disassembly

```asm
0x140001adc  sub     rsp, 28h
0x140001ae0  mov     eax, cs:Feature_ShadowAdminAppCompat__private_featureState
0x140001ae6  mov     [rsp+28h+arg_0], 0
0x140001aef  mov     dword ptr [rsp+28h+arg_0], eax
0x140001af3  test    al, 10h
0x140001af5  jz      short loc_140001AFC
0x140001af7  and     eax, 1
0x140001afa  jmp     short loc_140001B0B
0x140001afc  mov     rcx, [rsp+28h+arg_0]
0x140001b01  mov     edx, 3
0x140001b06  call    Feature_ShadowAdminAppCompat__private_IsEnabledFallback
0x140001b0b  add     rsp, 28h
0x140001b0f  retn
```

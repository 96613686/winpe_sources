# Feature_KG_Ncrypt_Telemetry__private_IsEnabledDeviceUsageNoInline

- ea: `0x180018e18`
- end: `0x180018e42`
- name: `Feature_KG_Ncrypt_Telemetry__private_IsEnabledDeviceUsageNoInline`
- size: `42`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800102c0`
- `0x180013a7c`
- `0x180013d38`
- `0x1800175f0`
- `0x180017990`

## callees

- `0x180018e18`
- `0x18001b9d0`

## pseudocode

```c
__int64 Feature_KG_Ncrypt_Telemetry__private_IsEnabledDeviceUsageNoInline()
{
  if ( (Feature_KG_Ncrypt_Telemetry__private_featureState & 0x10) != 0 )
    return Feature_KG_Ncrypt_Telemetry__private_featureState & 1;
  else
    return Feature_KG_Ncrypt_Telemetry__private_IsEnabledFallback(
             (unsigned int)Feature_KG_Ncrypt_Telemetry__private_featureState,
             3);
}

```

## disassembly

```asm
0x180018e18  mov     eax, cs:Feature_KG_Ncrypt_Telemetry__private_featureState
0x180018e1e  mov     [rsp+arg_0], 0
0x180018e27  mov     dword ptr [rsp+arg_0], eax
0x180018e2b  test    al, 10h
0x180018e2d  jz      short loc_180018E33
0x180018e2f  and     eax, 1
0x180018e32  retn
0x180018e33  mov     rcx, [rsp+arg_0]
0x180018e38  mov     edx, 3
0x180018e3d  jmp     Feature_KG_Ncrypt_Telemetry__private_IsEnabledFallback
```

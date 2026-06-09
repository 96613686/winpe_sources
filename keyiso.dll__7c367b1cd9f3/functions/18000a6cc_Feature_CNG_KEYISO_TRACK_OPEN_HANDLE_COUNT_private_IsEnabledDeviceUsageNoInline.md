# Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__private_IsEnabledDeviceUsageNoInline

- ea: `0x18000a6cc`
- end: `0x18000a6f6`
- name: `Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__private_IsEnabledDeviceUsageNoInline`
- size: `42`
- prototype: `__int64(void)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x180003880`
- `0x180004550`
- `0x180005540`
- `0x18000a0a8`
- `0x18000a13c`
- `0x18000a1dc`
- `0x18000a268`
- `0x18000a484`
- `0x18000a520`
- `0x18000a5c0`
- `0x18000a638`

## callees

- `0x18000a6cc`
- `0x18000a6fc`

## pseudocode

```c
__int64 Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__private_IsEnabledDeviceUsageNoInline()
{
  if ( (Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__private_featureState & 0x10) != 0 )
    return Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__private_featureState & 1;
  else
    return Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__private_IsEnabledFallback(
             (unsigned int)Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__private_featureState,
             3);
}

```

## disassembly

```asm
0x18000a6cc  mov     eax, cs:Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__private_featureState
0x18000a6d2  mov     [rsp+arg_0], 0
0x18000a6db  mov     dword ptr [rsp+arg_0], eax
0x18000a6df  test    al, 10h
0x18000a6e1  jz      short loc_18000A6E7
0x18000a6e3  and     eax, 1
0x18000a6e6  retn
0x18000a6e7  mov     rcx, [rsp+arg_0]
0x18000a6ec  mov     edx, 3
0x18000a6f1  jmp     Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__private_IsEnabledFallback
```

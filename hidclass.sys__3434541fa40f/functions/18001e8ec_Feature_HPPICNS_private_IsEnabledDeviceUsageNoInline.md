# Feature_HPPICNS__private_IsEnabledDeviceUsageNoInline

- ea: `0x18001e8ec`
- end: `0x18001e921`
- name: `Feature_HPPICNS__private_IsEnabledDeviceUsageNoInline`
- size: `53`
- prototype: ``
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x180015438`
- `0x180015b98`
- `0x180019694`
- `0x18001a1cc`
- `0x18001a560`
- `0x18001a5b0`
- `0x18001a6b0`
- `0x18001a708`
- `0x18001a7cc`
- `0x18002136c`
- `0x180023b44`
- `0x18003b444`
- `0x18003e5b0`
- `0x180042b00`
- `0x180042f24`

## callees

- `0x18001e8ec`
- `0x18001e928`

## pseudocode

```c
__int64 Feature_HPPICNS__private_IsEnabledDeviceUsageNoInline()
{
  if ( (Feature_HPPICNS__private_featureState & 0x10) != 0 )
    return Feature_HPPICNS__private_featureState & 1;
  else
    return Feature_HPPICNS__private_IsEnabledFallback((unsigned int)Feature_HPPICNS__private_featureState, 3);
}

```

## disassembly

```asm
0x18001e8ec  sub     rsp, 28h
0x18001e8f0  mov     eax, cs:Feature_HPPICNS__private_featureState
0x18001e8f6  mov     [rsp+28h+arg_0], 0
0x18001e8ff  mov     dword ptr [rsp+28h+arg_0], eax
0x18001e903  test    al, 10h
0x18001e905  jz      short loc_18001E90C
0x18001e907  and     eax, 1
0x18001e90a  jmp     short loc_18001E91B
0x18001e90c  mov     rcx, [rsp+28h+arg_0]
0x18001e911  mov     edx, 3
0x18001e916  call    Feature_HPPICNS__private_IsEnabledFallback
0x18001e91b  add     rsp, 28h
0x18001e91f  retn
```

# Feature_HCTI01__private_IsEnabledDeviceUsageNoInline

- ea: `0x18001b744`
- end: `0x18001b779`
- name: `Feature_HCTI01__private_IsEnabledDeviceUsageNoInline`
- size: `53`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x18000621c`
- `0x180006ac8`
- `0x18000b140`
- `0x18000c5c0`
- `0x18000e004`
- `0x18000e438`
- `0x18001b4f0`
- `0x18001b704`
- `0x180023b44`
- `0x180037e60`
- `0x1800385f0`

## callees

- `0x18001b744`
- `0x18001b780`

## pseudocode

```c
__int64 Feature_HCTI01__private_IsEnabledDeviceUsageNoInline()
{
  if ( (Feature_HCTI01__private_featureState & 0x10) != 0 )
    return Feature_HCTI01__private_featureState & 1;
  else
    return Feature_HCTI01__private_IsEnabledFallback((unsigned int)Feature_HCTI01__private_featureState, 3);
}

```

## disassembly

```asm
0x18001b744  sub     rsp, 28h
0x18001b748  mov     eax, cs:Feature_HCTI01__private_featureState
0x18001b74e  mov     [rsp+28h+arg_0], 0
0x18001b757  mov     dword ptr [rsp+28h+arg_0], eax
0x18001b75b  test    al, 10h
0x18001b75d  jz      short loc_18001B764
0x18001b75f  and     eax, 1
0x18001b762  jmp     short loc_18001B773
0x18001b764  mov     rcx, [rsp+28h+arg_0]
0x18001b769  mov     edx, 3
0x18001b76e  call    Feature_HCTI01__private_IsEnabledFallback
0x18001b773  add     rsp, 28h
0x18001b777  retn
```

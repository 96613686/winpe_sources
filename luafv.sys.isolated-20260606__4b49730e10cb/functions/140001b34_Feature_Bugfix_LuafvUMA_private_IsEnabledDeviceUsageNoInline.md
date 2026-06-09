# Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline

- ea: `0x140001b34`
- end: `0x140001b69`
- name: `Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline`
- size: `53`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140014df0`
- `0x1400220ac`
- `0x1400240a0`
- `0x140024664`

## callees

- `0x140001b34`
- `0x140001b70`

## pseudocode

```c
__int64 Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline()
{
  if ( (Feature_Bugfix_LuafvUMA__private_featureState & 0x10) != 0 )
    return Feature_Bugfix_LuafvUMA__private_featureState & 1;
  else
    return Feature_Bugfix_LuafvUMA__private_IsEnabledFallback(
             (unsigned int)Feature_Bugfix_LuafvUMA__private_featureState,
             3);
}

```

## disassembly

```asm
0x140001b34  sub     rsp, 28h
0x140001b38  mov     eax, cs:Feature_Bugfix_LuafvUMA__private_featureState
0x140001b3e  mov     [rsp+28h+arg_0], 0
0x140001b47  mov     dword ptr [rsp+28h+arg_0], eax
0x140001b4b  test    al, 10h
0x140001b4d  jz      short loc_140001B54
0x140001b4f  and     eax, 1
0x140001b52  jmp     short loc_140001B63
0x140001b54  mov     rcx, [rsp+28h+arg_0]
0x140001b59  mov     edx, 3
0x140001b5e  call    Feature_Bugfix_LuafvUMA__private_IsEnabledFallback
0x140001b63  add     rsp, 28h
0x140001b67  retn
```

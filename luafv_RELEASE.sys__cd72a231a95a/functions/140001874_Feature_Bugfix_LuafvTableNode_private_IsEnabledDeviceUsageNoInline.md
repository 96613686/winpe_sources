# Feature_Bugfix_LuafvTableNode__private_IsEnabledDeviceUsageNoInline

- ea: `0x140001874`
- end: `0x1400018a9`
- name: `Feature_Bugfix_LuafvTableNode__private_IsEnabledDeviceUsageNoInline`
- size: `53`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140001730`
- `0x140015bb0`
- `0x14001a378`
- `0x14001d010`

## callees

- `0x140001874`
- `0x140001ac0`

## pseudocode

```c
__int64 Feature_Bugfix_LuafvTableNode__private_IsEnabledDeviceUsageNoInline()
{
  if ( (Feature_Bugfix_LuafvTableNode__private_featureState & 0x10) != 0 )
    return Feature_Bugfix_LuafvTableNode__private_featureState & 1;
  else
    return Feature_Bugfix_LuafvTableNode__private_IsEnabledFallback(
             (unsigned int)Feature_Bugfix_LuafvTableNode__private_featureState,
             3);
}

```

## disassembly

```asm
0x140001874  sub     rsp, 28h
0x140001878  mov     eax, cs:Feature_Bugfix_LuafvTableNode__private_featureState
0x14000187e  mov     [rsp+28h+arg_0], 0
0x140001887  mov     dword ptr [rsp+28h+arg_0], eax
0x14000188b  test    al, 10h
0x14000188d  jnz     short loc_1400018A4
0x14000188f  mov     rcx, [rsp+28h+arg_0]
0x140001894  mov     edx, 3
0x140001899  call    Feature_Bugfix_LuafvTableNode__private_IsEnabledFallback
0x14000189e  add     rsp, 28h
0x1400018a2  retn
0x1400018a4  and     eax, 1
0x1400018a7  jmp     short loc_14000189E
```

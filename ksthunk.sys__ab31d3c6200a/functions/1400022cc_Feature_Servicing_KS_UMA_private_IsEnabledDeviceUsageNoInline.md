# Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline

- ea: `0x1400022cc`
- end: `0x140002301`
- name: `Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline`
- size: `53`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140001ba0`

## callees

- `0x1400022cc`
- `0x140002308`

## pseudocode

```c
__int64 Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline()
{
  if ( (Feature_Servicing_KS_UMA__private_featureState & 0x10) != 0 )
    return Feature_Servicing_KS_UMA__private_featureState & 1;
  else
    return Feature_Servicing_KS_UMA__private_IsEnabledFallback(
             (unsigned int)Feature_Servicing_KS_UMA__private_featureState,
             3);
}

```

## disassembly

```asm
0x1400022cc  sub     rsp, 28h
0x1400022d0  mov     eax, cs:Feature_Servicing_KS_UMA__private_featureState
0x1400022d6  mov     [rsp+28h+arg_0], 0
0x1400022df  mov     dword ptr [rsp+28h+arg_0], eax
0x1400022e3  test    al, 10h
0x1400022e5  jz      short loc_1400022EC
0x1400022e7  and     eax, 1
0x1400022ea  jmp     short loc_1400022FB
0x1400022ec  mov     rcx, [rsp+28h+arg_0]
0x1400022f1  mov     edx, 3
0x1400022f6  call    Feature_Servicing_KS_UMA__private_IsEnabledFallback
0x1400022fb  add     rsp, 28h
0x1400022ff  retn
```

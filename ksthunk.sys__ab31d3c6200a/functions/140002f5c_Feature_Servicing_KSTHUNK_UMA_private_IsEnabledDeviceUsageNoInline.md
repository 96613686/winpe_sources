# Feature_Servicing_KSTHUNK_UMA__private_IsEnabledDeviceUsageNoInline

- ea: `0x140002f5c`
- end: `0x140002f91`
- name: `Feature_Servicing_KSTHUNK_UMA__private_IsEnabledDeviceUsageNoInline`
- size: `53`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140003728`
- `0x140003d50`
- `0x14000bfc4`

## callees

- `0x140002f5c`
- `0x140002f98`

## pseudocode

```c
__int64 Feature_Servicing_KSTHUNK_UMA__private_IsEnabledDeviceUsageNoInline()
{
  if ( (Feature_Servicing_KSTHUNK_UMA__private_featureState & 0x10) != 0 )
    return Feature_Servicing_KSTHUNK_UMA__private_featureState & 1;
  else
    return Feature_Servicing_KSTHUNK_UMA__private_IsEnabledFallback(
             (unsigned int)Feature_Servicing_KSTHUNK_UMA__private_featureState,
             3);
}

```

## disassembly

```asm
0x140002f5c  sub     rsp, 28h
0x140002f60  mov     eax, cs:Feature_Servicing_KSTHUNK_UMA__private_featureState
0x140002f66  mov     [rsp+28h+arg_0], 0
0x140002f6f  mov     dword ptr [rsp+28h+arg_0], eax
0x140002f73  test    al, 10h
0x140002f75  jz      short loc_140002F7C
0x140002f77  and     eax, 1
0x140002f7a  jmp     short loc_140002F8B
0x140002f7c  mov     rcx, [rsp+28h+arg_0]
0x140002f81  mov     edx, 3
0x140002f86  call    Feature_Servicing_KSTHUNK_UMA__private_IsEnabledFallback
0x140002f8b  add     rsp, 28h
0x140002f8f  retn
```

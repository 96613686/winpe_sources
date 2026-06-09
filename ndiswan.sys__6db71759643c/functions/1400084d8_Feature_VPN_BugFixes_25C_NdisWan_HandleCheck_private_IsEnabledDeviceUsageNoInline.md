# Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline

- ea: `0x1400084d8`
- end: `0x14000850d`
- name: `Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline`
- size: `53`
- prototype: ``
- caller_count: `30`
- callee_count: `2`
- tags: ``

## callers

- `0x140001be0`
- `0x140002e40`
- `0x140004be0`
- `0x140007560`
- `0x140007710`
- `0x140007a00`
- `0x140007bf0`
- `0x140007dd0`
- `0x140007fb0`
- `0x140024008`
- `0x140025070`
- `0x140025c80`
- `0x1400267f4`
- `0x140026970`
- `0x140026c80`
- `0x1400274e0`
- `0x140027a50`
- `0x140027da0`
- `0x140027fe0`
- `0x140028610`
- `0x1400288a0`
- `0x140028f60`
- `0x1400296d0`
- `0x140029850`
- `0x14002a0f0`
- `0x14002a4e0`
- `0x14002aa40`
- `0x14002b270`
- `0x14002bab0`
- `0x14002bd20`

## callees

- `0x1400084d8`
- `0x140008514`

## pseudocode

```c
__int64 Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline()
{
  if ( (Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 0x10) != 0 )
    return Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 1;
  else
    return Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledFallback(
             (unsigned int)Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState,
             3);
}

```

## disassembly

```asm
0x1400084d8  sub     rsp, 28h
0x1400084dc  mov     eax, cs:Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState
0x1400084e2  mov     [rsp+28h+arg_0], 0
0x1400084eb  mov     dword ptr [rsp+28h+arg_0], eax
0x1400084ef  test    al, 10h
0x1400084f1  jz      short loc_1400084F8
0x1400084f3  and     eax, 1
0x1400084f6  jmp     short loc_140008507
0x1400084f8  mov     rcx, [rsp+28h+arg_0]
0x1400084fd  mov     edx, 3
0x140008502  call    Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledFallback
0x140008507  add     rsp, 28h
0x14000850b  retn
```

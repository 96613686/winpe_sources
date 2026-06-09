# _CDpSearchProtocol::CreateAccessorEx_::_1_::catch$10

- ea: `0x18000b054`
- end: `0x18000b0a1`
- name: `_CDpSearchProtocol::CreateAccessorEx_::_1_::catch$10`
- size: `77`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002de4`
- `0x18000b054`

## pseudocode

```c
__int64 CDpSearchProtocol::CreateAccessorEx_::_1_::catch_10()
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_67d934e699f83311671b1011635d052f_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x18000b054  mov     [rsp+arg_8], rdx
0x18000b059  push    rbp
0x18000b05a  sub     rsp, 30h
0x18000b05e  mov     rbp, rdx
0x18000b061  lea     rax, WPP_GLOBAL_Control
0x18000b068  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b06f  cmp     rcx, rax
0x18000b072  jz      short loc_18000B090
0x18000b074  test    byte ptr [rcx+1Ch], 1
0x18000b078  jz      short loc_18000B090
0x18000b07a  mov     edx, 0Ch
0x18000b07f  lea     r8, WPP_67d934e699f83311671b1011635d052f_Traceguids
0x18000b086  mov     rcx, [rcx+10h]
0x18000b08a  call    WPP_SF_
0x18000b08f  nop
0x18000b090  mov     rax, 0
0x18000b09a  add     rsp, 30h
0x18000b09e  pop     rbp
0x18000b09f  retn
```

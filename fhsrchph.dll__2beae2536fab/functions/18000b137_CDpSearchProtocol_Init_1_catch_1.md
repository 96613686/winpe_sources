# _CDpSearchProtocol::Init_::_1_::catch$1

- ea: `0x18000b137`
- end: `0x18000b184`
- name: `_CDpSearchProtocol::Init_::_1_::catch$1`
- size: `77`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002de4`
- `0x18000b137`

## pseudocode

```c
__int64 CDpSearchProtocol::Init_::_1_::catch_1()
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_67d934e699f83311671b1011635d052f_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x18000b137  mov     [rsp+arg_8], rdx
0x18000b13c  push    rbp
0x18000b13d  sub     rsp, 20h
0x18000b141  mov     rbp, rdx
0x18000b144  lea     rax, WPP_GLOBAL_Control
0x18000b14b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b152  cmp     rcx, rax
0x18000b155  jz      short loc_18000B173
0x18000b157  test    byte ptr [rcx+1Ch], 1
0x18000b15b  jz      short loc_18000B173
0x18000b15d  mov     edx, 0Ah
0x18000b162  lea     r8, WPP_67d934e699f83311671b1011635d052f_Traceguids
0x18000b169  mov     rcx, [rcx+10h]
0x18000b16d  call    WPP_SF_
0x18000b172  nop
0x18000b173  mov     rax, 0
0x18000b17d  add     rsp, 20h
0x18000b181  pop     rbp
0x18000b182  retn
```

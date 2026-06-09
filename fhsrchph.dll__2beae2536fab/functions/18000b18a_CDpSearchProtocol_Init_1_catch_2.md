# _CDpSearchProtocol::Init_::_1_::catch$2

- ea: `0x18000b18a`
- end: `0x18000b1de`
- name: `_CDpSearchProtocol::Init_::_1_::catch$2`
- size: `84`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800068c4`
- `0x18000b18a`

## pseudocode

```c
__int64 __fastcall CDpSearchProtocol::Init_::_1_::catch_2(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_67d934e699f83311671b1011635d052f_Traceguids,
      **(unsigned int **)(a2 + 32));
  return 0;
}

```

## disassembly

```asm
0x18000b18a  mov     [rsp+arg_8], rdx
0x18000b18f  push    rbp
0x18000b190  sub     rsp, 20h
0x18000b194  mov     rbp, rdx
0x18000b197  lea     rax, WPP_GLOBAL_Control
0x18000b19e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b1a5  cmp     rcx, rax
0x18000b1a8  jz      short loc_18000B1CD
0x18000b1aa  test    byte ptr [rcx+1Ch], 1
0x18000b1ae  jz      short loc_18000B1CD
0x18000b1b0  mov     edx, 0Bh
0x18000b1b5  mov     r9, [rbp+20h]
0x18000b1b9  mov     r9d, [r9]
0x18000b1bc  lea     r8, WPP_67d934e699f83311671b1011635d052f_Traceguids
0x18000b1c3  mov     rcx, [rcx+10h]
0x18000b1c7  call    WPP_SF_D
0x18000b1cc  nop
0x18000b1cd  mov     rax, 0
0x18000b1d7  add     rsp, 20h
0x18000b1db  pop     rbp
0x18000b1dc  retn
```

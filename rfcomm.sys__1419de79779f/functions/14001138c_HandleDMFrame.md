# HandleDMFrame

- ea: `0x14001138c`
- end: `0x1400114b7`
- name: `HandleDMFrame`
- size: `299`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400147a0`

## callees

- `0x140003bf4`
- `0x14000fd78`
- `0x14001138c`
- `0x1400161d0`
- `0x140017db4`
- `0x140019b64`
- `0x140019e5c`
- `0x14001ea34`

## string_xrefs

- `0x140011440`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`

## pseudocode

```c
__int64 __fastcall HandleDMFrame(__int64 a1, _BYTE *a2)
{
  char v4; // dl
  int v5; // edx
  __int64 *Locked; // rax
  int v7; // edx
  __int64 v8; // rbx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      3,
      145,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  v4 = *a2 >> 2;
  if ( v4 )
  {
    Locked = ChannelFindLocked(a1, v4, 0);
    v8 = (__int64)Locked;
    if ( Locked )
    {
      ChannelDisconnectInd(Locked, 2, 3221226320LL);
      ChannelAckCommand(v8, 0, -1073741299);
      RefObj_ReleaseEx(v8 + 24, 1145981254, 4832, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return 4;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        2,
        146,
        (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
    }
  }
  else
  {
    SessionAckCommand(a1, 0, -1073741299);
    SessionDisconnectInd(a1, 1, 0xC00000C3, 1);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      3,
      147,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  return 4;
}

```

## disassembly

```asm
0x14001138c  push    rbx
0x14001138e  push    rbp
0x14001138f  push    rsi
0x140011390  push    rdi
0x140011391  sub     rsp, 38h
0x140011395  mov     rdi, rdx
0x140011398  mov     rbx, rcx
0x14001139b  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400113a2  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400113a9  lea     rbp, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x1400113b0  jz      short loc_1400113D3
0x1400113b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400113b9  mov     r9d, 91h
0x1400113bf  mov     r8d, 3
0x1400113c5  mov     [rsp+58h+var_38], rbp
0x1400113ca  mov     rcx, [rcx+40h]
0x1400113ce  call    WPP_RECORDER_SF_
0x1400113d3  mov     al, [rdi]
0x1400113d5  mov     rcx, rbx
0x1400113d8  shr     al, 2
0x1400113db  mov     dl, al
0x1400113dd  test    al, al
0x1400113df  jnz     short loc_140011404
0x1400113e1  xor     edx, edx
0x1400113e3  mov     r8d, 0C000020Dh
0x1400113e9  call    SessionAckCommand
0x1400113ee  mov     r9b, 1
0x1400113f1  mov     r8d, 0C00000C3h
0x1400113f7  mov     dl, r9b
0x1400113fa  mov     rcx, rbx
0x1400113fd  call    SessionDisconnectInd
0x140011402  jmp     short loc_14001147E
0x140011404  xor     r8d, r8d
0x140011407  call    ChannelFindLocked
0x14001140c  mov     rbx, rax
0x14001140f  test    rax, rax
0x140011412  jz      short loc_140011454
0x140011414  mov     edx, 2
0x140011419  mov     r8d, 0C0000350h
0x14001141f  mov     rcx, rax
0x140011422  call    ChannelDisconnectInd
0x140011427  xor     edx, edx
0x140011429  mov     r8d, 0C000020Dh
0x14001142f  mov     rcx, rbx
0x140011432  call    ChannelAckCommand
0x140011437  lea     rcx, [rbx+18h]
0x14001143b  mov     edx, 444E4946h
0x140011440  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140011447  mov     r8d, 12E0h
0x14001144d  call    RefObj_ReleaseEx
0x140011452  jmp     short loc_14001147E
0x140011454  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14001145b  jz      short loc_1400114A8
0x14001145d  mov     rcx, cs:WPP_GLOBAL_Control
0x140011464  mov     r9d, 92h
0x14001146a  mov     r8d, 2
0x140011470  mov     [rsp+58h+var_38], rbp
0x140011475  mov     rcx, [rcx+40h]
0x140011479  call    WPP_RECORDER_SF_
0x14001147e  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140011485  jz      short loc_1400114A8
0x140011487  mov     rcx, cs:WPP_GLOBAL_Control
0x14001148e  mov     r9d, 93h
0x140011494  mov     r8d, 3
0x14001149a  mov     [rsp+58h+var_38], rbp
0x14001149f  mov     rcx, [rcx+40h]
0x1400114a3  call    WPP_RECORDER_SF_
0x1400114a8  mov     eax, 4
0x1400114ad  add     rsp, 38h
0x1400114b1  pop     rdi
0x1400114b2  pop     rsi
0x1400114b3  pop     rbp
0x1400114b4  pop     rbx
0x1400114b5  retn
```

# HandleDISCFrame

- ea: `0x14001127c`
- end: `0x140011386`
- name: `HandleDISCFrame`
- size: `266`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400147a0`

## callees

- `0x140003bf4`
- `0x14001127c`
- `0x140014b10`
- `0x140015688`
- `0x140017db4`
- `0x140019b64`
- `0x140019e5c`
- `0x14001ea34`

## string_xrefs

- `0x140011323`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`

## pseudocode

```c
__int64 __fastcall HandleDISCFrame(__int64 a1, _BYTE *a2)
{
  __int64 *Locked; // rax
  __int64 *v5; // rdi
  char v6; // dl
  int v7; // edx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      3,
      143,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  Locked = ChannelFindLocked(a1, *a2 >> 2, 0);
  v5 = Locked;
  v6 = *a2 >> 2;
  if ( v6 )
  {
    if ( Locked )
    {
      ChannelDisconnectInd(Locked, 4, 3221226039LL);
      RefObj_ReleaseEx(v5 + 3, 1145981254, 4778, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
    }
    else
    {
      RfcommSendDMEx(a1, v6, (a2[1] & 0x10) != 0);
    }
  }
  else
  {
    RfcommSendUA(a1, 0);
    SessionDisconnectInd(a1, 0, 0xC000013C, 1);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      3,
      144,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  return 4;
}

```

## disassembly

```asm
0x14001127c  push    rbx
0x14001127e  push    rbp
0x14001127f  push    rsi
0x140011280  push    rdi
0x140011281  push    r12
0x140011283  sub     rsp, 30h
0x140011287  mov     rsi, rdx
0x14001128a  mov     rbx, rcx
0x14001128d  lea     rbp, WPP_RECORDER_INITIALIZED
0x140011294  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001129b  lea     r12, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x1400112a2  jz      short loc_1400112C5
0x1400112a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400112ab  mov     r9d, 8Fh
0x1400112b1  mov     r8d, 3
0x1400112b7  mov     [rsp+58h+var_38], r12
0x1400112bc  mov     rcx, [rcx+40h]
0x1400112c0  call    WPP_RECORDER_SF_
0x1400112c5  mov     dl, [rsi]
0x1400112c7  xor     r8d, r8d
0x1400112ca  shr     dl, 2
0x1400112cd  mov     rcx, rbx
0x1400112d0  call    ChannelFindLocked
0x1400112d5  mov     cl, [rsi]
0x1400112d7  mov     rdi, rax
0x1400112da  shr     cl, 2
0x1400112dd  mov     dl, cl
0x1400112df  test    cl, cl
0x1400112e1  jnz     short loc_140011302
0x1400112e3  xor     edx, edx
0x1400112e5  mov     rcx, rbx
0x1400112e8  call    RfcommSendUA
0x1400112ed  mov     r9b, 1
0x1400112f0  xor     edx, edx
0x1400112f2  mov     r8d, 0C000013Ch
0x1400112f8  mov     rcx, rbx
0x1400112fb  call    SessionDisconnectInd
0x140011300  jmp     short loc_14001134B
0x140011302  test    rdi, rdi
0x140011305  jz      short loc_140011337
0x140011307  mov     edx, 4
0x14001130c  mov     r8d, 0C0000237h
0x140011312  mov     rcx, rdi
0x140011315  call    ChannelDisconnectInd
0x14001131a  lea     rcx, [rdi+18h]
0x14001131e  mov     edx, 444E4946h
0x140011323  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14001132a  mov     r8d, 12AAh
0x140011330  call    RefObj_ReleaseEx
0x140011335  jmp     short loc_14001134B
0x140011337  mov     r8b, [rsi+1]
0x14001133b  mov     rcx, rbx
0x14001133e  shr     r8b, 4
0x140011342  and     r8b, 1
0x140011346  call    RfcommSendDMEx
0x14001134b  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140011352  jz      short loc_140011375
0x140011354  mov     rcx, cs:WPP_GLOBAL_Control
0x14001135b  mov     r9d, 90h
0x140011361  mov     r8d, 3
0x140011367  mov     [rsp+58h+var_38], r12
0x14001136c  mov     rcx, [rcx+40h]
0x140011370  call    WPP_RECORDER_SF_
0x140011375  mov     eax, 4
0x14001137a  add     rsp, 30h
0x14001137e  pop     r12
0x140011380  pop     rdi
0x140011381  pop     rsi
0x140011382  pop     rbp
0x140011383  pop     rbx
0x140011384  retn
```

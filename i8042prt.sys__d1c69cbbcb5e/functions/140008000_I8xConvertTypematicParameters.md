# I8xConvertTypematicParameters

- ea: `0x140008000`
- end: `0x1400080d0`
- name: `I8xConvertTypematicParameters`
- size: `208`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140007c20`
- `0x14001d8b0`

## callees

- `0x140004530`
- `0x140008000`

## pseudocode

```c
__int64 __fastcall I8xConvertTypematicParameters(unsigned __int16 a1, __int64 a2)
{
  unsigned int v2; // ebx
  __int64 v3; // rdi
  unsigned __int8 v4; // bl
  _DWORD v6[8]; // [rsp+30h] [rbp-20h]

  v2 = (unsigned __int16)a2;
  v3 = a1;
  v6[0] = 438050591;
  v6[1] = 286397463;
  v6[2] = 185339151;
  v6[3] = 134809866;
  v6[4] = 67438087;
  v6[5] = 33751812;
  v6[6] = 16843010;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3u,
      0x1Fu,
      (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
  LODWORD(a2) = (274877907 * (unsigned __int64)v2) >> 32;
  v4 = 32 * (v2 / 0xFA - 1);
  if ( (unsigned int)v3 <= 0x1B )
    v4 |= *((_BYTE *)v6 + v3);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3u,
      0x20u,
      (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
  return v4;
}

```

## disassembly

```asm
0x140008000  push    rbp
0x140008002  push    rbx
0x140008003  push    rsi
0x140008004  push    rdi
0x140008005  push    r14
0x140008007  mov     rbp, rsp
0x14000800a  sub     rsp, 50h
0x14000800e  movzx   ebx, dx
0x140008011  movzx   edi, cx
0x140008014  mov     [rbp+var_20], 1A1C1F1Fh
0x14000801b  mov     [rbp+var_1C], 11121417h
0x140008022  mov     [rbp+var_18], 0B0C0D0Fh
0x140008029  mov     [rbp+var_14], 809090Ah
0x140008030  mov     [rbp+var_10], 4050607h
0x140008037  mov     [rbp+var_C], 2030304h
0x14000803e  mov     [rbp+var_8], 1010102h
0x140008045  lea     rsi, WPP_RECORDER_INITIALIZED
0x14000804c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140008053  lea     r14, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x14000805a  jz      short loc_14000807D
0x14000805c  mov     rcx, cs:WPP_GLOBAL_Control
0x140008063  mov     r9d, 1Fh
0x140008069  mov     r8d, 3
0x14000806f  mov     [rsp+50h+var_30], r14
0x140008074  mov     rcx, [rcx+40h]
0x140008078  call    WPP_RECORDER_SF_
0x14000807d  mov     eax, 10624DD3h
0x140008082  mul     ebx
0x140008084  mov     ebx, edx
0x140008086  shr     ebx, 4
0x140008089  dec     bl
0x14000808b  shl     bl, 5
0x14000808e  cmp     edi, 1Bh
0x140008091  ja      short loc_140008097
0x140008093  or      bl, byte ptr [rbp+rdi+var_20]
0x140008097  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000809e  jz      short loc_1400080C1
0x1400080a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400080a7  mov     r9d, 20h ; ' '
0x1400080ad  mov     r8d, 3
0x1400080b3  mov     [rsp+50h+var_30], r14
0x1400080b8  mov     rcx, [rcx+40h]
0x1400080bc  call    WPP_RECORDER_SF_
0x1400080c1  movzx   eax, bl
0x1400080c4  add     rsp, 50h
0x1400080c8  pop     r14
0x1400080ca  pop     rdi
0x1400080cb  pop     rsi
0x1400080cc  pop     rbx
0x1400080cd  pop     rbp
0x1400080ce  retn
```

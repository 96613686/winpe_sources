# QuicStreamSendWrite

- ea: `0x140018050`
- end: `0x1400183a3`
- name: `QuicStreamSendWrite`
- size: `851`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140016210`

## callees

- `0x140018050`
- `0x1400183d0`
- `0x140018fd4`
- `0x140019f94`
- `0x14001c1e0`
- `0x14002f89c`
- `0x140040de8`
- `0x140048a00`
- `0x140048b18`

## pseudocode

```c
bool __fastcall QuicStreamSendWrite(__int64 a1, __int64 a2)
{
  __int64 v3; // r9
  unsigned __int8 v5; // r15
  unsigned __int16 v6; // r14
  __int64 v7; // r9
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // r9
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // r9
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // r8
  __int16 v17; // cx
  _QWORD *v18; // rsi
  _QWORD *v19; // rbp
  unsigned __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // r8
  __int64 v26; // [rsp+30h] [rbp-38h] BYREF
  __int64 v27; // [rsp+38h] [rbp-30h]
  __int64 v28; // [rsp+40h] [rbp-28h]
  __int64 v29; // [rsp+48h] [rbp-20h]
  unsigned __int16 v30; // [rsp+70h] [rbp+8h] BYREF

  v3 = *(_QWORD *)(a2 + 408);
  v5 = *(_BYTE *)(v3 + 90);
  v6 = **(_WORD **)(a2 + 32) - *(unsigned __int8 *)(a2 + 370);
  if ( (byte_14005C48D & 2) != 0 )
    McTemplateU0pp_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)QuicStreamWriteFrames, a1, *(_QWORD *)(v3 + 8));
  if ( (*(_BYTE *)(a1 + 96) & 2) != 0 )
  {
    v7 = *(_QWORD *)(a2 + 32);
    v26 = *(_QWORD *)(a1 + 80);
    v27 = *(_QWORD *)(a1 + 424);
    if ( (unsigned __int8)QuicMaxStreamDataFrameEncode(&v26, a2 + 378, v6, *(_QWORD *)(v7 + 8)) )
    {
      LOBYTE(v8) = 17;
      *(_WORD *)(a1 + 96) &= ~2u;
      if ( (unsigned __int8)QuicPacketBuilderAddStreamFrame(a2, a1, v8) )
        return 1;
    }
  }
  if ( (*(_BYTE *)(a1 + 96) & 4) != 0 )
  {
    v9 = *(_QWORD *)(a2 + 32);
    v26 = *(_QWORD *)(a1 + 80);
    v27 = *(_QWORD *)(a1 + 256);
    v10 = *(_QWORD *)(v9 + 8);
    v28 = *(_QWORD *)(a1 + 208);
    if ( (unsigned __int8)QuicResetStreamFrameEncode(&v26, a2 + 378, v6, v10) )
    {
      LOBYTE(v11) = 4;
      *(_WORD *)(a1 + 96) &= ~4u;
      if ( (unsigned __int8)QuicPacketBuilderAddStreamFrame(a2, a1, v11) )
        return 1;
    }
  }
  if ( *(char *)(a1 + 96) < 0 )
  {
    v12 = *(_QWORD *)(a2 + 32);
    v26 = *(_QWORD *)(a1 + 80);
    v27 = *(_QWORD *)(a1 + 256);
    v13 = *(_QWORD *)(v12 + 8);
    v28 = *(_QWORD *)(a1 + 208);
    v29 = *(_QWORD *)(a1 + 248);
    if ( (unsigned __int8)QuicReliableResetFrameEncode(&v26, a2 + 378, v6, v13) )
    {
      LOBYTE(v14) = 33;
      *(_WORD *)(a1 + 96) &= ~0x80u;
      if ( (unsigned __int8)QuicPacketBuilderAddStreamFrame(a2, a1, v14) )
        return 1;
    }
  }
  if ( (*(_BYTE *)(a1 + 96) & 8) != 0 )
  {
    v15 = *(_QWORD *)(a2 + 32);
    v26 = *(_QWORD *)(a1 + 80);
    v27 = *(_QWORD *)(a1 + 704);
    if ( (unsigned __int8)QuicStopSendingFrameEncode(&v26, a2 + 378, v6, *(_QWORD *)(v15 + 8)) )
    {
      LOBYTE(v16) = 5;
      *(_WORD *)(a1 + 96) &= ~8u;
      if ( (unsigned __int8)QuicPacketBuilderAddStreamFrame(a2, a1, v16) )
        return 1;
    }
  }
  if ( (*(_BYTE *)(a1 + 96) & 0x70) != 0 )
  {
    v17 = *(_WORD *)(a1 + 96);
    v18 = (_QWORD *)(a1 + 240);
    v19 = (_QWORD *)(a1 + 232);
    if ( (v17 & 0x20) == 0 && *v19 >= *v18 )
    {
      v20 = *(_QWORD *)(a1 + 224);
      if ( v20 == *(_QWORD *)(a1 + 160) )
      {
        if ( (v17 & 0x40) == 0 )
          goto LABEL_28;
      }
      else if ( v20 >= *(_QWORD *)(a1 + 184)
             || *(_QWORD *)(*(_QWORD *)(a1 + 72) + 3472LL) >= *(_QWORD *)(*(_QWORD *)(a1 + 72) + 3456LL) )
      {
        goto LABEL_28;
      }
    }
    v21 = *(unsigned __int16 *)(a2 + 378);
    v22 = *(_QWORD *)(a2 + 408);
    v30 = v6 - v21;
    QuicStreamWriteStreamFrames(a1, a2, v22, &v30, *(_QWORD *)(*(_QWORD *)(a2 + 32) + 8LL) + v21);
    if ( v30 )
    {
      *(_WORD *)(a2 + 378) += v30;
      if ( *v19 >= *v18 && *(_QWORD *)(a1 + 224) >= *(_QWORD *)(a1 + 160) )
        *(_WORD *)(a1 + 96) &= ~0x10u;
      if ( *(_BYTE *)(*(_QWORD *)(a2 + 408) + 90LL) == 12 )
        return 1;
    }
  }
LABEL_28:
  if ( (*(_BYTE *)(a1 + 96) & 1) != 0 )
  {
    v23 = *(_QWORD *)(a2 + 32);
    v26 = *(_QWORD *)(a1 + 80);
    v27 = *(_QWORD *)(a1 + 224);
    if ( (unsigned __int8)QuicStreamDataBlockedFrameEncode(&v26, a2 + 378, v6, *(_QWORD *)(v23 + 8)) )
    {
      LOBYTE(v24) = 21;
      *(_WORD *)(a1 + 96) &= ~1u;
      if ( (unsigned __int8)QuicPacketBuilderAddStreamFrame(a2, a1, v24) )
        return 1;
    }
  }
  return *(_BYTE *)(*(_QWORD *)(a2 + 408) + 90LL) > v5;
}

```

## disassembly

```asm
0x140018050  mov     [rsp+arg_18], rbx
0x140018055  push    rdi
0x140018056  push    r14
0x140018058  push    r15
0x14001805a  sub     rsp, 50h
0x14001805e  mov     rax, [rdx+20h]
0x140018062  mov     rdi, rdx
0x140018065  mov     r9, [rdx+198h]
0x14001806c  mov     rbx, rcx
0x14001806f  movzx   r8d, byte ptr [rdx+172h]
0x140018077  movzx   r14d, word ptr [rax]
0x14001807b  movzx   r15d, byte ptr [r9+5Ah]
0x140018080  sub     r14w, r8w
0x140018084  test    cs:byte_14005C48D, 2
0x14001808b  jz      short loc_1400180A0
0x14001808d  mov     r9, [r9+8]
0x140018091  lea     rdx, QuicStreamWriteFrames
0x140018098  mov     r8, rcx
0x14001809b  call    McTemplateU0pp_EtwWriteTransfer
0x1400180a0  test    byte ptr [rbx+60h], 2
0x1400180a4  mov     [rsp+68h+arg_8], rbp
0x1400180a9  mov     [rsp+68h+arg_10], rsi
0x1400180b1  jz      short loc_140018108
0x1400180b3  mov     rax, [rbx+50h]
0x1400180b7  lea     rdx, [rdi+17Ah]
0x1400180be  mov     r9, [rdi+20h]
0x1400180c2  lea     rcx, [rsp+68h+var_38]
0x1400180c7  mov     [rsp+68h+var_38], rax
0x1400180cc  movzx   r8d, r14w
0x1400180d0  mov     rax, [rbx+1A8h]
0x1400180d7  mov     [rsp+68h+var_30], rax
0x1400180dc  mov     r9, [r9+8]
0x1400180e0  call    QuicMaxStreamDataFrameEncode
0x1400180e5  test    al, al
0x1400180e7  jz      short loc_140018108
0x1400180e9  mov     eax, 0FFFDh
0x1400180ee  mov     r8b, 11h
0x1400180f1  and     [rbx+60h], ax
0x1400180f5  mov     rdx, rbx
0x1400180f8  mov     rcx, rdi
0x1400180fb  call    QuicPacketBuilderAddStreamFrame
0x140018100  test    al, al
0x140018102  jnz     loc_140018371
0x140018108  test    byte ptr [rbx+60h], 4
0x14001810c  jz      short loc_14001816F
0x14001810e  mov     rax, [rbx+50h]
0x140018112  lea     rdx, [rdi+17Ah]
0x140018119  mov     r9, [rdi+20h]
0x14001811d  lea     rcx, [rsp+68h+var_38]
0x140018122  mov     [rsp+68h+var_38], rax
0x140018127  movzx   r8d, r14w
0x14001812b  mov     rax, [rbx+100h]
0x140018132  mov     [rsp+68h+var_30], rax
0x140018137  mov     rax, [rbx+0D0h]
0x14001813e  mov     r9, [r9+8]
0x140018142  mov     [rsp+68h+var_28], rax
0x140018147  call    QuicResetStreamFrameEncode
0x14001814c  test    al, al
0x14001814e  jz      short loc_14001816F
0x140018150  mov     eax, 0FFFBh
0x140018155  mov     r8b, 4
0x140018158  and     [rbx+60h], ax
0x14001815c  mov     rdx, rbx
0x14001815f  mov     rcx, rdi
0x140018162  call    QuicPacketBuilderAddStreamFrame
0x140018167  test    al, al
0x140018169  jnz     loc_140018371
0x14001816f  movzx   eax, byte ptr [rbx+60h]
0x140018173  test    al, al
0x140018175  jns     short loc_1400181E4
0x140018177  mov     rax, [rbx+50h]
0x14001817b  lea     rdx, [rdi+17Ah]
0x140018182  mov     r9, [rdi+20h]
0x140018186  lea     rcx, [rsp+68h+var_38]
0x14001818b  mov     [rsp+68h+var_38], rax
0x140018190  movzx   r8d, r14w
0x140018194  mov     rax, [rbx+100h]
0x14001819b  mov     [rsp+68h+var_30], rax
0x1400181a0  mov     rax, [rbx+0D0h]
0x1400181a7  mov     r9, [r9+8]
0x1400181ab  mov     [rsp+68h+var_28], rax
0x1400181b0  mov     rax, [rbx+0F8h]
0x1400181b7  mov     [rsp+68h+var_20], rax
0x1400181bc  call    QuicReliableResetFrameEncode
0x1400181c1  test    al, al
0x1400181c3  jz      short loc_1400181E4
0x1400181c5  mov     eax, 0FF7Fh
0x1400181ca  mov     r8b, 21h ; '!'
0x1400181cd  and     [rbx+60h], ax
0x1400181d1  mov     rdx, rbx
0x1400181d4  mov     rcx, rdi
0x1400181d7  call    QuicPacketBuilderAddStreamFrame
0x1400181dc  test    al, al
0x1400181de  jnz     loc_140018371
0x1400181e4  test    byte ptr [rbx+60h], 8
0x1400181e8  jz      short loc_14001823F
0x1400181ea  mov     rax, [rbx+50h]
0x1400181ee  lea     rdx, [rdi+17Ah]
0x1400181f5  mov     r9, [rdi+20h]
0x1400181f9  lea     rcx, [rsp+68h+var_38]
0x1400181fe  mov     [rsp+68h+var_38], rax
0x140018203  movzx   r8d, r14w
0x140018207  mov     rax, [rbx+2C0h]
0x14001820e  mov     [rsp+68h+var_30], rax
0x140018213  mov     r9, [r9+8]
0x140018217  call    QuicStopSendingFrameEncode
0x14001821c  test    al, al
0x14001821e  jz      short loc_14001823F
0x140018220  mov     eax, 0FFF7h
0x140018225  mov     r8b, 5
0x140018228  and     [rbx+60h], ax
0x14001822c  mov     rdx, rbx
0x14001822f  mov     rcx, rdi
0x140018232  call    QuicPacketBuilderAddStreamFrame
0x140018237  test    al, al
0x140018239  jnz     loc_140018371
0x14001823f  test    byte ptr [rbx+60h], 70h
0x140018243  jz      loc_14001831A
0x140018249  movzx   ecx, word ptr [rbx+60h]
0x14001824d  lea     rsi, [rbx+0F0h]
0x140018254  lea     rbp, [rbx+0E8h]
0x14001825b  test    cl, 20h
0x14001825e  jnz     short loc_1400182A6
0x140018260  mov     rax, [rsi]
0x140018263  cmp     [rbp+0], rax
0x140018267  jb      short loc_1400182A6
0x140018269  mov     rax, [rbx+0E0h]
0x140018270  cmp     rax, [rbx+0A0h]
0x140018277  jnz     short loc_140018285
0x140018279  and     cx, 40h
0x14001827d  jz      loc_14001831A
0x140018283  jmp     short loc_1400182A6
0x140018285  mov     rcx, [rbx+48h]
0x140018289  cmp     rax, [rbx+0B8h]
0x140018290  jnb     loc_14001831A
0x140018296  mov     rax, [rcx+0D80h]
0x14001829d  cmp     [rcx+0D90h], rax
0x1400182a4  jnb     short loc_14001831A
0x1400182a6  movzx   ecx, word ptr [rdi+17Ah]
0x1400182ad  lea     r9, [rsp+68h+arg_0]
0x1400182b2  mov     r8, [rdi+198h]
0x1400182b9  movzx   eax, r14w
0x1400182bd  sub     ax, cx
0x1400182c0  mov     [rsp+68h+arg_0], ax
0x1400182c5  mov     rax, [rdi+20h]
0x1400182c9  add     rcx, [rax+8]
0x1400182cd  mov     [rsp+68h+var_48], rcx
0x1400182d2  mov     rcx, rbx
0x1400182d5  call    QuicStreamWriteStreamFrames
0x1400182da  movzx   eax, [rsp+68h+arg_0]
0x1400182df  test    ax, ax
0x1400182e2  jz      short loc_14001831A
0x1400182e4  add     [rdi+17Ah], ax
0x1400182eb  mov     rax, [rsi]
0x1400182ee  cmp     [rbp+0], rax
0x1400182f2  jb      short loc_14001830D
0x1400182f4  mov     rax, [rbx+0A0h]
0x1400182fb  cmp     [rbx+0E0h], rax
0x140018302  jb      short loc_14001830D
0x140018304  mov     eax, 0FFEFh
0x140018309  and     [rbx+60h], ax
0x14001830d  mov     rax, [rdi+198h]
0x140018314  cmp     byte ptr [rax+5Ah], 0Ch
0x140018318  jz      short loc_140018371
0x14001831a  test    byte ptr [rbx+60h], 1
0x14001831e  jz      short loc_140018375
0x140018320  mov     rax, [rbx+50h]
0x140018324  lea     rdx, [rdi+17Ah]
0x14001832b  mov     r9, [rdi+20h]
0x14001832f  lea     rcx, [rsp+68h+var_38]
0x140018334  mov     [rsp+68h+var_38], rax
0x140018339  movzx   r8d, r14w
0x14001833d  mov     rax, [rbx+0E0h]
0x140018344  mov     [rsp+68h+var_30], rax
0x140018349  mov     r9, [r9+8]
0x14001834d  call    QuicStreamDataBlockedFrameEncode
0x140018352  test    al, al
0x140018354  jz      short loc_140018375
0x140018356  mov     ecx, 0FFFEh
0x14001835b  mov     r8b, 15h
0x14001835e  and     [rbx+60h], cx
0x140018362  mov     rdx, rbx
0x140018365  mov     rcx, rdi
0x140018368  call    QuicPacketBuilderAddStreamFrame
0x14001836d  test    al, al
0x14001836f  jz      short loc_140018375
0x140018371  mov     al, 1
0x140018373  jmp     short loc_140018383
0x140018375  mov     rax, [rdi+198h]
0x14001837c  cmp     [rax+5Ah], r15b
0x140018380  setnbe  al
0x140018383  mov     rsi, [rsp+68h+arg_10]
0x14001838b  mov     rbp, [rsp+68h+arg_8]
0x140018390  mov     rbx, [rsp+68h+arg_18]
0x140018398  add     rsp, 50h
0x14001839c  pop     r15
0x14001839e  pop     r14
0x1400183a0  pop     rdi
0x1400183a1  retn
```

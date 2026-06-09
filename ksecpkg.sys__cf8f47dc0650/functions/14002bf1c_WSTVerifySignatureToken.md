# WSTVerifySignatureToken

- ea: `0x14002bf1c`
- end: `0x14002c241`
- name: `WSTVerifySignatureToken`
- size: `805`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14002ae10`
- `0x14002bc00`

## callees

- `0x140007008`
- `0x14002bf1c`
- `0x14002c874`

## string_xrefs

- `0x14002c217`: `bad token id in the header\n`
- `0x14002bf72`: `bad token header\n`
- `0x14002bff2`: `bad EC in token header\n`
- `0x14002bfd8`: `token header too small\n`

## pseudocode

```c
__int64 __fastcall WSTVerifySignatureToken(
        __int64 a1,
        unsigned int *a2,
        char a3,
        __int64 a4,
        unsigned __int8 **a5,
        _DWORD *a6,
        int *a7,
        _QWORD *a8,
        _QWORD *a9)
{
  __int64 v11; // r8
  unsigned __int8 *v12; // rdi
  unsigned __int8 *v13; // rdi
  int v14; // edx
  unsigned int v15; // ebx
  int v16; // r8d
  unsigned int v17; // r10d
  int v18; // ecx
  int v19; // eax
  __int64 v20; // r8
  __int64 v21; // r9
  int v22; // r10d
  int v23; // r11d
  int v24; // eax
  int *v25; // rsi
  int v26; // edx
  __int64 v27; // rcx
  __int64 i; // rdx
  unsigned __int8 v29; // cl
  char v30; // al
  __int64 v32; // [rsp+30h] [rbp-28h]
  __int64 v33; // [rsp+38h] [rbp-20h] BYREF
  __int64 v34; // [rsp+40h] [rbp-18h] BYREF

  v11 = *a2;
  v34 = a4;
  v33 = 0;
  if ( (unsigned int)v11 < 0x1C )
  {
    if ( KsecInfoLevel )
      KsecDebugOut(1, "bad token header\n", v11, a7);
    return (unsigned int)-2146893048;
  }
  v12 = (unsigned __int8 *)*((_QWORD *)a2 + 1);
  if ( *v12 != (a3 != 0) + 4 || v12[1] != 4 )
  {
    if ( KsecInfoLevel )
      KsecDebugOut(1, "bad token id in the header\n", v11, a7);
    return (unsigned int)-2146893048;
  }
  v13 = v12 + 2;
  if ( a3 )
  {
    v14 = v13[3] + (v13[2] << 8);
    if ( (*v13 & 2) != 0 )
    {
      if ( (unsigned int)v11 < v14 + 60 )
      {
        if ( KsecInfoLevel )
          KsecDebugOut(1, "token header too small\n", v11, a7);
        return (unsigned int)-2146893048;
      }
    }
    else if ( v14 != 12 )
    {
      if ( KsecInfoLevel )
        KsecDebugOut(1, "bad EC in token header\n", v11, a7);
      return (unsigned int)-2146893041;
    }
  }
  if ( v13[1] != 0xFF || !a3 && *(_DWORD *)(v13 + 2) != -1 )
  {
    if ( KsecInfoLevel )
      KsecDebugOut(1, "bad filler\n", v11, a7);
    return (unsigned int)-2146893041;
  }
  v16 = *(_DWORD *)(a1 + 64);
  if ( v16 == 17 )
  {
    v17 = -148;
    v18 = (*v13 & 2) != 0 ? -150 : 15;
  }
  else
  {
    if ( v16 != 18 )
    {
      if ( KsecInfoLevel )
        KsecDebugOut(1, "unexpected etype %d\n", v16);
      return (unsigned int)-2146893054;
    }
    v17 = -149;
    v18 = (*v13 & 2) != 0 ? -151 : 16;
  }
  *a7 = v18;
  v19 = CDLocateCSystem(v17, &v33);
  v15 = v19;
  if ( v19 < 0 )
  {
    if ( KsecInfoLevel )
      KsecDebugOut(1, "Failed to load %d crypt system: %#x\n", v22, v19);
    return v15;
  }
  if ( (_BYTE)v23 && (*v13 & 2) == 0 )
    *a6 = -2147483647;
  v24 = *(_DWORD *)(a1 + 108);
  if ( (v24 & 0x400) != 0 || (v25 = (int *)(a1 + 96), (v24 & 0x1000C) == 0x10000) )
    v25 = (int *)&v34;
  v26 = *v25;
  v27 = HIDWORD(*(_QWORD *)v25);
  *(_WORD *)((char *)&v32 + 3) = WORD2(*(_QWORD *)v25);
  LOBYTE(v32) = BYTE3(v27);
  BYTE1(v32) = BYTE2(v27);
  BYTE2(v32) = BYTE1(v27);
  BYTE5(v32) = BYTE2(v26);
  BYTE6(v32) = BYTE1(v26);
  HIBYTE(v32) = v26;
  if ( KsecInfoLevel )
    KsecDebugOut(
      16,
      "Verifying signature buffer (decrypt = %d) with nonce 0x%I64x, message seq  0x%I64x\n",
      v23,
      v32,
      *(_QWORD *)(v13 + 6));
  if ( (*(_DWORD *)(a1 + 108) & 0xC) != 0 )
  {
    LOBYTE(v20) = 0;
    for ( i = 0; i != 8; ++i )
    {
      v29 = v13[i + 6];
      v30 = *((_BYTE *)&v32 + i);
      LOBYTE(v20) = v30 ^ v29 | v20;
    }
    if ( (_BYTE)v20 )
    {
      if ( KsecInfoLevel )
        KsecDebugOut(1, "sequence number mismatched\n");
      return (unsigned int)-2146893040;
    }
  }
  *a9 = *(_QWORD *)(v13 + 6);
  if ( ((unsigned __int8)~*v13 & ((*(_BYTE *)(a1 + 104) & 2) != 0)) != 0 )
  {
    if ( KsecInfoLevel )
      KsecDebugOut(1, "message not sent by acceptor\n", v20, v21);
    return (unsigned int)-2146893041;
  }
  ++*(_QWORD *)v25;
  if ( a8 )
    *a8 = v33;
  *a5 = v13;
  return v15;
}

```

## disassembly

```asm
0x14002bf1c  push    rbp
0x14002bf1e  push    rbx
0x14002bf1f  push    rsi
0x14002bf20  push    rdi
0x14002bf21  push    r12
0x14002bf23  push    r13
0x14002bf25  push    r14
0x14002bf27  push    r15
0x14002bf29  mov     rbp, rsp
0x14002bf2c  sub     rsp, 58h
0x14002bf30  mov     r12, [rbp+arg_20]
0x14002bf34  xor     r10d, r10d
0x14002bf37  mov     rsi, [rbp+arg_28]
0x14002bf3b  mov     r14, rcx
0x14002bf3e  mov     r15, [rbp+arg_38]
0x14002bf45  mov     r13, [rbp+arg_40]
0x14002bf4c  movzx   r11d, r8b
0x14002bf50  mov     r8d, [rdx]
0x14002bf53  mov     [rbp+var_18], r9
0x14002bf57  mov     r9, [rbp+arg_30]
0x14002bf5b  mov     [rbp+var_20], r10
0x14002bf5f  cmp     r8d, 1Ch
0x14002bf63  jnb     short loc_14002BF7E
0x14002bf65  cmp     cs:KsecInfoLevel, r10d
0x14002bf6c  jz      loc_14002C228
0x14002bf72  lea     rdx, aBadTokenHeader; "bad token header\n"
0x14002bf79  jmp     loc_14002C21E
0x14002bf7e  mov     rdi, [rdx+8]
0x14002bf82  mov     al, r11b
0x14002bf85  neg     al
0x14002bf87  sbb     cx, cx
0x14002bf8a  movzx   eax, byte ptr [rdi]
0x14002bf8d  neg     cx
0x14002bf90  add     cx, 4
0x14002bf94  cmp     ax, cx
0x14002bf97  jnz     loc_14002C20E
0x14002bf9d  cmp     byte ptr [rdi+1], 4
0x14002bfa1  jnz     loc_14002C20E
0x14002bfa7  add     rdi, 2
0x14002bfab  mov     bl, 2
0x14002bfad  test    r11b, r11b
0x14002bfb0  jz      short loc_14002C00D
0x14002bfb2  movzx   edx, byte ptr [rdi+2]
0x14002bfb6  movzx   eax, byte ptr [rdi+3]
0x14002bfba  shl     edx, 8
0x14002bfbd  add     edx, eax
0x14002bfbf  test    [rdi], bl
0x14002bfc1  jz      short loc_14002BFE4
0x14002bfc3  lea     eax, [rdx+3Ch]
0x14002bfc6  cmp     r8d, eax
0x14002bfc9  jnb     short loc_14002C00D
0x14002bfcb  cmp     cs:KsecInfoLevel, r10d
0x14002bfd2  jz      loc_14002C228
0x14002bfd8  lea     rdx, aTokenHeaderToo; "token header too small\n"
0x14002bfdf  jmp     loc_14002C21E
0x14002bfe4  cmp     edx, 0Ch
0x14002bfe7  jz      short loc_14002C00D
0x14002bfe9  cmp     cs:KsecInfoLevel, r10d
0x14002bff0  jz      short loc_14002C003
0x14002bff2  lea     rdx, aBadEcInTokenHe; "bad EC in token header\n"
0x14002bff9  mov     ecx, 1
0x14002bffe  call    KsecDebugOut
0x14002c003  mov     ebx, 8009030Fh
0x14002c008  jmp     loc_14002C22D
0x14002c00d  cmp     byte ptr [rdi+1], 0FFh
0x14002c011  jnz     loc_14002C1F5
0x14002c017  test    r11b, r11b
0x14002c01a  jnz     short loc_14002C026
0x14002c01c  cmp     dword ptr [rdi+2], 0FFFFFFFFh
0x14002c020  jnz     loc_14002C1F5
0x14002c026  mov     r8d, [r14+40h]
0x14002c02a  mov     ecx, r8d
0x14002c02d  sub     ecx, 11h
0x14002c030  jz      short loc_14002C074
0x14002c032  cmp     ecx, 1
0x14002c035  jz      short loc_14002C05B
0x14002c037  cmp     cs:KsecInfoLevel, r10d
0x14002c03e  jz      short loc_14002C051
0x14002c040  lea     rdx, aUnexpectedEtyp; "unexpected etype %d\n"
0x14002c047  mov     ecx, 1
0x14002c04c  call    KsecDebugOut
0x14002c051  mov     ebx, 80090302h
0x14002c056  jmp     loc_14002C22D
0x14002c05b  mov     al, [rdi]
0x14002c05d  mov     r10d, 0FFFFFF6Bh
0x14002c063  and     al, bl
0x14002c065  neg     al
0x14002c067  sbb     ecx, ecx
0x14002c069  and     ecx, 0FFFFFF59h
0x14002c06f  add     ecx, 10h
0x14002c072  jmp     short loc_14002C08B
0x14002c074  mov     al, [rdi]
0x14002c076  mov     r10d, 0FFFFFF6Ch
0x14002c07c  and     al, bl
0x14002c07e  neg     al
0x14002c080  sbb     ecx, ecx
0x14002c082  and     ecx, 0FFFFFF5Bh
0x14002c088  add     ecx, 0Fh
0x14002c08b  mov     [r9], ecx
0x14002c08e  lea     rdx, [rbp+var_20]
0x14002c092  mov     ecx, r10d
0x14002c095  call    CDLocateCSystem
0x14002c09a  mov     ebx, eax
0x14002c09c  test    eax, eax
0x14002c09e  jns     short loc_14002C0C9
0x14002c0a0  cmp     cs:KsecInfoLevel, 0
0x14002c0a7  jz      loc_14002C22D
0x14002c0ad  mov     r9d, eax
0x14002c0b0  lea     rdx, aFailedToLoadDC_0; "Failed to load %d crypt system: %#x\n"
0x14002c0b7  mov     r8d, r10d
0x14002c0ba  mov     ecx, 1
0x14002c0bf  call    KsecDebugOut
0x14002c0c4  jmp     loc_14002C22D
0x14002c0c9  test    r11b, r11b
0x14002c0cc  jz      short loc_14002C0D9
0x14002c0ce  test    byte ptr [rdi], 2
0x14002c0d1  jnz     short loc_14002C0D9
0x14002c0d3  mov     dword ptr [rsi], 80000001h
0x14002c0d9  mov     eax, [r14+6Ch]
0x14002c0dd  bt      eax, 0Ah
0x14002c0e1  jb      short loc_14002C0F3
0x14002c0e3  and     eax, 1000Ch
0x14002c0e8  lea     rsi, [r14+60h]
0x14002c0ec  cmp     eax, 10000h
0x14002c0f1  jnz     short loc_14002C0F7
0x14002c0f3  lea     rsi, [rbp+var_18]
0x14002c0f7  mov     edx, [rsi]
0x14002c0f9  mov     rcx, [rsi]
0x14002c0fc  shr     rcx, 20h
0x14002c100  mov     eax, ecx
0x14002c102  mov     byte ptr [rbp+var_28+3], cl
0x14002c105  shr     eax, 18h
0x14002c108  mov     byte ptr [rbp+var_28], al
0x14002c10b  mov     eax, ecx
0x14002c10d  shr     eax, 10h
0x14002c110  mov     byte ptr [rbp+var_28+1], al
0x14002c113  mov     eax, ecx
0x14002c115  shr     eax, 8
0x14002c118  mov     byte ptr [rbp+var_28+2], al
0x14002c11b  mov     eax, edx
0x14002c11d  shr     eax, 18h
0x14002c120  mov     byte ptr [rbp+var_28+4], al
0x14002c123  mov     eax, edx
0x14002c125  shr     eax, 10h
0x14002c128  mov     byte ptr [rbp+var_28+5], al
0x14002c12b  mov     eax, edx
0x14002c12d  shr     eax, 8
0x14002c130  cmp     cs:KsecInfoLevel, 0
0x14002c137  mov     byte ptr [rbp+var_28+6], al
0x14002c13a  mov     byte ptr [rbp+var_28+7], dl
0x14002c13d  jz      short loc_14002C160
0x14002c13f  mov     rax, [rdi+6]
0x14002c143  lea     rdx, aVerifyingSigna; "Verifying signature buffer (decrypt = %"...
0x14002c14a  mov     r9, [rbp+var_28]
0x14002c14e  mov     r8d, r11d
0x14002c151  mov     ecx, 10h
0x14002c156  mov     [rsp+58h+var_38], rax
0x14002c15b  call    KsecDebugOut
0x14002c160  mov     eax, [r14+6Ch]
0x14002c164  test    al, 0Ch
0x14002c166  jz      short loc_14002C1AC
0x14002c168  xor     r8b, r8b
0x14002c16b  xor     edx, edx
0x14002c16d  mov     cl, [rdx+rdi+6]
0x14002c171  mov     al, byte ptr [rbp+rdx+var_28]
0x14002c175  inc     rdx
0x14002c178  xor     cl, al
0x14002c17a  or      r8b, cl
0x14002c17d  cmp     rdx, 8
0x14002c181  jnz     short loc_14002C16D
0x14002c183  test    r8b, r8b
0x14002c186  jz      short loc_14002C1AC
0x14002c188  cmp     cs:KsecInfoLevel, 0
0x14002c18f  jz      short loc_14002C1A2
0x14002c191  lea     rdx, aSequenceNumber; "sequence number mismatched\n"
0x14002c198  mov     ecx, 1
0x14002c19d  call    KsecDebugOut
0x14002c1a2  mov     ebx, 80090310h
0x14002c1a7  jmp     loc_14002C22D
0x14002c1ac  mov     rax, [rdi+6]
0x14002c1b0  mov     [r13+0], rax
0x14002c1b4  test    byte ptr [r14+68h], 2
0x14002c1b9  mov     al, [rdi]
0x14002c1bb  setnz   cl
0x14002c1be  not     al
0x14002c1c0  and     cl, al
0x14002c1c2  test    cl, 1
0x14002c1c5  jz      short loc_14002C1E0
0x14002c1c7  cmp     cs:KsecInfoLevel, 0
0x14002c1ce  jz      loc_14002C003
0x14002c1d4  lea     rdx, aMessageNotSent; "message not sent by acceptor\n"
0x14002c1db  jmp     loc_14002BFF9
0x14002c1e0  inc     qword ptr [rsi]
0x14002c1e3  test    r15, r15
0x14002c1e6  jz      short loc_14002C1EF
0x14002c1e8  mov     rax, [rbp+var_20]
0x14002c1ec  mov     [r15], rax
0x14002c1ef  mov     [r12], rdi
0x14002c1f3  jmp     short loc_14002C22D
0x14002c1f5  cmp     cs:KsecInfoLevel, r10d
0x14002c1fc  jz      loc_14002C003
0x14002c202  lea     rdx, aBadFiller; "bad filler\n"
0x14002c209  jmp     loc_14002BFF9
0x14002c20e  cmp     cs:KsecInfoLevel, r10d
0x14002c215  jz      short loc_14002C228
0x14002c217  lea     rdx, aBadTokenIdInTh; "bad token id in the header\n"
0x14002c21e  mov     ecx, 1
0x14002c223  call    KsecDebugOut
0x14002c228  mov     ebx, 80090308h
0x14002c22d  mov     eax, ebx
0x14002c22f  add     rsp, 58h
0x14002c233  pop     r15
0x14002c235  pop     r14
0x14002c237  pop     r13
0x14002c239  pop     r12
0x14002c23b  pop     rdi
0x14002c23c  pop     rsi
0x14002c23d  pop     rbx
0x14002c23e  pop     rbp
0x14002c23f  retn
```

# msStatus

- ea: `0x180001eec`
- end: `0x18000226b`
- name: `msStatus`
- size: `895`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800025fc`

## callees

- `0x180001eec`
- `0x180003520`
- `0x180005270`
- `0x180005ff0`

## pseudocode

```c
__int64 __fastcall msStatus(__int64 a1, __int64 a2, __int16 a3, __int64 a4)
{
  __int64 result; // rax
  int v8; // r15d
  unsigned int v9; // ebx
  unsigned int v10; // edi
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  int v18; // eax
  int v19; // eax
  bool v20; // cc
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  int v26; // edx
  bool v27; // zf
  int v28; // ecx
  unsigned int v29; // ecx
  __int128 v30; // [rsp+20h] [rbp-40h] BYREF
  __int128 v31; // [rsp+30h] [rbp-30h]
  __int128 v32; // [rsp+40h] [rbp-20h]
  __int64 v33; // [rsp+50h] [rbp-10h]

  v33 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  if ( (a3 & 0x100) == 0 )
    return 273;
  v8 = a3 & 0x10;
  if ( (a3 & 0x10) != 0 && (*(_BYTE *)(a4 + 16) & 3) == 0 )
    return 295;
  v9 = 0;
  v10 = 0;
  midiSeqMessage(*(_QWORD *)(a1 + 256), 0xBu, (__int64)&v30, 0);
  v11 = *(_DWORD *)(a4 + 16);
  if ( v11 > 8 )
  {
    v21 = v11 - 16386;
    if ( !v21 )
    {
      v29 = 1;
      if ( HIDWORD(v31) * (unsigned int)WORD1(v30) > 1 )
        v29 = HIDWORD(v31) * WORD1(v30);
      v9 = 0x3938700 / v29;
      if ( (_WORD)v30 )
        v9 /= 0x3Cu;
      goto LABEL_77;
    }
    v22 = v21 - 1;
    if ( v22 )
    {
      v23 = v22 - 4;
      if ( v23 )
      {
        v24 = v23 - 1;
        if ( v24 )
        {
          v25 = v24 - 1;
          if ( v25 )
          {
            if ( v25 == 1 )
            {
              v10 = 0x10000;
              v26 = 0;
              if ( (_WORD)v30 )
              {
                switch ( (unsigned __int16)v30 )
                {
                  case 0x18u:
                    v26 = 1217;
                    break;
                  case 0x19u:
                    v26 = 1218;
                    break;
                  case 0x1Du:
                    v26 = 1219;
                    break;
                  case 0x1Eu:
                    v26 = 1220;
                    break;
                }
              }
              else
              {
                v26 = 1216;
              }
              v9 = v26 | (v26 << 16);
              goto LABEL_77;
            }
            goto LABEL_45;
          }
          v9 = BYTE8(v32) + ((BYTE9(v32) + ((BYTE10(v32) + (BYTE11(v32) << 8)) << 8)) << 8);
LABEL_34:
          v10 = 0x40000;
          goto LABEL_77;
        }
        v10 = 0x10000;
        if ( WORD1(v33) )
        {
          v28 = WORD1(v33) - 2;
          v27 = WORD1(v33) == 2;
          goto LABEL_60;
        }
      }
      else
      {
        v10 = 0x10000;
        if ( (_WORD)v33 )
        {
          if ( (unsigned __int16)v33 == 1 )
          {
            v9 = 80101378;
            goto LABEL_77;
          }
          v28 = (unsigned __int16)v33 - 2;
          v27 = (unsigned __int16)v33 == 2;
LABEL_60:
          if ( v27 )
          {
            v9 = 80166915;
          }
          else if ( v28 == 1 )
          {
            v9 = 80232452;
          }
          goto LABEL_77;
        }
      }
    }
    else
    {
      v9 = *(_DWORD *)(a1 + 288);
      if ( v9 != 65533 )
      {
        if ( v9 == -1 )
        {
          v10 = 0x10000;
          v9 = 80478207;
        }
        goto LABEL_77;
      }
      v10 = 0x10000;
    }
    v9 = 80412669;
    goto LABEL_77;
  }
  if ( v11 == 8 )
  {
LABEL_27:
    v9 = 1;
    goto LABEL_77;
  }
  v12 = v11 - 1;
  if ( !v12 )
  {
    if ( v8 && *(_DWORD *)(a4 + 20) != 1 )
      v10 = 282;
    v9 = CnvtTimeFromSeq(a1, DWORD1(v30), &v30);
    v20 = (unsigned int)(*(_DWORD *)(a1 + 344) - 4) <= 3;
LABEL_33:
    if ( !v20 )
      goto LABEL_77;
    goto LABEL_34;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    if ( v8 )
    {
      v10 = *(_DWORD *)(a4 + 20) != 1 ? 0x11A : 0;
    }
    else if ( (a3 & 0x200) == 0 )
    {
      v9 = CnvtTimeFromSeq(a1, DWORD1(v31), &v30);
    }
    v20 = (unsigned int)(*(_DWORD *)(a1 + 344) - 4) <= 3;
    goto LABEL_33;
  }
  v14 = v13 - 1;
  if ( !v14 )
    goto LABEL_27;
  v15 = v14 - 1;
  if ( !v15 )
  {
    v10 = 0x10000;
    if ( HIDWORD(v30) )
    {
      v19 = 528;
    }
    else if ( DWORD2(v30) )
    {
      v19 = 526;
    }
    else
    {
      v19 = *(_DWORD *)(a1 + 348) != 0 ? 529 : 525;
    }
    v9 = v19 | (v19 << 16);
    goto LABEL_77;
  }
  v16 = v15 - 1;
  if ( !v16 )
  {
    v10 = 0x10000;
    v9 = 34865153;
    goto LABEL_77;
  }
  v17 = v16 - 1;
  if ( !v17 )
  {
    v18 = *(_DWORD *)(a1 + 344);
    if ( v18 == 16385 )
      v9 = 80297985;
    else
      v9 = (unsigned __int16)v18 | ((unsigned __int16)(v18 + 533) << 16);
    v10 = 0x10000;
    goto LABEL_77;
  }
  if ( v17 != 1 )
  {
LABEL_45:
    v10 = 274;
    goto LABEL_77;
  }
  v10 = 0x10000;
  v9 = (_DWORD)v31 != 0 ? 34865153 : 34799616;
LABEL_77:
  result = v10;
  *(_QWORD *)(a4 + 8) = v9;
  return result;
}

```

## disassembly

```asm
0x180001eec  mov     [rsp-38h+arg_8], rbx
0x180001ef1  push    rbp
0x180001ef2  push    rsi
0x180001ef3  push    rdi
0x180001ef4  push    r12
0x180001ef6  push    r13
0x180001ef8  push    r14
0x180001efa  push    r15
0x180001efc  mov     rbp, rsp
0x180001eff  sub     rsp, 60h
0x180001f03  mov     rax, cs:__security_cookie
0x180001f0a  xor     rax, rsp
0x180001f0d  mov     [rbp+var_8], rax
0x180001f11  xorps   xmm0, xmm0
0x180001f14  xor     eax, eax
0x180001f16  mov     [rbp+var_10], rax
0x180001f1a  mov     r13, r9
0x180001f1d  mov     r12d, r8d
0x180001f20  mov     rsi, rcx
0x180001f23  movups  [rbp+var_40], xmm0
0x180001f27  movups  [rbp+var_30], xmm0
0x180001f2b  movups  [rbp+var_20], xmm0
0x180001f2f  bt      r8d, 8
0x180001f34  jb      short loc_180001F40
0x180001f36  mov     eax, 111h
0x180001f3b  jmp     loc_180002247
0x180001f40  mov     r15d, r12d
0x180001f43  and     r15d, 10h
0x180001f47  jz      short loc_180001F5A
0x180001f49  test    byte ptr [r9+10h], 3
0x180001f4e  jnz     short loc_180001F5A
0x180001f50  mov     eax, 127h
0x180001f55  jmp     loc_180002247
0x180001f5a  mov     rcx, [rcx+100h]; dwUser
0x180001f61  lea     r8, [rbp+var_40]
0x180001f65  xor     r9d, r9d
0x180001f68  mov     ebx, eax
0x180001f6a  mov     edi, eax
0x180001f6c  lea     edx, [r9+0Bh]
0x180001f70  call    midiSeqMessage
0x180001f75  mov     eax, [r13+10h]
0x180001f79  cmp     eax, 8
0x180001f7c  ja      loc_1800020E5
0x180001f82  jz      loc_180002057
0x180001f88  sub     eax, 1
0x180001f8b  jz      loc_1800020B0
0x180001f91  sub     eax, 1
0x180001f94  jz      loc_180002061
0x180001f9a  sub     eax, 1
0x180001f9d  jz      loc_180002057
0x180001fa3  sub     eax, 1
0x180001fa6  jz      short loc_180002017
0x180001fa8  sub     eax, 1
0x180001fab  jz      short loc_180002008
0x180001fad  sub     eax, 1
0x180001fb0  jz      short loc_180001FD8
0x180001fb2  cmp     eax, 1
0x180001fb5  jnz     loc_180002115
0x180001fbb  mov     eax, dword ptr [rbp+var_30]
0x180001fbe  mov     edi, 10000h
0x180001fc3  neg     eax
0x180001fc5  sbb     ebx, ebx
0x180001fc7  and     ebx, 10001h
0x180001fcd  add     ebx, 2130000h
0x180001fd3  jmp     loc_18000223F
0x180001fd8  mov     eax, [rsi+158h]
0x180001fde  cmp     eax, 4001h
0x180001fe3  jnz     short loc_180001FEC
0x180001fe5  mov     ebx, 4C94001h
0x180001fea  jmp     short loc_180001FFE
0x180001fec  movzx   ecx, ax
0x180001fef  mov     eax, 215h
0x180001ff4  add     eax, ecx
0x180001ff6  movzx   ebx, ax
0x180001ff9  shl     ebx, 10h
0x180001ffc  or      ebx, ecx
0x180001ffe  mov     edi, 10000h
0x180002003  jmp     loc_18000223F
0x180002008  mov     edi, 10000h
0x18000200d  mov     ebx, 2140001h
0x180002012  jmp     loc_18000223F
0x180002017  xor     r8d, r8d
0x18000201a  mov     edi, 10000h
0x18000201f  cmp     dword ptr [rbp+var_40+0Ch], r8d
0x180002023  jz      short loc_18000202C
0x180002025  mov     eax, 210h
0x18000202a  jmp     short loc_18000204B
0x18000202c  cmp     dword ptr [rbp+var_40+8], r8d
0x180002030  jz      short loc_180002039
0x180002032  mov     eax, 20Eh
0x180002037  jmp     short loc_18000204B
0x180002039  mov     eax, [rsi+15Ch]
0x18000203f  neg     eax
0x180002041  sbb     eax, eax
0x180002043  and     eax, 4
0x180002046  add     eax, 20Dh
0x18000204b  mov     ebx, eax
0x18000204d  shl     ebx, 10h
0x180002050  or      ebx, eax
0x180002052  jmp     loc_18000223F
0x180002057  mov     ebx, 1
0x18000205c  jmp     loc_18000223F
0x180002061  xor     r8d, r8d
0x180002064  test    r15d, r15d
0x180002067  jz      short loc_18000207C
0x180002069  mov     eax, [r13+14h]
0x18000206d  dec     eax
0x18000206f  neg     eax
0x180002071  mov     eax, 11Ah
0x180002076  sbb     edi, edi
0x180002078  and     edi, eax
0x18000207a  jmp     short loc_180002094
0x18000207c  bt      r12d, 9
0x180002081  jb      short loc_180002094
0x180002083  mov     edx, dword ptr [rbp+var_30+4]
0x180002086  lea     r8, [rbp+var_40]
0x18000208a  mov     rcx, rsi
0x18000208d  call    CnvtTimeFromSeq
0x180002092  mov     ebx, eax
0x180002094  mov     ecx, [rsi+158h]
0x18000209a  sub     ecx, 4
0x18000209d  cmp     ecx, 3
0x1800020a0  ja      loc_18000223F
0x1800020a6  mov     edi, 40000h
0x1800020ab  jmp     loc_18000223F
0x1800020b0  test    r15d, r15d
0x1800020b3  jz      short loc_1800020C6
0x1800020b5  mov     ecx, 1
0x1800020ba  mov     eax, 11Ah
0x1800020bf  cmp     [r13+14h], ecx
0x1800020c3  cmovnz  edi, eax
0x1800020c6  mov     edx, dword ptr [rbp+var_40+4]
0x1800020c9  lea     r8, [rbp+var_40]
0x1800020cd  mov     rcx, rsi
0x1800020d0  call    CnvtTimeFromSeq
0x1800020d5  mov     ebx, eax
0x1800020d7  mov     eax, [rsi+158h]
0x1800020dd  sub     eax, 4
0x1800020e0  cmp     eax, 3
0x1800020e3  jmp     short loc_1800020A0
0x1800020e5  sub     eax, 4002h
0x1800020ea  jz      loc_18000220C
0x1800020f0  sub     eax, 1
0x1800020f3  jz      loc_1800021E1
0x1800020f9  sub     eax, 4
0x1800020fc  jz      loc_1800021C3
0x180002102  sub     eax, 1
0x180002105  jz      loc_180002197
0x18000210b  sub     eax, 1
0x18000210e  jz      short loc_180002173
0x180002110  cmp     eax, 1
0x180002113  jz      short loc_18000211F
0x180002115  mov     edi, 112h
0x18000211a  jmp     loc_18000223F
0x18000211f  movzx   ecx, word ptr [rbp+var_40]
0x180002123  xor     r8d, r8d
0x180002126  mov     edi, 10000h
0x18000212b  mov     edx, r8d
0x18000212e  test    ecx, ecx
0x180002130  jz      short loc_180002162
0x180002132  sub     ecx, 18h
0x180002135  jz      short loc_18000215B
0x180002137  sub     ecx, 1
0x18000213a  jz      short loc_180002154
0x18000213c  sub     ecx, 4
0x18000213f  jz      short loc_18000214D
0x180002141  cmp     ecx, 1
0x180002144  jnz     short loc_180002167
0x180002146  mov     edx, 4C4h
0x18000214b  jmp     short loc_180002167
0x18000214d  mov     edx, 4C3h
0x180002152  jmp     short loc_180002167
0x180002154  mov     edx, 4C2h
0x180002159  jmp     short loc_180002167
0x18000215b  mov     edx, 4C1h
0x180002160  jmp     short loc_180002167
0x180002162  mov     edx, 4C0h
0x180002167  mov     ebx, edx
0x180002169  shl     ebx, 10h
0x18000216c  or      ebx, edx
0x18000216e  jmp     loc_18000223F
0x180002173  movzx   eax, byte ptr [rbp+var_20+0Ah]
0x180002177  movzx   ebx, byte ptr [rbp+var_20+0Bh]
0x18000217b  shl     ebx, 8
0x18000217e  add     ebx, eax
0x180002180  movzx   eax, byte ptr [rbp+var_20+9]
0x180002184  shl     ebx, 8
0x180002187  add     ebx, eax
0x180002189  movzx   eax, byte ptr [rbp+var_20+8]
0x18000218d  shl     ebx, 8
0x180002190  add     ebx, eax
0x180002192  jmp     loc_1800020A6
0x180002197  movzx   ecx, word ptr [rbp+var_10+2]
0x18000219b  mov     edi, 10000h
0x1800021a0  test    ecx, ecx
0x1800021a2  jz      short loc_180002205
0x1800021a4  sub     ecx, 2
0x1800021a7  jz      short loc_1800021BC
0x1800021a9  cmp     ecx, 1
0x1800021ac  jnz     loc_18000223F
0x1800021b2  mov     ebx, 4C84004h
0x1800021b7  jmp     loc_18000223F
0x1800021bc  mov     ebx, 4C74003h
0x1800021c1  jmp     short loc_18000223F
0x1800021c3  movzx   ecx, word ptr [rbp+var_10]
0x1800021c7  mov     edi, 10000h
0x1800021cc  test    ecx, ecx
0x1800021ce  jz      short loc_180002205
0x1800021d0  sub     ecx, 1
0x1800021d3  jz      short loc_1800021DA
0x1800021d5  sub     ecx, 1
0x1800021d8  jmp     short loc_1800021A7
0x1800021da  mov     ebx, 4C64002h
0x1800021df  jmp     short loc_18000223F
0x1800021e1  mov     ebx, [rsi+120h]
0x1800021e7  cmp     ebx, 0FFFDh
0x1800021ed  jz      short loc_180002200
0x1800021ef  cmp     ebx, 0FFFFFFFFh
0x1800021f2  jnz     short loc_18000223F
0x1800021f4  mov     edi, 10000h
0x1800021f9  mov     ebx, 4CBFFFFh
0x1800021fe  jmp     short loc_18000223F
0x180002200  mov     edi, 10000h
0x180002205  mov     ebx, 4CAFFFDh
0x18000220a  jmp     short loc_18000223F
0x18000220c  movzx   eax, word ptr [rbp+var_40+2]
0x180002210  mov     ecx, 1
0x180002215  imul    eax, dword ptr [rbp+var_30+0Ch]
0x180002219  cmp     eax, ecx
0x18000221b  cmova   ecx, eax
0x18000221e  xor     edx, edx
0x180002220  mov     eax, 3938700h
0x180002225  xor     r8d, r8d
0x180002228  div     ecx
0x18000222a  mov     ebx, eax
0x18000222c  cmp     word ptr [rbp+var_40], r8w
0x180002231  jz      short loc_18000223F
0x180002233  mov     eax, 88888889h
0x180002238  mul     ebx
0x18000223a  mov     ebx, edx
0x18000223c  shr     ebx, 5
0x18000223f  mov     ecx, ebx
0x180002241  mov     eax, edi
0x180002243  mov     [r13+8], rcx
0x180002247  mov     rcx, [rbp+var_8]
0x18000224b  xor     rcx, rsp; StackCookie
0x18000224e  call    __security_check_cookie
0x180002253  mov     rbx, [rsp+60h+arg_8]
0x18000225b  add     rsp, 60h
0x18000225f  pop     r15
0x180002261  pop     r14
0x180002263  pop     r13
0x180002265  pop     r12
0x180002267  pop     rdi
0x180002268  pop     rsi
0x180002269  pop     rbp
0x18000226a  retn
```

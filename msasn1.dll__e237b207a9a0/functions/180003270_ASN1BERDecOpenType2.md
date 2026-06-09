# ASN1BERDecOpenType2

- ea: `0x180003270`
- end: `0x1800036e5`
- name: `ASN1BERDecOpenType2`
- size: `1141`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001b30`
- `0x180001f50`
- `0x180001f80`
- `0x1800020a0`
- `0x180002200`
- `0x180003270`
- `0x180004310`

## pseudocode

```c
__int64 __fastcall ASN1BERDecOpenType2(__int64 a1, __int64 a2)
{
  int v2; // r8d
  unsigned __int8 *v4; // rdi
  int v5; // r9d
  __int64 v6; // rbx
  int v7; // ebp
  unsigned __int8 *v8; // r10
  char v9; // r12
  int v10; // r12d
  int v11; // r15d
  char v12; // si
  int v13; // esi
  int v14; // r8d
  __int64 v15; // rax
  __int64 result; // rax
  int v17; // ecx
  int v18; // edx
  int v19; // eax
  unsigned int v20; // esi
  unsigned __int8 *v21; // r10
  int v22; // eax
  int v23; // ecx
  unsigned int v24; // esi
  unsigned __int8 *v25; // r10
  int v26; // eax
  unsigned int v27; // r8d
  unsigned int v28; // r8d
  __int64 v29; // rax
  __int64 v30; // rsi
  __int64 v31; // rbp
  unsigned int v32; // r8d
  unsigned int v33; // r8d
  unsigned int v34; // r8d
  __int64 v35; // rdx
  unsigned int v36; // r8d
  int v37; // r13d
  _BYTE *v38; // rax
  char v39; // cl
  int v40; // r11d
  int v41; // esi
  char *v42; // rcx
  char v43; // al
  __int64 v44; // [rsp+70h] [rbp+8h] BYREF
  __int64 v45; // [rsp+80h] [rbp+18h] BYREF

  v2 = *(_DWORD *)(a1 + 16);
  v4 = *(unsigned __int8 **)(a1 + 40);
  v5 = *(_DWORD *)(a1 + 24);
  v44 = 0;
  v45 = 0;
  v6 = a1;
  if ( !(v5 + v2 - (_DWORD)v4) )
    return 0;
  v7 = *v4;
  v8 = v4 + 1;
  v9 = *v4;
  *(_QWORD *)(a1 + 40) = v4 + 1;
  v10 = v9 & 0x1F;
  if ( v10 == 31 )
  {
    v10 = 0;
    v40 = (_DWORD)v4 + 1;
    v41 = 0;
    v42 = (char *)(v4 + 1);
    while ( v5 + v2 - v40 )
    {
      v43 = *v42;
      v40 = (_DWORD)v42 + 1;
      *(_QWORD *)(v6 + 40) = v42 + 1;
      if ( (v10 & 0xE0000000) != 0 )
      {
        ASN1DecSetError(v6, 4294966285LL);
        break;
      }
      v10 = (v10 << 7) | v43 & 0x7F;
      if ( v43 >= 0 )
        goto LABEL_3;
      if ( (unsigned int)++v41 >= 4 )
      {
LABEL_61:
        ASN1DecSetError(v6, 4294966285LL);
        return 0;
      }
      ++v42;
    }
    *(_QWORD *)(v6 + 40) = v4;
    return 0;
  }
LABEL_3:
  *(_QWORD *)(v6 + 40) = v4;
  if ( !(v5 + v2 - (_DWORD)v4) )
    goto LABEL_48;
  v11 = *v4;
  v12 = *v4;
  *(_QWORD *)(v6 + 40) = v8;
  v13 = v12 & 0x1F;
  if ( v13 == 31 )
  {
    v13 = 0;
    v37 = 0;
    while ( (unsigned int)ASN1BERDecCheck(v6, 1) )
    {
      v38 = *(_BYTE **)(v6 + 40);
      v39 = *v38;
      v14 = (_DWORD)v38 + 1;
      *(_QWORD *)(v6 + 40) = v38 + 1;
      if ( (v13 & 0xE0000000) != 0 )
        goto LABEL_61;
      v8 = v38 + 1;
      v13 = (v13 << 7) | v39 & 0x7F;
      if ( v39 >= 0 )
        goto LABEL_6;
      if ( (unsigned int)++v37 >= 4 )
        goto LABEL_61;
    }
    return 0;
  }
  v14 = (_DWORD)v4 + 1;
LABEL_6:
  if ( (v10 | ((v7 & 0xFFFFFFC0) << 24)) != (v13 | ((v11 & 0xFFFFFFC0) << 24)) )
  {
    do
    {
      v15 = *(_QWORD *)(v6 + 56);
      *(_DWORD *)(v6 + 32) = -1011;
      if ( v6 == v15 )
        break;
      v6 = v15;
    }
    while ( v15 );
    return 0;
  }
  v17 = *(_DWORD *)(v6 + 16);
  v18 = *(_DWORD *)(v6 + 24);
  v19 = v18 + v17 - v14;
  if ( (v11 & 0x20) != 0 )
  {
    if ( !v19 )
      goto LABEL_48;
    v24 = *v8;
    v25 = v8 + 1;
    *(_QWORD *)(v6 + 40) = v25;
    if ( v24 < 0x80 )
    {
LABEL_20:
      if ( v24 > v18 + v17 - (int)v25 )
      {
        ASN1DecSetError(v6, 4294966294LL);
        v26 = 0;
      }
      else
      {
        v26 = 1;
      }
      if ( !v26 )
        return 0;
      *(_QWORD *)(v6 + 40) += v24;
      goto LABEL_17;
    }
    if ( v24 == 128 )
    {
      if ( !(unsigned int)BERDecConstructed(v6, 0, 1, (unsigned int)&v44, (__int64)&v45) )
        return 0;
      v30 = v44;
      v31 = v45;
      while ( (unsigned int)ASN1BERDecNotEndOfContents(v30, v31) )
      {
        if ( !(unsigned int)ASN1BERDecSkip(v30) )
          return 0;
      }
      if ( !(unsigned int)ASN1BERDecEndOfContents(v6, v30, v31) )
        return 0;
      goto LABEL_17;
    }
    if ( v24 > 0x84 )
      goto LABEL_74;
    v28 = v24 - 128;
    if ( v24 - 128 > v18 + v17 - (int)v25 )
    {
LABEL_48:
      v35 = 4294966294LL;
LABEL_49:
      ASN1DecSetError(v6, v35);
      return 0;
    }
    v24 = 0;
    if ( v28 != 2 )
    {
      v33 = v28 - 1;
      if ( !v33 )
        goto LABEL_34;
      v34 = v33 - 2;
      if ( v34 )
      {
        if ( v34 != 1 )
          goto LABEL_20;
        v24 = *v25++ << 24;
        *(_QWORD *)(v6 + 40) = v25;
      }
      v24 |= *v25++ << 16;
      *(_QWORD *)(v6 + 40) = v25;
    }
    v24 |= *v25++ << 8;
    *(_QWORD *)(v6 + 40) = v25;
LABEL_34:
    v24 |= *v25;
    *(_QWORD *)(v6 + 40) = v25 + 1;
    LODWORD(v25) = (_DWORD)v25 + 1;
    goto LABEL_20;
  }
  if ( !v19 )
    goto LABEL_48;
  v20 = *v8;
  v21 = v8 + 1;
  *(_QWORD *)(v6 + 40) = v21;
  if ( v20 >= 0x80 )
  {
    if ( v20 == 128 )
    {
      do
      {
        v29 = *(_QWORD *)(v6 + 56);
        *(_DWORD *)(v6 + 32) = -1003;
        if ( v6 == v29 )
          break;
        v6 = v29;
      }
      while ( v29 );
      return 0;
    }
    if ( v20 <= 0x84 )
    {
      v27 = v20 - 128;
      if ( v20 - 128 <= v18 + v17 - (int)v21 )
      {
        v20 = 0;
        if ( v27 != 2 )
        {
          v32 = v27 - 1;
          if ( !v32 )
            goto LABEL_44;
          v36 = v32 - 2;
          if ( v36 )
          {
            if ( v36 != 1 )
              goto LABEL_13;
            v20 = *v21++ << 24;
            *(_QWORD *)(v6 + 40) = v21;
          }
          v20 |= *v21++ << 16;
          *(_QWORD *)(v6 + 40) = v21;
        }
        v20 |= *v21++ << 8;
        *(_QWORD *)(v6 + 40) = v21;
LABEL_44:
        v20 |= *v21;
        *(_QWORD *)(v6 + 40) = v21 + 1;
        LODWORD(v21) = (_DWORD)v21 + 1;
        goto LABEL_13;
      }
      goto LABEL_48;
    }
LABEL_74:
    v35 = 4294966293LL;
    goto LABEL_49;
  }
LABEL_13:
  if ( v20 > v18 + v17 - (int)v21 )
  {
    ASN1DecSetError(v6, 4294966294LL);
    v22 = 0;
  }
  else
  {
    v22 = 1;
  }
  if ( !v22 )
    return 0;
  *(_QWORD *)(v6 + 40) += v20;
LABEL_17:
  result = 1;
  v23 = *(_DWORD *)(v6 + 40) - (_DWORD)v4;
  *(_QWORD *)(a2 + 8) = v4;
  *(_DWORD *)a2 = v23;
  return result;
}

```

## disassembly

```asm
0x180003270  mov     [rsp+arg_8], rbx
0x180003275  push    rbp
0x180003276  push    rsi
0x180003277  push    rdi
0x180003278  push    r12
0x18000327a  push    r13
0x18000327c  push    r14
0x18000327e  push    r15
0x180003280  sub     rsp, 30h
0x180003284  mov     r8d, [rcx+10h]
0x180003288  mov     r14, rdx
0x18000328b  mov     rdi, [rcx+28h]
0x18000328f  mov     eax, r8d
0x180003292  mov     r9d, [rcx+18h]
0x180003296  sub     eax, edi
0x180003298  add     eax, r9d
0x18000329b  mov     [rsp+68h+arg_0], 0
0x1800032a4  mov     [rsp+68h+arg_10], 0
0x1800032b0  mov     rbx, rcx
0x1800032b3  cmp     eax, 1
0x1800032b6  jb      short loc_180003332
0x1800032b8  movzx   ebp, byte ptr [rdi]
0x1800032bb  lea     r10, [rdi+1]
0x1800032bf  mov     r12d, ebp
0x1800032c2  mov     [rcx+28h], r10
0x1800032c6  and     r12d, 1Fh
0x1800032ca  cmp     r12d, 1Fh
0x1800032ce  jz      loc_180003680
0x1800032d4  sub     r8d, edi
0x1800032d7  mov     [rbx+28h], rdi
0x1800032db  add     r8d, r9d
0x1800032de  cmp     r8d, 1
0x1800032e2  jb      loc_180003556
0x1800032e8  movzx   r15d, byte ptr [rdi]
0x1800032ec  mov     esi, r15d
0x1800032ef  mov     [rbx+28h], r10
0x1800032f3  and     esi, 1Fh
0x1800032f6  cmp     esi, 1Fh
0x1800032f9  jz      loc_1800035CA
0x1800032ff  mov     r8d, r10d
0x180003302  and     ebp, 0FFFFFFC0h
0x180003305  mov     eax, r15d
0x180003308  and     eax, 0FFFFFFC0h
0x18000330b  shl     ebp, 18h
0x18000330e  shl     eax, 18h
0x180003311  or      ebp, r12d
0x180003314  or      eax, esi
0x180003316  cmp     ebp, eax
0x180003318  jz      short loc_180003349
0x18000331a  mov     rax, [rbx+38h]
0x18000331e  mov     dword ptr [rbx+20h], 0FFFFFC0Dh
0x180003325  cmp     rbx, rax
0x180003328  jz      short loc_180003332
0x18000332a  mov     rbx, rax
0x18000332d  test    rax, rax
0x180003330  jnz     short loc_18000331A
0x180003332  xor     eax, eax
0x180003334  mov     rbx, [rsp+68h+arg_8]
0x180003339  add     rsp, 30h
0x18000333d  pop     r15
0x18000333f  pop     r14
0x180003341  pop     r13
0x180003343  pop     r12
0x180003345  pop     rdi
0x180003346  pop     rsi
0x180003347  pop     rbp
0x180003348  retn
0x180003349  mov     ecx, [rbx+10h]
0x18000334c  mov     eax, ecx
0x18000334e  mov     edx, [rbx+18h]
0x180003351  sub     eax, r8d
0x180003354  add     eax, edx
0x180003356  test    r15b, 20h
0x18000335a  jnz     short loc_1800033A7
0x18000335c  cmp     eax, 1
0x18000335f  jb      loc_180003556
0x180003365  movzx   esi, byte ptr [r10]
0x180003369  inc     r10
0x18000336c  mov     [rbx+28h], r10
0x180003370  cmp     esi, 80h
0x180003376  jnb     short loc_1800033EF
0x180003378  sub     ecx, r10d
0x18000337b  add     ecx, edx
0x18000337d  cmp     esi, ecx
0x18000337f  ja      loc_180003587
0x180003385  mov     eax, 1
0x18000338a  test    eax, eax
0x18000338c  jz      short loc_180003332
0x18000338e  mov     ecx, esi
0x180003390  add     [rbx+28h], rcx
0x180003394  mov     ecx, [rbx+28h]
0x180003397  mov     eax, 1
0x18000339c  sub     ecx, edi
0x18000339e  mov     [r14+8], rdi
0x1800033a2  mov     [r14], ecx
0x1800033a5  jmp     short loc_180003334
0x1800033a7  cmp     eax, 1
0x1800033aa  jb      loc_180003556
0x1800033b0  movzx   esi, byte ptr [r10]
0x1800033b4  inc     r10
0x1800033b7  mov     [rbx+28h], r10
0x1800033bb  cmp     esi, 80h
0x1800033c1  jnb     short loc_180003436
0x1800033c3  sub     ecx, r10d
0x1800033c6  xor     ebp, ebp
0x1800033c8  add     ecx, edx
0x1800033ca  cmp     esi, ecx
0x1800033cc  ja      loc_18000359B
0x1800033d2  mov     eax, 1
0x1800033d7  test    eax, eax
0x1800033d9  jz      loc_180003332
0x1800033df  test    ebp, ebp
0x1800033e1  jnz     loc_1800034B9
0x1800033e7  mov     eax, esi
0x1800033e9  add     [rbx+28h], rax
0x1800033ed  jmp     short loc_180003394
0x1800033ef  jz      loc_180003490
0x1800033f5  cmp     esi, 84h
0x1800033fb  ja      loc_1800036DB
0x180003401  mov     eax, ecx
0x180003403  lea     r8d, [rsi-80h]
0x180003407  sub     eax, r10d
0x18000340a  add     eax, edx
0x18000340c  cmp     r8d, eax
0x18000340f  ja      loc_180003556
0x180003415  xor     esi, esi
0x180003417  cmp     r8d, 2
0x18000341b  jnz     loc_180003511
0x180003421  movzx   eax, byte ptr [r10]
0x180003425  shl     eax, 8
0x180003428  or      esi, eax
0x18000342a  inc     r10
0x18000342d  mov     [rbx+28h], r10
0x180003431  jmp     loc_180003517
0x180003436  jz      short loc_1800034B2
0x180003438  cmp     esi, 84h
0x18000343e  ja      loc_1800036DB
0x180003444  mov     eax, ecx
0x180003446  lea     r8d, [rsi-80h]
0x18000344a  sub     eax, r10d
0x18000344d  add     eax, edx
0x18000344f  cmp     r8d, eax
0x180003452  ja      loc_180003556
0x180003458  xor     esi, esi
0x18000345a  cmp     r8d, 2
0x18000345e  jnz     loc_18000352D
0x180003464  movzx   eax, byte ptr [r10]
0x180003468  shl     eax, 8
0x18000346b  or      esi, eax
0x18000346d  inc     r10
0x180003470  mov     [rbx+28h], r10
0x180003474  movzx   eax, byte ptr [r10]
0x180003478  or      esi, eax
0x18000347a  lea     rax, [r10+1]
0x18000347e  mov     [rbx+28h], rax
0x180003482  mov     r10d, eax
0x180003485  jmp     loc_1800033C3
0x180003490  mov     rax, [rbx+38h]
0x180003494  mov     dword ptr [rbx+20h], 0FFFFFC15h
0x18000349b  cmp     rbx, rax
0x18000349e  jz      loc_180003332
0x1800034a4  mov     rbx, rax
0x1800034a7  test    rax, rax
0x1800034aa  jz      loc_180003332
0x1800034b0  jmp     short loc_180003490
0x1800034b2  xor     esi, esi
0x1800034b4  mov     ebp, 1
0x1800034b9  lea     rax, [rsp+68h+arg_10]
0x1800034c1  mov     r8d, ebp
0x1800034c4  lea     r9, [rsp+68h+arg_0]
0x1800034c9  mov     [rsp+68h+var_48], rax
0x1800034ce  mov     edx, esi
0x1800034d0  mov     rcx, rbx
0x1800034d3  call    _BERDecConstructed
0x1800034d8  test    eax, eax
0x1800034da  jz      loc_180003332
0x1800034e0  mov     rsi, [rsp+68h+arg_0]
0x1800034e5  mov     rbp, [rsp+68h+arg_10]
0x1800034ed  mov     rdx, rbp
0x1800034f0  mov     rcx, rsi
0x1800034f3  call    ASN1BERDecNotEndOfContents
0x1800034f8  test    eax, eax
0x1800034fa  jz      loc_1800035AF
0x180003500  mov     rcx, rsi
0x180003503  call    ASN1BERDecSkip
0x180003508  test    eax, eax
0x18000350a  jnz     short loc_1800034ED
0x18000350c  jmp     loc_180003332
0x180003511  sub     r8d, 1
0x180003515  jnz     short loc_180003568
0x180003517  movzx   eax, byte ptr [r10]
0x18000351b  or      esi, eax
0x18000351d  lea     rax, [r10+1]
0x180003521  mov     [rbx+28h], rax
0x180003525  mov     r10d, eax
0x180003528  jmp     loc_180003378
0x18000352d  sub     r8d, 1
0x180003531  jz      loc_180003474
0x180003537  sub     r8d, 2
0x18000353b  jnz     loc_18000364C
0x180003541  movzx   eax, byte ptr [r10]
0x180003545  shl     eax, 10h
0x180003548  or      esi, eax
0x18000354a  inc     r10
0x18000354d  mov     [rbx+28h], r10
0x180003551  jmp     loc_180003464
0x180003556  mov     edx, 0FFFFFC16h
0x18000355b  mov     rcx, rbx
0x18000355e  call    ASN1DecSetError
0x180003563  jmp     loc_180003332
0x180003568  sub     r8d, 2
0x18000356c  jnz     loc_18000362F
0x180003572  movzx   eax, byte ptr [r10]
0x180003576  shl     eax, 10h
0x180003579  or      esi, eax
0x18000357b  inc     r10
0x18000357e  mov     [rbx+28h], r10
0x180003582  jmp     loc_180003421
0x180003587  mov     edx, 0FFFFFC16h
0x18000358c  mov     rcx, rbx
0x18000358f  call    ASN1DecSetError
0x180003594  xor     eax, eax
0x180003596  jmp     loc_18000338A
0x18000359b  mov     edx, 0FFFFFC16h
0x1800035a0  mov     rcx, rbx
0x1800035a3  call    ASN1DecSetError
0x1800035a8  xor     eax, eax
0x1800035aa  jmp     loc_1800033D7
0x1800035af  mov     r8, rbp
0x1800035b2  mov     rdx, rsi
0x1800035b5  mov     rcx, rbx
0x1800035b8  call    ASN1BERDecEndOfContents
0x1800035bd  test    eax, eax
0x1800035bf  jnz     loc_180003394
0x1800035c5  jmp     loc_180003332
0x1800035ca  xor     esi, esi
0x1800035cc  xor     r13d, r13d
0x1800035cf  mov     edx, 1
0x1800035d4  mov     rcx, rbx
0x1800035d7  call    ASN1BERDecCheck
0x1800035dc  test    eax, eax
0x1800035de  jz      loc_180003332
0x1800035e4  mov     rax, [rbx+28h]
0x1800035e8  movzx   ecx, byte ptr [rax]
0x1800035eb  lea     r8, [rax+1]
0x1800035ef  mov     [rbx+28h], r8
0x1800035f3  test    esi, 0E0000000h
0x1800035f9  jnz     short loc_18000361D
0x1800035fb  mov     eax, esi
0x1800035fd  mov     edx, ecx
0x1800035ff  and     ecx, 7Fh
0x180003602  shl     eax, 7
0x180003605  mov     esi, ecx
0x180003607  mov     r10, r8
0x18000360a  or      esi, eax
0x18000360c  test    dl, dl
0x18000360e  jns     loc_180003302
0x180003614  inc     r13d
0x180003617  cmp     r13d, 4
0x18000361b  jb      short loc_1800035CF
0x18000361d  mov     edx, 0FFFFFC0Dh
0x180003622  mov     rcx, rbx
0x180003625  call    ASN1DecSetError
0x18000362a  jmp     loc_180003332
0x18000362f  cmp     r8d, 1
0x180003633  jnz     loc_180003378
0x180003639  movzx   esi, byte ptr [r10]
0x18000363d  shl     esi, 18h
0x180003640  inc     r10
0x180003643  mov     [rbx+28h], r10
0x180003647  jmp     loc_180003572
0x18000364c  cmp     r8d, 1
0x180003650  jnz     loc_1800033C3
0x180003656  movzx   esi, byte ptr [r10]
0x18000365a  shl     esi, 18h
0x18000365d  inc     r10
0x180003660  mov     [rbx+28h], r10
0x180003664  jmp     loc_180003541
0x180003669  mov     eax, r8d
0x18000366c  sub     eax, r11d
0x18000366f  add     eax, r9d
0x180003672  cmp     eax, 1
0x180003675  jnb     short loc_18000368D
0x180003677  mov     [rbx+28h], rdi
0x18000367b  jmp     loc_180003332
0x180003680  xor     r12d, r12d
0x180003683  mov     r11d, r10d
0x180003686  xor     esi, esi
0x180003688  mov     rcx, r10
0x18000368b  jmp     short loc_180003669
0x18000368d  movzx   eax, byte ptr [rcx]
0x180003690  lea     r11, [rcx+1]
0x180003694  mov     [rbx+28h], r11
0x180003698  test    r12d, 0E0000000h
0x18000369f  jnz     short loc_1800036CC
0x1800036a1  mov     ecx, eax
0x1800036a3  mov     edx, eax
0x1800036a5  mov     eax, r12d
0x1800036a8  and     ecx, 7Fh
0x1800036ab  shl     eax, 7
  ... truncated ...
```

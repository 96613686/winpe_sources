# _BERDecOpenType

- ea: `0x1800026b0`
- end: `0x180002bdc`
- name: `_BERDecOpenType`
- size: `1324`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800026a0`

## callees

- `0x180001b30`
- `0x180001f50`
- `0x180001f80`
- `0x1800020a0`
- `0x180002200`
- `0x1800026b0`
- `0x180004310`
- `0x18000aadd`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002922`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002922`

## pseudocode

```c
__int64 __fastcall BERDecOpenType(__int64 a1, unsigned int *a2, int a3)
{
  int v3; // r9d
  unsigned __int8 *v4; // rdi
  int v5; // r10d
  __int64 v8; // rbx
  int v9; // ebp
  unsigned __int8 *v10; // r8
  char v11; // r13
  int v12; // r13d
  int v13; // r15d
  char v14; // si
  int v15; // esi
  int v16; // r9d
  __int64 v17; // rax
  int v19; // ecx
  int v20; // edx
  int v21; // eax
  unsigned int v22; // esi
  unsigned __int8 *v23; // r8
  int v24; // eax
  unsigned int v25; // ecx
  unsigned int v26; // esi
  unsigned __int8 *v27; // r8
  int v28; // eax
  unsigned int v29; // r9d
  unsigned int v30; // r9d
  __int64 v31; // rax
  char *v32; // rsi
  SIZE_T v33; // rdx
  __int64 v34; // rsi
  __int64 v35; // rbp
  unsigned int v36; // r9d
  unsigned int v37; // r9d
  unsigned int v38; // r9d
  __int64 v39; // rdx
  unsigned int v40; // r9d
  _BYTE *v41; // rax
  char v42; // cl
  unsigned int v43; // ecx
  int v44; // esi
  int v45; // r11d
  char *v46; // rcx
  char v47; // al
  __int64 v48[9]; // [rsp+30h] [rbp-48h] BYREF
  int v49; // [rsp+80h] [rbp+8h]
  __int64 v50; // [rsp+98h] [rbp+20h] BYREF

  v3 = *(_DWORD *)(a1 + 16);
  v4 = *(unsigned __int8 **)(a1 + 40);
  v5 = *(_DWORD *)(a1 + 24);
  v50 = 0;
  v48[0] = 0;
  v8 = a1;
  if ( !(v5 + v3 - (_DWORD)v4) )
    return 0;
  v9 = *v4;
  v10 = v4 + 1;
  v11 = *v4;
  *(_QWORD *)(a1 + 40) = v4 + 1;
  v12 = v11 & 0x1F;
  if ( v12 == 31 )
  {
    v12 = 0;
    v44 = 0;
    v45 = (_DWORD)v4 + 1;
    v46 = (char *)(v4 + 1);
    while ( v5 + v3 - v45 )
    {
      v47 = *v46;
      v45 = (_DWORD)v46 + 1;
      *(_QWORD *)(v8 + 40) = v46 + 1;
      if ( (v12 & 0xE0000000) != 0 )
      {
        ASN1DecSetError(v8, 4294966285LL);
        break;
      }
      v12 = (v12 << 7) | v47 & 0x7F;
      if ( v47 >= 0 )
        goto LABEL_3;
      if ( (unsigned int)++v44 >= 4 )
      {
LABEL_68:
        ASN1DecSetError(v8, 4294966285LL);
        return 0;
      }
      ++v46;
    }
    *(_QWORD *)(v8 + 40) = v4;
    return 0;
  }
LABEL_3:
  *(_QWORD *)(v8 + 40) = v4;
  if ( !(v5 + v3 - (_DWORD)v4) )
    goto LABEL_55;
  v13 = *v4;
  v14 = *v4;
  *(_QWORD *)(v8 + 40) = v10;
  v15 = v14 & 0x1F;
  if ( v15 == 31 )
  {
    v15 = 0;
    v49 = 0;
    while ( (unsigned int)ASN1BERDecCheck(v8, 1) )
    {
      v41 = *(_BYTE **)(v8 + 40);
      v42 = *v41;
      v16 = (_DWORD)v41 + 1;
      *(_QWORD *)(v8 + 40) = v41 + 1;
      if ( (v15 & 0xE0000000) != 0 )
        goto LABEL_68;
      v10 = v41 + 1;
      v15 = (v15 << 7) | v42 & 0x7F;
      if ( v42 >= 0 )
        goto LABEL_6;
      if ( (unsigned int)++v49 >= 4 )
        goto LABEL_68;
    }
    return 0;
  }
  v16 = (_DWORD)v4 + 1;
LABEL_6:
  if ( (v12 | ((v9 & 0xFFFFFFC0) << 24)) != (v15 | ((v13 & 0xFFFFFFC0) << 24)) )
  {
    do
    {
      v17 = *(_QWORD *)(v8 + 56);
      *(_DWORD *)(v8 + 32) = -1011;
      if ( v8 == v17 )
        break;
      v8 = v17;
    }
    while ( v17 );
    return 0;
  }
  v19 = *(_DWORD *)(v8 + 16);
  v20 = *(_DWORD *)(v8 + 24);
  v21 = v20 + v19 - v16;
  if ( (v13 & 0x20) != 0 )
  {
    if ( !v21 )
      goto LABEL_55;
    v26 = *v10;
    v27 = v10 + 1;
    *(_QWORD *)(v8 + 40) = v27;
    if ( v26 < 0x80 )
    {
LABEL_21:
      if ( v26 > v20 + v19 - (int)v27 )
      {
        ASN1DecSetError(v8, 4294966294LL);
        v28 = 0;
      }
      else
      {
        v28 = 1;
      }
      if ( !v28 )
        return 0;
      *(_QWORD *)(v8 + 40) += v26;
      goto LABEL_17;
    }
    if ( v26 == 128 )
    {
      if ( !(unsigned int)BERDecConstructed(v8, 0, 1, (unsigned int)&v50, (__int64)v48) )
        return 0;
      v34 = v50;
      v35 = v48[0];
      while ( (unsigned int)ASN1BERDecNotEndOfContents(v34, v35) )
      {
        if ( !(unsigned int)ASN1BERDecSkip(v34) )
          return 0;
      }
      if ( !(unsigned int)ASN1BERDecEndOfContents(v8, v34, v35) )
        return 0;
      goto LABEL_17;
    }
    if ( v26 > 0x84 )
      goto LABEL_86;
    v30 = v26 - 128;
    if ( v26 - 128 > v20 + v19 - (int)v27 )
    {
LABEL_55:
      v39 = 4294966294LL;
LABEL_56:
      ASN1DecSetError(v8, v39);
      return 0;
    }
    v26 = 0;
    if ( v30 != 2 )
    {
      v37 = v30 - 1;
      if ( !v37 )
        goto LABEL_35;
      v38 = v37 - 2;
      if ( v38 )
      {
        if ( v38 != 1 )
          goto LABEL_21;
        v26 = *v27++ << 24;
        *(_QWORD *)(v8 + 40) = v27;
      }
      v26 |= *v27++ << 16;
      *(_QWORD *)(v8 + 40) = v27;
    }
    v26 |= *v27++ << 8;
    *(_QWORD *)(v8 + 40) = v27;
LABEL_35:
    v26 |= *v27;
    *(_QWORD *)(v8 + 40) = v27 + 1;
    LODWORD(v27) = (_DWORD)v27 + 1;
    goto LABEL_21;
  }
  if ( !v21 )
    goto LABEL_55;
  v22 = *v10;
  v23 = v10 + 1;
  *(_QWORD *)(v8 + 40) = v23;
  if ( v22 >= 0x80 )
  {
    if ( v22 == 128 )
    {
      do
      {
        v31 = *(_QWORD *)(v8 + 56);
        *(_DWORD *)(v8 + 32) = -1003;
        if ( v8 == v31 )
          break;
        v8 = v31;
      }
      while ( v31 );
      return 0;
    }
    if ( v22 <= 0x84 )
    {
      v29 = v22 - 128;
      if ( v22 - 128 <= v20 + v19 - (int)v23 )
      {
        v22 = 0;
        if ( v29 != 2 )
        {
          v36 = v29 - 1;
          if ( !v36 )
            goto LABEL_51;
          v40 = v36 - 2;
          if ( v40 )
          {
            if ( v40 != 1 )
              goto LABEL_13;
            v22 = *v23++ << 24;
            *(_QWORD *)(v8 + 40) = v23;
          }
          v22 |= *v23++ << 16;
          *(_QWORD *)(v8 + 40) = v23;
        }
        v22 |= *v23++ << 8;
        *(_QWORD *)(v8 + 40) = v23;
LABEL_51:
        v22 |= *v23;
        *(_QWORD *)(v8 + 40) = v23 + 1;
        LODWORD(v23) = (_DWORD)v23 + 1;
        goto LABEL_13;
      }
      goto LABEL_55;
    }
LABEL_86:
    v39 = 4294966293LL;
    goto LABEL_56;
  }
LABEL_13:
  if ( v22 > v20 + v19 - (int)v23 )
  {
    ASN1DecSetError(v8, 4294966294LL);
    v24 = 0;
  }
  else
  {
    v24 = 1;
  }
  if ( !v24 )
    return 0;
  *(_QWORD *)(v8 + 40) += v22;
LABEL_17:
  v25 = *(_DWORD *)(v8 + 40) - (_DWORD)v4;
  *a2 = v25;
  if ( a3 )
  {
    *((_QWORD *)a2 + 1) = v4;
    return 1;
  }
  v32 = 0;
  v33 = (v25 + 3) & 0xFFFFFFFC;
  if ( v25 <= (unsigned int)v33 )
  {
    if ( !*(_DWORD *)(v8 + 76) )
    {
      v32 = (char *)LocalAlloc(0x40u, v33);
      goto LABEL_42;
    }
    v43 = *(_DWORD *)(v8 + 104);
    if ( v43 >= (unsigned int)v33 )
    {
      v32 = *(char **)(v8 + 96);
      *(_QWORD *)(v8 + 96) = &v32[(unsigned int)v33];
      *(_DWORD *)(v8 + 104) = v43 - v33;
LABEL_42:
      if ( v32 )
        goto LABEL_43;
    }
  }
  ASN1DecSetError(v8, 4294966290LL);
LABEL_43:
  *((_QWORD *)a2 + 1) = v32;
  if ( !v32 )
    return 0;
  memcpy_0(v32, v4, *a2);
  return 1;
}

```

## disassembly

```asm
0x1800026b0  mov     [rsp+arg_8], rbx
0x1800026b5  push    rbp
0x1800026b6  push    rsi
0x1800026b7  push    rdi
0x1800026b8  push    r12
0x1800026ba  push    r13
0x1800026bc  push    r14
0x1800026be  push    r15
0x1800026c0  sub     rsp, 40h
0x1800026c4  mov     r9d, [rcx+10h]
0x1800026c8  xor     r11d, r11d
0x1800026cb  mov     rdi, [rcx+28h]
0x1800026cf  mov     eax, r9d
0x1800026d2  mov     r10d, [rcx+18h]
0x1800026d6  sub     eax, edi
0x1800026d8  add     eax, r10d
0x1800026db  mov     [rsp+78h+arg_18], r11
0x1800026e3  mov     [rsp+78h+var_48], r11
0x1800026e8  mov     r12d, r8d
0x1800026eb  mov     r14, rdx
0x1800026ee  mov     rbx, rcx
0x1800026f1  cmp     eax, 1
0x1800026f4  jb      short loc_180002770
0x1800026f6  movzx   ebp, byte ptr [rdi]
0x1800026f9  lea     r8, [rdi+1]
0x1800026fd  mov     r13d, ebp
0x180002700  mov     [rcx+28h], r8
0x180002704  and     r13d, 1Fh
0x180002708  cmp     r13d, 1Fh
0x18000270c  jz      loc_180002B6A
0x180002712  sub     r9d, edi
0x180002715  mov     [rbx+28h], rdi
0x180002719  add     r9d, r10d
0x18000271c  cmp     r9d, 1
0x180002720  jb      loc_1800029FE
0x180002726  movzx   r15d, byte ptr [rdi]
0x18000272a  mov     esi, r15d
0x18000272d  mov     [rbx+28h], r8
0x180002731  and     esi, 1Fh
0x180002734  cmp     esi, 1Fh
0x180002737  jz      loc_180002A72
0x18000273d  mov     r9d, r8d
0x180002740  and     ebp, 0FFFFFFC0h
0x180002743  mov     eax, r15d
0x180002746  and     eax, 0FFFFFFC0h
0x180002749  shl     ebp, 18h
0x18000274c  shl     eax, 18h
0x18000274f  or      ebp, r13d
0x180002752  or      eax, esi
0x180002754  cmp     ebp, eax
0x180002756  jz      short loc_18000278A
0x180002758  mov     rax, [rbx+38h]
0x18000275c  mov     dword ptr [rbx+20h], 0FFFFFC0Dh
0x180002763  cmp     rbx, rax
0x180002766  jz      short loc_180002770
0x180002768  mov     rbx, rax
0x18000276b  test    rax, rax
0x18000276e  jnz     short loc_180002758
0x180002770  xor     eax, eax
0x180002772  mov     rbx, [rsp+78h+arg_8]
0x18000277a  add     rsp, 40h
0x18000277e  pop     r15
0x180002780  pop     r14
0x180002782  pop     r13
0x180002784  pop     r12
0x180002786  pop     rdi
0x180002787  pop     rsi
0x180002788  pop     rbp
0x180002789  retn
0x18000278a  mov     ecx, [rbx+10h]
0x18000278d  mov     eax, ecx
0x18000278f  mov     edx, [rbx+18h]
0x180002792  sub     eax, r9d
0x180002795  add     eax, edx
0x180002797  test    r15b, 20h
0x18000279b  jnz     short loc_1800027F8
0x18000279d  cmp     eax, 1
0x1800027a0  jb      loc_1800029FE
0x1800027a6  movzx   esi, byte ptr [r8]
0x1800027aa  inc     r8
0x1800027ad  mov     [rbx+28h], r8
0x1800027b1  cmp     esi, 80h
0x1800027b7  jnb     loc_180002841
0x1800027bd  sub     ecx, r8d
0x1800027c0  add     ecx, edx
0x1800027c2  cmp     esi, ecx
0x1800027c4  ja      loc_180002A2F
0x1800027ca  mov     eax, 1
0x1800027cf  test    eax, eax
0x1800027d1  jz      short loc_180002770
0x1800027d3  mov     ecx, esi
0x1800027d5  add     [rbx+28h], rcx
0x1800027d9  mov     ecx, [rbx+28h]
0x1800027dc  sub     ecx, edi
0x1800027de  mov     [r14], ecx
0x1800027e1  test    r12d, r12d
0x1800027e4  jz      loc_180002904
0x1800027ea  mov     [r14+8], rdi
0x1800027ee  mov     eax, 1
0x1800027f3  jmp     loc_180002772
0x1800027f8  cmp     eax, 1
0x1800027fb  jb      loc_1800029FE
0x180002801  movzx   esi, byte ptr [r8]
0x180002805  inc     r8
0x180002808  mov     [rbx+28h], r8
0x18000280c  cmp     esi, 80h
0x180002812  jnb     short loc_180002889
0x180002814  sub     ecx, r8d
0x180002817  mov     ebp, r11d
0x18000281a  add     ecx, edx
0x18000281c  cmp     esi, ecx
0x18000281e  ja      loc_180002A43
0x180002824  mov     eax, 1
0x180002829  test    eax, eax
0x18000282b  jz      loc_180002770
0x180002831  test    ebp, ebp
0x180002833  jnz     loc_180002961
0x180002839  mov     eax, esi
0x18000283b  add     [rbx+28h], rax
0x18000283f  jmp     short loc_1800027D9
0x180002841  jz      loc_1800028E2
0x180002847  cmp     esi, 84h
0x18000284d  ja      loc_180002BD2
0x180002853  mov     eax, ecx
0x180002855  lea     r9d, [rsi-80h]
0x180002859  sub     eax, r8d
0x18000285c  add     eax, edx
0x18000285e  cmp     r9d, eax
0x180002861  ja      loc_1800029FE
0x180002867  mov     esi, r11d
0x18000286a  cmp     r9d, 2
0x18000286e  jnz     loc_1800029B9
0x180002874  movzx   eax, byte ptr [r8]
0x180002878  shl     eax, 8
0x18000287b  or      esi, eax
0x18000287d  inc     r8
0x180002880  mov     [rbx+28h], r8
0x180002884  jmp     loc_1800029BF
0x180002889  jz      loc_180002959
0x18000288f  cmp     esi, 84h
0x180002895  ja      loc_180002BD2
0x18000289b  mov     eax, ecx
0x18000289d  lea     r9d, [rsi-80h]
0x1800028a1  sub     eax, r8d
0x1800028a4  add     eax, edx
0x1800028a6  cmp     r9d, eax
0x1800028a9  ja      loc_1800029FE
0x1800028af  mov     esi, r11d
0x1800028b2  cmp     r9d, 2
0x1800028b6  jnz     loc_1800029D5
0x1800028bc  movzx   eax, byte ptr [r8]
0x1800028c0  shl     eax, 8
0x1800028c3  or      esi, eax
0x1800028c5  inc     r8
0x1800028c8  mov     [rbx+28h], r8
0x1800028cc  movzx   eax, byte ptr [r8]
0x1800028d0  or      esi, eax
0x1800028d2  lea     rax, [r8+1]
0x1800028d6  mov     [rbx+28h], rax
0x1800028da  mov     r8d, eax
0x1800028dd  jmp     loc_180002814
0x1800028e2  mov     rax, [rbx+38h]
0x1800028e6  mov     dword ptr [rbx+20h], 0FFFFFC15h
0x1800028ed  cmp     rbx, rax
0x1800028f0  jz      loc_180002770
0x1800028f6  mov     rbx, rax
0x1800028f9  test    rax, rax
0x1800028fc  jz      loc_180002770
0x180002902  jmp     short loc_1800028E2
0x180002904  lea     edx, [rcx+3]
0x180002907  xor     esi, esi
0x180002909  and     edx, 0FFFFFFFCh; uBytes
0x18000290c  cmp     ecx, edx
0x18000290e  ja      loc_180002AE9
0x180002914  cmp     [rbx+4Ch], esi
0x180002917  jnz     loc_180002B35
0x18000291d  mov     ecx, 40h ; '@'; uFlags
0x180002922  call    cs:__imp_LocalAlloc
0x180002928  mov     rsi, rax
0x18000292b  test    rsi, rsi
0x18000292e  jz      loc_180002AE9
0x180002934  mov     [r14+8], rsi
0x180002938  test    rsi, rsi
0x18000293b  jz      loc_180002770
0x180002941  mov     r8d, [r14]; Size
0x180002944  mov     rdx, rdi; Src
0x180002947  mov     rcx, rsi; void *
0x18000294a  call    memcpy_0
0x18000294f  mov     eax, 1
0x180002954  jmp     loc_180002772
0x180002959  mov     esi, r11d
0x18000295c  mov     ebp, 1
0x180002961  lea     rax, [rsp+78h+var_48]
0x180002966  mov     r8d, ebp
0x180002969  lea     r9, [rsp+78h+arg_18]
0x180002971  mov     [rsp+78h+var_58], rax
0x180002976  mov     edx, esi
0x180002978  mov     rcx, rbx
0x18000297b  call    _BERDecConstructed
0x180002980  test    eax, eax
0x180002982  jz      loc_180002770
0x180002988  mov     rsi, [rsp+78h+arg_18]
0x180002990  mov     rbp, [rsp+78h+var_48]
0x180002995  mov     rdx, rbp
0x180002998  mov     rcx, rsi
0x18000299b  call    ASN1BERDecNotEndOfContents
0x1800029a0  test    eax, eax
0x1800029a2  jz      loc_180002A57
0x1800029a8  mov     rcx, rsi
0x1800029ab  call    ASN1BERDecSkip
0x1800029b0  test    eax, eax
0x1800029b2  jnz     short loc_180002995
0x1800029b4  jmp     loc_180002770
0x1800029b9  sub     r9d, 1
0x1800029bd  jnz     short loc_180002A10
0x1800029bf  movzx   eax, byte ptr [r8]
0x1800029c3  or      esi, eax
0x1800029c5  lea     rax, [r8+1]
0x1800029c9  mov     [rbx+28h], rax
0x1800029cd  mov     r8d, eax
0x1800029d0  jmp     loc_1800027BD
0x1800029d5  sub     r9d, 1
0x1800029d9  jz      loc_1800028CC
0x1800029df  sub     r9d, 2
0x1800029e3  jnz     loc_180002B18
0x1800029e9  movzx   eax, byte ptr [r8]
0x1800029ed  shl     eax, 10h
0x1800029f0  or      esi, eax
0x1800029f2  inc     r8
0x1800029f5  mov     [rbx+28h], r8
0x1800029f9  jmp     loc_1800028BC
0x1800029fe  mov     edx, 0FFFFFC16h
0x180002a03  mov     rcx, rbx
0x180002a06  call    ASN1DecSetError
0x180002a0b  jmp     loc_180002770
0x180002a10  sub     r9d, 2
0x180002a14  jnz     loc_180002AFB
0x180002a1a  movzx   eax, byte ptr [r8]
0x180002a1e  shl     eax, 10h
0x180002a21  or      esi, eax
0x180002a23  inc     r8
0x180002a26  mov     [rbx+28h], r8
0x180002a2a  jmp     loc_180002874
0x180002a2f  mov     edx, 0FFFFFC16h
0x180002a34  mov     rcx, rbx
0x180002a37  call    ASN1DecSetError
0x180002a3c  xor     eax, eax
0x180002a3e  jmp     loc_1800027CF
0x180002a43  mov     edx, 0FFFFFC16h
0x180002a48  mov     rcx, rbx
0x180002a4b  call    ASN1DecSetError
0x180002a50  xor     eax, eax
0x180002a52  jmp     loc_180002829
0x180002a57  mov     r8, rbp
0x180002a5a  mov     rdx, rsi
0x180002a5d  mov     rcx, rbx
0x180002a60  call    ASN1BERDecEndOfContents
0x180002a65  test    eax, eax
0x180002a67  jnz     loc_1800027D9
0x180002a6d  jmp     loc_180002770
0x180002a72  mov     esi, r11d
0x180002a75  mov     [rsp+78h+arg_0], r11d
0x180002a7d  mov     edx, 1
0x180002a82  mov     rcx, rbx
0x180002a85  call    ASN1BERDecCheck
0x180002a8a  test    eax, eax
0x180002a8c  jz      loc_180002770
0x180002a92  mov     rax, [rbx+28h]
0x180002a96  movzx   ecx, byte ptr [rax]
0x180002a99  lea     r9, [rax+1]
0x180002a9d  mov     [rbx+28h], r9
0x180002aa1  test    esi, 0E0000000h
0x180002aa7  jnz     short loc_180002AD7
0x180002aa9  mov     eax, esi
0x180002aab  mov     edx, ecx
0x180002aad  and     ecx, 7Fh
0x180002ab0  shl     eax, 7
0x180002ab3  mov     esi, ecx
0x180002ab5  mov     r8, r9
0x180002ab8  or      esi, eax
0x180002aba  test    dl, dl
0x180002abc  jns     loc_180002BCA
0x180002ac2  mov     eax, [rsp+78h+arg_0]
0x180002ac9  inc     eax
0x180002acb  mov     [rsp+78h+arg_0], eax
0x180002ad2  cmp     eax, 4
0x180002ad5  jb      short loc_180002A7D
0x180002ad7  mov     edx, 0FFFFFC0Dh
0x180002adc  mov     rcx, rbx
0x180002adf  call    ASN1DecSetError
0x180002ae4  jmp     loc_180002770
0x180002ae9  mov     edx, 0FFFFFC12h
0x180002aee  mov     rcx, rbx
0x180002af1  call    ASN1DecSetError
0x180002af6  jmp     loc_180002934
0x180002afb  cmp     r9d, 1
0x180002aff  jnz     loc_1800027BD
0x180002b05  movzx   esi, byte ptr [r8]
0x180002b09  shl     esi, 18h
0x180002b0c  inc     r8
  ... truncated ...
```

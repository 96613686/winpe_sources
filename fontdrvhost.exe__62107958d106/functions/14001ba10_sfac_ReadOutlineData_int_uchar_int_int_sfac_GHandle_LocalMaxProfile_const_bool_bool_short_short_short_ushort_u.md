# sfac_ReadOutlineData(int *,uchar *,int *,int *,sfac_GHandle *,LocalMaxProfile const *,bool,bool,short,short *,short *,ushort *,uchar const * *,uint *,uint *)

- ea: `0x14001ba10`
- end: `0x14001beea`
- name: `?sfac_ReadOutlineData@@YAHPEAHPEAE00PEAUsfac_GHandle@@PEBULocalMaxProfile@@_N4FPEAF5PEAGPEAPEBEPEAI8@Z`
- size: `1242`
- prototype: `int(int *, unsigned __int8 *, int *, int *, struct sfac_GHandle *, const struct LocalMaxProfile *, bool, bool, __int16, __int16 *, __int16 *, unsigned __int16 *, const unsigned __int8 **, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400197e0`

## callees

- `0x14001ba10`
- `0x140072578`
- `0x14007680c`

## pseudocode

```c
__int64 __fastcall sfac_ReadOutlineData(
        int *a1,
        unsigned __int8 *a2,
        int *a3,
        int *a4,
        struct sfac_GHandle *a5,
        const struct LocalMaxProfile *a6,
        bool a7,
        bool a8,
        unsigned __int16 a9,
        __int16 *a10,
        __int16 *a11,
        unsigned __int16 *a12,
        const unsigned __int8 **a13,
        unsigned int *a14,
        unsigned int *a15)
{
  unsigned __int8 *v15; // rbx
  int *v17; // r15
  unsigned __int8 *v18; // rdi
  __int64 v19; // rcx
  unsigned __int64 i; // rdx
  unsigned __int64 v22; // r8
  bool v23; // cf
  unsigned __int16 v24; // bp
  unsigned __int8 *v25; // r14
  unsigned __int8 *v26; // rcx
  unsigned __int8 v27; // al
  int v28; // esi
  int *v29; // r11
  int v30; // r9d
  unsigned __int8 *v31; // r10
  unsigned __int8 v32; // al
  unsigned __int8 *v33; // r8
  int v34; // r11d
  int v35; // r8d
  unsigned __int8 v36; // al
  int v37; // r9d
  unsigned __int64 v38; // rax
  unsigned __int16 *v39; // r10
  unsigned __int16 *v40; // r9
  unsigned __int64 v41; // r12
  __int64 v42; // rax
  __int16 *v43; // r14
  signed __int16 v44; // cx
  __int64 v45; // r8
  int v46; // ecx
  int *v47; // [rsp+88h] [rbp+20h]

  v47 = a4;
  v15 = 0;
  v17 = a3;
  v18 = a2;
  *a10 = 0;
  *a11 = 0;
  *a2 = 1;
  *a4 = 0;
  *a3 = 0;
  *a13 = 0;
  *a12 = 0;
  *a1 = 0;
  if ( !a7 && !a8 )
    return 0;
  if ( (__int16)a9 <= 0 )
    return 5123;
  v19 = *((unsigned __int16 *)a6 + 4);
  if ( a9 > (unsigned __int16)v19 )
    return 5123;
  i = (__int16)a9 + (unsigned __int64)*a15;
  if ( i > 0xFFFFFFFF )
    goto LABEL_5;
  v23 = (unsigned __int16)v19 < *((_WORD *)a6 + 6);
  *a15 = i;
  if ( v23 )
    LOWORD(v19) = *((_WORD *)a6 + 6);
  if ( (unsigned int)i > (unsigned __int16)v19 )
    return 5123;
  v41 = 0;
  v39 = 0;
  if ( a7 )
  {
    i = (unsigned __int64)(__int16)a9 >> 32;
    v38 = 2LL * (unsigned int)(__int16)a9;
    if ( v38 > 0x7FFFFFFFFFFFFFFFLL )
      goto LABEL_5;
    i = (unsigned __int64)a5;
    v39 = (unsigned __int16 *)*((_QWORD *)a5 + 3);
    v40 = &v39[v38 / 2];
    if ( &v39[v38 / 2] < v39 )
      goto LABEL_5;
    i = (unsigned __int64)(v40 + 1);
    v41 = *(unsigned int *)a5 + *((_QWORD *)a5 + 1);
    if ( (unsigned __int64)(v40 + 1) > v41 )
      return 5133;
    v19 = *(unsigned __int8 *)v40;
    LOWORD(v19) = _byteswap_ushort(*v40);
    *a12 = v19;
    *a13 = (const unsigned __int8 *)i;
    v42 = *a12;
    v15 = (unsigned __int8 *)(v42 + i);
    if ( v42 + i < i )
      goto LABEL_5;
    v43 = a10;
    *a10 = 0;
    v19 = *(unsigned __int8 *)v39;
    LOWORD(v19) = _byteswap_ushort(*v39);
    *a11 = v19;
  }
  else
  {
    v43 = a10;
  }
  i = 1;
  v28 = *a11 + 1;
  while ( 1 )
  {
    *a1 = v28;
    if ( (int)i >= (__int16)a9 )
      break;
    v19 = a11[(int)i - 1] + 1LL;
    if ( (unsigned __int64)(a11[(int)i - 1] + 32769LL) > 0xFFFF )
      goto LABEL_5;
    v43[(int)i] = v19;
    v44 = _byteswap_ushort(v39[(int)i]);
    a11[(int)i] = v44;
    v45 = v44;
    v46 = *a1;
    if ( *a1 > (int)v45 || v46 > *((unsigned __int16 *)a6 + 3) || v46 <= 0 )
      return 5121;
    v28 = v45 + 1;
    v19 = 0xFFFFFFFFLL;
    if ( (unsigned __int64)(v45 + 2147483649LL) > 0xFFFFFFFF )
      goto LABEL_5;
    i = (unsigned int)(i + 1);
  }
  if ( v28 <= 0 )
    return 5121;
  i = *((unsigned __int16 *)a6 + 3);
  if ( v28 > (int)i )
    return 5121;
  v22 = *a14 + (__int64)v28;
  if ( v22 > 0xFFFFFFFF )
  {
LABEL_5:
    SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v19, i);
    __debugbreak();
  }
  v23 = (unsigned __int16)i < *((_WORD *)a6 + 5);
  *a14 = v22;
  if ( v23 )
    LOWORD(i) = *((_WORD *)a6 + 5);
  if ( (unsigned int)v22 > (unsigned __int16)i )
    return 5121;
  if ( !a7 )
    return 0;
  v24 = 0;
  v25 = v18;
  while ( v28 > 0 )
  {
    if ( v24 )
    {
      v28 -= v24;
      if ( v28 < 0 )
        return 5133;
      memset_0(v25, *(v25 - 1), v24);
      do
      {
        ++v25;
        --v24;
      }
      while ( v24 );
    }
    else
    {
      v26 = v15 + 1;
      if ( (unsigned __int64)(v15 + 1) > v41 )
        return 5133;
      v27 = *v15;
      *v25 = *v15;
      if ( (v27 & 8) != 0 )
      {
        ++v15;
        if ( (unsigned __int64)(v26 + 1) > v41 )
          return 5133;
        v24 = *v26;
      }
      ++v15;
      ++v25;
      --v28;
    }
  }
  if ( v24 )
    return 5121;
  v29 = v47;
  i = 0;
  v30 = 0;
  v31 = v18;
  while ( v30 < *a1 )
  {
    v32 = *v31;
    if ( (*v31 & 2) != 0 )
    {
      v33 = v15 + 1;
      if ( (unsigned __int64)(v15 + 1) > v41 )
        return 5133;
      v34 = *v15;
      if ( (v32 & 0x10) != 0 )
        v19 = (unsigned int)(v34 + (__int16)i);
      else
        v19 = (unsigned int)((__int16)i - v34);
      if ( (unsigned int)(v19 + 0x8000) > 0xFFFF )
        goto LABEL_5;
      v29 = v47;
      i = (unsigned __int16)v19;
LABEL_33:
      v15 = v33;
      goto LABEL_34;
    }
    if ( (v32 & 0x10) == 0 )
    {
      v33 = v15 + 2;
      if ( (unsigned __int64)(v15 + 2) > v41 )
        return 5133;
      v19 = v15[1] | (unsigned int)(__int16)(*v15 << 8);
      i = (unsigned int)(v19 + (__int16)i);
      if ( (unsigned int)(i + 0x8000) > 0xFFFF )
        goto LABEL_5;
      goto LABEL_33;
    }
LABEL_34:
    ++v31;
    *v29++ = (__int16)i;
    v47 = v29;
    ++v30;
  }
  LOWORD(v35) = 0;
  for ( i = 0; (int)i < *a1; i = (unsigned int)(i + 1) )
  {
    v36 = *v18;
    if ( (*v18 & 4) != 0 )
    {
      v19 = (__int64)(v15 + 1);
      if ( (unsigned __int64)(v15 + 1) > v41 )
        return 5133;
      v37 = *v15;
      if ( (v36 & 0x20) != 0 )
        v35 = v37 + (__int16)v35;
      else
        v35 = (__int16)v35 - v37;
      if ( (unsigned int)(v35 + 0x8000) > 0xFFFF )
        goto LABEL_5;
      ++v15;
    }
    else if ( (v36 & 0x20) == 0 )
    {
      if ( (unsigned __int64)(v15 + 2) > v41 )
        return 5133;
      v19 = v15[1] | (unsigned int)(__int16)(*v15 << 8);
      v35 = v19 + (__int16)v35;
      if ( (unsigned int)(v35 + 0x8000) > 0xFFFF )
        goto LABEL_5;
      v15 += 2;
    }
    *v17++ = (__int16)v35;
    *v18++ &= 1u;
  }
  if ( (unsigned __int64)v15 <= v41 )
  {
    *((_QWORD *)a5 + 3) = v15;
    return 0;
  }
  return 5133;
}

```

## disassembly

```asm
0x14001ba10  mov     [rsp+arg_18], r9
0x14001ba15  push    rbx
0x14001ba16  push    rbp
0x14001ba17  push    rsi
0x14001ba18  push    rdi
0x14001ba19  push    r12
0x14001ba1b  push    r13
0x14001ba1d  push    r14
0x14001ba1f  push    r15
0x14001ba21  sub     rsp, 28h
0x14001ba25  mov     r11, [rsp+68h+arg_50]
0x14001ba2d  xor     ebx, ebx
0x14001ba2f  mov     r13, rcx
0x14001ba32  mov     rcx, [rsp+68h+arg_48]
0x14001ba3a  mov     r15, r8
0x14001ba3d  mov     r14, [rsp+68h+arg_60]
0x14001ba45  mov     rdi, rdx
0x14001ba48  mov     rsi, [rsp+68h+arg_58]
0x14001ba50  mov     [rcx], bx
0x14001ba53  mov     [r11], bx
0x14001ba57  mov     byte ptr [rdx], 1
0x14001ba5a  mov     [r9], ebx
0x14001ba5d  mov     [r8], ebx
0x14001ba60  mov     [r14], rbx
0x14001ba63  mov     [rsi], bx
0x14001ba66  mov     [r13+0], ebx
0x14001ba6a  cmp     [rsp+68h+arg_30], bl
0x14001ba71  jz      short loc_14001BABE
0x14001ba73  movsx   r8, [rsp+68h+arg_40]
0x14001ba7c  test    r8w, r8w
0x14001ba80  jle     loc_14001BEE0
0x14001ba86  mov     rbp, [rsp+68h+arg_28]
0x14001ba8e  movzx   ecx, word ptr [rbp+8]
0x14001ba92  cmp     r8w, cx
0x14001ba96  ja      loc_14001BEE0
0x14001ba9c  mov     r10, [rsp+68h+arg_70]
0x14001baa4  mov     eax, 0FFFFFFFFh
0x14001baa9  mov     edx, [r10]
0x14001baac  add     rdx, r8
0x14001baaf  cmp     rdx, rax
0x14001bab2  jbe     loc_14001BE7D
0x14001bab8  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@SAXXZ; SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(void)
0x14001babd  int     3; Trap to Debugger
0x14001babe  cmp     [rsp+68h+arg_38], bl
0x14001bac5  jz      short loc_14001BADE
0x14001bac7  jmp     short loc_14001BA73
0x14001bac9  cmp     rbx, r12
0x14001bacc  ja      loc_14001BD18
0x14001bad2  mov     rax, [rsp+68h+arg_20]
0x14001bada  mov     [rax+18h], rbx
0x14001bade  xor     eax, eax
0x14001bae0  add     rsp, 28h
0x14001bae4  pop     r15
0x14001bae6  pop     r14
0x14001bae8  pop     r13
0x14001baea  pop     r12
0x14001baec  pop     rdi
0x14001baed  pop     rsi
0x14001baee  pop     rbp
0x14001baef  pop     rbx
0x14001baf0  retn
0x14001baf1  test    esi, esi
0x14001baf3  jle     loc_14001BD22
0x14001baf9  movzx   edx, word ptr [rbp+6]
0x14001bafd  cmp     esi, edx
0x14001baff  jg      loc_14001BD22
0x14001bb05  mov     r9, [rsp+68h+arg_68]
0x14001bb0d  movsxd  r8, esi
0x14001bb10  mov     eax, [r9]
0x14001bb13  add     r8, rax
0x14001bb16  mov     eax, 0FFFFFFFFh
0x14001bb1b  cmp     r8, rax
0x14001bb1e  ja      short loc_14001BAB8
0x14001bb20  cmp     dx, [rbp+0Ah]
0x14001bb24  mov     [r9], r8d
0x14001bb27  cmovb   dx, [rbp+0Ah]
0x14001bb2c  movzx   eax, dx
0x14001bb2f  cmp     r8d, eax
0x14001bb32  ja      loc_14001BD22
0x14001bb38  cmp     [rsp+68h+arg_30], 0
0x14001bb40  jz      short loc_14001BADE
0x14001bb42  xor     ebp, ebp
0x14001bb44  mov     r14, rdi
0x14001bb47  test    esi, esi
0x14001bb49  jle     short loc_14001BB79
0x14001bb4b  test    bp, bp
0x14001bb4e  jnz     loc_14001BCDA
0x14001bb54  lea     rcx, [rbx+1]
0x14001bb58  cmp     rcx, r12
0x14001bb5b  ja      loc_14001BD18
0x14001bb61  movzx   eax, byte ptr [rbx]
0x14001bb64  mov     [r14], al
0x14001bb67  test    al, 8
0x14001bb69  jnz     loc_14001BD04
0x14001bb6f  inc     rbx
0x14001bb72  inc     r14
0x14001bb75  dec     esi
0x14001bb77  jmp     short loc_14001BB47
0x14001bb79  test    bp, bp
0x14001bb7c  jnz     loc_14001BD22
0x14001bb82  mov     r11, [rsp+68h+arg_18]
0x14001bb8a  xor     edx, edx
0x14001bb8c  xor     r9d, r9d
0x14001bb8f  mov     r10, rdi
0x14001bb92  cmp     r9d, [r13+0]
0x14001bb96  jge     loc_14001BC35
0x14001bb9c  movzx   eax, byte ptr [r10]
0x14001bba0  test    al, 2
0x14001bba2  jz      short loc_14001BBF8
0x14001bba4  lea     r8, [rbx+1]
0x14001bba8  cmp     r8, r12
0x14001bbab  ja      loc_14001BD18
0x14001bbb1  movzx   r11d, byte ptr [rbx]
0x14001bbb5  movsx   ecx, dx
0x14001bbb8  test    al, 10h
0x14001bbba  jz      short loc_14001BC30
0x14001bbbc  add     ecx, r11d
0x14001bbbf  lea     eax, [rcx+8000h]
0x14001bbc5  cmp     eax, 0FFFFh
0x14001bbca  ja      loc_14001BAB8
0x14001bbd0  mov     r11, [rsp+68h+arg_18]
0x14001bbd8  movzx   edx, cx
0x14001bbdb  mov     rbx, r8
0x14001bbde  movsx   eax, dx
0x14001bbe1  inc     r10
0x14001bbe4  mov     [r11], eax
0x14001bbe7  add     r11, 4
0x14001bbeb  mov     [rsp+68h+arg_18], r11
0x14001bbf3  inc     r9d
0x14001bbf6  jmp     short loc_14001BB92
0x14001bbf8  test    al, 10h
0x14001bbfa  jnz     short loc_14001BBDE
0x14001bbfc  lea     r8, [rbx+2]
0x14001bc00  cmp     r8, r12
0x14001bc03  ja      loc_14001BD18
0x14001bc09  movzx   eax, byte ptr [rbx]
0x14001bc0c  shl     ax, 8
0x14001bc10  movsx   ecx, ax
0x14001bc13  movzx   eax, byte ptr [rbx+1]
0x14001bc17  or      ecx, eax
0x14001bc19  movsx   edx, dx
0x14001bc1c  add     edx, ecx
0x14001bc1e  lea     eax, [rdx+8000h]
0x14001bc24  cmp     eax, 0FFFFh
0x14001bc29  jbe     short loc_14001BBDB
0x14001bc2b  jmp     loc_14001BAB8
0x14001bc30  sub     ecx, r11d
0x14001bc33  jmp     short loc_14001BBBF
0x14001bc35  xor     r8d, r8d
0x14001bc38  xor     edx, edx
0x14001bc3a  nop     word ptr [rax+rax+00h]
0x14001bc40  cmp     edx, [r13+0]
0x14001bc44  jge     loc_14001BAC9
0x14001bc4a  movzx   eax, byte ptr [rdi]
0x14001bc4d  test    al, 4
0x14001bc4f  jnz     short loc_14001BC90
0x14001bc51  test    al, 20h
0x14001bc53  jnz     short loc_14001BCBD
0x14001bc55  lea     r9, [rbx+2]
0x14001bc59  cmp     r9, r12
0x14001bc5c  ja      loc_14001BD18
0x14001bc62  movzx   eax, byte ptr [rbx]
0x14001bc65  shl     ax, 8
0x14001bc69  movsx   ecx, ax
0x14001bc6c  movzx   eax, byte ptr [rbx+1]
0x14001bc70  or      ecx, eax
0x14001bc72  movsx   r8d, r8w
0x14001bc76  add     r8d, ecx
0x14001bc79  lea     eax, [r8+8000h]
0x14001bc80  cmp     eax, 0FFFFh
0x14001bc85  ja      loc_14001BAB8
0x14001bc8b  mov     rbx, r9
0x14001bc8e  jmp     short loc_14001BCBD
0x14001bc90  lea     rcx, [rbx+1]
0x14001bc94  cmp     rcx, r12
0x14001bc97  ja      short loc_14001BD18
0x14001bc99  movzx   r9d, byte ptr [rbx]
0x14001bc9d  movsx   r8d, r8w
0x14001bca1  test    al, 20h
0x14001bca3  jnz     short loc_14001BCD5
0x14001bca5  sub     r8d, r9d
0x14001bca8  lea     eax, [r8+8000h]
0x14001bcaf  cmp     eax, 0FFFFh
0x14001bcb4  ja      loc_14001BAB8
0x14001bcba  mov     rbx, rcx
0x14001bcbd  movsx   eax, r8w
0x14001bcc1  mov     [r15], eax
0x14001bcc4  add     r15, 4
0x14001bcc8  and     byte ptr [rdi], 1
0x14001bccb  inc     rdi
0x14001bcce  inc     edx
0x14001bcd0  jmp     loc_14001BC40
0x14001bcd5  add     r8d, r9d
0x14001bcd8  jmp     short loc_14001BCA8
0x14001bcda  movzx   eax, bp
0x14001bcdd  sub     esi, eax
0x14001bcdf  js      short loc_14001BD18
0x14001bce1  movzx   edx, byte ptr [r14-1]; Val
0x14001bce6  mov     rcx, r14; void *
0x14001bce9  movzx   r8d, bp; Size
0x14001bced  call    memset_0
0x14001bcf2  mov     eax, 0FFFFh
0x14001bcf7  inc     r14
0x14001bcfa  add     bp, ax
0x14001bcfd  jnz     short loc_14001BCF7
0x14001bcff  jmp     loc_14001BB47
0x14001bd04  lea     rax, [rcx+1]
0x14001bd08  mov     rbx, rcx
0x14001bd0b  cmp     rax, r12
0x14001bd0e  ja      short loc_14001BD18
0x14001bd10  movzx   ebp, byte ptr [rcx]
0x14001bd13  jmp     loc_14001BB6F
0x14001bd18  mov     eax, 140Dh
0x14001bd1d  jmp     loc_14001BAE0
0x14001bd22  mov     eax, 1401h
0x14001bd27  jmp     loc_14001BAE0
0x14001bd2c  mov     eax, r8d
0x14001bd2f  add     rax, rax
0x14001bd32  mov     rbx, 7FFFFFFFFFFFFFFFh
0x14001bd3c  cmp     rax, rbx
0x14001bd3f  ja      loc_14001BAB8
0x14001bd45  mov     rdx, [rsp+68h+arg_20]
0x14001bd4d  mov     r10, [rdx+18h]
0x14001bd51  test    rax, rax
0x14001bd54  js      loc_14001BE66
0x14001bd5a  lea     r9, [r10+rax]
0x14001bd5e  cmp     r9, r10
0x14001bd61  jb      loc_14001BAB8
0x14001bd67  mov     ecx, [rdx]
0x14001bd69  mov     r12, [rdx+8]
0x14001bd6d  lea     rdx, [r9+2]
0x14001bd71  add     r12, rcx
0x14001bd74  cmp     rdx, r12
0x14001bd77  ja      short loc_14001BD18
0x14001bd79  movzx   eax, byte ptr [r9+1]
0x14001bd7e  movzx   ecx, byte ptr [r9]
0x14001bd82  shl     cx, 8
0x14001bd86  or      cx, ax
0x14001bd89  mov     [rsi], cx
0x14001bd8c  mov     [r14], rdx
0x14001bd8f  movzx   eax, word ptr [rsi]
0x14001bd92  cmp     rax, rbx
0x14001bd95  ja      loc_14001BAB8
0x14001bd9b  lea     rbx, [rax+rdx]
0x14001bd9f  cmp     rbx, rdx
0x14001bda2  jb      loc_14001BAB8
0x14001bda8  mov     r14, [rsp+68h+arg_48]
0x14001bdb0  xor     eax, eax
0x14001bdb2  mov     [r14], ax
0x14001bdb6  movzx   ecx, byte ptr [r10]
0x14001bdba  movzx   eax, byte ptr [r10+1]
0x14001bdbf  shl     cx, 8
0x14001bdc3  or      cx, ax
0x14001bdc6  mov     [r11], cx
0x14001bdca  movsx   esi, word ptr [r11]
0x14001bdce  mov     edx, 1
0x14001bdd3  inc     esi
0x14001bdd5  mov     r9d, r8d
0x14001bdd8  mov     [r13+0], esi
0x14001bddc  cmp     edx, r9d
0x14001bddf  jge     loc_14001BAF1
0x14001bde5  movsxd  r8, edx
0x14001bde8  movsx   rcx, word ptr [r11+r8*2-2]
0x14001bdee  inc     rcx
0x14001bdf1  lea     rax, [rcx+8000h]
0x14001bdf8  cmp     rax, 0FFFFh
0x14001bdfe  ja      loc_14001BAB8
0x14001be04  mov     [r14+r8*2], cx
0x14001be09  movzx   ecx, byte ptr [r10+r8*2]
0x14001be0e  movzx   eax, byte ptr [r10+r8*2+1]
0x14001be14  shl     cx, 8
0x14001be18  or      cx, ax
0x14001be1b  mov     [r11+r8*2], cx
0x14001be20  movsx   r8, cx
0x14001be24  mov     ecx, [r13+0]
0x14001be28  cmp     ecx, r8d
0x14001be2b  jg      loc_14001BD22
0x14001be31  movzx   eax, word ptr [rbp+6]
0x14001be35  cmp     ecx, eax
0x14001be37  jg      loc_14001BD22
0x14001be3d  test    ecx, ecx
0x14001be3f  jle     loc_14001BD22
0x14001be45  lea     rsi, [r8+1]
0x14001be49  mov     eax, 80000000h
0x14001be4e  add     rax, rsi
0x14001be51  mov     ecx, 0FFFFFFFFh
0x14001be56  cmp     rax, rcx
0x14001be59  ja      loc_14001BAB8
0x14001be5f  inc     edx
0x14001be61  jmp     loc_14001BDD8
0x14001be66  neg     rax
0x14001be69  cmp     rax, r10
0x14001be6c  ja      loc_14001BAB8
0x14001be72  mov     r9, r10
0x14001be75  sub     r9, rax
0x14001be78  jmp     loc_14001BD67
0x14001be7d  cmp     cx, [rbp+0Ch]
0x14001be81  mov     [r10], edx
0x14001be84  cmovb   cx, [rbp+0Ch]
0x14001be89  movzx   eax, cx
  ... truncated ...
```

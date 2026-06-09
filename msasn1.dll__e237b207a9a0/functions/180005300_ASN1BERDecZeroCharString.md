# ASN1BERDecZeroCharString

- ea: `0x180005300`
- end: `0x180005795`
- name: `ASN1BERDecZeroCharString`
- size: `1173`
- prototype: `__int64 __fastcall(_DWORD *, int, LPCSTR *)`
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x1800051a0`
- `0x180005250`
- `0x180005300`
- `0x18000a060`

## callees

- `0x180001b30`
- `0x180001f50`
- `0x1800020a0`
- `0x180002200`
- `0x180004310`
- `0x180004760`
- `0x180005300`
- `0x1800062ec`
- `0x18000aac5`
- `0x18000aadd`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005416`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005416`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000560c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005633`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005648`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000565c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000560c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005633`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005648`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000565c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800056e4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800056f6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800056e4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800056f6`

## pseudocode

```c
__int64 __fastcall ASN1BERDecZeroCharString(_DWORD *a1, int a2, LPCSTR *a3)
{
  _DWORD *v5; // rbx
  unsigned __int8 *v6; // rax
  int v7; // ebp
  unsigned __int8 *v8; // r8
  char v9; // di
  int v10; // edi
  _DWORD *v11; // rax
  int v13; // ecx
  int v14; // edx
  unsigned int v15; // esi
  unsigned __int8 *v16; // r8
  int v17; // edi
  int v18; // eax
  CHAR *v19; // rbp
  unsigned int v20; // ecx
  __int64 v21; // rdx
  CHAR *v22; // rdi
  unsigned int v23; // r9d
  unsigned int v24; // r9d
  unsigned int v25; // r9d
  __int64 v26; // rdx
  unsigned int i; // r15d
  _BYTE *v28; // rax
  char v29; // cl
  unsigned int v30; // edx
  void *v31; // rcx
  __int64 v32; // rdi
  __int64 v33; // r15
  unsigned int v34; // esi
  int v35; // ebp
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38[7]; // [rsp+30h] [rbp-38h] BYREF
  void *Src; // [rsp+70h] [rbp+8h] BYREF
  __int64 v40; // [rsp+88h] [rbp+20h] BYREF

  Src = 0;
  v40 = 0;
  v5 = a1;
  v38[0] = 0;
  if ( !(a1[6] + a1[4] - a1[10]) )
    goto LABEL_34;
  v6 = (unsigned __int8 *)*((_QWORD *)a1 + 5);
  v7 = *v6;
  v8 = v6 + 1;
  v9 = *v6;
  *((_QWORD *)a1 + 5) = v6 + 1;
  v10 = v9 & 0x1F;
  if ( v10 == 31 )
  {
    v10 = 0;
    for ( i = 0; i < 4; ++i )
    {
      if ( !(unsigned int)ASN1BERDecCheck(v5, 1) )
        return 0;
      v28 = (_BYTE *)*((_QWORD *)v5 + 5);
      v29 = *v28;
      v8 = v28 + 1;
      *((_QWORD *)v5 + 5) = v28 + 1;
      if ( (v10 & 0xE0000000) != 0 )
        break;
      v10 = (v10 << 7) | v29 & 0x7F;
      if ( v29 >= 0 )
        goto LABEL_3;
    }
    ASN1DecSetError(v5, 4294966285LL);
    return 0;
  }
LABEL_3:
  if ( a2 != (v10 | ((v7 & 0xFFFFFFC0) << 24)) )
  {
    do
    {
      v11 = (_DWORD *)*((_QWORD *)v5 + 7);
      v5[8] = -1011;
      if ( v5 == v11 )
        break;
      v5 = v11;
    }
    while ( v11 );
    return 0;
  }
  v13 = v5[4];
  v14 = v5[6];
  if ( !(v14 + v13 - (_DWORD)v8) )
    goto LABEL_34;
  v15 = *v8;
  v16 = v8 + 1;
  *((_QWORD *)v5 + 5) = v16;
  if ( v15 < 0x80 )
    goto LABEL_9;
  if ( v15 == 128 )
  {
    v15 = 0;
    v17 = 1;
    goto LABEL_12;
  }
  if ( v15 > 0x84 )
  {
    v26 = 4294966293LL;
    goto LABEL_35;
  }
  v23 = v15 - 128;
  if ( v15 - 128 > v14 + v13 - (int)v16 )
  {
LABEL_34:
    v26 = 4294966294LL;
LABEL_35:
    ASN1DecSetError(v5, v26);
    return 0;
  }
  v15 = 0;
  if ( v23 == 2 )
  {
LABEL_28:
    v15 |= *v16++ << 8;
    *((_QWORD *)v5 + 5) = v16;
LABEL_29:
    v15 |= *v16;
    *((_QWORD *)v5 + 5) = v16 + 1;
    LODWORD(v16) = (_DWORD)v16 + 1;
    goto LABEL_9;
  }
  v24 = v23 - 1;
  if ( !v24 )
    goto LABEL_29;
  v25 = v24 - 2;
  if ( !v25 )
  {
LABEL_33:
    v15 |= *v16++ << 16;
    *((_QWORD *)v5 + 5) = v16;
    goto LABEL_28;
  }
  if ( v25 == 1 )
  {
    v15 = *v16++ << 24;
    *((_QWORD *)v5 + 5) = v16;
    goto LABEL_33;
  }
LABEL_9:
  v17 = 0;
  if ( v15 > v14 + v13 - (int)v16 )
  {
    ASN1DecSetError(v5, 4294966294LL);
    v18 = 0;
  }
  else
  {
    v18 = 1;
  }
  if ( !v18 )
    return 0;
LABEL_12:
  if ( (v7 & 0x20) != 0 )
  {
    *a3 = 0;
    if ( !(unsigned int)BERDecConstructed((_DWORD)v5, v15, v17, (unsigned int)&v40, (__int64)v38) )
      return 0;
    v32 = v40;
    v33 = v38[0];
    while ( 1 )
    {
      while ( 1 )
      {
        do
        {
          if ( !(unsigned int)ASN1BERDecNotEndOfContents(v32, v33) )
          {
            if ( *a3 )
              return ASN1BERDecEndOfContents(v5, v32, v33);
            v37 = DecMemAlloc(v32, 1);
            *a3 = (LPCSTR)v37;
            if ( v37 )
              return ASN1BERDecEndOfContents(v5, v32, v33);
            return 0;
          }
          if ( !(unsigned int)ASN1BERDecZeroCharString(v32, 4, &Src) )
          {
            if ( Src && !v5[19] )
            {
LABEL_55:
              LocalFree(Src);
              return 0;
            }
            return 0;
          }
          if ( *a3 )
            v34 = lstrlenA(*a3);
          else
            v34 = 0;
        }
        while ( !Src );
        v35 = lstrlenA((LPCSTR)Src);
        if ( !v35 )
          break;
        v36 = DecMemReAlloc(v32, *a3);
        *a3 = (LPCSTR)v36;
        if ( !v36 )
        {
          if ( v5[19] )
            return 0;
          goto LABEL_55;
        }
        memcpy_0((void *)(v36 + v34), Src, (unsigned int)(v35 + 1));
        if ( !v5[19] )
        {
          v31 = Src;
LABEL_50:
          LocalFree(v31);
        }
LABEL_51:
        Src = 0;
      }
      v31 = Src;
      if ( Src )
      {
        if ( !v5[19] )
          goto LABEL_50;
        goto LABEL_51;
      }
    }
  }
  v19 = 0;
  v20 = (v15 + 4) & 0xFFFFFFFC;
  if ( v15 + 1 > v20 )
    goto LABEL_37;
  if ( v5[19] )
  {
    v30 = v5[26];
    if ( v30 < v20 )
      goto LABEL_37;
    v19 = (CHAR *)*((_QWORD *)v5 + 12);
    *((_QWORD *)v5 + 12) = &v19[v20];
    v5[26] = v30 - v20;
  }
  else
  {
    v19 = (CHAR *)LocalAlloc(0x40u, v20);
  }
  if ( !v19 )
LABEL_37:
    ASN1DecSetError(v5, 4294966290LL);
  *a3 = v19;
  if ( !v19 )
    return 0;
  memcpy_0(v19, *((const void **)v5 + 5), v15);
  (*a3)[v15] = 0;
  *((_QWORD *)v5 + 5) += v15;
  if ( (g_dwDecodingRules & 2) == 0 )
  {
    if ( v15 )
    {
      do
      {
        v21 = v15 - 1;
        if ( (*a3)[v21] )
          break;
        --v15;
      }
      while ( (_DWORD)v21 );
    }
    if ( v15 > 1 )
    {
      v22 = (CHAR *)*a3;
      if ( memchr_0(*a3, 0, v15 - 1) )
      {
        if ( !v5[19] )
          LocalFree(v22);
        *a3 = 0;
        ASN1DecSetError(v5, 4294966283LL);
        return 0;
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180005300  mov     rax, rsp
0x180005303  mov     [rax+10h], rbx
0x180005307  mov     [rax+18h], rbp
0x18000530b  push    rsi
0x18000530c  push    rdi
0x18000530d  push    r12
0x18000530f  push    r14
0x180005311  push    r15
0x180005313  sub     rsp, 40h
0x180005317  xor     r12d, r12d
0x18000531a  mov     r14, r8
0x18000531d  mov     [rax+8], r12
0x180005321  mov     esi, edx
0x180005323  mov     [rax+20h], r12
0x180005327  mov     rbx, rcx
0x18000532a  mov     [rax-38h], r12
0x18000532e  mov     eax, [rcx+10h]
0x180005331  sub     eax, [rcx+28h]
0x180005334  add     eax, [rcx+18h]
0x180005337  cmp     eax, 1
0x18000533a  jb      loc_180005513
0x180005340  mov     rax, [rcx+28h]
0x180005344  movzx   ebp, byte ptr [rax]
0x180005347  lea     r8, [rax+1]
0x18000534b  mov     edi, ebp
0x18000534d  mov     [rcx+28h], r8
0x180005351  and     edi, 1Fh
0x180005354  cmp     edi, 1Fh
0x180005357  jz      loc_18000554C
0x18000535d  mov     eax, ebp
0x18000535f  mov     r9d, r8d
0x180005362  and     eax, 0FFFFFFC0h
0x180005365  shl     eax, 18h
0x180005368  or      eax, edi
0x18000536a  cmp     esi, eax
0x18000536c  jz      short loc_1800053A2
0x18000536e  mov     rax, [rbx+38h]
0x180005372  mov     dword ptr [rbx+20h], 0FFFFFC0Dh
0x180005379  cmp     rbx, rax
0x18000537c  jz      short loc_180005386
0x18000537e  mov     rbx, rax
0x180005381  test    rax, rax
0x180005384  jnz     short loc_18000536E
0x180005386  xor     eax, eax
0x180005388  mov     rbx, [rsp+68h+arg_8]
0x18000538d  mov     rbp, [rsp+68h+arg_10]
0x180005395  add     rsp, 40h
0x180005399  pop     r15
0x18000539b  pop     r14
0x18000539d  pop     r12
0x18000539f  pop     rdi
0x1800053a0  pop     rsi
0x1800053a1  retn
0x1800053a2  mov     ecx, [rbx+10h]
0x1800053a5  mov     eax, ecx
0x1800053a7  mov     edx, [rbx+18h]
0x1800053aa  sub     eax, r9d
0x1800053ad  add     eax, edx
0x1800053af  cmp     eax, 1
0x1800053b2  jb      loc_180005513
0x1800053b8  movzx   esi, byte ptr [r8]
0x1800053bc  inc     r8
0x1800053bf  mov     [rbx+28h], r8
0x1800053c3  cmp     esi, 80h
0x1800053c9  jnb     loc_180005497
0x1800053cf  sub     ecx, r8d
0x1800053d2  mov     edi, r12d
0x1800053d5  add     ecx, edx
0x1800053d7  cmp     esi, ecx
0x1800053d9  ja      loc_180005525
0x1800053df  mov     eax, 1
0x1800053e4  test    eax, eax
0x1800053e6  jz      short loc_180005386
0x1800053e8  test    bpl, 20h
0x1800053ec  jnz     loc_180005677
0x1800053f2  lea     eax, [rsi+1]
0x1800053f5  mov     rbp, r12
0x1800053f8  lea     ecx, [rax+3]
0x1800053fb  and     ecx, 0FFFFFFFCh
0x1800053fe  cmp     eax, ecx
0x180005400  ja      loc_18000553A
0x180005406  cmp     [rbx+4Ch], ebp
0x180005409  jnz     loc_1800055CC
0x18000540f  mov     edx, ecx; uBytes
0x180005411  mov     ecx, 40h ; '@'; uFlags
0x180005416  call    cs:__imp_LocalAlloc
0x18000541c  mov     rbp, rax
0x18000541f  test    rbp, rbp
0x180005422  jz      loc_18000553A
0x180005428  mov     [r14], rbp
0x18000542b  test    rbp, rbp
0x18000542e  jz      loc_180005386
0x180005434  mov     rdx, [rbx+28h]; Src
0x180005438  mov     rcx, rbp; void *
0x18000543b  mov     r8d, esi; Size
0x18000543e  mov     edi, esi
0x180005440  call    memcpy_0
0x180005445  mov     rax, [r14]
0x180005448  mov     [rdi+rax], r12b
0x18000544c  add     [rbx+28h], rdi
0x180005450  mov     eax, cs:g_dwDecodingRules
0x180005456  test    al, 2
0x180005458  jnz     short loc_18000548D
0x18000545a  test    esi, esi
0x18000545c  jz      short loc_18000546E
0x18000545e  mov     rcx, [r14]
0x180005461  lea     edx, [rsi-1]
0x180005464  cmp     [rdx+rcx], r12b
0x180005468  jz      loc_18000577C
0x18000546e  cmp     esi, 1
0x180005471  jbe     short loc_18000548D
0x180005473  mov     rdi, [r14]
0x180005476  lea     r8d, [rsi-1]; MaxCount
0x18000547a  mov     rcx, rdi; Buf
0x18000547d  xor     edx, edx; Val
0x18000547f  call    memchr_0
0x180005484  test    rax, rax
0x180005487  jnz     loc_180005653
0x18000548d  mov     eax, 1
0x180005492  jmp     loc_180005388
0x180005497  jz      short loc_1800054E4
0x180005499  cmp     esi, 84h
0x18000549f  ja      loc_18000578B
0x1800054a5  mov     eax, ecx
0x1800054a7  lea     r9d, [rsi-80h]
0x1800054ab  sub     eax, r8d
0x1800054ae  add     eax, edx
0x1800054b0  cmp     r9d, eax
0x1800054b3  ja      short loc_180005513
0x1800054b5  mov     esi, r12d
0x1800054b8  cmp     r9d, 2
0x1800054bc  jnz     short loc_1800054F1
0x1800054be  movzx   eax, byte ptr [r8]
0x1800054c2  shl     eax, 8
0x1800054c5  or      esi, eax
0x1800054c7  inc     r8
0x1800054ca  mov     [rbx+28h], r8
0x1800054ce  movzx   eax, byte ptr [r8]
0x1800054d2  or      esi, eax
0x1800054d4  lea     rax, [r8+1]
0x1800054d8  mov     [rbx+28h], rax
0x1800054dc  mov     r8d, eax
0x1800054df  jmp     loc_1800053CF
0x1800054e4  mov     esi, r12d
0x1800054e7  mov     edi, 1
0x1800054ec  jmp     loc_1800053E8
0x1800054f1  sub     r9d, 1
0x1800054f5  jz      short loc_1800054CE
0x1800054f7  sub     r9d, 2
0x1800054fb  jnz     loc_1800055AF
0x180005501  movzx   eax, byte ptr [r8]
0x180005505  shl     eax, 10h
0x180005508  or      esi, eax
0x18000550a  inc     r8
0x18000550d  mov     [rbx+28h], r8
0x180005511  jmp     short loc_1800054BE
0x180005513  mov     edx, 0FFFFFC16h
0x180005518  mov     rcx, rbx
0x18000551b  call    ASN1DecSetError
0x180005520  jmp     loc_180005386
0x180005525  mov     edx, 0FFFFFC16h
0x18000552a  mov     rcx, rbx
0x18000552d  call    ASN1DecSetError
0x180005532  mov     eax, r12d
0x180005535  jmp     loc_1800053E4
0x18000553a  mov     edx, 0FFFFFC12h
0x18000553f  mov     rcx, rbx
0x180005542  call    ASN1DecSetError
0x180005547  jmp     loc_180005428
0x18000554c  mov     edi, r12d
0x18000554f  mov     r15d, r12d
0x180005552  mov     edx, 1
0x180005557  mov     rcx, rbx
0x18000555a  call    ASN1BERDecCheck
0x18000555f  test    eax, eax
0x180005561  jz      loc_180005386
0x180005567  mov     rax, [rbx+28h]
0x18000556b  movzx   ecx, byte ptr [rax]
0x18000556e  lea     r8, [rax+1]
0x180005572  mov     [rbx+28h], r8
0x180005576  test    edi, 0E0000000h
0x18000557c  jnz     short loc_18000559D
0x18000557e  mov     eax, edi
0x180005580  mov     edx, ecx
0x180005582  and     ecx, 7Fh
0x180005585  shl     eax, 7
0x180005588  mov     edi, ecx
0x18000558a  or      edi, eax
0x18000558c  test    dl, dl
0x18000558e  jns     loc_18000535D
0x180005594  inc     r15d
0x180005597  cmp     r15d, 4
0x18000559b  jb      short loc_180005552
0x18000559d  mov     edx, 0FFFFFC0Dh
0x1800055a2  mov     rcx, rbx
0x1800055a5  call    ASN1DecSetError
0x1800055aa  jmp     loc_180005386
0x1800055af  cmp     r9d, 1
0x1800055b3  jnz     loc_1800053CF
0x1800055b9  movzx   esi, byte ptr [r8]
0x1800055bd  shl     esi, 18h
0x1800055c0  inc     r8
0x1800055c3  mov     [rbx+28h], r8
0x1800055c7  jmp     loc_180005501
0x1800055cc  mov     edx, [rbx+68h]
0x1800055cf  cmp     edx, ecx
0x1800055d1  jb      loc_18000553A
0x1800055d7  mov     rbp, [rbx+60h]
0x1800055db  mov     eax, ecx
0x1800055dd  add     rax, rbp
0x1800055e0  sub     edx, ecx
0x1800055e2  mov     [rbx+60h], rax
0x1800055e6  mov     [rbx+68h], edx
0x1800055e9  jmp     loc_18000541F
0x1800055ee  mov     rdx, [rsp+68h+Src]; Src
0x1800055f3  lea     r8d, [rbp+1]; Size
0x1800055f7  mov     ecx, esi
0x1800055f9  add     rcx, rax; void *
0x1800055fc  call    memcpy_0
0x180005601  cmp     [rbx+4Ch], r12d
0x180005605  jnz     short loc_180005612
0x180005607  mov     rcx, [rsp+68h+Src]; hMem
0x18000560c  call    cs:__imp_LocalFree
0x180005612  mov     [rsp+68h+Src], r12
0x180005617  jmp     loc_1800056AE
0x18000561c  cmp     [rbx+4Ch], r12d
0x180005620  jz      short loc_18000560C
0x180005622  jmp     short loc_180005612
0x180005624  cmp     [rbx+4Ch], r12d
0x180005628  jnz     loc_180005386
0x18000562e  mov     rcx, [rsp+68h+Src]; hMem
0x180005633  call    cs:__imp_LocalFree
0x180005639  jmp     loc_180005386
0x18000563e  cmp     [rbx+4Ch], r12d
0x180005642  jnz     loc_180005386
0x180005648  call    cs:__imp_LocalFree
0x18000564e  jmp     loc_180005386
0x180005653  cmp     [rbx+4Ch], r12d
0x180005657  jnz     short loc_180005662
0x180005659  mov     rcx, rdi; hMem
0x18000565c  call    cs:__imp_LocalFree
0x180005662  mov     edx, 0FFFFFC0Bh
0x180005667  mov     [r14], r12
0x18000566a  mov     rcx, rbx
0x18000566d  call    ASN1DecSetError
0x180005672  jmp     loc_180005386
0x180005677  lea     rax, [rsp+68h+var_38]
0x18000567c  mov     [r14], r12
0x18000567f  lea     r9, [rsp+68h+arg_18]
0x180005687  mov     [rsp+68h+var_48], rax
0x18000568c  mov     r8d, edi
0x18000568f  mov     edx, esi
0x180005691  mov     rcx, rbx
0x180005694  call    _BERDecConstructed
0x180005699  test    eax, eax
0x18000569b  jz      loc_180005386
0x1800056a1  mov     rdi, [rsp+68h+arg_18]
0x1800056a9  mov     r15, [rsp+68h+var_38]
0x1800056ae  mov     rdx, r15
0x1800056b1  mov     rcx, rdi
0x1800056b4  call    ASN1BERDecNotEndOfContents
0x1800056b9  test    eax, eax
0x1800056bb  jz      loc_18000574B
0x1800056c1  lea     r8, [rsp+68h+Src]
0x1800056c6  mov     edx, 4
0x1800056cb  mov     rcx, rdi
0x1800056ce  call    ASN1BERDecZeroCharString
0x1800056d3  test    eax, eax
0x1800056d5  jz      short loc_180005738
0x1800056d7  mov     rcx, [r14]; lpString
0x1800056da  test    rcx, rcx
0x1800056dd  jnz     short loc_1800056E4
0x1800056df  mov     esi, r12d
0x1800056e2  jmp     short loc_1800056EC
0x1800056e4  call    cs:__imp_lstrlenA
0x1800056ea  mov     esi, eax
0x1800056ec  mov     rcx, [rsp+68h+Src]; lpString
0x1800056f1  test    rcx, rcx
0x1800056f4  jz      short loc_1800056AE
0x1800056f6  call    cs:__imp_lstrlenA
0x1800056fc  mov     ebp, eax
0x1800056fe  test    eax, eax
0x180005700  jz      short loc_180005725
0x180005702  mov     rdx, [r14]
0x180005705  lea     r8d, [rax+1]
0x180005709  add     r8d, esi
0x18000570c  mov     rcx, rdi
0x18000570f  call    DecMemReAlloc
0x180005714  mov     [r14], rax
0x180005717  test    rax, rax
0x18000571a  jz      loc_180005624
0x180005720  jmp     loc_1800055EE
0x180005725  mov     rcx, [rsp+68h+Src]
0x18000572a  test    rcx, rcx
0x18000572d  jz      loc_1800056AE
0x180005733  jmp     loc_18000561C
0x180005738  mov     rcx, [rsp+68h+Src]; hMem
0x18000573d  test    rcx, rcx
0x180005740  jz      loc_180005386
0x180005746  jmp     loc_18000563E
  ... truncated ...
```

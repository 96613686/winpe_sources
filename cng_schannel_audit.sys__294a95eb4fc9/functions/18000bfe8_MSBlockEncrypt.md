# MSBlockEncrypt

- ea: `0x18000bfe8`
- end: `0x18000c797`
- name: `MSBlockEncrypt`
- size: `1967`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000abf0`

## callees

- `0x18000743c`
- `0x18000bfe8`
- `0x18000ca20`
- `0x1800404e8`
- `0x18009d820`
- `0x18009d860`
- `0x18009da40`

## string_xrefs

- `0x18000c0b1`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`
- `0x18000c165`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`
- `0x18000c278`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`
- `0x18000c753`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`

## pseudocode

```c
__int64 __fastcall MSBlockEncrypt(
        _DWORD *a1,
        __int64 a2,
        void *a3,
        unsigned int a4,
        unsigned __int64 a5,
        unsigned int a6,
        unsigned __int64 a7,
        unsigned int a8,
        int *a9,
        int a10,
        char a11)
{
  unsigned int v11; // r10d
  size_t v13; // rsi
  __int64 v14; // r14
  unsigned __int64 v15; // r11
  unsigned __int64 v17; // r9
  bool v18; // cf
  bool v19; // zf
  BOOL v20; // ecx
  unsigned int v21; // ebx
  unsigned int v22; // r12d
  int v23; // edx
  __int64 v24; // r9
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // r9
  __int64 v28; // rcx
  volatile signed __int64 *v30; // r12
  _DWORD *v31; // r10
  __int64 v32; // rax
  __int64 v33; // rdi
  __int64 v34; // r9
  __int64 v35; // rcx
  int v36; // r8d
  int v37; // r14d
  unsigned int v38; // edx
  char *v39; // r15
  const void *v40; // r15
  __int64 v41; // rcx
  int v42; // eax
  __int64 v43; // rax
  __int64 v44; // rdi
  __int64 v45; // rdi
  __int64 v46; // rdi
  size_t v47; // rax
  _BYTE *v48; // rax
  size_t v49; // rcx
  _BYTE *v50; // [rsp+28h] [rbp-D8h]
  int v51; // [rsp+70h] [rbp-90h]
  void *Src; // [rsp+78h] [rbp-88h]
  int v53; // [rsp+80h] [rbp-80h]
  unsigned int v54; // [rsp+84h] [rbp-7Ch]
  _DWORD *v55; // [rsp+88h] [rbp-78h]
  int v56; // [rsp+98h] [rbp-68h]
  __int128 v57; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v58; // [rsp+B0h] [rbp-50h]
  __int128 v59; // [rsp+C0h] [rbp-40h]
  int *v60; // [rsp+D0h] [rbp-30h]
  _BYTE v61[16]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v62[16]; // [rsp+E8h] [rbp-18h] BYREF
  char v63; // [rsp+F8h] [rbp-8h] BYREF

  v11 = a1[5];
  v13 = (unsigned int)a1[4];
  v14 = a2;
  v15 = a5;
  v17 = a7;
  v60 = a9;
  Src = a3;
  v18 = a1[3] == 4;
  v19 = a1[3] == 5;
  v20 = (unsigned int)(a1[3] - 4) <= 1;
  v54 = v11;
  HIDWORD(a2) = 0;
  v53 = v18 || v19;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  if ( a10 )
  {
    LODWORD(a2) = a6 % (unsigned int)v13;
    v21 = a6 - a6 % (unsigned int)v13;
    v22 = v21 + v13;
    v51 = v21 + v13;
    if ( v21 + (unsigned int)v13 < v21 )
    {
      v23 = -1;
      v21 = -1073741675;
      goto LABEL_105;
    }
  }
  else
  {
    LODWORD(a2) = a6 % v11;
    v22 = a6;
    v51 = a6;
    if ( a6 % v11 )
    {
      v21 = -1073741306;
      DebugTraceError(3221225990LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c", 487);
      v23 = a6;
      goto LABEL_26;
    }
    v21 = a6;
  }
  if ( !a7 && (!v20 || a5) )
    goto LABEL_10;
  if ( v22 > a8 )
  {
    v21 = -1073741789;
    v24 = 506;
    v25 = 3221225507LL;
LABEL_102:
    DebugTraceError(v25, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c", v24);
LABEL_103:
    if ( a10 )
      goto LABEL_104;
LABEL_25:
    v23 = v51;
    goto LABEL_26;
  }
  if ( !a5 && !v20 || a5 + a6 < a5 || a7 + a8 < a7 )
  {
    v24 = 515;
    goto LABEL_101;
  }
  v56 = a1[2];
  v26 = a10;
  if ( !a10 )
  {
LABEL_22:
    if ( !v21 && !v20 && !v26 )
      goto LABEL_25;
    v30 = (volatile signed __int64 *)(a1 + 10);
    if ( a3 )
    {
      if ( a4 < (unsigned int)v13 && !v20 )
      {
        v21 = -1073741306;
        v24 = 570;
        v25 = 3221225990LL;
        goto LABEL_102;
      }
      if ( a1[3] == 2 )
      {
        v24 = 577;
LABEL_101:
        v25 = 3221225485LL;
        v21 = -1073741811;
        goto LABEL_102;
      }
      v31 = a3;
    }
    else
    {
      v31 = a1 + 10;
    }
    v55 = v31;
    if ( v20 )
    {
      if ( v26 )
      {
        v21 = -1073741811;
        v27 = 591;
        v28 = 3221225485LL;
        goto LABEL_20;
      }
      v32 = validateAuthCipherModeInfo(v14, a2, a3, v17);
      v33 = v32;
      if ( !v32 )
      {
        v21 = -1073741811;
        v34 = 599;
        v35 = 3221225485LL;
LABEL_40:
        DebugTraceError(v35, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c", v34);
        goto LABEL_25;
      }
      v36 = (*(_DWORD *)(v32 + 80) >> 1) & 1;
      v37 = *(_DWORD *)(v32 + 80) & 1;
      if ( v37 )
      {
        if ( a6 % (unsigned int)v13 )
        {
          v21 = -1073741306;
          v34 = 611;
          v35 = 3221225990LL;
          goto LABEL_40;
        }
LABEL_46:
        v38 = (unsigned __int16)v56 - 1;
        v39 = (char *)a1
            + *((unsigned int *)&rgSymmAlgorithmDefaults[14 * (unsigned int)(unsigned __int16)a1[2] - 5] - 1);
        switch ( a1[3] )
        {
          case 1:
            v46 = 14LL * v38;
            ((void (__fastcall *)(char *, _QWORD, _DWORD *, unsigned __int64, unsigned int, unsigned __int64, int))rgSymmAlgorithmDefaults[v46 + 10])(
              v39,
              (unsigned int)v13,
              v31,
              v15,
              v21,
              v17,
              1);
            if ( a10 )
              ((void (__fastcall *)(char *, _QWORD, _DWORD *, _BYTE *, _DWORD, unsigned __int64, int))rgSymmAlgorithmDefaults[v46 + 10])(
                v39,
                (unsigned int)v13,
                v55,
                v61,
                v13,
                a7 + v21,
                1);
            break;
          case 2:
            v45 = 14LL * v38;
            LODWORD(v50) = 1;
            ((void (__fastcall *)(char *, _QWORD, unsigned __int64, _QWORD, unsigned __int64, _BYTE *))rgSymmAlgorithmDefaults[v45 + 9])(
              v39,
              (unsigned int)v13,
              v15,
              v21,
              v17,
              v50);
            if ( a10 )
              ((void (__fastcall *)(char *, _QWORD, _BYTE *, _QWORD, unsigned __int64, int))rgSymmAlgorithmDefaults[v45 + 9])(
                v39,
                (unsigned int)v13,
                v61,
                (unsigned int)v13,
                a7 + v21,
                1);
            break;
          case 3:
            v44 = 14LL * v38;
            LODWORD(v50) = v21;
            ((void (__fastcall *)(char *, _QWORD, _QWORD, _DWORD *, unsigned __int64, _BYTE *, unsigned __int64, int))rgSymmAlgorithmDefaults[v44 + 11])(
              (char *)a1
            + *((unsigned int *)&rgSymmAlgorithmDefaults[14 * (unsigned int)(unsigned __int16)a1[2] - 5] - 1),
              (unsigned int)v13,
              v54,
              v31,
              v15,
              v50,
              v17,
              1);
            if ( a10 )
              ((void (__fastcall *)(char *, _QWORD, _QWORD, _DWORD *, _BYTE *, _DWORD, unsigned __int64, int))rgSymmAlgorithmDefaults[v44 + 11])(
                v39,
                (unsigned int)v13,
                v54,
                v55,
                v61,
                v13,
                a7 + v21,
                1);
            break;
          case 4:
            if ( v37 || *(_QWORD *)(v33 + 56) )
            {
              v24 = 694;
              goto LABEL_101;
            }
            v42 = ((__int64 (__fastcall *)(char *, _QWORD, _QWORD, _QWORD, _DWORD, unsigned __int64, unsigned int, unsigned __int64, _QWORD, _DWORD, _QWORD, _DWORD, int))rgSymmAlgorithmDefaults[14 * v38 + 12])(
                    v39,
                    0,
                    (unsigned int)v13,
                    *(_QWORD *)(v33 + 8),
                    *(_DWORD *)(v33 + 16),
                    v15,
                    v21,
                    v17,
                    *(_QWORD *)(v33 + 24),
                    *(_DWORD *)(v33 + 32),
                    *(_QWORD *)(v33 + 40),
                    *(_DWORD *)(v33 + 48),
                    1);
            v21 = v42;
            if ( v42 < 0 )
            {
              v24 = 714;
              goto LABEL_69;
            }
            break;
          case 5:
            *(_QWORD *)&v57 = a1;
            if ( v37 || v36 )
            {
              if ( !*(_QWORD *)(v33 + 56) || *(_DWORD *)(v33 + 64) < (unsigned int)v13 || (v40 = Src) == 0 )
              {
                v24 = 731;
                goto LABEL_101;
              }
              *((_QWORD *)&v57 + 1) = Src;
              *(_QWORD *)&v58 = *(_QWORD *)(v33 + 56);
              *((_QWORD *)&v58 + 1) = *(unsigned int *)(v33 + 68);
              *(_QWORD *)&v59 = *(_QWORD *)(v33 + 72);
              DWORD2(v59) = v37 == 0;
            }
            else
            {
              v40 = Src;
              *((_QWORD *)&v57 + 1) = v62;
              *(_QWORD *)&v58 = &v63;
              *((_QWORD *)&v58 + 1) = 0;
              *(_QWORD *)&v59 = 0;
              DWORD2(v59) = 1;
            }
            if ( (a11 & 0x20) != 0 )
            {
              if ( (a1[7] & 2) == 0 )
              {
                v24 = 759;
                goto LABEL_101;
              }
              if ( *(_DWORD *)(v33 + 16) != 12 || (v41 = *(_QWORD *)(v33 + 8)) == 0 )
              {
                v24 = 767;
                goto LABEL_101;
              }
              if ( v36 )
              {
                *(_QWORD *)v41 = *v30;
              }
              else
              {
                **(_QWORD **)(v33 + 8) = _InterlockedIncrement64(v30);
                v41 = *(_QWORD *)(v33 + 8);
              }
              *(_DWORD *)(v41 + 8) = a1[12];
            }
            v42 = ((__int64 (__fastcall *)(_QWORD, __int128 *, _QWORD, _QWORD, _DWORD, unsigned __int64, unsigned int, unsigned __int64, _QWORD, _DWORD, _QWORD, _DWORD, int))rgSymmAlgorithmDefaults[14 * v38 + 13])(
                    0,
                    &v57,
                    (unsigned int)v13,
                    *(_QWORD *)(v33 + 8),
                    *(_DWORD *)(v33 + 16),
                    v15,
                    v21,
                    v17,
                    *(_QWORD *)(v33 + 24),
                    *(_DWORD *)(v33 + 32),
                    *(_QWORD *)(v33 + 40),
                    *(_DWORD *)(v33 + 48),
                    1);
            v21 = v42;
            if ( v42 < 0 )
            {
              v24 = 803;
LABEL_69:
              v25 = (unsigned int)v42;
              goto LABEL_102;
            }
            if ( v37 )
            {
              *(_DWORD *)(v33 + 68) = DWORD2(v58);
              v43 = v59;
              *(_DWORD *)(v33 + 80) |= 2u;
              *(_QWORD *)(v33 + 72) = v43;
            }
            else
            {
              *(_DWORD *)(v33 + 80) &= ~2u;
              *(_DWORD *)(v33 + 68) = 0;
              *(_QWORD *)(v33 + 72) = 0;
            }
LABEL_88:
            if ( (a1[7] & 2) == 0 )
            {
              if ( v40 )
              {
                if ( !a10 || v53 && v37 )
                {
                  memmove(a1 + 10, v40, v13);
                  goto LABEL_10;
                }
              }
              else if ( !a10 && (!v53 || v37) )
              {
                goto LABEL_10;
              }
              v47 = v13;
              if ( (_DWORD)v13 )
              {
                do
                {
                  *(_BYTE *)v30 = 0;
                  v30 = (volatile signed __int64 *)((char *)v30 + 1);
                  --v47;
                }
                while ( v47 );
              }
            }
LABEL_10:
            v21 = 0;
            goto LABEL_103;
          default:
            v21 = -1073741816;
            v24 = 827;
            v25 = 3221225480LL;
            goto LABEL_102;
        }
        v40 = Src;
        goto LABEL_88;
      }
    }
    else
    {
      v33 = 0;
      v36 = 0;
    }
    v37 = 0;
    goto LABEL_46;
  }
  if ( (unsigned int)v13 <= 0x10 )
  {
    v50 = v62;
    SymCryptPaddingPkcs7Add(v13, a5 + v21, a6 - v21, v61);
    v20 = v53;
    v17 = a7;
    v26 = a10;
    v15 = a5;
    a3 = Src;
    goto LABEL_22;
  }
  v21 = -1073741789;
  v27 = 527;
  v28 = 3221225507LL;
LABEL_20:
  DebugTraceError(v28, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c", v27);
LABEL_104:
  v23 = v51;
LABEL_105:
  v48 = v61;
  v49 = v13;
  if ( (_DWORD)v13 )
  {
    do
    {
      *v48++ = 0;
      --v49;
    }
    while ( v49 );
  }
LABEL_26:
  *v60 = v23;
  return v21;
}

```

## disassembly

```asm
0x18000bfe8  mov     [rsp-8+arg_18], rbx
0x18000bfed  push    rbp
0x18000bfee  push    rsi
0x18000bfef  push    rdi
0x18000bff0  push    r12
0x18000bff2  push    r13
0x18000bff4  push    r14
0x18000bff6  push    r15
0x18000bff8  lea     rbp, [rsp-10h]
0x18000bffd  sub     rsp, 110h
0x18000c004  mov     rax, cs:__security_cookie
0x18000c00b  xor     rax, rsp
0x18000c00e  mov     [rbp+40h+var_38], rax
0x18000c012  mov     r10d, [rcx+14h]
0x18000c016  xorps   xmm0, xmm0
0x18000c019  mov     rax, [rbp+40h+arg_40]
0x18000c020  mov     r13, rcx
0x18000c023  mov     esi, [rcx+10h]
0x18000c026  mov     r14, rdx
0x18000c029  mov     r11, [rbp+40h+arg_20]
0x18000c02d  mov     edi, r9d
0x18000c030  mov     r15d, [rbp+40h+arg_28]
0x18000c034  mov     r9, [rbp+40h+arg_30]
0x18000c03b  mov     [rbp+40h+var_70], rax
0x18000c03f  mov     eax, [rcx+0Ch]
0x18000c042  xor     ecx, ecx
0x18000c044  sub     eax, 4
0x18000c047  mov     [rsp+140h+Src], r8
0x18000c04c  cmp     eax, 1
0x18000c04f  mov     [rbp+40h+var_B8], r11
0x18000c053  mov     [rbp+40h+var_B0], r9
0x18000c057  mov     eax, r15d
0x18000c05a  setbe   cl
0x18000c05d  mov     [rbp+40h+var_BC], r10d
0x18000c061  xor     edx, edx
0x18000c063  mov     [rbp+40h+var_C0], ecx
0x18000c066  movups  [rbp+40h+var_A0], xmm0
0x18000c06a  movups  [rbp+40h+var_90], xmm0
0x18000c06e  movups  [rbp+40h+var_80], xmm0
0x18000c072  cmp     [rbp+40h+arg_48], edx
0x18000c078  jz      short loc_18000C09C
0x18000c07a  div     esi
0x18000c07c  mov     ebx, r15d
0x18000c07f  sub     ebx, edx
0x18000c081  lea     r12d, [rbx+rsi]
0x18000c085  mov     [rsp+140h+var_D0], r12d
0x18000c08a  cmp     r12d, ebx
0x18000c08d  jnb     short loc_18000C0D9
0x18000c08f  or      edx, 0FFFFFFFFh
0x18000c092  mov     ebx, 0C0000095h
0x18000c097  jmp     loc_18000C777
0x18000c09c  div     r10d
0x18000c09f  mov     r12d, r15d
0x18000c0a2  mov     [rsp+140h+var_D0], r15d
0x18000c0a7  test    edx, edx
0x18000c0a9  jz      short loc_18000C0D6
0x18000c0ab  mov     r9d, 1E7h
0x18000c0b1  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c0b8  lea     rdx, aStatus; "Status"
0x18000c0bf  mov     ecx, 0C0000206h
0x18000c0c4  mov     ebx, 0C0000206h
0x18000c0c9  call    DebugTraceError
0x18000c0ce  mov     edx, r15d
0x18000c0d1  jmp     loc_18000C1BC
0x18000c0d6  mov     ebx, r15d
0x18000c0d9  test    r9, r9
0x18000c0dc  jnz     short loc_18000C0EE
0x18000c0de  test    ecx, ecx
0x18000c0e0  jz      short loc_18000C0E7
0x18000c0e2  test    r11, r11
0x18000c0e5  jz      short loc_18000C0EE
0x18000c0e7  xor     ebx, ebx
0x18000c0e9  jmp     loc_18000C766
0x18000c0ee  cmp     r12d, [rbp+40h+arg_38]
0x18000c0f5  jbe     short loc_18000C10C
0x18000c0f7  mov     ebx, 0C0000023h
0x18000c0fc  mov     r9d, 1FAh
0x18000c102  mov     ecx, 0C0000023h
0x18000c107  jmp     loc_18000C753
0x18000c10c  test    r11, r11
0x18000c10f  jnz     short loc_18000C119
0x18000c111  test    ecx, ecx
0x18000c113  jz      loc_18000C743
0x18000c119  lea     rax, [r11+r15]
0x18000c11d  cmp     rax, r11
0x18000c120  jb      loc_18000C743
0x18000c126  mov     eax, [rbp+40h+arg_38]
0x18000c12c  add     rax, r9
0x18000c12f  cmp     rax, r9
0x18000c132  jb      loc_18000C743
0x18000c138  mov     eax, [r13+8]
0x18000c13c  mov     [rbp+40h+var_A8], eax
0x18000c13f  mov     eax, [rbp+40h+arg_48]
0x18000c145  test    eax, eax
0x18000c147  jz      short loc_18000C1AC
0x18000c149  cmp     esi, 10h
0x18000c14c  jbe     short loc_18000C176
0x18000c14e  mov     ebx, 0C0000023h
0x18000c153  mov     r9d, 20Fh
0x18000c159  mov     ecx, 0C0000023h
0x18000c15e  lea     rdx, aStatus; "Status"
0x18000c165  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c16c  call    DebugTraceError
0x18000c171  jmp     loc_18000C773
0x18000c176  mov     r8d, r15d
0x18000c179  mov     edx, ebx
0x18000c17b  lea     rax, [rbp+40h+var_58]
0x18000c17f  sub     r8d, ebx
0x18000c182  add     rdx, r11
0x18000c185  mov     [rsp+140h+var_118], rax
0x18000c18a  mov     rcx, rsi
0x18000c18d  lea     r9, [rbp+40h+var_68]
0x18000c191  call    SymCryptPaddingPkcs7Add
0x18000c196  mov     ecx, [rbp+40h+var_C0]
0x18000c199  mov     r9, [rbp+40h+var_B0]
0x18000c19d  mov     eax, [rbp+40h+arg_48]
0x18000c1a3  mov     r11, [rbp+40h+var_B8]
0x18000c1a7  mov     r8, [rsp+140h+Src]
0x18000c1ac  test    ebx, ebx
0x18000c1ae  jnz     short loc_18000C1EC
0x18000c1b0  test    ecx, ecx
0x18000c1b2  jnz     short loc_18000C1EC
0x18000c1b4  test    eax, eax
0x18000c1b6  jnz     short loc_18000C1EC
0x18000c1b8  mov     edx, [rsp+140h+var_D0]
0x18000c1bc  mov     rax, [rbp+40h+var_70]
0x18000c1c0  mov     [rax], edx
0x18000c1c2  mov     eax, ebx
0x18000c1c4  mov     rcx, [rbp+40h+var_38]
0x18000c1c8  xor     rcx, rsp; StackCookie
0x18000c1cb  call    __security_check_cookie
0x18000c1d0  mov     rbx, [rsp+140h+arg_18]
0x18000c1d8  add     rsp, 110h
0x18000c1df  pop     r15
0x18000c1e1  pop     r14
0x18000c1e3  pop     r13
0x18000c1e5  pop     r12
0x18000c1e7  pop     rdi
0x18000c1e8  pop     rsi
0x18000c1e9  pop     rbp
0x18000c1ea  retn
0x18000c1ec  lea     r12, [r13+28h]
0x18000c1f0  test    r8, r8
0x18000c1f3  jnz     short loc_18000C1FA
0x18000c1f5  mov     r10, r12
0x18000c1f8  jmp     short loc_18000C22C
0x18000c1fa  cmp     edi, esi
0x18000c1fc  jnb     short loc_18000C217
0x18000c1fe  test    ecx, ecx
0x18000c200  jnz     short loc_18000C217
0x18000c202  mov     ebx, 0C0000206h
0x18000c207  mov     r9d, 23Ah
0x18000c20d  mov     ecx, 0C0000206h
0x18000c212  jmp     loc_18000C753
0x18000c217  cmp     dword ptr [r13+0Ch], 2
0x18000c21c  jnz     short loc_18000C229
0x18000c21e  mov     r9d, 241h
0x18000c224  jmp     loc_18000C749
0x18000c229  mov     r10, r8
0x18000c22c  mov     [rbp+40h+var_B8], r10
0x18000c230  test    ecx, ecx
0x18000c232  jz      loc_18000C2BA
0x18000c238  test    eax, eax
0x18000c23a  jz      short loc_18000C251
0x18000c23c  mov     ebx, 0C000000Dh
0x18000c241  mov     r9d, 24Fh
0x18000c247  mov     ecx, 0C000000Dh
0x18000c24c  jmp     loc_18000C15E
0x18000c251  mov     rcx, r14
0x18000c254  call    validateAuthCipherModeInfo
0x18000c259  mov     rdi, rax
0x18000c25c  test    rax, rax
0x18000c25f  jnz     short loc_18000C289
0x18000c261  mov     ebx, 0C000000Dh
0x18000c266  mov     r9d, 257h
0x18000c26c  mov     ecx, 0C000000Dh
0x18000c271  lea     rdx, aStatus; "Status"
0x18000c278  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c27f  call    DebugTraceError
0x18000c284  jmp     loc_18000C1B8
0x18000c289  mov     r8d, [rax+50h]
0x18000c28d  mov     r14d, r8d
0x18000c290  shr     r8d, 1
0x18000c293  and     r8d, 1
0x18000c297  and     r14d, 1
0x18000c29b  jz      short loc_18000C2BF
0x18000c29d  xor     edx, edx
0x18000c29f  mov     eax, r15d
0x18000c2a2  div     esi
0x18000c2a4  test    edx, edx
0x18000c2a6  jz      short loc_18000C2C2
0x18000c2a8  mov     ebx, 0C0000206h
0x18000c2ad  mov     r9d, 263h
0x18000c2b3  mov     ecx, 0C0000206h
0x18000c2b8  jmp     short loc_18000C271
0x18000c2ba  xor     edi, edi
0x18000c2bc  xor     r8d, r8d
0x18000c2bf  xor     r14d, r14d
0x18000c2c2  mov     eax, [r13+8]
0x18000c2c6  movzx   edx, word ptr [rbp+40h+var_A8]
0x18000c2ca  movzx   eax, ax
0x18000c2cd  dec     edx
0x18000c2cf  dec     eax
0x18000c2d1  imul    rcx, rax, 70h ; 'p'
0x18000c2d5  lea     rax, rgSymmAlgorithmDefaults
0x18000c2dc  mov     r15d, [rcx+rax+44h]
0x18000c2e1  mov     ecx, [r13+0Ch]
0x18000c2e5  add     r15, r13
0x18000c2e8  sub     ecx, 1
0x18000c2eb  jz      loc_18000C65B
0x18000c2f1  sub     ecx, 1
0x18000c2f4  jz      loc_18000C5ED
0x18000c2fa  sub     ecx, 1
0x18000c2fd  jz      loc_18000C564
0x18000c303  sub     ecx, 1
0x18000c306  jz      loc_18000C4D5
0x18000c30c  cmp     ecx, 1
0x18000c30f  jz      short loc_18000C326
0x18000c311  mov     ebx, 0C0000008h
0x18000c316  mov     r9d, 33Bh
0x18000c31c  mov     ecx, 0C0000008h
0x18000c321  jmp     loc_18000C753
0x18000c326  xor     r10d, r10d
0x18000c329  mov     qword ptr [rbp+40h+var_A0], r13
0x18000c32d  test    r14d, r14d
0x18000c330  jnz     short loc_18000C35D
0x18000c332  test    r8d, r8d
0x18000c335  jnz     short loc_18000C35D
0x18000c337  mov     r15, [rsp+140h+Src]
0x18000c33c  lea     rax, [rbp+40h+var_58]
0x18000c340  mov     qword ptr [rbp+40h+var_A0+8], rax
0x18000c344  lea     rax, [rbp+40h+var_48]
0x18000c348  mov     qword ptr [rbp+40h+var_90], rax
0x18000c34c  mov     qword ptr [rbp+40h+var_90+8], r10
0x18000c350  mov     qword ptr [rbp+40h+var_80], r10
0x18000c354  mov     dword ptr [rbp+40h+var_80+8], 1
0x18000c35b  jmp     short loc_18000C3A5
0x18000c35d  cmp     [rdi+38h], r10
0x18000c361  jz      loc_18000C4CA
0x18000c367  cmp     [rdi+40h], esi
0x18000c36a  jb      loc_18000C4CA
0x18000c370  mov     r15, [rsp+140h+Src]
0x18000c375  test    r15, r15
0x18000c378  jz      loc_18000C4CA
0x18000c37e  mov     qword ptr [rbp+40h+var_A0+8], r15
0x18000c382  test    r14d, r14d
0x18000c385  mov     rax, [rdi+38h]
0x18000c389  mov     qword ptr [rbp+40h+var_90], rax
0x18000c38d  mov     eax, [rdi+44h]
0x18000c390  mov     qword ptr [rbp+40h+var_90+8], rax
0x18000c394  mov     rax, [rdi+48h]
0x18000c398  mov     qword ptr [rbp+40h+var_80], rax
0x18000c39c  mov     eax, r10d
0x18000c39f  setz    al
0x18000c3a2  mov     dword ptr [rbp+40h+var_80+8], eax
0x18000c3a5  test    [rbp+40h+arg_50], 20h
0x18000c3ac  jz      short loc_18000C400
0x18000c3ae  mov     eax, [r13+1Ch]
0x18000c3b2  test    al, 2
0x18000c3b4  jnz     short loc_18000C3C1
0x18000c3b6  mov     r9d, 2F7h
0x18000c3bc  jmp     loc_18000C749
0x18000c3c1  cmp     dword ptr [rdi+10h], 0Ch
0x18000c3c5  jnz     loc_18000C48B
0x18000c3cb  mov     rcx, [rdi+8]
0x18000c3cf  test    rcx, rcx
0x18000c3d2  jz      loc_18000C48B
0x18000c3d8  test    r8d, r8d
0x18000c3db  jnz     loc_18000C477
0x18000c3e1  lea     ecx, [r8+1]
0x18000c3e5  lock xadd [r12], rcx
0x18000c3eb  mov     rax, [rdi+8]
0x18000c3ef  inc     rcx
0x18000c3f2  mov     [rax], rcx
0x18000c3f5  mov     rcx, [rdi+8]
0x18000c3f9  mov     eax, [r13+30h]
0x18000c3fd  mov     [rcx+8], eax
0x18000c400  mov     [rsp+140h+var_E0], 1
0x18000c408  mov     r8d, esi
0x18000c40b  mov     eax, edx
0x18000c40d  lea     rdx, [rbp+40h+var_A0]
0x18000c411  imul    rcx, rax, 70h ; 'p'
0x18000c415  lea     rax, rgSymmAlgorithmDefaults
0x18000c41c  mov     r10, [rcx+rax+68h]
0x18000c421  mov     rcx, [rdi+28h]
0x18000c425  mov     eax, [rdi+30h]
0x18000c428  mov     [rsp+140h+var_E8], eax
0x18000c42c  mov     rax, r10
0x18000c42f  mov     [rsp+140h+var_F0], rcx
0x18000c434  mov     ecx, [rdi+20h]
0x18000c437  mov     [rsp+140h+var_F8], ecx
0x18000c43b  mov     rcx, [rdi+18h]
0x18000c43f  mov     [rsp+140h+var_100], rcx
0x18000c444  mov     ecx, [rdi+10h]
0x18000c447  mov     [rsp+140h+var_108], r9
0x18000c44c  mov     r9, [rdi+8]
0x18000c450  mov     dword ptr [rsp+140h+var_110], ebx
0x18000c454  mov     [rsp+140h+var_118], r11
0x18000c459  mov     dword ptr [rsp+140h+var_120], ecx
0x18000c45d  xor     ecx, ecx
  ... truncated ...
```

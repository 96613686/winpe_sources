# MSBlockEncrypt

- ea: `0x180016108`
- end: `0x1800168b7`
- name: `MSBlockEncrypt`
- size: `1967`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180014d10`

## callees

- `0x18001155c`
- `0x180016108`
- `0x180016b40`
- `0x18004a4c4`
- `0x1800a4260`
- `0x1800a4300`
- `0x1800a45c0`

## string_xrefs

- `0x1800161d1`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`
- `0x180016285`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`
- `0x180016398`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`
- `0x180016873`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`

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
0x180016108  mov     [rsp-8+arg_18], rbx
0x18001610d  push    rbp
0x18001610e  push    rsi
0x18001610f  push    rdi
0x180016110  push    r12
0x180016112  push    r13
0x180016114  push    r14
0x180016116  push    r15
0x180016118  lea     rbp, [rsp-10h]
0x18001611d  sub     rsp, 110h
0x180016124  mov     rax, cs:__security_cookie
0x18001612b  xor     rax, rsp
0x18001612e  mov     [rbp+40h+var_38], rax
0x180016132  mov     r10d, [rcx+14h]
0x180016136  xorps   xmm0, xmm0
0x180016139  mov     rax, [rbp+40h+arg_40]
0x180016140  mov     r13, rcx
0x180016143  mov     esi, [rcx+10h]
0x180016146  mov     r14, rdx
0x180016149  mov     r11, [rbp+40h+arg_20]
0x18001614d  mov     edi, r9d
0x180016150  mov     r15d, [rbp+40h+arg_28]
0x180016154  mov     r9, [rbp+40h+arg_30]
0x18001615b  mov     [rbp+40h+var_70], rax
0x18001615f  mov     eax, [rcx+0Ch]
0x180016162  xor     ecx, ecx
0x180016164  sub     eax, 4
0x180016167  mov     [rsp+140h+Src], r8
0x18001616c  cmp     eax, 1
0x18001616f  mov     [rbp+40h+var_B8], r11
0x180016173  mov     [rbp+40h+var_B0], r9
0x180016177  mov     eax, r15d
0x18001617a  setbe   cl
0x18001617d  mov     [rbp+40h+var_BC], r10d
0x180016181  xor     edx, edx
0x180016183  mov     [rbp+40h+var_C0], ecx
0x180016186  movups  [rbp+40h+var_A0], xmm0
0x18001618a  movups  [rbp+40h+var_90], xmm0
0x18001618e  movups  [rbp+40h+var_80], xmm0
0x180016192  cmp     [rbp+40h+arg_48], edx
0x180016198  jz      short loc_1800161BC
0x18001619a  div     esi
0x18001619c  mov     ebx, r15d
0x18001619f  sub     ebx, edx
0x1800161a1  lea     r12d, [rbx+rsi]
0x1800161a5  mov     [rsp+140h+var_D0], r12d
0x1800161aa  cmp     r12d, ebx
0x1800161ad  jnb     short loc_1800161F9
0x1800161af  or      edx, 0FFFFFFFFh
0x1800161b2  mov     ebx, 0C0000095h
0x1800161b7  jmp     loc_180016897
0x1800161bc  div     r10d
0x1800161bf  mov     r12d, r15d
0x1800161c2  mov     [rsp+140h+var_D0], r15d
0x1800161c7  test    edx, edx
0x1800161c9  jz      short loc_1800161F6
0x1800161cb  mov     r9d, 1E7h
0x1800161d1  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800161d8  lea     rdx, aStatus; "Status"
0x1800161df  mov     ecx, 0C0000206h
0x1800161e4  mov     ebx, 0C0000206h
0x1800161e9  call    DebugTraceError
0x1800161ee  mov     edx, r15d
0x1800161f1  jmp     loc_1800162DC
0x1800161f6  mov     ebx, r15d
0x1800161f9  test    r9, r9
0x1800161fc  jnz     short loc_18001620E
0x1800161fe  test    ecx, ecx
0x180016200  jz      short loc_180016207
0x180016202  test    r11, r11
0x180016205  jz      short loc_18001620E
0x180016207  xor     ebx, ebx
0x180016209  jmp     loc_180016886
0x18001620e  cmp     r12d, [rbp+40h+arg_38]
0x180016215  jbe     short loc_18001622C
0x180016217  mov     ebx, 0C0000023h
0x18001621c  mov     r9d, 1FAh
0x180016222  mov     ecx, 0C0000023h
0x180016227  jmp     loc_180016873
0x18001622c  test    r11, r11
0x18001622f  jnz     short loc_180016239
0x180016231  test    ecx, ecx
0x180016233  jz      loc_180016863
0x180016239  lea     rax, [r11+r15]
0x18001623d  cmp     rax, r11
0x180016240  jb      loc_180016863
0x180016246  mov     eax, [rbp+40h+arg_38]
0x18001624c  add     rax, r9
0x18001624f  cmp     rax, r9
0x180016252  jb      loc_180016863
0x180016258  mov     eax, [r13+8]
0x18001625c  mov     [rbp+40h+var_A8], eax
0x18001625f  mov     eax, [rbp+40h+arg_48]
0x180016265  test    eax, eax
0x180016267  jz      short loc_1800162CC
0x180016269  cmp     esi, 10h
0x18001626c  jbe     short loc_180016296
0x18001626e  mov     ebx, 0C0000023h
0x180016273  mov     r9d, 20Fh
0x180016279  mov     ecx, 0C0000023h
0x18001627e  lea     rdx, aStatus; "Status"
0x180016285  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001628c  call    DebugTraceError
0x180016291  jmp     loc_180016893
0x180016296  mov     r8d, r15d
0x180016299  mov     edx, ebx
0x18001629b  lea     rax, [rbp+40h+var_58]
0x18001629f  sub     r8d, ebx
0x1800162a2  add     rdx, r11
0x1800162a5  mov     [rsp+140h+var_118], rax
0x1800162aa  mov     rcx, rsi
0x1800162ad  lea     r9, [rbp+40h+var_68]
0x1800162b1  call    SymCryptPaddingPkcs7Add
0x1800162b6  mov     ecx, [rbp+40h+var_C0]
0x1800162b9  mov     r9, [rbp+40h+var_B0]
0x1800162bd  mov     eax, [rbp+40h+arg_48]
0x1800162c3  mov     r11, [rbp+40h+var_B8]
0x1800162c7  mov     r8, [rsp+140h+Src]
0x1800162cc  test    ebx, ebx
0x1800162ce  jnz     short loc_18001630C
0x1800162d0  test    ecx, ecx
0x1800162d2  jnz     short loc_18001630C
0x1800162d4  test    eax, eax
0x1800162d6  jnz     short loc_18001630C
0x1800162d8  mov     edx, [rsp+140h+var_D0]
0x1800162dc  mov     rax, [rbp+40h+var_70]
0x1800162e0  mov     [rax], edx
0x1800162e2  mov     eax, ebx
0x1800162e4  mov     rcx, [rbp+40h+var_38]
0x1800162e8  xor     rcx, rsp; StackCookie
0x1800162eb  call    __security_check_cookie
0x1800162f0  mov     rbx, [rsp+140h+arg_18]
0x1800162f8  add     rsp, 110h
0x1800162ff  pop     r15
0x180016301  pop     r14
0x180016303  pop     r13
0x180016305  pop     r12
0x180016307  pop     rdi
0x180016308  pop     rsi
0x180016309  pop     rbp
0x18001630a  retn
0x18001630c  lea     r12, [r13+28h]
0x180016310  test    r8, r8
0x180016313  jnz     short loc_18001631A
0x180016315  mov     r10, r12
0x180016318  jmp     short loc_18001634C
0x18001631a  cmp     edi, esi
0x18001631c  jnb     short loc_180016337
0x18001631e  test    ecx, ecx
0x180016320  jnz     short loc_180016337
0x180016322  mov     ebx, 0C0000206h
0x180016327  mov     r9d, 23Ah
0x18001632d  mov     ecx, 0C0000206h
0x180016332  jmp     loc_180016873
0x180016337  cmp     dword ptr [r13+0Ch], 2
0x18001633c  jnz     short loc_180016349
0x18001633e  mov     r9d, 241h
0x180016344  jmp     loc_180016869
0x180016349  mov     r10, r8
0x18001634c  mov     [rbp+40h+var_B8], r10
0x180016350  test    ecx, ecx
0x180016352  jz      loc_1800163DA
0x180016358  test    eax, eax
0x18001635a  jz      short loc_180016371
0x18001635c  mov     ebx, 0C000000Dh
0x180016361  mov     r9d, 24Fh
0x180016367  mov     ecx, 0C000000Dh
0x18001636c  jmp     loc_18001627E
0x180016371  mov     rcx, r14
0x180016374  call    validateAuthCipherModeInfo
0x180016379  mov     rdi, rax
0x18001637c  test    rax, rax
0x18001637f  jnz     short loc_1800163A9
0x180016381  mov     ebx, 0C000000Dh
0x180016386  mov     r9d, 257h
0x18001638c  mov     ecx, 0C000000Dh
0x180016391  lea     rdx, aStatus; "Status"
0x180016398  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001639f  call    DebugTraceError
0x1800163a4  jmp     loc_1800162D8
0x1800163a9  mov     r8d, [rax+50h]
0x1800163ad  mov     r14d, r8d
0x1800163b0  shr     r8d, 1
0x1800163b3  and     r8d, 1
0x1800163b7  and     r14d, 1
0x1800163bb  jz      short loc_1800163DF
0x1800163bd  xor     edx, edx
0x1800163bf  mov     eax, r15d
0x1800163c2  div     esi
0x1800163c4  test    edx, edx
0x1800163c6  jz      short loc_1800163E2
0x1800163c8  mov     ebx, 0C0000206h
0x1800163cd  mov     r9d, 263h
0x1800163d3  mov     ecx, 0C0000206h
0x1800163d8  jmp     short loc_180016391
0x1800163da  xor     edi, edi
0x1800163dc  xor     r8d, r8d
0x1800163df  xor     r14d, r14d
0x1800163e2  mov     eax, [r13+8]
0x1800163e6  movzx   edx, word ptr [rbp+40h+var_A8]
0x1800163ea  movzx   eax, ax
0x1800163ed  dec     edx
0x1800163ef  dec     eax
0x1800163f1  imul    rcx, rax, 70h ; 'p'
0x1800163f5  lea     rax, rgSymmAlgorithmDefaults
0x1800163fc  mov     r15d, [rcx+rax+44h]
0x180016401  mov     ecx, [r13+0Ch]
0x180016405  add     r15, r13
0x180016408  sub     ecx, 1
0x18001640b  jz      loc_18001677B
0x180016411  sub     ecx, 1
0x180016414  jz      loc_18001670D
0x18001641a  sub     ecx, 1
0x18001641d  jz      loc_180016684
0x180016423  sub     ecx, 1
0x180016426  jz      loc_1800165F5
0x18001642c  cmp     ecx, 1
0x18001642f  jz      short loc_180016446
0x180016431  mov     ebx, 0C0000008h
0x180016436  mov     r9d, 33Bh
0x18001643c  mov     ecx, 0C0000008h
0x180016441  jmp     loc_180016873
0x180016446  xor     r10d, r10d
0x180016449  mov     qword ptr [rbp+40h+var_A0], r13
0x18001644d  test    r14d, r14d
0x180016450  jnz     short loc_18001647D
0x180016452  test    r8d, r8d
0x180016455  jnz     short loc_18001647D
0x180016457  mov     r15, [rsp+140h+Src]
0x18001645c  lea     rax, [rbp+40h+var_58]
0x180016460  mov     qword ptr [rbp+40h+var_A0+8], rax
0x180016464  lea     rax, [rbp+40h+var_48]
0x180016468  mov     qword ptr [rbp+40h+var_90], rax
0x18001646c  mov     qword ptr [rbp+40h+var_90+8], r10
0x180016470  mov     qword ptr [rbp+40h+var_80], r10
0x180016474  mov     dword ptr [rbp+40h+var_80+8], 1
0x18001647b  jmp     short loc_1800164C5
0x18001647d  cmp     [rdi+38h], r10
0x180016481  jz      loc_1800165EA
0x180016487  cmp     [rdi+40h], esi
0x18001648a  jb      loc_1800165EA
0x180016490  mov     r15, [rsp+140h+Src]
0x180016495  test    r15, r15
0x180016498  jz      loc_1800165EA
0x18001649e  mov     qword ptr [rbp+40h+var_A0+8], r15
0x1800164a2  test    r14d, r14d
0x1800164a5  mov     rax, [rdi+38h]
0x1800164a9  mov     qword ptr [rbp+40h+var_90], rax
0x1800164ad  mov     eax, [rdi+44h]
0x1800164b0  mov     qword ptr [rbp+40h+var_90+8], rax
0x1800164b4  mov     rax, [rdi+48h]
0x1800164b8  mov     qword ptr [rbp+40h+var_80], rax
0x1800164bc  mov     eax, r10d
0x1800164bf  setz    al
0x1800164c2  mov     dword ptr [rbp+40h+var_80+8], eax
0x1800164c5  test    [rbp+40h+arg_50], 20h
0x1800164cc  jz      short loc_180016520
0x1800164ce  mov     eax, [r13+1Ch]
0x1800164d2  test    al, 2
0x1800164d4  jnz     short loc_1800164E1
0x1800164d6  mov     r9d, 2F7h
0x1800164dc  jmp     loc_180016869
0x1800164e1  cmp     dword ptr [rdi+10h], 0Ch
0x1800164e5  jnz     loc_1800165AB
0x1800164eb  mov     rcx, [rdi+8]
0x1800164ef  test    rcx, rcx
0x1800164f2  jz      loc_1800165AB
0x1800164f8  test    r8d, r8d
0x1800164fb  jnz     loc_180016597
0x180016501  lea     ecx, [r8+1]
0x180016505  lock xadd [r12], rcx
0x18001650b  mov     rax, [rdi+8]
0x18001650f  inc     rcx
0x180016512  mov     [rax], rcx
0x180016515  mov     rcx, [rdi+8]
0x180016519  mov     eax, [r13+30h]
0x18001651d  mov     [rcx+8], eax
0x180016520  mov     [rsp+140h+var_E0], 1
0x180016528  mov     r8d, esi
0x18001652b  mov     eax, edx
0x18001652d  lea     rdx, [rbp+40h+var_A0]
0x180016531  imul    rcx, rax, 70h ; 'p'
0x180016535  lea     rax, rgSymmAlgorithmDefaults
0x18001653c  mov     r10, [rcx+rax+68h]
0x180016541  mov     rcx, [rdi+28h]
0x180016545  mov     eax, [rdi+30h]
0x180016548  mov     [rsp+140h+var_E8], eax
0x18001654c  mov     rax, r10
0x18001654f  mov     [rsp+140h+var_F0], rcx
0x180016554  mov     ecx, [rdi+20h]
0x180016557  mov     [rsp+140h+var_F8], ecx
0x18001655b  mov     rcx, [rdi+18h]
0x18001655f  mov     [rsp+140h+var_100], rcx
0x180016564  mov     ecx, [rdi+10h]
0x180016567  mov     [rsp+140h+var_108], r9
0x18001656c  mov     r9, [rdi+8]
0x180016570  mov     dword ptr [rsp+140h+var_110], ebx
0x180016574  mov     [rsp+140h+var_118], r11
0x180016579  mov     dword ptr [rsp+140h+var_120], ecx
0x18001657d  xor     ecx, ecx
  ... truncated ...
```

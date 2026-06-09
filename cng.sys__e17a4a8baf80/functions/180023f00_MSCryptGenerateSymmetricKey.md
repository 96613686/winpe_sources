# MSCryptGenerateSymmetricKey

- ea: `0x180023f00`
- end: `0x1800244da`
- name: `MSCryptGenerateSymmetricKey`
- size: `1498`
- prototype: `__int64 __fastcall(int, int, int, int, void *Src, size_t Size, int)`
- caller_count: `4`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x1800210a0`
- `0x180021e20`
- `0x180023a50`
- `0x180088308`

## callees

- `0x18001155c`
- `0x1800123d0`
- `0x180016db0`
- `0x180023f00`
- `0x180024500`
- `0x180024da0`
- `0x180025360`
- `0x180025700`
- `0x180025ec0`
- `0x180025fb0`
- `0x1800466c8`
- `0x1800564d0`
- `0x18006e180`
- `0x180090a9c`
- `0x18009ca80`
- `0x18009ccd0`
- `0x1800a4260`
- `0x1800a45c0`
- `0x1800a4890`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1800240f0`
- `ntoskrnl!KeGetCurrentIrql` at `0x1800240f0`

## string_xrefs

- `0x180024262`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x1800242d2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18002432b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x1800243a2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`

## pseudocode

```c
__int64 __fastcall MSCryptGenerateSymmetricKey(
        _DWORD *a1,
        char **a2,
        __int64 a3,
        unsigned int a4,
        char *Src,
        size_t Size,
        int a7)
{
  char *v8; // rbx
  unsigned int v9; // ebp
  unsigned int v10; // edi
  int v11; // r10d
  __int64 v12; // rdx
  unsigned int v13; // r9d
  __int64 v14; // r9
  char *v15; // r13
  int v16; // eax
  int v17; // edx
  int v18; // esi
  int v19; // r8d
  int v20; // eax
  unsigned __int64 v21; // r14
  _BYTE *v22; // r15
  size_t v23; // rbp
  int v24; // r12d
  __int64 v26; // r9
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r8
  __int64 v30; // r8
  __int64 v31; // r8
  KIRQL CurrentIrql; // [rsp+40h] [rbp-C8h]
  __int64 v33; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v34; // [rsp+50h] [rbp-B8h] BYREF
  char *v35; // [rsp+58h] [rbp-B0h]
  char **v36; // [rsp+60h] [rbp-A8h]
  _BYTE v37[64]; // [rsp+70h] [rbp-98h] BYREF

  v8 = (char *)a3;
  v9 = Size;
  v10 = a4;
  v35 = (char *)a3;
  v36 = a2;
  if ( (a7 & 0xFFFFFE5F) != 0 )
  {
    v24 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
        219);
    goto LABEL_31;
  }
  if ( !a1 || a1[1] != 1297306433 )
  {
    v24 = -1073741816;
LABEL_31:
    SymCryptWipeAsm(v8, v10);
    return (unsigned int)v24;
  }
  if ( !a3 )
  {
    v24 = -1073741811;
    goto LABEL_31;
  }
  if ( (a7 & 0x20) != 0 && (a1[2] != 65538 || a1[3] != 5) )
  {
    v26 = 498;
    goto LABEL_77;
  }
  if ( a4 >= 0xC80 )
    v10 = 3200;
  if ( v10 < a1[7] && (a1[2] != 65538 || a1[3] != 5 || v10 < 0x250) )
  {
    v24 = -1073741789;
    goto LABEL_31;
  }
  *(_DWORD *)a3 = v10;
  *(_DWORD *)(a3 + 4) = 1297306443;
  *(_DWORD *)(a3 + 8) = a1[2];
  *(_DWORD *)(a3 + 12) = a1[3];
  *(_DWORD *)(a3 + 16) = a1[4];
  *(_DWORD *)(a3 + 20) = a1[5];
  *(_DWORD *)(a3 + 24) = a1[6];
  *(_DWORD *)(a3 + 28) = 0;
  *(_QWORD *)(a3 + 32) = a1;
  v11 = a1[2];
  v12 = 112LL * ((unsigned int)(unsigned __int16)v11 - 1);
  if ( (a7 & 0x80u) == 0 )
  {
    if ( (unsigned int)Size >= *(_DWORD *)((char *)qword_1800AC078 + v12 + 4) )
      v9 = *(_DWORD *)((char *)qword_1800AC078 + v12 + 4);
  }
  else if ( (unsigned int)Size > *(_DWORD *)((char *)&qword_1800AC078[1] + v12 + 4) )
  {
    goto LABEL_48;
  }
  v13 = *(_DWORD *)((char *)qword_1800AC078 + v12);
  if ( v9 < v13
    || (LODWORD(a3) = *(_DWORD *)((char *)&qword_1800AC078[1] + v12), (_DWORD)a3)
    && (LODWORD(v12) = (v9 - v13) % (unsigned int)a3, (_DWORD)v12) )
  {
LABEL_48:
    v24 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v12,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
        49);
    goto LABEL_31;
  }
  if ( (a7 & 0x100) != 0
    && (v11 != 65544 || g_fSelftest && !memcmp(Src, &Src[(unsigned __int64)v9 >> 1], (unsigned __int64)v9 >> 1)) )
  {
    v26 = 572;
LABEL_77:
    v24 = -1073741811;
    v27 = 3221225485LL;
LABEL_60:
    DebugTraceError(v27, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c", v26);
    goto LABEL_31;
  }
  *((_DWORD *)v8 + 14) = v9;
  memmove(v8 + 60, Src, v9);
  *((_DWORD *)v8 + 6) = 8 * v9;
  v15 = v8 + 40;
  *(_OWORD *)(v8 + 40) = 0;
  v16 = a1[2];
  if ( v16 != 65538 )
  {
    switch ( v16 )
    {
      case 65537:
        v18 = SymCryptRc4Init(v8 + 320, v8 + 60, *((unsigned int *)v8 + 14));
        goto LABEL_34;
      case 65539:
        v28 = *((unsigned int *)v8 + 14);
        *((_DWORD *)v8 + 6) = 56;
        v18 = SymCryptDesExpandKey(v8 + 80, v8 + 60, v28);
        goto LABEL_34;
      case 65540:
        v29 = *((unsigned int *)v8 + 14);
        *((_DWORD *)v8 + 6) = 184;
        v18 = SymCryptDesxExpandKey(v8 + 96, v8 + 60, v29);
        goto LABEL_34;
      case 65541:
        v30 = *((unsigned int *)v8 + 14);
        *((_DWORD *)v8 + 6) = 168;
        v18 = SymCrypt3DesExpandKey(v8 + 96, v8 + 60, v30);
        goto LABEL_34;
      case 65542:
        v31 = *((unsigned int *)v8 + 14);
        *((_DWORD *)v8 + 6) = 112;
        v18 = SymCrypt3DesExpandKey(v8 + 80, v8 + 60, v31);
        goto LABEL_34;
      case 65543:
        *((_DWORD *)v8 + 84) = a1[9];
        *((_DWORD *)v8 + 6) = a1[9];
        v18 = SymCryptRc2ExpandKeyEx(v8 + 192);
        goto LABEL_34;
      case 65544:
        *((_DWORD *)v8 + 6) >>= 1;
        v18 = SymCryptXtsAesExpandKey(v8 + 128, v8 + 60, *((unsigned int *)v8 + 14));
        goto LABEL_34;
      case 65545:
        goto LABEL_35;
      default:
        v24 = -1073741637;
        v26 = 742;
        v27 = 3221225659LL;
        goto LABEL_60;
    }
  }
  LOBYTE(v14) = 1;
  v18 = SymCryptAesExpandKeyInternal(v8 + 96, v8 + 60, *((unsigned int *)v8 + 14), v14);
  if ( !v18 )
  {
    if ( *((_DWORD *)v8 + 3) != 5 )
      goto LABEL_34;
    if ( *(_DWORD *)v8 >= 0xC80u )
    {
      v20 = SymCryptGcmExpandKey(v8 + 592, SymCryptAesBlockCipher_Fast, v8 + 60, *((unsigned int *)v8 + 14));
      *((_DWORD *)v8 + 7) |= 1u;
      v18 = v20;
    }
  }
  if ( *((_DWORD *)v8 + 3) == 5 && (a7 & 0x20) != 0 )
  {
    *((_DWORD *)v8 + 7) |= 2u;
    v21 = 12;
    v33 = 0;
    v22 = 0;
    v34 = 0;
    CurrentIrql = KeGetCurrentIrql();
    if ( CurrentIrql < 2u )
    {
      v22 = (_BYTE *)BCryptAlloc(12);
      if ( !v22 )
        v22 = v37;
    }
    AesRNGState_select(&v33);
    do
    {
      v23 = 12;
      if ( v21 < 0xC )
        v23 = v21;
      if ( CurrentIrql < 2u )
      {
        v24 = AesRNGState_generate(v33, v22, v23, &v34);
        memmove(v15, v22, v23);
      }
      else
      {
        v24 = AesRNGState_generate(v33, v15, v23, &v34);
      }
      v15 += v23;
      v21 -= v23;
    }
    while ( v21 );
    if ( v22 && v22 != v37 )
      BCryptFree(v22);
    v8 = v35;
    if ( v24 < 0 )
      goto LABEL_31;
  }
LABEL_34:
  if ( v18 )
  {
    v24 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v17,
        v19,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
        238);
    goto LABEL_31;
  }
LABEL_35:
  if ( v36 )
    *v36 = v8;
  return 0;
}

```

## disassembly

```asm
0x180023f00  push    rbx
0x180023f02  push    rbp
0x180023f03  push    rsi
0x180023f04  push    rdi
0x180023f05  push    r12
0x180023f07  push    r13
0x180023f09  push    r14
0x180023f0b  push    r15
0x180023f0d  sub     rsp, 0C8h
0x180023f14  mov     rax, cs:__security_cookie
0x180023f1b  xor     rax, rsp
0x180023f1e  mov     [rsp+108h+var_58], rax
0x180023f26  mov     r13, [rsp+108h+Src]
0x180023f2e  mov     rsi, rcx
0x180023f31  mov     ecx, [rsp+108h+arg_30]
0x180023f38  mov     rbx, r8
0x180023f3b  mov     ebp, dword ptr [rsp+108h+Size]
0x180023f42  mov     edi, r9d
0x180023f45  mov     [rsp+108h+var_B0], rbx
0x180023f4a  mov     [rsp+108h+var_A8], rdx
0x180023f4f  test    ecx, 0FFFFFE5Fh
0x180023f55  jnz     loc_180024236
0x180023f5b  test    rsi, rsi
0x180023f5e  jz      loc_180024358
0x180023f64  cmp     dword ptr [rsi+4], 4D535341h
0x180023f6b  jnz     loc_180024358
0x180023f71  test    rbx, rbx
0x180023f74  jz      loc_180024363
0x180023f7a  mov     r14d, ecx
0x180023f7d  and     r14d, 20h
0x180023f81  jnz     loc_18002436E
0x180023f87  mov     eax, 0C80h
0x180023f8c  cmp     edi, eax
0x180023f8e  cmovnb  edi, eax
0x180023f91  cmp     edi, [rsi+1Ch]
0x180023f94  jb      loc_1800243B3
0x180023f9a  mov     [r8], edi
0x180023f9d  lea     r12, cs:180000000h
0x180023fa4  mov     dword ptr [r8+4], 4D53534Bh
0x180023fac  mov     eax, [rsi+8]
0x180023faf  mov     [r8+8], eax
0x180023fb3  mov     eax, [rsi+0Ch]
0x180023fb6  mov     [r8+0Ch], eax
0x180023fba  mov     eax, [rsi+10h]
0x180023fbd  mov     [r8+10h], eax
0x180023fc1  mov     eax, [rsi+14h]
0x180023fc4  mov     [r8+14h], eax
0x180023fc8  mov     eax, [rsi+18h]
0x180023fcb  mov     [r8+18h], eax
0x180023fcf  mov     dword ptr [r8+1Ch], 0
0x180023fd7  mov     [r8+20h], rsi
0x180023fdb  mov     r10d, [rsi+8]
0x180023fdf  movzx   eax, r10w
0x180023fe3  dec     eax
0x180023fe5  imul    rdx, rax, 70h ; 'p'
0x180023fe9  test    cl, cl
0x180023feb  jns     loc_18002428F
0x180023ff1  mov     eax, [rdx+r12+0AC084h]
0x180023ff9  cmp     ebp, eax
0x180023ffb  ja      loc_1800242A6
0x180024001  mov     r9d, [rdx+r12+0AC078h]
0x180024009  cmp     ebp, r9d
0x18002400c  jb      loc_1800242A6
0x180024012  mov     r8d, [rdx+r12+0AC080h]
0x18002401a  test    r8d, r8d
0x18002401d  jz      short loc_180024031
0x18002401f  xor     edx, edx
0x180024021  mov     eax, ebp
0x180024023  sub     eax, r9d
0x180024026  div     r8d
0x180024029  test    edx, edx
0x18002402b  jnz     loc_1800242A6
0x180024031  bt      ecx, 8
0x180024035  jb      loc_1800243DB
0x18002403b  mov     r8d, ebp; Size
0x18002403e  lea     rcx, [rbx+3Ch]; void *
0x180024042  mov     rdx, r13; Src
0x180024045  mov     [rbx+38h], ebp
0x180024048  call    memmove
0x18002404d  lea     eax, ds:0[rbp*8]
0x180024054  xorps   xmm0, xmm0
0x180024057  mov     [rbx+18h], eax
0x18002405a  lea     r13, [rbx+28h]
0x18002405e  movups  xmmword ptr [r13+0], xmm0
0x180024063  mov     eax, [rsi+8]
0x180024066  cmp     eax, 10002h
0x18002406b  jnz     loc_18002416E
0x180024071  mov     r8d, [rbx+38h]
0x180024075  lea     rcx, [rbx+60h]
0x180024079  mov     r9b, 1
0x18002407c  lea     rdx, [rbx+3Ch]
0x180024080  call    SymCryptAesExpandKeyInternal
0x180024085  mov     esi, eax
0x180024087  test    eax, eax
0x180024089  jnz     short loc_1800240BE
0x18002408b  cmp     dword ptr [rbx+0Ch], 5
0x18002408f  jnz     loc_1800241A3
0x180024095  cmp     dword ptr [rbx], 0C80h
0x18002409b  jb      short loc_1800240BE
0x18002409d  mov     r9d, [rbx+38h]
0x1800240a1  lea     rcx, [rbx+250h]
0x1800240a8  lea     r8, [rbx+3Ch]
0x1800240ac  lea     rdx, SymCryptAesBlockCipher_Fast
0x1800240b3  call    SymCryptGcmExpandKey
0x1800240b8  or      dword ptr [rbx+1Ch], 1
0x1800240bc  mov     esi, eax
0x1800240be  cmp     dword ptr [rbx+0Ch], 5
0x1800240c2  jnz     loc_1800241A3
0x1800240c8  test    r14d, r14d
0x1800240cb  jz      loc_1800241A3
0x1800240d1  or      dword ptr [rbx+1Ch], 2
0x1800240d5  mov     r14d, 0Ch
0x1800240db  mov     [rsp+108h+var_C0], 0
0x1800240e4  xor     r15d, r15d
0x1800240e7  mov     [rsp+108h+var_B8], 0
0x1800240f0  call    cs:__imp_KeGetCurrentIrql
0x1800240f7  nop     dword ptr [rax+rax+00h]
0x1800240fc  mov     [rsp+108h+var_C8], al
0x180024100  cmp     al, 2
0x180024102  jb      loc_180024218
0x180024108  lea     rcx, [rsp+108h+var_C0]
0x18002410d  call    AesRNGState_select
0x180024112  movzx   ebx, [rsp+108h+var_C8]
0x180024117  mov     rcx, [rsp+108h+var_C0]
0x18002411c  lea     r9, [rsp+108h+var_B8]
0x180024121  mov     ebp, 0Ch
0x180024126  cmp     r14, rbp
0x180024129  cmovb   rbp, r14
0x18002412d  mov     r8, rbp
0x180024130  cmp     bl, 2
0x180024133  jb      loc_1800241FA
0x180024139  mov     rdx, r13
0x18002413c  call    AesRNGState_generate
0x180024141  mov     r12d, eax
0x180024144  add     r13, rbp
0x180024147  sub     r14, rbp
0x18002414a  jnz     short loc_180024117
0x18002414c  test    r15, r15
0x18002414f  jnz     loc_1800241DF
0x180024155  mov     rbx, [rsp+108h+var_B0]
0x18002415a  test    r12d, r12d
0x18002415d  jns     short loc_1800241A3
0x18002415f  mov     edx, edi
0x180024161  mov     rcx, rbx
0x180024164  call    SymCryptWipeAsm
0x180024169  mov     eax, r12d
0x18002416c  jmp     short loc_1800241BA
0x18002416e  add     eax, 0FFFEFFFFh; switch 9 cases
0x180024173  cmp     eax, 8
0x180024176  ja      def_180024187; jumptable 0000000180024187 default case, case 65538
0x18002417c  mov     eax, ds:(jpt_180024187 - 180000000h)[r12+rax*4]
0x180024184  add     rax, r12
0x180024187  jmp     rax; switch jump
0x18002418d  mov     r8d, [rbx+38h]; jumptable 0000000180024187 case 65537
0x180024191  lea     rcx, [rbx+140h]
0x180024198  lea     rdx, [rbx+3Ch]
0x18002419c  call    SymCryptRc4Init
0x1800241a1  mov     esi, eax
0x1800241a3  test    esi, esi
0x1800241a5  jnz     loc_1800242FF
0x1800241ab  mov     rax, [rsp+108h+var_A8]; jumptable 0000000180024187 case 65545
0x1800241b0  test    rax, rax
0x1800241b3  jz      short loc_1800241B8
0x1800241b5  mov     [rax], rbx
0x1800241b8  xor     eax, eax
0x1800241ba  mov     rcx, [rsp+108h+var_58]
0x1800241c2  xor     rcx, rsp; StackCookie
0x1800241c5  call    __security_check_cookie
0x1800241ca  add     rsp, 0C8h
0x1800241d1  pop     r15
0x1800241d3  pop     r14
0x1800241d5  pop     r13
0x1800241d7  pop     r12
0x1800241d9  pop     rdi
0x1800241da  pop     rsi
0x1800241db  pop     rbp
0x1800241dc  pop     rbx
0x1800241dd  retn
0x1800241df  lea     rax, [rsp+108h+var_98]
0x1800241e4  cmp     r15, rax
0x1800241e7  jz      loc_180024155
0x1800241ed  mov     rcx, r15; P
0x1800241f0  call    BCryptFree
0x1800241f5  jmp     loc_180024155
0x1800241fa  mov     rdx, r15
0x1800241fd  call    AesRNGState_generate
0x180024202  mov     r8, rbp; Size
0x180024205  mov     rdx, r15; Src
0x180024208  mov     rcx, r13; void *
0x18002420b  mov     r12d, eax
0x18002420e  call    memmove
0x180024213  jmp     loc_180024144
0x180024218  mov     rcx, r14
0x18002421b  call    BCryptAlloc
0x180024220  mov     r15, rax
0x180024223  test    rax, rax
0x180024226  jnz     loc_180024108
0x18002422c  lea     r15, [rsp+108h+var_98]
0x180024231  jmp     loc_180024108
0x180024236  mov     r12d, 0C000000Dh
0x18002423c  mov     rcx, cs:WPP_GLOBAL_Control
0x180024243  lea     rax, WPP_GLOBAL_Control
0x18002424a  cmp     rcx, rax
0x18002424d  jz      loc_18002415F
0x180024253  mov     eax, [rcx+2Ch]
0x180024256  test    al, 1
0x180024258  jz      loc_18002415F
0x18002425e  mov     rcx, [rcx+18h]
0x180024262  lea     rax, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180024269  mov     [rsp+108h+var_D8], 1DBh
0x180024271  lea     r9, aStatus; "Status"
0x180024278  mov     [rsp+108h+var_E0], rax
0x18002427d  mov     [rsp+108h+var_E8], 0C000000Dh
0x180024285  call    WPP_SF_sDsd
0x18002428a  jmp     loc_18002415F
0x18002428f  mov     eax, [rdx+r12+0AC07Ch]
0x180024297  cmp     ebp, eax
0x180024299  jb      loc_180024001
0x18002429f  mov     ebp, eax
0x1800242a1  jmp     loc_180024001
0x1800242a6  mov     r12d, 0C000000Dh
0x1800242ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800242b3  lea     rax, WPP_GLOBAL_Control
0x1800242ba  cmp     rcx, rax
0x1800242bd  jz      loc_18002415F
0x1800242c3  mov     eax, [rcx+2Ch]
0x1800242c6  test    al, 1
0x1800242c8  jz      loc_18002415F
0x1800242ce  mov     rcx, [rcx+18h]
0x1800242d2  lea     rax, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800242d9  mov     [rsp+108h+var_D8], 231h
0x1800242e1  lea     r9, aStatus; "Status"
0x1800242e8  mov     [rsp+108h+var_E0], rax
0x1800242ed  mov     [rsp+108h+var_E8], 0C000000Dh
0x1800242f5  call    WPP_SF_sDsd
0x1800242fa  jmp     loc_18002415F
0x1800242ff  mov     r12d, 0C000000Dh
0x180024305  mov     rcx, cs:WPP_GLOBAL_Control
0x18002430c  lea     rax, WPP_GLOBAL_Control
0x180024313  cmp     rcx, rax
0x180024316  jz      loc_18002415F
0x18002431c  mov     eax, [rcx+2Ch]
0x18002431f  test    al, 1
0x180024321  jz      loc_18002415F
0x180024327  mov     rcx, [rcx+18h]
0x18002432b  lea     rax, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180024332  mov     [rsp+108h+var_D8], 2EEh
0x18002433a  lea     r9, aStatus; "Status"
0x180024341  mov     [rsp+108h+var_E0], rax
0x180024346  mov     [rsp+108h+var_E8], 0C000000Dh
0x18002434e  call    WPP_SF_sDsd
0x180024353  jmp     loc_18002415F
0x180024358  mov     r12d, 0C0000008h
0x18002435e  jmp     loc_18002415F
0x180024363  mov     r12d, 0C000000Dh
0x180024369  jmp     loc_18002415F
0x18002436e  cmp     dword ptr [rsi+8], 10002h
0x180024375  jnz     loc_1800A6A3E
0x18002437b  cmp     dword ptr [rsi+0Ch], 5
0x18002437f  jz      loc_180023F87
0x180024385  jmp     loc_1800A6A3E
0x18002438a  mov     r12d, 0C00000BBh; jumptable 0000000180024187 default case, case 65538
0x180024390  mov     r9d, 2E6h
0x180024396  mov     ecx, 0C00000BBh
0x18002439b  lea     rdx, aStatus; "Status"
0x1800243a2  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800243a9  call    DebugTraceError
0x1800243ae  jmp     loc_18002415F
0x1800243b3  cmp     dword ptr [rsi+8], 10002h
0x1800243ba  jnz     loc_1800A6A5C
0x1800243c0  cmp     dword ptr [rsi+0Ch], 5
0x1800243c4  jnz     loc_1800A6A5C
0x1800243ca  cmp     edi, 250h
0x1800243d0  jnb     loc_180023F9A
0x1800243d6  jmp     loc_1800A6A5C
0x1800243db  cmp     r10d, 10008h
0x1800243e2  jnz     loc_1800A6A46
0x1800243e8  cmp     cs:g_fSelftest, 0
0x1800243ef  jz      loc_18002403B
0x1800243f5  mov     r8d, ebp
0x1800243f8  mov     rcx, r13; Buf1
0x1800243fb  shr     r8, 1; Size
0x1800243fe  lea     rdx, [r8+r13]; Buf2
0x180024402  call    memcmp
0x180024407  test    eax, eax
0x180024409  jnz     loc_18002403B
0x18002440f  jmp     loc_1800A6A46
0x180024414  mov     r8d, [rbx+38h]; jumptable 0000000180024187 case 65539
0x180024418  lea     rcx, [rbx+50h]
0x18002441c  lea     rdx, [rbx+3Ch]
0x180024420  mov     dword ptr [rbx+18h], 38h ; '8'
0x180024427  call    SymCryptDesExpandKey
0x18002442c  mov     esi, eax
0x18002442e  jmp     loc_1800241A3
0x180024433  mov     r8d, [rbx+38h]; jumptable 0000000180024187 case 65540
0x180024437  lea     rcx, [rbx+60h]
0x18002443b  lea     rdx, [rbx+3Ch]
0x18002443f  mov     dword ptr [rbx+18h], 0B8h
0x180024446  call    SymCryptDesxExpandKey
0x18002444b  mov     esi, eax
  ... truncated ...
```

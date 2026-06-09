# MSCryptGenerateSymmetricKey

- ea: `0x180016e80`
- end: `0x18001745a`
- name: `MSCryptGenerateSymmetricKey`
- size: `1498`
- prototype: `__int64 __fastcall(int, int, int, int, void *Src, size_t Size, int)`
- caller_count: `4`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x180014070`
- `0x180014da0`
- `0x1800169d0`
- `0x18007f0f8`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x18000cc90`
- `0x180016e80`
- `0x180017480`
- `0x180017d20`
- `0x1800182e0`
- `0x180018680`
- `0x180018e40`
- `0x180018f30`
- `0x18003d208`
- `0x18004cc10`
- `0x180064960`
- `0x1800878bc`
- `0x180096230`
- `0x180096480`
- `0x18009f650`
- `0x18009f780`
- `0x18009ffa0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180017070`
- `ntoskrnl!KeGetCurrentIrql` at `0x180017070`

## string_xrefs

- `0x1800171e2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180017252`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x1800172ab`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180017322`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`

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
        218);
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
    v26 = 497;
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
    if ( (unsigned int)Size >= *(_DWORD *)((char *)qword_1800A7078 + v12 + 4) )
      v9 = *(_DWORD *)((char *)qword_1800A7078 + v12 + 4);
  }
  else if ( (unsigned int)Size > *(_DWORD *)((char *)&qword_1800A7078[1] + v12 + 4) )
  {
    goto LABEL_48;
  }
  v13 = *(_DWORD *)((char *)qword_1800A7078 + v12);
  if ( v9 < v13
    || (LODWORD(a3) = *(_DWORD *)((char *)&qword_1800A7078[1] + v12), (_DWORD)a3)
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
        48);
    goto LABEL_31;
  }
  if ( (a7 & 0x100) != 0
    && (v11 != 65544 || g_fSelftest && !memcmp(Src, &Src[(unsigned __int64)v9 >> 1], (unsigned __int64)v9 >> 1)) )
  {
    v26 = 571;
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
        v26 = 741;
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
        237);
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
0x180016e80  push    rbx
0x180016e82  push    rbp
0x180016e83  push    rsi
0x180016e84  push    rdi
0x180016e85  push    r12
0x180016e87  push    r13
0x180016e89  push    r14
0x180016e8b  push    r15
0x180016e8d  sub     rsp, 0C8h
0x180016e94  mov     rax, cs:__security_cookie
0x180016e9b  xor     rax, rsp
0x180016e9e  mov     [rsp+108h+var_58], rax
0x180016ea6  mov     r13, [rsp+108h+Src]
0x180016eae  mov     rsi, rcx
0x180016eb1  mov     ecx, [rsp+108h+arg_30]
0x180016eb8  mov     rbx, r8
0x180016ebb  mov     ebp, dword ptr [rsp+108h+Size]
0x180016ec2  mov     edi, r9d
0x180016ec5  mov     [rsp+108h+var_B0], rbx
0x180016eca  mov     [rsp+108h+var_A8], rdx
0x180016ecf  test    ecx, 0FFFFFE5Fh
0x180016ed5  jnz     loc_1800171B6
0x180016edb  test    rsi, rsi
0x180016ede  jz      loc_1800172D8
0x180016ee4  cmp     dword ptr [rsi+4], 4D535341h
0x180016eeb  jnz     loc_1800172D8
0x180016ef1  test    rbx, rbx
0x180016ef4  jz      loc_1800172E3
0x180016efa  mov     r14d, ecx
0x180016efd  and     r14d, 20h
0x180016f01  jnz     loc_1800172EE
0x180016f07  mov     eax, 0C80h
0x180016f0c  cmp     edi, eax
0x180016f0e  cmovnb  edi, eax
0x180016f11  cmp     edi, [rsi+1Ch]
0x180016f14  jb      loc_180017333
0x180016f1a  mov     [r8], edi
0x180016f1d  lea     r12, cs:180000000h
0x180016f24  mov     dword ptr [r8+4], 4D53534Bh
0x180016f2c  mov     eax, [rsi+8]
0x180016f2f  mov     [r8+8], eax
0x180016f33  mov     eax, [rsi+0Ch]
0x180016f36  mov     [r8+0Ch], eax
0x180016f3a  mov     eax, [rsi+10h]
0x180016f3d  mov     [r8+10h], eax
0x180016f41  mov     eax, [rsi+14h]
0x180016f44  mov     [r8+14h], eax
0x180016f48  mov     eax, [rsi+18h]
0x180016f4b  mov     [r8+18h], eax
0x180016f4f  mov     dword ptr [r8+1Ch], 0
0x180016f57  mov     [r8+20h], rsi
0x180016f5b  mov     r10d, [rsi+8]
0x180016f5f  movzx   eax, r10w
0x180016f63  dec     eax
0x180016f65  imul    rdx, rax, 70h ; 'p'
0x180016f69  test    cl, cl
0x180016f6b  jns     loc_18001720F
0x180016f71  mov     eax, [rdx+r12+0A7084h]
0x180016f79  cmp     ebp, eax
0x180016f7b  ja      loc_180017226
0x180016f81  mov     r9d, [rdx+r12+0A7078h]
0x180016f89  cmp     ebp, r9d
0x180016f8c  jb      loc_180017226
0x180016f92  mov     r8d, [rdx+r12+0A7080h]
0x180016f9a  test    r8d, r8d
0x180016f9d  jz      short loc_180016FB1
0x180016f9f  xor     edx, edx
0x180016fa1  mov     eax, ebp
0x180016fa3  sub     eax, r9d
0x180016fa6  div     r8d
0x180016fa9  test    edx, edx
0x180016fab  jnz     loc_180017226
0x180016fb1  bt      ecx, 8
0x180016fb5  jb      loc_18001735B
0x180016fbb  mov     r8d, ebp; Size
0x180016fbe  lea     rcx, [rbx+3Ch]; void *
0x180016fc2  mov     rdx, r13; Src
0x180016fc5  mov     [rbx+38h], ebp
0x180016fc8  call    memmove
0x180016fcd  lea     eax, ds:0[rbp*8]
0x180016fd4  xorps   xmm0, xmm0
0x180016fd7  mov     [rbx+18h], eax
0x180016fda  lea     r13, [rbx+28h]
0x180016fde  movups  xmmword ptr [r13+0], xmm0
0x180016fe3  mov     eax, [rsi+8]
0x180016fe6  cmp     eax, 10002h
0x180016feb  jnz     loc_1800170EE
0x180016ff1  mov     r8d, [rbx+38h]
0x180016ff5  lea     rcx, [rbx+60h]
0x180016ff9  mov     r9b, 1
0x180016ffc  lea     rdx, [rbx+3Ch]
0x180017000  call    SymCryptAesExpandKeyInternal
0x180017005  mov     esi, eax
0x180017007  test    eax, eax
0x180017009  jnz     short loc_18001703E
0x18001700b  cmp     dword ptr [rbx+0Ch], 5
0x18001700f  jnz     loc_180017123
0x180017015  cmp     dword ptr [rbx], 0C80h
0x18001701b  jb      short loc_18001703E
0x18001701d  mov     r9d, [rbx+38h]
0x180017021  lea     rcx, [rbx+250h]
0x180017028  lea     r8, [rbx+3Ch]
0x18001702c  lea     rdx, SymCryptAesBlockCipher_Fast
0x180017033  call    SymCryptGcmExpandKey
0x180017038  or      dword ptr [rbx+1Ch], 1
0x18001703c  mov     esi, eax
0x18001703e  cmp     dword ptr [rbx+0Ch], 5
0x180017042  jnz     loc_180017123
0x180017048  test    r14d, r14d
0x18001704b  jz      loc_180017123
0x180017051  or      dword ptr [rbx+1Ch], 2
0x180017055  mov     r14d, 0Ch
0x18001705b  mov     [rsp+108h+var_C0], 0
0x180017064  xor     r15d, r15d
0x180017067  mov     [rsp+108h+var_B8], 0
0x180017070  call    cs:__imp_KeGetCurrentIrql
0x180017077  nop     dword ptr [rax+rax+00h]
0x18001707c  mov     [rsp+108h+var_C8], al
0x180017080  cmp     al, 2
0x180017082  jb      loc_180017198
0x180017088  lea     rcx, [rsp+108h+var_C0]
0x18001708d  call    AesRNGState_select
0x180017092  movzx   ebx, [rsp+108h+var_C8]
0x180017097  mov     rcx, [rsp+108h+var_C0]
0x18001709c  lea     r9, [rsp+108h+var_B8]
0x1800170a1  mov     ebp, 0Ch
0x1800170a6  cmp     r14, rbp
0x1800170a9  cmovb   rbp, r14
0x1800170ad  mov     r8, rbp
0x1800170b0  cmp     bl, 2
0x1800170b3  jb      loc_18001717A
0x1800170b9  mov     rdx, r13
0x1800170bc  call    AesRNGState_generate
0x1800170c1  mov     r12d, eax
0x1800170c4  add     r13, rbp
0x1800170c7  sub     r14, rbp
0x1800170ca  jnz     short loc_180017097
0x1800170cc  test    r15, r15
0x1800170cf  jnz     loc_18001715F
0x1800170d5  mov     rbx, [rsp+108h+var_B0]
0x1800170da  test    r12d, r12d
0x1800170dd  jns     short loc_180017123
0x1800170df  mov     edx, edi
0x1800170e1  mov     rcx, rbx
0x1800170e4  call    SymCryptWipeAsm
0x1800170e9  mov     eax, r12d
0x1800170ec  jmp     short loc_18001713A
0x1800170ee  add     eax, 0FFFEFFFFh; switch 9 cases
0x1800170f3  cmp     eax, 8
0x1800170f6  ja      def_180017107; jumptable 0000000180017107 default case, case 65538
0x1800170fc  mov     eax, ds:(jpt_180017107 - 180000000h)[r12+rax*4]
0x180017104  add     rax, r12
0x180017107  jmp     rax; switch jump
0x18001710d  mov     r8d, [rbx+38h]; jumptable 0000000180017107 case 65537
0x180017111  lea     rcx, [rbx+140h]
0x180017118  lea     rdx, [rbx+3Ch]
0x18001711c  call    SymCryptRc4Init
0x180017121  mov     esi, eax
0x180017123  test    esi, esi
0x180017125  jnz     loc_18001727F
0x18001712b  mov     rax, [rsp+108h+var_A8]; jumptable 0000000180017107 case 65545
0x180017130  test    rax, rax
0x180017133  jz      short loc_180017138
0x180017135  mov     [rax], rbx
0x180017138  xor     eax, eax
0x18001713a  mov     rcx, [rsp+108h+var_58]
0x180017142  xor     rcx, rsp; StackCookie
0x180017145  call    __security_check_cookie
0x18001714a  add     rsp, 0C8h
0x180017151  pop     r15
0x180017153  pop     r14
0x180017155  pop     r13
0x180017157  pop     r12
0x180017159  pop     rdi
0x18001715a  pop     rsi
0x18001715b  pop     rbp
0x18001715c  pop     rbx
0x18001715d  retn
0x18001715f  lea     rax, [rsp+108h+var_98]
0x180017164  cmp     r15, rax
0x180017167  jz      loc_1800170D5
0x18001716d  mov     rcx, r15; P
0x180017170  call    BCryptFree
0x180017175  jmp     loc_1800170D5
0x18001717a  mov     rdx, r15
0x18001717d  call    AesRNGState_generate
0x180017182  mov     r8, rbp; Size
0x180017185  mov     rdx, r15; Src
0x180017188  mov     rcx, r13; void *
0x18001718b  mov     r12d, eax
0x18001718e  call    memmove
0x180017193  jmp     loc_1800170C4
0x180017198  mov     rcx, r14
0x18001719b  call    BCryptAlloc
0x1800171a0  mov     r15, rax
0x1800171a3  test    rax, rax
0x1800171a6  jnz     loc_180017088
0x1800171ac  lea     r15, [rsp+108h+var_98]
0x1800171b1  jmp     loc_180017088
0x1800171b6  mov     r12d, 0C000000Dh
0x1800171bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800171c3  lea     rax, WPP_GLOBAL_Control
0x1800171ca  cmp     rcx, rax
0x1800171cd  jz      loc_1800170DF
0x1800171d3  mov     eax, [rcx+2Ch]
0x1800171d6  test    al, 1
0x1800171d8  jz      loc_1800170DF
0x1800171de  mov     rcx, [rcx+18h]
0x1800171e2  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800171e9  mov     [rsp+108h+var_D8], 1DAh
0x1800171f1  lea     r9, aStatus; "Status"
0x1800171f8  mov     [rsp+108h+var_E0], rax
0x1800171fd  mov     [rsp+108h+var_E8], 0C000000Dh
0x180017205  call    WPP_SF_sDsd
0x18001720a  jmp     loc_1800170DF
0x18001720f  mov     eax, [rdx+r12+0A707Ch]
0x180017217  cmp     ebp, eax
0x180017219  jb      loc_180016F81
0x18001721f  mov     ebp, eax
0x180017221  jmp     loc_180016F81
0x180017226  mov     r12d, 0C000000Dh
0x18001722c  mov     rcx, cs:WPP_GLOBAL_Control
0x180017233  lea     rax, WPP_GLOBAL_Control
0x18001723a  cmp     rcx, rax
0x18001723d  jz      loc_1800170DF
0x180017243  mov     eax, [rcx+2Ch]
0x180017246  test    al, 1
0x180017248  jz      loc_1800170DF
0x18001724e  mov     rcx, [rcx+18h]
0x180017252  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180017259  mov     [rsp+108h+var_D8], 230h
0x180017261  lea     r9, aStatus; "Status"
0x180017268  mov     [rsp+108h+var_E0], rax
0x18001726d  mov     [rsp+108h+var_E8], 0C000000Dh
0x180017275  call    WPP_SF_sDsd
0x18001727a  jmp     loc_1800170DF
0x18001727f  mov     r12d, 0C000000Dh
0x180017285  mov     rcx, cs:WPP_GLOBAL_Control
0x18001728c  lea     rax, WPP_GLOBAL_Control
0x180017293  cmp     rcx, rax
0x180017296  jz      loc_1800170DF
0x18001729c  mov     eax, [rcx+2Ch]
0x18001729f  test    al, 1
0x1800172a1  jz      loc_1800170DF
0x1800172a7  mov     rcx, [rcx+18h]
0x1800172ab  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800172b2  mov     [rsp+108h+var_D8], 2EDh
0x1800172ba  lea     r9, aStatus; "Status"
0x1800172c1  mov     [rsp+108h+var_E0], rax
0x1800172c6  mov     [rsp+108h+var_E8], 0C000000Dh
0x1800172ce  call    WPP_SF_sDsd
0x1800172d3  jmp     loc_1800170DF
0x1800172d8  mov     r12d, 0C0000008h
0x1800172de  jmp     loc_1800170DF
0x1800172e3  mov     r12d, 0C000000Dh
0x1800172e9  jmp     loc_1800170DF
0x1800172ee  cmp     dword ptr [rsi+8], 10002h
0x1800172f5  jnz     loc_1800A1856
0x1800172fb  cmp     dword ptr [rsi+0Ch], 5
0x1800172ff  jz      loc_180016F07
0x180017305  jmp     loc_1800A1856
0x18001730a  mov     r12d, 0C00000BBh; jumptable 0000000180017107 default case, case 65538
0x180017310  mov     r9d, 2E5h
0x180017316  mov     ecx, 0C00000BBh
0x18001731b  lea     rdx, aStatus; "Status"
0x180017322  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180017329  call    DebugTraceError
0x18001732e  jmp     loc_1800170DF
0x180017333  cmp     dword ptr [rsi+8], 10002h
0x18001733a  jnz     loc_1800A1874
0x180017340  cmp     dword ptr [rsi+0Ch], 5
0x180017344  jnz     loc_1800A1874
0x18001734a  cmp     edi, 250h
0x180017350  jnb     loc_180016F1A
0x180017356  jmp     loc_1800A1874
0x18001735b  cmp     r10d, 10008h
0x180017362  jnz     loc_1800A185E
0x180017368  cmp     cs:g_fSelftest, 0
0x18001736f  jz      loc_180016FBB
0x180017375  mov     r8d, ebp
0x180017378  mov     rcx, r13; Buf1
0x18001737b  shr     r8, 1; Size
0x18001737e  lea     rdx, [r8+r13]; Buf2
0x180017382  call    memcmp
0x180017387  test    eax, eax
0x180017389  jnz     loc_180016FBB
0x18001738f  jmp     loc_1800A185E
0x180017394  mov     r8d, [rbx+38h]; jumptable 0000000180017107 case 65539
0x180017398  lea     rcx, [rbx+50h]
0x18001739c  lea     rdx, [rbx+3Ch]
0x1800173a0  mov     dword ptr [rbx+18h], 38h ; '8'
0x1800173a7  call    SymCryptDesExpandKey
0x1800173ac  mov     esi, eax
0x1800173ae  jmp     loc_180017123
0x1800173b3  mov     r8d, [rbx+38h]; jumptable 0000000180017107 case 65540
0x1800173b7  lea     rcx, [rbx+60h]
0x1800173bb  lea     rdx, [rbx+3Ch]
0x1800173bf  mov     dword ptr [rbx+18h], 0B8h
0x1800173c6  call    SymCryptDesxExpandKey
0x1800173cb  mov     esi, eax
  ... truncated ...
```

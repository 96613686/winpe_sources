# MSCryptGenerateSymmetricKey

- ea: `0x180019dd0`
- end: `0x18001a3aa`
- name: `MSCryptGenerateSymmetricKey`
- size: `1498`
- prototype: `__int64 __fastcall(int, int, int, int, void *Src, size_t Size, int)`
- caller_count: `4`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x180016fc0`
- `0x180017cf0`
- `0x180019920`
- `0x18007e108`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x18000cc90`
- `0x180019dd0`
- `0x18001a3d0`
- `0x18001ac70`
- `0x18001b230`
- `0x18001b5d0`
- `0x18001bd90`
- `0x18001be80`
- `0x18003c708`
- `0x18004c3d0`
- `0x180063fe0`
- `0x1800868ac`
- `0x1800947d0`
- `0x180094a20`
- `0x18009d820`
- `0x18009d920`
- `0x18009da40`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180019fc0`
- `ntoskrnl!KeGetCurrentIrql` at `0x180019fc0`

## string_xrefs

- `0x18001a132`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18001a1a2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18001a1fb`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18001a272`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`

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
    if ( (unsigned int)Size >= *(_DWORD *)((char *)qword_1800A5078 + v12 + 4) )
      v9 = *(_DWORD *)((char *)qword_1800A5078 + v12 + 4);
  }
  else if ( (unsigned int)Size > *(_DWORD *)((char *)&qword_1800A5078[1] + v12 + 4) )
  {
    goto LABEL_48;
  }
  v13 = *(_DWORD *)((char *)qword_1800A5078 + v12);
  if ( v9 < v13
    || (LODWORD(a3) = *(_DWORD *)((char *)&qword_1800A5078[1] + v12), (_DWORD)a3)
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
0x180019dd0  push    rbx
0x180019dd2  push    rbp
0x180019dd3  push    rsi
0x180019dd4  push    rdi
0x180019dd5  push    r12
0x180019dd7  push    r13
0x180019dd9  push    r14
0x180019ddb  push    r15
0x180019ddd  sub     rsp, 0C8h
0x180019de4  mov     rax, cs:__security_cookie
0x180019deb  xor     rax, rsp
0x180019dee  mov     [rsp+108h+var_58], rax
0x180019df6  mov     r13, [rsp+108h+Src]
0x180019dfe  mov     rsi, rcx
0x180019e01  mov     ecx, [rsp+108h+arg_30]
0x180019e08  mov     rbx, r8
0x180019e0b  mov     ebp, dword ptr [rsp+108h+Size]
0x180019e12  mov     edi, r9d
0x180019e15  mov     [rsp+108h+var_B0], rbx
0x180019e1a  mov     [rsp+108h+var_A8], rdx
0x180019e1f  test    ecx, 0FFFFFE5Fh
0x180019e25  jnz     loc_18001A106
0x180019e2b  test    rsi, rsi
0x180019e2e  jz      loc_18001A228
0x180019e34  cmp     dword ptr [rsi+4], 4D535341h
0x180019e3b  jnz     loc_18001A228
0x180019e41  test    rbx, rbx
0x180019e44  jz      loc_18001A233
0x180019e4a  mov     r14d, ecx
0x180019e4d  and     r14d, 20h
0x180019e51  jnz     loc_18001A23E
0x180019e57  mov     eax, 0C80h
0x180019e5c  cmp     edi, eax
0x180019e5e  cmovnb  edi, eax
0x180019e61  cmp     edi, [rsi+1Ch]
0x180019e64  jb      loc_18001A283
0x180019e6a  mov     [r8], edi
0x180019e6d  lea     r12, cs:180000000h
0x180019e74  mov     dword ptr [r8+4], 4D53534Bh
0x180019e7c  mov     eax, [rsi+8]
0x180019e7f  mov     [r8+8], eax
0x180019e83  mov     eax, [rsi+0Ch]
0x180019e86  mov     [r8+0Ch], eax
0x180019e8a  mov     eax, [rsi+10h]
0x180019e8d  mov     [r8+10h], eax
0x180019e91  mov     eax, [rsi+14h]
0x180019e94  mov     [r8+14h], eax
0x180019e98  mov     eax, [rsi+18h]
0x180019e9b  mov     [r8+18h], eax
0x180019e9f  mov     dword ptr [r8+1Ch], 0
0x180019ea7  mov     [r8+20h], rsi
0x180019eab  mov     r10d, [rsi+8]
0x180019eaf  movzx   eax, r10w
0x180019eb3  dec     eax
0x180019eb5  imul    rdx, rax, 70h ; 'p'
0x180019eb9  test    cl, cl
0x180019ebb  jns     loc_18001A15F
0x180019ec1  mov     eax, [rdx+r12+0A5084h]
0x180019ec9  cmp     ebp, eax
0x180019ecb  ja      loc_18001A176
0x180019ed1  mov     r9d, [rdx+r12+0A5078h]
0x180019ed9  cmp     ebp, r9d
0x180019edc  jb      loc_18001A176
0x180019ee2  mov     r8d, [rdx+r12+0A5080h]
0x180019eea  test    r8d, r8d
0x180019eed  jz      short loc_180019F01
0x180019eef  xor     edx, edx
0x180019ef1  mov     eax, ebp
0x180019ef3  sub     eax, r9d
0x180019ef6  div     r8d
0x180019ef9  test    edx, edx
0x180019efb  jnz     loc_18001A176
0x180019f01  bt      ecx, 8
0x180019f05  jb      loc_18001A2AB
0x180019f0b  mov     r8d, ebp; Size
0x180019f0e  lea     rcx, [rbx+3Ch]; void *
0x180019f12  mov     rdx, r13; Src
0x180019f15  mov     [rbx+38h], ebp
0x180019f18  call    memmove
0x180019f1d  lea     eax, ds:0[rbp*8]
0x180019f24  xorps   xmm0, xmm0
0x180019f27  mov     [rbx+18h], eax
0x180019f2a  lea     r13, [rbx+28h]
0x180019f2e  movups  xmmword ptr [r13+0], xmm0
0x180019f33  mov     eax, [rsi+8]
0x180019f36  cmp     eax, 10002h
0x180019f3b  jnz     loc_18001A03E
0x180019f41  mov     r8d, [rbx+38h]
0x180019f45  lea     rcx, [rbx+60h]
0x180019f49  mov     r9b, 1
0x180019f4c  lea     rdx, [rbx+3Ch]
0x180019f50  call    SymCryptAesExpandKeyInternal
0x180019f55  mov     esi, eax
0x180019f57  test    eax, eax
0x180019f59  jnz     short loc_180019F8E
0x180019f5b  cmp     dword ptr [rbx+0Ch], 5
0x180019f5f  jnz     loc_18001A073
0x180019f65  cmp     dword ptr [rbx], 0C80h
0x180019f6b  jb      short loc_180019F8E
0x180019f6d  mov     r9d, [rbx+38h]
0x180019f71  lea     rcx, [rbx+250h]
0x180019f78  lea     r8, [rbx+3Ch]
0x180019f7c  lea     rdx, SymCryptAesBlockCipher_Fast
0x180019f83  call    SymCryptGcmExpandKey
0x180019f88  or      dword ptr [rbx+1Ch], 1
0x180019f8c  mov     esi, eax
0x180019f8e  cmp     dword ptr [rbx+0Ch], 5
0x180019f92  jnz     loc_18001A073
0x180019f98  test    r14d, r14d
0x180019f9b  jz      loc_18001A073
0x180019fa1  or      dword ptr [rbx+1Ch], 2
0x180019fa5  mov     r14d, 0Ch
0x180019fab  mov     [rsp+108h+var_C0], 0
0x180019fb4  xor     r15d, r15d
0x180019fb7  mov     [rsp+108h+var_B8], 0
0x180019fc0  call    cs:__imp_KeGetCurrentIrql
0x180019fc7  nop     dword ptr [rax+rax+00h]
0x180019fcc  mov     [rsp+108h+var_C8], al
0x180019fd0  cmp     al, 2
0x180019fd2  jb      loc_18001A0E8
0x180019fd8  lea     rcx, [rsp+108h+var_C0]
0x180019fdd  call    AesRNGState_select
0x180019fe2  movzx   ebx, [rsp+108h+var_C8]
0x180019fe7  mov     rcx, [rsp+108h+var_C0]
0x180019fec  lea     r9, [rsp+108h+var_B8]
0x180019ff1  mov     ebp, 0Ch
0x180019ff6  cmp     r14, rbp
0x180019ff9  cmovb   rbp, r14
0x180019ffd  mov     r8, rbp
0x18001a000  cmp     bl, 2
0x18001a003  jb      loc_18001A0CA
0x18001a009  mov     rdx, r13
0x18001a00c  call    AesRNGState_generate
0x18001a011  mov     r12d, eax
0x18001a014  add     r13, rbp
0x18001a017  sub     r14, rbp
0x18001a01a  jnz     short loc_180019FE7
0x18001a01c  test    r15, r15
0x18001a01f  jnz     loc_18001A0AF
0x18001a025  mov     rbx, [rsp+108h+var_B0]
0x18001a02a  test    r12d, r12d
0x18001a02d  jns     short loc_18001A073
0x18001a02f  mov     edx, edi
0x18001a031  mov     rcx, rbx
0x18001a034  call    SymCryptWipeAsm
0x18001a039  mov     eax, r12d
0x18001a03c  jmp     short loc_18001A08A
0x18001a03e  add     eax, 0FFFEFFFFh; switch 9 cases
0x18001a043  cmp     eax, 8
0x18001a046  ja      def_18001A057; jumptable 000000018001A057 default case, case 65538
0x18001a04c  mov     eax, ds:(jpt_18001A057 - 180000000h)[r12+rax*4]
0x18001a054  add     rax, r12
0x18001a057  jmp     rax; switch jump
0x18001a05d  mov     r8d, [rbx+38h]; jumptable 000000018001A057 case 65537
0x18001a061  lea     rcx, [rbx+140h]
0x18001a068  lea     rdx, [rbx+3Ch]
0x18001a06c  call    SymCryptRc4Init
0x18001a071  mov     esi, eax
0x18001a073  test    esi, esi
0x18001a075  jnz     loc_18001A1CF
0x18001a07b  mov     rax, [rsp+108h+var_A8]; jumptable 000000018001A057 case 65545
0x18001a080  test    rax, rax
0x18001a083  jz      short loc_18001A088
0x18001a085  mov     [rax], rbx
0x18001a088  xor     eax, eax
0x18001a08a  mov     rcx, [rsp+108h+var_58]
0x18001a092  xor     rcx, rsp; StackCookie
0x18001a095  call    __security_check_cookie
0x18001a09a  add     rsp, 0C8h
0x18001a0a1  pop     r15
0x18001a0a3  pop     r14
0x18001a0a5  pop     r13
0x18001a0a7  pop     r12
0x18001a0a9  pop     rdi
0x18001a0aa  pop     rsi
0x18001a0ab  pop     rbp
0x18001a0ac  pop     rbx
0x18001a0ad  retn
0x18001a0af  lea     rax, [rsp+108h+var_98]
0x18001a0b4  cmp     r15, rax
0x18001a0b7  jz      loc_18001A025
0x18001a0bd  mov     rcx, r15; P
0x18001a0c0  call    BCryptFree
0x18001a0c5  jmp     loc_18001A025
0x18001a0ca  mov     rdx, r15
0x18001a0cd  call    AesRNGState_generate
0x18001a0d2  mov     r8, rbp; Size
0x18001a0d5  mov     rdx, r15; Src
0x18001a0d8  mov     rcx, r13; void *
0x18001a0db  mov     r12d, eax
0x18001a0de  call    memmove
0x18001a0e3  jmp     loc_18001A014
0x18001a0e8  mov     rcx, r14
0x18001a0eb  call    BCryptAlloc
0x18001a0f0  mov     r15, rax
0x18001a0f3  test    rax, rax
0x18001a0f6  jnz     loc_180019FD8
0x18001a0fc  lea     r15, [rsp+108h+var_98]
0x18001a101  jmp     loc_180019FD8
0x18001a106  mov     r12d, 0C000000Dh
0x18001a10c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a113  lea     rax, WPP_GLOBAL_Control
0x18001a11a  cmp     rcx, rax
0x18001a11d  jz      loc_18001A02F
0x18001a123  mov     eax, [rcx+2Ch]
0x18001a126  test    al, 1
0x18001a128  jz      loc_18001A02F
0x18001a12e  mov     rcx, [rcx+18h]
0x18001a132  lea     rax, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001a139  mov     [rsp+108h+var_D8], 1DAh
0x18001a141  lea     r9, aStatus; "Status"
0x18001a148  mov     [rsp+108h+var_E0], rax
0x18001a14d  mov     [rsp+108h+var_E8], 0C000000Dh
0x18001a155  call    WPP_SF_sDsd
0x18001a15a  jmp     loc_18001A02F
0x18001a15f  mov     eax, [rdx+r12+0A507Ch]
0x18001a167  cmp     ebp, eax
0x18001a169  jb      loc_180019ED1
0x18001a16f  mov     ebp, eax
0x18001a171  jmp     loc_180019ED1
0x18001a176  mov     r12d, 0C000000Dh
0x18001a17c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a183  lea     rax, WPP_GLOBAL_Control
0x18001a18a  cmp     rcx, rax
0x18001a18d  jz      loc_18001A02F
0x18001a193  mov     eax, [rcx+2Ch]
0x18001a196  test    al, 1
0x18001a198  jz      loc_18001A02F
0x18001a19e  mov     rcx, [rcx+18h]
0x18001a1a2  lea     rax, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001a1a9  mov     [rsp+108h+var_D8], 230h
0x18001a1b1  lea     r9, aStatus; "Status"
0x18001a1b8  mov     [rsp+108h+var_E0], rax
0x18001a1bd  mov     [rsp+108h+var_E8], 0C000000Dh
0x18001a1c5  call    WPP_SF_sDsd
0x18001a1ca  jmp     loc_18001A02F
0x18001a1cf  mov     r12d, 0C000000Dh
0x18001a1d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a1dc  lea     rax, WPP_GLOBAL_Control
0x18001a1e3  cmp     rcx, rax
0x18001a1e6  jz      loc_18001A02F
0x18001a1ec  mov     eax, [rcx+2Ch]
0x18001a1ef  test    al, 1
0x18001a1f1  jz      loc_18001A02F
0x18001a1f7  mov     rcx, [rcx+18h]
0x18001a1fb  lea     rax, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001a202  mov     [rsp+108h+var_D8], 2EDh
0x18001a20a  lea     r9, aStatus; "Status"
0x18001a211  mov     [rsp+108h+var_E0], rax
0x18001a216  mov     [rsp+108h+var_E8], 0C000000Dh
0x18001a21e  call    WPP_SF_sDsd
0x18001a223  jmp     loc_18001A02F
0x18001a228  mov     r12d, 0C0000008h
0x18001a22e  jmp     loc_18001A02F
0x18001a233  mov     r12d, 0C000000Dh
0x18001a239  jmp     loc_18001A02F
0x18001a23e  cmp     dword ptr [rsi+8], 10002h
0x18001a245  jnz     loc_18009FCA0
0x18001a24b  cmp     dword ptr [rsi+0Ch], 5
0x18001a24f  jz      loc_180019E57
0x18001a255  jmp     loc_18009FCA0
0x18001a25a  mov     r12d, 0C00000BBh; jumptable 000000018001A057 default case, case 65538
0x18001a260  mov     r9d, 2E5h
0x18001a266  mov     ecx, 0C00000BBh
0x18001a26b  lea     rdx, aStatus; "Status"
0x18001a272  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001a279  call    DebugTraceError
0x18001a27e  jmp     loc_18001A02F
0x18001a283  cmp     dword ptr [rsi+8], 10002h
0x18001a28a  jnz     loc_18009FCBE
0x18001a290  cmp     dword ptr [rsi+0Ch], 5
0x18001a294  jnz     loc_18009FCBE
0x18001a29a  cmp     edi, 250h
0x18001a2a0  jnb     loc_180019E6A
0x18001a2a6  jmp     loc_18009FCBE
0x18001a2ab  cmp     r10d, 10008h
0x18001a2b2  jnz     loc_18009FCA8
0x18001a2b8  cmp     cs:g_fSelftest, 0
0x18001a2bf  jz      loc_180019F0B
0x18001a2c5  mov     r8d, ebp
0x18001a2c8  mov     rcx, r13; Buf1
0x18001a2cb  shr     r8, 1; Size
0x18001a2ce  lea     rdx, [r8+r13]; Buf2
0x18001a2d2  call    memcmp
0x18001a2d7  test    eax, eax
0x18001a2d9  jnz     loc_180019F0B
0x18001a2df  jmp     loc_18009FCA8
0x18001a2e4  mov     r8d, [rbx+38h]; jumptable 000000018001A057 case 65539
0x18001a2e8  lea     rcx, [rbx+50h]
0x18001a2ec  lea     rdx, [rbx+3Ch]
0x18001a2f0  mov     dword ptr [rbx+18h], 38h ; '8'
0x18001a2f7  call    SymCryptDesExpandKey
0x18001a2fc  mov     esi, eax
0x18001a2fe  jmp     loc_18001A073
0x18001a303  mov     r8d, [rbx+38h]; jumptable 000000018001A057 case 65540
0x18001a307  lea     rcx, [rbx+60h]
0x18001a30b  lea     rdx, [rbx+3Ch]
0x18001a30f  mov     dword ptr [rbx+18h], 0B8h
0x18001a316  call    SymCryptDesxExpandKey
0x18001a31b  mov     esi, eax
  ... truncated ...
```

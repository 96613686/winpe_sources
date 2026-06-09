# MSCryptGetHashProperty

- ea: `0x18000e440`
- end: `0x18000e939`
- name: `MSCryptGetHashProperty`
- size: `1273`
- prototype: ``
- caller_count: `7`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000bde4`
- `0x18000e940`
- `0x1800871c4`
- `0x180087530`
- `0x180087c38`
- `0x18008a398`
- `0x18008ae48`

## callees

- `0x18000e440`
- `0x18000f764`
- `0x18001155c`
- `0x1800123d0`
- `0x18001bfe0`
- `0x1800a4232`
- `0x1800a45c0`

## string_xrefs

- `0x18000e636`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18000e67b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18000e6cf`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18000e805`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18000e86b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x1800a588f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x1800a58ec`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall MSCryptGetHashProperty(
        _DWORD *a1,
        const wchar_t *a2,
        _QWORD *a3,
        unsigned int a4,
        unsigned int *a5,
        int a6)
{
  int v10; // ebp
  unsigned int v11; // edi
  int v12; // edx
  int v13; // r8d
  __int64 v15; // rax
  int v16; // edx
  int v17; // r8d
  __int64 v18; // rcx
  _QWORD *v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 *v22; // r13
  __int64 v23; // rsi
  unsigned int v24; // edx
  unsigned int v25; // ecx
  __int64 v26; // rax
  _QWORD *v27; // rdx
  unsigned int v28; // r14d
  __int64 v29; // r12
  char *v30; // rbp
  __int64 v31; // rbx
  char *v32; // rcx
  const void *v33; // rdx
  __int64 v34; // rax
  int v35; // edx
  int v36; // r8d
  __int64 v37; // r9
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 *v42; // rdx
  __int64 v43; // rax
  unsigned int v45; // eax
  int v46; // eax
  BOOL v47; // eax
  __int64 v48; // rdx
  __int64 v49; // r8
  char v50; // [rsp+30h] [rbp-48h]

  if ( a6 )
  {
    v11 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
        184);
    return v11;
  }
  if ( !a1 || (v10 = a1[1], v10 != 1297303617) && v10 != 1297303624 )
  {
    v11 = -1073741816;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
      return v11;
    v50 = -63;
    goto LABEL_34;
  }
  if ( !a5 )
  {
    v37 = 3528;
LABEL_87:
    v11 = -1073741811;
    v39 = 3221225485LL;
    goto LABEL_88;
  }
  v11 = 0;
  if ( !wcscmp_0(a2, L"AlgorithmName") )
  {
    v38 = (unsigned int)(unsigned __int16)a1[2] - 1;
    if ( (unsigned int)v38 < 0x1A )
    {
      v42 = &rgHashAlgorithmDefaults[12 * v38];
      v43 = -1;
      while ( *(_WORD *)(v42[7] + 2 * v43++ + 2) != 0 )
        ;
      v45 = 2 * v43 + 2;
      *a5 = v45;
      if ( a3 )
      {
        if ( a4 >= v45 )
        {
          memmove(a3, (const void *)v42[7], v45);
          return v11;
        }
        return (unsigned int)-1073741789;
      }
      return v11;
    }
    v11 = -1073741816;
    v37 = 3539;
    v39 = 3221225480LL;
LABEL_88:
    DebugTraceError(v39, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c", v37);
    return v11;
  }
  if ( !wcscmp_0(a2, L"HashDigestLength") )
  {
    *a5 = 4;
    if ( !a3 )
      return v11;
    if ( a4 >= 4 )
    {
      *(_DWORD *)a3 = a1[3];
      return v11;
    }
    return (unsigned int)-1073741789;
  }
  if ( wcscmp_0(a2, L"ObjectLength") )
  {
    if ( !wcscmp_0(a2, L"MultiObjectLength") )
    {
      v34 = validateMSCryptHashAlgorithm(a1);
      if ( v34 )
      {
        *a5 = 8;
        if ( !a3 )
          return v11;
        if ( a4 >= 8 )
        {
          *a3 = __PAIR64__(*(_DWORD *)(v34 + 24), *(_DWORD *)(v34 + 20) - *(_DWORD *)(v34 + 24));
          return v11;
        }
        return (unsigned int)-1073741789;
      }
      v11 = -1073741637;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v35,
          v36,
          (unsigned int)"Status",
          187,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
          32);
      return v11;
    }
    if ( wcscmp_0(a2, L"HashOIDList") )
    {
      if ( !wcscmp_0(a2, L"HashBlockLength") )
      {
        v15 = validateMSCryptHashAlgorithm(a1);
        if ( v15 )
        {
          *a5 = 4;
          if ( !a3 )
            return v11;
          if ( a4 >= 4 )
          {
            *(_DWORD *)a3 = *(_DWORD *)(v15 + 28);
            return v11;
          }
          return (unsigned int)-1073741789;
        }
        v11 = -1073741637;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v16,
            v17,
            (unsigned int)"Status",
            187,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
            120);
        return v11;
      }
      if ( !wcscmp_0(a2, L"IsKeyedHash") )
      {
        v41 = validateMSCryptHash(a1, 0);
        if ( v41 || (v40 = validateMSCryptHashAlgorithm(a1)) != 0 )
        {
          v46 = a1[2];
          *a5 = 4;
          if ( !a3 )
            return v11;
          if ( a4 < 4 )
            return (unsigned int)-1073741789;
          v47 = LODWORD(rgHashAlgorithmDefaults[12 * (unsigned int)(unsigned __int16)v46 - 8])
             || v41 && *(_DWORD *)(v41 + 28) == 1
             || v40 && *(_DWORD *)(v40 + 52) == 1;
          *(_DWORD *)a3 = v47;
          return v11;
        }
        v37 = 3737;
      }
      else
      {
        if ( wcscmp_0(a2, L"IsReusableHash") )
        {
          v11 = -1073741637;
          DebugTraceError(
            3221225659LL,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
            3812);
          return v11;
        }
        v49 = validateMSCryptHash(a1, 0);
        if ( v49 || (v48 = validateMSCryptHashAlgorithm(a1)) != 0 )
        {
          *a5 = 4;
          if ( !a3 )
            return v11;
          if ( a4 < 4 )
            return (unsigned int)-1073741789;
          *(_DWORD *)a3 = v49 && *(_DWORD *)(v49 + 24) == 1 || v48 && *(_DWORD *)(v48 + 40) == 1;
          return v11;
        }
        v37 = 3780;
      }
      goto LABEL_87;
    }
    v18 = (unsigned int)(unsigned __int16)a1[2] - 1;
    if ( (unsigned int)v18 < 0x1A )
    {
      _mm_lfence();
      v20 = 12 * v18;
      v21 = rgHashAlgorithmDefaults[v20 + 10];
      v22 = &rgHashAlgorithmDefaults[v20];
      v23 = LODWORD(rgHashAlgorithmDefaults[v20 + 9]);
      v24 = 16 * (v23 + 1);
      *a5 = v24;
      if ( (_DWORD)v23 )
      {
        v25 = 0;
        do
        {
          v26 = v25++;
          v24 += *(_DWORD *)(16 * v26 + v21);
          *a5 = v24;
        }
        while ( v25 < (unsigned int)v23 );
      }
      if ( a3 )
      {
        if ( a4 < v24 )
          return (unsigned int)-1073741789;
        *(_DWORD *)a3 = v23;
        v27 = a3 + 2;
        a3[1] = a3 + 2;
        if ( (_DWORD)v23 )
        {
          v28 = 0;
          v29 = 0;
          v30 = (char *)&a3[2 * v23 + 2];
          do
          {
            v31 = 2 * v29;
            LODWORD(v27[2 * v29]) = *(_DWORD *)(v22[10] + 16 * v29);
            v32 = v30;
            v33 = *(const void **)(v22[10] + 16 * v29 + 8);
            if ( !v33 )
              v32 = 0;
            *(_QWORD *)(a3[1] + 16 * v29 + 8) = v32;
            memmove(v30, v33, *(unsigned int *)(a3[1] + 16 * v29));
            v27 = (_QWORD *)a3[1];
            ++v28;
            ++v29;
            v30 += LODWORD(v27[v31]);
          }
          while ( v28 < (unsigned int)v23 );
        }
      }
      return v11;
    }
    v11 = -1073741816;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
      return v11;
    v50 = 66;
LABEL_34:
    WPP_SF_sDsd(
      v19[3],
      (_DWORD)a2,
      (_DWORD)a3,
      (unsigned int)"Status",
      8,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
      v50);
    return v11;
  }
  if ( v10 == 1297303617 )
  {
    *a5 = 4;
    if ( a3 )
    {
      if ( a4 >= 4 )
      {
        *(_DWORD *)a3 = a1[4];
        return v11;
      }
      return (unsigned int)-1073741789;
    }
  }
  else
  {
    v11 = -1073741637;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v12,
        v13,
        (unsigned int)"Status",
        187,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
        2);
  }
  return v11;
}

```

## disassembly

```asm
0x18000e440  mov     [rsp+arg_8], rbx
0x18000e445  mov     [rsp+arg_10], rsi
0x18000e44a  push    rdi
0x18000e44b  push    r12
0x18000e44d  push    r13
0x18000e44f  push    r14
0x18000e451  push    r15
0x18000e453  sub     rsp, 50h
0x18000e457  cmp     [rsp+78h+arg_28], 0
0x18000e45f  mov     r12d, r9d
0x18000e462  mov     r15, r8
0x18000e465  mov     rsi, rdx
0x18000e468  mov     rbx, rcx
0x18000e46b  jnz     loc_18000E6A4
0x18000e471  mov     [rsp+78h+arg_0], rbp
0x18000e479  test    rcx, rcx
0x18000e47c  jz      loc_18000E64C
0x18000e482  mov     ebp, [rcx+4]
0x18000e485  cmp     ebp, 4D534841h
0x18000e48b  jnz     loc_18000E81E
0x18000e491  mov     r14, [rsp+78h+arg_20]
0x18000e499  test    r14, r14
0x18000e49c  jz      loc_18000E884
0x18000e4a2  lea     rdx, aAlgorithmname; "AlgorithmName"
0x18000e4a9  mov     rcx, rsi; Str1
0x18000e4ac  call    wcscmp_0
0x18000e4b1  xor     edi, edi
0x18000e4b3  test    eax, eax
0x18000e4b5  jz      loc_18000E88F
0x18000e4bb  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18000e4c2  mov     rcx, rsi; Str1
0x18000e4c5  call    wcscmp_0
0x18000e4ca  test    eax, eax
0x18000e4cc  jz      short loc_18000E52E
0x18000e4ce  lea     rdx, aObjectlength; "ObjectLength"
0x18000e4d5  mov     rcx, rsi; Str1
0x18000e4d8  call    wcscmp_0
0x18000e4dd  test    eax, eax
0x18000e4df  jnz     short loc_18000E54C
0x18000e4e1  cmp     ebp, 4D534841h
0x18000e4e7  jnz     loc_18000E7D6
0x18000e4ed  mov     dword ptr [r14], 4
0x18000e4f4  test    r15, r15
0x18000e4f7  jz      short loc_18000E509
0x18000e4f9  cmp     r12d, 4
0x18000e4fd  jb      loc_18000E5FD
0x18000e503  mov     eax, [rbx+10h]
0x18000e506  mov     [r15], eax
0x18000e509  mov     rbp, [rsp+78h+arg_0]
0x18000e511  lea     r11, [rsp+78h+var_28]
0x18000e516  mov     eax, edi
0x18000e518  mov     rbx, [r11+38h]
0x18000e51c  mov     rsi, [r11+40h]
0x18000e520  mov     rsp, r11
0x18000e523  pop     r15
0x18000e525  pop     r14
0x18000e527  pop     r13
0x18000e529  pop     r12
0x18000e52b  pop     rdi
0x18000e52c  retn
0x18000e52e  mov     dword ptr [r14], 4
0x18000e535  test    r15, r15
0x18000e538  jz      short loc_18000E509
0x18000e53a  cmp     r12d, 4
0x18000e53e  jb      loc_18000E5FD
0x18000e544  mov     eax, [rbx+0Ch]
0x18000e547  mov     [r15], eax
0x18000e54a  jmp     short loc_18000E509
0x18000e54c  lea     rdx, aMultiobjectlen; "MultiObjectLength"
0x18000e553  mov     rcx, rsi; Str1
0x18000e556  call    wcscmp_0
0x18000e55b  test    eax, eax
0x18000e55d  jz      loc_18000E82F
0x18000e563  lea     rdx, aHashoidlist; "HashOIDList"
0x18000e56a  mov     rcx, rsi; Str1
0x18000e56d  call    wcscmp_0
0x18000e572  test    eax, eax
0x18000e574  jz      short loc_18000E5BB
0x18000e576  lea     rdx, aHashblocklengt; "HashBlockLength"
0x18000e57d  mov     rcx, rsi; Str1
0x18000e580  call    wcscmp_0
0x18000e585  test    eax, eax
0x18000e587  jnz     loc_18000E8EC
0x18000e58d  mov     rcx, rbx
0x18000e590  call    validateMSCryptHashAlgorithm
0x18000e595  test    rax, rax
0x18000e598  jz      short loc_18000E607
0x18000e59a  mov     dword ptr [r14], 4
0x18000e5a1  test    r15, r15
0x18000e5a4  jz      loc_18000E509
0x18000e5aa  cmp     r12d, 4
0x18000e5ae  jb      short loc_18000E5FD
0x18000e5b0  mov     eax, [rax+1Ch]
0x18000e5b3  mov     [r15], eax
0x18000e5b6  jmp     loc_18000E509
0x18000e5bb  mov     eax, [rbx+8]
0x18000e5be  movzx   ecx, ax
0x18000e5c1  dec     ecx
0x18000e5c3  cmp     ecx, 1Ah
0x18000e5c6  jb      loc_18000E6FC
0x18000e5cc  mov     edi, 0C0000008h
0x18000e5d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e5d8  lea     rax, WPP_GLOBAL_Control
0x18000e5df  cmp     rcx, rax
0x18000e5e2  jz      loc_18000E509
0x18000e5e8  mov     eax, [rcx+2Ch]
0x18000e5eb  test    al, 1
0x18000e5ed  jz      loc_18000E509
0x18000e5f3  mov     dword ptr [rsp+78h+var_48], 0E42h
0x18000e5fb  jmp     short loc_18000E67B
0x18000e5fd  mov     edi, 0C0000023h
0x18000e602  jmp     loc_18000E509
0x18000e607  mov     edi, 0C00000BBh
0x18000e60c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e613  lea     rax, WPP_GLOBAL_Control
0x18000e61a  cmp     rcx, rax
0x18000e61d  jz      loc_18000E509
0x18000e623  mov     eax, [rcx+2Ch]
0x18000e626  test    al, 1
0x18000e628  jz      loc_18000E509
0x18000e62e  mov     dword ptr [rsp+78h+var_48], 0E78h
0x18000e636  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e63d  mov     [rsp+78h+var_50], rax
0x18000e642  mov     [rsp+78h+var_58], 0C00000BBh
0x18000e64a  jmp     short loc_18000E68F
0x18000e64c  mov     edi, 0C0000008h
0x18000e651  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e658  lea     rax, WPP_GLOBAL_Control
0x18000e65f  cmp     rcx, rax
0x18000e662  jz      loc_18000E509
0x18000e668  mov     eax, [rcx+2Ch]
0x18000e66b  test    al, 1
0x18000e66d  jz      loc_18000E509
0x18000e673  mov     dword ptr [rsp+78h+var_48], 0DC1h
0x18000e67b  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e682  mov     [rsp+78h+var_50], rax
0x18000e687  mov     [rsp+78h+var_58], 0C0000008h
0x18000e68f  mov     rcx, [rcx+18h]
0x18000e693  lea     r9, aStatus; "Status"
0x18000e69a  call    WPP_SF_sDsd
0x18000e69f  jmp     loc_18000E509
0x18000e6a4  mov     edi, 0C000000Dh
0x18000e6a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e6b0  lea     rax, WPP_GLOBAL_Control
0x18000e6b7  cmp     rcx, rax
0x18000e6ba  jz      loc_18000E511
0x18000e6c0  mov     eax, [rcx+2Ch]
0x18000e6c3  test    al, 1
0x18000e6c5  jz      loc_18000E511
0x18000e6cb  mov     rcx, [rcx+18h]
0x18000e6cf  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e6d6  mov     dword ptr [rsp+78h+var_48], 0DB8h
0x18000e6de  lea     r9, aStatus; "Status"
0x18000e6e5  mov     [rsp+78h+var_50], rax
0x18000e6ea  mov     [rsp+78h+var_58], 0C000000Dh
0x18000e6f2  call    WPP_SF_sDsd
0x18000e6f7  jmp     loc_18000E511
0x18000e6fc  lfence
0x18000e6ff  lea     rax, rgHashAlgorithmDefaults
0x18000e706  lea     rcx, [rcx+rcx*2]
0x18000e70a  shl     rcx, 5
0x18000e70e  mov     r8, [rcx+rax+50h]
0x18000e713  lea     r13, [rcx+rax]
0x18000e717  mov     esi, [rcx+rax+48h]
0x18000e71b  lea     edx, [rsi+1]
0x18000e71e  shl     edx, 4
0x18000e721  mov     [r14], edx
0x18000e724  test    esi, esi
0x18000e726  jz      short loc_18000E743
0x18000e728  mov     ecx, edi
0x18000e72a  nop     word ptr [rax+rax+00h]
0x18000e730  mov     eax, ecx
0x18000e732  inc     ecx
0x18000e734  shl     rax, 4
0x18000e738  add     edx, [rax+r8]
0x18000e73c  mov     [r14], edx
0x18000e73f  cmp     ecx, esi
0x18000e741  jb      short loc_18000E730
0x18000e743  test    r15, r15
0x18000e746  jz      loc_18000E509
0x18000e74c  cmp     r12d, edx
0x18000e74f  jb      loc_18000E5FD
0x18000e755  mov     [r15], esi
0x18000e758  lea     rdx, [r15+10h]
0x18000e75c  mov     [r15+8], rdx
0x18000e760  test    esi, esi
0x18000e762  jz      loc_18000E509
0x18000e768  lea     rbp, [rsi+1]
0x18000e76c  mov     r14d, edi
0x18000e76f  shl     rbp, 4
0x18000e773  mov     r12, rdi
0x18000e776  add     rbp, r15
0x18000e779  nop     dword ptr [rax+00000000h]
0x18000e780  mov     rax, [r13+50h]
0x18000e784  mov     rbx, r12
0x18000e787  add     rbx, rbx
0x18000e78a  mov     ecx, [rax+rbx*8]
0x18000e78d  mov     [rdx+rbx*8], ecx
0x18000e790  mov     rcx, rbp
0x18000e793  mov     rax, [r13+50h]
0x18000e797  mov     rdx, [rax+rbx*8+8]; Src
0x18000e79c  mov     rax, [r15+8]
0x18000e7a0  test    rdx, rdx
0x18000e7a3  cmovz   rcx, rdi
0x18000e7a7  mov     [rax+rbx*8+8], rcx
0x18000e7ac  mov     rcx, rbp; void *
0x18000e7af  mov     rax, [r15+8]
0x18000e7b3  mov     r8d, [rax+rbx*8]; Size
0x18000e7b7  call    memmove
0x18000e7bc  mov     rdx, [r15+8]
0x18000e7c0  inc     r14d
0x18000e7c3  inc     r12
0x18000e7c6  mov     eax, [rdx+rbx*8]
0x18000e7c9  add     rbp, rax
0x18000e7cc  cmp     r14d, esi
0x18000e7cf  jb      short loc_18000E780
0x18000e7d1  jmp     loc_18000E509
0x18000e7d6  mov     edi, 0C00000BBh
0x18000e7db  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e7e2  lea     rax, WPP_GLOBAL_Control
0x18000e7e9  cmp     rcx, rax
0x18000e7ec  jz      loc_18000E509
0x18000e7f2  mov     eax, [rcx+2Ch]
0x18000e7f5  test    al, 1
0x18000e7f7  jz      loc_18000E509
0x18000e7fd  mov     dword ptr [rsp+78h+var_48], 0E02h
0x18000e805  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e80c  mov     [rsp+78h+var_50], rax
0x18000e811  mov     [rsp+78h+var_58], 0C00000BBh
0x18000e819  jmp     loc_18000E68F
0x18000e81e  cmp     ebp, 4D534848h
0x18000e824  jnz     loc_18000E64C
0x18000e82a  jmp     loc_18000E491
0x18000e82f  mov     rcx, rbx
0x18000e832  call    validateMSCryptHashAlgorithm
0x18000e837  test    rax, rax
0x18000e83a  jnz     short loc_18000E8B5
0x18000e83c  mov     edi, 0C00000BBh
0x18000e841  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e848  lea     rax, WPP_GLOBAL_Control
0x18000e84f  cmp     rcx, rax
0x18000e852  jz      loc_18000E509
0x18000e858  mov     eax, [rcx+2Ch]
0x18000e85b  test    al, 1
0x18000e85d  jz      loc_18000E509
0x18000e863  mov     dword ptr [rsp+78h+var_48], 0E20h
0x18000e86b  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e872  mov     [rsp+78h+var_50], rax
0x18000e877  mov     [rsp+78h+var_58], 0C00000BBh
0x18000e87f  jmp     loc_18000E68F
0x18000e884  mov     r9d, 0DC8h
0x18000e88a  jmp     loc_1800A587E
0x18000e88f  mov     eax, [rbx+8]
0x18000e892  movzx   ecx, ax
0x18000e895  dec     ecx
0x18000e897  cmp     ecx, 1Ah
0x18000e89a  jb      loc_1800A5786
0x18000e8a0  mov     edi, 0C0000008h
0x18000e8a5  mov     r9d, 0DD3h
0x18000e8ab  mov     ecx, 0C0000008h
0x18000e8b0  jmp     loc_1800A5888
0x18000e8b5  mov     dword ptr [r14], 8
0x18000e8bc  test    r15, r15
0x18000e8bf  jz      loc_18000E509
0x18000e8c5  cmp     r12d, 8
0x18000e8c9  jb      loc_18000E5FD
0x18000e8cf  mov     ecx, [rax+18h]
0x18000e8d2  mov     eax, [rax+14h]
0x18000e8d5  sub     eax, ecx
0x18000e8d7  mov     dword ptr [rsp+78h+var_38+4], ecx
0x18000e8db  mov     dword ptr [rsp+78h+var_38], eax
0x18000e8df  mov     rax, [rsp+78h+var_38]
0x18000e8e4  mov     [r15], rax
0x18000e8e7  jmp     loc_18000E509
0x18000e8ec  lea     rdx, aIskeyedhash; "IsKeyedHash"
0x18000e8f3  mov     rcx, rsi; Str1
0x18000e8f6  call    wcscmp_0
0x18000e8fb  test    eax, eax
0x18000e8fd  jnz     loc_1800A583E
0x18000e903  mov     rcx, rbx
0x18000e906  mov     rdx, rdi
0x18000e909  call    validateMSCryptHash
0x18000e90e  mov     r8, rax
0x18000e911  test    rax, rax
0x18000e914  jnz     loc_1800A57DF
0x18000e91a  mov     rcx, rbx
0x18000e91d  call    validateMSCryptHashAlgorithm
0x18000e922  mov     rdx, rax
0x18000e925  test    rax, rax
0x18000e928  jnz     loc_1800A57DF
0x18000e92e  mov     r9d, 0E99h
0x18000e934  jmp     loc_1800A587E
0x1800a5786  lea     rdx, [rcx+rcx*2]
0x1800a578a  lea     rax, rgHashAlgorithmDefaults
0x1800a5791  shl     rdx, 5
0x1800a5795  add     rdx, rax
0x1800a5798  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800a579f  mov     rcx, [rdx+38h]
0x1800a57a3  cmp     [rcx+rax*2+2], di
0x1800a57a8  lea     rax, [rax+1]
  ... truncated ...
```

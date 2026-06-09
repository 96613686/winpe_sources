# ImportEccKeyBlobWithoutParameters

- ea: `0x18004623c`
- end: `0x18004662b`
- name: `ImportEccKeyBlobWithoutParameters`
- size: `1007`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800779e8`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x1800421d8`
- `0x180044134`
- `0x18004623c`
- `0x180046634`
- `0x180047628`
- `0x18004788c`
- `0x180048770`
- `0x1800496a4`
- `0x1800497b8`
- `0x180075d00`
- `0x180076d9c`
- `0x18009f780`

## string_xrefs

- `0x180046299`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180046315`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800463cd`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18004644d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180046529`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180046609`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall ImportEccKeyBlobWithoutParameters(
        __int64 a1,
        int *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        char a7,
        _QWORD *a8)
{
  __int64 *v8; // rsi
  __int64 v9; // rdi
  int v10; // r10d
  __int64 v14; // r13
  int NistParametersForKeyMagic; // eax
  __int64 v16; // rbx
  unsigned int v17; // r8d
  unsigned int v18; // eax
  unsigned int v19; // edx
  __int64 v20; // r9
  __int64 v21; // rcx
  unsigned int v22; // ecx
  int KeyMagicForAlgId; // eax
  int v24; // eax
  int v25; // eax
  char *v26; // r14
  __int64 *v27; // rax
  unsigned int *v28; // r12
  __int64 v29; // r13
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  unsigned int v33; // r10d
  unsigned int v34; // eax
  char *v35; // rax
  size_t v37; // r8
  int v38; // r13d
  char *v39; // r15
  __int64 v40; // r9
  __int64 v41; // rcx
  int v42; // r12d
  __int64 v43; // rax
  unsigned int v44; // eax
  int v45; // [rsp+40h] [rbp-20h] BYREF
  PVOID P; // [rsp+48h] [rbp-18h] BYREF
  __int64 v47; // [rsp+50h] [rbp-10h] BYREF
  int v49; // [rsp+A8h] [rbp+48h] BYREF

  v8 = *(__int64 **)(a1 + 16);
  v9 = 0;
  v10 = 0;
  v47 = 0;
  v45 = 0;
  v49 = 0;
  P = 0;
  v14 = a1;
  if ( !v8 )
  {
    NistParametersForKeyMagic = GetNistParametersForKeyMagic((unsigned int)*a2, &P);
    LODWORD(v16) = NistParametersForKeyMagic;
    if ( NistParametersForKeyMagic < 0 )
    {
      DebugTraceError(
        (unsigned int)NistParametersForKeyMagic,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        2005);
      v8 = (__int64 *)P;
      goto LABEL_42;
    }
    v10 = *a2;
    v8 = (__int64 *)P;
    v49 = *a2;
  }
  if ( a3 >= 8 && v8 )
  {
    v17 = *(_DWORD *)(*v8 + 12);
    v18 = a2[1];
    v19 = v17;
    if ( v17 <= *(_DWORD *)(*v8 + 16) )
      v19 = *(_DWORD *)(*v8 + 16);
    if ( a6 )
    {
      if ( v18 != v19 )
      {
        v20 = 2043;
        goto LABEL_13;
      }
    }
    else if ( v18 != v17 && v18 != v19 )
    {
      v20 = 2035;
LABEL_13:
      LODWORD(v16) = -1073741811;
      v21 = 3221225485LL;
LABEL_14:
      DebugTraceError(v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v20);
      goto LABEL_42;
    }
    v22 = 2 * v18 + 8;
    if ( a6 )
      v22 += v18;
    if ( a3 < v22 )
    {
      v20 = 2057;
      goto LABEL_13;
    }
    if ( !v10 )
    {
      KeyMagicForAlgId = MSCryptEcGetKeyMagicForAlgId(*(_DWORD *)(v14 + 8), (_DWORD)v8, a5, a6, (__int64)&v49);
      LODWORD(v16) = KeyMagicForAlgId;
      if ( KeyMagicForAlgId < 0 )
      {
        v20 = 2070;
        v21 = (unsigned int)KeyMagicForAlgId;
        goto LABEL_14;
      }
      v10 = v49;
    }
    v24 = *a2;
    if ( *a2 != v10 && v24 != 1447314245 && v24 != 1346650949 && v24 != 1447772997 && v24 != 1347109701 )
    {
      v20 = 2086;
      goto LABEL_13;
    }
    v25 = AllocateGenericEccKey(&v47, &v45, a4, v14);
    LODWORD(v16) = v25;
    if ( v25 < 0 )
    {
      DebugTraceError((unsigned int)v25, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 2093);
      v9 = v47;
      goto LABEL_40;
    }
    v49 = 0;
    v26 = 0;
    P = 0;
    v9 = v47;
    v27 = *(__int64 **)(v47 + 16);
    if ( !v27 )
    {
      *(_QWORD *)(v47 + 16) = v8;
      v27 = v8;
      v8 = 0;
    }
    v28 = (unsigned int *)(a2 + 2);
    v29 = *v27;
    if ( !(unsigned int)IsAllZeros(a2 + 2, (unsigned int)(2 * a2[1])) )
    {
      v34 = *(_DWORD *)(v29 + 12);
      if ( v33 <= v34 )
      {
        v26 = (char *)(a2 + 2);
        P = (PVOID)(unsigned int)v30;
      }
      else
      {
        v35 = (char *)MSCryptAlloc(2 * v34, v30, v31, v32);
        v26 = v35;
        if ( !v35 )
        {
          LODWORD(v16) = -1073741801;
          DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 2125);
LABEL_39:
          v14 = a1;
          goto LABEL_40;
        }
        v37 = *(unsigned int *)(v29 + 12);
        P = (PVOID)(unsigned int)(2 * v37);
        memmove(v35, a2 + 2, v37);
        memmove(&v26[*(unsigned int *)(v29 + 12)], (char *)v28 + (unsigned int)a2[1], *(unsigned int *)(v29 + 12));
        v49 = 1;
      }
    }
    if ( a6 )
    {
      v38 = *(_DWORD *)(v29 + 16);
      v39 = (char *)v28 + (unsigned int)(2 * a2[1]);
    }
    else
    {
      v39 = 0;
      v38 = 0;
    }
    if ( (a7 & 0x20) == 0 || v39 && v26 )
    {
      v45 = BCryptFlagsToSymCryptKeyValidationFlags();
      v42 = a5 != 0 ? 4096 : 0x2000;
      v43 = SymCryptEckeyAllocate(*(_QWORD *)(*(_QWORD *)(v9 + 16) + 8LL));
      *(_QWORD *)(v9 + 24) = v43;
      if ( v43 )
      {
        v44 = SymCryptEckeySetValue(
                (_DWORD)v39,
                v38,
                (_DWORD)v26,
                (_DWORD)P,
                (unsigned int)(*(_DWORD *)(**(_QWORD **)(v9 + 16) + 4LL) != 3) + 1,
                2,
                v45 | (unsigned int)v42,
                v43);
        if ( !v44 )
        {
          *a8 = v9;
          v9 = 0;
LABEL_61:
          if ( v49 )
            MSCryptFree(v26);
          goto LABEL_39;
        }
        v16 = (unsigned int)SymcryptErrorCodeToNtStatus(v44);
        v41 = v16;
        v40 = 2184;
      }
      else
      {
        LODWORD(v16) = -1073741801;
        v40 = 2168;
        v41 = 3221225495LL;
      }
    }
    else
    {
      LODWORD(v16) = -1073741811;
      v40 = 2157;
      v41 = 3221225485LL;
    }
    DebugTraceError(v41, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v40);
    goto LABEL_61;
  }
  LODWORD(v16) = -1073741811;
  DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 2024);
LABEL_40:
  if ( v9 )
    MSCryptEccDestroyKeyPair(v9, a5);
LABEL_42:
  if ( !*(_QWORD *)(v14 + 16) && v8 )
    FreeGenericEccKeyParameters(v8);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18004623c  mov     [rsp-38h+arg_10], rbx
0x180046241  mov     [rsp-38h+arg_0], rcx
0x180046246  push    rbp
0x180046247  push    rsi
0x180046248  push    rdi
0x180046249  push    r12
0x18004624b  push    r13
0x18004624d  push    r14
0x18004624f  push    r15
0x180046251  mov     rbp, rsp
0x180046254  sub     rsp, 60h
0x180046258  mov     rsi, [rcx+10h]
0x18004625c  xor     edi, edi
0x18004625e  xor     r10d, r10d
0x180046261  mov     [rbp+var_10], rdi
0x180046265  mov     [rbp+var_20], edi
0x180046268  mov     r12d, r9d
0x18004626b  mov     [rbp+arg_8], r10d
0x18004626f  mov     r14d, r8d
0x180046272  mov     [rbp+P], rdi
0x180046276  mov     r15, rdx
0x180046279  mov     r13, rcx
0x18004627c  test    rsi, rsi
0x18004627f  jnz     short loc_1800462C2
0x180046281  mov     ecx, [r15]
0x180046284  lea     rdx, [rbp+P]
0x180046288  call    GetNistParametersForKeyMagic
0x18004628d  mov     ebx, eax
0x18004628f  test    eax, eax
0x180046291  jns     short loc_1800462B7
0x180046293  mov     r9d, 7D5h
0x180046299  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800462a0  lea     rdx, aStatus; "Status"
0x1800462a7  mov     ecx, eax
0x1800462a9  call    DebugTraceError
0x1800462ae  mov     rsi, [rbp+P]
0x1800462b2  jmp     loc_18004647E
0x1800462b7  mov     r10d, [r15]
0x1800462ba  mov     rsi, [rbp+P]
0x1800462be  mov     [rbp+arg_8], r10d
0x1800462c2  cmp     r14d, 8
0x1800462c6  jb      loc_180046603
0x1800462cc  test    rsi, rsi
0x1800462cf  jz      loc_180046603
0x1800462d5  mov     rax, [rsi]
0x1800462d8  mov     r9d, [rbp+arg_28]
0x1800462dc  mov     ecx, [rax+10h]
0x1800462df  mov     r8d, [rax+0Ch]
0x1800462e3  cmp     r8d, ecx
0x1800462e6  mov     eax, [r15+4]
0x1800462ea  mov     edx, r8d
0x1800462ed  cmovbe  edx, ecx
0x1800462f0  test    r9d, r9d
0x1800462f3  jnz     short loc_180046326
0x1800462f5  cmp     eax, r8d
0x1800462f8  jz      short loc_180046332
0x1800462fa  cmp     eax, edx
0x1800462fc  jz      short loc_180046332
0x1800462fe  mov     r9d, 7F3h
0x180046304  mov     ebx, 0C000000Dh
0x180046309  mov     ecx, 0C000000Dh
0x18004630e  lea     rdx, aStatus; "Status"
0x180046315  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004631c  call    DebugTraceError
0x180046321  jmp     loc_18004647E
0x180046326  cmp     eax, edx
0x180046328  jz      short loc_180046332
0x18004632a  mov     r9d, 7FBh
0x180046330  jmp     short loc_180046304
0x180046332  lea     ecx, ds:8[rax*2]
0x180046339  test    r9d, r9d
0x18004633c  jz      short loc_180046340
0x18004633e  add     ecx, eax
0x180046340  cmp     r14d, ecx
0x180046343  jnb     short loc_18004634D
0x180046345  mov     r9d, 809h
0x18004634b  jmp     short loc_180046304
0x18004634d  test    r10d, r10d
0x180046350  jnz     short loc_18004637F
0x180046352  mov     r8d, [rbp+arg_20]
0x180046356  lea     rax, [rbp+arg_8]
0x18004635a  mov     ecx, [r13+8]
0x18004635e  mov     rdx, rsi
0x180046361  mov     [rsp+60h+var_40], rax
0x180046366  call    MSCryptEcGetKeyMagicForAlgId
0x18004636b  mov     ebx, eax
0x18004636d  test    eax, eax
0x18004636f  jns     short loc_18004637B
0x180046371  mov     r9d, 816h
0x180046377  mov     ecx, eax
0x180046379  jmp     short loc_18004630E
0x18004637b  mov     r10d, [rbp+arg_8]
0x18004637f  mov     eax, [r15]
0x180046382  cmp     eax, r10d
0x180046385  jz      short loc_1800463AE
0x180046387  cmp     eax, 56444345h
0x18004638c  jz      short loc_1800463AE
0x18004638e  cmp     eax, 50444345h
0x180046393  jz      short loc_1800463AE
0x180046395  cmp     eax, 564B4345h
0x18004639a  jz      short loc_1800463AE
0x18004639c  cmp     eax, 504B4345h
0x1800463a1  jz      short loc_1800463AE
0x1800463a3  mov     r9d, 826h
0x1800463a9  jmp     loc_180046304
0x1800463ae  mov     r9, r13
0x1800463b1  lea     rdx, [rbp+var_20]
0x1800463b5  mov     r8d, r12d
0x1800463b8  lea     rcx, [rbp+var_10]
0x1800463bc  call    AllocateGenericEccKey
0x1800463c1  mov     ebx, eax
0x1800463c3  test    eax, eax
0x1800463c5  jns     short loc_1800463EB
0x1800463c7  mov     r9d, 82Dh
0x1800463cd  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800463d4  lea     rdx, aStatus; "Status"
0x1800463db  mov     ecx, eax
0x1800463dd  call    DebugTraceError
0x1800463e2  mov     rdi, [rbp+var_10]
0x1800463e6  jmp     loc_18004646E
0x1800463eb  mov     [rbp+arg_8], edi
0x1800463ee  xor     r14d, r14d
0x1800463f1  mov     [rbp+P], rdi
0x1800463f5  mov     rdi, [rbp+var_10]
0x1800463f9  mov     rax, [rdi+10h]
0x1800463fd  test    rax, rax
0x180046400  jnz     short loc_18004640B
0x180046402  mov     [rdi+10h], rsi
0x180046406  mov     rax, rsi
0x180046409  xor     esi, esi
0x18004640b  mov     r10d, [r15+4]
0x18004640f  lea     r12, [r15+8]
0x180046413  mov     r13, [rax]
0x180046416  mov     rcx, r12
0x180046419  lea     edx, [r10+r10]
0x18004641d  call    IsAllZeros
0x180046422  test    eax, eax
0x180046424  jnz     loc_1800464EA
0x18004642a  mov     eax, [r13+0Ch]
0x18004642e  cmp     r10d, eax
0x180046431  jbe     loc_1800464E1
0x180046437  lea     ecx, [rax+rax]
0x18004643a  call    MSCryptAlloc
0x18004643f  mov     r14, rax
0x180046442  test    rax, rax
0x180046445  jnz     short loc_1800464AD
0x180046447  mov     r9d, 84Dh
0x18004644d  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180046454  lea     rdx, aStatus; "Status"
0x18004645b  mov     ecx, 0C0000017h
0x180046460  mov     ebx, 0C0000017h
0x180046465  call    DebugTraceError
0x18004646a  mov     r13, [rbp+arg_0]
0x18004646e  test    rdi, rdi
0x180046471  jz      short loc_18004647E
0x180046473  mov     edx, [rbp+arg_20]
0x180046476  mov     rcx, rdi
0x180046479  call    MSCryptEccDestroyKeyPair
0x18004647e  cmp     qword ptr [r13+10h], 0
0x180046483  jnz     short loc_180046492
0x180046485  test    rsi, rsi
0x180046488  jz      short loc_180046492
0x18004648a  mov     rcx, rsi; P
0x18004648d  call    FreeGenericEccKeyParameters
0x180046492  mov     eax, ebx
0x180046494  mov     rbx, [rsp+60h+arg_10]
0x18004649c  add     rsp, 60h
0x1800464a0  pop     r15
0x1800464a2  pop     r14
0x1800464a4  pop     r13
0x1800464a6  pop     r12
0x1800464a8  pop     rdi
0x1800464a9  pop     rsi
0x1800464aa  pop     rbp
0x1800464ab  retn
0x1800464ad  mov     r8d, [r13+0Ch]; Size
0x1800464b1  mov     rdx, r12; Src
0x1800464b4  mov     rcx, r14; void *
0x1800464b7  lea     eax, [r8+r8]
0x1800464bb  mov     [rbp+P], rax
0x1800464bf  call    memmove
0x1800464c4  mov     r8d, [r13+0Ch]; Size
0x1800464c8  mov     edx, [r15+4]
0x1800464cc  add     rdx, r12; Src
0x1800464cf  lea     rcx, [r8+r14]; void *
0x1800464d3  call    memmove
0x1800464d8  mov     [rbp+arg_8], 1
0x1800464df  jmp     short loc_1800464EA
0x1800464e1  mov     eax, edx
0x1800464e3  mov     r14, r12
0x1800464e6  mov     [rbp+P], rax
0x1800464ea  cmp     [rbp+arg_28], 0
0x1800464ee  jz      short loc_180046501
0x1800464f0  mov     eax, [r15+4]
0x1800464f4  mov     r13d, [r13+10h]
0x1800464f8  lea     r15d, [rax+rax]
0x1800464fc  add     r15, r12
0x1800464ff  jmp     short loc_180046507
0x180046501  xor     r15d, r15d
0x180046504  xor     r13d, r13d
0x180046507  mov     ecx, dword ptr [rbp+arg_30]
0x18004650a  test    cl, 20h
0x18004650d  jz      short loc_180046541
0x18004650f  test    r15, r15
0x180046512  jz      short loc_180046519
0x180046514  test    r14, r14
0x180046517  jnz     short loc_180046541
0x180046519  mov     ebx, 0C000000Dh
0x18004651e  mov     r9d, 86Dh
0x180046524  mov     ecx, 0C000000Dh
0x180046529  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180046530  lea     rdx, aStatus; "Status"
0x180046537  call    DebugTraceError
0x18004653c  jmp     loc_1800465EC
0x180046541  call    BCryptFlagsToSymCryptKeyValidationFlags
0x180046546  mov     ecx, [rbp+arg_20]
0x180046549  neg     ecx
0x18004654b  mov     [rbp+var_20], eax
0x18004654e  mov     rcx, [rdi+10h]
0x180046552  sbb     r12d, r12d
0x180046555  and     r12d, 0FFFFF000h
0x18004655c  add     r12d, 2000h
0x180046563  mov     rcx, [rcx+8]
0x180046567  call    SymCryptEckeyAllocate
0x18004656c  mov     [rdi+18h], rax
0x180046570  mov     rcx, rax
0x180046573  test    rax, rax
0x180046576  jnz     short loc_18004658A
0x180046578  mov     ebx, 0C0000017h
0x18004657d  mov     r9d, 878h
0x180046583  mov     ecx, 0C0000017h
0x180046588  jmp     short loc_180046529
0x18004658a  mov     rax, [rdi+10h]
0x18004658e  mov     rdx, r13
0x180046591  or      r12d, [rbp+var_20]
0x180046595  mov     r9, [rbp+P]
0x180046599  mov     [rsp+60h+var_28], rcx
0x18004659e  mov     rcx, r15
0x1800465a1  mov     r8, [rax]
0x1800465a4  xor     eax, eax
0x1800465a6  mov     [rsp+60h+var_30], r12d
0x1800465ab  mov     [rsp+60h+var_38], 2
0x1800465b3  cmp     dword ptr [r8+4], 3
0x1800465b8  mov     r8, r14
0x1800465bb  setnz   al
0x1800465be  inc     eax
0x1800465c0  mov     dword ptr [rsp+60h+var_40], eax
0x1800465c4  call    SymCryptEckeySetValue
0x1800465c9  test    eax, eax
0x1800465cb  jz      short loc_1800465E3
0x1800465cd  mov     ecx, eax
0x1800465cf  call    SymcryptErrorCodeToNtStatus
0x1800465d4  mov     ebx, eax
0x1800465d6  mov     ecx, eax
0x1800465d8  mov     r9d, 888h
0x1800465de  jmp     loc_180046529
0x1800465e3  mov     rax, [rbp+arg_38]
0x1800465e7  mov     [rax], rdi
0x1800465ea  xor     edi, edi
0x1800465ec  cmp     [rbp+arg_8], 0
0x1800465f0  jz      loc_18004646A
0x1800465f6  mov     rcx, r14; P
0x1800465f9  call    MSCryptFree
0x1800465fe  jmp     loc_18004646A
0x180046603  mov     r9d, 7E8h
0x180046609  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180046610  lea     rdx, aStatus; "Status"
0x180046617  mov     ecx, 0C000000Dh
0x18004661c  mov     ebx, 0C000000Dh
0x180046621  call    DebugTraceError
0x180046626  jmp     loc_18004646E
```

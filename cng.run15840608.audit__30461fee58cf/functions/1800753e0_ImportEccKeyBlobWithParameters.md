# ImportEccKeyBlobWithParameters

- ea: `0x1800753e0`
- end: `0x180075800`
- name: `ImportEccKeyBlobWithParameters`
- size: `1056`
- prototype: `__int64 __fastcall(__int64, int *, unsigned int, unsigned int, int, unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180076fd8`

## callees

- `0x18000743c`
- `0x18003d474`
- `0x180041648`
- `0x1800436a4`
- `0x180045ba4`
- `0x180046b98`
- `0x180046dfc`
- `0x180047ce0`
- `0x180048c14`
- `0x180048d28`
- `0x1800753e0`
- `0x18007638c`
- `0x1800774ec`
- `0x180077564`

## string_xrefs

- `0x180075564`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180075790`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800757d2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall ImportEccKeyBlobWithParameters(
        __int64 a1,
        int *a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        unsigned int a6,
        _QWORD *a7)
{
  __int64 v7; // rdi
  PVOID v8; // r12
  __int64 v12; // r9
  unsigned int v13; // ebx
  __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  unsigned int v16; // eax
  int v17; // r8d
  unsigned int v18; // ecx
  unsigned int v19; // edx
  unsigned int v20; // ecx
  int v21; // r13d
  int KeyMagicForAlgId; // eax
  int v23; // ecx
  int v24; // eax
  __int64 v25; // r9
  __int64 v26; // rcx
  int v27; // r15d
  int v28; // eax
  _QWORD *v29; // r13
  int v30; // eax
  __int64 v31; // r9
  __int64 v32; // rcx
  __int64 v33; // r15
  int v34; // eax
  __int64 v35; // r10
  unsigned int v36; // r11d
  unsigned int v37; // edx
  __int64 v38; // rcx
  unsigned __int64 v39; // rdx
  __int64 v40; // r14
  __int64 v41; // r15
  int v42; // r13d
  int v43; // esi
  __int64 v44; // rax
  unsigned int v45; // eax
  __int64 v47; // [rsp+40h] [rbp-10h] BYREF
  PVOID P; // [rsp+48h] [rbp-8h] BYREF
  _QWORD *v49; // [rsp+98h] [rbp+48h] BYREF
  int v50; // [rsp+A0h] [rbp+50h] BYREF
  unsigned int v51; // [rsp+A8h] [rbp+58h]

  v51 = a4;
  v7 = 0;
  v8 = 0;
  v47 = 0;
  P = 0;
  LODWORD(v49) = 0;
  v50 = 0;
  if ( a3 < 0x20 )
  {
    v12 = 2270;
LABEL_3:
    v13 = -1073741789;
    v14 = 3221225507LL;
LABEL_67:
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v12);
    return v13;
  }
  v15 = 7LL * (unsigned int)a2[4];
  if ( v15 > 0xFFFFFFFF )
  {
    v13 = -1073741675;
    v12 = 2279;
    v14 = 3221225621LL;
    goto LABEL_67;
  }
  v16 = v15 + 32;
  if ( (int)v15 + 32 < (unsigned int)v15 )
    goto LABEL_60;
  v17 = a2[5];
  v18 = v17 + v16;
  if ( v17 + v16 < v16 )
    goto LABEL_60;
  v19 = v18 + a2[6];
  if ( v19 < v18 )
    goto LABEL_60;
  v20 = v19 + a2[7];
  if ( v20 < v19 )
    goto LABEL_60;
  v21 = a5;
  if ( a5 )
  {
    if ( v20 + v17 >= v20 )
    {
      v20 += v17;
      goto LABEL_12;
    }
LABEL_60:
    v13 = -1073741675;
    v31 = 2290;
    v32 = 3221225621LL;
    goto LABEL_61;
  }
LABEL_12:
  if ( a3 < v20 )
  {
    v12 = 2299;
    goto LABEL_3;
  }
  KeyMagicForAlgId = MSCryptEcGetKeyMagicForAlgId(*(_DWORD *)(a1 + 8), *(_QWORD *)(a1 + 16), a4, a5, (__int64)&v50);
  v13 = KeyMagicForAlgId;
  if ( KeyMagicForAlgId < 0 )
  {
    v12 = 2320;
    v14 = (unsigned int)KeyMagicForAlgId;
    goto LABEL_67;
  }
  v23 = *a2;
  if ( *a2 != v50 )
  {
    if ( *(_QWORD *)(a1 + 16) )
    {
      v12 = 2350;
      goto LABEL_27;
    }
    if ( v50 != 1447314245
      && v50 != 1346650949
      && v50 != 1447772997
      && v50 != 1347109701
      && (v23 == 1447314245 || v23 == 1346650949 || v23 == 1447772997 || v23 == 1347109701) )
    {
      v12 = 2343;
LABEL_27:
      v13 = -1073741811;
      v14 = 3221225485LL;
      goto LABEL_67;
    }
  }
  v24 = AllocateGenericEccKey(&v47, &v49, 0, a1);
  v13 = v24;
  if ( v24 < 0 )
  {
    v25 = 2358;
    v26 = (unsigned int)v24;
LABEL_31:
    DebugTraceError(v26, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v25);
    v7 = v47;
    goto LABEL_62;
  }
  v27 = a3 - 2 * a2[4] - 4;
  if ( v21 )
    v27 -= a2[5];
  v7 = v47;
  if ( !*(_QWORD *)(a1 + 16) )
    goto LABEL_40;
  v28 = AssignGenericDomainParameters((unsigned int)&P, *(_DWORD *)(a1 + 8), (int)a2 + 4, v27, 0, 0);
  v8 = P;
  v13 = v28;
  if ( v28 < 0 )
    goto LABEL_62;
  if ( !P || (v29 = *(_QWORD **)(a1 + 16), !(unsigned int)TestIfCurveParametersAreEqual(*v29, *(_QWORD *)P)) )
  {
    v13 = -1073741811;
    v25 = 2388;
    v26 = 3221225485LL;
    goto LABEL_31;
  }
  if ( !v29 || !(unsigned int)TestIfSeedIsEqual(*v29, a2) )
  {
LABEL_40:
    v30 = AssignGenericDomainParameters((int)v7 + 16, *(_DWORD *)(a1 + 8), (int)a2 + 4, v27, 0, 0);
    v13 = v30;
    if ( v30 < 0 )
    {
      v31 = 2402;
LABEL_42:
      v32 = (unsigned int)v30;
LABEL_61:
      DebugTraceError(v32, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v31);
LABEL_62:
      if ( v7 )
        MSCryptEccDestroyKeyPair(v7, v51);
      goto LABEL_64;
    }
    *(_DWORD *)(v7 + 32) = 0;
  }
  v33 = 0;
  v49 = *(_QWORD **)(v7 + 16);
  v34 = IsAllZeros(
          (char *)a2
        + 5 * *(_DWORD *)(*v49 + 12LL)
        + *(unsigned int *)(*v49 + 16LL)
        + (unsigned __int64)*(unsigned int *)(*v49 + 24LL)
        + *(unsigned int *)(*v49 + 20LL)
        + 32,
          (unsigned int)(2 * *(_DWORD *)(*v49 + 12LL)));
  v38 = v37;
  v39 = 0;
  if ( !v34 )
    v39 = (unsigned int)v38;
  v40 = 0;
  P = (PVOID)v39;
  if ( !v34 )
    v40 = v35;
  if ( a5 )
    v33 = v36;
  v47 = v33;
  v41 = (v38 + v35) & -(__int64)(a5 != 0);
  if ( (a6 & 0x20) != 0 && (!v41 || !v40) )
  {
    v13 = -1073741811;
    v31 = 2445;
    v32 = 3221225485LL;
    goto LABEL_61;
  }
  v42 = BCryptFlagsToSymCryptKeyValidationFlags(a6);
  v43 = v51 != 0 ? 4096 : 0x2000;
  v44 = SymCryptEckeyAllocate(v49[1]);
  *(_QWORD *)(v7 + 24) = v44;
  if ( !v44 )
  {
    v13 = -1073741801;
    v31 = 2456;
    v32 = 3221225495LL;
    goto LABEL_61;
  }
  v45 = SymCryptEckeySetValue(
          v41,
          v47,
          v40,
          (_DWORD)P,
          (unsigned int)(*(_DWORD *)(**(_QWORD **)(v7 + 16) + 4LL) != 3) + 1,
          2,
          v42 | (unsigned int)v43,
          v44);
  if ( v45 )
  {
    v30 = SymcryptErrorCodeToNtStatus(v45);
    v13 = v30;
    v31 = 2472;
    goto LABEL_42;
  }
  *a7 = v7;
LABEL_64:
  if ( v8 )
    FreeGenericEccKeyParameters(v8);
  return v13;
}

```

## disassembly

```asm
0x1800753e0  mov     [rsp-38h+arg_0], rbx
0x1800753e5  mov     [rsp-38h+arg_18], r9d
0x1800753ea  push    rbp
0x1800753eb  push    rsi
0x1800753ec  push    rdi
0x1800753ed  push    r12
0x1800753ef  push    r13
0x1800753f1  push    r14
0x1800753f3  push    r15
0x1800753f5  mov     rbp, rsp
0x1800753f8  sub     rsp, 50h
0x1800753fc  xor     edi, edi
0x1800753fe  xor     r12d, r12d
0x180075401  mov     [rbp+var_10], rdi
0x180075405  mov     r10d, r9d
0x180075408  mov     [rbp+P], r12
0x18007540c  mov     r15d, r8d
0x18007540f  mov     dword ptr [rbp+arg_8], edi
0x180075412  mov     rsi, rdx
0x180075415  mov     [rbp+arg_10], edi
0x180075418  mov     r14, rcx
0x18007541b  cmp     r8d, 20h ; ' '
0x18007541f  jnb     short loc_180075436
0x180075421  mov     r9d, 8DEh
0x180075427  mov     ebx, 0C0000023h
0x18007542c  mov     ecx, 0C0000023h
0x180075431  jmp     loc_1800757D2
0x180075436  mov     eax, [rdx+10h]
0x180075439  imul    rcx, rax, 7
0x18007543d  mov     eax, 0FFFFFFFFh
0x180075442  cmp     rcx, rax
0x180075445  ja      loc_1800757C2
0x18007544b  lea     eax, [rcx+20h]
0x18007544e  cmp     eax, ecx
0x180075450  jb      loc_180075780
0x180075456  mov     r8d, [rdx+14h]
0x18007545a  lea     ecx, [r8+rax]
0x18007545e  cmp     ecx, eax
0x180075460  jb      loc_180075780
0x180075466  mov     edx, [rdx+18h]
0x180075469  add     edx, ecx
0x18007546b  cmp     edx, ecx
0x18007546d  jb      loc_180075780
0x180075473  mov     ecx, [rsi+1Ch]
0x180075476  add     ecx, edx
0x180075478  cmp     ecx, edx
0x18007547a  jb      loc_180075780
0x180075480  mov     r13d, [rbp+arg_20]
0x180075484  test    r13d, r13d
0x180075487  jz      short loc_180075497
0x180075489  lea     eax, [rcx+r8]
0x18007548d  cmp     eax, ecx
0x18007548f  jb      loc_180075780
0x180075495  mov     ecx, eax
0x180075497  cmp     r15d, ecx
0x18007549a  jnb     short loc_1800754A4
0x18007549c  mov     r9d, 8FBh
0x1800754a2  jmp     short loc_180075427
0x1800754a4  mov     rdx, [r14+10h]
0x1800754a8  lea     rax, [rbp+arg_10]
0x1800754ac  mov     ecx, [r14+8]
0x1800754b0  mov     r9d, r13d
0x1800754b3  mov     r8d, r10d
0x1800754b6  mov     [rsp+50h+var_30], rax
0x1800754bb  call    MSCryptEcGetKeyMagicForAlgId
0x1800754c0  mov     ebx, eax
0x1800754c2  test    eax, eax
0x1800754c4  jns     short loc_1800754D3
0x1800754c6  mov     r9d, 910h
0x1800754cc  mov     ecx, eax
0x1800754ce  jmp     loc_1800757D2
0x1800754d3  mov     ecx, [rsi]
0x1800754d5  mov     eax, [rbp+arg_10]
0x1800754d8  cmp     ecx, eax
0x1800754da  jz      short loc_18007553C
0x1800754dc  cmp     [r14+10h], rdi
0x1800754e0  jnz     short loc_180075534
0x1800754e2  mov     edx, 56444345h
0x1800754e7  cmp     eax, edx
0x1800754e9  jz      short loc_18007553C
0x1800754eb  mov     r8d, 50444345h
0x1800754f1  cmp     eax, r8d
0x1800754f4  jz      short loc_18007553C
0x1800754f6  mov     r9d, 564B4345h
0x1800754fc  cmp     eax, r9d
0x1800754ff  jz      short loc_18007553C
0x180075501  mov     r10d, 504B4345h
0x180075507  cmp     eax, r10d
0x18007550a  jz      short loc_18007553C
0x18007550c  cmp     ecx, edx
0x18007550e  jz      short loc_18007551F
0x180075510  cmp     ecx, r8d
0x180075513  jz      short loc_18007551F
0x180075515  cmp     ecx, r9d
0x180075518  jz      short loc_18007551F
0x18007551a  cmp     ecx, r10d
0x18007551d  jnz     short loc_18007553C
0x18007551f  mov     r9d, 927h
0x180075525  mov     ebx, 0C000000Dh
0x18007552a  mov     ecx, 0C000000Dh
0x18007552f  jmp     loc_1800757D2
0x180075534  mov     r9d, 92Eh
0x18007553a  jmp     short loc_180075525
0x18007553c  mov     r9, r14
0x18007553f  lea     rdx, [rbp+arg_8]
0x180075543  xor     r8d, r8d
0x180075546  lea     rcx, [rbp+var_10]
0x18007554a  call    AllocateGenericEccKey
0x18007554f  mov     ebx, eax
0x180075551  test    eax, eax
0x180075553  jns     short loc_180075579
0x180075555  mov     r9d, 936h
0x18007555b  mov     ecx, eax
0x18007555d  lea     rdx, aStatus; "Status"
0x180075564  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007556b  call    DebugTraceError
0x180075570  mov     rdi, [rbp+var_10]
0x180075574  jmp     loc_1800757A3
0x180075579  mov     eax, [rsi+10h]
0x18007557c  add     eax, eax
0x18007557e  sub     r15d, eax
0x180075581  add     r15d, 0FFFFFFFCh
0x180075585  test    r13d, r13d
0x180075588  jz      short loc_18007558E
0x18007558a  sub     r15d, [rsi+14h]
0x18007558e  mov     rdi, [rbp+var_10]
0x180075592  cmp     [r14+10h], r12
0x180075596  jz      short loc_1800755F3
0x180075598  mov     edx, [r14+8]
0x18007559c  lea     r8, [rsi+4]
0x1800755a0  mov     [rsp+50h+var_28], r12d
0x1800755a5  lea     rcx, [rbp+P]
0x1800755a9  mov     r9d, r15d
0x1800755ac  mov     [rsp+50h+var_30], r12
0x1800755b1  call    AssignGenericDomainParameters
0x1800755b6  mov     r12, [rbp+P]
0x1800755ba  mov     ebx, eax
0x1800755bc  test    eax, eax
0x1800755be  js      loc_1800757A3
0x1800755c4  test    r12, r12
0x1800755c7  jz      short loc_18007562B
0x1800755c9  mov     r13, [r14+10h]
0x1800755cd  mov     rdx, [r12]
0x1800755d1  mov     rcx, [r13+0]
0x1800755d5  call    TestIfCurveParametersAreEqual
0x1800755da  test    eax, eax
0x1800755dc  jz      short loc_18007562B
0x1800755de  test    r13, r13
0x1800755e1  jz      short loc_1800755F3
0x1800755e3  mov     rcx, [r13+0]
0x1800755e7  mov     rdx, rsi
0x1800755ea  call    TestIfSeedIsEqual
0x1800755ef  test    eax, eax
0x1800755f1  jnz     short loc_180075647
0x1800755f3  mov     edx, [r14+8]
0x1800755f7  lea     rcx, [rdi+10h]
0x1800755fb  mov     [rsp+50h+var_28], 0
0x180075603  lea     r8, [rsi+4]
0x180075607  mov     r9d, r15d
0x18007560a  mov     [rsp+50h+var_30], 0
0x180075613  call    AssignGenericDomainParameters
0x180075618  mov     ebx, eax
0x18007561a  test    eax, eax
0x18007561c  jns     short loc_180075640
0x18007561e  mov     r9d, 962h
0x180075624  mov     ecx, eax
0x180075626  jmp     loc_180075790
0x18007562b  mov     ebx, 0C000000Dh
0x180075630  mov     r9d, 954h
0x180075636  mov     ecx, 0C000000Dh
0x18007563b  jmp     loc_18007555D
0x180075640  mov     dword ptr [rdi+20h], 0
0x180075647  mov     rax, [rdi+10h]
0x18007564b  xor     r15d, r15d
0x18007564e  mov     [rbp+arg_8], rax
0x180075652  mov     r8, [rax]
0x180075655  mov     r9d, [r8+0Ch]
0x180075659  mov     r11d, [r8+10h]
0x18007565d  mov     edx, [r8+18h]
0x180075661  mov     r10d, [r8+14h]
0x180075665  add     rdx, r11
0x180075668  lea     ecx, [r9+r9*4]
0x18007566c  add     r10, 20h ; ' '
0x180075670  add     rdx, rcx
0x180075673  add     r10, rdx
0x180075676  lea     edx, [r9+r9]
0x18007567a  add     r10, rsi
0x18007567d  mov     rcx, r10
0x180075680  call    IsAllZeros
0x180075685  mov     ecx, edx
0x180075687  xor     edx, edx
0x180075689  test    eax, eax
0x18007568b  cmovz   edx, ecx
0x18007568e  xor     r14d, r14d
0x180075691  test    eax, eax
0x180075693  mov     [rbp+P], rdx
0x180075697  lea     rax, [rcx+r10]
0x18007569b  mov     ecx, [rbp+arg_20]
0x18007569e  cmovz   r14, r10
0x1800756a2  test    ecx, ecx
0x1800756a4  cmovnz  r15d, r11d
0x1800756a8  neg     ecx
0x1800756aa  mov     ecx, [rbp+arg_28]
0x1800756ad  mov     [rbp+var_10], r15
0x1800756b1  sbb     r15, r15
0x1800756b4  and     r15, rax
0x1800756b7  test    cl, 20h
0x1800756ba  jz      short loc_1800756DB
0x1800756bc  test    r15, r15
0x1800756bf  jz      short loc_1800756C6
0x1800756c1  test    r14, r14
0x1800756c4  jnz     short loc_1800756DB
0x1800756c6  mov     ebx, 0C000000Dh
0x1800756cb  mov     r9d, 98Dh
0x1800756d1  mov     ecx, 0C000000Dh
0x1800756d6  jmp     loc_180075790
0x1800756db  call    BCryptFlagsToSymCryptKeyValidationFlags
0x1800756e0  mov     edx, [rbp+arg_18]
0x1800756e3  mov     r13d, eax
0x1800756e6  mov     rcx, [rbp+arg_8]
0x1800756ea  neg     edx
0x1800756ec  sbb     esi, esi
0x1800756ee  and     esi, 0FFFFF000h
0x1800756f4  mov     rcx, [rcx+8]
0x1800756f8  add     esi, 2000h
0x1800756fe  call    SymCryptEckeyAllocate
0x180075703  mov     [rdi+18h], rax
0x180075707  mov     rcx, rax
0x18007570a  test    rax, rax
0x18007570d  jnz     short loc_180075721
0x18007570f  mov     ebx, 0C0000017h
0x180075714  mov     r9d, 998h
0x18007571a  mov     ecx, 0C0000017h
0x18007571f  jmp     short loc_180075790
0x180075721  mov     rax, [rdi+10h]
0x180075725  or      esi, r13d
0x180075728  mov     r9, [rbp+P]
0x18007572c  mov     r8, r14
0x18007572f  mov     rdx, [rbp+var_10]
0x180075733  mov     [rsp+50h+var_18], rcx
0x180075738  mov     rcx, r15
0x18007573b  mov     r10, [rax]
0x18007573e  xor     eax, eax
0x180075740  mov     [rsp+50h+var_20], esi
0x180075744  mov     [rsp+50h+var_28], 2
0x18007574c  cmp     dword ptr [r10+4], 3
0x180075751  setnz   al
0x180075754  inc     eax
0x180075756  mov     dword ptr [rsp+50h+var_30], eax
0x18007575a  call    SymCryptEckeySetValue
0x18007575f  test    eax, eax
0x180075761  jz      short loc_180075777
0x180075763  mov     ecx, eax
0x180075765  call    SymcryptErrorCodeToNtStatus
0x18007576a  mov     ebx, eax
0x18007576c  mov     r9d, 9A8h
0x180075772  jmp     loc_180075624
0x180075777  mov     rax, [rbp+arg_30]
0x18007577b  mov     [rax], rdi
0x18007577e  jmp     short loc_1800757B3
0x180075780  mov     ebx, 0C0000095h
0x180075785  mov     r9d, 8F2h
0x18007578b  mov     ecx, 0C0000095h
0x180075790  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180075797  lea     rdx, aStatus; "Status"
0x18007579e  call    DebugTraceError
0x1800757a3  test    rdi, rdi
0x1800757a6  jz      short loc_1800757B3
0x1800757a8  mov     edx, [rbp+arg_18]
0x1800757ab  mov     rcx, rdi
0x1800757ae  call    MSCryptEccDestroyKeyPair
0x1800757b3  test    r12, r12
0x1800757b6  jz      short loc_1800757E5
0x1800757b8  mov     rcx, r12; P
0x1800757bb  call    FreeGenericEccKeyParameters
0x1800757c0  jmp     short loc_1800757E5
0x1800757c2  mov     ebx, 0C0000095h
0x1800757c7  mov     r9d, 8E7h
0x1800757cd  mov     ecx, 0C0000095h
0x1800757d2  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800757d9  lea     rdx, aStatus; "Status"
0x1800757e0  call    DebugTraceError
0x1800757e5  mov     eax, ebx
0x1800757e7  mov     rbx, [rsp+50h+arg_0]
0x1800757ef  add     rsp, 50h
0x1800757f3  pop     r15
0x1800757f5  pop     r14
0x1800757f7  pop     r13
0x1800757f9  pop     r12
0x1800757fb  pop     rdi
0x1800757fc  pop     rsi
0x1800757fd  pop     rbp
0x1800757fe  retn
```

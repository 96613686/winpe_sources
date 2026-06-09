# ImportEccKeyBlobWithoutParameters

- ea: `0x1800457ac`
- end: `0x180045b9b`
- name: `ImportEccKeyBlobWithoutParameters`
- size: `1007`
- prototype: `__int64 __fastcall(__int64, int *, unsigned int, unsigned int, unsigned int, int, unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180076fd8`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x180041648`
- `0x1800436a4`
- `0x1800457ac`
- `0x180045ba4`
- `0x180046b98`
- `0x180046dfc`
- `0x180047ce0`
- `0x180048c14`
- `0x180048d28`
- `0x1800752f0`
- `0x18007638c`
- `0x18009da40`

## string_xrefs

- `0x180045809`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180045885`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18004593d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800459bd`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180045a99`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180045b79`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall ImportEccKeyBlobWithoutParameters(
        __int64 a1,
        int *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        unsigned int a7,
        _QWORD *a8)
{
  __int64 *v8; // rsi
  __int64 v9; // rdi
  int v10; // r10d
  __int64 v14; // r13
  int NistParametersForKeyMagic; // eax
  unsigned int v16; // ebx
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
  unsigned int v30; // edx
  unsigned int v31; // r10d
  unsigned int v32; // eax
  char *v33; // rax
  size_t v35; // r8
  int v36; // r13d
  char *v37; // r15
  __int64 v38; // r9
  __int64 v39; // rcx
  int v40; // r12d
  __int64 v41; // rax
  unsigned int v42; // eax
  int v43; // [rsp+40h] [rbp-20h] BYREF
  PVOID P; // [rsp+48h] [rbp-18h] BYREF
  __int64 v45; // [rsp+50h] [rbp-10h] BYREF
  int v47; // [rsp+A8h] [rbp+48h] BYREF

  v8 = *(__int64 **)(a1 + 16);
  v9 = 0;
  v10 = 0;
  v45 = 0;
  v43 = 0;
  v47 = 0;
  P = 0;
  v14 = a1;
  if ( !v8 )
  {
    NistParametersForKeyMagic = GetNistParametersForKeyMagic((unsigned int)*a2, &P);
    v16 = NistParametersForKeyMagic;
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
    v47 = *a2;
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
      v16 = -1073741811;
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
      KeyMagicForAlgId = MSCryptEcGetKeyMagicForAlgId(*(_DWORD *)(v14 + 8), (_DWORD)v8, a5, a6, (__int64)&v47);
      v16 = KeyMagicForAlgId;
      if ( KeyMagicForAlgId < 0 )
      {
        v20 = 2070;
        v21 = (unsigned int)KeyMagicForAlgId;
        goto LABEL_14;
      }
      v10 = v47;
    }
    v24 = *a2;
    if ( *a2 != v10 && v24 != 1447314245 && v24 != 1346650949 && v24 != 1447772997 && v24 != 1347109701 )
    {
      v20 = 2086;
      goto LABEL_13;
    }
    v25 = AllocateGenericEccKey(&v45, &v43, a4, v14);
    v16 = v25;
    if ( v25 < 0 )
    {
      DebugTraceError((unsigned int)v25, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 2093);
      v9 = v45;
      goto LABEL_40;
    }
    v47 = 0;
    v26 = 0;
    P = 0;
    v9 = v45;
    v27 = *(__int64 **)(v45 + 16);
    if ( !v27 )
    {
      *(_QWORD *)(v45 + 16) = v8;
      v27 = v8;
      v8 = 0;
    }
    v28 = (unsigned int *)(a2 + 2);
    v29 = *v27;
    if ( !(unsigned int)IsAllZeros(a2 + 2, (unsigned int)(2 * a2[1])) )
    {
      v32 = *(_DWORD *)(v29 + 12);
      if ( v31 <= v32 )
      {
        v26 = (char *)(a2 + 2);
        P = (PVOID)v30;
      }
      else
      {
        v33 = (char *)MSCryptAlloc(2 * v32);
        v26 = v33;
        if ( !v33 )
        {
          v16 = -1073741801;
          DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 2125);
LABEL_39:
          v14 = a1;
          goto LABEL_40;
        }
        v35 = *(unsigned int *)(v29 + 12);
        P = (PVOID)(unsigned int)(2 * v35);
        memmove(v33, a2 + 2, v35);
        memmove(&v26[*(unsigned int *)(v29 + 12)], (char *)v28 + (unsigned int)a2[1], *(unsigned int *)(v29 + 12));
        v47 = 1;
      }
    }
    if ( a6 )
    {
      v36 = *(_DWORD *)(v29 + 16);
      v37 = (char *)v28 + (unsigned int)(2 * a2[1]);
    }
    else
    {
      v37 = 0;
      v36 = 0;
    }
    if ( (a7 & 0x20) == 0 || v37 && v26 )
    {
      v43 = BCryptFlagsToSymCryptKeyValidationFlags(a7);
      v40 = a5 != 0 ? 4096 : 0x2000;
      v41 = SymCryptEckeyAllocate(*(_QWORD *)(*(_QWORD *)(v9 + 16) + 8LL));
      *(_QWORD *)(v9 + 24) = v41;
      if ( v41 )
      {
        v42 = SymCryptEckeySetValue(
                (_DWORD)v37,
                v36,
                (_DWORD)v26,
                (_DWORD)P,
                (unsigned int)(*(_DWORD *)(**(_QWORD **)(v9 + 16) + 4LL) != 3) + 1,
                2,
                v43 | (unsigned int)v40,
                v41);
        if ( !v42 )
        {
          *a8 = v9;
          v9 = 0;
LABEL_61:
          if ( v47 )
            MSCryptFree(v26);
          goto LABEL_39;
        }
        v16 = SymcryptErrorCodeToNtStatus(v42);
        v39 = v16;
        v38 = 2184;
      }
      else
      {
        v16 = -1073741801;
        v38 = 2168;
        v39 = 3221225495LL;
      }
    }
    else
    {
      v16 = -1073741811;
      v38 = 2157;
      v39 = 3221225485LL;
    }
    DebugTraceError(v39, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v38);
    goto LABEL_61;
  }
  v16 = -1073741811;
  DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 2024);
LABEL_40:
  if ( v9 )
    MSCryptEccDestroyKeyPair(v9, a5);
LABEL_42:
  if ( !*(_QWORD *)(v14 + 16) && v8 )
    FreeGenericEccKeyParameters(v8);
  return v16;
}

```

## disassembly

```asm
0x1800457ac  mov     [rsp-38h+arg_10], rbx
0x1800457b1  mov     [rsp-38h+arg_0], rcx
0x1800457b6  push    rbp
0x1800457b7  push    rsi
0x1800457b8  push    rdi
0x1800457b9  push    r12
0x1800457bb  push    r13
0x1800457bd  push    r14
0x1800457bf  push    r15
0x1800457c1  mov     rbp, rsp
0x1800457c4  sub     rsp, 60h
0x1800457c8  mov     rsi, [rcx+10h]
0x1800457cc  xor     edi, edi
0x1800457ce  xor     r10d, r10d
0x1800457d1  mov     [rbp+var_10], rdi
0x1800457d5  mov     [rbp+var_20], edi
0x1800457d8  mov     r12d, r9d
0x1800457db  mov     [rbp+arg_8], r10d
0x1800457df  mov     r14d, r8d
0x1800457e2  mov     [rbp+P], rdi
0x1800457e6  mov     r15, rdx
0x1800457e9  mov     r13, rcx
0x1800457ec  test    rsi, rsi
0x1800457ef  jnz     short loc_180045832
0x1800457f1  mov     ecx, [r15]
0x1800457f4  lea     rdx, [rbp+P]
0x1800457f8  call    GetNistParametersForKeyMagic
0x1800457fd  mov     ebx, eax
0x1800457ff  test    eax, eax
0x180045801  jns     short loc_180045827
0x180045803  mov     r9d, 7D5h
0x180045809  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180045810  lea     rdx, aStatus; "Status"
0x180045817  mov     ecx, eax
0x180045819  call    DebugTraceError
0x18004581e  mov     rsi, [rbp+P]
0x180045822  jmp     loc_1800459EE
0x180045827  mov     r10d, [r15]
0x18004582a  mov     rsi, [rbp+P]
0x18004582e  mov     [rbp+arg_8], r10d
0x180045832  cmp     r14d, 8
0x180045836  jb      loc_180045B73
0x18004583c  test    rsi, rsi
0x18004583f  jz      loc_180045B73
0x180045845  mov     rax, [rsi]
0x180045848  mov     r9d, [rbp+arg_28]
0x18004584c  mov     ecx, [rax+10h]
0x18004584f  mov     r8d, [rax+0Ch]
0x180045853  cmp     r8d, ecx
0x180045856  mov     eax, [r15+4]
0x18004585a  mov     edx, r8d
0x18004585d  cmovbe  edx, ecx
0x180045860  test    r9d, r9d
0x180045863  jnz     short loc_180045896
0x180045865  cmp     eax, r8d
0x180045868  jz      short loc_1800458A2
0x18004586a  cmp     eax, edx
0x18004586c  jz      short loc_1800458A2
0x18004586e  mov     r9d, 7F3h
0x180045874  mov     ebx, 0C000000Dh
0x180045879  mov     ecx, 0C000000Dh
0x18004587e  lea     rdx, aStatus; "Status"
0x180045885  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004588c  call    DebugTraceError
0x180045891  jmp     loc_1800459EE
0x180045896  cmp     eax, edx
0x180045898  jz      short loc_1800458A2
0x18004589a  mov     r9d, 7FBh
0x1800458a0  jmp     short loc_180045874
0x1800458a2  lea     ecx, ds:8[rax*2]
0x1800458a9  test    r9d, r9d
0x1800458ac  jz      short loc_1800458B0
0x1800458ae  add     ecx, eax
0x1800458b0  cmp     r14d, ecx
0x1800458b3  jnb     short loc_1800458BD
0x1800458b5  mov     r9d, 809h
0x1800458bb  jmp     short loc_180045874
0x1800458bd  test    r10d, r10d
0x1800458c0  jnz     short loc_1800458EF
0x1800458c2  mov     r8d, [rbp+arg_20]
0x1800458c6  lea     rax, [rbp+arg_8]
0x1800458ca  mov     ecx, [r13+8]
0x1800458ce  mov     rdx, rsi
0x1800458d1  mov     [rsp+60h+var_40], rax
0x1800458d6  call    MSCryptEcGetKeyMagicForAlgId
0x1800458db  mov     ebx, eax
0x1800458dd  test    eax, eax
0x1800458df  jns     short loc_1800458EB
0x1800458e1  mov     r9d, 816h
0x1800458e7  mov     ecx, eax
0x1800458e9  jmp     short loc_18004587E
0x1800458eb  mov     r10d, [rbp+arg_8]
0x1800458ef  mov     eax, [r15]
0x1800458f2  cmp     eax, r10d
0x1800458f5  jz      short loc_18004591E
0x1800458f7  cmp     eax, 56444345h
0x1800458fc  jz      short loc_18004591E
0x1800458fe  cmp     eax, 50444345h
0x180045903  jz      short loc_18004591E
0x180045905  cmp     eax, 564B4345h
0x18004590a  jz      short loc_18004591E
0x18004590c  cmp     eax, 504B4345h
0x180045911  jz      short loc_18004591E
0x180045913  mov     r9d, 826h
0x180045919  jmp     loc_180045874
0x18004591e  mov     r9, r13
0x180045921  lea     rdx, [rbp+var_20]
0x180045925  mov     r8d, r12d
0x180045928  lea     rcx, [rbp+var_10]
0x18004592c  call    AllocateGenericEccKey
0x180045931  mov     ebx, eax
0x180045933  test    eax, eax
0x180045935  jns     short loc_18004595B
0x180045937  mov     r9d, 82Dh
0x18004593d  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180045944  lea     rdx, aStatus; "Status"
0x18004594b  mov     ecx, eax
0x18004594d  call    DebugTraceError
0x180045952  mov     rdi, [rbp+var_10]
0x180045956  jmp     loc_1800459DE
0x18004595b  mov     [rbp+arg_8], edi
0x18004595e  xor     r14d, r14d
0x180045961  mov     [rbp+P], rdi
0x180045965  mov     rdi, [rbp+var_10]
0x180045969  mov     rax, [rdi+10h]
0x18004596d  test    rax, rax
0x180045970  jnz     short loc_18004597B
0x180045972  mov     [rdi+10h], rsi
0x180045976  mov     rax, rsi
0x180045979  xor     esi, esi
0x18004597b  mov     r10d, [r15+4]
0x18004597f  lea     r12, [r15+8]
0x180045983  mov     r13, [rax]
0x180045986  mov     rcx, r12
0x180045989  lea     edx, [r10+r10]
0x18004598d  call    IsAllZeros
0x180045992  test    eax, eax
0x180045994  jnz     loc_180045A5A
0x18004599a  mov     eax, [r13+0Ch]
0x18004599e  cmp     r10d, eax
0x1800459a1  jbe     loc_180045A51
0x1800459a7  lea     ecx, [rax+rax]
0x1800459aa  call    MSCryptAlloc
0x1800459af  mov     r14, rax
0x1800459b2  test    rax, rax
0x1800459b5  jnz     short loc_180045A1D
0x1800459b7  mov     r9d, 84Dh
0x1800459bd  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800459c4  lea     rdx, aStatus; "Status"
0x1800459cb  mov     ecx, 0C0000017h
0x1800459d0  mov     ebx, 0C0000017h
0x1800459d5  call    DebugTraceError
0x1800459da  mov     r13, [rbp+arg_0]
0x1800459de  test    rdi, rdi
0x1800459e1  jz      short loc_1800459EE
0x1800459e3  mov     edx, [rbp+arg_20]
0x1800459e6  mov     rcx, rdi
0x1800459e9  call    MSCryptEccDestroyKeyPair
0x1800459ee  cmp     qword ptr [r13+10h], 0
0x1800459f3  jnz     short loc_180045A02
0x1800459f5  test    rsi, rsi
0x1800459f8  jz      short loc_180045A02
0x1800459fa  mov     rcx, rsi; P
0x1800459fd  call    FreeGenericEccKeyParameters
0x180045a02  mov     eax, ebx
0x180045a04  mov     rbx, [rsp+60h+arg_10]
0x180045a0c  add     rsp, 60h
0x180045a10  pop     r15
0x180045a12  pop     r14
0x180045a14  pop     r13
0x180045a16  pop     r12
0x180045a18  pop     rdi
0x180045a19  pop     rsi
0x180045a1a  pop     rbp
0x180045a1b  retn
0x180045a1d  mov     r8d, [r13+0Ch]; Size
0x180045a21  mov     rdx, r12; Src
0x180045a24  mov     rcx, r14; void *
0x180045a27  lea     eax, [r8+r8]
0x180045a2b  mov     [rbp+P], rax
0x180045a2f  call    memmove
0x180045a34  mov     r8d, [r13+0Ch]; Size
0x180045a38  mov     edx, [r15+4]
0x180045a3c  add     rdx, r12; Src
0x180045a3f  lea     rcx, [r8+r14]; void *
0x180045a43  call    memmove
0x180045a48  mov     [rbp+arg_8], 1
0x180045a4f  jmp     short loc_180045A5A
0x180045a51  mov     eax, edx
0x180045a53  mov     r14, r12
0x180045a56  mov     [rbp+P], rax
0x180045a5a  cmp     [rbp+arg_28], 0
0x180045a5e  jz      short loc_180045A71
0x180045a60  mov     eax, [r15+4]
0x180045a64  mov     r13d, [r13+10h]
0x180045a68  lea     r15d, [rax+rax]
0x180045a6c  add     r15, r12
0x180045a6f  jmp     short loc_180045A77
0x180045a71  xor     r15d, r15d
0x180045a74  xor     r13d, r13d
0x180045a77  mov     ecx, [rbp+arg_30]
0x180045a7a  test    cl, 20h
0x180045a7d  jz      short loc_180045AB1
0x180045a7f  test    r15, r15
0x180045a82  jz      short loc_180045A89
0x180045a84  test    r14, r14
0x180045a87  jnz     short loc_180045AB1
0x180045a89  mov     ebx, 0C000000Dh
0x180045a8e  mov     r9d, 86Dh
0x180045a94  mov     ecx, 0C000000Dh
0x180045a99  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180045aa0  lea     rdx, aStatus; "Status"
0x180045aa7  call    DebugTraceError
0x180045aac  jmp     loc_180045B5C
0x180045ab1  call    BCryptFlagsToSymCryptKeyValidationFlags
0x180045ab6  mov     ecx, [rbp+arg_20]
0x180045ab9  neg     ecx
0x180045abb  mov     [rbp+var_20], eax
0x180045abe  mov     rcx, [rdi+10h]
0x180045ac2  sbb     r12d, r12d
0x180045ac5  and     r12d, 0FFFFF000h
0x180045acc  add     r12d, 2000h
0x180045ad3  mov     rcx, [rcx+8]
0x180045ad7  call    SymCryptEckeyAllocate
0x180045adc  mov     [rdi+18h], rax
0x180045ae0  mov     rcx, rax
0x180045ae3  test    rax, rax
0x180045ae6  jnz     short loc_180045AFA
0x180045ae8  mov     ebx, 0C0000017h
0x180045aed  mov     r9d, 878h
0x180045af3  mov     ecx, 0C0000017h
0x180045af8  jmp     short loc_180045A99
0x180045afa  mov     rax, [rdi+10h]
0x180045afe  mov     rdx, r13
0x180045b01  or      r12d, [rbp+var_20]
0x180045b05  mov     r9, [rbp+P]
0x180045b09  mov     [rsp+60h+var_28], rcx
0x180045b0e  mov     rcx, r15
0x180045b11  mov     r8, [rax]
0x180045b14  xor     eax, eax
0x180045b16  mov     [rsp+60h+var_30], r12d
0x180045b1b  mov     [rsp+60h+var_38], 2
0x180045b23  cmp     dword ptr [r8+4], 3
0x180045b28  mov     r8, r14
0x180045b2b  setnz   al
0x180045b2e  inc     eax
0x180045b30  mov     dword ptr [rsp+60h+var_40], eax
0x180045b34  call    SymCryptEckeySetValue
0x180045b39  test    eax, eax
0x180045b3b  jz      short loc_180045B53
0x180045b3d  mov     ecx, eax
0x180045b3f  call    SymcryptErrorCodeToNtStatus
0x180045b44  mov     ebx, eax
0x180045b46  mov     ecx, eax
0x180045b48  mov     r9d, 888h
0x180045b4e  jmp     loc_180045A99
0x180045b53  mov     rax, [rbp+arg_38]
0x180045b57  mov     [rax], rdi
0x180045b5a  xor     edi, edi
0x180045b5c  cmp     [rbp+arg_8], 0
0x180045b60  jz      loc_1800459DA
0x180045b66  mov     rcx, r14; P
0x180045b69  call    MSCryptFree
0x180045b6e  jmp     loc_1800459DA
0x180045b73  mov     r9d, 7E8h
0x180045b79  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180045b80  lea     rdx, aStatus; "Status"
0x180045b87  mov     ecx, 0C000000Dh
0x180045b8c  mov     ebx, 0C000000Dh
0x180045b91  call    DebugTraceError
0x180045b96  jmp     loc_1800459DE
```

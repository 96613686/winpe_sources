# ImportEccKeyBlobWithParameters

- ea: `0x18007f580`
- end: `0x18007f9a0`
- name: `ImportEccKeyBlobWithParameters`
- size: `1056`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180081178`

## callees

- `0x18001155c`
- `0x180047434`
- `0x18004b628`
- `0x18004d684`
- `0x18004fc94`
- `0x180050c88`
- `0x180050eec`
- `0x180051dd0`
- `0x180052d04`
- `0x180052e18`
- `0x18007f580`
- `0x18008052c`
- `0x18008168c`
- `0x180081704`

## string_xrefs

- `0x18007f704`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18007f930`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18007f972`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

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
0x18007f580  mov     [rsp-38h+arg_0], rbx
0x18007f585  mov     [rsp-38h+arg_18], r9d
0x18007f58a  push    rbp
0x18007f58b  push    rsi
0x18007f58c  push    rdi
0x18007f58d  push    r12
0x18007f58f  push    r13
0x18007f591  push    r14
0x18007f593  push    r15
0x18007f595  mov     rbp, rsp
0x18007f598  sub     rsp, 50h
0x18007f59c  xor     edi, edi
0x18007f59e  xor     r12d, r12d
0x18007f5a1  mov     [rbp+var_10], rdi
0x18007f5a5  mov     r10d, r9d
0x18007f5a8  mov     [rbp+P], r12
0x18007f5ac  mov     r15d, r8d
0x18007f5af  mov     dword ptr [rbp+arg_8], edi
0x18007f5b2  mov     rsi, rdx
0x18007f5b5  mov     [rbp+arg_10], edi
0x18007f5b8  mov     r14, rcx
0x18007f5bb  cmp     r8d, 20h ; ' '
0x18007f5bf  jnb     short loc_18007F5D6
0x18007f5c1  mov     r9d, 8DEh
0x18007f5c7  mov     ebx, 0C0000023h
0x18007f5cc  mov     ecx, 0C0000023h
0x18007f5d1  jmp     loc_18007F972
0x18007f5d6  mov     eax, [rdx+10h]
0x18007f5d9  imul    rcx, rax, 7
0x18007f5dd  mov     eax, 0FFFFFFFFh
0x18007f5e2  cmp     rcx, rax
0x18007f5e5  ja      loc_18007F962
0x18007f5eb  lea     eax, [rcx+20h]
0x18007f5ee  cmp     eax, ecx
0x18007f5f0  jb      loc_18007F920
0x18007f5f6  mov     r8d, [rdx+14h]
0x18007f5fa  lea     ecx, [r8+rax]
0x18007f5fe  cmp     ecx, eax
0x18007f600  jb      loc_18007F920
0x18007f606  mov     edx, [rdx+18h]
0x18007f609  add     edx, ecx
0x18007f60b  cmp     edx, ecx
0x18007f60d  jb      loc_18007F920
0x18007f613  mov     ecx, [rsi+1Ch]
0x18007f616  add     ecx, edx
0x18007f618  cmp     ecx, edx
0x18007f61a  jb      loc_18007F920
0x18007f620  mov     r13d, [rbp+arg_20]
0x18007f624  test    r13d, r13d
0x18007f627  jz      short loc_18007F637
0x18007f629  lea     eax, [rcx+r8]
0x18007f62d  cmp     eax, ecx
0x18007f62f  jb      loc_18007F920
0x18007f635  mov     ecx, eax
0x18007f637  cmp     r15d, ecx
0x18007f63a  jnb     short loc_18007F644
0x18007f63c  mov     r9d, 8FBh
0x18007f642  jmp     short loc_18007F5C7
0x18007f644  mov     rdx, [r14+10h]
0x18007f648  lea     rax, [rbp+arg_10]
0x18007f64c  mov     ecx, [r14+8]
0x18007f650  mov     r9d, r13d
0x18007f653  mov     r8d, r10d
0x18007f656  mov     [rsp+50h+var_30], rax
0x18007f65b  call    MSCryptEcGetKeyMagicForAlgId
0x18007f660  mov     ebx, eax
0x18007f662  test    eax, eax
0x18007f664  jns     short loc_18007F673
0x18007f666  mov     r9d, 910h
0x18007f66c  mov     ecx, eax
0x18007f66e  jmp     loc_18007F972
0x18007f673  mov     ecx, [rsi]
0x18007f675  mov     eax, [rbp+arg_10]
0x18007f678  cmp     ecx, eax
0x18007f67a  jz      short loc_18007F6DC
0x18007f67c  cmp     [r14+10h], rdi
0x18007f680  jnz     short loc_18007F6D4
0x18007f682  mov     edx, 56444345h
0x18007f687  cmp     eax, edx
0x18007f689  jz      short loc_18007F6DC
0x18007f68b  mov     r8d, 50444345h
0x18007f691  cmp     eax, r8d
0x18007f694  jz      short loc_18007F6DC
0x18007f696  mov     r9d, 564B4345h
0x18007f69c  cmp     eax, r9d
0x18007f69f  jz      short loc_18007F6DC
0x18007f6a1  mov     r10d, 504B4345h
0x18007f6a7  cmp     eax, r10d
0x18007f6aa  jz      short loc_18007F6DC
0x18007f6ac  cmp     ecx, edx
0x18007f6ae  jz      short loc_18007F6BF
0x18007f6b0  cmp     ecx, r8d
0x18007f6b3  jz      short loc_18007F6BF
0x18007f6b5  cmp     ecx, r9d
0x18007f6b8  jz      short loc_18007F6BF
0x18007f6ba  cmp     ecx, r10d
0x18007f6bd  jnz     short loc_18007F6DC
0x18007f6bf  mov     r9d, 927h
0x18007f6c5  mov     ebx, 0C000000Dh
0x18007f6ca  mov     ecx, 0C000000Dh
0x18007f6cf  jmp     loc_18007F972
0x18007f6d4  mov     r9d, 92Eh
0x18007f6da  jmp     short loc_18007F6C5
0x18007f6dc  mov     r9, r14
0x18007f6df  lea     rdx, [rbp+arg_8]
0x18007f6e3  xor     r8d, r8d
0x18007f6e6  lea     rcx, [rbp+var_10]
0x18007f6ea  call    AllocateGenericEccKey
0x18007f6ef  mov     ebx, eax
0x18007f6f1  test    eax, eax
0x18007f6f3  jns     short loc_18007F719
0x18007f6f5  mov     r9d, 936h
0x18007f6fb  mov     ecx, eax
0x18007f6fd  lea     rdx, aStatus; "Status"
0x18007f704  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007f70b  call    DebugTraceError
0x18007f710  mov     rdi, [rbp+var_10]
0x18007f714  jmp     loc_18007F943
0x18007f719  mov     eax, [rsi+10h]
0x18007f71c  add     eax, eax
0x18007f71e  sub     r15d, eax
0x18007f721  add     r15d, 0FFFFFFFCh
0x18007f725  test    r13d, r13d
0x18007f728  jz      short loc_18007F72E
0x18007f72a  sub     r15d, [rsi+14h]
0x18007f72e  mov     rdi, [rbp+var_10]
0x18007f732  cmp     [r14+10h], r12
0x18007f736  jz      short loc_18007F793
0x18007f738  mov     edx, [r14+8]
0x18007f73c  lea     r8, [rsi+4]
0x18007f740  mov     [rsp+50h+var_28], r12d
0x18007f745  lea     rcx, [rbp+P]
0x18007f749  mov     r9d, r15d
0x18007f74c  mov     [rsp+50h+var_30], r12
0x18007f751  call    AssignGenericDomainParameters
0x18007f756  mov     r12, [rbp+P]
0x18007f75a  mov     ebx, eax
0x18007f75c  test    eax, eax
0x18007f75e  js      loc_18007F943
0x18007f764  test    r12, r12
0x18007f767  jz      short loc_18007F7CB
0x18007f769  mov     r13, [r14+10h]
0x18007f76d  mov     rdx, [r12]
0x18007f771  mov     rcx, [r13+0]
0x18007f775  call    TestIfCurveParametersAreEqual
0x18007f77a  test    eax, eax
0x18007f77c  jz      short loc_18007F7CB
0x18007f77e  test    r13, r13
0x18007f781  jz      short loc_18007F793
0x18007f783  mov     rcx, [r13+0]
0x18007f787  mov     rdx, rsi
0x18007f78a  call    TestIfSeedIsEqual
0x18007f78f  test    eax, eax
0x18007f791  jnz     short loc_18007F7E7
0x18007f793  mov     edx, [r14+8]
0x18007f797  lea     rcx, [rdi+10h]
0x18007f79b  mov     [rsp+50h+var_28], 0
0x18007f7a3  lea     r8, [rsi+4]
0x18007f7a7  mov     r9d, r15d
0x18007f7aa  mov     [rsp+50h+var_30], 0
0x18007f7b3  call    AssignGenericDomainParameters
0x18007f7b8  mov     ebx, eax
0x18007f7ba  test    eax, eax
0x18007f7bc  jns     short loc_18007F7E0
0x18007f7be  mov     r9d, 962h
0x18007f7c4  mov     ecx, eax
0x18007f7c6  jmp     loc_18007F930
0x18007f7cb  mov     ebx, 0C000000Dh
0x18007f7d0  mov     r9d, 954h
0x18007f7d6  mov     ecx, 0C000000Dh
0x18007f7db  jmp     loc_18007F6FD
0x18007f7e0  mov     dword ptr [rdi+20h], 0
0x18007f7e7  mov     rax, [rdi+10h]
0x18007f7eb  xor     r15d, r15d
0x18007f7ee  mov     [rbp+arg_8], rax
0x18007f7f2  mov     r8, [rax]
0x18007f7f5  mov     r9d, [r8+0Ch]
0x18007f7f9  mov     r11d, [r8+10h]
0x18007f7fd  mov     edx, [r8+18h]
0x18007f801  mov     r10d, [r8+14h]
0x18007f805  add     rdx, r11
0x18007f808  lea     ecx, [r9+r9*4]
0x18007f80c  add     r10, 20h ; ' '
0x18007f810  add     rdx, rcx
0x18007f813  add     r10, rdx
0x18007f816  lea     edx, [r9+r9]
0x18007f81a  add     r10, rsi
0x18007f81d  mov     rcx, r10
0x18007f820  call    IsAllZeros
0x18007f825  mov     ecx, edx
0x18007f827  xor     edx, edx
0x18007f829  test    eax, eax
0x18007f82b  cmovz   edx, ecx
0x18007f82e  xor     r14d, r14d
0x18007f831  test    eax, eax
0x18007f833  mov     [rbp+P], rdx
0x18007f837  lea     rax, [rcx+r10]
0x18007f83b  mov     ecx, [rbp+arg_20]
0x18007f83e  cmovz   r14, r10
0x18007f842  test    ecx, ecx
0x18007f844  cmovnz  r15d, r11d
0x18007f848  neg     ecx
0x18007f84a  mov     ecx, [rbp+arg_28]
0x18007f84d  mov     [rbp+var_10], r15
0x18007f851  sbb     r15, r15
0x18007f854  and     r15, rax
0x18007f857  test    cl, 20h
0x18007f85a  jz      short loc_18007F87B
0x18007f85c  test    r15, r15
0x18007f85f  jz      short loc_18007F866
0x18007f861  test    r14, r14
0x18007f864  jnz     short loc_18007F87B
0x18007f866  mov     ebx, 0C000000Dh
0x18007f86b  mov     r9d, 98Dh
0x18007f871  mov     ecx, 0C000000Dh
0x18007f876  jmp     loc_18007F930
0x18007f87b  call    BCryptFlagsToSymCryptKeyValidationFlags
0x18007f880  mov     edx, [rbp+arg_18]
0x18007f883  mov     r13d, eax
0x18007f886  mov     rcx, [rbp+arg_8]
0x18007f88a  neg     edx
0x18007f88c  sbb     esi, esi
0x18007f88e  and     esi, 0FFFFF000h
0x18007f894  mov     rcx, [rcx+8]
0x18007f898  add     esi, 2000h
0x18007f89e  call    SymCryptEckeyAllocate
0x18007f8a3  mov     [rdi+18h], rax
0x18007f8a7  mov     rcx, rax
0x18007f8aa  test    rax, rax
0x18007f8ad  jnz     short loc_18007F8C1
0x18007f8af  mov     ebx, 0C0000017h
0x18007f8b4  mov     r9d, 998h
0x18007f8ba  mov     ecx, 0C0000017h
0x18007f8bf  jmp     short loc_18007F930
0x18007f8c1  mov     rax, [rdi+10h]
0x18007f8c5  or      esi, r13d
0x18007f8c8  mov     r9, [rbp+P]
0x18007f8cc  mov     r8, r14
0x18007f8cf  mov     rdx, [rbp+var_10]
0x18007f8d3  mov     [rsp+50h+var_18], rcx
0x18007f8d8  mov     rcx, r15
0x18007f8db  mov     r10, [rax]
0x18007f8de  xor     eax, eax
0x18007f8e0  mov     [rsp+50h+var_20], esi
0x18007f8e4  mov     [rsp+50h+var_28], 2
0x18007f8ec  cmp     dword ptr [r10+4], 3
0x18007f8f1  setnz   al
0x18007f8f4  inc     eax
0x18007f8f6  mov     dword ptr [rsp+50h+var_30], eax
0x18007f8fa  call    SymCryptEckeySetValue
0x18007f8ff  test    eax, eax
0x18007f901  jz      short loc_18007F917
0x18007f903  mov     ecx, eax
0x18007f905  call    SymcryptErrorCodeToNtStatus
0x18007f90a  mov     ebx, eax
0x18007f90c  mov     r9d, 9A8h
0x18007f912  jmp     loc_18007F7C4
0x18007f917  mov     rax, [rbp+arg_30]
0x18007f91b  mov     [rax], rdi
0x18007f91e  jmp     short loc_18007F953
0x18007f920  mov     ebx, 0C0000095h
0x18007f925  mov     r9d, 8F2h
0x18007f92b  mov     ecx, 0C0000095h
0x18007f930  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007f937  lea     rdx, aStatus; "Status"
0x18007f93e  call    DebugTraceError
0x18007f943  test    rdi, rdi
0x18007f946  jz      short loc_18007F953
0x18007f948  mov     edx, [rbp+arg_18]
0x18007f94b  mov     rcx, rdi
0x18007f94e  call    MSCryptEccDestroyKeyPair
0x18007f953  test    r12, r12
0x18007f956  jz      short loc_18007F985
0x18007f958  mov     rcx, r12; P
0x18007f95b  call    FreeGenericEccKeyParameters
0x18007f960  jmp     short loc_18007F985
0x18007f962  mov     ebx, 0C0000095h
0x18007f967  mov     r9d, 8E7h
0x18007f96d  mov     ecx, 0C0000095h
0x18007f972  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007f979  lea     rdx, aStatus; "Status"
0x18007f980  call    DebugTraceError
0x18007f985  mov     eax, ebx
0x18007f987  mov     rbx, [rsp+50h+arg_0]
0x18007f98f  add     rsp, 50h
0x18007f993  pop     r15
0x18007f995  pop     r14
0x18007f997  pop     r13
0x18007f999  pop     r12
0x18007f99b  pop     rdi
0x18007f99c  pop     rsi
0x18007f99d  pop     rbp
0x18007f99e  retn
```

# ImportEccKeyBlobWithParameters

- ea: `0x180075df0`
- end: `0x180076210`
- name: `ImportEccKeyBlobWithParameters`
- size: `1056`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800779e8`

## callees

- `0x18000743c`
- `0x18003e004`
- `0x1800421d8`
- `0x180044134`
- `0x180046634`
- `0x180047628`
- `0x18004788c`
- `0x180048770`
- `0x1800496a4`
- `0x1800497b8`
- `0x180075df0`
- `0x180076d9c`
- `0x180077efc`
- `0x180077f74`

## string_xrefs

- `0x180075f74`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800761a0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800761e2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

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
0x180075df0  mov     [rsp-38h+arg_0], rbx
0x180075df5  mov     [rsp-38h+arg_18], r9d
0x180075dfa  push    rbp
0x180075dfb  push    rsi
0x180075dfc  push    rdi
0x180075dfd  push    r12
0x180075dff  push    r13
0x180075e01  push    r14
0x180075e03  push    r15
0x180075e05  mov     rbp, rsp
0x180075e08  sub     rsp, 50h
0x180075e0c  xor     edi, edi
0x180075e0e  xor     r12d, r12d
0x180075e11  mov     [rbp+var_10], rdi
0x180075e15  mov     r10d, r9d
0x180075e18  mov     [rbp+P], r12
0x180075e1c  mov     r15d, r8d
0x180075e1f  mov     dword ptr [rbp+arg_8], edi
0x180075e22  mov     rsi, rdx
0x180075e25  mov     [rbp+arg_10], edi
0x180075e28  mov     r14, rcx
0x180075e2b  cmp     r8d, 20h ; ' '
0x180075e2f  jnb     short loc_180075E46
0x180075e31  mov     r9d, 8DEh
0x180075e37  mov     ebx, 0C0000023h
0x180075e3c  mov     ecx, 0C0000023h
0x180075e41  jmp     loc_1800761E2
0x180075e46  mov     eax, [rdx+10h]
0x180075e49  imul    rcx, rax, 7
0x180075e4d  mov     eax, 0FFFFFFFFh
0x180075e52  cmp     rcx, rax
0x180075e55  ja      loc_1800761D2
0x180075e5b  lea     eax, [rcx+20h]
0x180075e5e  cmp     eax, ecx
0x180075e60  jb      loc_180076190
0x180075e66  mov     r8d, [rdx+14h]
0x180075e6a  lea     ecx, [r8+rax]
0x180075e6e  cmp     ecx, eax
0x180075e70  jb      loc_180076190
0x180075e76  mov     edx, [rdx+18h]
0x180075e79  add     edx, ecx
0x180075e7b  cmp     edx, ecx
0x180075e7d  jb      loc_180076190
0x180075e83  mov     ecx, [rsi+1Ch]
0x180075e86  add     ecx, edx
0x180075e88  cmp     ecx, edx
0x180075e8a  jb      loc_180076190
0x180075e90  mov     r13d, [rbp+arg_20]
0x180075e94  test    r13d, r13d
0x180075e97  jz      short loc_180075EA7
0x180075e99  lea     eax, [rcx+r8]
0x180075e9d  cmp     eax, ecx
0x180075e9f  jb      loc_180076190
0x180075ea5  mov     ecx, eax
0x180075ea7  cmp     r15d, ecx
0x180075eaa  jnb     short loc_180075EB4
0x180075eac  mov     r9d, 8FBh
0x180075eb2  jmp     short loc_180075E37
0x180075eb4  mov     rdx, [r14+10h]
0x180075eb8  lea     rax, [rbp+arg_10]
0x180075ebc  mov     ecx, [r14+8]
0x180075ec0  mov     r9d, r13d
0x180075ec3  mov     r8d, r10d
0x180075ec6  mov     [rsp+50h+var_30], rax
0x180075ecb  call    MSCryptEcGetKeyMagicForAlgId
0x180075ed0  mov     ebx, eax
0x180075ed2  test    eax, eax
0x180075ed4  jns     short loc_180075EE3
0x180075ed6  mov     r9d, 910h
0x180075edc  mov     ecx, eax
0x180075ede  jmp     loc_1800761E2
0x180075ee3  mov     ecx, [rsi]
0x180075ee5  mov     eax, [rbp+arg_10]
0x180075ee8  cmp     ecx, eax
0x180075eea  jz      short loc_180075F4C
0x180075eec  cmp     [r14+10h], rdi
0x180075ef0  jnz     short loc_180075F44
0x180075ef2  mov     edx, 56444345h
0x180075ef7  cmp     eax, edx
0x180075ef9  jz      short loc_180075F4C
0x180075efb  mov     r8d, 50444345h
0x180075f01  cmp     eax, r8d
0x180075f04  jz      short loc_180075F4C
0x180075f06  mov     r9d, 564B4345h
0x180075f0c  cmp     eax, r9d
0x180075f0f  jz      short loc_180075F4C
0x180075f11  mov     r10d, 504B4345h
0x180075f17  cmp     eax, r10d
0x180075f1a  jz      short loc_180075F4C
0x180075f1c  cmp     ecx, edx
0x180075f1e  jz      short loc_180075F2F
0x180075f20  cmp     ecx, r8d
0x180075f23  jz      short loc_180075F2F
0x180075f25  cmp     ecx, r9d
0x180075f28  jz      short loc_180075F2F
0x180075f2a  cmp     ecx, r10d
0x180075f2d  jnz     short loc_180075F4C
0x180075f2f  mov     r9d, 927h
0x180075f35  mov     ebx, 0C000000Dh
0x180075f3a  mov     ecx, 0C000000Dh
0x180075f3f  jmp     loc_1800761E2
0x180075f44  mov     r9d, 92Eh
0x180075f4a  jmp     short loc_180075F35
0x180075f4c  mov     r9, r14
0x180075f4f  lea     rdx, [rbp+arg_8]
0x180075f53  xor     r8d, r8d
0x180075f56  lea     rcx, [rbp+var_10]
0x180075f5a  call    AllocateGenericEccKey
0x180075f5f  mov     ebx, eax
0x180075f61  test    eax, eax
0x180075f63  jns     short loc_180075F89
0x180075f65  mov     r9d, 936h
0x180075f6b  mov     ecx, eax
0x180075f6d  lea     rdx, aStatus; "Status"
0x180075f74  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180075f7b  call    DebugTraceError
0x180075f80  mov     rdi, [rbp+var_10]
0x180075f84  jmp     loc_1800761B3
0x180075f89  mov     eax, [rsi+10h]
0x180075f8c  add     eax, eax
0x180075f8e  sub     r15d, eax
0x180075f91  add     r15d, 0FFFFFFFCh
0x180075f95  test    r13d, r13d
0x180075f98  jz      short loc_180075F9E
0x180075f9a  sub     r15d, [rsi+14h]
0x180075f9e  mov     rdi, [rbp+var_10]
0x180075fa2  cmp     [r14+10h], r12
0x180075fa6  jz      short loc_180076003
0x180075fa8  mov     edx, [r14+8]
0x180075fac  lea     r8, [rsi+4]
0x180075fb0  mov     [rsp+50h+var_28], r12d
0x180075fb5  lea     rcx, [rbp+P]
0x180075fb9  mov     r9d, r15d
0x180075fbc  mov     [rsp+50h+var_30], r12
0x180075fc1  call    AssignGenericDomainParameters
0x180075fc6  mov     r12, [rbp+P]
0x180075fca  mov     ebx, eax
0x180075fcc  test    eax, eax
0x180075fce  js      loc_1800761B3
0x180075fd4  test    r12, r12
0x180075fd7  jz      short loc_18007603B
0x180075fd9  mov     r13, [r14+10h]
0x180075fdd  mov     rdx, [r12]
0x180075fe1  mov     rcx, [r13+0]
0x180075fe5  call    TestIfCurveParametersAreEqual
0x180075fea  test    eax, eax
0x180075fec  jz      short loc_18007603B
0x180075fee  test    r13, r13
0x180075ff1  jz      short loc_180076003
0x180075ff3  mov     rcx, [r13+0]
0x180075ff7  mov     rdx, rsi
0x180075ffa  call    TestIfSeedIsEqual
0x180075fff  test    eax, eax
0x180076001  jnz     short loc_180076057
0x180076003  mov     edx, [r14+8]
0x180076007  lea     rcx, [rdi+10h]
0x18007600b  mov     [rsp+50h+var_28], 0
0x180076013  lea     r8, [rsi+4]
0x180076017  mov     r9d, r15d
0x18007601a  mov     [rsp+50h+var_30], 0
0x180076023  call    AssignGenericDomainParameters
0x180076028  mov     ebx, eax
0x18007602a  test    eax, eax
0x18007602c  jns     short loc_180076050
0x18007602e  mov     r9d, 962h
0x180076034  mov     ecx, eax
0x180076036  jmp     loc_1800761A0
0x18007603b  mov     ebx, 0C000000Dh
0x180076040  mov     r9d, 954h
0x180076046  mov     ecx, 0C000000Dh
0x18007604b  jmp     loc_180075F6D
0x180076050  mov     dword ptr [rdi+20h], 0
0x180076057  mov     rax, [rdi+10h]
0x18007605b  xor     r15d, r15d
0x18007605e  mov     [rbp+arg_8], rax
0x180076062  mov     r8, [rax]
0x180076065  mov     r9d, [r8+0Ch]
0x180076069  mov     r11d, [r8+10h]
0x18007606d  mov     edx, [r8+18h]
0x180076071  mov     r10d, [r8+14h]
0x180076075  add     rdx, r11
0x180076078  lea     ecx, [r9+r9*4]
0x18007607c  add     r10, 20h ; ' '
0x180076080  add     rdx, rcx
0x180076083  add     r10, rdx
0x180076086  lea     edx, [r9+r9]
0x18007608a  add     r10, rsi
0x18007608d  mov     rcx, r10
0x180076090  call    IsAllZeros
0x180076095  mov     ecx, edx
0x180076097  xor     edx, edx
0x180076099  test    eax, eax
0x18007609b  cmovz   edx, ecx
0x18007609e  xor     r14d, r14d
0x1800760a1  test    eax, eax
0x1800760a3  mov     [rbp+P], rdx
0x1800760a7  lea     rax, [rcx+r10]
0x1800760ab  mov     ecx, [rbp+arg_20]
0x1800760ae  cmovz   r14, r10
0x1800760b2  test    ecx, ecx
0x1800760b4  cmovnz  r15d, r11d
0x1800760b8  neg     ecx
0x1800760ba  mov     ecx, [rbp+arg_28]
0x1800760bd  mov     [rbp+var_10], r15
0x1800760c1  sbb     r15, r15
0x1800760c4  and     r15, rax
0x1800760c7  test    cl, 20h
0x1800760ca  jz      short loc_1800760EB
0x1800760cc  test    r15, r15
0x1800760cf  jz      short loc_1800760D6
0x1800760d1  test    r14, r14
0x1800760d4  jnz     short loc_1800760EB
0x1800760d6  mov     ebx, 0C000000Dh
0x1800760db  mov     r9d, 98Dh
0x1800760e1  mov     ecx, 0C000000Dh
0x1800760e6  jmp     loc_1800761A0
0x1800760eb  call    BCryptFlagsToSymCryptKeyValidationFlags
0x1800760f0  mov     edx, [rbp+arg_18]
0x1800760f3  mov     r13d, eax
0x1800760f6  mov     rcx, [rbp+arg_8]
0x1800760fa  neg     edx
0x1800760fc  sbb     esi, esi
0x1800760fe  and     esi, 0FFFFF000h
0x180076104  mov     rcx, [rcx+8]
0x180076108  add     esi, 2000h
0x18007610e  call    SymCryptEckeyAllocate
0x180076113  mov     [rdi+18h], rax
0x180076117  mov     rcx, rax
0x18007611a  test    rax, rax
0x18007611d  jnz     short loc_180076131
0x18007611f  mov     ebx, 0C0000017h
0x180076124  mov     r9d, 998h
0x18007612a  mov     ecx, 0C0000017h
0x18007612f  jmp     short loc_1800761A0
0x180076131  mov     rax, [rdi+10h]
0x180076135  or      esi, r13d
0x180076138  mov     r9, [rbp+P]
0x18007613c  mov     r8, r14
0x18007613f  mov     rdx, [rbp+var_10]
0x180076143  mov     [rsp+50h+var_18], rcx
0x180076148  mov     rcx, r15
0x18007614b  mov     r10, [rax]
0x18007614e  xor     eax, eax
0x180076150  mov     [rsp+50h+var_20], esi
0x180076154  mov     [rsp+50h+var_28], 2
0x18007615c  cmp     dword ptr [r10+4], 3
0x180076161  setnz   al
0x180076164  inc     eax
0x180076166  mov     dword ptr [rsp+50h+var_30], eax
0x18007616a  call    SymCryptEckeySetValue
0x18007616f  test    eax, eax
0x180076171  jz      short loc_180076187
0x180076173  mov     ecx, eax
0x180076175  call    SymcryptErrorCodeToNtStatus
0x18007617a  mov     ebx, eax
0x18007617c  mov     r9d, 9A8h
0x180076182  jmp     loc_180076034
0x180076187  mov     rax, [rbp+arg_30]
0x18007618b  mov     [rax], rdi
0x18007618e  jmp     short loc_1800761C3
0x180076190  mov     ebx, 0C0000095h
0x180076195  mov     r9d, 8F2h
0x18007619b  mov     ecx, 0C0000095h
0x1800761a0  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800761a7  lea     rdx, aStatus; "Status"
0x1800761ae  call    DebugTraceError
0x1800761b3  test    rdi, rdi
0x1800761b6  jz      short loc_1800761C3
0x1800761b8  mov     edx, [rbp+arg_18]
0x1800761bb  mov     rcx, rdi
0x1800761be  call    MSCryptEccDestroyKeyPair
0x1800761c3  test    r12, r12
0x1800761c6  jz      short loc_1800761F5
0x1800761c8  mov     rcx, r12; P
0x1800761cb  call    FreeGenericEccKeyParameters
0x1800761d0  jmp     short loc_1800761F5
0x1800761d2  mov     ebx, 0C0000095h
0x1800761d7  mov     r9d, 8E7h
0x1800761dd  mov     ecx, 0C0000095h
0x1800761e2  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800761e9  lea     rdx, aStatus; "Status"
0x1800761f0  call    DebugTraceError
0x1800761f5  mov     eax, ebx
0x1800761f7  mov     rbx, [rsp+50h+arg_0]
0x1800761ff  add     rsp, 50h
0x180076203  pop     r15
0x180076205  pop     r14
0x180076207  pop     r13
0x180076209  pop     r12
0x18007620b  pop     rdi
0x18007620c  pop     rsi
0x18007620d  pop     rbp
0x18007620e  retn
```

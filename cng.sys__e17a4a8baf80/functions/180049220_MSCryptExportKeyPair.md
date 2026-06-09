# MSCryptExportKeyPair

- ea: `0x180049220`
- end: `0x180049676`
- name: `MSCryptExportKeyPair`
- size: `1110`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18007e59c`
- `0x180081874`

## callees

- `0x18001155c`
- `0x1800123d0`
- `0x1800288a0`
- `0x180049220`
- `0x18004967c`
- `0x180049c28`
- `0x1800517b4`
- `0x180051dd0`
- `0x1800954c8`
- `0x1800a4232`

## string_xrefs

- `0x1800495a3`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18004964c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptExportKeyPair(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        __int64 a4,
        unsigned int a5,
        unsigned int *a6,
        int a7)
{
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // r8
  __int64 v14; // r14
  __int64 v15; // rsi
  __int64 v16; // rax
  unsigned int v17; // edi
  unsigned int v18; // r15d
  int v19; // r13d
  __int64 v20; // rcx
  __int64 v21; // r8
  unsigned int v22; // edx
  __int64 v23; // rdx
  __int64 v24; // r12
  __int64 v25; // r10
  __int64 v26; // rcx
  unsigned int v27; // r11d
  __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // rdi
  int v35; // esi
  unsigned int v36; // ecx
  unsigned int Value; // eax
  __int64 v38; // r15
  __int64 i; // rdi
  __int64 v40; // r8
  unsigned int Uint64; // eax
  int v42; // edx
  unsigned int v43; // eax
  unsigned int CrtValue; // eax
  __int64 v46; // [rsp+50h] [rbp-71h]
  __int64 v47; // [rsp+58h] [rbp-69h]
  __int64 v48; // [rsp+60h] [rbp-61h]
  __int64 v49; // [rsp+68h] [rbp-59h]
  __int64 v50; // [rsp+70h] [rbp-51h]
  __int128 v51; // [rsp+78h] [rbp-49h]
  __int128 v52; // [rsp+88h] [rbp-39h]
  __int128 v53; // [rsp+98h] [rbp-29h] BYREF
  __int128 v54; // [rsp+A8h] [rbp-19h] BYREF

  v51 = 0;
  v52 = 0;
  v54 = 0;
  v53 = 0;
  if ( a7 )
  {
    v9 = -1073741811;
    v10 = 1164;
    v11 = 3221225485LL;
LABEL_56:
    DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", v10);
    return v9;
  }
  if ( a2 )
  {
    v10 = 1171;
LABEL_5:
    v9 = -1073741637;
    v11 = 3221225659LL;
    goto LABEL_56;
  }
  v12 = validateMSCryptRsaKey(a1);
  v14 = v12;
  if ( !v12 || *(_DWORD *)(v12 + 16) == (_DWORD)v13 || (v15 = *(_QWORD *)(v12 + 32)) == 0 )
  {
    v9 = -1073741816;
    v10 = 1181;
    v11 = 3221225480LL;
    goto LABEL_56;
  }
  v16 = *(_QWORD *)(v15 + 56);
  v49 = v13;
  v48 = v13;
  v47 = v13;
  v46 = v13;
  if ( HIDWORD(v16) )
    v17 = ((__int64 (*)(void))SymCryptUint32Bytesize)() + 4;
  else
    v17 = SymCryptUint32Bytesize((unsigned int)v16);
  v18 = (unsigned int)(*(_DWORD *)(v15 + 16) + 7) >> 3;
  v19 = wcscmp_0(a3, L"RSAFULLPRIVATEBLOB");
  if ( !wcscmp_0(a3, L"RSAPUBLICBLOB") || !wcscmp_0(a3, L"PUBLICBLOB") )
  {
    v36 = v17 + v18 + 24;
    *a6 = v36;
    if ( !a4 )
      return 0;
    if ( a5 < v36 )
    {
      v9 = -1073741789;
      v10 = 1210;
      v11 = 3221225507LL;
      goto LABEL_56;
    }
    v35 = 0;
    *(_DWORD *)a4 = 826364754;
    v24 = v17;
    *(_DWORD *)(a4 + 4) = *(_DWORD *)(v14 + 12);
    v25 = v17 + a4 + 24;
    *(_DWORD *)(a4 + 8) = v17;
    *(_DWORD *)(a4 + 12) = v18;
    *(_QWORD *)(a4 + 16) = 0;
    v34 = *(_QWORD *)(v14 + 32);
    v27 = v18;
  }
  else
  {
    if ( wcscmp_0(a3, L"RSAPRIVATEBLOB") && wcscmp_0(a3, L"PRIVATEBLOB") && v19 )
    {
      v10 = 1331;
      goto LABEL_5;
    }
    if ( !*(_BYTE *)(v15 + 8) )
      return (unsigned int)-1073741811;
    v20 = (unsigned int)(*(_DWORD *)(v15 + 32) + 7) >> 3;
    v21 = (unsigned int)(*(_DWORD *)(v15 + 36) + 7) >> 3;
    v22 = v17 + v18 + v21 + v20 + 24;
    *a6 = v22;
    if ( !v19 )
    {
      v22 = v17 + v20 + 2 * (v18 + v21 + v20 + 12);
      *a6 = v22;
    }
    if ( !a4 )
      return 0;
    if ( a5 < v22 )
      return (unsigned int)-1073741789;
    *(_DWORD *)a4 = 843141970;
    if ( !v19 )
      *(_DWORD *)a4 = 859919186;
    v23 = (unsigned int)v20;
    v24 = v17;
    v25 = v17 + a4 + 24;
    *(_DWORD *)(a4 + 4) = *(_DWORD *)(v14 + 12);
    *(_DWORD *)(a4 + 16) = v20;
    *(_DWORD *)(a4 + 8) = v17;
    *(_DWORD *)(a4 + 12) = v18;
    v26 = v18 + v25 + v20;
    *(_DWORD *)(a4 + 20) = v21;
    v27 = v18;
    *(_QWORD *)&v51 = v18 + v25;
    *(_QWORD *)&v52 = v23;
    *((_QWORD *)&v51 + 1) = v26;
    *((_QWORD *)&v52 + 1) = (unsigned int)v21;
    if ( v19 )
    {
      v30 = v49;
      v31 = v49;
      v32 = v49;
      v33 = v49;
    }
    else
    {
      v28 = v21 + v26;
      *(_QWORD *)&v53 = v23;
      v29 = v21 + v26 + v23;
      *(_QWORD *)&v54 = v28;
      v30 = v21 + v29;
      *((_QWORD *)&v54 + 1) = v29;
      v31 = (unsigned int)v23;
      *((_QWORD *)&v53 + 1) = (unsigned int)v21;
      v32 = v30 + v23;
      v33 = v18;
    }
    v34 = *(_QWORD *)(v14 + 32);
    v46 = v33;
    v47 = v32;
    v48 = v31;
    v49 = v30;
    if ( !*(_BYTE *)(v34 + 8) )
    {
      Value = 32782;
LABEL_50:
      v43 = SymcryptErrorCodeToNtStatus(Value);
      v10 = 1349;
LABEL_51:
      v9 = v43;
      v11 = v43;
      goto LABEL_56;
    }
    v35 = 2;
  }
  v50 = v34;
  if ( v25 )
  {
    Value = SymCryptFdefRawGetValue(
              (unsigned int)*(_QWORD *)(v34 + 120) + 128,
              *(_DWORD *)(*(_QWORD *)(v34 + 120) + 100LL),
              v25,
              v27,
              2);
    if ( Value )
      goto LABEL_50;
  }
  v38 = *(_QWORD *)(v34 + 56);
  if ( v35 )
  {
    for ( i = 0; (unsigned int)i < 2; i = (unsigned int)(i + 1) )
    {
      v40 = *((_QWORD *)&v51 + i);
      if ( v40 )
      {
        Value = SymCryptFdefRawGetValue(
                  (unsigned int)*(_QWORD *)(v50 + 8 * i + 128) + 128,
                  *(_DWORD *)(*(_QWORD *)(v50 + 8 * i + 128) + 100LL),
                  v40,
                  *((_QWORD *)&v52 + i),
                  2);
        if ( Value )
          goto LABEL_50;
      }
    }
  }
  Uint64 = SymCryptStoreMsbFirstUint64(v38, a4 + 24, v24);
  if ( !Uint64 )
  {
    if ( !v19 )
    {
      CrtValue = SymCryptRsakeyGetCrtValue(
                   *(_QWORD *)(v14 + 32),
                   (unsigned int)&v54,
                   (unsigned int)&v53,
                   v35,
                   v49,
                   v48,
                   v47,
                   v46);
      if ( CrtValue )
      {
        v43 = SymcryptErrorCodeToNtStatus(CrtValue);
        v10 = 1377;
        goto LABEL_51;
      }
    }
    return 0;
  }
  v9 = SymcryptErrorCodeToNtStatus(Uint64);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v42,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
      (unsigned int)"Status",
      v9,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
      77);
  return v9;
}

```

## disassembly

```asm
0x180049220  push    rbp
0x180049222  push    rbx
0x180049223  push    rsi
0x180049224  push    rdi
0x180049225  push    r12
0x180049227  push    r13
0x180049229  push    r14
0x18004922b  push    r15
0x18004922d  lea     rbp, [rsp-7]
0x180049232  sub     rsp, 0C8h
0x180049239  xorps   xmm0, xmm0
0x18004923c  xorps   xmm1, xmm1
0x18004923f  mov     r12, r8
0x180049242  mov     rbx, r9
0x180049245  xor     r8d, r8d
0x180049248  movups  [rbp+3Fh+var_88], xmm0
0x18004924c  movups  [rbp+3Fh+var_78], xmm1
0x180049250  movups  [rbp+3Fh+var_58], xmm0
0x180049254  movups  [rbp+3Fh+var_68], xmm1
0x180049258  cmp     [rbp+3Fh+arg_30], r8d
0x18004925c  jz      short loc_180049273
0x18004925e  mov     ebx, 0C000000Dh
0x180049263  mov     r9d, 48Ch
0x180049269  mov     ecx, 0C000000Dh
0x18004926e  jmp     loc_18004964C
0x180049273  test    rdx, rdx
0x180049276  jz      short loc_18004928D
0x180049278  mov     r9d, 493h
0x18004927e  mov     ebx, 0C00000BBh
0x180049283  mov     ecx, 0C00000BBh
0x180049288  jmp     loc_18004964C
0x18004928d  call    validateMSCryptRsaKey
0x180049292  mov     r14, rax
0x180049295  test    rax, rax
0x180049298  jz      loc_18004963C
0x18004929e  cmp     [rax+10h], r8d
0x1800492a2  jz      loc_18004963C
0x1800492a8  mov     rsi, [rax+20h]
0x1800492ac  test    rsi, rsi
0x1800492af  jz      loc_18004963C
0x1800492b5  mov     rax, [rsi+38h]
0x1800492b9  mov     rcx, rax
0x1800492bc  mov     [rbp+3Fh+var_98], r8
0x1800492c0  shr     rcx, 20h
0x1800492c4  mov     [rbp+3Fh+var_A0], r8
0x1800492c8  mov     [rbp+3Fh+var_A8], r8
0x1800492cc  mov     [rbp+3Fh+var_B0], r8
0x1800492d0  test    ecx, ecx
0x1800492d2  jnz     short loc_1800492DF
0x1800492d4  mov     ecx, eax
0x1800492d6  call    SymCryptUint32Bytesize
0x1800492db  mov     edi, eax
0x1800492dd  jmp     short loc_1800492E7
0x1800492df  call    SymCryptUint32Bytesize
0x1800492e4  lea     edi, [rax+4]
0x1800492e7  mov     r15d, [rsi+10h]
0x1800492eb  lea     rdx, aRsafullprivate; "RSAFULLPRIVATEBLOB"
0x1800492f2  add     r15d, 7
0x1800492f6  mov     rcx, r12; Str1
0x1800492f9  shr     r15d, 3
0x1800492fd  call    wcscmp_0
0x180049302  lea     rdx, aRsapublicblob; "RSAPUBLICBLOB"
0x180049309  mov     rcx, r12; Str1
0x18004930c  mov     r13d, eax
0x18004930f  call    wcscmp_0
0x180049314  test    eax, eax
0x180049316  jz      loc_18004947A
0x18004931c  lea     rdx, aPublicblob; "PUBLICBLOB"
0x180049323  mov     rcx, r12; Str1
0x180049326  call    wcscmp_0
0x18004932b  test    eax, eax
0x18004932d  jz      loc_18004947A
0x180049333  lea     rdx, aRsaprivateblob; "RSAPRIVATEBLOB"
0x18004933a  mov     rcx, r12; Str1
0x18004933d  call    wcscmp_0
0x180049342  test    eax, eax
0x180049344  jz      short loc_180049369
0x180049346  lea     rdx, aPrivateblob; "PRIVATEBLOB"
0x18004934d  mov     rcx, r12; Str1
0x180049350  call    wcscmp_0
0x180049355  test    eax, eax
0x180049357  jz      short loc_180049369
0x180049359  test    r13d, r13d
0x18004935c  jz      short loc_180049369
0x18004935e  mov     r9d, 533h
0x180049364  jmp     loc_18004927E
0x180049369  cmp     byte ptr [rsi+8], 0
0x18004936d  jnz     short loc_180049379
0x18004936f  mov     ebx, 0C000000Dh
0x180049374  jmp     loc_18004965F
0x180049379  mov     ecx, [rsi+20h]
0x18004937c  mov     r8d, [rsi+24h]
0x180049380  add     ecx, 7
0x180049383  mov     r9, [rbp+3Fh+arg_28]
0x180049387  add     r8d, 7
0x18004938b  shr     ecx, 3
0x18004938e  shr     r8d, 3
0x180049392  lea     edx, [rcx+18h]
0x180049395  add     edx, r8d
0x180049398  add     edx, r15d
0x18004939b  add     edx, edi
0x18004939d  mov     [r9], edx
0x1800493a0  test    r13d, r13d
0x1800493a3  jnz     short loc_1800493B6
0x1800493a5  lea     edx, [rcx+0Ch]
0x1800493a8  add     edx, r8d
0x1800493ab  add     edx, r15d
0x1800493ae  lea     edx, [rcx+rdx*2]
0x1800493b1  add     edx, edi
0x1800493b3  mov     [r9], edx
0x1800493b6  test    rbx, rbx
0x1800493b9  jz      loc_18004948B
0x1800493bf  cmp     [rbp+3Fh+arg_20], edx
0x1800493c2  jnb     short loc_1800493CE
0x1800493c4  mov     ebx, 0C0000023h
0x1800493c9  jmp     loc_18004965F
0x1800493ce  mov     dword ptr [rbx], 32415352h
0x1800493d4  test    r13d, r13d
0x1800493d7  jnz     short loc_1800493DF
0x1800493d9  mov     dword ptr [rbx], 33415352h
0x1800493df  mov     eax, [r14+0Ch]
0x1800493e3  lea     r10, [rbx+18h]
0x1800493e7  mov     edx, ecx
0x1800493e9  mov     r12d, edi
0x1800493ec  add     r10, r12
0x1800493ef  mov     [rbx+4], eax
0x1800493f2  mov     [rbx+10h], ecx
0x1800493f5  mov     r9d, r8d
0x1800493f8  mov     [rbx+8], edi
0x1800493fb  lea     rax, [r15+r10]
0x1800493ff  mov     [rbx+0Ch], r15d
0x180049403  add     rcx, rax
0x180049406  mov     [rbx+14h], r8d
0x18004940a  mov     r11d, r15d
0x18004940d  mov     qword ptr [rbp+3Fh+var_88], rax
0x180049411  mov     qword ptr [rbp+3Fh+var_78], rdx
0x180049415  mov     qword ptr [rbp+3Fh+var_88+8], rcx
0x180049419  mov     qword ptr [rbp+3Fh+var_78+8], r9
0x18004941d  test    r13d, r13d
0x180049420  jnz     short loc_180049448
0x180049422  lea     rax, [r8+rcx]
0x180049426  mov     qword ptr [rbp+3Fh+var_68], rdx
0x18004942a  lea     rcx, [rax+rdx]
0x18004942e  mov     qword ptr [rbp+3Fh+var_58], rax
0x180049432  lea     rax, [r8+rcx]
0x180049436  mov     qword ptr [rbp+3Fh+var_58+8], rcx
0x18004943a  mov     ecx, edx
0x18004943c  mov     qword ptr [rbp+3Fh+var_68+8], r9
0x180049440  add     rdx, rax
0x180049443  mov     r8d, r11d
0x180049446  jmp     short loc_180049455
0x180049448  mov     rax, [rbp+3Fh+var_98]
0x18004944c  mov     rcx, rax
0x18004944f  mov     rdx, rax
0x180049452  mov     r8, rax
0x180049455  mov     rdi, [r14+20h]
0x180049459  mov     [rbp+3Fh+var_B0], r8
0x18004945d  mov     [rbp+3Fh+var_A8], rdx
0x180049461  mov     [rbp+3Fh+var_A0], rcx
0x180049465  cmp     byte ptr [rdi+8], 0
0x180049469  mov     [rbp+3Fh+var_98], rax
0x18004946d  jz      loc_1800495CC
0x180049473  mov     esi, 2
0x180049478  jmp     short loc_1800494D7
0x18004947a  mov     rax, [rbp+3Fh+arg_28]
0x18004947e  lea     ecx, [r15+18h]
0x180049482  add     ecx, edi
0x180049484  mov     [rax], ecx
0x180049486  test    rbx, rbx
0x180049489  jnz     short loc_180049492
0x18004948b  xor     ebx, ebx
0x18004948d  jmp     loc_18004965F
0x180049492  cmp     [rbp+3Fh+arg_20], ecx
0x180049495  jnb     short loc_1800494AC
0x180049497  mov     ebx, 0C0000023h
0x18004949c  mov     r9d, 4BAh
0x1800494a2  mov     ecx, 0C0000023h
0x1800494a7  jmp     loc_18004964C
0x1800494ac  xor     esi, esi
0x1800494ae  mov     dword ptr [rbx], 31415352h
0x1800494b4  mov     eax, [r14+0Ch]
0x1800494b8  lea     r10, [rbx+18h]
0x1800494bc  mov     r12d, edi
0x1800494bf  mov     [rbx+4], eax
0x1800494c2  add     r10, r12
0x1800494c5  mov     [rbx+8], edi
0x1800494c8  mov     [rbx+0Ch], r15d
0x1800494cc  mov     [rbx+10h], rsi
0x1800494d0  mov     rdi, [r14+20h]
0x1800494d4  mov     r11d, r15d
0x1800494d7  xor     eax, eax
0x1800494d9  mov     [rbp+3Fh+var_90], rdi
0x1800494dd  test    r10, r10
0x1800494e0  jz      short loc_18004950B
0x1800494e2  mov     rdx, [rdi+78h]
0x1800494e6  mov     r9, r11
0x1800494e9  mov     r8, r10
0x1800494ec  mov     dword ptr [rsp+100h+var_E0], 2
0x1800494f4  lea     rcx, [rdx+80h]
0x1800494fb  mov     edx, [rdx+64h]
0x1800494fe  call    SymCryptFdefRawGetValue
0x180049503  test    eax, eax
0x180049505  jnz     loc_1800495D1
0x18004950b  mov     r15, [rdi+38h]
0x18004950f  test    esi, esi
0x180049511  jz      short loc_180049561
0x180049513  cmp     esi, 2
0x180049516  jnz     loc_1800495CC
0x18004951c  xor     edi, edi
0x18004951e  cmp     edi, 2
0x180049521  jnb     short loc_18004955D
0x180049523  mov     r8, qword ptr [rbp+rdi*8+3Fh+var_88]
0x180049528  test    r8, r8
0x18004952b  jz      short loc_180049559
0x18004952d  mov     rax, [rbp+3Fh+var_90]
0x180049531  mov     r9, qword ptr [rbp+rdi*8+3Fh+var_78]
0x180049536  mov     dword ptr [rsp+100h+var_E0], 2
0x18004953e  mov     rdx, [rax+rdi*8+80h]
0x180049546  lea     rcx, [rdx+80h]
0x18004954d  mov     edx, [rdx+64h]
0x180049550  call    SymCryptFdefRawGetValue
0x180049555  test    eax, eax
0x180049557  jnz     short loc_1800495D1
0x180049559  inc     edi
0x18004955b  jmp     short loc_18004951E
0x18004955d  test    eax, eax
0x18004955f  jnz     short loc_1800495D1
0x180049561  lea     rdx, [rbx+18h]
0x180049565  mov     r8, r12
0x180049568  mov     rcx, r15
0x18004956b  call    SymCryptStoreMsbFirstUint64
0x180049570  test    eax, eax
0x180049572  jz      short loc_1800495E4
0x180049574  mov     ecx, eax
0x180049576  call    SymcryptErrorCodeToNtStatus
0x18004957b  mov     ebx, eax
0x18004957d  mov     rcx, cs:WPP_GLOBAL_Control
0x180049584  lea     rax, WPP_GLOBAL_Control
0x18004958b  cmp     rcx, rax
0x18004958e  jz      loc_18004965F
0x180049594  mov     eax, [rcx+2Ch]
0x180049597  test    al, 1
0x180049599  jz      loc_18004965F
0x18004959f  mov     rcx, [rcx+18h]
0x1800495a3  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800495aa  mov     dword ptr [rsp+100h+var_D0], 54Dh
0x1800495b2  lea     r9, aStatus; "Status"
0x1800495b9  mov     [rsp+100h+var_D8], r8
0x1800495be  mov     dword ptr [rsp+100h+var_E0], ebx
0x1800495c2  call    WPP_SF_sDsd
0x1800495c7  jmp     loc_18004965F
0x1800495cc  mov     eax, 800Eh
0x1800495d1  mov     ecx, eax
0x1800495d3  call    SymcryptErrorCodeToNtStatus
0x1800495d8  mov     r9d, 545h
0x1800495de  mov     ebx, eax
0x1800495e0  mov     ecx, eax
0x1800495e2  jmp     short loc_18004964C
0x1800495e4  test    r13d, r13d
0x1800495e7  jnz     loc_18004948B
0x1800495ed  mov     rax, [rbp+3Fh+var_B0]
0x1800495f1  lea     r8, [rbp+3Fh+var_68]
0x1800495f5  mov     rcx, [r14+20h]
0x1800495f9  lea     rdx, [rbp+3Fh+var_58]
0x1800495fd  mov     [rsp+100h+var_C8], rax
0x180049602  mov     r9d, esi
0x180049605  mov     rax, [rbp+3Fh+var_A8]
0x180049609  mov     [rsp+100h+var_D0], rax
0x18004960e  mov     rax, [rbp+3Fh+var_A0]
0x180049612  mov     [rsp+100h+var_D8], rax
0x180049617  mov     rax, [rbp+3Fh+var_98]
0x18004961b  mov     [rsp+100h+var_E0], rax
0x180049620  call    SymCryptRsakeyGetCrtValue
0x180049625  test    eax, eax
0x180049627  jz      loc_18004948B
0x18004962d  mov     ecx, eax
0x18004962f  call    SymcryptErrorCodeToNtStatus
0x180049634  mov     r9d, 561h
0x18004963a  jmp     short loc_1800495DE
0x18004963c  mov     ebx, 0C0000008h
0x180049641  mov     r9d, 49Dh
0x180049647  mov     ecx, 0C0000008h
0x18004964c  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180049653  lea     rdx, aStatus; "Status"
0x18004965a  call    DebugTraceError
0x18004965f  mov     eax, ebx
0x180049661  add     rsp, 0C8h
0x180049668  pop     r15
0x18004966a  pop     r14
0x18004966c  pop     r13
0x18004966e  pop     r12
0x180049670  pop     rdi
0x180049671  pop     rsi
0x180049672  pop     rbx
0x180049673  pop     rbp
0x180049674  retn
```

# MSCryptExportKeyPair

- ea: `0x18003f260`
- end: `0x18003f6b6`
- name: `MSCryptExportKeyPair`
- size: `1110`
- prototype: `__int64 __fastcall(__int64, __int64, const wchar_t *, __int64, unsigned int, unsigned int *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800743fc`
- `0x1800776d4`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x18001e770`
- `0x18003f260`
- `0x18003f6bc`
- `0x18003fc68`
- `0x1800476c4`
- `0x180047ce0`
- `0x18008b498`
- `0x18009d746`

## string_xrefs

- `0x18003f5e3`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18003f68c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

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
0x18003f260  push    rbp
0x18003f262  push    rbx
0x18003f263  push    rsi
0x18003f264  push    rdi
0x18003f265  push    r12
0x18003f267  push    r13
0x18003f269  push    r14
0x18003f26b  push    r15
0x18003f26d  lea     rbp, [rsp-7]
0x18003f272  sub     rsp, 0C8h
0x18003f279  xorps   xmm0, xmm0
0x18003f27c  xorps   xmm1, xmm1
0x18003f27f  mov     r12, r8
0x18003f282  mov     rbx, r9
0x18003f285  xor     r8d, r8d
0x18003f288  movups  [rbp+3Fh+var_88], xmm0
0x18003f28c  movups  [rbp+3Fh+var_78], xmm1
0x18003f290  movups  [rbp+3Fh+var_58], xmm0
0x18003f294  movups  [rbp+3Fh+var_68], xmm1
0x18003f298  cmp     [rbp+3Fh+arg_30], r8d
0x18003f29c  jz      short loc_18003F2B3
0x18003f29e  mov     ebx, 0C000000Dh
0x18003f2a3  mov     r9d, 48Ch
0x18003f2a9  mov     ecx, 0C000000Dh
0x18003f2ae  jmp     loc_18003F68C
0x18003f2b3  test    rdx, rdx
0x18003f2b6  jz      short loc_18003F2CD
0x18003f2b8  mov     r9d, 493h
0x18003f2be  mov     ebx, 0C00000BBh
0x18003f2c3  mov     ecx, 0C00000BBh
0x18003f2c8  jmp     loc_18003F68C
0x18003f2cd  call    validateMSCryptRsaKey
0x18003f2d2  mov     r14, rax
0x18003f2d5  test    rax, rax
0x18003f2d8  jz      loc_18003F67C
0x18003f2de  cmp     [rax+10h], r8d
0x18003f2e2  jz      loc_18003F67C
0x18003f2e8  mov     rsi, [rax+20h]
0x18003f2ec  test    rsi, rsi
0x18003f2ef  jz      loc_18003F67C
0x18003f2f5  mov     rax, [rsi+38h]
0x18003f2f9  mov     rcx, rax
0x18003f2fc  mov     [rbp+3Fh+var_98], r8
0x18003f300  shr     rcx, 20h
0x18003f304  mov     [rbp+3Fh+var_A0], r8
0x18003f308  mov     [rbp+3Fh+var_A8], r8
0x18003f30c  mov     [rbp+3Fh+var_B0], r8
0x18003f310  test    ecx, ecx
0x18003f312  jnz     short loc_18003F31F
0x18003f314  mov     ecx, eax
0x18003f316  call    SymCryptUint32Bytesize
0x18003f31b  mov     edi, eax
0x18003f31d  jmp     short loc_18003F327
0x18003f31f  call    SymCryptUint32Bytesize
0x18003f324  lea     edi, [rax+4]
0x18003f327  mov     r15d, [rsi+10h]
0x18003f32b  lea     rdx, aRsafullprivate; "RSAFULLPRIVATEBLOB"
0x18003f332  add     r15d, 7
0x18003f336  mov     rcx, r12; Str1
0x18003f339  shr     r15d, 3
0x18003f33d  call    wcscmp_0
0x18003f342  lea     rdx, aRsapublicblob; "RSAPUBLICBLOB"
0x18003f349  mov     rcx, r12; Str1
0x18003f34c  mov     r13d, eax
0x18003f34f  call    wcscmp_0
0x18003f354  test    eax, eax
0x18003f356  jz      loc_18003F4BA
0x18003f35c  lea     rdx, aPublicblob; "PUBLICBLOB"
0x18003f363  mov     rcx, r12; Str1
0x18003f366  call    wcscmp_0
0x18003f36b  test    eax, eax
0x18003f36d  jz      loc_18003F4BA
0x18003f373  lea     rdx, aRsaprivateblob; "RSAPRIVATEBLOB"
0x18003f37a  mov     rcx, r12; Str1
0x18003f37d  call    wcscmp_0
0x18003f382  test    eax, eax
0x18003f384  jz      short loc_18003F3A9
0x18003f386  lea     rdx, aPrivateblob; "PRIVATEBLOB"
0x18003f38d  mov     rcx, r12; Str1
0x18003f390  call    wcscmp_0
0x18003f395  test    eax, eax
0x18003f397  jz      short loc_18003F3A9
0x18003f399  test    r13d, r13d
0x18003f39c  jz      short loc_18003F3A9
0x18003f39e  mov     r9d, 533h
0x18003f3a4  jmp     loc_18003F2BE
0x18003f3a9  cmp     byte ptr [rsi+8], 0
0x18003f3ad  jnz     short loc_18003F3B9
0x18003f3af  mov     ebx, 0C000000Dh
0x18003f3b4  jmp     loc_18003F69F
0x18003f3b9  mov     ecx, [rsi+20h]
0x18003f3bc  mov     r8d, [rsi+24h]
0x18003f3c0  add     ecx, 7
0x18003f3c3  mov     r9, [rbp+3Fh+arg_28]
0x18003f3c7  add     r8d, 7
0x18003f3cb  shr     ecx, 3
0x18003f3ce  shr     r8d, 3
0x18003f3d2  lea     edx, [rcx+18h]
0x18003f3d5  add     edx, r8d
0x18003f3d8  add     edx, r15d
0x18003f3db  add     edx, edi
0x18003f3dd  mov     [r9], edx
0x18003f3e0  test    r13d, r13d
0x18003f3e3  jnz     short loc_18003F3F6
0x18003f3e5  lea     edx, [rcx+0Ch]
0x18003f3e8  add     edx, r8d
0x18003f3eb  add     edx, r15d
0x18003f3ee  lea     edx, [rcx+rdx*2]
0x18003f3f1  add     edx, edi
0x18003f3f3  mov     [r9], edx
0x18003f3f6  test    rbx, rbx
0x18003f3f9  jz      loc_18003F4CB
0x18003f3ff  cmp     [rbp+3Fh+arg_20], edx
0x18003f402  jnb     short loc_18003F40E
0x18003f404  mov     ebx, 0C0000023h
0x18003f409  jmp     loc_18003F69F
0x18003f40e  mov     dword ptr [rbx], 32415352h
0x18003f414  test    r13d, r13d
0x18003f417  jnz     short loc_18003F41F
0x18003f419  mov     dword ptr [rbx], 33415352h
0x18003f41f  mov     eax, [r14+0Ch]
0x18003f423  lea     r10, [rbx+18h]
0x18003f427  mov     edx, ecx
0x18003f429  mov     r12d, edi
0x18003f42c  add     r10, r12
0x18003f42f  mov     [rbx+4], eax
0x18003f432  mov     [rbx+10h], ecx
0x18003f435  mov     r9d, r8d
0x18003f438  mov     [rbx+8], edi
0x18003f43b  lea     rax, [r15+r10]
0x18003f43f  mov     [rbx+0Ch], r15d
0x18003f443  add     rcx, rax
0x18003f446  mov     [rbx+14h], r8d
0x18003f44a  mov     r11d, r15d
0x18003f44d  mov     qword ptr [rbp+3Fh+var_88], rax
0x18003f451  mov     qword ptr [rbp+3Fh+var_78], rdx
0x18003f455  mov     qword ptr [rbp+3Fh+var_88+8], rcx
0x18003f459  mov     qword ptr [rbp+3Fh+var_78+8], r9
0x18003f45d  test    r13d, r13d
0x18003f460  jnz     short loc_18003F488
0x18003f462  lea     rax, [r8+rcx]
0x18003f466  mov     qword ptr [rbp+3Fh+var_68], rdx
0x18003f46a  lea     rcx, [rax+rdx]
0x18003f46e  mov     qword ptr [rbp+3Fh+var_58], rax
0x18003f472  lea     rax, [r8+rcx]
0x18003f476  mov     qword ptr [rbp+3Fh+var_58+8], rcx
0x18003f47a  mov     ecx, edx
0x18003f47c  mov     qword ptr [rbp+3Fh+var_68+8], r9
0x18003f480  add     rdx, rax
0x18003f483  mov     r8d, r11d
0x18003f486  jmp     short loc_18003F495
0x18003f488  mov     rax, [rbp+3Fh+var_98]
0x18003f48c  mov     rcx, rax
0x18003f48f  mov     rdx, rax
0x18003f492  mov     r8, rax
0x18003f495  mov     rdi, [r14+20h]
0x18003f499  mov     [rbp+3Fh+var_B0], r8
0x18003f49d  mov     [rbp+3Fh+var_A8], rdx
0x18003f4a1  mov     [rbp+3Fh+var_A0], rcx
0x18003f4a5  cmp     byte ptr [rdi+8], 0
0x18003f4a9  mov     [rbp+3Fh+var_98], rax
0x18003f4ad  jz      loc_18003F60C
0x18003f4b3  mov     esi, 2
0x18003f4b8  jmp     short loc_18003F517
0x18003f4ba  mov     rax, [rbp+3Fh+arg_28]
0x18003f4be  lea     ecx, [r15+18h]
0x18003f4c2  add     ecx, edi
0x18003f4c4  mov     [rax], ecx
0x18003f4c6  test    rbx, rbx
0x18003f4c9  jnz     short loc_18003F4D2
0x18003f4cb  xor     ebx, ebx
0x18003f4cd  jmp     loc_18003F69F
0x18003f4d2  cmp     [rbp+3Fh+arg_20], ecx
0x18003f4d5  jnb     short loc_18003F4EC
0x18003f4d7  mov     ebx, 0C0000023h
0x18003f4dc  mov     r9d, 4BAh
0x18003f4e2  mov     ecx, 0C0000023h
0x18003f4e7  jmp     loc_18003F68C
0x18003f4ec  xor     esi, esi
0x18003f4ee  mov     dword ptr [rbx], 31415352h
0x18003f4f4  mov     eax, [r14+0Ch]
0x18003f4f8  lea     r10, [rbx+18h]
0x18003f4fc  mov     r12d, edi
0x18003f4ff  mov     [rbx+4], eax
0x18003f502  add     r10, r12
0x18003f505  mov     [rbx+8], edi
0x18003f508  mov     [rbx+0Ch], r15d
0x18003f50c  mov     [rbx+10h], rsi
0x18003f510  mov     rdi, [r14+20h]
0x18003f514  mov     r11d, r15d
0x18003f517  xor     eax, eax
0x18003f519  mov     [rbp+3Fh+var_90], rdi
0x18003f51d  test    r10, r10
0x18003f520  jz      short loc_18003F54B
0x18003f522  mov     rdx, [rdi+78h]
0x18003f526  mov     r9, r11
0x18003f529  mov     r8, r10
0x18003f52c  mov     dword ptr [rsp+100h+var_E0], 2
0x18003f534  lea     rcx, [rdx+80h]
0x18003f53b  mov     edx, [rdx+64h]
0x18003f53e  call    SymCryptFdefRawGetValue
0x18003f543  test    eax, eax
0x18003f545  jnz     loc_18003F611
0x18003f54b  mov     r15, [rdi+38h]
0x18003f54f  test    esi, esi
0x18003f551  jz      short loc_18003F5A1
0x18003f553  cmp     esi, 2
0x18003f556  jnz     loc_18003F60C
0x18003f55c  xor     edi, edi
0x18003f55e  cmp     edi, 2
0x18003f561  jnb     short loc_18003F59D
0x18003f563  mov     r8, qword ptr [rbp+rdi*8+3Fh+var_88]
0x18003f568  test    r8, r8
0x18003f56b  jz      short loc_18003F599
0x18003f56d  mov     rax, [rbp+3Fh+var_90]
0x18003f571  mov     r9, qword ptr [rbp+rdi*8+3Fh+var_78]
0x18003f576  mov     dword ptr [rsp+100h+var_E0], 2
0x18003f57e  mov     rdx, [rax+rdi*8+80h]
0x18003f586  lea     rcx, [rdx+80h]
0x18003f58d  mov     edx, [rdx+64h]
0x18003f590  call    SymCryptFdefRawGetValue
0x18003f595  test    eax, eax
0x18003f597  jnz     short loc_18003F611
0x18003f599  inc     edi
0x18003f59b  jmp     short loc_18003F55E
0x18003f59d  test    eax, eax
0x18003f59f  jnz     short loc_18003F611
0x18003f5a1  lea     rdx, [rbx+18h]
0x18003f5a5  mov     r8, r12
0x18003f5a8  mov     rcx, r15
0x18003f5ab  call    SymCryptStoreMsbFirstUint64
0x18003f5b0  test    eax, eax
0x18003f5b2  jz      short loc_18003F624
0x18003f5b4  mov     ecx, eax
0x18003f5b6  call    SymcryptErrorCodeToNtStatus
0x18003f5bb  mov     ebx, eax
0x18003f5bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f5c4  lea     rax, WPP_GLOBAL_Control
0x18003f5cb  cmp     rcx, rax
0x18003f5ce  jz      loc_18003F69F
0x18003f5d4  mov     eax, [rcx+2Ch]
0x18003f5d7  test    al, 1
0x18003f5d9  jz      loc_18003F69F
0x18003f5df  mov     rcx, [rcx+18h]
0x18003f5e3  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003f5ea  mov     dword ptr [rsp+100h+var_D0], 54Dh
0x18003f5f2  lea     r9, aStatus; "Status"
0x18003f5f9  mov     [rsp+100h+var_D8], r8
0x18003f5fe  mov     dword ptr [rsp+100h+var_E0], ebx
0x18003f602  call    WPP_SF_sDsd
0x18003f607  jmp     loc_18003F69F
0x18003f60c  mov     eax, 800Eh
0x18003f611  mov     ecx, eax
0x18003f613  call    SymcryptErrorCodeToNtStatus
0x18003f618  mov     r9d, 545h
0x18003f61e  mov     ebx, eax
0x18003f620  mov     ecx, eax
0x18003f622  jmp     short loc_18003F68C
0x18003f624  test    r13d, r13d
0x18003f627  jnz     loc_18003F4CB
0x18003f62d  mov     rax, [rbp+3Fh+var_B0]
0x18003f631  lea     r8, [rbp+3Fh+var_68]
0x18003f635  mov     rcx, [r14+20h]
0x18003f639  lea     rdx, [rbp+3Fh+var_58]
0x18003f63d  mov     [rsp+100h+var_C8], rax
0x18003f642  mov     r9d, esi
0x18003f645  mov     rax, [rbp+3Fh+var_A8]
0x18003f649  mov     [rsp+100h+var_D0], rax
0x18003f64e  mov     rax, [rbp+3Fh+var_A0]
0x18003f652  mov     [rsp+100h+var_D8], rax
0x18003f657  mov     rax, [rbp+3Fh+var_98]
0x18003f65b  mov     [rsp+100h+var_E0], rax
0x18003f660  call    SymCryptRsakeyGetCrtValue
0x18003f665  test    eax, eax
0x18003f667  jz      loc_18003F4CB
0x18003f66d  mov     ecx, eax
0x18003f66f  call    SymcryptErrorCodeToNtStatus
0x18003f674  mov     r9d, 561h
0x18003f67a  jmp     short loc_18003F61E
0x18003f67c  mov     ebx, 0C0000008h
0x18003f681  mov     r9d, 49Dh
0x18003f687  mov     ecx, 0C0000008h
0x18003f68c  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003f693  lea     rdx, aStatus; "Status"
0x18003f69a  call    DebugTraceError
0x18003f69f  mov     eax, ebx
0x18003f6a1  add     rsp, 0C8h
0x18003f6a8  pop     r15
0x18003f6aa  pop     r14
0x18003f6ac  pop     r13
0x18003f6ae  pop     r12
0x18003f6b0  pop     rdi
0x18003f6b1  pop     rsi
0x18003f6b2  pop     rbx
0x18003f6b3  pop     rbp
0x18003f6b4  retn
```

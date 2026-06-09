# MSCryptExportKeyPair

- ea: `0x18003fdf0`
- end: `0x180040246`
- name: `MSCryptExportKeyPair`
- size: `1110`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180074dfc`
- `0x1800780e4`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x18001b820`
- `0x18003fdf0`
- `0x18004024c`
- `0x1800407f8`
- `0x180048154`
- `0x180048770`
- `0x18008c4a8`
- `0x18009f616`

## string_xrefs

- `0x180040173`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18004021c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

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
0x18003fdf0  push    rbp
0x18003fdf2  push    rbx
0x18003fdf3  push    rsi
0x18003fdf4  push    rdi
0x18003fdf5  push    r12
0x18003fdf7  push    r13
0x18003fdf9  push    r14
0x18003fdfb  push    r15
0x18003fdfd  lea     rbp, [rsp-7]
0x18003fe02  sub     rsp, 0C8h
0x18003fe09  xorps   xmm0, xmm0
0x18003fe0c  xorps   xmm1, xmm1
0x18003fe0f  mov     r12, r8
0x18003fe12  mov     rbx, r9
0x18003fe15  xor     r8d, r8d
0x18003fe18  movups  [rbp+3Fh+var_88], xmm0
0x18003fe1c  movups  [rbp+3Fh+var_78], xmm1
0x18003fe20  movups  [rbp+3Fh+var_58], xmm0
0x18003fe24  movups  [rbp+3Fh+var_68], xmm1
0x18003fe28  cmp     [rbp+3Fh+arg_30], r8d
0x18003fe2c  jz      short loc_18003FE43
0x18003fe2e  mov     ebx, 0C000000Dh
0x18003fe33  mov     r9d, 48Ch
0x18003fe39  mov     ecx, 0C000000Dh
0x18003fe3e  jmp     loc_18004021C
0x18003fe43  test    rdx, rdx
0x18003fe46  jz      short loc_18003FE5D
0x18003fe48  mov     r9d, 493h
0x18003fe4e  mov     ebx, 0C00000BBh
0x18003fe53  mov     ecx, 0C00000BBh
0x18003fe58  jmp     loc_18004021C
0x18003fe5d  call    validateMSCryptRsaKey
0x18003fe62  mov     r14, rax
0x18003fe65  test    rax, rax
0x18003fe68  jz      loc_18004020C
0x18003fe6e  cmp     [rax+10h], r8d
0x18003fe72  jz      loc_18004020C
0x18003fe78  mov     rsi, [rax+20h]
0x18003fe7c  test    rsi, rsi
0x18003fe7f  jz      loc_18004020C
0x18003fe85  mov     rax, [rsi+38h]
0x18003fe89  mov     rcx, rax
0x18003fe8c  mov     [rbp+3Fh+var_98], r8
0x18003fe90  shr     rcx, 20h
0x18003fe94  mov     [rbp+3Fh+var_A0], r8
0x18003fe98  mov     [rbp+3Fh+var_A8], r8
0x18003fe9c  mov     [rbp+3Fh+var_B0], r8
0x18003fea0  test    ecx, ecx
0x18003fea2  jnz     short loc_18003FEAF
0x18003fea4  mov     ecx, eax
0x18003fea6  call    SymCryptUint32Bytesize
0x18003feab  mov     edi, eax
0x18003fead  jmp     short loc_18003FEB7
0x18003feaf  call    SymCryptUint32Bytesize
0x18003feb4  lea     edi, [rax+4]
0x18003feb7  mov     r15d, [rsi+10h]
0x18003febb  lea     rdx, aRsafullprivate; "RSAFULLPRIVATEBLOB"
0x18003fec2  add     r15d, 7
0x18003fec6  mov     rcx, r12; Str1
0x18003fec9  shr     r15d, 3
0x18003fecd  call    wcscmp_0
0x18003fed2  lea     rdx, aRsapublicblob; "RSAPUBLICBLOB"
0x18003fed9  mov     rcx, r12; Str1
0x18003fedc  mov     r13d, eax
0x18003fedf  call    wcscmp_0
0x18003fee4  test    eax, eax
0x18003fee6  jz      loc_18004004A
0x18003feec  lea     rdx, aPublicblob; "PUBLICBLOB"
0x18003fef3  mov     rcx, r12; Str1
0x18003fef6  call    wcscmp_0
0x18003fefb  test    eax, eax
0x18003fefd  jz      loc_18004004A
0x18003ff03  lea     rdx, aRsaprivateblob; "RSAPRIVATEBLOB"
0x18003ff0a  mov     rcx, r12; Str1
0x18003ff0d  call    wcscmp_0
0x18003ff12  test    eax, eax
0x18003ff14  jz      short loc_18003FF39
0x18003ff16  lea     rdx, aPrivateblob; "PRIVATEBLOB"
0x18003ff1d  mov     rcx, r12; Str1
0x18003ff20  call    wcscmp_0
0x18003ff25  test    eax, eax
0x18003ff27  jz      short loc_18003FF39
0x18003ff29  test    r13d, r13d
0x18003ff2c  jz      short loc_18003FF39
0x18003ff2e  mov     r9d, 533h
0x18003ff34  jmp     loc_18003FE4E
0x18003ff39  cmp     byte ptr [rsi+8], 0
0x18003ff3d  jnz     short loc_18003FF49
0x18003ff3f  mov     ebx, 0C000000Dh
0x18003ff44  jmp     loc_18004022F
0x18003ff49  mov     ecx, [rsi+20h]
0x18003ff4c  mov     r8d, [rsi+24h]
0x18003ff50  add     ecx, 7
0x18003ff53  mov     r9, [rbp+3Fh+arg_28]
0x18003ff57  add     r8d, 7
0x18003ff5b  shr     ecx, 3
0x18003ff5e  shr     r8d, 3
0x18003ff62  lea     edx, [rcx+18h]
0x18003ff65  add     edx, r8d
0x18003ff68  add     edx, r15d
0x18003ff6b  add     edx, edi
0x18003ff6d  mov     [r9], edx
0x18003ff70  test    r13d, r13d
0x18003ff73  jnz     short loc_18003FF86
0x18003ff75  lea     edx, [rcx+0Ch]
0x18003ff78  add     edx, r8d
0x18003ff7b  add     edx, r15d
0x18003ff7e  lea     edx, [rcx+rdx*2]
0x18003ff81  add     edx, edi
0x18003ff83  mov     [r9], edx
0x18003ff86  test    rbx, rbx
0x18003ff89  jz      loc_18004005B
0x18003ff8f  cmp     [rbp+3Fh+arg_20], edx
0x18003ff92  jnb     short loc_18003FF9E
0x18003ff94  mov     ebx, 0C0000023h
0x18003ff99  jmp     loc_18004022F
0x18003ff9e  mov     dword ptr [rbx], 32415352h
0x18003ffa4  test    r13d, r13d
0x18003ffa7  jnz     short loc_18003FFAF
0x18003ffa9  mov     dword ptr [rbx], 33415352h
0x18003ffaf  mov     eax, [r14+0Ch]
0x18003ffb3  lea     r10, [rbx+18h]
0x18003ffb7  mov     edx, ecx
0x18003ffb9  mov     r12d, edi
0x18003ffbc  add     r10, r12
0x18003ffbf  mov     [rbx+4], eax
0x18003ffc2  mov     [rbx+10h], ecx
0x18003ffc5  mov     r9d, r8d
0x18003ffc8  mov     [rbx+8], edi
0x18003ffcb  lea     rax, [r15+r10]
0x18003ffcf  mov     [rbx+0Ch], r15d
0x18003ffd3  add     rcx, rax
0x18003ffd6  mov     [rbx+14h], r8d
0x18003ffda  mov     r11d, r15d
0x18003ffdd  mov     qword ptr [rbp+3Fh+var_88], rax
0x18003ffe1  mov     qword ptr [rbp+3Fh+var_78], rdx
0x18003ffe5  mov     qword ptr [rbp+3Fh+var_88+8], rcx
0x18003ffe9  mov     qword ptr [rbp+3Fh+var_78+8], r9
0x18003ffed  test    r13d, r13d
0x18003fff0  jnz     short loc_180040018
0x18003fff2  lea     rax, [r8+rcx]
0x18003fff6  mov     qword ptr [rbp+3Fh+var_68], rdx
0x18003fffa  lea     rcx, [rax+rdx]
0x18003fffe  mov     qword ptr [rbp+3Fh+var_58], rax
0x180040002  lea     rax, [r8+rcx]
0x180040006  mov     qword ptr [rbp+3Fh+var_58+8], rcx
0x18004000a  mov     ecx, edx
0x18004000c  mov     qword ptr [rbp+3Fh+var_68+8], r9
0x180040010  add     rdx, rax
0x180040013  mov     r8d, r11d
0x180040016  jmp     short loc_180040025
0x180040018  mov     rax, [rbp+3Fh+var_98]
0x18004001c  mov     rcx, rax
0x18004001f  mov     rdx, rax
0x180040022  mov     r8, rax
0x180040025  mov     rdi, [r14+20h]
0x180040029  mov     [rbp+3Fh+var_B0], r8
0x18004002d  mov     [rbp+3Fh+var_A8], rdx
0x180040031  mov     [rbp+3Fh+var_A0], rcx
0x180040035  cmp     byte ptr [rdi+8], 0
0x180040039  mov     [rbp+3Fh+var_98], rax
0x18004003d  jz      loc_18004019C
0x180040043  mov     esi, 2
0x180040048  jmp     short loc_1800400A7
0x18004004a  mov     rax, [rbp+3Fh+arg_28]
0x18004004e  lea     ecx, [r15+18h]
0x180040052  add     ecx, edi
0x180040054  mov     [rax], ecx
0x180040056  test    rbx, rbx
0x180040059  jnz     short loc_180040062
0x18004005b  xor     ebx, ebx
0x18004005d  jmp     loc_18004022F
0x180040062  cmp     [rbp+3Fh+arg_20], ecx
0x180040065  jnb     short loc_18004007C
0x180040067  mov     ebx, 0C0000023h
0x18004006c  mov     r9d, 4BAh
0x180040072  mov     ecx, 0C0000023h
0x180040077  jmp     loc_18004021C
0x18004007c  xor     esi, esi
0x18004007e  mov     dword ptr [rbx], 31415352h
0x180040084  mov     eax, [r14+0Ch]
0x180040088  lea     r10, [rbx+18h]
0x18004008c  mov     r12d, edi
0x18004008f  mov     [rbx+4], eax
0x180040092  add     r10, r12
0x180040095  mov     [rbx+8], edi
0x180040098  mov     [rbx+0Ch], r15d
0x18004009c  mov     [rbx+10h], rsi
0x1800400a0  mov     rdi, [r14+20h]
0x1800400a4  mov     r11d, r15d
0x1800400a7  xor     eax, eax
0x1800400a9  mov     [rbp+3Fh+var_90], rdi
0x1800400ad  test    r10, r10
0x1800400b0  jz      short loc_1800400DB
0x1800400b2  mov     rdx, [rdi+78h]
0x1800400b6  mov     r9, r11
0x1800400b9  mov     r8, r10
0x1800400bc  mov     dword ptr [rsp+100h+var_E0], 2
0x1800400c4  lea     rcx, [rdx+80h]
0x1800400cb  mov     edx, [rdx+64h]
0x1800400ce  call    SymCryptFdefRawGetValue
0x1800400d3  test    eax, eax
0x1800400d5  jnz     loc_1800401A1
0x1800400db  mov     r15, [rdi+38h]
0x1800400df  test    esi, esi
0x1800400e1  jz      short loc_180040131
0x1800400e3  cmp     esi, 2
0x1800400e6  jnz     loc_18004019C
0x1800400ec  xor     edi, edi
0x1800400ee  cmp     edi, 2
0x1800400f1  jnb     short loc_18004012D
0x1800400f3  mov     r8, qword ptr [rbp+rdi*8+3Fh+var_88]
0x1800400f8  test    r8, r8
0x1800400fb  jz      short loc_180040129
0x1800400fd  mov     rax, [rbp+3Fh+var_90]
0x180040101  mov     r9, qword ptr [rbp+rdi*8+3Fh+var_78]
0x180040106  mov     dword ptr [rsp+100h+var_E0], 2
0x18004010e  mov     rdx, [rax+rdi*8+80h]
0x180040116  lea     rcx, [rdx+80h]
0x18004011d  mov     edx, [rdx+64h]
0x180040120  call    SymCryptFdefRawGetValue
0x180040125  test    eax, eax
0x180040127  jnz     short loc_1800401A1
0x180040129  inc     edi
0x18004012b  jmp     short loc_1800400EE
0x18004012d  test    eax, eax
0x18004012f  jnz     short loc_1800401A1
0x180040131  lea     rdx, [rbx+18h]
0x180040135  mov     r8, r12
0x180040138  mov     rcx, r15
0x18004013b  call    SymCryptStoreMsbFirstUint64
0x180040140  test    eax, eax
0x180040142  jz      short loc_1800401B4
0x180040144  mov     ecx, eax
0x180040146  call    SymcryptErrorCodeToNtStatus
0x18004014b  mov     ebx, eax
0x18004014d  mov     rcx, cs:WPP_GLOBAL_Control
0x180040154  lea     rax, WPP_GLOBAL_Control
0x18004015b  cmp     rcx, rax
0x18004015e  jz      loc_18004022F
0x180040164  mov     eax, [rcx+2Ch]
0x180040167  test    al, 1
0x180040169  jz      loc_18004022F
0x18004016f  mov     rcx, [rcx+18h]
0x180040173  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004017a  mov     dword ptr [rsp+100h+var_D0], 54Dh
0x180040182  lea     r9, aStatus; "Status"
0x180040189  mov     [rsp+100h+var_D8], r8
0x18004018e  mov     dword ptr [rsp+100h+var_E0], ebx
0x180040192  call    WPP_SF_sDsd
0x180040197  jmp     loc_18004022F
0x18004019c  mov     eax, 800Eh
0x1800401a1  mov     ecx, eax
0x1800401a3  call    SymcryptErrorCodeToNtStatus
0x1800401a8  mov     r9d, 545h
0x1800401ae  mov     ebx, eax
0x1800401b0  mov     ecx, eax
0x1800401b2  jmp     short loc_18004021C
0x1800401b4  test    r13d, r13d
0x1800401b7  jnz     loc_18004005B
0x1800401bd  mov     rax, [rbp+3Fh+var_B0]
0x1800401c1  lea     r8, [rbp+3Fh+var_68]
0x1800401c5  mov     rcx, [r14+20h]
0x1800401c9  lea     rdx, [rbp+3Fh+var_58]
0x1800401cd  mov     [rsp+100h+var_C8], rax
0x1800401d2  mov     r9d, esi
0x1800401d5  mov     rax, [rbp+3Fh+var_A8]
0x1800401d9  mov     [rsp+100h+var_D0], rax
0x1800401de  mov     rax, [rbp+3Fh+var_A0]
0x1800401e2  mov     [rsp+100h+var_D8], rax
0x1800401e7  mov     rax, [rbp+3Fh+var_98]
0x1800401eb  mov     [rsp+100h+var_E0], rax
0x1800401f0  call    SymCryptRsakeyGetCrtValue
0x1800401f5  test    eax, eax
0x1800401f7  jz      loc_18004005B
0x1800401fd  mov     ecx, eax
0x1800401ff  call    SymcryptErrorCodeToNtStatus
0x180040204  mov     r9d, 561h
0x18004020a  jmp     short loc_1800401AE
0x18004020c  mov     ebx, 0C0000008h
0x180040211  mov     r9d, 49Dh
0x180040217  mov     ecx, 0C0000008h
0x18004021c  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180040223  lea     rdx, aStatus; "Status"
0x18004022a  call    DebugTraceError
0x18004022f  mov     eax, ebx
0x180040231  add     rsp, 0C8h
0x180040238  pop     r15
0x18004023a  pop     r14
0x18004023c  pop     r13
0x18004023e  pop     r12
0x180040240  pop     rdi
0x180040241  pop     rsi
0x180040242  pop     rbx
0x180040243  pop     rbp
0x180040244  retn
```

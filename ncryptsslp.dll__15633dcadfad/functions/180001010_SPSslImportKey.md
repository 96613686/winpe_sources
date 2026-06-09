# SPSslImportKey

- ea: `0x180001010`
- end: `0x180001669`
- name: `SPSslImportKey`
- size: `1625`
- prototype: `__int64 __fastcall(__int64, __int64 *, const WCHAR *, __int64, DWORD, int)`
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x180001010`
- `0x180001690`
- `0x180001acc`
- `0x180003ef0`
- `0x180005e50`
- `0x1800068e0`
- `0x180007940`
- `0x18000b594`
- `0x18000b654`
- `0x1800185e0`
- `0x18001f59c`
- `0x180021778`
- `0x1800222f0`
- `0x180022420`
- `0x1800234b0`
- `0x180024fb0`
- `0x180025660`

## import_xrefs

- `bcrypt!BCryptDestroyKey` at `0x18000156a`
- `bcrypt!BCryptDestroyKey` at `0x18000156a`
- `bcrypt!BCryptImportKey` at `0x180001248`
- `bcrypt!BCryptImportKey` at `0x180001248`

## string_xrefs

- `0x18000132a`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180001548`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180001651`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslImportKey(__int64 a1, __int64 *a2, const WCHAR *a3, __int64 a4, DWORD a5, int a6)
{
  __int64 v9; // rdx
  __int64 v10; // rdi
  const wchar_t *v11; // r8
  __int64 v12; // r9
  __m128i v13; // xmm2
  __int128 v14; // xmm3
  __int128 v15; // xmm1
  __m128i v16; // xmm0
  __int64 v17; // r13
  int v18; // r12d
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // ebx
  _BYTE *v22; // rax
  _BYTE *v23; // rdi
  UCHAR *pbKeyObject; // r8
  int v25; // ecx
  NTSTATUS v26; // eax
  unsigned int CipherEntry; // ebx
  __int64 v29; // rax
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int64 v32; // rdx
  __int64 v33; // r12
  int v34; // edx
  int HashEntry; // eax
  __int64 v36; // r9
  __int64 v37; // rcx
  __int64 v38; // rax
  _BYTE *v39; // rcx
  void *v40; // rcx
  DWORD v41; // edi
  __int64 v42; // rax
  _DWORD *v43; // rbx
  int v44; // [rsp+50h] [rbp-79h]
  ULONG v45; // [rsp+50h] [rbp-79h]
  ULONG cbKeyObject; // [rsp+54h] [rbp-75h]
  __int32 v47; // [rsp+60h] [rbp-69h]
  size_t Size; // [rsp+70h] [rbp-59h]
  __int64 hAlgorithm; // [rsp+78h] [rbp-51h]
  _BYTE Src_8[56]; // [rsp+98h] [rbp-31h] BYREF

  v10 = SslpValidateProvHandle();
  if ( !v10 )
  {
    CipherEntry = -2146893786;
    v36 = 3519;
    v37 = 2148073510LL;
    goto LABEL_88;
  }
  if ( !v9 || !v12 )
  {
    v36 = 3526;
    goto LABEL_87;
  }
  if ( a6 )
  {
    CipherEntry = -2146893815;
    v36 = 3533;
    v37 = 2148073481LL;
    goto LABEL_88;
  }
  if ( wcscmp(v11, L"OpaqueKeyBlob") )
  {
    if ( wcscmp(a3, L"TLS13PRESHAREDKEY") )
    {
      if ( !wcscmp(a3, L"TLS_KEM_CIPHERTEXT") )
      {
        HashEntry = SslpImportKemCipherText(a4, a5, a2);
        CipherEntry = HashEntry;
        if ( HashEntry >= 0 )
          return 0;
        v36 = 3777;
      }
      else
      {
        if ( !wcscmp(a3, L"MLKEMPUBLICBLOB") )
        {
          HashEntry = SslpImportKemKeyWithNCrypt((PBYTE)a4, a5, a3);
          CipherEntry = HashEntry;
          if ( HashEntry < 0 )
          {
            v36 = 3790;
            goto LABEL_44;
          }
          return 0;
        }
        if ( !wcscmp(a3, L"TLS_HYBRID_KEY") )
        {
          HashEntry = SslpImportHybridKey(a4, a5, a3, a2);
          CipherEntry = HashEntry;
          if ( HashEntry < 0 )
          {
            v36 = 3803;
            goto LABEL_44;
          }
          return 0;
        }
        HashEntry = SslpImportEphemeralKeyWithNCrypt((PBYTE)a4, a5, a3, a2);
        CipherEntry = HashEntry;
        if ( HashEntry >= 0 )
          return 0;
        v36 = 3816;
      }
LABEL_44:
      v37 = (unsigned int)HashEntry;
LABEL_88:
      DebugTraceError(v37, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v36);
      return CipherEntry;
    }
    v41 = a5 + 12;
    if ( a5 + 12 >= 0x10 )
    {
      v42 = SafeAllocaAllocateFromHeap(v41);
      v43 = (_DWORD *)v42;
      if ( !v42 )
      {
        CipherEntry = -2146893810;
        v36 = 3759;
        v37 = 2148073486LL;
        goto LABEL_88;
      }
      memmove((void *)(v42 + 12), (const void *)a4, a5);
      *v43 = v41;
      v43[1] = 1936944186;
      v43[2] = 12288;
      *a2 = (__int64)v43;
      return 0;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2));
    v36 = 3750;
LABEL_87:
    v37 = 2148073511LL;
    CipherEntry = -2146893785;
    goto LABEL_88;
  }
  if ( a5 < 0x50 )
  {
    v36 = 3549;
LABEL_60:
    CipherEntry = -2146893819;
    v37 = 2148073477LL;
    goto LABEL_88;
  }
  v13 = *(__m128i *)a4;
  v14 = *(_OWORD *)(a4 + 16);
  v15 = *(_OWORD *)(a4 + 48);
  *(_OWORD *)&Src_8[8] = *(_OWORD *)(a4 + 32);
  *(_OWORD *)&Src_8[40] = *(_OWORD *)(a4 + 64);
  *(_QWORD *)Src_8 = *((_QWORD *)&v14 + 1);
  *(_OWORD *)&Src_8[24] = v15;
  if ( _mm_cvtsi128_si32(v13) > a5 || DWORD1(v14) >= a5 )
  {
    v36 = 3559;
    goto LABEL_60;
  }
  v16 = _mm_srli_si128(v13, 8);
  v47 = v16.m128i_i32[0];
  v17 = LookupCipherSuite((unsigned int)_mm_cvtsi128_si32(v16), HIDWORD(v16.m128i_i64[0]));
  if ( !v17 )
  {
    v36 = 3568;
    goto LABEL_60;
  }
  v18 = _mm_cvtsi128_si32(_mm_srli_si128(v13, 4));
  v44 = v18;
  if ( v18 == 1936944179 && *(_DWORD *)Src_8 > 0x30u )
  {
    v36 = 3577;
    goto LABEL_60;
  }
  v19 = *(unsigned int *)(v17 + 40);
  hAlgorithm = 913;
  cbKeyObject = 0;
  if ( (_DWORD)v19 )
  {
    v32 = 16 * v19;
    Size = 16 * v19;
    v33 = 16 * v19 + v10;
    if ( !*(_DWORD *)(v33 + 28) )
    {
      CipherEntry = I_GetCipherEntry(v19, *(unsigned int *)(v10 + 12), v33 + 16);
      if ( (CipherEntry & 0x80000000) != 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v34,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            (unsigned int)"Status",
            CipherEntry,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            16);
        return CipherEntry;
      }
      v32 = Size;
    }
    if ( ((*(_DWORD *)&Src_8[52] - 4) & 0xFFFFFFFC) != 0 || *(_DWORD *)&Src_8[52] == 5 )
    {
      hAlgorithm = *(_QWORD *)(v33 + 16);
      if ( !hAlgorithm )
      {
        CipherEntry = -2146893783;
        v36 = 3617;
        v37 = 2148073513LL;
        goto LABEL_88;
      }
      cbKeyObject = *(_DWORD *)(v32 + v10 + 24);
    }
    v18 = v44;
  }
  v20 = *(unsigned int *)(v17 + 72);
  if ( (_DWORD)v20 )
  {
    if ( !*(_DWORD *)(32 * v20 + v10 + 300) )
    {
      HashEntry = I_GetHashEntry(v20, *(unsigned int *)(v10 + 12), v10 + 32 * v20 + 272);
      CipherEntry = HashEntry;
      if ( HashEntry < 0 )
      {
        v36 = 3636;
        goto LABEL_44;
      }
    }
  }
  if ( v18 != 1936944179 )
  {
    if ( v18 != 1936944181 )
      return 0;
    v29 = SafeAllocaAllocateFromHeap(80);
    if ( v29 )
    {
      *(_DWORD *)(v29 + 12) = 0;
      v30 = *(_OWORD *)&Src_8[20];
      *(_OWORD *)(v29 + 28) = *(_OWORD *)&Src_8[4];
      *(_DWORD *)(v29 + 24) = v14;
      v31 = *(_OWORD *)&Src_8[36];
      *(_OWORD *)(v29 + 44) = v30;
      *(_DWORD *)v29 = 80;
      *(_OWORD *)(v29 + 60) = v31;
      *(_DWORD *)(v29 + 4) = 1936944181;
      *(_DWORD *)(v29 + 8) = v47;
      *(_QWORD *)(v29 + 16) = v17;
      *(_DWORD *)(v29 + 76) = *(_DWORD *)Src_8;
      *a2 = v29;
      return 0;
    }
    return (unsigned int)-2146893810;
  }
  v21 = 0;
  if ( !(_DWORD)v14
    && v16.m128i_i32[0] >= 0x302u
    && *(_DWORD *)(v17 + 36) > 1u
    && wcscmp(*(const wchar_t **)(v17 + 48), L"ChainingModeGCM") )
  {
    v21 = 128;
  }
  v45 = v21 + cbKeyObject + 112;
  v22 = (_BYTE *)SafeAllocaAllocateFromHeap(v45);
  v23 = v22;
  if ( !v22 )
    return (unsigned int)-2146893810;
  memset(v22, 0, v21 + cbKeyObject + 112);
  *(_DWORD *)v23 = v45;
  *((_DWORD *)v23 + 6) = v14;
  *((_DWORD *)v23 + 27) = *(_DWORD *)&Src_8[52];
  *((_DWORD *)v23 + 1) = 1936944179;
  *((_DWORD *)v23 + 2) = v16.m128i_i32[0];
  *((_QWORD *)v23 + 2) = v17;
  *((_DWORD *)v23 + 26) = *(_DWORD *)Src_8;
  memmove(v23 + 56, &Src_8[4], *(unsigned int *)Src_8);
  if ( v21 )
  {
    *((_DWORD *)v23 + 12) = v21;
    *((_DWORD *)v23 + 13) = v21;
    *((_QWORD *)v23 + 5) = &v23[cbKeyObject + 112];
  }
  if ( !*(_DWORD *)(v17 + 40) )
    goto LABEL_27;
  if ( cbKeyObject )
    pbKeyObject = v23 + 112;
  else
    pbKeyObject = 0;
  v25 = *((_DWORD *)v23 + 27);
  if ( ((v25 - 4) & 0xFFFFFFFC) == 0 && v25 != 5 )
    a3 = L"KeyDataBlob";
  v26 = BCryptImportKey(
          (BCRYPT_ALG_HANDLE)hAlgorithm,
          0,
          a3,
          (BCRYPT_KEY_HANDLE *)v23 + 4,
          pbKeyObject,
          cbKeyObject,
          (PUCHAR)(a4 + 80),
          a5 - 80,
          0);
  CipherEntry = v26;
  if ( v26 >= 0 )
  {
LABEL_27:
    *a2 = (__int64)v23;
    return 0;
  }
  DebugTraceError((unsigned int)v26, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", 3699);
  v40 = (void *)*((_QWORD *)v23 + 4);
  if ( v40 )
    BCryptDestroyKey(v40);
  v38 = v45;
  v39 = v23;
  if ( v45 )
  {
    do
    {
      *v23++ = 0;
      --v38;
    }
    while ( v38 );
  }
  MSCryptFree(v39);
  return CipherEntry;
}

```

## disassembly

```asm
0x180001010  push    rbp
0x180001012  push    rbx
0x180001013  push    rsi
0x180001014  push    rdi
0x180001015  push    r12
0x180001017  push    r13
0x180001019  push    r14
0x18000101b  push    r15
0x18000101d  lea     rbp, [rsp-0Fh]
0x180001022  sub     rsp, 0D8h
0x180001029  mov     rsi, r9
0x18000102c  mov     r14, r8
0x18000102f  mov     r15, rdx
0x180001032  call    SslpValidateProvHandle
0x180001037  mov     rdi, rax
0x18000103a  test    rax, rax
0x18000103d  jz      loc_180001454
0x180001043  test    rdx, rdx
0x180001046  jz      loc_180001641
0x18000104c  test    r9, r9
0x18000104f  jz      loc_180001641
0x180001055  cmp     [rbp+47h+arg_28], 0
0x180001059  jnz     loc_180001469
0x18000105f  lea     rdx, aOpaquekeyblob; "OpaqueKeyBlob"
0x180001066  mov     rcx, r8; String1
0x180001069  call    wcscmp
0x18000106e  test    eax, eax
0x180001070  jnz     loc_180001353
0x180001076  mov     ecx, dword ptr [rbp+47h+arg_20]
0x180001079  cmp     ecx, 50h ; 'P'
0x18000107c  jb      loc_18000147E
0x180001082  movups  xmm2, xmmword ptr [rsi]
0x180001085  movups  xmm0, xmmword ptr [rsi+20h]
0x180001089  movups  xmm3, xmmword ptr [rsi+10h]
0x18000108d  movups  xmm1, xmmword ptr [rsi+30h]
0x180001091  movaps  [rbp+47h+var_70], xmm0
0x180001095  movups  xmm0, xmmword ptr [rsi+40h]
0x180001099  movd    eax, xmm2
0x18000109d  movaps  [rbp+47h+var_50], xmm0
0x1800010a1  movaps  [rbp+47h+var_90], xmm2
0x1800010a5  movaps  [rbp+47h+Src], xmm3
0x1800010a9  movaps  [rbp+47h+var_60], xmm1
0x1800010ad  cmp     eax, ecx
0x1800010af  ja      loc_180001486
0x1800010b5  movq    rax, xmm3
0x1800010ba  mov     [rbp+47h+var_A8], rax
0x1800010be  shr     rax, 20h
0x1800010c2  cmp     eax, ecx
0x1800010c4  jnb     loc_180001486
0x1800010ca  movdqa  xmm0, xmm2
0x1800010ce  psrldq  xmm0, 8
0x1800010d3  movq    rdx, xmm0
0x1800010d8  movd    ecx, xmm0
0x1800010dc  shr     rdx, 20h
0x1800010e0  movq    [rbp+47h+var_B0], xmm0
0x1800010e5  call    LookupCipherSuite
0x1800010ea  mov     r13, rax
0x1800010ed  test    rax, rax
0x1800010f0  jz      loc_18000149B
0x1800010f6  mov     eax, dword ptr [rbp+47h+Src+8]
0x1800010f9  psrldq  xmm2, 4
0x1800010fe  movd    r12d, xmm2
0x180001103  mov     dword ptr [rbp+47h+var_B8], eax
0x180001106  mov     [rbp+47h+var_C0], r12d
0x18000110a  cmp     r12d, 73736C33h
0x180001111  jz      loc_1800014A3
0x180001117  mov     ecx, [r13+28h]
0x18000111b  mov     [rbp+47h+hAlgorithm], 391h
0x180001123  mov     [rbp+47h+var_BC], 0
0x18000112a  test    ecx, ecx
0x18000112c  jnz     loc_1800012D4
0x180001132  mov     ecx, [r13+48h]
0x180001136  test    ecx, ecx
0x180001138  jnz     loc_1800014E3
0x18000113e  cmp     r12d, 73736C33h
0x180001145  jnz     loc_180001273
0x18000114b  mov     r12, [rbp+47h+var_B0]
0x18000114f  xor     ebx, ebx
0x180001151  cmp     dword ptr [rbp+47h+var_A8], ebx
0x180001154  jnz     short loc_180001180
0x180001156  cmp     r12d, 302h
0x18000115d  jb      short loc_180001180
0x18000115f  cmp     dword ptr [r13+24h], 1
0x180001164  jbe     short loc_180001180
0x180001166  mov     rcx, [r13+30h]; String1
0x18000116a  lea     rdx, aChainingmodegc; "ChainingModeGCM"
0x180001171  call    wcscmp
0x180001176  test    eax, eax
0x180001178  mov     ecx, 80h
0x18000117d  cmovnz  ebx, ecx
0x180001180  mov     eax, [rbp+47h+var_BC]
0x180001183  add     eax, 70h ; 'p'
0x180001186  add     eax, ebx
0x180001188  mov     ecx, eax
0x18000118a  mov     [rbp+47h+var_C0], eax
0x18000118d  mov     [rbp+47h+Size], rax
0x180001191  call    SafeAllocaAllocateFromHeap
0x180001196  mov     rdi, rax
0x180001199  test    rax, rax
0x18000119c  jz      loc_180001575
0x1800011a2  mov     r8, [rbp+47h+Size]; Size
0x1800011a6  xor     edx, edx; Val
0x1800011a8  mov     rcx, rax; void *
0x1800011ab  call    memset
0x1800011b0  mov     eax, [rbp+47h+var_C0]
0x1800011b3  lea     rcx, [rdi+38h]; void *
0x1800011b7  mov     r8d, dword ptr [rbp+47h+var_B8]; Size
0x1800011bb  lea     rdx, [rbp+47h+Src+0Ch]; Src
0x1800011bf  mov     [rdi], eax
0x1800011c1  mov     rax, [rbp+47h+var_A8]
0x1800011c5  mov     [rdi+18h], eax
0x1800011c8  mov     eax, dword ptr [rbp+47h+var_50+0Ch]
0x1800011cb  mov     [rdi+6Ch], eax
0x1800011ce  mov     dword ptr [rdi+4], 73736C33h
0x1800011d5  mov     [rdi+8], r12d
0x1800011d9  mov     [rdi+10h], r13
0x1800011dd  mov     [rdi+68h], r8d
0x1800011e1  call    memmove
0x1800011e6  test    ebx, ebx
0x1800011e8  jnz     loc_18000151F
0x1800011ee  mov     r10d, [rbp+47h+var_BC]
0x1800011f2  cmp     dword ptr [r13+28h], 0
0x1800011f7  jz      short loc_180001258
0x1800011f9  test    r10d, r10d
0x1800011fc  jnz     loc_180001539
0x180001202  xor     r8d, r8d
0x180001205  mov     ecx, [rdi+6Ch]
0x180001208  lea     eax, [rcx-4]
0x18000120b  test    eax, 0FFFFFFFCh
0x180001210  jz      loc_1800013D7
0x180001216  mov     eax, dword ptr [rbp+47h+arg_20]
0x180001219  lea     rdx, [rsi+50h]
0x18000121d  mov     rcx, [rbp+47h+hAlgorithm]; hAlgorithm
0x180001221  lea     r9, [rdi+20h]; phKey
0x180001225  mov     [rsp+110h+dwFlags], 0; dwFlags
0x18000122d  add     eax, 0FFFFFFB0h
0x180001230  mov     [rsp+110h+cbInput], eax; cbInput
0x180001234  mov     [rsp+110h+pbInput], rdx; pbInput
0x180001239  xor     edx, edx; hImportKey
0x18000123b  mov     [rsp+110h+cbKeyObject], r10d; cbKeyObject
0x180001240  mov     [rsp+110h+pbKeyObject], r8; pbKeyObject
0x180001245  mov     r8, r14; pszBlobType
0x180001248  call    cs:__imp_BCryptImportKey
0x18000124e  mov     ebx, eax
0x180001250  test    eax, eax
0x180001252  js      loc_180001542
0x180001258  mov     [r15], rdi
0x18000125b  xor     ebx, ebx
0x18000125d  mov     eax, ebx
0x18000125f  add     rsp, 0D8h
0x180001266  pop     r15
0x180001268  pop     r14
0x18000126a  pop     r13
0x18000126c  pop     r12
0x18000126e  pop     rdi
0x18000126f  pop     rsi
0x180001270  pop     rbx
0x180001271  pop     rbp
0x180001272  retn
0x180001273  mov     ebx, 73736C35h
0x180001278  cmp     r12d, ebx
0x18000127b  jnz     short loc_18000125B
0x18000127d  mov     edi, 50h ; 'P'
0x180001282  mov     ecx, edi
0x180001284  call    SafeAllocaAllocateFromHeap
0x180001289  test    rax, rax
0x18000128c  jz      loc_180001575
0x180001292  mov     dword ptr [rax+0Ch], 0
0x180001299  movups  xmm0, [rbp+47h+Src+0Ch]
0x18000129d  mov     rcx, [rbp+47h+var_A8]
0x1800012a1  movups  xmm1, [rbp+47h+var_70+0Ch]
0x1800012a5  mov     r12, [rbp+47h+var_B0]
0x1800012a9  movups  xmmword ptr [rax+1Ch], xmm0
0x1800012ad  mov     [rax+18h], ecx
0x1800012b0  movups  xmm0, [rbp+47h+var_60+0Ch]
0x1800012b4  mov     ecx, dword ptr [rbp+47h+var_B8]
0x1800012b7  movups  xmmword ptr [rax+2Ch], xmm1
0x1800012bb  mov     [rax], edi
0x1800012bd  movups  xmmword ptr [rax+3Ch], xmm0
0x1800012c1  mov     [rax+4], ebx
0x1800012c4  mov     [rax+8], r12d
0x1800012c8  mov     [rax+10h], r13
0x1800012cc  mov     [rax+4Ch], ecx
0x1800012cf  mov     [r15], rax
0x1800012d2  jmp     short loc_18000125B
0x1800012d4  mov     rdx, rcx
0x1800012d7  shl     rdx, 4
0x1800012db  mov     [rbp+47h+Size], rdx
0x1800012df  cmp     dword ptr [rdx+rdi+1Ch], 0
0x1800012e4  lea     r12, [rdx+rdi]
0x1800012e8  jnz     loc_1800013F0
0x1800012ee  mov     edx, [rdi+0Ch]
0x1800012f1  lea     r8, [r12+10h]
0x1800012f6  call    I_GetCipherEntry
0x1800012fb  mov     ebx, eax
0x1800012fd  test    eax, eax
0x1800012ff  jns     loc_1800013EC
0x180001305  mov     rcx, cs:WPP_GLOBAL_Control
0x18000130c  lea     rax, WPP_GLOBAL_Control
0x180001313  cmp     rcx, rax
0x180001316  jz      loc_18000125D
0x18000131c  test    byte ptr [rcx+1Ch], 1
0x180001320  jz      loc_18000125D
0x180001326  mov     rcx, [rcx+10h]
0x18000132a  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001331  mov     dword ptr [rsp+110h+pbInput], 0E10h
0x180001339  lea     r9, aStatus; "Status"
0x180001340  mov     qword ptr [rsp+110h+cbKeyObject], r8
0x180001345  mov     dword ptr [rsp+110h+pbKeyObject], ebx
0x180001349  call    WPP_SF_sDsd
0x18000134e  jmp     loc_18000125D
0x180001353  lea     rdx, aTls13preshared; "TLS13PRESHAREDKEY"
0x18000135a  mov     rcx, r14; String1
0x18000135d  call    wcscmp
0x180001362  test    eax, eax
0x180001364  jz      loc_18000157F
0x18000136a  lea     rdx, aTlsKemCipherte; "TLS_KEM_CIPHERTEXT"
0x180001371  mov     rcx, r14; String1
0x180001374  call    wcscmp
0x180001379  test    eax, eax
0x18000137b  jz      loc_180001413
0x180001381  lea     rdx, aMlkempublicblo; "MLKEMPUBLICBLOB"
0x180001388  mov     rcx, r14; String1
0x18000138b  call    wcscmp
0x180001390  test    eax, eax
0x180001392  jz      loc_180001601
0x180001398  lea     rdx, aTlsHybridKey; "TLS_HYBRID_KEY"
0x18000139f  mov     rcx, r14; String1
0x1800013a2  call    wcscmp
0x1800013a7  mov     edx, dword ptr [rbp+47h+arg_20]; cbData
0x1800013aa  mov     r9, r15
0x1800013ad  mov     r8, r14; pszBlobType
0x1800013b0  mov     rcx, rsi; pbData
0x1800013b3  test    eax, eax
0x1800013b5  jz      loc_180001627
0x1800013bb  call    SslpImportEphemeralKeyWithNCrypt
0x1800013c0  mov     ebx, eax
0x1800013c2  test    eax, eax
0x1800013c4  jns     loc_18000125B
0x1800013ca  mov     r9d, 0EE8h
0x1800013d0  mov     ecx, eax
0x1800013d2  jmp     loc_180001651
0x1800013d7  cmp     ecx, 5
0x1800013da  jz      loc_180001216
0x1800013e0  lea     r14, aKeydatablob; "KeyDataBlob"
0x1800013e7  jmp     loc_180001216
0x1800013ec  mov     rdx, [rbp+47h+Size]
0x1800013f0  mov     ecx, dword ptr [rbp+47h+var_50+0Ch]
0x1800013f3  lea     eax, [rcx-4]
0x1800013f6  test    eax, 0FFFFFFFCh
0x1800013fb  jnz     loc_1800014B4
0x180001401  cmp     ecx, 5
0x180001404  jz      loc_1800014B4
0x18000140a  mov     r12d, [rbp+47h+var_C0]
0x18000140e  jmp     loc_180001132
0x180001413  mov     edx, dword ptr [rbp+47h+arg_20]
0x180001416  mov     r8, r15
0x180001419  mov     rcx, rsi
0x18000141c  call    SslpImportKemCipherText
0x180001421  mov     ebx, eax
0x180001423  test    eax, eax
0x180001425  jns     loc_18000125B
0x18000142b  mov     r9d, 0EC1h
0x180001431  jmp     short loc_1800013D0
0x180001433  mov     eax, [rbp+47h+var_C0]
0x180001436  mov     rcx, rdi
0x180001439  test    rax, rax
0x18000143c  jz      short loc_18000144A
0x18000143e  mov     byte ptr [rdi], 0
0x180001441  inc     rdi
0x180001444  sub     rax, 1
0x180001448  jnz     short loc_18000143E
0x18000144a  call    MSCryptFree
0x18000144f  jmp     loc_18000125D
0x180001454  mov     ebx, 80090026h
0x180001459  mov     r9d, 0DBFh
0x18000145f  mov     ecx, 80090026h
0x180001464  jmp     loc_180001651
0x180001469  mov     ebx, 80090009h
0x18000146e  mov     r9d, 0DCDh
0x180001474  mov     ecx, 80090009h
0x180001479  jmp     loc_180001651
0x18000147e  mov     r9d, 0DDDh
0x180001484  jmp     short loc_18000148C
0x180001486  mov     r9d, 0DE7h
0x18000148c  mov     ebx, 80090005h
0x180001491  mov     ecx, 80090005h
0x180001496  jmp     loc_180001651
0x18000149b  mov     r9d, 0DF0h
0x1800014a1  jmp     short loc_18000148C
0x1800014a3  cmp     eax, 30h ; '0'
0x1800014a6  jbe     loc_180001117
0x1800014ac  mov     r9d, 0DF9h
0x1800014b2  jmp     short loc_18000148C
0x1800014b4  mov     r8, [r12+10h]
0x1800014b9  mov     [rbp+47h+hAlgorithm], r8
0x1800014bd  test    r8, r8
0x1800014c0  jnz     short loc_1800014D7
0x1800014c2  mov     ebx, 80090029h
0x1800014c7  mov     r9d, 0E21h
  ... truncated ...
```

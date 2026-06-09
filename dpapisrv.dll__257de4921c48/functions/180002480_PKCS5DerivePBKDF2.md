# PKCS5DerivePBKDF2

- ea: `0x180002480`
- end: `0x1800029c3`
- name: `PKCS5DerivePBKDF2`
- size: `1347`
- prototype: `_BOOL8 __fastcall(UCHAR *, ULONG, __int128 *, __int64, unsigned int, unsigned int, char, PUCHAR, unsigned int)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ad44`
- `0x18001199c`
- `0x1800146ac`
- `0x180028b1c`
- `0x18002955c`

## callees

- `0x180002480`
- `0x1800029d0`
- `0x18001d810`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002890`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002890`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002848`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002848`
- `bcrypt!BCryptFinishHash` at `0x18000266d`
- `bcrypt!BCryptFinishHash` at `0x18000272a`
- `bcrypt!BCryptFinishHash` at `0x18000266d`
- `bcrypt!BCryptFinishHash` at `0x18000272a`
- `bcrypt!BCryptDestroyHash` at `0x18000287c`
- `bcrypt!BCryptDestroyHash` at `0x1800028ce`
- `bcrypt!BCryptDestroyHash` at `0x18000296d`
- `bcrypt!BCryptDestroyHash` at `0x18000287c`
- `bcrypt!BCryptDestroyHash` at `0x1800028ce`
- `bcrypt!BCryptDestroyHash` at `0x18000296d`
- `bcrypt!BCryptHashData` at `0x18000264f`
- `bcrypt!BCryptHashData` at `0x18000270b`
- `bcrypt!BCryptHashData` at `0x18000264f`
- `bcrypt!BCryptHashData` at `0x18000270b`
- `bcrypt!BCryptCreateHash` at `0x1800025c0`
- `bcrypt!BCryptCreateHash` at `0x18000290c`
- `bcrypt!BCryptCreateHash` at `0x1800029a5`
- `bcrypt!BCryptCreateHash` at `0x1800025c0`
- `bcrypt!BCryptCreateHash` at `0x18000290c`
- `bcrypt!BCryptCreateHash` at `0x1800029a5`
- `bcrypt!BCryptGetProperty` at `0x180002577`
- `bcrypt!BCryptGetProperty` at `0x180002577`

## pseudocode

```c
_BOOL8 __fastcall PKCS5DerivePBKDF2(
        UCHAR *a1,
        ULONG a2,
        __int128 *a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6,
        char a7,
        PUCHAR a8,
        unsigned int a9)
{
  unsigned int v9; // r15d
  NTSTATUS Property; // edi
  unsigned int v12; // eax
  ULONG v13; // r13d
  UCHAR *v14; // r12
  BCRYPT_ALG_HANDLE v15; // r14
  ULONG v16; // r9d
  __int128 v17; // xmm0
  unsigned int v18; // eax
  ULONG v19; // edi
  int v20; // r14d
  BCRYPT_HASH_HANDLE v21; // rsi
  BCRYPT_HASH_HANDLE v22; // rcx
  unsigned int i; // r12d
  ULONG v24; // r14d
  BCRYPT_HASH_HANDLE v25; // rdi
  int v26; // esi
  BCRYPT_HASH_HANDLE v27; // rcx
  unsigned int v28; // r8d
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rcx
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-B1h] BYREF
  BCRYPT_HASH_HANDLE hHash; // [rsp+48h] [rbp-A9h] BYREF
  ULONG cbSecret; // [rsp+50h] [rbp-A1h]
  PUCHAR pbHashObject; // [rsp+58h] [rbp-99h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+60h] [rbp-91h] BYREF
  ULONG pcbResult; // [rsp+68h] [rbp-89h] BYREF
  PUCHAR pbSecret; // [rsp+70h] [rbp-81h]
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+78h] [rbp-79h]
  UCHAR pbInput[16]; // [rsp+80h] [rbp-71h] BYREF
  __int16 v42; // [rsp+90h] [rbp-61h]
  char v43; // [rsp+92h] [rbp-5Fh]
  char v44; // [rsp+93h] [rbp-5Eh]
  UCHAR v45[16]; // [rsp+A0h] [rbp-51h] BYREF

  v9 = a5;
  cbSecret = a2;
  Property = -2146893792;
  pbSecret = a1;
  pcbResult = 0;
  *(_DWORD *)pbOutput = 0;
  phHash = 0;
  if ( !a6 || !a1 || !a3 || !a2 )
    return Property >= 0;
  if ( a5 == 32777 || a5 == 32772 )
  {
    v12 = 32772;
    v13 = 20;
    if ( a5 != 32777 )
      v12 = a5;
    v9 = v12;
  }
  else
  {
    if ( a5 != 32782 )
      return Property >= 0;
    v13 = 64;
  }
  v14 = 0;
  pbHashObject = 0;
  hAlgorithm = (BCRYPT_ALG_HANDLE)GetBCryptProviderHandle(v9);
  v15 = hAlgorithm;
  if ( hAlgorithm )
  {
    Property = BCryptGetProperty(hAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
    if ( Property >= 0 )
    {
      v16 = *(_DWORD *)pbOutput;
      if ( *(_DWORD *)pbOutput )
      {
        pbHashObject = (PUCHAR)LocalAlloc(0, *(unsigned int *)pbOutput);
        v14 = pbHashObject;
        if ( !pbHashObject )
          goto LABEL_50;
        v16 = *(_DWORD *)pbOutput;
      }
      Property = BCryptCreateHash(v15, &phHash, v14, v16, pbSecret, cbSecret, 0);
      if ( Property >= 0 )
      {
        v17 = *a3;
        v42 = 0;
        v43 = 0;
        v44 = a7;
        hHash = 0;
        *(_OWORD *)pbInput = v17;
        if ( v9 == 32772 )
          v18 = 20;
        else
          v18 = 64;
        v19 = a9;
        v20 = 0;
        v21 = phHash;
        if ( a9 > v18 )
          v19 = v18;
        if ( phHash )
        {
          v22 = phHash;
          hHash = phHash;
        }
        else
        {
          if ( BCryptCreateHash(hAlgorithm, &hHash, v14, *(ULONG *)pbOutput, pbSecret, cbSecret, 0) < 0 )
          {
LABEL_22:
            if ( hHash && v21 != hHash )
              BCryptDestroyHash(hHash);
            if ( v20 )
            {
              for ( i = 1; ; ++i )
              {
                if ( i >= a6 )
                {
                  v14 = pbHashObject;
                  Property = 0;
                  goto LABEL_51;
                }
                hHash = 0;
                if ( v9 == 32772 )
                  v24 = 20;
                else
                  v24 = 64;
                v25 = phHash;
                v26 = 0;
                if ( phHash )
                {
                  v27 = phHash;
                  hHash = phHash;
                }
                else
                {
                  if ( BCryptCreateHash(hAlgorithm, &hHash, pbHashObject, *(ULONG *)pbOutput, pbSecret, cbSecret, 0) < 0 )
                    goto LABEL_35;
                  v27 = hHash;
                }
                if ( BCryptHashData(v27, a8, v13, 0) >= 0 && BCryptFinishHash(hHash, v45, v24, 0) >= 0 )
                  v26 = 1;
LABEL_35:
                if ( hHash && v25 != hHash )
                  BCryptDestroyHash(hHash);
                if ( !v26 )
                {
                  v14 = pbHashObject;
                  break;
                }
                v28 = v13 >> 2;
                v29 = 0;
                v30 = (v13 >> 2) - 1;
                if ( a8 > &v45[4 * v30] || &a8[4 * v30] < v45 )
                {
                  if ( v28 < 0x10 )
                    goto LABEL_69;
                  do
                  {
                    *(__m128 *)&a8[4 * v29] = _mm_xor_ps(
                                                (__m128)_mm_loadu_si128((const __m128i *)&v45[4 * v29]),
                                                (__m128)_mm_loadu_si128((const __m128i *)&a8[4 * v29]));
                    *(__m128 *)&a8[4 * (unsigned int)(v29 + 4)] = _mm_xor_ps(
                                                                    (__m128)_mm_loadu_si128((const __m128i *)&v45[4 * (unsigned int)(v29 + 4)]),
                                                                    (__m128)_mm_loadu_si128((const __m128i *)&a8[4 * (unsigned int)(v29 + 4)]));
                    *(__m128 *)&a8[4 * (unsigned int)(v29 + 8)] = _mm_xor_ps(
                                                                    (__m128)_mm_loadu_si128((const __m128i *)&v45[4 * (unsigned int)(v29 + 8)]),
                                                                    (__m128)_mm_loadu_si128((const __m128i *)&a8[4 * (unsigned int)(v29 + 8)]));
                    v31 = (unsigned int)(v29 + 12);
                    v29 = (unsigned int)(v29 + 16);
                    *(__m128 *)&a8[4 * v31] = _mm_xor_ps(
                                                (__m128)_mm_loadu_si128((const __m128i *)&v45[4 * v31]),
                                                (__m128)_mm_loadu_si128((const __m128i *)&a8[4 * v31]));
                  }
                  while ( (unsigned int)v29 < (v28 & 0xFFFFFFF0) );
                  if ( (v28 & 0xF) >= 2 )
                  {
LABEL_69:
                    do
                    {
                      *(_QWORD *)&a8[4 * v29] ^= *(_QWORD *)&v45[4 * v29];
                      v29 = (unsigned int)(v29 + 2);
                    }
                    while ( (unsigned int)v29 < (v28 & 0xFFFFFFFE) );
                  }
                }
                for ( ; (unsigned int)v29 < v28; v29 = (unsigned int)(v29 + 1) )
                  *(_DWORD *)&a8[4 * v29] ^= *(_DWORD *)&v45[4 * v29];
              }
            }
LABEL_50:
            Property = -2146893792;
            goto LABEL_51;
          }
          v22 = hHash;
        }
        if ( BCryptHashData(v22, pbInput, 0x14u, 0) >= 0 && BCryptFinishHash(hHash, a8, v19, 0) >= 0 )
          v20 = 1;
        goto LABEL_22;
      }
    }
  }
LABEL_51:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v14 )
    LocalFree(v14);
  return Property >= 0;
}

```

## disassembly

```asm
0x180002480  push    rbp
0x180002482  push    rbx
0x180002483  push    rsi
0x180002484  push    rdi
0x180002485  push    r15
0x180002487  lea     rbp, [rsp-0Fh]
0x18000248c  sub     rsp, 100h
0x180002493  mov     rax, cs:__security_cookie
0x18000249a  xor     rax, rsp
0x18000249d  mov     [rbp+2Fh+var_40], rax
0x1800024a1  mov     r15d, [rbp+2Fh+arg_20]
0x1800024a5  mov     eax, edx
0x1800024a7  mov     rbx, [rbp+2Fh+arg_38]
0x1800024ab  mov     rsi, r8
0x1800024ae  mov     [rsp+120h+cbSecret], edx
0x1800024b2  mov     edi, 80090020h
0x1800024b7  xor     edx, edx
0x1800024b9  mov     [rsp+120h+pbSecret], rcx
0x1800024be  cmp     [rbp+2Fh+arg_28], 1
0x1800024c2  mov     [rsp+120h+var_B8], edx
0x1800024c6  mov     dword ptr [rsp+120h+pbOutput], edx
0x1800024ca  mov     [rsp+120h+phHash], rdx
0x1800024cf  jb      loc_1800028AC
0x1800024d5  test    rcx, rcx
0x1800024d8  jz      loc_1800028AC
0x1800024de  test    r8, r8
0x1800024e1  jz      loc_1800028AC
0x1800024e7  test    eax, eax
0x1800024e9  jz      loc_1800028AC
0x1800024ef  mov     [rsp+120h+var_28], r13
0x1800024f7  cmp     r15d, 8009h
0x1800024fe  jnz     loc_180002934
0x180002504  cmp     r15d, 8009h
0x18000250b  mov     eax, 8004h
0x180002510  mov     r13d, 14h
0x180002516  cmovnz  eax, r15d
0x18000251a  mov     r15d, eax
0x18000251d  mov     [rsp+120h+arg_18], r12
0x180002525  mov     r8d, 28h ; '('
0x18000252b  mov     ecx, r15d; unsigned int
0x18000252e  mov     [rsp+120h+var_30], r14
0x180002536  mov     r12, rdx
0x180002539  mov     [rsp+120h+pbHashObject], rdx
0x18000253e  call    GetBCryptProviderHandle
0x180002543  mov     [rbp+2Fh+hAlgorithm], rax
0x180002547  mov     r14, rax
0x18000254a  test    rax, rax
0x18000254d  jz      loc_18000286A
0x180002553  lea     rax, [rsp+120h+var_B8]
0x180002558  mov     [rsp+120h+dwFlags], r12d; dwFlags
0x18000255d  mov     r9d, 4; cbOutput
0x180002563  mov     [rsp+120h+pcbResult], rax; pcbResult
0x180002568  lea     r8, [rsp+120h+pbOutput]; pbOutput
0x18000256d  mov     rcx, r14; hObject
0x180002570  lea     rdx, pszProperty; "ObjectLength"
0x180002577  call    cs:__imp_BCryptGetProperty
0x18000257e  nop     dword ptr [rax+rax+00h]
0x180002583  mov     edi, eax
0x180002585  test    eax, eax
0x180002587  js      loc_18000286A
0x18000258d  mov     r9d, dword ptr [rsp+120h+pbOutput]; cbHashObject
0x180002592  test    r9d, r9d
0x180002595  jnz     loc_180002843
0x18000259b  mov     eax, [rsp+120h+cbSecret]
0x18000259f  lea     rdx, [rsp+120h+phHash]; phHash
0x1800025a4  mov     [rsp+120h+var_F0], 0; dwFlags
0x1800025ac  mov     r8, r12; pbHashObject
0x1800025af  mov     [rsp+120h+dwFlags], eax; cbSecret
0x1800025b3  mov     rcx, r14; hAlgorithm
0x1800025b6  mov     rax, [rsp+120h+pbSecret]
0x1800025bb  mov     [rsp+120h+pcbResult], rax; pbSecret
0x1800025c0  call    cs:__imp_BCryptCreateHash
0x1800025c7  nop     dword ptr [rax+rax+00h]
0x1800025cc  mov     edi, eax
0x1800025ce  test    eax, eax
0x1800025d0  js      loc_18000286A
0x1800025d6  movups  xmm0, xmmword ptr [rsi]
0x1800025d9  movzx   eax, [rbp+2Fh+arg_30]
0x1800025dd  xor     ecx, ecx
0x1800025df  mov     [rbp+2Fh+var_90], 0
0x1800025e5  mov     [rbp+2Fh+var_8E], 0
0x1800025e9  mov     [rbp+2Fh+var_8D], al
0x1800025ec  mov     [rsp+120h+hHash], rcx
0x1800025f1  movups  xmmword ptr [rbp+2Fh+pbInput], xmm0
0x1800025f5  cmp     r15d, 8009h
0x1800025fc  jz      loc_18000292A
0x180002602  cmp     r15d, 8004h
0x180002609  jz      loc_18000292A
0x18000260f  cmp     r15d, 800Eh
0x180002616  jnz     loc_180002865
0x18000261c  mov     eax, 40h ; '@'
0x180002621  mov     edi, [rbp+2Fh+arg_40]
0x180002624  mov     r14d, ecx
0x180002627  mov     rsi, [rsp+120h+phHash]
0x18000262c  cmp     edi, eax
0x18000262e  cmova   edi, eax
0x180002631  test    rsi, rsi
0x180002634  jz      loc_18000297E
0x18000263a  mov     rcx, rsi; hHash
0x18000263d  mov     [rsp+120h+hHash], rcx
0x180002642  xor     r9d, r9d; dwFlags
0x180002645  lea     rdx, [rbp+2Fh+pbInput]; pbInput
0x180002649  mov     r8d, 14h; cbInput
0x18000264f  call    cs:__imp_BCryptHashData
0x180002656  nop     dword ptr [rax+rax+00h]
0x18000265b  test    eax, eax
0x18000265d  js      short loc_180002683
0x18000265f  mov     rcx, [rsp+120h+hHash]; hHash
0x180002664  xor     r9d, r9d; dwFlags
0x180002667  mov     r8d, edi; cbOutput
0x18000266a  mov     rdx, rbx; pbOutput
0x18000266d  call    cs:__imp_BCryptFinishHash
0x180002674  nop     dword ptr [rax+rax+00h]
0x180002679  test    eax, eax
0x18000267b  js      short loc_180002683
0x18000267d  mov     r14d, 1
0x180002683  mov     rcx, [rsp+120h+hHash]; hHash
0x180002688  test    rcx, rcx
0x18000268b  jz      short loc_180002696
0x18000268d  cmp     rsi, rcx
0x180002690  jnz     loc_18000296D
0x180002696  test    r14d, r14d
0x180002699  jz      loc_180002865
0x18000269f  mov     r12d, 1
0x1800026a5  cmp     r12d, [rbp+2Fh+arg_28]
0x1800026a9  jnb     loc_1800028DF
0x1800026af  mov     [rsp+120h+hHash], 0
0x1800026b8  cmp     r15d, 8009h
0x1800026bf  jz      loc_180002838
0x1800026c5  cmp     r15d, 8004h
0x1800026cc  jz      loc_180002838
0x1800026d2  cmp     r15d, 800Eh
0x1800026d9  jnz     loc_180002963
0x1800026df  mov     r14d, 40h ; '@'
0x1800026e5  mov     rdi, [rsp+120h+phHash]
0x1800026ea  xor     esi, esi
0x1800026ec  mov     r9d, dword ptr [rsp+120h+pbOutput]; cbHashObject
0x1800026f1  test    rdi, rdi
0x1800026f4  jz      loc_1800028E8
0x1800026fa  mov     rcx, rdi; hHash
0x1800026fd  mov     [rsp+120h+hHash], rcx
0x180002702  xor     r9d, r9d; dwFlags
0x180002705  mov     r8d, r13d; cbInput
0x180002708  mov     rdx, rbx; pbInput
0x18000270b  call    cs:__imp_BCryptHashData
0x180002712  nop     dword ptr [rax+rax+00h]
0x180002717  test    eax, eax
0x180002719  js      short loc_18000273F
0x18000271b  mov     rcx, [rsp+120h+hHash]; hHash
0x180002720  lea     rdx, [rbp+2Fh+var_80]; pbOutput
0x180002724  xor     r9d, r9d; dwFlags
0x180002727  mov     r8d, r14d; cbOutput
0x18000272a  call    cs:__imp_BCryptFinishHash
0x180002731  nop     dword ptr [rax+rax+00h]
0x180002736  test    eax, eax
0x180002738  js      short loc_18000273F
0x18000273a  mov     esi, 1
0x18000273f  mov     rcx, [rsp+120h+hHash]; hHash
0x180002744  test    rcx, rcx
0x180002747  jz      short loc_180002752
0x180002749  cmp     rdi, rcx
0x18000274c  jnz     loc_1800028CE
0x180002752  test    esi, esi
0x180002754  jz      loc_180002963
0x18000275a  mov     r8d, r13d
0x18000275d  lea     rcx, [rbp+2Fh+var_80]
0x180002761  shr     r8d, 2
0x180002765  xor     eax, eax
0x180002767  lea     edx, [r8-1]
0x18000276b  lea     rcx, [rcx+rdx*4]
0x18000276f  cmp     rbx, rcx
0x180002772  ja      short loc_180002785
0x180002774  lea     rcx, [rbx+rdx*4]
0x180002778  lea     rdx, [rbp+2Fh+var_80]
0x18000277c  cmp     rcx, rdx
0x18000277f  jnb     loc_18000281A
0x180002785  cmp     r8d, 10h
0x180002789  jb      short loc_1800027FA
0x18000278b  mov     r9d, r8d
0x18000278e  and     r9d, 0FFFFFFF0h
0x180002792  movdqu  xmm0, xmmword ptr [rbx+rax*4]
0x180002797  lea     ecx, [rax+4]
0x18000279a  movdqu  xmm1, xmmword ptr [rbp+rax*4+2Fh+var_80]
0x1800027a0  xorps   xmm1, xmm0
0x1800027a3  movdqu  xmmword ptr [rbx+rax*4], xmm1
0x1800027a8  movdqu  xmm0, xmmword ptr [rbx+rcx*4]
0x1800027ad  movdqu  xmm1, xmmword ptr [rbp+rcx*4+2Fh+var_80]
0x1800027b3  xorps   xmm1, xmm0
0x1800027b6  movdqu  xmmword ptr [rbx+rcx*4], xmm1
0x1800027bb  lea     ecx, [rax+8]
0x1800027be  movdqu  xmm0, xmmword ptr [rbx+rcx*4]
0x1800027c3  movdqu  xmm1, xmmword ptr [rbp+rcx*4+2Fh+var_80]
0x1800027c9  xorps   xmm1, xmm0
0x1800027cc  movdqu  xmmword ptr [rbx+rcx*4], xmm1
0x1800027d1  lea     ecx, [rax+0Ch]
0x1800027d4  add     eax, 10h
0x1800027d7  movdqu  xmm0, xmmword ptr [rbx+rcx*4]
0x1800027dc  movdqu  xmm1, xmmword ptr [rbp+rcx*4+2Fh+var_80]
0x1800027e2  xorps   xmm1, xmm0
0x1800027e5  movdqu  xmmword ptr [rbx+rcx*4], xmm1
0x1800027ea  cmp     eax, r9d
0x1800027ed  jb      short loc_180002792
0x1800027ef  mov     ecx, r8d
0x1800027f2  and     cl, 0Fh
0x1800027f5  cmp     cl, 2
0x1800027f8  jb      short loc_18000281A
0x1800027fa  mov     edx, r8d
0x1800027fd  and     edx, 0FFFFFFFEh
0x180002800  movq    xmm0, qword ptr [rbx+rax*4]
0x180002805  movq    xmm1, qword ptr [rbp+rax*4+2Fh+var_80]
0x18000280b  xorps   xmm1, xmm0
0x18000280e  movq    qword ptr [rbx+rax*4], xmm1
0x180002813  add     eax, 2
0x180002816  cmp     eax, edx
0x180002818  jb      short loc_180002800
0x18000281a  cmp     eax, r8d
0x18000281d  jnb     short loc_180002830
0x18000281f  mov     ecx, dword ptr [rbp+rax*4+2Fh+var_80]
0x180002823  lea     rdx, [rbx+rax*4]
0x180002827  xor     [rdx], ecx
0x180002829  inc     eax
0x18000282b  cmp     eax, r8d
0x18000282e  jb      short loc_18000281F
0x180002830  inc     r12d
0x180002833  jmp     loc_1800026A5
0x180002838  mov     r14d, 14h
0x18000283e  jmp     loc_1800026E5
0x180002843  mov     rdx, r9; uBytes
0x180002846  xor     ecx, ecx; uFlags
0x180002848  call    cs:__imp_LocalAlloc
0x18000284f  nop     dword ptr [rax+rax+00h]
0x180002854  mov     [rsp+120h+pbHashObject], rax
0x180002859  mov     r12, rax
0x18000285c  test    rax, rax
0x18000285f  jnz     loc_180002959
0x180002865  mov     edi, 80090020h
0x18000286a  mov     rcx, [rsp+120h+phHash]; hHash
0x18000286f  mov     r14, [rsp+120h+var_30]
0x180002877  test    rcx, rcx
0x18000287a  jz      short loc_180002888
0x18000287c  call    cs:__imp_BCryptDestroyHash
0x180002883  nop     dword ptr [rax+rax+00h]
0x180002888  test    r12, r12
0x18000288b  jz      short loc_18000289C
0x18000288d  mov     rcx, r12; hMem
0x180002890  call    cs:__imp_LocalFree
0x180002897  nop     dword ptr [rax+rax+00h]
0x18000289c  mov     r12, [rsp+120h+arg_18]
0x1800028a4  mov     r13, [rsp+120h+var_28]
0x1800028ac  not     edi
0x1800028ae  shr     edi, 1Fh
0x1800028b1  mov     eax, edi
0x1800028b3  mov     rcx, [rbp+2Fh+var_40]
0x1800028b7  xor     rcx, rsp; StackCookie
0x1800028ba  call    __security_check_cookie
0x1800028bf  add     rsp, 100h
0x1800028c6  pop     r15
0x1800028c8  pop     rdi
0x1800028c9  pop     rsi
0x1800028ca  pop     rbx
0x1800028cb  pop     rbp
0x1800028cc  retn
0x1800028ce  call    cs:__imp_BCryptDestroyHash
0x1800028d5  nop     dword ptr [rax+rax+00h]
0x1800028da  jmp     loc_180002752
0x1800028df  mov     r12, [rsp+120h+pbHashObject]
0x1800028e4  xor     edi, edi
0x1800028e6  jmp     short loc_18000286A
0x1800028e8  mov     eax, [rsp+120h+cbSecret]
0x1800028ec  lea     rdx, [rsp+120h+hHash]; phHash
0x1800028f1  mov     r8, [rsp+120h+pbHashObject]; pbHashObject
0x1800028f6  mov     rcx, [rbp+2Fh+hAlgorithm]; hAlgorithm
0x1800028fa  mov     [rsp+120h+var_F0], esi; dwFlags
0x1800028fe  mov     [rsp+120h+dwFlags], eax; cbSecret
0x180002902  mov     rax, [rsp+120h+pbSecret]
0x180002907  mov     [rsp+120h+pcbResult], rax; pbSecret
0x18000290c  call    cs:__imp_BCryptCreateHash
0x180002913  nop     dword ptr [rax+rax+00h]
0x180002918  test    eax, eax
0x18000291a  js      loc_18000273F
0x180002920  mov     rcx, [rsp+120h+hHash]
0x180002925  jmp     loc_180002702
0x18000292a  mov     eax, 14h
0x18000292f  jmp     loc_180002621
0x180002934  cmp     r15d, 8004h
0x18000293b  jz      loc_180002504
0x180002941  cmp     r15d, 800Eh
0x180002948  jnz     loc_1800028A4
0x18000294e  mov     r13d, 40h ; '@'
0x180002954  jmp     loc_18000251D
0x180002959  mov     r9d, dword ptr [rsp+120h+pbOutput]
0x18000295e  jmp     loc_18000259B
0x180002963  mov     r12, [rsp+120h+pbHashObject]
0x180002968  jmp     loc_180002865
0x18000296d  call    cs:__imp_BCryptDestroyHash
0x180002974  nop     dword ptr [rax+rax+00h]
0x180002979  jmp     loc_180002696
0x18000297e  mov     eax, [rsp+120h+cbSecret]
0x180002982  lea     rdx, [rsp+120h+hHash]; phHash
0x180002987  mov     r9d, dword ptr [rsp+120h+pbOutput]; cbHashObject
  ... truncated ...
```

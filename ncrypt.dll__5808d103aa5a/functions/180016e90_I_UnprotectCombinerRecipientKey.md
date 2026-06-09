# I_UnprotectCombinerRecipientKey

- ea: `0x180016e90`
- end: `0x1800173b9`
- name: `I_UnprotectCombinerRecipientKey`
- size: `1321`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800122c4`

## callees

- `0x180006be4`
- `0x18000d02c`
- `0x18000e120`
- `0x180010890`
- `0x180015c4c`
- `0x180016e90`
- `0x18001c690`
- `0x18001eb38`
- `0x18001f145`
- `0x18001f15d`
- `0x18001f1b0`
- `0x180020010`

## import_xrefs

- `NTASN1!__imp_RtlAsn1DecodeAndAllocate` at `0x180016fc2`
- `NTASN1!__imp_RtlAsn1DecodeAndAllocate` at `0x180016fc2`

## string_xrefs

- `0x180016f2b`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x180016fdd`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x180017182`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x1800172be`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x180017352`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`

## pseudocode

```c
__int64 __fastcall I_UnprotectCombinerRecipientKey(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        _DWORD *a7)
{
  UCHAR *v9; // rsi
  __int64 v10; // rdi
  __int64 v11; // r14
  __int64 v12; // rax
  unsigned int v13; // ebx
  __int64 v14; // rax
  __int64 v15; // rcx
  unsigned int BCryptOidInfo; // eax
  __int64 v17; // r9
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 (__fastcall *v21)(__int64); // rax
  __int64 v22; // rax
  char *v23; // r15
  unsigned int i; // edi
  __int64 v25; // rcx
  unsigned int v26; // eax
  __int64 v27; // rax
  _BYTE *v28; // rcx
  __int64 v29; // r9
  __int64 v30; // rcx
  _BYTE *v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rcx
  UCHAR *v34; // rax
  __int64 v36; // r14
  size_t *p_Size; // rdi
  unsigned __int64 v38; // rax
  unsigned __int64 v39; // rbx
  __int64 v40; // rcx
  unsigned __int64 v41; // rcx
  void *v42; // rsp
  void *v43; // rsp
  size_t *v44; // rax
  __int64 v45; // r8
  int v46; // eax
  __int64 v47; // r9
  __int64 v48; // rax
  size_t *v49; // rcx
  __int64 v50; // [rsp+0h] [rbp-40h] BYREF
  size_t v51; // [rsp+20h] [rbp-20h]
  size_t Size; // [rsp+40h] [rbp+0h] BYREF
  const void *v53; // [rsp+48h] [rbp+8h] BYREF
  ULONG cbInput[2]; // [rsp+50h] [rbp+10h]
  __int64 v55; // [rsp+58h] [rbp+18h] BYREF
  __int64 v56; // [rsp+60h] [rbp+20h] BYREF

  Size = 0;
  v53 = 0;
  v9 = 0;
  *a6 = 0;
  LODWORD(v10) = 0;
  v55 = 0;
  v11 = 32LL * a2;
  *a7 = 0;
  v12 = *(_QWORD *)(a1 + 8);
  v56 = 0;
  if ( *(_DWORD *)(v11 + *(_QWORD *)(v12 + 8)) <= 8u )
  {
    if ( *(_DWORD *)a3 != 5 || *(_DWORD *)(a3 + 8) != 12 )
      goto LABEL_70;
    v14 = *(_QWORD *)(a3 + 16);
    v15 = *(_QWORD *)v14 + 0x7DFEFBFEF9D4F5FALL;
    if ( *(_QWORD *)v14 == 0x82010401062B0A06uLL )
      v15 = *(unsigned int *)(v14 + 8) - 67193399LL;
    if ( !v15 )
    {
      BCryptOidInfo = RtlAsn1DecodeAndAllocate(
                        ASN1_NCRYPT_MODULE_HANDLE,
                        29,
                        1,
                        *(_QWORD *)(a3 + 32),
                        *(unsigned int *)(a3 + 24),
                        0,
                        a4,
                        &v55);
      v13 = BCryptOidInfo;
      if ( BCryptOidInfo )
      {
        v17 = 497;
LABEL_12:
        v18 = BCryptOidInfo;
LABEL_13:
        DebugTraceError(
          v18,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
          v17);
        goto LABEL_36;
      }
      if ( *(_DWORD *)(v55 + 56) == 11 )
      {
        v19 = *(_QWORD *)(v55 + 64);
        v20 = *(_QWORD *)v19 - 0x365014886600906LL;
        if ( *(_QWORD *)v19 == 0x365014886600906LL )
        {
          v20 = *(unsigned __int16 *)(v19 + 8) - 260LL;
          if ( *(_WORD *)(v19 + 8) == 260 )
            v20 = *(unsigned __int8 *)(v19 + 10) - 45LL;
        }
        if ( !v20 )
        {
          BCryptOidInfo = CNG_FindBCryptOidInfo(*(_QWORD *)(v55 + 24), *(unsigned int *)(v55 + 16), 2, &v56);
          v13 = BCryptOidInfo;
          if ( BCryptOidInfo )
          {
            v17 = 520;
            goto LABEL_12;
          }
          v10 = (unsigned int)(32 * *(_DWORD *)(v11 + *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL)));
          v21 = *(__int64 (__fastcall **)(__int64))(a4 + 8);
          *(_QWORD *)cbInput = v10;
          v22 = v21(v10);
          v9 = (UCHAR *)v22;
          if ( !v22 )
          {
            v13 = -2146893810;
            v17 = 536;
            v18 = 2148073486LL;
            goto LABEL_13;
          }
          if ( (unsigned int)v10 < 0x20 )
          {
            v13 = -2147024362;
            v17 = 543;
            v18 = 2147942934LL;
            goto LABEL_13;
          }
          v23 = (char *)v22;
          for ( i = 0; ; ++i )
          {
            v25 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL);
            if ( i >= *(_DWORD *)(v25 + v11) )
              break;
            v26 = NCryptUnprotectKey(
                    *(_QWORD *)(*(_QWORD *)(v25 + v11 + 8) + 32LL * i + 16),
                    *(_DWORD *)(v55 + 8) + 160 * i,
                    a4,
                    a5,
                    (__int64)&v53,
                    (__int64)&Size + 4,
                    0);
            v13 = v26;
            if ( v26 )
            {
              v29 = 562;
              v30 = v26;
              goto LABEL_34;
            }
            if ( HIDWORD(Size) != 32 )
            {
              v13 = -2146893821;
              v29 = 569;
              v30 = 2148073475LL;
LABEL_34:
              DebugTraceError(
                v30,
                "Status",
                "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
                v29);
              goto LABEL_35;
            }
            memcpy_0(v23, v53, 0x20u);
            v27 = HIDWORD(Size);
            v28 = v53;
            v23 += HIDWORD(Size);
            if ( HIDWORD(Size) )
            {
              do
              {
                *v28++ = 0;
                --v27;
              }
              while ( v27 );
              v28 = v53;
            }
            (*(void (__fastcall **)(_BYTE *))(a4 + 16))(v28);
            v53 = 0;
          }
          v36 = v56;
          p_Size = 0;
          v38 = *(unsigned int *)(v56 + 60);
          LODWORD(Size) = v38;
          v39 = (unsigned int)v38;
          if ( !(_DWORD)v38
            || v38 > g_ulMaxStackAllocSize
            || v38 + g_ulAdditionalProbeSize + 8 < v38
            || !(unsigned int)VerifyStackAvailable() )
          {
            goto LABEL_73;
          }
          v40 = v39 + 23;
          if ( v39 + 23 <= v39 + 8 )
            v40 = 0xFFFFFFFFFFFFFF0LL;
          v41 = v40 & 0xFFFFFFFFFFFFFFF0uLL;
          v42 = alloca(v41);
          v43 = alloca(v41);
          p_Size = &Size;
          if ( &v50 == (__int64 *)-64LL || (LODWORD(Size) = 1801679955, (p_Size = (size_t *)&v53) == 0) )
          {
LABEL_73:
            if ( v39 + 8 >= v39 )
            {
              v44 = (size_t *)((__int64 (*)(void))g_pfnAllocate)();
              p_Size = v44;
              if ( v44 )
              {
                *(_DWORD *)v44 = 1885431112;
                p_Size = v44 + 1;
              }
            }
          }
          if ( !p_Size )
          {
            v13 = -2146893810;
            DebugTraceError(
              2148073486LL,
              "Status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
              591);
LABEL_35:
            LODWORD(v10) = cbInput[0];
            goto LABEL_36;
          }
          v45 = *(_QWORD *)(v36 + 8);
          LODWORD(v51) = Size;
          v46 = CNG_ComputeHash(v9, cbInput[0], v45, p_Size, v51, (ULONG *)&Size);
          v13 = v46;
          if ( v46 )
          {
            v47 = 605;
          }
          else
          {
            v46 = CNG_AesKeyUnwrap(a4, *(_QWORD *)(v55 + 104), *(unsigned int *)(v55 + 96), p_Size, Size, a6, a7);
            v13 = v46;
            if ( v46 >= 0 )
            {
LABEL_64:
              v48 = (unsigned int)Size;
              v49 = p_Size;
              if ( (_DWORD)Size )
              {
                do
                {
                  *(_BYTE *)v49 = 0;
                  v49 = (size_t *)((char *)v49 + 1);
                  --v48;
                }
                while ( v48 );
              }
              if ( *((_DWORD *)p_Size - 2) == 1885431112 )
                ((void (*)(void))g_pfnFree)();
              goto LABEL_35;
            }
            v47 = 622;
          }
          DebugTraceError(
            (unsigned int)v46,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
            v47);
          goto LABEL_64;
        }
      }
      v17 = 504;
    }
    else
    {
LABEL_70:
      v17 = 481;
    }
    v13 = -2146893819;
    v18 = 2148073477LL;
    goto LABEL_13;
  }
  v13 = -2146893819;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    return v13;
  WPP_SF_sDsd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    a2,
    (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
    (unsigned int)"Status",
    5,
    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
    217);
LABEL_36:
  v31 = v53;
  if ( v53 )
  {
    v32 = HIDWORD(Size);
    if ( HIDWORD(Size) )
    {
      do
      {
        *v31++ = 0;
        --v32;
      }
      while ( v32 );
    }
    (*(void (**)(void))(a4 + 16))();
  }
  if ( v9 )
  {
    v33 = (unsigned int)v10;
    v34 = v9;
    if ( (_DWORD)v10 )
    {
      do
      {
        *v34++ = 0;
        --v33;
      }
      while ( v33 );
    }
    (*(void (__fastcall **)(UCHAR *))(a4 + 16))(v9);
  }
  return v13;
}

```

## disassembly

```asm
0x180016e90  push    rbp
0x180016e92  push    rbx
0x180016e93  push    rsi
0x180016e94  push    rdi
0x180016e95  push    r12
0x180016e97  push    r13
0x180016e99  push    r14
0x180016e9b  push    r15
0x180016e9d  sub     rsp, 78h
0x180016ea1  lea     rbp, [rsp+40h]
0x180016ea6  mov     rax, cs:__security_cookie
0x180016ead  xor     rax, rbp
0x180016eb0  mov     [rbp+70h+var_48], rax
0x180016eb4  mov     rax, [rbp+70h+arg_28]
0x180016ebb  xor     r15d, r15d
0x180016ebe  mov     dword ptr [rbp+70h+Size], r15d
0x180016ec2  mov     r12, rcx
0x180016ec5  mov     [rbp+70h+var_68], r15
0x180016ec9  mov     r13, r9
0x180016ecc  mov     dword ptr [rbp+70h+Size+4], r15d
0x180016ed0  mov     esi, r15d
0x180016ed3  mov     [rax], r15
0x180016ed6  mov     edi, r15d
0x180016ed9  mov     rax, [rbp+70h+arg_30]
0x180016ee0  mov     [rbp+70h+var_58], r15
0x180016ee4  mov     r14d, edx
0x180016ee7  shl     r14, 5
0x180016eeb  mov     [rax], r15d
0x180016eee  mov     rax, [rcx+8]
0x180016ef2  mov     [rbp+70h+var_50], r15
0x180016ef6  mov     rcx, [rax+8]
0x180016efa  cmp     dword ptr [r14+rcx], 8
0x180016eff  jbe     short loc_180016F58
0x180016f01  mov     ebx, 80090005h
0x180016f06  mov     rcx, cs:WPP_GLOBAL_Control
0x180016f0d  lea     rax, WPP_GLOBAL_Control
0x180016f14  cmp     rcx, rax
0x180016f17  jz      loc_1800171E5
0x180016f1d  test    byte ptr [rcx+1Ch], 1
0x180016f21  jz      loc_1800171E5
0x180016f27  mov     rcx, [rcx+10h]
0x180016f2b  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180016f32  mov     dword ptr [rsp+0B0h+var_80], 1D9h
0x180016f3a  lea     r9, aStatus; "Status"
0x180016f41  mov     [rsp+0B0h+pbOutput], r8
0x180016f46  mov     dword ptr [rsp+0B0h+var_90], 80090005h
0x180016f4e  call    WPP_SF_sDsd
0x180016f53  jmp     loc_180017195
0x180016f58  cmp     dword ptr [r8], 5
0x180016f5c  jnz     loc_1800173B1
0x180016f62  cmp     dword ptr [r8+8], 0Ch
0x180016f67  jnz     loc_1800173B1
0x180016f6d  mov     rax, [r8+10h]
0x180016f71  mov     rcx, [rax]
0x180016f74  sub     rcx, cs:qword_180023328
0x180016f7b  jnz     short loc_180016F89
0x180016f7d  mov     ecx, [rax+8]
0x180016f80  mov     eax, cs:dword_180023330
0x180016f86  sub     rcx, rax
0x180016f89  test    rcx, rcx
0x180016f8c  jnz     loc_1800173B1
0x180016f92  mov     eax, [r8+18h]
0x180016f96  lea     rcx, [rbp+70h+var_58]
0x180016f9a  mov     r9, [r8+20h]
0x180016f9e  mov     edx, 1Dh
0x180016fa3  mov     [rsp+0B0h+var_78], rcx
0x180016fa8  mov     rcx, cs:ASN1_NCRYPT_MODULE_HANDLE
0x180016faf  mov     [rsp+0B0h+var_80], r13
0x180016fb4  lea     r8d, [rdx-1Ch]
0x180016fb8  mov     [rsp+0B0h+pbOutput], r15
0x180016fbd  mov     [rsp+0B0h+var_90], rax
0x180016fc2  call    cs:__imp_RtlAsn1DecodeAndAllocate
0x180016fc8  mov     ebx, eax
0x180016fca  test    eax, eax
0x180016fcc  jz      short loc_180016FEE
0x180016fce  mov     r9d, 1F1h
0x180016fd4  mov     ecx, eax
0x180016fd6  lea     rdx, aStatus; "Status"
0x180016fdd  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180016fe4  call    DebugTraceError
0x180016fe9  jmp     loc_180017195
0x180016fee  mov     r10, [rbp+70h+var_58]
0x180016ff2  cmp     dword ptr [r10+38h], 0Bh
0x180016ff7  jnz     loc_18001739C
0x180016ffd  mov     rdx, [r10+40h]
0x180017001  mov     rcx, [rdx]
0x180017004  sub     rcx, cs:qword_180023BB8
0x18001700b  jnz     short loc_18001702B
0x18001700d  movzx   ecx, word ptr [rdx+8]
0x180017011  movzx   eax, cs:word_180023BC0
0x180017018  sub     rcx, rax
0x18001701b  jnz     short loc_18001702B
0x18001701d  movzx   ecx, byte ptr [rdx+0Ah]
0x180017021  movzx   eax, cs:byte_180023BC2
0x180017028  sub     rcx, rax
0x18001702b  test    rcx, rcx
0x18001702e  jnz     loc_18001739C
0x180017034  mov     edx, [r10+10h]
0x180017038  lea     r8d, [rcx+2]
0x18001703c  mov     rcx, [r10+18h]
0x180017040  lea     r9, [rbp+70h+var_50]
0x180017044  call    CNG_FindBCryptOidInfo
0x180017049  mov     ebx, eax
0x18001704b  test    eax, eax
0x18001704d  jz      short loc_18001705A
0x18001704f  mov     r9d, 208h
0x180017055  jmp     loc_180016FD4
0x18001705a  mov     rax, [r12+8]
0x18001705f  mov     rcx, [rax+8]
0x180017063  mov     eax, [r14+rcx]
0x180017067  shl     eax, 5
0x18001706a  mov     edi, eax
0x18001706c  mov     ecx, eax
0x18001706e  mov     rax, [r13+8]
0x180017072  mov     qword ptr [rbp+70h+cbInput], rdi
0x180017076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001707b  mov     rsi, rax
0x18001707e  test    rax, rax
0x180017081  jnz     short loc_180017098
0x180017083  mov     ebx, 8009000Eh
0x180017088  mov     r9d, 218h
0x18001708e  mov     ecx, 8009000Eh
0x180017093  jmp     loc_180016FD6
0x180017098  cmp     edi, 20h ; ' '
0x18001709b  jnb     short loc_1800170B2
0x18001709d  mov     ebx, 80070216h
0x1800170a2  mov     r9d, 21Fh
0x1800170a8  mov     ecx, 80070216h
0x1800170ad  jmp     loc_180016FD6
0x1800170b2  mov     r15, rsi
0x1800170b5  xor     edi, edi
0x1800170b7  mov     rax, [r12+8]
0x1800170bc  mov     rcx, [rax+8]
0x1800170c0  cmp     edi, [rcx+r14]
0x1800170c4  jnb     loc_180017211
0x1800170ca  mov     rax, [rbp+70h+var_58]
0x1800170ce  lea     rdx, [rdi+rdi*4]
0x1800170d2  mov     rcx, [rcx+r14+8]
0x1800170d7  mov     r8, r13
0x1800170da  mov     r9, [rbp+70h+arg_20]
0x1800170e1  shl     rdx, 5
0x1800170e5  add     rdx, [rax+8]
0x1800170e9  lea     rax, [rbp+70h+Size+4]
0x1800170ed  mov     dword ptr [rsp+0B0h+var_80], 0
0x1800170f5  mov     [rsp+0B0h+pbOutput], rax
0x1800170fa  lea     rax, [rbp+70h+var_68]
0x1800170fe  mov     r10d, edi
0x180017101  shl     r10, 5
0x180017105  mov     [rsp+0B0h+var_90], rax
0x18001710a  mov     rcx, [rcx+r10+10h]
0x18001710f  call    NCryptUnprotectKey
0x180017114  mov     ebx, eax
0x180017116  test    eax, eax
0x180017118  jnz     loc_180017204
0x18001711e  cmp     dword ptr [rbp+70h+Size+4], 20h ; ' '
0x180017122  jnz     short loc_18001716B
0x180017124  mov     r8d, dword ptr [rbp+70h+Size+4]; Size
0x180017128  mov     rcx, r15; void *
0x18001712b  mov     rdx, [rbp+70h+var_68]; Src
0x18001712f  call    memcpy_0
0x180017134  mov     eax, dword ptr [rbp+70h+Size+4]
0x180017137  mov     rcx, [rbp+70h+var_68]
0x18001713b  add     r15, rax
0x18001713e  test    rax, rax
0x180017141  jz      short loc_180017153
0x180017143  mov     byte ptr [rcx], 0
0x180017146  inc     rcx
0x180017149  sub     rax, 1
0x18001714d  jnz     short loc_180017143
0x18001714f  mov     rcx, [rbp+70h+var_68]
0x180017153  mov     rax, [r13+10h]
0x180017157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001715c  inc     edi
0x18001715e  mov     [rbp+70h+var_68], 0
0x180017166  jmp     loc_1800170B7
0x18001716b  mov     ebx, 80090003h
0x180017170  mov     r9d, 239h
0x180017176  mov     ecx, 80090003h
0x18001717b  lea     rdx, aStatus; "Status"
0x180017182  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180017189  call    DebugTraceError
0x18001718e  xor     r15d, r15d
0x180017191  mov     rdi, qword ptr [rbp+70h+cbInput]
0x180017195  mov     rcx, [rbp+70h+var_68]
0x180017199  test    rcx, rcx
0x18001719c  jz      short loc_1800171BF
0x18001719e  mov     eax, dword ptr [rbp+70h+Size+4]
0x1800171a1  test    rax, rax
0x1800171a4  jz      short loc_1800171B6
0x1800171a6  mov     [rcx], r15b
0x1800171a9  inc     rcx
0x1800171ac  sub     rax, 1
0x1800171b0  jnz     short loc_1800171A6
0x1800171b2  mov     rcx, [rbp+70h+var_68]
0x1800171b6  mov     rax, [r13+10h]
0x1800171ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171bf  test    rsi, rsi
0x1800171c2  jz      short loc_1800171E5
0x1800171c4  mov     ecx, edi
0x1800171c6  mov     rax, rsi
0x1800171c9  test    edi, edi
0x1800171cb  jz      short loc_1800171D9
0x1800171cd  mov     [rax], r15b
0x1800171d0  inc     rax
0x1800171d3  sub     rcx, 1
0x1800171d7  jnz     short loc_1800171CD
0x1800171d9  mov     rax, [r13+10h]
0x1800171dd  mov     rcx, rsi
0x1800171e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171e5  mov     eax, ebx
0x1800171e7  mov     rcx, [rbp+70h+var_48]
0x1800171eb  xor     rcx, rbp; StackCookie
0x1800171ee  call    __security_check_cookie
0x1800171f3  lea     rsp, [rbp+38h]
0x1800171f7  pop     r15
0x1800171f9  pop     r14
0x1800171fb  pop     r13
0x1800171fd  pop     r12
0x1800171ff  pop     rdi
0x180017200  pop     rsi
0x180017201  pop     rbx
0x180017202  pop     rbp
0x180017203  retn
0x180017204  mov     r9d, 232h
0x18001720a  mov     ecx, eax
0x18001720c  jmp     loc_18001717B
0x180017211  mov     r14, [rbp+70h+var_50]
0x180017215  xor     r15d, r15d
0x180017218  mov     edi, r15d
0x18001721b  mov     r12d, 70616548h
0x180017221  mov     eax, [r14+3Ch]
0x180017225  mov     dword ptr [rbp+70h+Size], eax
0x180017228  mov     ebx, eax
0x18001722a  test    eax, eax
0x18001722c  jz      short loc_18001728F
0x18001722e  cmp     rax, cs:g_ulMaxStackAllocSize
0x180017235  ja      short loc_18001728F
0x180017237  mov     rcx, cs:g_ulAdditionalProbeSize
0x18001723e  add     rcx, 8
0x180017242  add     rcx, rax
0x180017245  cmp     rcx, rax
0x180017248  jb      short loc_18001728F
0x18001724a  call    VerifyStackAvailable
0x18001724f  test    eax, eax
0x180017251  jz      short loc_18001728F
0x180017253  lea     rax, [rbx+8]
0x180017257  lea     rcx, [rax+0Fh]
0x18001725b  cmp     rcx, rax
0x18001725e  ja      short loc_18001726A
0x180017260  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001726a  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001726e  mov     rax, rcx
0x180017271  call    __chkstk_0
0x180017276  sub     rsp, rcx
0x180017279  lea     rdi, [rsp+0B0h+Size]
0x18001727e  test    rdi, rdi
0x180017281  jz      short loc_18001728F
0x180017283  mov     dword ptr [rdi], 6B637453h
0x180017289  add     rdi, 8
0x18001728d  jnz     short loc_1800172B3
0x18001728f  lea     rcx, [rbx+8]
0x180017293  cmp     rcx, rbx
0x180017296  jb      short loc_1800172B3
0x180017298  mov     rax, cs:g_pfnAllocate
0x18001729f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172a4  mov     rdi, rax
0x1800172a7  test    rax, rax
0x1800172aa  jz      short loc_1800172B3
0x1800172ac  mov     [rax], r12d
0x1800172af  add     rdi, 8
0x1800172b3  test    rdi, rdi
0x1800172b6  jnz     short loc_1800172E0
0x1800172b8  mov     r9d, 24Fh
0x1800172be  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800172c5  lea     rdx, aStatus; "Status"
0x1800172cc  mov     ecx, 8009000Eh
0x1800172d1  mov     ebx, 8009000Eh
0x1800172d6  call    DebugTraceError
0x1800172db  jmp     loc_180017191
0x1800172e0  mov     r8, [r14+8]
0x1800172e4  lea     rax, [rbp+70h+Size]
0x1800172e8  mov     edx, [rbp+70h+cbInput]; cbInput
0x1800172eb  mov     r9, rdi
0x1800172ee  mov     [rsp+0B0h+pbOutput], rax; pbOutput
0x1800172f3  mov     rcx, rsi; pbInput
0x1800172f6  mov     eax, dword ptr [rbp+70h+Size]
0x1800172f9  mov     dword ptr [rsp+0B0h+var_90], eax; Size
0x1800172fd  call    CNG_ComputeHash
0x180017302  mov     ebx, eax
0x180017304  test    eax, eax
0x180017306  jz      short loc_180017310
0x180017308  mov     r9d, 25Dh
0x18001730e  jmp     short loc_180017352
0x180017310  mov     rdx, [rbp+70h+var_58]
0x180017314  mov     r9, rdi
0x180017317  mov     rax, [rbp+70h+arg_30]
0x18001731e  mov     rcx, r13
0x180017321  mov     [rsp+0B0h+var_80], rax
0x180017326  mov     rax, [rbp+70h+arg_28]
0x18001732d  mov     r8d, [rdx+60h]
  ... truncated ...
```

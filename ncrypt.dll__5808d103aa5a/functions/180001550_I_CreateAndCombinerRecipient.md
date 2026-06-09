# I_CreateAndCombinerRecipient

- ea: `0x180001550`
- end: `0x180001c01`
- name: `I_CreateAndCombinerRecipient`
- size: `1713`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180003150`

## callees

- `0x180001550`
- `0x18000d02c`
- `0x18000e120`
- `0x1800106f0`
- `0x180015c4c`
- `0x18001c690`
- `0x18001ee20`
- `0x18001f004`
- `0x18001f145`
- `0x18001f175`
- `0x18001f1b0`
- `0x180020010`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x180001700`
- `bcrypt!BCryptGenRandom` at `0x180001700`
- `NTASN1!__imp_RtlAsn1EncodeAndAllocate` at `0x180001a07`
- `NTASN1!__imp_RtlAsn1EncodeAndAllocate` at `0x180001a86`
- `NTASN1!__imp_RtlAsn1EncodeAndAllocate` at `0x180001a07`
- `NTASN1!__imp_RtlAsn1EncodeAndAllocate` at `0x180001a86`
- `NTASN1!__imp_RtlAsn1DecodeAndAllocate` at `0x180001ace`
- `NTASN1!__imp_RtlAsn1DecodeAndAllocate` at `0x180001ace`

## string_xrefs

- `0x180001672`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x180001714`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x180001ae0`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x180001b54`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`

## pseudocode

```c
__int64 __fastcall I_CreateAndCombinerRecipient(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7,
        int a8)
{
  __int64 v10; // rdx
  int v11; // r8d
  unsigned int *v12; // rax
  __int64 v13; // rdi
  __int64 v14; // rcx
  unsigned int BCryptOidInfoStr; // eax
  unsigned int v16; // ebx
  __int64 v17; // r9
  __int64 v18; // rcx
  __int64 v19; // r13
  ULONG v20; // r14d
  UCHAR *v21; // rax
  UCHAR *v22; // r15
  unsigned int v23; // eax
  __int64 v24; // r9
  __int64 v25; // rcx
  int v26; // r10d
  __int64 i; // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // r8
  __int64 v31; // rdx
  __int64 v32; // rcx
  _OWORD *v33; // rdx
  unsigned int v34; // r8d
  __int64 v35; // rcx
  __int128 v36; // xmm1
  unsigned __int64 v37; // rax
  size_t *p_pbOutput; // rdi
  unsigned __int64 v39; // rbx
  __int64 v40; // rcx
  unsigned __int64 v41; // rcx
  void *v42; // rsp
  void *v43; // rsp
  size_t *v44; // rax
  __int64 v45; // r8
  int v46; // eax
  __int64 v47; // r9
  __int64 v48; // rcx
  UCHAR *v49; // rax
  __int64 v51; // [rsp+0h] [rbp-40h] BYREF
  size_t Size; // [rsp+20h] [rbp-20h]
  size_t pbOutput; // [rsp+40h] [rbp+0h] BYREF
  __int64 v54; // [rsp+48h] [rbp+8h] BYREF
  int v55; // [rsp+50h] [rbp+10h] BYREF
  unsigned int v56; // [rsp+54h] [rbp+14h]
  __int64 v57; // [rsp+58h] [rbp+18h] BYREF
  __int64 v58; // [rsp+60h] [rbp+20h] BYREF
  UCHAR *v59; // [rsp+68h] [rbp+28h]
  __int64 v60; // [rsp+70h] [rbp+30h] BYREF
  __int64 v61; // [rsp+78h] [rbp+38h] BYREF
  __int64 v62; // [rsp+80h] [rbp+40h] BYREF
  _QWORD *v63; // [rsp+88h] [rbp+48h]
  __int64 v64; // [rsp+90h] [rbp+50h]
  __int64 v65; // [rsp+98h] [rbp+58h]
  _QWORD *v66; // [rsp+A0h] [rbp+60h]
  _BYTE v67[4]; // [rsp+B0h] [rbp+70h] BYREF
  unsigned int v68; // [rsp+B4h] [rbp+74h]
  _OWORD *v69; // [rsp+B8h] [rbp+78h]
  int v70; // [rsp+C0h] [rbp+80h]
  __int64 v71; // [rsp+C8h] [rbp+88h]
  int v72; // [rsp+E8h] [rbp+A8h]
  __int64 *v73; // [rsp+F0h] [rbp+B0h]
  int v74; // [rsp+110h] [rbp+D0h]
  __int64 v75; // [rsp+118h] [rbp+D8h]
  _DWORD v76[4]; // [rsp+120h] [rbp+E0h] BYREF
  __int64 *v77; // [rsp+130h] [rbp+F0h]
  int v78; // [rsp+138h] [rbp+F8h]
  __int64 v79; // [rsp+140h] [rbp+100h]
  _QWORD v80[8]; // [rsp+1C0h] [rbp+180h] BYREF
  _OWORD v81[80]; // [rsp+200h] [rbp+1C0h] BYREF

  v65 = a3;
  v64 = a6;
  v66 = a7;
  v56 = a4;
  memset_0(v76, 0, 0xA0u);
  memset_0(v67, 0, 0x70u);
  memset_0(v81, 0, sizeof(v81));
  memset_0(v80, 0, sizeof(v80));
  *a7 = 0;
  v12 = *(unsigned int **)(a1 + 8);
  LODWORD(pbOutput) = 0;
  v58 = 0;
  v61 = 0;
  v57 = 0;
  v62 = 0;
  v54 = 0;
  v60 = 0;
  v55 = 0;
  if ( a2 < *v12 )
  {
    _mm_lfence();
    v13 = 32LL * a2;
    v14 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL);
    if ( *(_DWORD *)(v13 + v14) <= 8u )
    {
      BCryptOidInfoStr = CNG_FindBCryptOidInfoStr(v14, v10, &v54);
      v16 = BCryptOidInfoStr;
      if ( BCryptOidInfoStr )
      {
        v17 = 711;
        v18 = BCryptOidInfoStr;
LABEL_5:
        DebugTraceError(
          v18,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
          v17);
        goto LABEL_56;
      }
      v19 = v54;
      v71 = *(_QWORD *)(v54 + 48);
      v70 = *(_DWORD *)(v54 + 40);
      v20 = 32 * *(_DWORD *)(v13 + *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL));
      if ( v20 < 0x20 )
      {
        v16 = -2147024362;
        v17 = 728;
        v18 = 2147942934LL;
        goto LABEL_5;
      }
      v21 = (UCHAR *)(*(__int64 (__fastcall **)(_QWORD))(a5 + 8))(v20);
      v22 = v21;
      if ( !v21 )
      {
        v16 = -2146893810;
        v17 = 736;
        v18 = 2148073486LL;
        goto LABEL_5;
      }
      v23 = BCryptGenRandom(0, v21, v20, 2u);
      v16 = v23;
      if ( v23 )
      {
        v24 = 748;
LABEL_12:
        v25 = v23;
        goto LABEL_13;
      }
      v59 = v22;
      v69 = v81;
      v26 = (int)v22;
      for ( i = 0; ; i = (unsigned int)(v54 + 1) )
      {
        v28 = *(_QWORD *)(a1 + 8);
        LODWORD(v54) = i;
        v29 = *(_QWORD *)(v28 + 8);
        if ( (unsigned int)i >= *(_DWORD *)(v29 + v13) )
          break;
        v30 = (unsigned int)i;
        v31 = 32 * i + *(_QWORD *)(v29 + v13 + 8);
        if ( *(_DWORD *)(v31 + 24) != 1 || (v32 = *(_QWORD *)(v31 + 16)) == 0 )
        {
          v16 = -2146893805;
          v24 = 767;
          v25 = 2148073491LL;
          goto LABEL_13;
        }
        v63 = &v80[v30];
        v23 = NCryptProtectKey(v32, v31, v26, 32, a5, v64, (__int64)v63, a8);
        v16 = v23;
        if ( v23 )
        {
          v24 = 783;
          goto LABEL_12;
        }
        v26 = (_DWORD)v59 + 32;
        v59 += 32;
        v33 = (_OWORD *)*v63;
        v34 = v68 + 1;
        v35 = 10LL * v68;
        v81[v35] = *(_OWORD *)*v63;
        v81[v35 + 1] = v33[1];
        v81[v35 + 2] = v33[2];
        v81[v35 + 3] = v33[3];
        v81[v35 + 4] = v33[4];
        v81[v35 + 5] = v33[5];
        v81[v35 + 6] = v33[6];
        v81[v35 + 7] = v33[7];
        v81[v35 + 8] = v33[8];
        v36 = v33[9];
        v68 = v34;
        v81[v35 + 9] = v36;
      }
      v37 = *(unsigned int *)(v19 + 60);
      p_pbOutput = 0;
      LODWORD(pbOutput) = v37;
      v39 = (unsigned int)v37;
      if ( !(_DWORD)v37
        || v37 > g_ulMaxStackAllocSize
        || v37 + g_ulAdditionalProbeSize + 8 < v37
        || !(unsigned int)VerifyStackAvailable() )
      {
        goto LABEL_66;
      }
      v40 = v39 + 23;
      if ( v39 + 23 <= v39 + 8 )
        v40 = 0xFFFFFFFFFFFFFF0LL;
      v41 = v40 & 0xFFFFFFFFFFFFFFF0uLL;
      v42 = alloca(v41);
      v43 = alloca(v41);
      p_pbOutput = &pbOutput;
      if ( &v51 == (__int64 *)-64LL || (LODWORD(pbOutput) = 1801679955, (p_pbOutput = (size_t *)&v54) == 0) )
      {
LABEL_66:
        if ( v39 + 8 >= v39 )
        {
          v44 = (size_t *)((__int64 (*)(void))g_pfnAllocate)();
          p_pbOutput = v44;
          if ( v44 )
          {
            *(_DWORD *)v44 = 1885431112;
            p_pbOutput = v44 + 1;
          }
        }
      }
      if ( !p_pbOutput )
      {
        v16 = -2146893810;
        v24 = 799;
        v25 = 2148073486LL;
LABEL_13:
        DebugTraceError(
          v25,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
          v24);
LABEL_48:
        v48 = v20;
        v49 = v22;
        do
        {
          *v49++ = 0;
          --v48;
        }
        while ( v48 );
        (*(void (__fastcall **)(UCHAR *))(a5 + 16))(v22);
        goto LABEL_56;
      }
      v45 = *(_QWORD *)(v19 + 8);
      LODWORD(Size) = pbOutput;
      v46 = CNG_ComputeHash(v22, v20, v45, p_pbOutput, Size, (ULONG *)&pbOutput);
      v16 = v46;
      if ( v46 )
      {
        v47 = 813;
      }
      else
      {
        v46 = CNG_AesKeyWrap(a5, v65, v56, p_pbOutput, pbOutput, &v60, &v55);
        v16 = v46;
        if ( v46 >= 0 )
        {
          v73 = &qword_180023BB8;
          v75 = v60;
          v74 = v55;
          v72 = 11;
          v46 = RtlAsn1EncodeAndAllocate(ASN1_NCRYPT_MODULE_HANDLE, 29, 0, a5, &v58, &v61, v67);
          v16 = v46;
          if ( v46 )
          {
            v47 = 862;
          }
          else
          {
            v77 = &qword_180023328;
            v79 = v58;
            v78 = v61;
            v76[0] = 5;
            v76[2] = 12;
            v46 = RtlAsn1EncodeAndAllocate(ASN1_NCRYPT_MODULE_HANDLE, 22, 0, a5, &v57, &v62, v76);
            v16 = v46;
            if ( v46 )
            {
              v47 = 887;
            }
            else
            {
              v46 = RtlAsn1DecodeAndAllocate(ASN1_NCRYPT_MODULE_HANDLE, 22, 0x200000, v57, v62, 0, a5, v66);
              v16 = v46;
              if ( !v46 )
                goto LABEL_46;
              v47 = 903;
            }
          }
        }
        else
        {
          v47 = 832;
        }
      }
      DebugTraceError(
        (unsigned int)v46,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
        v47);
LABEL_46:
      if ( *((_DWORD *)p_pbOutput - 2) == 1885431112 )
        ((void (*)(void))g_pfnFree)();
      goto LABEL_48;
    }
  }
  v16 = -2146893785;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      v11,
      (unsigned int)"Status",
      39,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
      184);
LABEL_56:
  while ( v68 )
    (*(void (__fastcall **)(_QWORD))(a5 + 16))(v80[--v68]);
  v68 = -1;
  if ( v75 )
    (*(void (**)(void))(a5 + 16))();
  if ( v57 )
    (*(void (**)(void))(a5 + 16))();
  if ( v58 )
    (*(void (**)(void))(a5 + 16))();
  return v16;
}

```

## disassembly

```asm
0x180001550  push    rbp
0x180001552  push    rbx
0x180001553  push    rsi
0x180001554  push    rdi
0x180001555  push    r12
0x180001557  push    r13
0x180001559  push    r14
0x18000155b  push    r15
0x18000155d  sub     rsp, 718h
0x180001564  lea     rbp, [rsp+40h]
0x180001569  mov     rax, cs:__security_cookie
0x180001570  xor     rax, rbp
0x180001573  mov     [rbp+710h+var_50], rax
0x18000157a  mov     rax, [rbp+710h+arg_28]
0x180001581  mov     r12, rcx
0x180001584  mov     rdi, [rbp+710h+arg_30]
0x18000158b  lea     rcx, [rbp+710h+var_630]; void *
0x180001592  mov     rsi, [rbp+710h+arg_20]
0x180001599  mov     [rbp+710h+var_6B8], r8
0x18000159d  mov     r8d, 0A0h; Size
0x1800015a3  mov     ebx, edx
0x1800015a5  xor     edx, edx; Val
0x1800015a7  mov     [rbp+710h+var_6C0], rax
0x1800015ab  mov     [rbp+710h+var_6B0], rdi
0x1800015af  mov     [rbp+710h+var_6FC], r9d
0x1800015b3  call    memset_0
0x1800015b8  xor     edx, edx; Val
0x1800015ba  lea     rcx, [rbp+710h+var_6A0]; void *
0x1800015be  lea     r8d, [rdx+70h]; Size
0x1800015c2  call    memset_0
0x1800015c7  xor     edx, edx; Val
0x1800015c9  lea     rcx, [rbp+710h+var_550]; void *
0x1800015d0  mov     r8d, 500h; Size
0x1800015d6  call    memset_0
0x1800015db  xor     edx, edx; Val
0x1800015dd  lea     rcx, [rbp+710h+var_590]; void *
0x1800015e4  lea     r8d, [rdx+40h]; Size
0x1800015e8  call    memset_0
0x1800015ed  mov     qword ptr [rdi], 0
0x1800015f4  mov     rax, [r12+8]
0x1800015f9  mov     dword ptr [rbp+710h+var_710], 0
0x180001600  mov     [rbp+710h+var_6F0], 0
0x180001608  mov     [rbp+710h+var_6D8], 0
0x180001610  mov     [rbp+710h+var_6F8], 0
0x180001618  mov     [rbp+710h+var_6D0], 0
0x180001620  mov     [rbp+710h+var_708], 0
0x180001628  mov     [rbp+710h+var_6E0], 0
0x180001630  mov     [rbp+710h+var_700], 0
0x180001637  cmp     ebx, [rax]
0x180001639  jnb     loc_180001B32
0x18000163f  lfence
0x180001642  mov     rax, [r12+8]
0x180001647  mov     edi, ebx
0x180001649  shl     rdi, 5
0x18000164d  mov     rcx, [rax+8]
0x180001651  cmp     dword ptr [rdi+rcx], 8
0x180001655  ja      loc_180001B32
0x18000165b  lea     r8, [rbp+710h+var_708]
0x18000165f  call    CNG_FindBCryptOidInfoStr
0x180001664  mov     ebx, eax
0x180001666  test    eax, eax
0x180001668  jz      short loc_18000168A
0x18000166a  mov     r9d, 2C7h
0x180001670  mov     ecx, eax
0x180001672  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001679  lea     rdx, aStatus; "Status"
0x180001680  call    DebugTraceError
0x180001685  jmp     loc_180001B7C
0x18000168a  mov     r13, [rbp+710h+var_708]
0x18000168e  mov     rax, [r13+30h]
0x180001692  mov     [rbp+710h+var_688], rax
0x180001699  mov     eax, [r13+28h]
0x18000169d  mov     [rbp+710h+var_690], eax
0x1800016a3  mov     rax, [r12+8]
0x1800016a8  mov     rcx, [rax+8]
0x1800016ac  mov     r14d, [rdi+rcx]
0x1800016b0  shl     r14d, 5
0x1800016b4  cmp     r14d, 20h ; ' '
0x1800016b8  jnb     short loc_1800016CC
0x1800016ba  mov     ebx, 80070216h
0x1800016bf  mov     r9d, 2D8h
0x1800016c5  mov     ecx, 80070216h
0x1800016ca  jmp     short loc_180001672
0x1800016cc  mov     rax, [rsi+8]
0x1800016d0  mov     ecx, r14d
0x1800016d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016d8  mov     r15, rax
0x1800016db  test    rax, rax
0x1800016de  jnz     short loc_1800016F2
0x1800016e0  mov     ebx, 8009000Eh
0x1800016e5  mov     r9d, 2E0h
0x1800016eb  mov     ecx, 8009000Eh
0x1800016f0  jmp     short loc_180001672
0x1800016f2  mov     r9d, 2; dwFlags
0x1800016f8  mov     r8d, r14d; cbBuffer
0x1800016fb  mov     rdx, r15; pbBuffer
0x1800016fe  xor     ecx, ecx; hAlgorithm
0x180001700  call    cs:__imp_BCryptGenRandom
0x180001706  mov     ebx, eax
0x180001708  test    eax, eax
0x18000170a  jz      short loc_18000172C
0x18000170c  mov     r9d, 2ECh
0x180001712  mov     ecx, eax
0x180001714  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000171b  lea     rdx, aStatus; "Status"
0x180001722  call    DebugTraceError
0x180001727  jmp     loc_180001B0D
0x18000172c  lea     rax, [rbp+710h+var_550]
0x180001733  mov     [rbp+710h+var_6E8], r15
0x180001737  mov     [rbp+710h+var_698], rax
0x18000173b  mov     r10, r15
0x18000173e  xor     ecx, ecx
0x180001740  mov     rax, [r12+8]
0x180001745  mov     dword ptr [rbp+710h+var_708], ecx
0x180001748  mov     rax, [rax+8]
0x18000174c  cmp     ecx, [rax+rdi]
0x18000174f  jnb     loc_18000188E
0x180001755  mov     rdx, [rax+rdi+8]
0x18000175a  mov     r8d, ecx
0x18000175d  shl     rcx, 5
0x180001761  add     rdx, rcx
0x180001764  cmp     dword ptr [rdx+18h], 1
0x180001768  jnz     loc_180001879
0x18000176e  mov     rcx, [rdx+10h]
0x180001772  test    rcx, rcx
0x180001775  jz      loc_180001879
0x18000177b  lea     rax, [rbp+710h+var_590]
0x180001782  mov     r9d, 20h ; ' '
0x180001788  lea     rax, [rax+r8*8]
0x18000178c  mov     r8d, [rbp+710h+arg_38]
0x180001793  mov     dword ptr [rsp+750h+var_718], r8d
0x180001798  mov     r8, r10
0x18000179b  mov     [rsp+750h+var_720], rax
0x1800017a0  mov     [rbp+710h+var_6C8], rax
0x1800017a4  mov     rax, [rbp+710h+var_6C0]
0x1800017a8  mov     [rsp+750h+pbOutput], rax
0x1800017ad  mov     [rsp+750h+Size], rsi
0x1800017b2  call    NCryptProtectKey
0x1800017b7  mov     ebx, eax
0x1800017b9  test    eax, eax
0x1800017bb  jnz     loc_18000186E
0x1800017c1  mov     r8d, [rbp+710h+var_69C]
0x1800017c5  mov     rdx, [rbp+710h+var_6C8]
0x1800017c9  mov     r10, [rbp+710h+var_6E8]
0x1800017cd  add     r10, 20h ; ' '
0x1800017d1  lea     rcx, [r8+r8*4]
0x1800017d5  mov     [rbp+710h+var_6E8], r10
0x1800017d9  mov     rdx, [rdx]
0x1800017dc  inc     r8d
0x1800017df  shl     rcx, 5
0x1800017e3  movups  xmm0, xmmword ptr [rdx]
0x1800017e6  movups  [rbp+rcx+710h+var_550], xmm0
0x1800017ee  movups  xmm1, xmmword ptr [rdx+10h]
0x1800017f2  movups  [rbp+rcx+710h+var_540], xmm1
0x1800017fa  movups  xmm0, xmmword ptr [rdx+20h]
0x1800017fe  movups  [rbp+rcx+710h+var_530], xmm0
0x180001806  movups  xmm1, xmmword ptr [rdx+30h]
0x18000180a  movups  [rbp+rcx+710h+var_520], xmm1
0x180001812  movups  xmm0, xmmword ptr [rdx+40h]
0x180001816  movups  [rbp+rcx+710h+var_510], xmm0
0x18000181e  movups  xmm1, xmmword ptr [rdx+50h]
0x180001822  movups  [rbp+rcx+710h+var_500], xmm1
0x18000182a  movups  xmm0, xmmword ptr [rdx+60h]
0x18000182e  movups  [rbp+rcx+710h+var_4F0], xmm0
0x180001836  movups  xmm1, xmmword ptr [rdx+70h]
0x18000183a  movups  [rbp+rcx+710h+var_4E0], xmm1
0x180001842  movups  xmm0, xmmword ptr [rdx+80h]
0x180001849  movups  [rbp+rcx+710h+var_4D0], xmm0
0x180001851  movups  xmm1, xmmword ptr [rdx+90h]
0x180001858  mov     [rbp+710h+var_69C], r8d
0x18000185c  movups  [rbp+rcx+710h+var_4C0], xmm1
0x180001864  mov     ecx, dword ptr [rbp+710h+var_708]
0x180001867  inc     ecx
0x180001869  jmp     loc_180001740
0x18000186e  mov     r9d, 30Fh
0x180001874  jmp     loc_180001712
0x180001879  mov     ebx, 80090013h
0x18000187e  mov     r9d, 2FFh
0x180001884  mov     ecx, 80090013h
0x180001889  jmp     loc_180001714
0x18000188e  mov     eax, [r13+3Ch]
0x180001892  xor     edi, edi
0x180001894  mov     dword ptr [rbp+710h+var_710], eax
0x180001897  mov     ebx, eax
0x180001899  test    eax, eax
0x18000189b  jz      short loc_1800018FE
0x18000189d  cmp     rax, cs:g_ulMaxStackAllocSize
0x1800018a4  ja      short loc_1800018FE
0x1800018a6  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800018ad  add     rcx, 8
0x1800018b1  add     rcx, rax
0x1800018b4  cmp     rcx, rax
0x1800018b7  jb      short loc_1800018FE
0x1800018b9  call    VerifyStackAvailable
0x1800018be  test    eax, eax
0x1800018c0  jz      short loc_1800018FE
0x1800018c2  lea     rax, [rbx+8]
0x1800018c6  lea     rcx, [rax+0Fh]
0x1800018ca  cmp     rcx, rax
0x1800018cd  ja      short loc_1800018D9
0x1800018cf  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800018d9  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800018dd  mov     rax, rcx
0x1800018e0  call    __chkstk_0
0x1800018e5  sub     rsp, rcx
0x1800018e8  lea     rdi, [rsp+750h+var_710]
0x1800018ed  test    rdi, rdi
0x1800018f0  jz      short loc_1800018FE
0x1800018f2  mov     dword ptr [rdi], 6B637453h
0x1800018f8  add     rdi, 8
0x1800018fc  jnz     short loc_180001925
0x1800018fe  lea     rcx, [rbx+8]
0x180001902  cmp     rcx, rbx
0x180001905  jb      short loc_180001925
0x180001907  mov     rax, cs:g_pfnAllocate
0x18000190e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001913  mov     rdi, rax
0x180001916  test    rax, rax
0x180001919  jz      short loc_180001925
0x18000191b  mov     dword ptr [rax], 70616548h
0x180001921  add     rdi, 8
0x180001925  test    rdi, rdi
0x180001928  jnz     short loc_18000193F
0x18000192a  mov     ebx, 8009000Eh
0x18000192f  mov     r9d, 31Fh
0x180001935  mov     ecx, 8009000Eh
0x18000193a  jmp     loc_180001714
0x18000193f  mov     r8, [r13+8]
0x180001943  lea     rax, [rbp+710h+var_710]
0x180001947  mov     [rsp+750h+pbOutput], rax; pbOutput
0x18000194c  mov     r9, rdi
0x18000194f  mov     eax, dword ptr [rbp+710h+var_710]
0x180001952  mov     edx, r14d; cbInput
0x180001955  mov     rcx, r15; pbInput
0x180001958  mov     dword ptr [rsp+750h+Size], eax; Size
0x18000195c  call    CNG_ComputeHash
0x180001961  mov     ebx, eax
0x180001963  test    eax, eax
0x180001965  jz      short loc_180001972
0x180001967  mov     r9d, 32Dh
0x18000196d  jmp     loc_180001AE0
0x180001972  mov     r8d, [rbp+710h+var_6FC]
0x180001976  lea     rax, [rbp+710h+var_700]
0x18000197a  mov     rdx, [rbp+710h+var_6B8]
0x18000197e  mov     r9, rdi
0x180001981  mov     [rsp+750h+var_720], rax
0x180001986  mov     rcx, rsi
0x180001989  lea     rax, [rbp+710h+var_6E0]
0x18000198d  mov     [rsp+750h+pbOutput], rax
0x180001992  mov     eax, dword ptr [rbp+710h+var_710]
0x180001995  mov     dword ptr [rsp+750h+Size], eax
0x180001999  call    CNG_AesKeyWrap
0x18000199e  mov     ebx, eax
0x1800019a0  test    eax, eax
0x1800019a2  jns     short loc_1800019AF
0x1800019a4  mov     r9d, 340h
0x1800019aa  jmp     loc_180001AE0
0x1800019af  mov     rcx, cs:ASN1_NCRYPT_MODULE_HANDLE
0x1800019b6  lea     rax, qword_180023BB8
0x1800019bd  mov     [rbp+710h+var_660], rax
0x1800019c4  xor     r8d, r8d
0x1800019c7  mov     rax, [rbp+710h+var_6E0]
0x1800019cb  mov     r9, rsi
0x1800019ce  mov     [rbp+710h+var_638], rax
0x1800019d5  mov     eax, [rbp+710h+var_700]
0x1800019d8  mov     [rbp+710h+var_640], eax
0x1800019de  lea     edx, [r8+1Dh]
0x1800019e2  lea     rax, [rbp+710h+var_6A0]
0x1800019e6  mov     [rbp+710h+var_668], 0Bh
0x1800019f0  mov     [rsp+750h+var_720], rax
0x1800019f5  lea     rax, [rbp+710h+var_6D8]
0x1800019f9  mov     [rsp+750h+pbOutput], rax
0x1800019fe  lea     rax, [rbp+710h+var_6F0]
0x180001a02  mov     [rsp+750h+Size], rax
0x180001a07  call    cs:__imp_RtlAsn1EncodeAndAllocate
0x180001a0d  mov     ebx, eax
0x180001a0f  test    eax, eax
0x180001a11  jz      short loc_180001A1E
0x180001a13  mov     r9d, 35Eh
0x180001a19  jmp     loc_180001AE0
0x180001a1e  mov     rcx, cs:ASN1_NCRYPT_MODULE_HANDLE
0x180001a25  lea     rax, qword_180023328
0x180001a2c  mov     [rbp+710h+var_620], rax
0x180001a33  xor     r8d, r8d
0x180001a36  mov     rax, [rbp+710h+var_6F0]
0x180001a3a  mov     r9, rsi
0x180001a3d  mov     [rbp+710h+var_610], rax
0x180001a44  mov     eax, dword ptr [rbp+710h+var_6D8]
0x180001a47  mov     [rbp+710h+var_618], eax
0x180001a4d  lea     r12d, [r8+16h]
0x180001a51  lea     rax, [rbp+710h+var_630]
0x180001a58  mov     [rbp+710h+var_630], 5
0x180001a62  mov     [rsp+750h+var_720], rax
0x180001a67  mov     edx, r12d
0x180001a6a  lea     rax, [rbp+710h+var_6D0]
0x180001a6e  mov     [rbp+710h+var_628], 0Ch
0x180001a78  mov     [rsp+750h+pbOutput], rax
0x180001a7d  lea     rax, [rbp+710h+var_6F8]
0x180001a81  mov     [rsp+750h+Size], rax
0x180001a86  call    cs:__imp_RtlAsn1EncodeAndAllocate
  ... truncated ...
```

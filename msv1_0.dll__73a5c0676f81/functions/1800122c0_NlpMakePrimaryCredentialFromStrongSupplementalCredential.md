# NlpMakePrimaryCredentialFromStrongSupplementalCredential

- ea: `0x1800122c0`
- end: `0x180012756`
- name: `NlpMakePrimaryCredentialFromStrongSupplementalCredential`
- size: `1174`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, PCUNICODE_STRING, __int64, _QWORD *, int *)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18000d1b0`
- `0x1800193e0`

## callees

- `0x180010b14`
- `0x1800122c0`
- `0x18002ee7c`
- `0x18002fb50`
- `0x180030844`
- `0x180040c04`
- `0x180055548`
- `0x1800555f8`
- `0x18006bcf0`
- `0x18006bd74`
- `0x18006d010`

## import_xrefs

- `NtlmShared!MsvpValidateSupplementalCreds` at `0x1800122fa`
- `NtlmShared!MsvpValidateSupplementalCreds` at `0x1800122fa`
- `ntdll!RtlCopyUnicodeString` at `0x1800123d5`
- `ntdll!RtlCopyUnicodeString` at `0x18001241c`
- `ntdll!RtlCopyUnicodeString` at `0x1800123d5`
- `ntdll!RtlCopyUnicodeString` at `0x18001241c`
- `ntdll!RtlInitUnicodeString` at `0x1800123f6`
- `ntdll!RtlInitUnicodeString` at `0x180012430`
- `ntdll!RtlInitUnicodeString` at `0x1800123f6`
- `ntdll!RtlInitUnicodeString` at `0x180012430`

## pseudocode

```c
__int64 __fastcall NlpMakePrimaryCredentialFromStrongSupplementalCredential(
        PCUNICODE_STRING SourceString,
        PCUNICODE_STRING a2,
        __int64 a3,
        _QWORD *a4,
        int *a5)
{
  int v9; // edi
  int v10; // r10d
  int v11; // r9d
  int v12; // esi
  __int64 v13; // r9
  unsigned int v14; // esi
  __int64 v15; // rdx
  __int64 v16; // r8
  char *v17; // rax
  char *v18; // rbx
  _QWORD *v20; // r14
  char *v21; // rsi
  __int64 Length; // rcx
  struct _UNICODE_STRING *v23; // rcx
  int v24; // edx
  __int64 v25; // rax
  int v26; // r8d
  __int64 v27; // rax
  int v28; // ecx
  int v29; // edx
  __int128 v30; // xmm1
  __int64 v31; // rax
  __m128i v32; // xmm1
  int v33; // edx
  __int128 v34; // xmm0
  __m128i v35; // xmm2
  __int128 v36; // xmm3
  __int64 v37; // rcx
  __int128 v38; // xmm0
  __int128 v39; // xmm0
  unsigned __int64 v40; // rsi
  int *v41; // rdi
  __int64 v42; // rcx
  unsigned __int64 v43; // rcx
  void *v44; // rsp
  void *v45; // rsp
  _DWORD *v46; // rax
  int v47; // esi
  __int64 v48; // rax
  int v49; // ecx
  __int128 v50; // xmm0
  __int64 v51; // rcx
  _DWORD v52[10]; // [rsp+0h] [rbp-40h] BYREF
  int v53; // [rsp+40h] [rbp+0h] BYREF
  _QWORD v54[3]; // [rsp+48h] [rbp+8h] BYREF
  _BYTE v55[48]; // [rsp+60h] [rbp+20h]

  v54[0] = a4;
  v9 = MsvpValidateSupplementalCreds(a3);
  v10 = SourceString->Length + 388 + a2->Length;
  *a4 = 0;
  v11 = v10 & 7;
  v12 = 8 - v11;
  *a5 = 0;
  v13 = (unsigned int)-v11;
  v14 = v10 + ((_DWORD)v13 != 0 ? v12 : 0);
  v53 = v14;
  v17 = (char *)((__int64 (__fastcall *)(_QWORD, __int64, __int64, __int64))qword_180088238)(v14, v15, v16, v13);
  v18 = v17;
  if ( !v17 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_392ea864dd3e33f07e463c681f7a5069_Traceguids, v14);
    return 3221225540LL;
  }
  memset_0(v17, 0, v14);
  v20 = v18 + 32;
  *((_QWORD *)v18 + 4) = LocalhostNtLmCredIsoObj::IsoObj;
  v21 = v18 + 384;
  if ( SourceString->Length )
  {
    *((_QWORD *)v18 + 1) = v21;
    *((_WORD *)v18 + 1) = SourceString->Length + 2;
    RtlCopyUnicodeString((PUNICODE_STRING)v18, SourceString);
    Length = SourceString->Length;
    *(_WORD *)&v21[Length] = 0;
    v21 = &v18[Length + 386];
  }
  else
  {
    RtlInitUnicodeString((PUNICODE_STRING)v18, 0);
  }
  v23 = (struct _UNICODE_STRING *)(v18 + 16);
  if ( a2->Length )
  {
    *((_QWORD *)v18 + 3) = v21;
    *((_WORD *)v18 + 9) = a2->Length + 2;
    RtlCopyUnicodeString(v23, a2);
    *(_WORD *)&v21[a2->Length] = 0;
  }
  else
  {
    RtlInitUnicodeString(v23, 0);
  }
  if ( !v9 )
  {
    v25 = *(_QWORD *)(a3 + 24);
    if ( (*(_BYTE *)(v25 + 4) & 2) != 0 )
    {
      *(_OWORD *)(v18 + 70) = *(_OWORD *)(v25 + 24);
      v18[41] = 1;
    }
    goto LABEL_49;
  }
  v26 = 2;
  switch ( v9 )
  {
    case 2:
      v27 = *(_QWORD *)(a3 + 24);
      v28 = *(_DWORD *)(v27 + 4);
      v29 = *(_DWORD *)(v27 + 40);
      v30 = *(_OWORD *)(v27 + 24);
      if ( (v28 & 2) != 0 )
      {
        *(_OWORD *)(v18 + 70) = *(_OWORD *)(v27 + 8);
        v18[41] = 1;
      }
      if ( (v28 & 8) != 0 )
      {
        *(_OWORD *)(v18 + 50) = v30;
        *(_DWORD *)(v18 + 66) = v29;
        v18[43] = 1;
        *((_DWORD *)v18 + 11) = 4;
      }
      goto LABEL_49;
    case 4:
      v31 = *(_QWORD *)(a3 + 24);
      v32 = *(__m128i *)v31;
      v33 = *(_DWORD *)(v31 + 64);
      v34 = *(_OWORD *)(v31 + 16);
      v35 = *(__m128i *)(v31 + 32);
      v36 = *(_OWORD *)(v31 + 48);
      *(_OWORD *)v55 = *(_OWORD *)v31;
      v37 = HIDWORD(*(_QWORD *)v55);
      *(_OWORD *)&v55[16] = v34;
      *(__m128i *)&v55[32] = v35;
      if ( (v55[4] & 2) != 0 )
      {
        v38 = *(_OWORD *)&v55[12];
        v18[41] = 1;
        *(_OWORD *)(v18 + 70) = v38;
      }
      if ( (v37 & 8) != 0 )
      {
        v39 = *(_OWORD *)&v55[28];
        v18[43] = 1;
        *(_OWORD *)(v18 + 50) = v39;
        *(_DWORD *)(v18 + 66) = _mm_cvtsi128_si32(_mm_srli_si128(v35, 12));
        *((_DWORD *)v18 + 11) = _mm_cvtsi128_si32(_mm_srli_si128(v32, 8));
      }
      if ( (v37 & 0x10) == 0 )
        goto LABEL_49;
      *(_OWORD *)(v18 + 102) = v36;
      goto LABEL_48;
    case -65535:
      v40 = *(unsigned int *)(a3 + 16);
      v41 = 0;
      if ( !*(_DWORD *)(a3 + 16)
        || v40 > g_ulMaxStackAllocSize
        || v40 + g_ulAdditionalProbeSize + 8 < v40
        || !(unsigned int)VerifyStackAvailable() )
      {
        goto LABEL_36;
      }
      v42 = v40 + 23;
      if ( v40 + 23 <= v40 + 8 )
        v42 = 0xFFFFFFFFFFFFFF0LL;
      v43 = v42 & 0xFFFFFFFFFFFFFFF0uLL;
      v44 = alloca(v43);
      v45 = alloca(v43);
      v41 = &v53;
      if ( v52 == (_DWORD *)-64LL || (v53 = 1801679955, (v41 = (int *)v54) == 0) )
      {
LABEL_36:
        if ( v40 + 8 >= v40 )
        {
          v46 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
          if ( !v46 )
          {
LABEL_40:
            v47 = -1073741801;
LABEL_57:
            ((void (__fastcall *)(char *))qword_180088240)(v18);
            v18 = 0;
            goto LABEL_58;
          }
          *v46 = 1885431112;
          v41 = v46 + 2;
        }
        if ( !v41 )
          goto LABEL_40;
      }
      memcpy_0(v41, *(const void **)(a3 + 24), *(unsigned int *)(a3 + 16));
      v47 = (*(__int64 (__fastcall **)(_QWORD, int *, char *))(*(_QWORD *)*v20 + 136LL))(*v20, v41, v18 + 32);
      if ( *(v41 - 2) == 1885431112 )
        ((void (*)(void))g_pfnFree)();
LABEL_50:
      if ( v47 >= 0 )
        goto LABEL_58;
      goto LABEL_57;
    case -2:
      v48 = *(_QWORD *)(a3 + 24);
      v49 = *(_DWORD *)(v48 + 8);
      v33 = *(_DWORD *)(v48 + 60);
      v50 = *(_OWORD *)(v48 + 44);
      if ( (*(_BYTE *)(v48 + 4) & 2) != 0 )
      {
        *(_OWORD *)(v18 + 70) = *(_OWORD *)(v48 + 28);
        v18[41] = 1;
      }
      if ( (v49 & 0x10) == 0 )
        goto LABEL_49;
      *(_OWORD *)(v18 + 102) = v50;
LABEL_48:
      *(_DWORD *)(v18 + 118) = v33;
      v18[42] = 1;
LABEL_49:
      v47 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v20 + 24LL))(*v20, v18 + 32);
      goto LABEL_50;
  }
  v47 = 0;
  if ( a3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v51 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v52[8] = v9;
      WPP_SF_sd(v51);
    }
    v47 = -1073741811;
    goto LABEL_57;
  }
LABEL_58:
  *(_QWORD *)v54[0] = v18;
  *a5 = v53;
  if ( v47 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v24,
        v26,
        (unsigned int)"NlpMakePrimaryCredentialFromStrongSupplementalCredential",
        112,
        (__int64)"NtlmFailure",
        v47);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_sds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      v26,
      (unsigned int)"NlpMakePrimaryCredentialFromStrongSupplementalCredential",
      112,
      (__int64)"NtlmSuccess");
  }
  return (unsigned int)v47;
}

```

## disassembly

```asm
0x1800122c0  push    rbp
0x1800122c2  push    rbx
0x1800122c3  push    rsi
0x1800122c4  push    rdi
0x1800122c5  push    r12
0x1800122c7  push    r13
0x1800122c9  push    r14
0x1800122cb  push    r15
0x1800122cd  sub     rsp, 0C8h
0x1800122d4  lea     rbp, [rsp+40h]
0x1800122d9  mov     rax, cs:__security_cookie
0x1800122e0  xor     rax, rbp
0x1800122e3  mov     [rbp+0C0h+var_50], rax
0x1800122e7  mov     rbx, r9
0x1800122ea  mov     r12, rcx
0x1800122ed  mov     rcx, r8
0x1800122f0  mov     [rbp+0C0h+var_B8], rbx
0x1800122f4  mov     r13, r8
0x1800122f7  mov     r15, rdx
0x1800122fa  call    cs:__imp_MsvpValidateSupplementalCreds
0x180012300  movzx   r11d, word ptr [r12]
0x180012305  xor     r14d, r14d
0x180012308  movzx   r10d, word ptr [r15]
0x18001230c  mov     edi, eax
0x18001230e  mov     rax, [rbp+0C0h+arg_20]
0x180012315  add     r11d, 184h
0x18001231c  add     r10d, r11d
0x18001231f  mov     [rbx], r14
0x180012322  mov     r9d, r10d
0x180012325  lea     esi, [r14+8]
0x180012329  and     r9d, 7
0x18001232d  sub     esi, r9d
0x180012330  mov     [rax], r14d
0x180012333  neg     r9d
0x180012336  sbb     eax, eax
0x180012338  and     esi, eax
0x18001233a  mov     rax, cs:qword_180088238
0x180012341  add     esi, r10d
0x180012344  mov     ecx, esi
0x180012346  mov     [rbp+0C0h+var_C0], esi
0x180012349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001234e  mov     rbx, rax
0x180012351  test    rax, rax
0x180012354  jnz     short loc_18001238F
0x180012356  mov     rcx, cs:WPP_GLOBAL_Control
0x18001235d  lea     r15, WPP_GLOBAL_Control
0x180012364  cmp     rcx, r15
0x180012367  jz      short loc_180012385
0x180012369  test    byte ptr [rcx+1Ch], 1
0x18001236d  jz      short loc_180012385
0x18001236f  mov     rcx, [rcx+10h]
0x180012373  lea     edx, [rax+12h]
0x180012376  mov     r9d, esi
0x180012379  lea     r8, WPP_392ea864dd3e33f07e463c681f7a5069_Traceguids
0x180012380  call    WPP_SF_d
0x180012385  mov     eax, 0C0000044h
0x18001238a  jmp     loc_180012736
0x18001238f  mov     r8d, esi; Size
0x180012392  xor     edx, edx; Val
0x180012394  mov     rcx, rbx; void *
0x180012397  call    memset_0
0x18001239c  mov     rax, cs:?IsoObj@LocalhostNtLmCredIsoObj@@0PEAVNtlmCredIsoApi@@EA; NtlmCredIsoApi * LocalhostNtLmCredIsoObj::IsoObj
0x1800123a3  lea     r14, [rbx+20h]
0x1800123a7  mov     [r14], rax
0x1800123aa  lea     rsi, [rbx+180h]
0x1800123b1  xor     eax, eax
0x1800123b3  mov     ecx, 2
0x1800123b8  cmp     [r12], ax
0x1800123bd  jbe     short loc_1800123F1
0x1800123bf  mov     [rbx+8], rsi
0x1800123c3  mov     rdx, r12; SourceString
0x1800123c6  movzx   eax, word ptr [r12]
0x1800123cb  add     ax, cx
0x1800123ce  mov     rcx, rbx; DestinationString
0x1800123d1  mov     [rbx+2], ax
0x1800123d5  call    cs:__imp_RtlCopyUnicodeString
0x1800123db  movzx   ecx, word ptr [r12]
0x1800123e0  xor     r12d, r12d
0x1800123e3  mov     [rcx+rsi], r12w
0x1800123e8  add     rsi, 2
0x1800123ec  add     rsi, rcx
0x1800123ef  jmp     short loc_1800123FF
0x1800123f1  xor     edx, edx; SourceString
0x1800123f3  mov     rcx, rbx; DestinationString
0x1800123f6  call    cs:__imp_RtlInitUnicodeString
0x1800123fc  xor     r12d, r12d
0x1800123ff  lea     rcx, [rbx+10h]; DestinationString
0x180012403  cmp     [r15], r12w
0x180012407  jbe     short loc_18001242E
0x180012409  mov     [rcx+8], rsi
0x18001240d  mov     rdx, r15; SourceString
0x180012410  movzx   eax, word ptr [r15]
0x180012414  add     ax, 2
0x180012418  mov     [rcx+2], ax
0x18001241c  call    cs:__imp_RtlCopyUnicodeString
0x180012422  movzx   eax, word ptr [r15]
0x180012426  mov     word ptr [rax+rsi], 0
0x18001242c  jmp     short loc_180012436
0x18001242e  xor     edx, edx; SourceString
0x180012430  call    cs:__imp_RtlInitUnicodeString
0x180012436  lea     r15, WPP_GLOBAL_Control
0x18001243d  test    edi, edi
0x18001243f  jnz     short loc_180012461
0x180012441  mov     rax, [r13+18h]
0x180012445  test    byte ptr [rax+4], 2
0x180012449  movups  xmm1, xmmword ptr [rax+18h]
0x18001244d  jz      loc_18001264E
0x180012453  movdqu  xmmword ptr [rbx+46h], xmm1
0x180012458  mov     byte ptr [rbx+29h], 1
0x18001245c  jmp     loc_18001264E
0x180012461  mov     r8d, 2
0x180012467  cmp     edi, r8d
0x18001246a  jnz     short loc_1800124AC
0x18001246c  mov     rax, [r13+18h]
0x180012470  mov     ecx, [rax+4]
0x180012473  mov     edx, [rax+28h]
0x180012476  movups  xmm0, xmmword ptr [rax+8]
0x18001247a  movups  xmm1, xmmword ptr [rax+18h]
0x18001247e  test    r8b, cl
0x180012481  jz      short loc_18001248C
0x180012483  movdqu  xmmword ptr [rbx+46h], xmm0
0x180012488  mov     byte ptr [rbx+29h], 1
0x18001248c  test    cl, 8
0x18001248f  jz      loc_18001264E
0x180012495  movups  xmmword ptr [rbx+32h], xmm1
0x180012499  mov     [rbx+42h], edx
0x18001249c  mov     byte ptr [rbx+2Bh], 1
0x1800124a0  mov     dword ptr [rbx+2Ch], 4
0x1800124a7  jmp     loc_18001264E
0x1800124ac  cmp     edi, 4
0x1800124af  jnz     short loc_180012525
0x1800124b1  mov     rax, [r13+18h]
0x1800124b5  movups  xmm1, xmmword ptr [rax]
0x1800124b8  mov     edx, [rax+40h]
0x1800124bb  movups  xmm0, xmmword ptr [rax+10h]
0x1800124bf  movups  xmm2, xmmword ptr [rax+20h]
0x1800124c3  movups  xmm3, xmmword ptr [rax+30h]
0x1800124c7  movq    rcx, xmm1
0x1800124cc  movaps  [rbp+0C0h+var_A0], xmm1
0x1800124d0  shr     rcx, 20h
0x1800124d4  movaps  [rbp+0C0h+var_90], xmm0
0x1800124d8  movaps  [rbp+0C0h+var_80], xmm2
0x1800124dc  test    r8b, cl
0x1800124df  jz      short loc_1800124EE
0x1800124e1  movups  xmm0, [rbp+0C0h+var_A0+0Ch]
0x1800124e5  mov     byte ptr [rbx+29h], 1
0x1800124e9  movdqu  xmmword ptr [rbx+46h], xmm0
0x1800124ee  test    cl, 8
0x1800124f1  jz      short loc_180012513
0x1800124f3  movups  xmm0, [rbp+0C0h+var_90+0Ch]
0x1800124f7  mov     byte ptr [rbx+2Bh], 1
0x1800124fb  psrldq  xmm2, 0Ch
0x180012500  psrldq  xmm1, 8
0x180012505  movups  xmmword ptr [rbx+32h], xmm0
0x180012509  movd    dword ptr [rbx+42h], xmm2
0x18001250e  movd    dword ptr [rbx+2Ch], xmm1
0x180012513  test    cl, 10h
0x180012516  jz      loc_18001264E
0x18001251c  movups  xmmword ptr [rbx+66h], xmm3
0x180012520  jmp     loc_180012647
0x180012525  cmp     edi, 0FFFF0001h
0x18001252b  jnz     loc_180012618
0x180012531  mov     esi, [r13+10h]
0x180012535  mov     rdi, r12
0x180012538  test    rsi, rsi
0x18001253b  jz      short loc_18001259E
0x18001253d  cmp     rsi, cs:g_ulMaxStackAllocSize
0x180012544  ja      short loc_18001259E
0x180012546  mov     rcx, cs:g_ulAdditionalProbeSize
0x18001254d  add     rcx, 8
0x180012551  add     rcx, rsi
0x180012554  cmp     rcx, rsi
0x180012557  jb      short loc_18001259E
0x180012559  call    VerifyStackAvailable
0x18001255e  test    eax, eax
0x180012560  jz      short loc_18001259E
0x180012562  lea     rax, [rsi+8]
0x180012566  lea     rcx, [rax+0Fh]
0x18001256a  cmp     rcx, rax
0x18001256d  ja      short loc_180012579
0x18001256f  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180012579  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001257d  mov     rax, rcx
0x180012580  call    _alloca_probe
0x180012585  sub     rsp, rcx
0x180012588  lea     rdi, [rsp+100h+var_C0]
0x18001258d  test    rdi, rdi
0x180012590  jz      short loc_18001259E
0x180012592  mov     dword ptr [rdi], 6B637453h
0x180012598  add     rdi, 8
0x18001259c  jnz     short loc_1800125D4
0x18001259e  lea     rcx, [rsi+8]
0x1800125a2  cmp     rcx, rsi
0x1800125a5  jb      short loc_1800125C5
0x1800125a7  mov     rax, cs:g_pfnAllocate
0x1800125ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125b3  mov     rdi, rax
0x1800125b6  test    rax, rax
0x1800125b9  jz      short loc_1800125CA
0x1800125bb  mov     dword ptr [rax], 70616548h
0x1800125c1  add     rdi, 8
0x1800125c5  test    rdi, rdi
0x1800125c8  jnz     short loc_1800125D4
0x1800125ca  mov     esi, 0C0000017h
0x1800125cf  jmp     loc_180012694
0x1800125d4  mov     r8d, [r13+10h]; Size
0x1800125d8  mov     rcx, rdi; void *
0x1800125db  mov     rdx, [r13+18h]; Src
0x1800125df  call    memcpy_0
0x1800125e4  mov     rcx, [r14]
0x1800125e7  mov     r8, r14
0x1800125ea  mov     rdx, rdi
0x1800125ed  mov     rax, [rcx]
0x1800125f0  mov     rax, [rax+88h]
0x1800125f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125fc  lea     rcx, [rdi-8]
0x180012600  mov     esi, eax
0x180012602  cmp     dword ptr [rcx], 70616548h
0x180012608  jnz     short loc_180012662
0x18001260a  mov     rax, cs:g_pfnFree
0x180012611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012616  jmp     short loc_180012662
0x180012618  cmp     edi, 0FFFFFFFEh
0x18001261b  jnz     short loc_180012668
0x18001261d  mov     rax, [r13+18h]
0x180012621  mov     ecx, [rax+8]
0x180012624  movups  xmm1, xmmword ptr [rax+1Ch]
0x180012628  mov     edx, [rax+3Ch]
0x18001262b  movups  xmm0, xmmword ptr [rax+2Ch]
0x18001262f  test    [rax+4], r8b
0x180012633  jz      short loc_18001263E
0x180012635  movdqu  xmmword ptr [rbx+46h], xmm1
0x18001263a  mov     byte ptr [rbx+29h], 1
0x18001263e  test    cl, 10h
0x180012641  jz      short loc_18001264E
0x180012643  movups  xmmword ptr [rbx+66h], xmm0
0x180012647  mov     [rbx+76h], edx
0x18001264a  mov     byte ptr [rbx+2Ah], 1
0x18001264e  mov     rcx, [r14]
0x180012651  mov     rdx, r14
0x180012654  mov     rax, [rcx]
0x180012657  mov     rax, [rax+18h]
0x18001265b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012660  mov     esi, eax
0x180012662  test    esi, esi
0x180012664  js      short loc_180012694
0x180012666  jmp     short loc_1800126A6
0x180012668  mov     esi, r12d
0x18001266b  test    r13, r13
0x18001266e  jz      short loc_1800126A6
0x180012670  mov     rcx, cs:WPP_GLOBAL_Control
0x180012677  cmp     rcx, r15
0x18001267a  jz      short loc_18001268F
0x18001267c  test    [rcx+1Ch], r8b
0x180012680  jz      short loc_18001268F
0x180012682  mov     rcx, [rcx+10h]
0x180012686  mov     [rsp+100h+var_E0], edi
0x18001268a  call    WPP_SF_sd
0x18001268f  mov     esi, 0C000000Dh
0x180012694  mov     rax, cs:qword_180088240
0x18001269b  mov     rcx, rbx
0x18001269e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126a3  mov     rbx, r12
0x1800126a6  mov     rax, [rbp+0C0h+var_B8]
0x1800126aa  mov     rcx, [rbp+0C0h+arg_20]
0x1800126b1  mov     [rax], rbx
0x1800126b4  mov     eax, [rbp+0C0h+var_C0]
0x1800126b7  mov     [rcx], eax
0x1800126b9  test    esi, esi
0x1800126bb  js      short loc_1800126FA
0x1800126bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800126c4  cmp     rcx, r15
0x1800126c7  jz      short loc_180012734
0x1800126c9  test    byte ptr [rcx+1Ch], 8
0x1800126cd  jz      short loc_180012734
0x1800126cf  mov     rcx, [rcx+10h]
0x1800126d3  lea     rax, aNtlmsuccess; "NtlmSuccess"
0x1800126da  mov     [rsp+100h+var_D8], rax
0x1800126df  lea     r9, aNlpmakeprimary; "NlpMakePrimaryCredentialFromStrongSuppl"...
0x1800126e6  mov     edx, 0Eh
0x1800126eb  mov     [rsp+100h+var_E0], 870h
0x1800126f3  call    WPP_SF_sds
0x1800126f8  jmp     short loc_180012734
0x1800126fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180012701  cmp     rcx, r15
0x180012704  jz      short loc_180012734
0x180012706  test    byte ptr [rcx+1Ch], 1
0x18001270a  jz      short loc_180012734
0x18001270c  mov     rcx, [rcx+10h]
0x180012710  lea     rax, aNtlmfailure; "NtlmFailure"
0x180012717  mov     [rsp+100h+var_D0], esi
0x18001271b  lea     r9, aNlpmakeprimary; "NlpMakePrimaryCredentialFromStrongSuppl"...
0x180012722  mov     [rsp+100h+var_D8], rax
0x180012727  mov     [rsp+100h+var_E0], 870h
0x18001272f  call    WPP_SF_sdsD
0x180012734  mov     eax, esi
0x180012736  mov     rcx, [rbp+0C0h+var_50]
0x18001273a  xor     rcx, rbp; StackCookie
0x18001273d  call    __security_check_cookie
0x180012742  lea     rsp, [rbp+88h]
  ... truncated ...
```

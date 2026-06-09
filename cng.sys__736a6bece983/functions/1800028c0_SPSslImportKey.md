# SPSslImportKey

- ea: `0x1800028c0`
- end: `0x180002f84`
- name: `SPSslImportKey`
- size: `1732`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x1800023e0`
- `0x1800028c0`
- `0x180002f90`
- `0x180003c70`
- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x1800082b0`
- `0x180036040`
- `0x18005a4d0`
- `0x180082418`
- `0x180082598`
- `0x180082664`
- `0x18009f616`
- `0x18009f780`
- `0x18009fa80`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180002bb9`
- `ntoskrnl!ExAllocatePool2` at `0x180002bb9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180002de4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180002de4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180002df9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180002df9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a02cd`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a02cd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a02d9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a02d9`
- `ntoskrnl!SkIsSecureKernel` at `0x180002dc7`
- `ntoskrnl!SkIsSecureKernel` at `0x180002dc7`
- `ntoskrnl!SkAllocatePool` at `0x180002f3a`
- `ntoskrnl!SkAllocatePool` at `0x180002f3a`

## string_xrefs

- `0x180002962`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180002ab2`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180002d73`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180002e2c`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180002e78`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180002ef0`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800a0339`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800a03db`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800a0406`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslImportKey(_DWORD *a1, __int64 *a2, const wchar_t *a3, __int64 a4, unsigned int a5, int a6)
{
  __int64 *v7; // rax
  _DWORD *v8; // rsi
  unsigned int v9; // esi
  __m128i v10; // xmm2
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int64 v14; // r9
  unsigned int v15; // r15d
  __int64 i; // rcx
  __int64 v17; // r8
  __int64 j; // rax
  __int64 v19; // rbx
  __int32 v20; // edi
  unsigned int v21; // r13d
  __int64 v22; // r14
  __int64 v23; // rdx
  ULONG cbKeyObject; // r12d
  __int64 v25; // r15
  int v26; // r9d
  __int64 *v27; // r13
  __int64 *v28; // r13
  LPCWSTR *v29; // rcx
  __int64 v30; // rcx
  int v31; // esi
  ULONG v32; // r15d
  __int64 v33; // rdi
  __int64 v34; // r14
  int v35; // eax
  char *Pool; // rax
  char *v37; // rdi
  unsigned int v38; // eax
  int v39; // eax
  UCHAR *pbKeyObject; // r8
  int v41; // ecx
  const WCHAR *v42; // rcx
  int v43; // edx
  int v44; // r8d
  int v46; // eax
  __int64 v47; // r9
  void *v48; // rcx
  _BYTE *v49; // rax
  __int64 v50; // rcx
  NTSTATUS AlgorithmHandle; // eax
  __int64 v52; // r9
  int HashEntry; // eax
  bool v54; // zf
  BCRYPT_HANDLE v55; // r14
  NTSTATUS Property; // eax
  __int64 v57; // r9
  void *v58; // rsi
  __int64 v59; // rax
  __int128 v60; // xmm0
  __int128 v61; // xmm1
  __int128 v62; // xmm0
  UCHAR pbOutput[4]; // [rsp+50h] [rbp-79h] BYREF
  unsigned int v64; // [rsp+54h] [rbp-75h]
  ULONG pcbResult; // [rsp+58h] [rbp-71h] BYREF
  unsigned int v66; // [rsp+5Ch] [rbp-6Dh]
  __int64 v67; // [rsp+60h] [rbp-69h]
  BCRYPT_HANDLE hObject; // [rsp+68h] [rbp-61h]
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+70h] [rbp-59h]
  __m128i v70; // [rsp+80h] [rbp-49h]
  _BYTE Size[64]; // [rsp+90h] [rbp-39h] BYREF
  const wchar_t *v74; // [rsp+130h] [rbp+67h]

  v74 = a3;
  v7 = a2;
  v8 = a1;
  if ( !dword_1800CE0E4 )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&Resource, 1u);
    if ( !dword_1800CE0E4 )
    {
      GetExternalSchannelAlgorithms();
      dword_1800CE0E4 = 1;
    }
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
    v7 = a2;
    a3 = v74;
  }
  if ( !v8 || *v8 < 0x390u || v8[1] != 1936944177 )
  {
    v9 = -2146893786;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        191);
    return v9;
  }
  if ( !v7 || !a4 )
  {
    v9 = -2146893785;
    v47 = 3526;
    v50 = 2148073511LL;
    goto LABEL_89;
  }
  if ( a6 )
  {
    v9 = -2146893815;
    DebugTraceError(2148073481LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", 3533);
    return v9;
  }
  if ( wcscmp_0(a3, L"OpaqueKeyBlob") )
  {
    v9 = -2146893783;
    v47 = 3824;
    v50 = 2148073513LL;
    goto LABEL_89;
  }
  if ( a5 < 0x50 )
  {
    v47 = 3549;
    goto LABEL_86;
  }
  v10 = *(__m128i *)a4;
  v11 = *(_OWORD *)(a4 + 32);
  *(_OWORD *)Size = *(_OWORD *)(a4 + 16);
  v12 = *(_OWORD *)(a4 + 48);
  *(_OWORD *)&Size[16] = v11;
  v13 = *(_OWORD *)(a4 + 64);
  *(_OWORD *)&Size[32] = v12;
  *(_OWORD *)&Size[48] = v13;
  v70 = v10;
  if ( _mm_cvtsi128_si32(v10) > a5 || (v14 = *(_QWORD *)Size, v67 = *(_QWORD *)Size, *(_DWORD *)&Size[4] >= a5) )
  {
    v47 = 3559;
    goto LABEL_86;
  }
  v15 = v70.m128i_u32[2];
  v64 = v70.m128i_u32[2];
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 7 )
      goto LABEL_98;
    if ( LOWORD(ProtocolVersionList[i]) == v70.m128i_i32[2] )
      break;
  }
  v17 = HIDWORD(ProtocolVersionList[i]);
  if ( !(_DWORD)v17 )
  {
LABEL_98:
    v47 = 3568;
    goto LABEL_86;
  }
  for ( j = 0; ; j = (unsigned int)(j + 1) )
  {
    if ( (unsigned int)j >= g_dwCipherSuiteInfoTotalCount )
      goto LABEL_98;
    v19 = g_pCipherSuiteInfo[j];
    if ( v19 )
    {
      if ( *(_DWORD *)(v19 + 4) == v70.m128i_i32[3] && ((unsigned int)v17 & *(_DWORD *)v19) != 0 )
        break;
    }
  }
  v20 = v70.m128i_i32[1];
  v21 = *(_DWORD *)&Size[8];
  v66 = *(_DWORD *)&Size[8];
  if ( v70.m128i_i32[1] == 1936944179 && *(_DWORD *)&Size[8] > 0x30u )
  {
    v47 = 3577;
LABEL_86:
    v9 = -2146893819;
    v50 = 2148073477LL;
LABEL_89:
    DebugTraceError(v50, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v47);
    return v9;
  }
  v22 = *(unsigned int *)(v19 + 40);
  v23 = (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c";
  cbKeyObject = 0;
  hAlgorithm = (BCRYPT_ALG_HANDLE)913;
  if ( (_DWORD)v22 )
  {
    v25 = 16LL * (unsigned int)v22;
    if ( v8[(unsigned __int64)v25 / 4 + 7] )
      goto LABEL_36;
    v26 = v8[3];
    hObject = 0;
    *(_DWORD *)pbOutput = 0;
    if ( (v26 & 1) != 0 )
      v27 = l_NonPagedCipherEntryCache;
    else
      v27 = l_PagedCipherEntryCache;
    v28 = &v27[(unsigned __int64)v25 / 8];
    if ( (unsigned int)v22 >= g_dwCipherInfoTotalCount || (_mm_lfence(), (v29 = (LPCWSTR *)g_pCipherInfo[v22]) == 0) )
    {
      DebugTraceError(1168, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", 4725);
      v23 = (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c";
      goto LABEL_35;
    }
    if ( *((_DWORD *)v28 + 3) )
    {
LABEL_34:
      *(_QWORD *)&v8[(unsigned __int64)v25 / 4 + 4] = *v28;
      v8[(unsigned __int64)v25 / 4 + 6] = *((_DWORD *)v28 + 2);
LABEL_35:
      v14 = v67;
      v21 = v66;
LABEL_36:
      if ( ((*(_DWORD *)&Size[60] - 4) & 0xFFFFFFFC) != 0 || *(_DWORD *)&Size[60] == 5 )
      {
        hAlgorithm = *(BCRYPT_ALG_HANDLE *)&v8[(unsigned __int64)v25 / 4 + 4];
        if ( !hAlgorithm )
        {
          v9 = -2146893783;
          v47 = 3617;
          v50 = 2148073513LL;
          goto LABEL_89;
        }
        cbKeyObject = v8[(unsigned __int64)v25 / 4 + 6];
      }
      v15 = v64;
      goto LABEL_39;
    }
    AlgorithmHandle = GetAlgorithmHandle(*v29);
    v9 = AlgorithmHandle;
    if ( AlgorithmHandle < 0 )
    {
      v52 = 4739;
LABEL_110:
      DebugTraceError(
        (unsigned int)AlgorithmHandle,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        v52);
      goto LABEL_111;
    }
    v54 = (_DWORD)v22 == 5;
    v55 = hObject;
    if ( v54 )
    {
      pcbResult = 0;
      Property = BCryptSetProperty(hObject, L"ChainingMode", (PUCHAR)L"ChainingModeGCM", 0x20u, 0);
      v9 = Property;
      if ( Property < 0 )
      {
        v57 = 4754;
LABEL_105:
        DebugTraceError(
          (unsigned int)Property,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          v57);
        BCryptCloseAlgorithmProvider(v55, 0);
LABEL_111:
        v47 = 3600;
        v50 = v9;
        goto LABEL_89;
      }
      Property = BCryptGetProperty(hObject, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
      v9 = Property;
      if ( Property < 0 )
      {
        v57 = 4768;
        goto LABEL_105;
      }
    }
    v58 = (void *)_InterlockedCompareExchange64(v28, (signed __int64)v55, 0);
    if ( !v58
      || (pcbResult = 0,
          BCryptCloseAlgorithmProvider(v55, 0),
          AlgorithmHandle = BCryptGetProperty(v58, L"ObjectLength", pbOutput, 4u, &pcbResult, 0),
          v9 = AlgorithmHandle,
          AlgorithmHandle >= 0) )
    {
      v23 = (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c";
      v8 = a1;
      *((_DWORD *)v28 + 2) = *(_DWORD *)pbOutput;
      *((_DWORD *)v28 + 3) = 1;
      goto LABEL_34;
    }
    v52 = 4794;
    goto LABEL_110;
  }
LABEL_39:
  v30 = *(unsigned int *)(v19 + 72);
  if ( (_DWORD)v30 )
  {
    v23 = 5 * v30;
    if ( !v8[10 * v30 + 77] )
    {
      HashEntry = I_GetHashEntry(v30, (unsigned int)v8[3], &v8[2 * v23 + 68]);
      v9 = HashEntry;
      if ( HashEntry < 0 )
      {
        v47 = 3636;
        v50 = (unsigned int)HashEntry;
        goto LABEL_89;
      }
      v14 = v67;
    }
  }
  if ( v20 != 1936944179 )
  {
    if ( v20 != 1936944181 )
      return 0;
    v59 = MSCryptAlloc(80, v23, v17, v14);
    if ( v59 )
    {
      *(_DWORD *)(v59 + 12) = 0;
      v60 = *(_OWORD *)&Size[12];
      v61 = *(_OWORD *)&Size[28];
      *(_DWORD *)(v59 + 24) = v67;
      *(_OWORD *)(v59 + 28) = v60;
      *(_DWORD *)v59 = 80;
      v62 = *(_OWORD *)&Size[44];
      *(_DWORD *)(v59 + 4) = 1936944181;
      *(_OWORD *)(v59 + 44) = v61;
      *(_DWORD *)(v59 + 8) = v15;
      *(_OWORD *)(v59 + 60) = v62;
      *(_QWORD *)(v59 + 16) = v19;
      *(_DWORD *)(v59 + 76) = v21;
      *a2 = v59;
      return 0;
    }
    return (unsigned int)-2146893810;
  }
  v31 = 0;
  if ( !(_DWORD)v14 && v15 >= 0x302 && *(_DWORD *)(v19 + 36) > 1u )
  {
    v46 = wcscmp_0(*(const wchar_t **)(v19 + 48), L"ChainingModeGCM");
    v30 = 128;
    if ( v46 )
      v31 = 128;
  }
  v32 = cbKeyObject + v31 + 112;
  v33 = v32;
  if ( !v32 )
    v33 = 8;
  v34 = v32;
  LOBYTE(v35) = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
  {
    v35 = ((int)SkIsSecureKernel(v30, v23) >> 31) + 2;
    g_TrustedEnvironment = v35;
  }
  if ( (v35 & 2) != 0 )
    Pool = (char *)SkAllocatePool(512, v33, 1650945603);
  else
    Pool = (char *)ExAllocatePool2(64, v33, 1650945603);
  v37 = Pool;
  if ( !Pool )
    return (unsigned int)-2146893810;
  memset(Pool, 0, v32);
  v38 = v64;
  *((_DWORD *)v37 + 6) = v67;
  *((_DWORD *)v37 + 2) = v38;
  v39 = *(_DWORD *)&Size[60];
  *(_DWORD *)v37 = v32;
  *((_DWORD *)v37 + 1) = 1936944179;
  *((_QWORD *)v37 + 2) = v19;
  *((_DWORD *)v37 + 26) = v21;
  *((_DWORD *)v37 + 27) = v39;
  memmove(v37 + 56, &Size[12], v21);
  if ( v31 )
  {
    *((_DWORD *)v37 + 12) = v31;
    *((_DWORD *)v37 + 13) = v31;
    *((_QWORD *)v37 + 5) = &v37[cbKeyObject + 112];
  }
  if ( !*(_DWORD *)(v19 + 40)
    || (!cbKeyObject ? (pbKeyObject = 0) : (pbKeyObject = (UCHAR *)(v37 + 112)),
        (v41 = *((_DWORD *)v37 + 27), ((v41 - 4) & 0xFFFFFFFC) != 0) || v41 == 5 ? (v42 = v74) : (v42 = L"KeyDataBlob"),
        v9 = BCryptImportKey(
               hAlgorithm,
               0,
               v42,
               (BCRYPT_KEY_HANDLE *)v37 + 4,
               pbKeyObject,
               cbKeyObject,
               (PUCHAR)(a4 + 80),
               a5 - 80,
               0),
        (v9 & 0x80000000) == 0) )
  {
    *a2 = (__int64)v37;
    return 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v43,
      v44,
      (unsigned int)"Status",
      v9,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
      115);
  v48 = (void *)*((_QWORD *)v37 + 4);
  if ( v48 )
    BCryptDestroyKey(v48);
  v49 = v37;
  if ( v32 )
  {
    do
    {
      *v49++ = 0;
      --v34;
    }
    while ( v34 );
  }
  MSCryptFree(v37);
  return v9;
}

```

## disassembly

```asm
0x1800028c0  mov     [rsp-8+arg_18], r9
0x1800028c5  mov     [rsp-8+arg_10], r8
0x1800028ca  mov     [rsp-8+arg_8], rdx
0x1800028cf  mov     [rsp-8+arg_0], rcx
0x1800028d4  push    rbp
0x1800028d5  push    rbx
0x1800028d6  push    rsi
0x1800028d7  lea     rbp, [rsp-37h]
0x1800028dc  sub     rsp, 100h
0x1800028e3  cmp     cs:dword_1800CE0E4, 0
0x1800028ea  mov     rbx, r9
0x1800028ed  mov     rax, rdx
0x1800028f0  mov     rsi, rcx
0x1800028f3  jz      loc_180002DE4
0x1800028f9  mov     [rsp+110h+var_18], rdi
0x180002901  mov     [rsp+110h+var_20], r12
0x180002909  mov     [rsp+110h+var_28], r13
0x180002911  mov     [rsp+110h+var_30], r14
0x180002919  mov     [rsp+110h+var_38], r15
0x180002921  test    rsi, rsi
0x180002924  jz      short loc_180002937
0x180002926  cmp     dword ptr [rsi], 390h
0x18000292c  jb      short loc_180002937
0x18000292e  cmp     dword ptr [rsi+4], 73736C31h
0x180002935  jz      short loc_18000298F
0x180002937  mov     esi, 80090026h
0x18000293c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002943  lea     rax, WPP_GLOBAL_Control
0x18000294a  cmp     rcx, rax
0x18000294d  jz      loc_180002C9D
0x180002953  mov     eax, [rcx+2Ch]
0x180002956  test    al, 1
0x180002958  jz      loc_180002C9D
0x18000295e  mov     rcx, [rcx+18h]
0x180002962  lea     r15, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002969  mov     dword ptr [rsp+110h+pbInput], 0DBFh
0x180002971  lea     r9, aStatus; "Status"
0x180002978  mov     qword ptr [rsp+110h+cbKeyObject], r15
0x18000297d  mov     dword ptr [rsp+110h+pbKeyObject], 80090026h
0x180002985  call    WPP_SF_sDsd
0x18000298a  jmp     loc_180002C9D
0x18000298f  test    rax, rax
0x180002992  jz      loc_180002E68
0x180002998  test    rbx, rbx
0x18000299b  jz      loc_180002E68
0x1800029a1  cmp     [rbp+47h+arg_28], 0
0x1800029a5  jnz     loc_180002E26
0x1800029ab  lea     rdx, aOpaquekeyblob; "OpaqueKeyBlob"
0x1800029b2  mov     rcx, r8; Str1
0x1800029b5  call    wcscmp_0
0x1800029ba  test    eax, eax
0x1800029bc  jnz     loc_180002F6F
0x1800029c2  mov     ecx, [rbp+47h+arg_20]
0x1800029c5  cmp     ecx, 50h ; 'P'
0x1800029c8  jb      loc_180002E4E
0x1800029ce  movups  xmm2, xmmword ptr [rbx]
0x1800029d1  movups  xmm0, xmmword ptr [rbx+10h]
0x1800029d5  movups  xmm1, xmmword ptr [rbx+20h]
0x1800029d9  movaps  xmmword ptr [rbp+47h+Size], xmm0
0x1800029dd  movups  xmm0, xmmword ptr [rbx+30h]
0x1800029e1  movaps  [rbp+47h+var_70], xmm1
0x1800029e5  movups  xmm1, xmmword ptr [rbx+40h]
0x1800029e9  movd    eax, xmm2
0x1800029ed  movaps  [rbp+47h+var_60], xmm0
0x1800029f1  movaps  [rbp+47h+var_50], xmm1
0x1800029f5  movaps  [rbp+47h+var_90], xmm2
0x1800029f9  cmp     eax, ecx
0x1800029fb  ja      loc_180002E56
0x180002a01  mov     r9, [rbp+47h+Size]
0x180002a05  mov     rax, r9
0x180002a08  mov     [rbp+47h+var_B0], r9
0x180002a0c  shr     rax, 20h
0x180002a10  cmp     eax, ecx
0x180002a12  jnb     loc_180002E56
0x180002a18  mov     r15d, dword ptr [rbp+47h+var_90+8]
0x180002a1c  lea     r10, cs:180000000h
0x180002a23  mov     [rbp+47h+var_BC], r15d
0x180002a27  xor     ecx, ecx
0x180002a29  nop     dword ptr [rax+00000000h]
0x180002a30  cmp     ecx, 7
0x180002a33  jnb     loc_180002F64
0x180002a39  lea     rdx, ds:0[rcx*8]
0x180002a41  movzx   eax, word ptr [rdx+r10+0BCE60h]
0x180002a4a  cmp     eax, r15d
0x180002a4d  jz      short loc_180002A53
0x180002a4f  inc     ecx
0x180002a51  jmp     short loc_180002A30
0x180002a53  mov     r8d, [rdx+r10+0BCE64h]
0x180002a5b  test    r8d, r8d
0x180002a5e  jz      loc_180002F64
0x180002a64  mov     edx, dword ptr [rbp+47h+var_90+0Ch]
0x180002a67  xor     eax, eax
0x180002a69  nop     dword ptr [rax+00000000h]
0x180002a70  cmp     eax, cs:g_dwCipherSuiteInfoTotalCount
0x180002a76  jnb     loc_180002F64
0x180002a7c  mov     rbx, rva g_pCipherSuiteInfo[r10+rax*8]
0x180002a84  test    rbx, rbx
0x180002a87  jz      short loc_180002A8E
0x180002a89  cmp     [rbx+4], edx
0x180002a8c  jz      short loc_180002A92
0x180002a8e  inc     eax
0x180002a90  jmp     short loc_180002A70
0x180002a92  test    [rbx], r8d
0x180002a95  jz      short loc_180002A8E
0x180002a97  mov     edi, dword ptr [rbp+47h+var_90+4]
0x180002a9a  mov     r13d, dword ptr [rbp+47h+Size+8]
0x180002a9e  mov     [rbp+47h+var_B4], r13d
0x180002aa2  cmp     edi, 73736C33h
0x180002aa8  jz      loc_180002D09
0x180002aae  mov     r14d, [rbx+28h]
0x180002ab2  lea     rdx, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002ab9  xor     r12d, r12d
0x180002abc  mov     [rbp+47h+hAlgorithm], 391h
0x180002ac4  test    r14d, r14d
0x180002ac7  jz      loc_180002B5E
0x180002acd  mov     r15d, r14d
0x180002ad0  shl     r15, 4
0x180002ad4  cmp     [r15+rsi+1Ch], r12d
0x180002ad9  jnz     short loc_180002B40
0x180002adb  mov     r9d, [rsi+0Ch]
0x180002adf  mov     [rbp+47h+hObject], r12
0x180002ae3  mov     dword ptr [rbp+47h+pbOutput], r12d
0x180002ae7  test    r9b, 1
0x180002aeb  jnz     loc_180002EA5
0x180002af1  lea     r13, rva l_PagedCipherEntryCache[r10]
0x180002af8  add     r13, r15
0x180002afb  cmp     r14d, cs:g_dwCipherInfoTotalCount
0x180002b02  jnb     loc_180002ED6
0x180002b08  lfence
0x180002b0b  mov     rcx, rva g_pCipherInfo[r10+r14*8]
0x180002b13  test    rcx, rcx
0x180002b16  jz      loc_180002ED6
0x180002b1c  cmp     [r13+0Ch], r12d
0x180002b20  jz      loc_180002EB1
0x180002b26  mov     rax, [r13+0]
0x180002b2a  mov     [r15+rsi+10h], rax
0x180002b2f  mov     eax, [r13+8]
0x180002b33  mov     [r15+rsi+18h], eax
0x180002b38  mov     r9, [rbp+47h+var_B0]
0x180002b3c  mov     r13d, [rbp+47h+var_B4]
0x180002b40  mov     ecx, dword ptr [rbp+47h+var_50+0Ch]
0x180002b43  lea     eax, [rcx-4]
0x180002b46  test    eax, 0FFFFFFFCh
0x180002b4b  jnz     loc_180002D30
0x180002b51  cmp     ecx, 5
0x180002b54  jz      loc_180002D30
0x180002b5a  mov     r15d, [rbp+47h+var_BC]
0x180002b5e  mov     ecx, [rbx+48h]
0x180002b61  test    ecx, ecx
0x180002b63  jnz     loc_180002EFC
0x180002b69  cmp     edi, 73736C33h
0x180002b6f  jnz     loc_1800A042B
0x180002b75  xor     esi, esi
0x180002b77  test    r9d, r9d
0x180002b7a  jz      loc_180002CD3
0x180002b80  mov     eax, 8
0x180002b85  lea     r15d, [rsi+70h]
0x180002b89  add     r15d, r12d
0x180002b8c  mov     edi, r15d
0x180002b8f  cmovz   edi, eax
0x180002b92  mov     r14d, r15d
0x180002b95  mov     eax, cs:g_TrustedEnvironment
0x180002b9b  test    eax, eax
0x180002b9d  jz      loc_180002DC7
0x180002ba3  mov     r8d, 62676E43h
0x180002ba9  mov     rdx, rdi
0x180002bac  test    al, 2
0x180002bae  jnz     loc_180002F35
0x180002bb4  mov     ecx, 40h ; '@'
0x180002bb9  call    cs:__imp_ExAllocatePool2
0x180002bc0  nop     dword ptr [rax+rax+00h]
0x180002bc5  mov     rdi, rax
0x180002bc8  test    rax, rax
0x180002bcb  jz      loc_180002D1E
0x180002bd1  mov     r8, r14; Size
0x180002bd4  xor     edx, edx; Val
0x180002bd6  mov     rcx, rax; void *
0x180002bd9  call    memset
0x180002bde  mov     eax, [rbp+47h+var_BC]
0x180002be1  lea     rdx, [rbp+47h+Size+0Ch]; Src
0x180002be5  mov     rcx, [rbp+47h+var_B0]
0x180002be9  mov     [rdi+18h], ecx
0x180002bec  lea     rcx, [rdi+38h]; void *
0x180002bf0  mov     [rdi+8], eax
0x180002bf3  mov     eax, dword ptr [rbp+47h+var_50+0Ch]
0x180002bf6  mov     r8d, r13d; Size
0x180002bf9  mov     [rdi], r15d
0x180002bfc  mov     dword ptr [rdi+4], 73736C33h
0x180002c03  mov     [rdi+10h], rbx
0x180002c07  mov     [rdi+68h], r8d
0x180002c0b  mov     [rdi+6Ch], eax
0x180002c0e  call    memmove
0x180002c13  test    esi, esi
0x180002c15  jnz     loc_180002F4B
0x180002c1b  cmp     dword ptr [rbx+28h], 0
0x180002c1f  jz      short loc_180002C94
0x180002c21  test    r12d, r12d
0x180002c24  jz      loc_180002D28
0x180002c2a  lea     r8, [rdi+70h]
0x180002c2e  mov     ecx, [rdi+6Ch]
0x180002c31  lea     eax, [rcx-4]
0x180002c34  test    eax, 0FFFFFFFCh
0x180002c39  jnz     loc_180002D4C
0x180002c3f  cmp     ecx, 5
0x180002c42  jz      loc_180002D4C
0x180002c48  lea     rcx, aKeydatablob; "KeyDataBlob"
0x180002c4f  mov     eax, [rbp+47h+arg_20]
0x180002c52  lea     r9, [rdi+20h]; phKey
0x180002c56  mov     rdx, [rbp+47h+arg_18]
0x180002c5a  add     eax, 0FFFFFFB0h
0x180002c5d  mov     [rsp+110h+dwFlags], 0; dwFlags
0x180002c65  add     rdx, 50h ; 'P'
0x180002c69  mov     [rsp+110h+cbInput], eax; cbInput
0x180002c6d  mov     [rsp+110h+pbInput], rdx; pbInput
0x180002c72  xor     edx, edx; hImportKey
0x180002c74  mov     [rsp+110h+cbKeyObject], r12d; cbKeyObject
0x180002c79  mov     [rsp+110h+pbKeyObject], r8; pbKeyObject
0x180002c7e  mov     r8, rcx; pszBlobType
0x180002c81  mov     rcx, [rbp+47h+hAlgorithm]; hAlgorithm
0x180002c85  call    BCryptImportKey
0x180002c8a  mov     esi, eax
0x180002c8c  test    eax, eax
0x180002c8e  js      loc_180002D55
0x180002c94  mov     rcx, [rbp+47h+arg_8]
0x180002c98  mov     [rcx], rdi
0x180002c9b  xor     esi, esi
0x180002c9d  mov     r15, [rsp+110h+var_38]
0x180002ca5  mov     eax, esi
0x180002ca7  mov     r14, [rsp+110h+var_30]
0x180002caf  mov     r13, [rsp+110h+var_28]
0x180002cb7  mov     r12, [rsp+110h+var_20]
0x180002cbf  mov     rdi, [rsp+110h+var_18]
0x180002cc7  add     rsp, 100h
0x180002cce  pop     rsi
0x180002ccf  pop     rbx
0x180002cd0  pop     rbp
0x180002cd1  retn
0x180002cd3  cmp     r15d, 302h
0x180002cda  jb      loc_180002B80
0x180002ce0  cmp     dword ptr [rbx+24h], 1
0x180002ce4  jbe     loc_180002B80
0x180002cea  mov     rcx, [rbx+30h]; Str1
0x180002cee  lea     rdx, aChainingmodegc; "ChainingModeGCM"
0x180002cf5  call    wcscmp_0
0x180002cfa  test    eax, eax
0x180002cfc  mov     ecx, 80h
0x180002d01  cmovnz  esi, ecx
0x180002d04  jmp     loc_180002B80
0x180002d09  cmp     r13d, 30h ; '0'
0x180002d0d  jbe     loc_180002AAE
0x180002d13  mov     r9d, 0DF9h
0x180002d19  jmp     loc_180002E5C
0x180002d1e  mov     esi, 8009000Eh
0x180002d23  jmp     loc_180002C9D
0x180002d28  xor     r8d, r8d
0x180002d2b  jmp     loc_180002C2E
0x180002d30  mov     rax, [r15+rsi+10h]
0x180002d35  mov     [rbp+47h+hAlgorithm], rax
0x180002d39  test    rax, rax
0x180002d3c  jz      loc_180002E81
0x180002d42  mov     r12d, [r15+rsi+18h]
0x180002d47  jmp     loc_180002B5A
0x180002d4c  mov     rcx, [rbp+47h+arg_10]
0x180002d50  jmp     loc_180002C4F
0x180002d55  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d5c  lea     rax, WPP_GLOBAL_Control
0x180002d63  cmp     rcx, rax
0x180002d66  jz      short loc_180002D97
0x180002d68  mov     eax, [rcx+2Ch]
0x180002d6b  test    al, 1
0x180002d6d  jz      short loc_180002D97
0x180002d6f  mov     rcx, [rcx+18h]
0x180002d73  lea     r15, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002d7a  mov     dword ptr [rsp+110h+pbInput], 0E73h
0x180002d82  lea     r9, aStatus; "Status"
0x180002d89  mov     qword ptr [rsp+110h+cbKeyObject], r15
0x180002d8e  mov     dword ptr [rsp+110h+pbKeyObject], esi
0x180002d92  call    WPP_SF_sDsd
0x180002d97  mov     rcx, [rdi+20h]; hKey
0x180002d9b  test    rcx, rcx
0x180002d9e  jz      short loc_180002DA5
0x180002da0  call    BCryptDestroyKey
0x180002da5  mov     rax, rdi
0x180002da8  test    r14, r14
0x180002dab  jz      short loc_180002DBA
0x180002dad  mov     byte ptr [rax], 0
0x180002db0  lea     rax, [rax+1]
0x180002db4  sub     r14, 1
0x180002db8  jnz     short loc_180002DAD
0x180002dba  mov     rcx, rdi; P
0x180002dbd  call    MSCryptFree
0x180002dc2  jmp     loc_180002C9D
0x180002dc7  call    cs:__imp_SkIsSecureKernel
0x180002dce  nop     dword ptr [rax+rax+00h]
0x180002dd3  sar     eax, 1Fh
0x180002dd6  add     eax, 2
0x180002dd9  mov     cs:g_TrustedEnvironment, eax
0x180002ddf  jmp     loc_180002BA3
0x180002de4  call    cs:__imp_KeEnterCriticalRegion
0x180002deb  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```

# SPSslImportKey

- ea: `0x18000c9e0`
- end: `0x18000d0a4`
- name: `SPSslImportKey`
- size: `1732`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x18000c500`
- `0x18000c9e0`
- `0x18000d0b0`
- `0x18000dd90`
- `0x18000e090`
- `0x180010590`
- `0x18001155c`
- `0x1800123d0`
- `0x18003f5b0`
- `0x180063db0`
- `0x18008b618`
- `0x18008b798`
- `0x18008b864`
- `0x1800a4232`
- `0x1800a4380`
- `0x1800a45c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18000ccd9`
- `ntoskrnl!ExAllocatePool2` at `0x18000ccd9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000cf04`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000cf04`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000cf19`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000cf19`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a523b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a523b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a5247`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a5247`
- `ntoskrnl!SkIsSecureKernel` at `0x18000cee7`
- `ntoskrnl!SkIsSecureKernel` at `0x18000cee7`
- `ntoskrnl!SkAllocatePool` at `0x18000d05a`
- `ntoskrnl!SkAllocatePool` at `0x18000d05a`

## string_xrefs

- `0x18000ca82`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000cbd2`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000ce93`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000cf4c`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000cf98`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000d010`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800a52a7`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800a5349`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800a5374`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

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
  int v14; // r9d
  unsigned int v15; // r15d
  __int64 i; // rcx
  int v17; // r8d
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
  if ( !dword_1800D40E4 )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&Resource, 1u);
    if ( !dword_1800D40E4 )
    {
      GetExternalSchannelAlgorithms();
      dword_1800D40E4 = 1;
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
  if ( _mm_cvtsi128_si32(v10) > a5 || (v14 = *(_DWORD *)Size, v67 = *(_QWORD *)Size, *(_DWORD *)&Size[4] >= a5) )
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
  if ( !v17 )
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
      if ( *(_DWORD *)(v19 + 4) == v70.m128i_i32[3] && (v17 & *(_DWORD *)v19) != 0 )
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
    v59 = MSCryptAlloc(80, v23);
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
  if ( !v14 && v15 >= 0x302 && *(_DWORD *)(v19 + 36) > 1u )
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
0x18000c9e0  mov     [rsp-8+arg_18], r9
0x18000c9e5  mov     [rsp-8+arg_10], r8
0x18000c9ea  mov     [rsp-8+arg_8], rdx
0x18000c9ef  mov     [rsp-8+arg_0], rcx
0x18000c9f4  push    rbp
0x18000c9f5  push    rbx
0x18000c9f6  push    rsi
0x18000c9f7  lea     rbp, [rsp-37h]
0x18000c9fc  sub     rsp, 100h
0x18000ca03  cmp     cs:dword_1800D40E4, 0
0x18000ca0a  mov     rbx, r9
0x18000ca0d  mov     rax, rdx
0x18000ca10  mov     rsi, rcx
0x18000ca13  jz      loc_18000CF04
0x18000ca19  mov     [rsp+110h+var_18], rdi
0x18000ca21  mov     [rsp+110h+var_20], r12
0x18000ca29  mov     [rsp+110h+var_28], r13
0x18000ca31  mov     [rsp+110h+var_30], r14
0x18000ca39  mov     [rsp+110h+var_38], r15
0x18000ca41  test    rsi, rsi
0x18000ca44  jz      short loc_18000CA57
0x18000ca46  cmp     dword ptr [rsi], 390h
0x18000ca4c  jb      short loc_18000CA57
0x18000ca4e  cmp     dword ptr [rsi+4], 73736C31h
0x18000ca55  jz      short loc_18000CAAF
0x18000ca57  mov     esi, 80090026h
0x18000ca5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca63  lea     rax, WPP_GLOBAL_Control
0x18000ca6a  cmp     rcx, rax
0x18000ca6d  jz      loc_18000CDBD
0x18000ca73  mov     eax, [rcx+2Ch]
0x18000ca76  test    al, 1
0x18000ca78  jz      loc_18000CDBD
0x18000ca7e  mov     rcx, [rcx+18h]
0x18000ca82  lea     r15, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ca89  mov     dword ptr [rsp+110h+pbInput], 0DBFh
0x18000ca91  lea     r9, aStatus; "Status"
0x18000ca98  mov     qword ptr [rsp+110h+cbKeyObject], r15
0x18000ca9d  mov     dword ptr [rsp+110h+pbKeyObject], 80090026h
0x18000caa5  call    WPP_SF_sDsd
0x18000caaa  jmp     loc_18000CDBD
0x18000caaf  test    rax, rax
0x18000cab2  jz      loc_18000CF88
0x18000cab8  test    rbx, rbx
0x18000cabb  jz      loc_18000CF88
0x18000cac1  cmp     [rbp+47h+arg_28], 0
0x18000cac5  jnz     loc_18000CF46
0x18000cacb  lea     rdx, aOpaquekeyblob; "OpaqueKeyBlob"
0x18000cad2  mov     rcx, r8; Str1
0x18000cad5  call    wcscmp_0
0x18000cada  test    eax, eax
0x18000cadc  jnz     loc_18000D08F
0x18000cae2  mov     ecx, [rbp+47h+arg_20]
0x18000cae5  cmp     ecx, 50h ; 'P'
0x18000cae8  jb      loc_18000CF6E
0x18000caee  movups  xmm2, xmmword ptr [rbx]
0x18000caf1  movups  xmm0, xmmword ptr [rbx+10h]
0x18000caf5  movups  xmm1, xmmword ptr [rbx+20h]
0x18000caf9  movaps  xmmword ptr [rbp+47h+Size], xmm0
0x18000cafd  movups  xmm0, xmmword ptr [rbx+30h]
0x18000cb01  movaps  [rbp+47h+var_70], xmm1
0x18000cb05  movups  xmm1, xmmword ptr [rbx+40h]
0x18000cb09  movd    eax, xmm2
0x18000cb0d  movaps  [rbp+47h+var_60], xmm0
0x18000cb11  movaps  [rbp+47h+var_50], xmm1
0x18000cb15  movaps  [rbp+47h+var_90], xmm2
0x18000cb19  cmp     eax, ecx
0x18000cb1b  ja      loc_18000CF76
0x18000cb21  mov     r9, [rbp+47h+Size]
0x18000cb25  mov     rax, r9
0x18000cb28  mov     [rbp+47h+var_B0], r9
0x18000cb2c  shr     rax, 20h
0x18000cb30  cmp     eax, ecx
0x18000cb32  jnb     loc_18000CF76
0x18000cb38  mov     r15d, dword ptr [rbp+47h+var_90+8]
0x18000cb3c  lea     r10, cs:180000000h
0x18000cb43  mov     [rbp+47h+var_BC], r15d
0x18000cb47  xor     ecx, ecx
0x18000cb49  nop     dword ptr [rax+00000000h]
0x18000cb50  cmp     ecx, 7
0x18000cb53  jnb     loc_18000D084
0x18000cb59  lea     rdx, ds:0[rcx*8]
0x18000cb61  movzx   eax, word ptr [rdx+r10+0C3570h]
0x18000cb6a  cmp     eax, r15d
0x18000cb6d  jz      short loc_18000CB73
0x18000cb6f  inc     ecx
0x18000cb71  jmp     short loc_18000CB50
0x18000cb73  mov     r8d, [rdx+r10+0C3574h]
0x18000cb7b  test    r8d, r8d
0x18000cb7e  jz      loc_18000D084
0x18000cb84  mov     edx, dword ptr [rbp+47h+var_90+0Ch]
0x18000cb87  xor     eax, eax
0x18000cb89  nop     dword ptr [rax+00000000h]
0x18000cb90  cmp     eax, cs:g_dwCipherSuiteInfoTotalCount
0x18000cb96  jnb     loc_18000D084
0x18000cb9c  mov     rbx, rva g_pCipherSuiteInfo[r10+rax*8]
0x18000cba4  test    rbx, rbx
0x18000cba7  jz      short loc_18000CBAE
0x18000cba9  cmp     [rbx+4], edx
0x18000cbac  jz      short loc_18000CBB2
0x18000cbae  inc     eax
0x18000cbb0  jmp     short loc_18000CB90
0x18000cbb2  test    [rbx], r8d
0x18000cbb5  jz      short loc_18000CBAE
0x18000cbb7  mov     edi, dword ptr [rbp+47h+var_90+4]
0x18000cbba  mov     r13d, dword ptr [rbp+47h+Size+8]
0x18000cbbe  mov     [rbp+47h+var_B4], r13d
0x18000cbc2  cmp     edi, 73736C33h
0x18000cbc8  jz      loc_18000CE29
0x18000cbce  mov     r14d, [rbx+28h]
0x18000cbd2  lea     rdx, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cbd9  xor     r12d, r12d
0x18000cbdc  mov     [rbp+47h+hAlgorithm], 391h
0x18000cbe4  test    r14d, r14d
0x18000cbe7  jz      loc_18000CC7E
0x18000cbed  mov     r15d, r14d
0x18000cbf0  shl     r15, 4
0x18000cbf4  cmp     [r15+rsi+1Ch], r12d
0x18000cbf9  jnz     short loc_18000CC60
0x18000cbfb  mov     r9d, [rsi+0Ch]
0x18000cbff  mov     [rbp+47h+hObject], r12
0x18000cc03  mov     dword ptr [rbp+47h+pbOutput], r12d
0x18000cc07  test    r9b, 1
0x18000cc0b  jnz     loc_18000CFC5
0x18000cc11  lea     r13, rva l_PagedCipherEntryCache[r10]
0x18000cc18  add     r13, r15
0x18000cc1b  cmp     r14d, cs:g_dwCipherInfoTotalCount
0x18000cc22  jnb     loc_18000CFF6
0x18000cc28  lfence
0x18000cc2b  mov     rcx, rva g_pCipherInfo[r10+r14*8]
0x18000cc33  test    rcx, rcx
0x18000cc36  jz      loc_18000CFF6
0x18000cc3c  cmp     [r13+0Ch], r12d
0x18000cc40  jz      loc_18000CFD1
0x18000cc46  mov     rax, [r13+0]
0x18000cc4a  mov     [r15+rsi+10h], rax
0x18000cc4f  mov     eax, [r13+8]
0x18000cc53  mov     [r15+rsi+18h], eax
0x18000cc58  mov     r9, [rbp+47h+var_B0]
0x18000cc5c  mov     r13d, [rbp+47h+var_B4]
0x18000cc60  mov     ecx, dword ptr [rbp+47h+var_50+0Ch]
0x18000cc63  lea     eax, [rcx-4]
0x18000cc66  test    eax, 0FFFFFFFCh
0x18000cc6b  jnz     loc_18000CE50
0x18000cc71  cmp     ecx, 5
0x18000cc74  jz      loc_18000CE50
0x18000cc7a  mov     r15d, [rbp+47h+var_BC]
0x18000cc7e  mov     ecx, [rbx+48h]
0x18000cc81  test    ecx, ecx
0x18000cc83  jnz     loc_18000D01C
0x18000cc89  cmp     edi, 73736C33h
0x18000cc8f  jnz     loc_1800A5399
0x18000cc95  xor     esi, esi
0x18000cc97  test    r9d, r9d
0x18000cc9a  jz      loc_18000CDF3
0x18000cca0  mov     eax, 8
0x18000cca5  lea     r15d, [rsi+70h]
0x18000cca9  add     r15d, r12d
0x18000ccac  mov     edi, r15d
0x18000ccaf  cmovz   edi, eax
0x18000ccb2  mov     r14d, r15d
0x18000ccb5  mov     eax, cs:g_TrustedEnvironment
0x18000ccbb  test    eax, eax
0x18000ccbd  jz      loc_18000CEE7
0x18000ccc3  mov     r8d, 62676E43h
0x18000ccc9  mov     rdx, rdi
0x18000cccc  test    al, 2
0x18000ccce  jnz     loc_18000D055
0x18000ccd4  mov     ecx, 40h ; '@'
0x18000ccd9  call    cs:__imp_ExAllocatePool2
0x18000cce0  nop     dword ptr [rax+rax+00h]
0x18000cce5  mov     rdi, rax
0x18000cce8  test    rax, rax
0x18000cceb  jz      loc_18000CE3E
0x18000ccf1  mov     r8, r14; Size
0x18000ccf4  xor     edx, edx; Val
0x18000ccf6  mov     rcx, rax; void *
0x18000ccf9  call    memset
0x18000ccfe  mov     eax, [rbp+47h+var_BC]
0x18000cd01  lea     rdx, [rbp+47h+Size+0Ch]; Src
0x18000cd05  mov     rcx, [rbp+47h+var_B0]
0x18000cd09  mov     [rdi+18h], ecx
0x18000cd0c  lea     rcx, [rdi+38h]; void *
0x18000cd10  mov     [rdi+8], eax
0x18000cd13  mov     eax, dword ptr [rbp+47h+var_50+0Ch]
0x18000cd16  mov     r8d, r13d; Size
0x18000cd19  mov     [rdi], r15d
0x18000cd1c  mov     dword ptr [rdi+4], 73736C33h
0x18000cd23  mov     [rdi+10h], rbx
0x18000cd27  mov     [rdi+68h], r8d
0x18000cd2b  mov     [rdi+6Ch], eax
0x18000cd2e  call    memmove
0x18000cd33  test    esi, esi
0x18000cd35  jnz     loc_18000D06B
0x18000cd3b  cmp     dword ptr [rbx+28h], 0
0x18000cd3f  jz      short loc_18000CDB4
0x18000cd41  test    r12d, r12d
0x18000cd44  jz      loc_18000CE48
0x18000cd4a  lea     r8, [rdi+70h]
0x18000cd4e  mov     ecx, [rdi+6Ch]
0x18000cd51  lea     eax, [rcx-4]
0x18000cd54  test    eax, 0FFFFFFFCh
0x18000cd59  jnz     loc_18000CE6C
0x18000cd5f  cmp     ecx, 5
0x18000cd62  jz      loc_18000CE6C
0x18000cd68  lea     rcx, aKeydatablob; "KeyDataBlob"
0x18000cd6f  mov     eax, [rbp+47h+arg_20]
0x18000cd72  lea     r9, [rdi+20h]; phKey
0x18000cd76  mov     rdx, [rbp+47h+arg_18]
0x18000cd7a  add     eax, 0FFFFFFB0h
0x18000cd7d  mov     [rsp+110h+dwFlags], 0; dwFlags
0x18000cd85  add     rdx, 50h ; 'P'
0x18000cd89  mov     [rsp+110h+cbInput], eax; cbInput
0x18000cd8d  mov     [rsp+110h+pbInput], rdx; pbInput
0x18000cd92  xor     edx, edx; hImportKey
0x18000cd94  mov     [rsp+110h+cbKeyObject], r12d; cbKeyObject
0x18000cd99  mov     [rsp+110h+pbKeyObject], r8; pbKeyObject
0x18000cd9e  mov     r8, rcx; pszBlobType
0x18000cda1  mov     rcx, [rbp+47h+hAlgorithm]; hAlgorithm
0x18000cda5  call    BCryptImportKey
0x18000cdaa  mov     esi, eax
0x18000cdac  test    eax, eax
0x18000cdae  js      loc_18000CE75
0x18000cdb4  mov     rcx, [rbp+47h+arg_8]
0x18000cdb8  mov     [rcx], rdi
0x18000cdbb  xor     esi, esi
0x18000cdbd  mov     r15, [rsp+110h+var_38]
0x18000cdc5  mov     eax, esi
0x18000cdc7  mov     r14, [rsp+110h+var_30]
0x18000cdcf  mov     r13, [rsp+110h+var_28]
0x18000cdd7  mov     r12, [rsp+110h+var_20]
0x18000cddf  mov     rdi, [rsp+110h+var_18]
0x18000cde7  add     rsp, 100h
0x18000cdee  pop     rsi
0x18000cdef  pop     rbx
0x18000cdf0  pop     rbp
0x18000cdf1  retn
0x18000cdf3  cmp     r15d, 302h
0x18000cdfa  jb      loc_18000CCA0
0x18000ce00  cmp     dword ptr [rbx+24h], 1
0x18000ce04  jbe     loc_18000CCA0
0x18000ce0a  mov     rcx, [rbx+30h]; Str1
0x18000ce0e  lea     rdx, aChainingmodegc; "ChainingModeGCM"
0x18000ce15  call    wcscmp_0
0x18000ce1a  test    eax, eax
0x18000ce1c  mov     ecx, 80h
0x18000ce21  cmovnz  esi, ecx
0x18000ce24  jmp     loc_18000CCA0
0x18000ce29  cmp     r13d, 30h ; '0'
0x18000ce2d  jbe     loc_18000CBCE
0x18000ce33  mov     r9d, 0DF9h
0x18000ce39  jmp     loc_18000CF7C
0x18000ce3e  mov     esi, 8009000Eh
0x18000ce43  jmp     loc_18000CDBD
0x18000ce48  xor     r8d, r8d
0x18000ce4b  jmp     loc_18000CD4E
0x18000ce50  mov     rax, [r15+rsi+10h]
0x18000ce55  mov     [rbp+47h+hAlgorithm], rax
0x18000ce59  test    rax, rax
0x18000ce5c  jz      loc_18000CFA1
0x18000ce62  mov     r12d, [r15+rsi+18h]
0x18000ce67  jmp     loc_18000CC7A
0x18000ce6c  mov     rcx, [rbp+47h+arg_10]
0x18000ce70  jmp     loc_18000CD6F
0x18000ce75  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce7c  lea     rax, WPP_GLOBAL_Control
0x18000ce83  cmp     rcx, rax
0x18000ce86  jz      short loc_18000CEB7
0x18000ce88  mov     eax, [rcx+2Ch]
0x18000ce8b  test    al, 1
0x18000ce8d  jz      short loc_18000CEB7
0x18000ce8f  mov     rcx, [rcx+18h]
0x18000ce93  lea     r15, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ce9a  mov     dword ptr [rsp+110h+pbInput], 0E73h
0x18000cea2  lea     r9, aStatus; "Status"
0x18000cea9  mov     qword ptr [rsp+110h+cbKeyObject], r15
0x18000ceae  mov     dword ptr [rsp+110h+pbKeyObject], esi
0x18000ceb2  call    WPP_SF_sDsd
0x18000ceb7  mov     rcx, [rdi+20h]; hKey
0x18000cebb  test    rcx, rcx
0x18000cebe  jz      short loc_18000CEC5
0x18000cec0  call    BCryptDestroyKey
0x18000cec5  mov     rax, rdi
0x18000cec8  test    r14, r14
0x18000cecb  jz      short loc_18000CEDA
0x18000cecd  mov     byte ptr [rax], 0
0x18000ced0  lea     rax, [rax+1]
0x18000ced4  sub     r14, 1
0x18000ced8  jnz     short loc_18000CECD
0x18000ceda  mov     rcx, rdi; P
0x18000cedd  call    MSCryptFree
0x18000cee2  jmp     loc_18000CDBD
0x18000cee7  call    cs:__imp_SkIsSecureKernel
0x18000ceee  nop     dword ptr [rax+rax+00h]
0x18000cef3  sar     eax, 1Fh
0x18000cef6  add     eax, 2
0x18000cef9  mov     cs:g_TrustedEnvironment, eax
0x18000ceff  jmp     loc_18000CCC3
0x18000cf04  call    cs:__imp_KeEnterCriticalRegion
0x18000cf0b  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```

# BCryptOpenAlgorithmProvider

- ea: `0x1800449b0`
- end: `0x1800451e8`
- name: `BCryptOpenAlgorithmProvider`
- size: `2104`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE *phAlgorithm, LPCWSTR pszAlgId, LPCWSTR pszImplementation, ULONG dwFlags)`
- caller_count: `6`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x180001770`
- `0x18005a6dc`
- `0x180067a38`
- `0x1800815a8`
- `0x180084550`
- `0x1800849e0`

## callees

- `0x1800010ac`
- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x180024a34`
- `0x180039c40`
- `0x18003a46c`
- `0x18003cdf4`
- `0x1800414e0`
- `0x1800449b0`
- `0x1800451f0`
- `0x180048c4c`
- `0x18005a8fc`
- `0x18005aca8`
- `0x18005b0e8`
- `0x18005b260`
- `0x18005fe74`
- `0x18009d820`
- `0x18009d860`
- `0x18009dd40`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180044a31`
- `ntoskrnl!KeGetCurrentIrql` at `0x180044a31`
- `ntoskrnl!wcsncpy_s` at `0x180044c39`
- `ntoskrnl!wcsncpy_s` at `0x180044c39`

## string_xrefs

- `0x180044b41`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180044b97`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180044bd5`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180044c48`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18004509e`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptOpenAlgorithmProvider(
        BCRYPT_ALG_HANDLE *phAlgorithm,
        LPCWSTR pszAlgId,
        LPCWSTR pszImplementation,
        ULONG dwFlags)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(_QWORD, const wchar_t *, char *, __int64, int *, _DWORD); // r12
  LPCWSTR v7; // rsi
  const wchar_t *v8; // r15
  int v10; // edx
  int v11; // r8d
  NTSTATUS Provider; // ebx
  __int64 v13; // r9
  __int64 v14; // rcx
  char TrustedEnvironment; // al
  ULONG v16; // r8d
  const WCHAR *v17; // rdi
  int v18; // eax
  NTSTATUS v19; // esi
  _QWORD *v20; // rax
  _QWORD *v21; // r14
  void *v22; // r8
  unsigned int v23; // ecx
  char v24; // r12
  __int64 *v25; // rdx
  __int64 v26; // rax
  __int64 v27; // r9
  __int64 v28; // rdx
  _OWORD *v29; // rax
  _OWORD *v30; // rcx
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  int v38; // eax
  LPCWSTR v39; // r12
  _QWORD *v40; // r15
  NTSTATUS v41; // eax
  __int64 v42; // r15
  __int64 v43; // rcx
  __int64 v44; // r9
  int v45; // eax
  __int64 v46; // rcx
  __int64 v47; // rbx
  __int64 v48; // rdi
  __int64 v49; // rdx
  char v50; // al
  char v52; // [rsp+40h] [rbp-C0h]
  _BYTE v53[15]; // [rsp+41h] [rbp-BFh] BYREF
  PVOID pvBuffer; // [rsp+50h] [rbp-B0h] BYREF
  NTSTATUS v55; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR v56; // [rsp+60h] [rbp-A0h]
  ULONG pcbBuffer; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v58; // [rsp+6Ch] [rbp-94h] BYREF
  LPCWSTR v59; // [rsp+70h] [rbp-90h]
  int v60; // [rsp+78h] [rbp-88h] BYREF
  __int64 (__fastcall *v61)(_QWORD *, LPCWSTR, _QWORD); // [rsp+80h] [rbp-80h] BYREF
  __int64 v62; // [rsp+88h] [rbp-78h]
  __int64 (__fastcall *v63)(_QWORD, const wchar_t *, char *, __int64, int *, _DWORD); // [rsp+90h] [rbp-70h] BYREF
  __int64 v64; // [rsp+98h] [rbp-68h] BYREF
  __int64 v65; // [rsp+A0h] [rbp-60h] BYREF
  void (__fastcall *v66)(_QWORD, _QWORD); // [rsp+A8h] [rbp-58h] BYREF
  void (__fastcall *v67[2])(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD); // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v68[32]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v69; // [rsp+E0h] [rbp-20h]
  __int64 v70; // [rsp+E8h] [rbp-18h]
  __int64 *v71; // [rsp+F0h] [rbp-10h]
  __int64 v72; // [rsp+F8h] [rbp-8h]
  NTSTATUS *v73; // [rsp+100h] [rbp+0h]
  __int64 v74; // [rsp+108h] [rbp+8h]
  _BYTE *v75; // [rsp+110h] [rbp+10h]
  __int64 v76; // [rsp+118h] [rbp+18h]
  char v77[16]; // [rsp+120h] [rbp+20h] BYREF
  char v78[16]; // [rsp+130h] [rbp+30h] BYREF
  char v79[16]; // [rsp+140h] [rbp+40h] BYREF
  char v80[256]; // [rsp+150h] [rbp+50h] BYREF

  v56 = pszImplementation;
  v66 = 0;
  v4 = 0;
  *(_QWORD *)&v53[7] = 0;
  v5 = 0;
  pvBuffer = 0;
  v53[0] = 0;
  v7 = pszImplementation;
  v60 = 0;
  v8 = pszAlgId;
  pcbBuffer = 0;
  v67[0] = 0;
  v63 = 0;
  v61 = 0;
  v59 = pszAlgId;
  v65 = (__int64)phAlgorithm;
  v58 = 4;
  if ( KeGetCurrentIrql() >= 2u )
  {
    Provider = -1073741637;
    v13 = 1939;
    v14 = 3221225659LL;
LABEL_71:
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v13);
    goto LABEL_72;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_SSD(*((_QWORD *)WPP_GLOBAL_Control + 3), v10, v11, (_DWORD)v8, (__int64)v7, dwFlags);
  if ( !phAlgorithm || !v8 )
  {
    Provider = -1073741811;
    v13 = 1955;
    v14 = 3221225485LL;
    goto LABEL_71;
  }
  TrustedEnvironment = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
    TrustedEnvironment = GetTrustedEnvironment();
  if ( (TrustedEnvironment & 1) == 0 )
  {
    Provider = VsmOpenAlgorithmProvider(phAlgorithm, v8, v7, dwFlags);
    goto LABEL_72;
  }
  v16 = 0;
  v52 = 0;
  if ( g_fLoadCNGDone )
  {
    v17 = v7;
    if ( !v7 )
    {
      v52 = 1;
      v16 = 2;
    }
  }
  else
  {
    v17 = L"Microsoft Primitive Provider";
  }
  pcbBuffer = 0;
  pvBuffer = 0;
  v18 = BCryptResolveProvidersForBcoapCached(v8, v17, v16, &pcbBuffer, (PCRYPT_PROVIDER_REFS *)&pvBuffer, (__int64)v53);
  Provider = v18;
  if ( v18 < 0 )
  {
    LogBCryptOpenProviderFailure((_DWORD)v17, (_DWORD)v8, dwFlags, v18, 1);
    DebugTraceError((unsigned int)Provider, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 2030);
LABEL_18:
    v4 = 0;
    goto LABEL_72;
  }
  v19 = ***((_DWORD ***)pvBuffer + 1);
  v55 = v19;
  if ( (unsigned int)(v19 - 1) > 7 )
  {
    LogBCryptOpenProviderFailure((_DWORD)v17, (_DWORD)v8, dwFlags, v18, 1);
    Provider = -1073741816;
    DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 2061);
    v7 = v56;
    goto LABEL_18;
  }
  v20 = (_QWORD *)MSCryptAlloc(968);
  v21 = v20;
  if ( !v20 )
  {
    Provider = -1073741801;
    DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 2076);
    v4 = 0;
LABEL_23:
    v7 = v56;
    goto LABEL_72;
  }
  memset(v20, 0, 0x3C8u);
  *(_DWORD *)v21 = 968;
  *((_DWORD *)v21 + 1) = 1431655761;
  *((_DWORD *)v21 + 4) = 1;
  *((_DWORD *)v21 + 9) = v19;
  wcsncpy_s((wchar_t *)v21 + 222, 0x104u, v8, 0xFFFFFFFFFFFFFFFFuLL);
  *((_DWORD *)v21 + 8) = dwFlags & 1;
  v23 = 0;
  *(_DWORD *)&v53[3] = 0;
  if ( *(_DWORD *)pvBuffer )
  {
    v24 = v52;
    v22 = v21 + 6;
    v25 = v21 + 5;
    while ( 1 )
    {
      v62 = v23;
      Provider = LoadProviderEx(*(int **)(*((_QWORD *)pvBuffer + 1) + 8LL * v23), (__int64)v25, 0, v25, v22);
      v26 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)pvBuffer + 1) + 8 * v62) + 16LL);
      *(_QWORD *)&v53[7] = v26;
      v64 = v26;
      if ( Provider >= 0 )
      {
        v28 = 3;
        v29 = v21 + 6;
        v30 = v68;
        do
        {
          v31 = v29[1];
          *v30 = *v29;
          v32 = v29[2];
          v30[1] = v31;
          v33 = v29[3];
          v30[2] = v32;
          v34 = v29[4];
          v30[3] = v33;
          v35 = v29[5];
          v30[4] = v34;
          v36 = v29[6];
          v30[5] = v35;
          v37 = v29[7];
          v29 += 8;
          v30[6] = v36;
          v30[7] = v37;
          v30 += 8;
          --v28;
        }
        while ( v28 );
        *(_QWORD *)v30 = *(_QWORD *)v29;
        v38 = ValidateFunctionTable(
                v55,
                (unsigned int)v68,
                (unsigned int)&v61,
                (unsigned int)&v66,
                (__int64)v67,
                (__int64)&v63);
        Provider = v38;
        if ( v38 >= 0 )
        {
          v39 = v59;
          v40 = v21 + 3;
          Provider = v61(v21 + 3, v59, dwFlags);
          if ( Provider == -1073700863 )
          {
            if ( v55 == 2 && (dwFlags & 0x68) == 8 )
            {
              v41 = v61(v21 + 3, v39, dwFlags & 0xFFFFFFF7);
              *((_DWORD *)v21 + 2) |= 8u;
              Provider = v41;
              goto LABEL_38;
            }
          }
          else
          {
LABEL_38:
            if ( Provider >= 0 )
            {
              v5 = v63;
              goto LABEL_46;
            }
          }
          LODWORD(v8) = (_DWORD)v39;
          LogBCryptOpenProviderFailure(
            *(_QWORD *)(*(_QWORD *)(*((_QWORD *)pvBuffer + 1) + 8 * v62) + 16LL),
            (_DWORD)v39,
            dwFlags,
            Provider,
            4);
          DebugTraceError(
            (unsigned int)Provider,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
            2243);
          if ( v52 != 1 )
            goto LABEL_60;
          UnloadProvider(v21[5]);
          v24 = 1;
          v25 = v21 + 5;
          v21[5] = 0;
          goto LABEL_41;
        }
        LogBCryptOpenProviderFailure(
          *(_QWORD *)(*(_QWORD *)(*((_QWORD *)pvBuffer + 1) + 8 * v62) + 16LL),
          (_DWORD)v8,
          dwFlags,
          v38,
          3);
        v27 = 2179;
      }
      else
      {
        LogBCryptOpenProviderFailure(v26, (_DWORD)v8, dwFlags, Provider, 2);
        v27 = 2140;
      }
      DebugTraceError((unsigned int)Provider, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v27);
      if ( v24 != 1 )
        goto LABEL_60;
      v25 = v21 + 5;
LABEL_41:
      v22 = v21 + 6;
      v23 = *(_DWORD *)&v53[3] + 1;
      *(_DWORD *)&v53[3] = v23;
      if ( v23 >= *(_DWORD *)pvBuffer )
      {
        v42 = v64;
        *(_QWORD *)&v53[7] = v64;
        *(_DWORD *)&v53[3] = v23;
        if ( Provider < 0 )
        {
          DebugTraceError(
            (unsigned int)Provider,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
            2276);
          v4 = v42;
          goto LABEL_61;
        }
        v5 = v63;
        break;
      }
    }
  }
  v40 = v21 + 3;
LABEL_46:
  if ( v55 == 2 )
  {
    if ( !v5 )
    {
      Provider = -1073741595;
      v43 = 3221225701LL;
      v44 = 2292;
      goto LABEL_58;
    }
    v40 = v21 + 3;
    v45 = v5(v21[3], L"HashBlockLength", (char *)v21 + 12, 4, &v60, 0);
    Provider = v45;
    if ( v45 < 0 )
    {
      v44 = 2304;
LABEL_57:
      v43 = (unsigned int)v45;
LABEL_58:
      DebugTraceError(v43, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v44);
      if ( v66 )
        v66(*v40, 0);
LABEL_60:
      v4 = *(_QWORD *)&v53[7];
LABEL_61:
      v46 = v21[5];
      if ( v46 )
        UnloadProvider(v46);
      MSCryptFree(v21);
      v8 = v59;
      goto LABEL_23;
    }
  }
  else if ( v55 == 3 )
  {
    if ( !v5 )
    {
      Provider = -1073741595;
      v43 = 3221225701LL;
      v44 = 2313;
      goto LABEL_58;
    }
    v40 = v21 + 3;
    v45 = v5(v21[3], L"PaddingSchemes", (char *)v21 + 440, v58, (int *)&v58, 0);
    Provider = v45;
    if ( v45 < 0 )
    {
      v44 = 2325;
      goto LABEL_57;
    }
  }
  v47 = 0;
  v48 = *(unsigned int *)&v53[3];
  if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)pvBuffer + 1) + 8LL * *(unsigned int *)&v53[3]) + 24LL) )
  {
    do
    {
      v49 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)pvBuffer + 1) + 8 * v48) + 32LL) + 8 * v47);
      v67[0](v21[3], *(_QWORD *)v49, *(_QWORD *)(v49 + 16), *(unsigned int *)(v49 + 8), 0);
      v47 = (unsigned int)(v47 + 1);
    }
    while ( (unsigned int)v47 < *(_DWORD *)(*(_QWORD *)(*((_QWORD *)pvBuffer + 1) + 8 * v48) + 24LL) );
  }
  *(_QWORD *)v65 = v21;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 3), 13, v22, v21);
  v8 = v59;
  v7 = v56;
  Provider = 0;
  v4 = *(_QWORD *)&v53[7];
LABEL_72:
  v50 = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
    v50 = GetTrustedEnvironment();
  if ( (v50 & 1) != 0
    && (unsigned int)dword_1800C95C0 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_1800C95C0, 0x400000000000LL) )
  {
    v65 = 1;
    v69 = &v65;
    v70 = 8;
    v71 = &v64;
    v64 = 0x1000000;
    v73 = &v55;
    v75 = &v53[3];
    v72 = 8;
    v55 = Provider;
    v74 = 4;
    *(_DWORD *)&v53[3] = 1;
    v76 = 4;
    tlgCreate1Sz_wchar_t(v77, g_processImageName);
    tlgCreate1Sz_wchar_t(v78, v8);
    tlgCreate1Sz_wchar_t(v79, v7);
    tlgCreate1Sz_wchar_t(v80, v4);
    tlgWriteAgg((unsigned int)&dword_1800C95C0, (unsigned int)&word_1800C07D6, 0, 10, (__int64)v68);
  }
  if ( v53[0] && pvBuffer )
    BCryptFreeBuffer(pvBuffer);
  return Provider;
}

```

## disassembly

```asm
0x1800449b0  push    rbp
0x1800449b2  push    rbx
0x1800449b3  push    rsi
0x1800449b4  push    rdi
0x1800449b5  push    r12
0x1800449b7  push    r13
0x1800449b9  push    r14
0x1800449bb  push    r15
0x1800449bd  lea     rbp, [rsp-168h]
0x1800449c5  sub     rsp, 268h
0x1800449cc  mov     rax, cs:__security_cookie
0x1800449d3  xor     rax, rsp
0x1800449d6  mov     [rbp+1A0h+var_50], rax
0x1800449dd  xor     r14d, r14d
0x1800449e0  mov     [rsp+2A0h+var_240], r8
0x1800449e5  mov     [rbp+1A0h+var_1F8], r14
0x1800449e9  mov     edi, r14d
0x1800449ec  mov     qword ptr [rsp+2A0h+var_25F+7], r14
0x1800449f1  mov     r12d, r14d
0x1800449f4  mov     [rsp+2A0h+pvBuffer], r14
0x1800449f9  mov     r13d, r9d
0x1800449fc  mov     [rsp+2A0h+var_25F], r14b
0x180044a01  mov     rsi, r8
0x180044a04  mov     [rsp+2A0h+var_228], r14d
0x180044a09  mov     r15, rdx
0x180044a0c  mov     [rsp+2A0h+pcbBuffer], r14d
0x180044a11  mov     rbx, rcx
0x180044a14  mov     [rbp+1A0h+var_1F0], r14
0x180044a18  mov     [rbp+1A0h+var_210], r14
0x180044a1c  mov     [rbp+1A0h+var_220], r14
0x180044a20  mov     [rsp+2A0h+var_230], rdx
0x180044a25  mov     [rbp+1A0h+var_200], rcx
0x180044a29  mov     [rsp+2A0h+var_234], 4
0x180044a31  call    cs:__imp_KeGetCurrentIrql
0x180044a38  nop     dword ptr [rax+rax+00h]
0x180044a3d  cmp     al, 2
0x180044a3f  jb      short loc_180044A56
0x180044a41  mov     ebx, 0C00000BBh
0x180044a46  mov     r9d, 793h
0x180044a4c  mov     ecx, 0C00000BBh
0x180044a51  jmp     loc_18004509E
0x180044a56  mov     rcx, cs:WPP_GLOBAL_Control
0x180044a5d  lea     rax, WPP_GLOBAL_Control
0x180044a64  cmp     rcx, rax
0x180044a67  jz      short loc_180044A86
0x180044a69  mov     eax, [rcx+2Ch]
0x180044a6c  test    al, 4
0x180044a6e  jz      short loc_180044A86
0x180044a70  mov     rcx, [rcx+18h]
0x180044a74  mov     r9, r15
0x180044a77  mov     dword ptr [rsp+2A0h+var_278], r13d
0x180044a7c  mov     [rsp+2A0h+var_280], rsi
0x180044a81  call    WPP_SF_SSD
0x180044a86  test    rbx, rbx
0x180044a89  jz      loc_18004508E
0x180044a8f  test    r15, r15
0x180044a92  jz      loc_18004508E
0x180044a98  mov     eax, cs:g_TrustedEnvironment
0x180044a9e  test    eax, eax
0x180044aa0  jnz     short loc_180044AA7
0x180044aa2  call    GetTrustedEnvironment
0x180044aa7  test    al, 1
0x180044aa9  jnz     short loc_180044AC3
0x180044aab  mov     r9d, r13d
0x180044aae  mov     r8, rsi
0x180044ab1  mov     rdx, r15
0x180044ab4  mov     rcx, rbx
0x180044ab7  call    VsmOpenAlgorithmProvider
0x180044abc  mov     ebx, eax
0x180044abe  jmp     loc_1800450B1
0x180044ac3  cmp     cs:g_fLoadCNGDone, r14d
0x180044aca  mov     r8d, r14d
0x180044acd  mov     [rsp+2A0h+var_260], r14b
0x180044ad2  jnz     short loc_180044ADD
0x180044ad4  lea     rdi, pszProvider; "Microsoft Primitive Provider"
0x180044adb  jmp     short loc_180044AEE
0x180044add  mov     rdi, rsi
0x180044ae0  test    rsi, rsi
0x180044ae3  jnz     short loc_180044AEE
0x180044ae5  mov     [rsp+2A0h+var_260], 1
0x180044aea  lea     r8d, [rsi+2]; dwFlags
0x180044aee  lea     rax, [rsp+2A0h+var_25F]
0x180044af3  mov     [rsp+2A0h+pcbBuffer], r14d
0x180044af8  mov     [rsp+2A0h+var_278], rax; __int64
0x180044afd  lea     r9, [rsp+2A0h+pcbBuffer]; pcbBuffer
0x180044b02  lea     rax, [rsp+2A0h+pvBuffer]
0x180044b07  mov     [rsp+2A0h+pvBuffer], r14
0x180044b0c  mov     rdx, rdi; pszProvider
0x180044b0f  mov     [rsp+2A0h+var_280], rax; PCRYPT_PROVIDER_REFS *
0x180044b14  mov     rcx, r15; pszSrc
0x180044b17  call    BCryptResolveProvidersForBcoapCached
0x180044b1c  mov     ebx, eax
0x180044b1e  test    eax, eax
0x180044b20  jns     short loc_180044B5E
0x180044b22  mov     r9d, eax
0x180044b25  mov     dword ptr [rsp+2A0h+var_280], 1
0x180044b2d  mov     r8d, r13d
0x180044b30  mov     rdx, r15
0x180044b33  mov     rcx, rdi
0x180044b36  call    _LogBCryptOpenProviderFailure
0x180044b3b  mov     r9d, 7EEh
0x180044b41  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180044b48  lea     rdx, aStatus; "Status"
0x180044b4f  mov     ecx, ebx
0x180044b51  call    DebugTraceError
0x180044b56  mov     rdi, r12
0x180044b59  jmp     loc_1800450B1
0x180044b5e  mov     rax, [rsp+2A0h+pvBuffer]
0x180044b63  mov     rcx, [rax+8]
0x180044b67  mov     rax, [rcx]
0x180044b6a  mov     esi, [rax]
0x180044b6c  mov     [rsp+2A0h+var_248], esi
0x180044b70  lea     eax, [rsi-1]
0x180044b73  cmp     eax, 7
0x180044b76  jbe     short loc_180044BBB
0x180044b78  mov     r9d, ebx
0x180044b7b  mov     dword ptr [rsp+2A0h+var_280], 1
0x180044b83  mov     r8d, r13d
0x180044b86  mov     rdx, r15
0x180044b89  mov     rcx, rdi
0x180044b8c  call    _LogBCryptOpenProviderFailure
0x180044b91  mov     r9d, 80Dh
0x180044b97  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180044b9e  lea     rdx, aStatus; "Status"
0x180044ba5  mov     ecx, 0C0000008h
0x180044baa  mov     ebx, 0C0000008h
0x180044baf  call    DebugTraceError
0x180044bb4  mov     rsi, [rsp+2A0h+var_240]
0x180044bb9  jmp     short loc_180044B56
0x180044bbb  mov     ebx, 3C8h
0x180044bc0  mov     ecx, ebx
0x180044bc2  call    MSCryptAlloc
0x180044bc7  mov     r14, rax
0x180044bca  test    rax, rax
0x180044bcd  jnz     short loc_180044C02
0x180044bcf  mov     r9d, 81Ch
0x180044bd5  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180044bdc  lea     rdx, aStatus; "Status"
0x180044be3  mov     ecx, 0C0000017h
0x180044be8  mov     ebx, 0C0000017h
0x180044bed  call    DebugTraceError
0x180044bf2  mov     rdi, r12
0x180044bf5  mov     rsi, [rsp+2A0h+var_240]
0x180044bfa  xor     r14d, r14d
0x180044bfd  jmp     loc_1800450B1
0x180044c02  mov     r8, rbx; Size
0x180044c05  xor     edx, edx; Val
0x180044c07  mov     rcx, r14; void *
0x180044c0a  call    memset
0x180044c0f  lea     rcx, [r14+1BCh]; Dst
0x180044c16  mov     [r14], ebx
0x180044c19  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180044c1d  mov     dword ptr [r14+4], 55555551h
0x180044c25  mov     r8, r15; Src
0x180044c28  mov     dword ptr [r14+10h], 1
0x180044c30  mov     edx, 104h; SizeInWords
0x180044c35  mov     [r14+24h], esi
0x180044c39  call    cs:__imp_wcsncpy_s
0x180044c40  nop     dword ptr [rax+rax+00h]
0x180044c45  mov     eax, r13d
0x180044c48  lea     rsi, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180044c4f  and     eax, 1
0x180044c52  lea     rdi, aStatus; "Status"
0x180044c59  mov     [r14+20h], eax
0x180044c5d  xor     ecx, ecx
0x180044c5f  mov     rax, [rsp+2A0h+pvBuffer]
0x180044c64  mov     dword ptr [rsp+2A0h+var_25F+3], ecx
0x180044c68  cmp     [rax], ecx
0x180044c6a  jbe     loc_180044ECE
0x180044c70  mov     r12b, [rsp+2A0h+var_260]
0x180044c75  lea     r8, [r14+30h]
0x180044c79  lea     rdx, [r14+28h]
0x180044c7d  mov     rax, [rsp+2A0h+pvBuffer]
0x180044c82  mov     r9, rdx
0x180044c85  mov     r10d, ecx
0x180044c88  mov     [rsp+2A0h+var_280], r8
0x180044c8d  xor     r8d, r8d
0x180044c90  mov     [rbp+1A0h+var_218], r10
0x180044c94  mov     rcx, [rax+8]
0x180044c98  mov     rcx, [rcx+r10*8]
0x180044c9c  call    LoadProviderEx
0x180044ca1  mov     ebx, eax
0x180044ca3  mov     rax, [rsp+2A0h+pvBuffer]
0x180044ca8  mov     rcx, [rax+8]
0x180044cac  mov     rax, [rbp+1A0h+var_218]
0x180044cb0  mov     rax, [rcx+rax*8]
0x180044cb4  mov     rax, [rax+10h]
0x180044cb8  mov     qword ptr [rsp+2A0h+var_25F+7], rax
0x180044cbd  mov     [rbp+1A0h+var_208], rax
0x180044cc1  test    ebx, ebx
0x180044cc3  jns     short loc_180044D04
0x180044cc5  mov     r9d, ebx
0x180044cc8  mov     dword ptr [rsp+2A0h+var_280], 2
0x180044cd0  mov     r8d, r13d
0x180044cd3  mov     rdx, r15
0x180044cd6  mov     rcx, rax
0x180044cd9  call    _LogBCryptOpenProviderFailure
0x180044cde  mov     r9d, 85Ch
0x180044ce4  mov     r8, rsi
0x180044ce7  mov     rdx, rdi
0x180044cea  mov     ecx, ebx
0x180044cec  call    DebugTraceError
0x180044cf1  cmp     r12b, 1
0x180044cf5  jnz     loc_180044FBF
0x180044cfb  lea     rdx, [r14+28h]
0x180044cff  jmp     loc_180044E83
0x180044d04  mov     edx, 3
0x180044d09  lea     rax, [r14+30h]
0x180044d0d  lea     rcx, [rbp+1A0h+var_1E0]
0x180044d11  lea     r8d, [rdx+7Dh]
0x180044d15  movups  xmm0, xmmword ptr [rax]
0x180044d18  movups  xmm1, xmmword ptr [rax+10h]
0x180044d1c  movups  xmmword ptr [rcx], xmm0
0x180044d1f  movups  xmm0, xmmword ptr [rax+20h]
0x180044d23  movups  xmmword ptr [rcx+10h], xmm1
0x180044d27  movups  xmm1, xmmword ptr [rax+30h]
0x180044d2b  movups  xmmword ptr [rcx+20h], xmm0
0x180044d2f  movups  xmm0, xmmword ptr [rax+40h]
0x180044d33  movups  xmmword ptr [rcx+30h], xmm1
0x180044d37  movups  xmm1, xmmword ptr [rax+50h]
0x180044d3b  movups  xmmword ptr [rcx+40h], xmm0
0x180044d3f  movups  xmm0, xmmword ptr [rax+60h]
0x180044d43  movups  xmmword ptr [rcx+50h], xmm1
0x180044d47  movups  xmm1, xmmword ptr [rax+70h]
0x180044d4b  add     rax, r8
0x180044d4e  movups  xmmword ptr [rcx+60h], xmm0
0x180044d52  movups  xmmword ptr [rcx+70h], xmm1
0x180044d56  add     rcx, r8
0x180044d59  sub     rdx, 1
0x180044d5d  jnz     short loc_180044D15
0x180044d5f  mov     rax, [rax]
0x180044d62  lea     r9, [rbp+1A0h+var_1F8]
0x180044d66  mov     [rcx], rax
0x180044d69  lea     r8, [rbp+1A0h+var_220]
0x180044d6d  mov     ecx, [rsp+2A0h+var_248]
0x180044d71  lea     rax, [rbp+1A0h+var_210]
0x180044d75  mov     [rsp+2A0h+var_278], rax
0x180044d7a  lea     rdx, [rbp+1A0h+var_1E0]
0x180044d7e  lea     rax, [rbp+1A0h+var_1F0]
0x180044d82  mov     [rsp+2A0h+var_280], rax
0x180044d87  call    ValidateFunctionTable
0x180044d8c  mov     ebx, eax
0x180044d8e  mov     r8d, r13d
0x180044d91  test    eax, eax
0x180044d93  jns     short loc_180044DC8
0x180044d95  mov     rax, [rsp+2A0h+pvBuffer]
0x180044d9a  mov     r9d, ebx
0x180044d9d  mov     rdx, r15
0x180044da0  mov     dword ptr [rsp+2A0h+var_280], 3
0x180044da8  mov     rcx, [rax+8]
0x180044dac  mov     rax, [rbp+1A0h+var_218]
0x180044db0  mov     rcx, [rcx+rax*8]
0x180044db4  mov     rcx, [rcx+10h]
0x180044db8  call    _LogBCryptOpenProviderFailure
0x180044dbd  mov     r9d, 883h
0x180044dc3  jmp     loc_180044CE4
0x180044dc8  mov     r12, [rsp+2A0h+var_230]
0x180044dcd  lea     r15, [r14+18h]
0x180044dd1  mov     rax, [rbp+1A0h+var_220]
0x180044dd5  mov     rdx, r12
0x180044dd8  mov     rcx, r15
0x180044ddb  call    _guard_dispatch_icall
0x180044de0  mov     ebx, eax
0x180044de2  cmp     eax, 0C000A001h
0x180044de7  jnz     short loc_180044E16
0x180044de9  cmp     [rsp+2A0h+var_248], 2
0x180044dee  jnz     short loc_180044E1E
0x180044df0  mov     eax, r13d
0x180044df3  and     al, 68h
0x180044df5  cmp     al, 8
0x180044df7  jnz     short loc_180044E1E
0x180044df9  mov     rax, [rbp+1A0h+var_220]
0x180044dfd  mov     r8d, r13d
0x180044e00  and     r8d, 0FFFFFFF7h
0x180044e04  mov     rdx, r12
0x180044e07  mov     rcx, r15
0x180044e0a  call    _guard_dispatch_icall
0x180044e0f  or      dword ptr [r14+8], 8
0x180044e14  mov     ebx, eax
0x180044e16  test    ebx, ebx
0x180044e18  jns     loc_180044EF5
0x180044e1e  mov     rax, [rsp+2A0h+pvBuffer]
0x180044e23  mov     r9d, ebx
0x180044e26  mov     r8d, r13d
0x180044e29  mov     dword ptr [rsp+2A0h+var_280], 4
0x180044e31  mov     rdx, r12
0x180044e34  mov     r15, r12
0x180044e37  mov     rcx, [rax+8]
0x180044e3b  mov     rax, [rbp+1A0h+var_218]
0x180044e3f  mov     rcx, [rcx+rax*8]
0x180044e43  mov     rcx, [rcx+10h]
0x180044e47  call    _LogBCryptOpenProviderFailure
0x180044e4c  mov     r9d, 8C3h
0x180044e52  mov     r8, rsi
0x180044e55  mov     rdx, rdi
0x180044e58  mov     ecx, ebx
0x180044e5a  call    DebugTraceError
0x180044e5f  cmp     [rsp+2A0h+var_260], 1
0x180044e64  jnz     loc_180044FBF
0x180044e6a  mov     rcx, [r14+28h]
  ... truncated ...
```

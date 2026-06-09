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
  __int64 v19; // rdx
  NTSTATUS v20; // esi
  _QWORD *v21; // rax
  _QWORD *v22; // r14
  _QWORD *v23; // r8
  unsigned int v24; // ecx
  char v25; // r12
  _QWORD *v26; // rdx
  __int64 v27; // rax
  __int64 v28; // r9
  __int64 v29; // rdx
  _OWORD *v30; // rax
  _OWORD *v31; // rcx
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  int v39; // eax
  LPCWSTR v40; // r12
  _QWORD *v41; // r15
  NTSTATUS v42; // eax
  __int64 v43; // r15
  __int64 v44; // rcx
  __int64 v45; // r9
  int v46; // eax
  __int64 v47; // rcx
  __int64 v48; // rbx
  __int64 v49; // rdi
  __int64 v50; // rdx
  char v51; // al
  char v53; // [rsp+40h] [rbp-C0h]
  _BYTE v54[15]; // [rsp+41h] [rbp-BFh] BYREF
  PVOID pvBuffer; // [rsp+50h] [rbp-B0h] BYREF
  NTSTATUS v56; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR v57; // [rsp+60h] [rbp-A0h]
  ULONG pcbBuffer; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v59; // [rsp+6Ch] [rbp-94h] BYREF
  LPCWSTR v60; // [rsp+70h] [rbp-90h]
  int v61; // [rsp+78h] [rbp-88h] BYREF
  __int64 (__fastcall *v62)(_QWORD *, LPCWSTR, _QWORD); // [rsp+80h] [rbp-80h] BYREF
  __int64 v63; // [rsp+88h] [rbp-78h]
  __int64 (__fastcall *v64)(_QWORD, const wchar_t *, char *, __int64, int *, _DWORD); // [rsp+90h] [rbp-70h] BYREF
  __int64 v65; // [rsp+98h] [rbp-68h] BYREF
  __int64 v66; // [rsp+A0h] [rbp-60h] BYREF
  void (__fastcall *v67)(_QWORD, _QWORD); // [rsp+A8h] [rbp-58h] BYREF
  void (__fastcall *v68[2])(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD); // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v69[32]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v70; // [rsp+E0h] [rbp-20h]
  __int64 v71; // [rsp+E8h] [rbp-18h]
  __int64 *v72; // [rsp+F0h] [rbp-10h]
  __int64 v73; // [rsp+F8h] [rbp-8h]
  NTSTATUS *v74; // [rsp+100h] [rbp+0h]
  __int64 v75; // [rsp+108h] [rbp+8h]
  _BYTE *v76; // [rsp+110h] [rbp+10h]
  __int64 v77; // [rsp+118h] [rbp+18h]
  char v78[16]; // [rsp+120h] [rbp+20h] BYREF
  char v79[16]; // [rsp+130h] [rbp+30h] BYREF
  char v80[16]; // [rsp+140h] [rbp+40h] BYREF
  char v81[256]; // [rsp+150h] [rbp+50h] BYREF

  v57 = pszImplementation;
  v67 = 0;
  v4 = 0;
  *(_QWORD *)&v54[7] = 0;
  v5 = 0;
  pvBuffer = 0;
  v54[0] = 0;
  v7 = pszImplementation;
  v61 = 0;
  v8 = pszAlgId;
  pcbBuffer = 0;
  v68[0] = 0;
  v64 = 0;
  v62 = 0;
  v60 = pszAlgId;
  v66 = (__int64)phAlgorithm;
  v59 = 4;
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
  v53 = 0;
  if ( g_fLoadCNGDone )
  {
    v17 = v7;
    if ( !v7 )
    {
      v53 = 1;
      v16 = 2;
    }
  }
  else
  {
    v17 = L"Microsoft Primitive Provider";
  }
  pcbBuffer = 0;
  pvBuffer = 0;
  v18 = BCryptResolveProvidersForBcoapCached(v8, v17, v16, &pcbBuffer, (PCRYPT_PROVIDER_REFS *)&pvBuffer, (__int64)v54);
  Provider = v18;
  if ( v18 < 0 )
  {
    LogBCryptOpenProviderFailure((_DWORD)v17, (_DWORD)v8, dwFlags, v18, 1);
    DebugTraceError((unsigned int)Provider, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 2030);
LABEL_18:
    v4 = 0;
    goto LABEL_72;
  }
  v20 = ***((_DWORD ***)pvBuffer + 1);
  v56 = v20;
  if ( (unsigned int)(v20 - 1) > 7 )
  {
    LogBCryptOpenProviderFailure((_DWORD)v17, (_DWORD)v8, dwFlags, v18, 1);
    Provider = -1073741816;
    DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 2061);
    v7 = v57;
    goto LABEL_18;
  }
  v21 = (_QWORD *)MSCryptAlloc(968, v19);
  v22 = v21;
  if ( !v21 )
  {
    Provider = -1073741801;
    DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 2076);
    v4 = 0;
LABEL_23:
    v7 = v57;
    goto LABEL_72;
  }
  memset(v21, 0, 0x3C8u);
  *(_DWORD *)v22 = 968;
  *((_DWORD *)v22 + 1) = 1431655761;
  *((_DWORD *)v22 + 4) = 1;
  *((_DWORD *)v22 + 9) = v20;
  wcsncpy_s((wchar_t *)v22 + 222, 0x104u, v8, 0xFFFFFFFFFFFFFFFFuLL);
  *((_DWORD *)v22 + 8) = dwFlags & 1;
  v24 = 0;
  *(_DWORD *)&v54[3] = 0;
  if ( *(_DWORD *)pvBuffer )
  {
    v25 = v53;
    v23 = v22 + 6;
    v26 = v22 + 5;
    while ( 1 )
    {
      v63 = v24;
      Provider = LoadProviderEx(*(_QWORD *)(*((_QWORD *)pvBuffer + 1) + 8LL * v24), v26, 0, v26, v23);
      v27 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)pvBuffer + 1) + 8 * v63) + 16LL);
      *(_QWORD *)&v54[7] = v27;
      v65 = v27;
      if ( Provider >= 0 )
      {
        v29 = 3;
        v30 = v22 + 6;
        v31 = v69;
        do
        {
          v32 = v30[1];
          *v31 = *v30;
          v33 = v30[2];
          v31[1] = v32;
          v34 = v30[3];
          v31[2] = v33;
          v35 = v30[4];
          v31[3] = v34;
          v36 = v30[5];
          v31[4] = v35;
          v37 = v30[6];
          v31[5] = v36;
          v38 = v30[7];
          v30 += 8;
          v31[6] = v37;
          v31[7] = v38;
          v31 += 8;
          --v29;
        }
        while ( v29 );
        *(_QWORD *)v31 = *(_QWORD *)v30;
        v39 = ValidateFunctionTable(
                v56,
                (unsigned int)v69,
                (unsigned int)&v62,
                (unsigned int)&v67,
                (__int64)v68,
                (__int64)&v64);
        Provider = v39;
        if ( v39 >= 0 )
        {
          v40 = v60;
          v41 = v22 + 3;
          Provider = v62(v22 + 3, v60, dwFlags);
          if ( Provider == -1073700863 )
          {
            if ( v56 == 2 && (dwFlags & 0x68) == 8 )
            {
              v42 = v62(v22 + 3, v40, dwFlags & 0xFFFFFFF7);
              *((_DWORD *)v22 + 2) |= 8u;
              Provider = v42;
              goto LABEL_38;
            }
          }
          else
          {
LABEL_38:
            if ( Provider >= 0 )
            {
              v5 = v64;
              goto LABEL_46;
            }
          }
          LODWORD(v8) = (_DWORD)v40;
          LogBCryptOpenProviderFailure(
            *(_QWORD *)(*(_QWORD *)(*((_QWORD *)pvBuffer + 1) + 8 * v63) + 16LL),
            (_DWORD)v40,
            dwFlags,
            Provider,
            4);
          DebugTraceError(
            (unsigned int)Provider,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
            2243);
          if ( v53 != 1 )
            goto LABEL_60;
          UnloadProvider(v22[5]);
          v25 = 1;
          v26 = v22 + 5;
          v22[5] = 0;
          goto LABEL_41;
        }
        LogBCryptOpenProviderFailure(
          *(_QWORD *)(*(_QWORD *)(*((_QWORD *)pvBuffer + 1) + 8 * v63) + 16LL),
          (_DWORD)v8,
          dwFlags,
          v39,
          3);
        v28 = 2179;
      }
      else
      {
        LogBCryptOpenProviderFailure(v27, (_DWORD)v8, dwFlags, Provider, 2);
        v28 = 2140;
      }
      DebugTraceError((unsigned int)Provider, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v28);
      if ( v25 != 1 )
        goto LABEL_60;
      v26 = v22 + 5;
LABEL_41:
      v23 = v22 + 6;
      v24 = *(_DWORD *)&v54[3] + 1;
      *(_DWORD *)&v54[3] = v24;
      if ( v24 >= *(_DWORD *)pvBuffer )
      {
        v43 = v65;
        *(_QWORD *)&v54[7] = v65;
        *(_DWORD *)&v54[3] = v24;
        if ( Provider < 0 )
        {
          DebugTraceError(
            (unsigned int)Provider,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
            2276);
          v4 = v43;
          goto LABEL_61;
        }
        v5 = v64;
        break;
      }
    }
  }
  v41 = v22 + 3;
LABEL_46:
  if ( v56 == 2 )
  {
    if ( !v5 )
    {
      Provider = -1073741595;
      v44 = 3221225701LL;
      v45 = 2292;
      goto LABEL_58;
    }
    v41 = v22 + 3;
    v46 = v5(v22[3], L"HashBlockLength", (char *)v22 + 12, 4, &v61, 0);
    Provider = v46;
    if ( v46 < 0 )
    {
      v45 = 2304;
LABEL_57:
      v44 = (unsigned int)v46;
LABEL_58:
      DebugTraceError(v44, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v45);
      if ( v67 )
        v67(*v41, 0);
LABEL_60:
      v4 = *(_QWORD *)&v54[7];
LABEL_61:
      v47 = v22[5];
      if ( v47 )
        UnloadProvider(v47);
      MSCryptFree(v22);
      v8 = v60;
      goto LABEL_23;
    }
  }
  else if ( v56 == 3 )
  {
    if ( !v5 )
    {
      Provider = -1073741595;
      v44 = 3221225701LL;
      v45 = 2313;
      goto LABEL_58;
    }
    v41 = v22 + 3;
    v46 = v5(v22[3], L"PaddingSchemes", (char *)v22 + 440, v59, (int *)&v59, 0);
    Provider = v46;
    if ( v46 < 0 )
    {
      v45 = 2325;
      goto LABEL_57;
    }
  }
  v48 = 0;
  v49 = *(unsigned int *)&v54[3];
  if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)pvBuffer + 1) + 8LL * *(unsigned int *)&v54[3]) + 24LL) )
  {
    do
    {
      v50 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)pvBuffer + 1) + 8 * v49) + 32LL) + 8 * v48);
      v68[0](v22[3], *(_QWORD *)v50, *(_QWORD *)(v50 + 16), *(unsigned int *)(v50 + 8), 0);
      v48 = (unsigned int)(v48 + 1);
    }
    while ( (unsigned int)v48 < *(_DWORD *)(*(_QWORD *)(*((_QWORD *)pvBuffer + 1) + 8 * v49) + 24LL) );
  }
  *(_QWORD *)v66 = v22;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 3), 13, v23, v22);
  v8 = v60;
  v7 = v57;
  Provider = 0;
  v4 = *(_QWORD *)&v54[7];
LABEL_72:
  v51 = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
    v51 = GetTrustedEnvironment();
  if ( (v51 & 1) != 0
    && (unsigned int)dword_1800C95C0 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_1800C95C0, 0x400000000000LL) )
  {
    v66 = 1;
    v70 = &v66;
    v71 = 8;
    v72 = &v65;
    v65 = 0x1000000;
    v74 = &v56;
    v76 = &v54[3];
    v73 = 8;
    v56 = Provider;
    v75 = 4;
    *(_DWORD *)&v54[3] = 1;
    v77 = 4;
    tlgCreate1Sz_wchar_t(v78, g_processImageName);
    tlgCreate1Sz_wchar_t(v79, v8);
    tlgCreate1Sz_wchar_t(v80, v7);
    tlgCreate1Sz_wchar_t(v81, v4);
    tlgWriteAgg((unsigned int)&dword_1800C95C0, (unsigned int)&word_1800C07D6, 0, 10, (__int64)v69);
  }
  if ( v54[0] && pvBuffer )
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

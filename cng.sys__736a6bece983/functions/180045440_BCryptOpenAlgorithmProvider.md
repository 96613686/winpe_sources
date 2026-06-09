# BCryptOpenAlgorithmProvider

- ea: `0x180045440`
- end: `0x180045c78`
- name: `BCryptOpenAlgorithmProvider`
- size: `2104`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE *phAlgorithm, LPCWSTR pszAlgId, LPCWSTR pszImplementation, ULONG dwFlags)`
- caller_count: `6`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x180001770`
- `0x18005afcc`
- `0x180068438`
- `0x180082598`
- `0x180085568`
- `0x1800859f8`

## callees

- `0x1800010ac`
- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x180021af4`
- `0x18003a740`
- `0x18003af6c`
- `0x18003d980`
- `0x180042070`
- `0x180045440`
- `0x180045c80`
- `0x1800496dc`
- `0x18005b1ec`
- `0x18005b598`
- `0x18005b9d8`
- `0x18005bb50`
- `0x180060764`
- `0x18009f650`
- `0x18009f6d0`
- `0x18009fa80`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1800454c1`
- `ntoskrnl!KeGetCurrentIrql` at `0x1800454c1`
- `ntoskrnl!wcsncpy_s` at `0x1800456c9`
- `ntoskrnl!wcsncpy_s` at `0x1800456c9`

## string_xrefs

- `0x1800455d1`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180045627`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180045665`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800456d8`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180045b2e`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
  __int64 v20; // r8
  __int64 v21; // r9
  NTSTATUS v22; // esi
  _QWORD *v23; // rax
  _QWORD *v24; // r14
  _QWORD *v25; // r8
  unsigned int v26; // ecx
  char v27; // r12
  _QWORD *v28; // rdx
  __int64 v29; // rax
  __int64 v30; // r9
  __int64 v31; // rdx
  _OWORD *v32; // rax
  _OWORD *v33; // rcx
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  int v41; // eax
  LPCWSTR v42; // r12
  _QWORD *v43; // r15
  NTSTATUS v44; // eax
  __int64 v45; // r15
  __int64 v46; // rcx
  __int64 v47; // r9
  int v48; // eax
  __int64 v49; // rcx
  __int64 v50; // rbx
  __int64 v51; // rdi
  __int64 v52; // rdx
  char v53; // al
  char v55; // [rsp+40h] [rbp-C0h]
  _BYTE v56[15]; // [rsp+41h] [rbp-BFh] BYREF
  PVOID pvBuffer; // [rsp+50h] [rbp-B0h] BYREF
  NTSTATUS v58; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR v59; // [rsp+60h] [rbp-A0h]
  ULONG pcbBuffer; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v61; // [rsp+6Ch] [rbp-94h] BYREF
  LPCWSTR v62; // [rsp+70h] [rbp-90h]
  int v63; // [rsp+78h] [rbp-88h] BYREF
  __int64 (__fastcall *v64)(_QWORD *, LPCWSTR, _QWORD); // [rsp+80h] [rbp-80h] BYREF
  __int64 v65; // [rsp+88h] [rbp-78h]
  __int64 (__fastcall *v66)(_QWORD, const wchar_t *, char *, __int64, int *, _DWORD); // [rsp+90h] [rbp-70h] BYREF
  __int64 v67; // [rsp+98h] [rbp-68h] BYREF
  __int64 v68; // [rsp+A0h] [rbp-60h] BYREF
  void (__fastcall *v69)(_QWORD, _QWORD); // [rsp+A8h] [rbp-58h] BYREF
  void (__fastcall *v70[2])(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD); // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v71[32]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v72; // [rsp+E0h] [rbp-20h]
  __int64 v73; // [rsp+E8h] [rbp-18h]
  __int64 *v74; // [rsp+F0h] [rbp-10h]
  __int64 v75; // [rsp+F8h] [rbp-8h]
  NTSTATUS *v76; // [rsp+100h] [rbp+0h]
  __int64 v77; // [rsp+108h] [rbp+8h]
  _BYTE *v78; // [rsp+110h] [rbp+10h]
  __int64 v79; // [rsp+118h] [rbp+18h]
  char v80[16]; // [rsp+120h] [rbp+20h] BYREF
  char v81[16]; // [rsp+130h] [rbp+30h] BYREF
  char v82[16]; // [rsp+140h] [rbp+40h] BYREF
  char v83[256]; // [rsp+150h] [rbp+50h] BYREF

  v59 = pszImplementation;
  v69 = 0;
  v4 = 0;
  *(_QWORD *)&v56[7] = 0;
  v5 = 0;
  pvBuffer = 0;
  v56[0] = 0;
  v7 = pszImplementation;
  v63 = 0;
  v8 = pszAlgId;
  pcbBuffer = 0;
  v70[0] = 0;
  v66 = 0;
  v64 = 0;
  v62 = pszAlgId;
  v68 = (__int64)phAlgorithm;
  v61 = 4;
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
  v55 = 0;
  if ( g_fLoadCNGDone )
  {
    v17 = v7;
    if ( !v7 )
    {
      v55 = 1;
      v16 = 2;
    }
  }
  else
  {
    v17 = L"Microsoft Primitive Provider";
  }
  pcbBuffer = 0;
  pvBuffer = 0;
  v18 = BCryptResolveProvidersForBcoapCached(v8, v17, v16, &pcbBuffer, (PCRYPT_PROVIDER_REFS *)&pvBuffer, (__int64)v56);
  Provider = v18;
  if ( v18 < 0 )
  {
    LogBCryptOpenProviderFailure((_DWORD)v17, (_DWORD)v8, dwFlags, v18, 1);
    DebugTraceError((unsigned int)Provider, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 2030);
LABEL_18:
    v4 = 0;
    goto LABEL_72;
  }
  v22 = ***((_DWORD ***)pvBuffer + 1);
  v58 = v22;
  if ( (unsigned int)(v22 - 1) > 7 )
  {
    LogBCryptOpenProviderFailure((_DWORD)v17, (_DWORD)v8, dwFlags, v18, 1);
    Provider = -1073741816;
    DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 2061);
    v7 = v59;
    goto LABEL_18;
  }
  v23 = (_QWORD *)MSCryptAlloc(968, v19, v20, v21);
  v24 = v23;
  if ( !v23 )
  {
    Provider = -1073741801;
    DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 2076);
    v4 = 0;
LABEL_23:
    v7 = v59;
    goto LABEL_72;
  }
  memset(v23, 0, 0x3C8u);
  *(_DWORD *)v24 = 968;
  *((_DWORD *)v24 + 1) = 1431655761;
  *((_DWORD *)v24 + 4) = 1;
  *((_DWORD *)v24 + 9) = v22;
  wcsncpy_s((wchar_t *)v24 + 222, 0x104u, v8, 0xFFFFFFFFFFFFFFFFuLL);
  *((_DWORD *)v24 + 8) = dwFlags & 1;
  v26 = 0;
  *(_DWORD *)&v56[3] = 0;
  if ( *(_DWORD *)pvBuffer )
  {
    v27 = v55;
    v25 = v24 + 6;
    v28 = v24 + 5;
    while ( 1 )
    {
      v65 = v26;
      Provider = LoadProviderEx(*(_QWORD *)(*((_QWORD *)pvBuffer + 1) + 8LL * v26), v28, 0, v28, v25);
      v29 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)pvBuffer + 1) + 8 * v65) + 16LL);
      *(_QWORD *)&v56[7] = v29;
      v67 = v29;
      if ( Provider >= 0 )
      {
        v31 = 3;
        v32 = v24 + 6;
        v33 = v71;
        do
        {
          v34 = v32[1];
          *v33 = *v32;
          v35 = v32[2];
          v33[1] = v34;
          v36 = v32[3];
          v33[2] = v35;
          v37 = v32[4];
          v33[3] = v36;
          v38 = v32[5];
          v33[4] = v37;
          v39 = v32[6];
          v33[5] = v38;
          v40 = v32[7];
          v32 += 8;
          v33[6] = v39;
          v33[7] = v40;
          v33 += 8;
          --v31;
        }
        while ( v31 );
        *(_QWORD *)v33 = *(_QWORD *)v32;
        v41 = ValidateFunctionTable(
                v58,
                (unsigned int)v71,
                (unsigned int)&v64,
                (unsigned int)&v69,
                (__int64)v70,
                (__int64)&v66);
        Provider = v41;
        if ( v41 >= 0 )
        {
          v42 = v62;
          v43 = v24 + 3;
          Provider = v64(v24 + 3, v62, dwFlags);
          if ( Provider == -1073700863 )
          {
            if ( v58 == 2 && (dwFlags & 0x68) == 8 )
            {
              v44 = v64(v24 + 3, v42, dwFlags & 0xFFFFFFF7);
              *((_DWORD *)v24 + 2) |= 8u;
              Provider = v44;
              goto LABEL_38;
            }
          }
          else
          {
LABEL_38:
            if ( Provider >= 0 )
            {
              v5 = v66;
              goto LABEL_46;
            }
          }
          LODWORD(v8) = (_DWORD)v42;
          LogBCryptOpenProviderFailure(
            *(_QWORD *)(*(_QWORD *)(*((_QWORD *)pvBuffer + 1) + 8 * v65) + 16LL),
            (_DWORD)v42,
            dwFlags,
            Provider,
            4);
          DebugTraceError(
            (unsigned int)Provider,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
            2243);
          if ( v55 != 1 )
            goto LABEL_60;
          UnloadProvider(v24[5]);
          v27 = 1;
          v28 = v24 + 5;
          v24[5] = 0;
          goto LABEL_41;
        }
        LogBCryptOpenProviderFailure(
          *(_QWORD *)(*(_QWORD *)(*((_QWORD *)pvBuffer + 1) + 8 * v65) + 16LL),
          (_DWORD)v8,
          dwFlags,
          v41,
          3);
        v30 = 2179;
      }
      else
      {
        LogBCryptOpenProviderFailure(v29, (_DWORD)v8, dwFlags, Provider, 2);
        v30 = 2140;
      }
      DebugTraceError((unsigned int)Provider, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v30);
      if ( v27 != 1 )
        goto LABEL_60;
      v28 = v24 + 5;
LABEL_41:
      v25 = v24 + 6;
      v26 = *(_DWORD *)&v56[3] + 1;
      *(_DWORD *)&v56[3] = v26;
      if ( v26 >= *(_DWORD *)pvBuffer )
      {
        v45 = v67;
        *(_QWORD *)&v56[7] = v67;
        *(_DWORD *)&v56[3] = v26;
        if ( Provider < 0 )
        {
          DebugTraceError(
            (unsigned int)Provider,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
            2276);
          v4 = v45;
          goto LABEL_61;
        }
        v5 = v66;
        break;
      }
    }
  }
  v43 = v24 + 3;
LABEL_46:
  if ( v58 == 2 )
  {
    if ( !v5 )
    {
      Provider = -1073741595;
      v46 = 3221225701LL;
      v47 = 2292;
      goto LABEL_58;
    }
    v43 = v24 + 3;
    v48 = v5(v24[3], L"HashBlockLength", (char *)v24 + 12, 4, &v63, 0);
    Provider = v48;
    if ( v48 < 0 )
    {
      v47 = 2304;
LABEL_57:
      v46 = (unsigned int)v48;
LABEL_58:
      DebugTraceError(v46, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v47);
      if ( v69 )
        v69(*v43, 0);
LABEL_60:
      v4 = *(_QWORD *)&v56[7];
LABEL_61:
      v49 = v24[5];
      if ( v49 )
        UnloadProvider(v49);
      MSCryptFree(v24);
      v8 = v62;
      goto LABEL_23;
    }
  }
  else if ( v58 == 3 )
  {
    if ( !v5 )
    {
      Provider = -1073741595;
      v46 = 3221225701LL;
      v47 = 2313;
      goto LABEL_58;
    }
    v43 = v24 + 3;
    v48 = v5(v24[3], L"PaddingSchemes", (char *)v24 + 440, v61, (int *)&v61, 0);
    Provider = v48;
    if ( v48 < 0 )
    {
      v47 = 2325;
      goto LABEL_57;
    }
  }
  v50 = 0;
  v51 = *(unsigned int *)&v56[3];
  if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)pvBuffer + 1) + 8LL * *(unsigned int *)&v56[3]) + 24LL) )
  {
    do
    {
      v52 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)pvBuffer + 1) + 8 * v51) + 32LL) + 8 * v50);
      v70[0](v24[3], *(_QWORD *)v52, *(_QWORD *)(v52 + 16), *(unsigned int *)(v52 + 8), 0);
      v50 = (unsigned int)(v50 + 1);
    }
    while ( (unsigned int)v50 < *(_DWORD *)(*(_QWORD *)(*((_QWORD *)pvBuffer + 1) + 8 * v51) + 24LL) );
  }
  *(_QWORD *)v68 = v24;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 3), 13, v25, v24);
  v8 = v62;
  v7 = v59;
  Provider = 0;
  v4 = *(_QWORD *)&v56[7];
LABEL_72:
  v53 = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
    v53 = GetTrustedEnvironment();
  if ( (v53 & 1) != 0
    && (unsigned int)dword_1800CB5C0 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_1800CB5C0, 0x400000000000LL) )
  {
    v68 = 1;
    v72 = &v68;
    v73 = 8;
    v74 = &v67;
    v67 = 0x1000000;
    v76 = &v58;
    v78 = &v56[3];
    v75 = 8;
    v58 = Provider;
    v77 = 4;
    *(_DWORD *)&v56[3] = 1;
    v79 = 4;
    tlgCreate1Sz_wchar_t(v80, g_processImageName);
    tlgCreate1Sz_wchar_t(v81, v8);
    tlgCreate1Sz_wchar_t(v82, v7);
    tlgCreate1Sz_wchar_t(v83, v4);
    tlgWriteAgg((unsigned int)&dword_1800CB5C0, (unsigned int)&word_1800C2DD6, 0, 10, (__int64)v71);
  }
  if ( v56[0] && pvBuffer )
    BCryptFreeBuffer(pvBuffer);
  return Provider;
}

```

## disassembly

```asm
0x180045440  push    rbp
0x180045442  push    rbx
0x180045443  push    rsi
0x180045444  push    rdi
0x180045445  push    r12
0x180045447  push    r13
0x180045449  push    r14
0x18004544b  push    r15
0x18004544d  lea     rbp, [rsp-168h]
0x180045455  sub     rsp, 268h
0x18004545c  mov     rax, cs:__security_cookie
0x180045463  xor     rax, rsp
0x180045466  mov     [rbp+1A0h+var_50], rax
0x18004546d  xor     r14d, r14d
0x180045470  mov     [rsp+2A0h+var_240], r8
0x180045475  mov     [rbp+1A0h+var_1F8], r14
0x180045479  mov     edi, r14d
0x18004547c  mov     qword ptr [rsp+2A0h+var_25F+7], r14
0x180045481  mov     r12d, r14d
0x180045484  mov     [rsp+2A0h+pvBuffer], r14
0x180045489  mov     r13d, r9d
0x18004548c  mov     [rsp+2A0h+var_25F], r14b
0x180045491  mov     rsi, r8
0x180045494  mov     [rsp+2A0h+var_228], r14d
0x180045499  mov     r15, rdx
0x18004549c  mov     [rsp+2A0h+pcbBuffer], r14d
0x1800454a1  mov     rbx, rcx
0x1800454a4  mov     [rbp+1A0h+var_1F0], r14
0x1800454a8  mov     [rbp+1A0h+var_210], r14
0x1800454ac  mov     [rbp+1A0h+var_220], r14
0x1800454b0  mov     [rsp+2A0h+var_230], rdx
0x1800454b5  mov     [rbp+1A0h+var_200], rcx
0x1800454b9  mov     [rsp+2A0h+var_234], 4
0x1800454c1  call    cs:__imp_KeGetCurrentIrql
0x1800454c8  nop     dword ptr [rax+rax+00h]
0x1800454cd  cmp     al, 2
0x1800454cf  jb      short loc_1800454E6
0x1800454d1  mov     ebx, 0C00000BBh
0x1800454d6  mov     r9d, 793h
0x1800454dc  mov     ecx, 0C00000BBh
0x1800454e1  jmp     loc_180045B2E
0x1800454e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800454ed  lea     rax, WPP_GLOBAL_Control
0x1800454f4  cmp     rcx, rax
0x1800454f7  jz      short loc_180045516
0x1800454f9  mov     eax, [rcx+2Ch]
0x1800454fc  test    al, 4
0x1800454fe  jz      short loc_180045516
0x180045500  mov     rcx, [rcx+18h]
0x180045504  mov     r9, r15
0x180045507  mov     dword ptr [rsp+2A0h+var_278], r13d
0x18004550c  mov     [rsp+2A0h+var_280], rsi
0x180045511  call    WPP_SF_SSD
0x180045516  test    rbx, rbx
0x180045519  jz      loc_180045B1E
0x18004551f  test    r15, r15
0x180045522  jz      loc_180045B1E
0x180045528  mov     eax, cs:g_TrustedEnvironment
0x18004552e  test    eax, eax
0x180045530  jnz     short loc_180045537
0x180045532  call    GetTrustedEnvironment
0x180045537  test    al, 1
0x180045539  jnz     short loc_180045553
0x18004553b  mov     r9d, r13d
0x18004553e  mov     r8, rsi
0x180045541  mov     rdx, r15
0x180045544  mov     rcx, rbx
0x180045547  call    VsmOpenAlgorithmProvider
0x18004554c  mov     ebx, eax
0x18004554e  jmp     loc_180045B41
0x180045553  cmp     cs:g_fLoadCNGDone, r14d
0x18004555a  mov     r8d, r14d
0x18004555d  mov     [rsp+2A0h+var_260], r14b
0x180045562  jnz     short loc_18004556D
0x180045564  lea     rdi, pszProvider; "Microsoft Primitive Provider"
0x18004556b  jmp     short loc_18004557E
0x18004556d  mov     rdi, rsi
0x180045570  test    rsi, rsi
0x180045573  jnz     short loc_18004557E
0x180045575  mov     [rsp+2A0h+var_260], 1
0x18004557a  lea     r8d, [rsi+2]; dwFlags
0x18004557e  lea     rax, [rsp+2A0h+var_25F]
0x180045583  mov     [rsp+2A0h+pcbBuffer], r14d
0x180045588  mov     [rsp+2A0h+var_278], rax; __int64
0x18004558d  lea     r9, [rsp+2A0h+pcbBuffer]; pcbBuffer
0x180045592  lea     rax, [rsp+2A0h+pvBuffer]
0x180045597  mov     [rsp+2A0h+pvBuffer], r14
0x18004559c  mov     rdx, rdi; pszProvider
0x18004559f  mov     [rsp+2A0h+var_280], rax; PCRYPT_PROVIDER_REFS *
0x1800455a4  mov     rcx, r15; pszSrc
0x1800455a7  call    BCryptResolveProvidersForBcoapCached
0x1800455ac  mov     ebx, eax
0x1800455ae  test    eax, eax
0x1800455b0  jns     short loc_1800455EE
0x1800455b2  mov     r9d, eax
0x1800455b5  mov     dword ptr [rsp+2A0h+var_280], 1
0x1800455bd  mov     r8d, r13d
0x1800455c0  mov     rdx, r15
0x1800455c3  mov     rcx, rdi
0x1800455c6  call    _LogBCryptOpenProviderFailure
0x1800455cb  mov     r9d, 7EEh
0x1800455d1  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800455d8  lea     rdx, aStatus; "Status"
0x1800455df  mov     ecx, ebx
0x1800455e1  call    DebugTraceError
0x1800455e6  mov     rdi, r12
0x1800455e9  jmp     loc_180045B41
0x1800455ee  mov     rax, [rsp+2A0h+pvBuffer]
0x1800455f3  mov     rcx, [rax+8]
0x1800455f7  mov     rax, [rcx]
0x1800455fa  mov     esi, [rax]
0x1800455fc  mov     [rsp+2A0h+var_248], esi
0x180045600  lea     eax, [rsi-1]
0x180045603  cmp     eax, 7
0x180045606  jbe     short loc_18004564B
0x180045608  mov     r9d, ebx
0x18004560b  mov     dword ptr [rsp+2A0h+var_280], 1
0x180045613  mov     r8d, r13d
0x180045616  mov     rdx, r15
0x180045619  mov     rcx, rdi
0x18004561c  call    _LogBCryptOpenProviderFailure
0x180045621  mov     r9d, 80Dh
0x180045627  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004562e  lea     rdx, aStatus; "Status"
0x180045635  mov     ecx, 0C0000008h
0x18004563a  mov     ebx, 0C0000008h
0x18004563f  call    DebugTraceError
0x180045644  mov     rsi, [rsp+2A0h+var_240]
0x180045649  jmp     short loc_1800455E6
0x18004564b  mov     ebx, 3C8h
0x180045650  mov     ecx, ebx
0x180045652  call    MSCryptAlloc
0x180045657  mov     r14, rax
0x18004565a  test    rax, rax
0x18004565d  jnz     short loc_180045692
0x18004565f  mov     r9d, 81Ch
0x180045665  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004566c  lea     rdx, aStatus; "Status"
0x180045673  mov     ecx, 0C0000017h
0x180045678  mov     ebx, 0C0000017h
0x18004567d  call    DebugTraceError
0x180045682  mov     rdi, r12
0x180045685  mov     rsi, [rsp+2A0h+var_240]
0x18004568a  xor     r14d, r14d
0x18004568d  jmp     loc_180045B41
0x180045692  mov     r8, rbx; Size
0x180045695  xor     edx, edx; Val
0x180045697  mov     rcx, r14; void *
0x18004569a  call    memset
0x18004569f  lea     rcx, [r14+1BCh]; Dst
0x1800456a6  mov     [r14], ebx
0x1800456a9  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800456ad  mov     dword ptr [r14+4], 55555551h
0x1800456b5  mov     r8, r15; Src
0x1800456b8  mov     dword ptr [r14+10h], 1
0x1800456c0  mov     edx, 104h; SizeInWords
0x1800456c5  mov     [r14+24h], esi
0x1800456c9  call    cs:__imp_wcsncpy_s
0x1800456d0  nop     dword ptr [rax+rax+00h]
0x1800456d5  mov     eax, r13d
0x1800456d8  lea     rsi, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800456df  and     eax, 1
0x1800456e2  lea     rdi, aStatus; "Status"
0x1800456e9  mov     [r14+20h], eax
0x1800456ed  xor     ecx, ecx
0x1800456ef  mov     rax, [rsp+2A0h+pvBuffer]
0x1800456f4  mov     dword ptr [rsp+2A0h+var_25F+3], ecx
0x1800456f8  cmp     [rax], ecx
0x1800456fa  jbe     loc_18004595E
0x180045700  mov     r12b, [rsp+2A0h+var_260]
0x180045705  lea     r8, [r14+30h]
0x180045709  lea     rdx, [r14+28h]
0x18004570d  mov     rax, [rsp+2A0h+pvBuffer]
0x180045712  mov     r9, rdx
0x180045715  mov     r10d, ecx
0x180045718  mov     [rsp+2A0h+var_280], r8
0x18004571d  xor     r8d, r8d
0x180045720  mov     [rbp+1A0h+var_218], r10
0x180045724  mov     rcx, [rax+8]
0x180045728  mov     rcx, [rcx+r10*8]
0x18004572c  call    LoadProviderEx
0x180045731  mov     ebx, eax
0x180045733  mov     rax, [rsp+2A0h+pvBuffer]
0x180045738  mov     rcx, [rax+8]
0x18004573c  mov     rax, [rbp+1A0h+var_218]
0x180045740  mov     rax, [rcx+rax*8]
0x180045744  mov     rax, [rax+10h]
0x180045748  mov     qword ptr [rsp+2A0h+var_25F+7], rax
0x18004574d  mov     [rbp+1A0h+var_208], rax
0x180045751  test    ebx, ebx
0x180045753  jns     short loc_180045794
0x180045755  mov     r9d, ebx
0x180045758  mov     dword ptr [rsp+2A0h+var_280], 2
0x180045760  mov     r8d, r13d
0x180045763  mov     rdx, r15
0x180045766  mov     rcx, rax
0x180045769  call    _LogBCryptOpenProviderFailure
0x18004576e  mov     r9d, 85Ch
0x180045774  mov     r8, rsi
0x180045777  mov     rdx, rdi
0x18004577a  mov     ecx, ebx
0x18004577c  call    DebugTraceError
0x180045781  cmp     r12b, 1
0x180045785  jnz     loc_180045A4F
0x18004578b  lea     rdx, [r14+28h]
0x18004578f  jmp     loc_180045913
0x180045794  mov     edx, 3
0x180045799  lea     rax, [r14+30h]
0x18004579d  lea     rcx, [rbp+1A0h+var_1E0]
0x1800457a1  lea     r8d, [rdx+7Dh]
0x1800457a5  movups  xmm0, xmmword ptr [rax]
0x1800457a8  movups  xmm1, xmmword ptr [rax+10h]
0x1800457ac  movups  xmmword ptr [rcx], xmm0
0x1800457af  movups  xmm0, xmmword ptr [rax+20h]
0x1800457b3  movups  xmmword ptr [rcx+10h], xmm1
0x1800457b7  movups  xmm1, xmmword ptr [rax+30h]
0x1800457bb  movups  xmmword ptr [rcx+20h], xmm0
0x1800457bf  movups  xmm0, xmmword ptr [rax+40h]
0x1800457c3  movups  xmmword ptr [rcx+30h], xmm1
0x1800457c7  movups  xmm1, xmmword ptr [rax+50h]
0x1800457cb  movups  xmmword ptr [rcx+40h], xmm0
0x1800457cf  movups  xmm0, xmmword ptr [rax+60h]
0x1800457d3  movups  xmmword ptr [rcx+50h], xmm1
0x1800457d7  movups  xmm1, xmmword ptr [rax+70h]
0x1800457db  add     rax, r8
0x1800457de  movups  xmmword ptr [rcx+60h], xmm0
0x1800457e2  movups  xmmword ptr [rcx+70h], xmm1
0x1800457e6  add     rcx, r8
0x1800457e9  sub     rdx, 1
0x1800457ed  jnz     short loc_1800457A5
0x1800457ef  mov     rax, [rax]
0x1800457f2  lea     r9, [rbp+1A0h+var_1F8]
0x1800457f6  mov     [rcx], rax
0x1800457f9  lea     r8, [rbp+1A0h+var_220]
0x1800457fd  mov     ecx, [rsp+2A0h+var_248]
0x180045801  lea     rax, [rbp+1A0h+var_210]
0x180045805  mov     [rsp+2A0h+var_278], rax
0x18004580a  lea     rdx, [rbp+1A0h+var_1E0]
0x18004580e  lea     rax, [rbp+1A0h+var_1F0]
0x180045812  mov     [rsp+2A0h+var_280], rax
0x180045817  call    ValidateFunctionTable
0x18004581c  mov     ebx, eax
0x18004581e  mov     r8d, r13d
0x180045821  test    eax, eax
0x180045823  jns     short loc_180045858
0x180045825  mov     rax, [rsp+2A0h+pvBuffer]
0x18004582a  mov     r9d, ebx
0x18004582d  mov     rdx, r15
0x180045830  mov     dword ptr [rsp+2A0h+var_280], 3
0x180045838  mov     rcx, [rax+8]
0x18004583c  mov     rax, [rbp+1A0h+var_218]
0x180045840  mov     rcx, [rcx+rax*8]
0x180045844  mov     rcx, [rcx+10h]
0x180045848  call    _LogBCryptOpenProviderFailure
0x18004584d  mov     r9d, 883h
0x180045853  jmp     loc_180045774
0x180045858  mov     r12, [rsp+2A0h+var_230]
0x18004585d  lea     r15, [r14+18h]
0x180045861  mov     rax, [rbp+1A0h+var_220]
0x180045865  mov     rdx, r12
0x180045868  mov     rcx, r15
0x18004586b  call    _guard_dispatch_icall
0x180045870  mov     ebx, eax
0x180045872  cmp     eax, 0C000A001h
0x180045877  jnz     short loc_1800458A6
0x180045879  cmp     [rsp+2A0h+var_248], 2
0x18004587e  jnz     short loc_1800458AE
0x180045880  mov     eax, r13d
0x180045883  and     al, 68h
0x180045885  cmp     al, 8
0x180045887  jnz     short loc_1800458AE
0x180045889  mov     rax, [rbp+1A0h+var_220]
0x18004588d  mov     r8d, r13d
0x180045890  and     r8d, 0FFFFFFF7h
0x180045894  mov     rdx, r12
0x180045897  mov     rcx, r15
0x18004589a  call    _guard_dispatch_icall
0x18004589f  or      dword ptr [r14+8], 8
0x1800458a4  mov     ebx, eax
0x1800458a6  test    ebx, ebx
0x1800458a8  jns     loc_180045985
0x1800458ae  mov     rax, [rsp+2A0h+pvBuffer]
0x1800458b3  mov     r9d, ebx
0x1800458b6  mov     r8d, r13d
0x1800458b9  mov     dword ptr [rsp+2A0h+var_280], 4
0x1800458c1  mov     rdx, r12
0x1800458c4  mov     r15, r12
0x1800458c7  mov     rcx, [rax+8]
0x1800458cb  mov     rax, [rbp+1A0h+var_218]
0x1800458cf  mov     rcx, [rcx+rax*8]
0x1800458d3  mov     rcx, [rcx+10h]
0x1800458d7  call    _LogBCryptOpenProviderFailure
0x1800458dc  mov     r9d, 8C3h
0x1800458e2  mov     r8, rsi
0x1800458e5  mov     rdx, rdi
0x1800458e8  mov     ecx, ebx
0x1800458ea  call    DebugTraceError
0x1800458ef  cmp     [rsp+2A0h+var_260], 1
0x1800458f4  jnz     loc_180045A4F
0x1800458fa  mov     rcx, [r14+28h]
  ... truncated ...
```

# BCryptOpenAlgorithmProvider

- ea: `0x18004eaa0`
- end: `0x18004f2d8`
- name: `BCryptOpenAlgorithmProvider`
- size: `2104`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE *phAlgorithm, LPCWSTR pszAlgId, LPCWSTR pszImplementation, ULONG dwFlags)`
- caller_count: `6`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x18000b898`
- `0x1800648ac`
- `0x180071bd8`
- `0x18008b798`
- `0x18008e740`
- `0x18008ebd0`

## callees

- `0x18000b1d8`
- `0x18000e090`
- `0x180010590`
- `0x18001155c`
- `0x18002eb64`
- `0x180043cd0`
- `0x1800444fc`
- `0x180046db4`
- `0x18004b4c0`
- `0x18004eaa0`
- `0x18004f2e0`
- `0x180052d3c`
- `0x180064acc`
- `0x180064e78`
- `0x1800652b8`
- `0x180065430`
- `0x18006a044`
- `0x1800a4260`
- `0x1800a4300`
- `0x1800a4380`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x18004eb21`
- `ntoskrnl!KeGetCurrentIrql` at `0x18004eb21`
- `ntoskrnl!wcsncpy_s` at `0x18004ed29`
- `ntoskrnl!wcsncpy_s` at `0x18004ed29`

## string_xrefs

- `0x18004ec31`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18004ec87`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18004ecc5`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18004ed38`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18004f18e`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
    && (unsigned int)dword_1800D15C0 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_1800D15C0, 0x400000000000LL) )
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
    tlgWriteAgg((unsigned int)&dword_1800D15C0, (unsigned int)&word_1800C9056, 0, 10, (__int64)v69);
  }
  if ( v54[0] && pvBuffer )
    BCryptFreeBuffer(pvBuffer);
  return Provider;
}

```

## disassembly

```asm
0x18004eaa0  push    rbp
0x18004eaa2  push    rbx
0x18004eaa3  push    rsi
0x18004eaa4  push    rdi
0x18004eaa5  push    r12
0x18004eaa7  push    r13
0x18004eaa9  push    r14
0x18004eaab  push    r15
0x18004eaad  lea     rbp, [rsp-168h]
0x18004eab5  sub     rsp, 268h
0x18004eabc  mov     rax, cs:__security_cookie
0x18004eac3  xor     rax, rsp
0x18004eac6  mov     [rbp+1A0h+var_50], rax
0x18004eacd  xor     r14d, r14d
0x18004ead0  mov     [rsp+2A0h+var_240], r8
0x18004ead5  mov     [rbp+1A0h+var_1F8], r14
0x18004ead9  mov     edi, r14d
0x18004eadc  mov     qword ptr [rsp+2A0h+var_25F+7], r14
0x18004eae1  mov     r12d, r14d
0x18004eae4  mov     [rsp+2A0h+pvBuffer], r14
0x18004eae9  mov     r13d, r9d
0x18004eaec  mov     [rsp+2A0h+var_25F], r14b
0x18004eaf1  mov     rsi, r8
0x18004eaf4  mov     [rsp+2A0h+var_228], r14d
0x18004eaf9  mov     r15, rdx
0x18004eafc  mov     [rsp+2A0h+pcbBuffer], r14d
0x18004eb01  mov     rbx, rcx
0x18004eb04  mov     [rbp+1A0h+var_1F0], r14
0x18004eb08  mov     [rbp+1A0h+var_210], r14
0x18004eb0c  mov     [rbp+1A0h+var_220], r14
0x18004eb10  mov     [rsp+2A0h+var_230], rdx
0x18004eb15  mov     [rbp+1A0h+var_200], rcx
0x18004eb19  mov     [rsp+2A0h+var_234], 4
0x18004eb21  call    cs:__imp_KeGetCurrentIrql
0x18004eb28  nop     dword ptr [rax+rax+00h]
0x18004eb2d  cmp     al, 2
0x18004eb2f  jb      short loc_18004EB46
0x18004eb31  mov     ebx, 0C00000BBh
0x18004eb36  mov     r9d, 793h
0x18004eb3c  mov     ecx, 0C00000BBh
0x18004eb41  jmp     loc_18004F18E
0x18004eb46  mov     rcx, cs:WPP_GLOBAL_Control
0x18004eb4d  lea     rax, WPP_GLOBAL_Control
0x18004eb54  cmp     rcx, rax
0x18004eb57  jz      short loc_18004EB76
0x18004eb59  mov     eax, [rcx+2Ch]
0x18004eb5c  test    al, 4
0x18004eb5e  jz      short loc_18004EB76
0x18004eb60  mov     rcx, [rcx+18h]
0x18004eb64  mov     r9, r15
0x18004eb67  mov     dword ptr [rsp+2A0h+var_278], r13d
0x18004eb6c  mov     [rsp+2A0h+var_280], rsi
0x18004eb71  call    WPP_SF_SSD
0x18004eb76  test    rbx, rbx
0x18004eb79  jz      loc_18004F17E
0x18004eb7f  test    r15, r15
0x18004eb82  jz      loc_18004F17E
0x18004eb88  mov     eax, cs:g_TrustedEnvironment
0x18004eb8e  test    eax, eax
0x18004eb90  jnz     short loc_18004EB97
0x18004eb92  call    GetTrustedEnvironment
0x18004eb97  test    al, 1
0x18004eb99  jnz     short loc_18004EBB3
0x18004eb9b  mov     r9d, r13d
0x18004eb9e  mov     r8, rsi
0x18004eba1  mov     rdx, r15
0x18004eba4  mov     rcx, rbx
0x18004eba7  call    VsmOpenAlgorithmProvider
0x18004ebac  mov     ebx, eax
0x18004ebae  jmp     loc_18004F1A1
0x18004ebb3  cmp     cs:g_fLoadCNGDone, r14d
0x18004ebba  mov     r8d, r14d
0x18004ebbd  mov     [rsp+2A0h+var_260], r14b
0x18004ebc2  jnz     short loc_18004EBCD
0x18004ebc4  lea     rdi, pszProvider; "Microsoft Primitive Provider"
0x18004ebcb  jmp     short loc_18004EBDE
0x18004ebcd  mov     rdi, rsi
0x18004ebd0  test    rsi, rsi
0x18004ebd3  jnz     short loc_18004EBDE
0x18004ebd5  mov     [rsp+2A0h+var_260], 1
0x18004ebda  lea     r8d, [rsi+2]; dwFlags
0x18004ebde  lea     rax, [rsp+2A0h+var_25F]
0x18004ebe3  mov     [rsp+2A0h+pcbBuffer], r14d
0x18004ebe8  mov     [rsp+2A0h+var_278], rax; __int64
0x18004ebed  lea     r9, [rsp+2A0h+pcbBuffer]; pcbBuffer
0x18004ebf2  lea     rax, [rsp+2A0h+pvBuffer]
0x18004ebf7  mov     [rsp+2A0h+pvBuffer], r14
0x18004ebfc  mov     rdx, rdi; pszProvider
0x18004ebff  mov     [rsp+2A0h+var_280], rax; PCRYPT_PROVIDER_REFS *
0x18004ec04  mov     rcx, r15; pszSrc
0x18004ec07  call    BCryptResolveProvidersForBcoapCached
0x18004ec0c  mov     ebx, eax
0x18004ec0e  test    eax, eax
0x18004ec10  jns     short loc_18004EC4E
0x18004ec12  mov     r9d, eax
0x18004ec15  mov     dword ptr [rsp+2A0h+var_280], 1
0x18004ec1d  mov     r8d, r13d
0x18004ec20  mov     rdx, r15
0x18004ec23  mov     rcx, rdi
0x18004ec26  call    _LogBCryptOpenProviderFailure
0x18004ec2b  mov     r9d, 7EEh
0x18004ec31  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004ec38  lea     rdx, aStatus; "Status"
0x18004ec3f  mov     ecx, ebx
0x18004ec41  call    DebugTraceError
0x18004ec46  mov     rdi, r12
0x18004ec49  jmp     loc_18004F1A1
0x18004ec4e  mov     rax, [rsp+2A0h+pvBuffer]
0x18004ec53  mov     rcx, [rax+8]
0x18004ec57  mov     rax, [rcx]
0x18004ec5a  mov     esi, [rax]
0x18004ec5c  mov     [rsp+2A0h+var_248], esi
0x18004ec60  lea     eax, [rsi-1]
0x18004ec63  cmp     eax, 7
0x18004ec66  jbe     short loc_18004ECAB
0x18004ec68  mov     r9d, ebx
0x18004ec6b  mov     dword ptr [rsp+2A0h+var_280], 1
0x18004ec73  mov     r8d, r13d
0x18004ec76  mov     rdx, r15
0x18004ec79  mov     rcx, rdi
0x18004ec7c  call    _LogBCryptOpenProviderFailure
0x18004ec81  mov     r9d, 80Dh
0x18004ec87  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004ec8e  lea     rdx, aStatus; "Status"
0x18004ec95  mov     ecx, 0C0000008h
0x18004ec9a  mov     ebx, 0C0000008h
0x18004ec9f  call    DebugTraceError
0x18004eca4  mov     rsi, [rsp+2A0h+var_240]
0x18004eca9  jmp     short loc_18004EC46
0x18004ecab  mov     ebx, 3C8h
0x18004ecb0  mov     ecx, ebx
0x18004ecb2  call    MSCryptAlloc
0x18004ecb7  mov     r14, rax
0x18004ecba  test    rax, rax
0x18004ecbd  jnz     short loc_18004ECF2
0x18004ecbf  mov     r9d, 81Ch
0x18004ecc5  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004eccc  lea     rdx, aStatus; "Status"
0x18004ecd3  mov     ecx, 0C0000017h
0x18004ecd8  mov     ebx, 0C0000017h
0x18004ecdd  call    DebugTraceError
0x18004ece2  mov     rdi, r12
0x18004ece5  mov     rsi, [rsp+2A0h+var_240]
0x18004ecea  xor     r14d, r14d
0x18004eced  jmp     loc_18004F1A1
0x18004ecf2  mov     r8, rbx; Size
0x18004ecf5  xor     edx, edx; Val
0x18004ecf7  mov     rcx, r14; void *
0x18004ecfa  call    memset
0x18004ecff  lea     rcx, [r14+1BCh]; Dst
0x18004ed06  mov     [r14], ebx
0x18004ed09  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18004ed0d  mov     dword ptr [r14+4], 55555551h
0x18004ed15  mov     r8, r15; Src
0x18004ed18  mov     dword ptr [r14+10h], 1
0x18004ed20  mov     edx, 104h; SizeInWords
0x18004ed25  mov     [r14+24h], esi
0x18004ed29  call    cs:__imp_wcsncpy_s
0x18004ed30  nop     dword ptr [rax+rax+00h]
0x18004ed35  mov     eax, r13d
0x18004ed38  lea     rsi, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004ed3f  and     eax, 1
0x18004ed42  lea     rdi, aStatus; "Status"
0x18004ed49  mov     [r14+20h], eax
0x18004ed4d  xor     ecx, ecx
0x18004ed4f  mov     rax, [rsp+2A0h+pvBuffer]
0x18004ed54  mov     dword ptr [rsp+2A0h+var_25F+3], ecx
0x18004ed58  cmp     [rax], ecx
0x18004ed5a  jbe     loc_18004EFBE
0x18004ed60  mov     r12b, [rsp+2A0h+var_260]
0x18004ed65  lea     r8, [r14+30h]
0x18004ed69  lea     rdx, [r14+28h]
0x18004ed6d  mov     rax, [rsp+2A0h+pvBuffer]
0x18004ed72  mov     r9, rdx
0x18004ed75  mov     r10d, ecx
0x18004ed78  mov     [rsp+2A0h+var_280], r8
0x18004ed7d  xor     r8d, r8d
0x18004ed80  mov     [rbp+1A0h+var_218], r10
0x18004ed84  mov     rcx, [rax+8]
0x18004ed88  mov     rcx, [rcx+r10*8]
0x18004ed8c  call    LoadProviderEx
0x18004ed91  mov     ebx, eax
0x18004ed93  mov     rax, [rsp+2A0h+pvBuffer]
0x18004ed98  mov     rcx, [rax+8]
0x18004ed9c  mov     rax, [rbp+1A0h+var_218]
0x18004eda0  mov     rax, [rcx+rax*8]
0x18004eda4  mov     rax, [rax+10h]
0x18004eda8  mov     qword ptr [rsp+2A0h+var_25F+7], rax
0x18004edad  mov     [rbp+1A0h+var_208], rax
0x18004edb1  test    ebx, ebx
0x18004edb3  jns     short loc_18004EDF4
0x18004edb5  mov     r9d, ebx
0x18004edb8  mov     dword ptr [rsp+2A0h+var_280], 2
0x18004edc0  mov     r8d, r13d
0x18004edc3  mov     rdx, r15
0x18004edc6  mov     rcx, rax
0x18004edc9  call    _LogBCryptOpenProviderFailure
0x18004edce  mov     r9d, 85Ch
0x18004edd4  mov     r8, rsi
0x18004edd7  mov     rdx, rdi
0x18004edda  mov     ecx, ebx
0x18004eddc  call    DebugTraceError
0x18004ede1  cmp     r12b, 1
0x18004ede5  jnz     loc_18004F0AF
0x18004edeb  lea     rdx, [r14+28h]
0x18004edef  jmp     loc_18004EF73
0x18004edf4  mov     edx, 3
0x18004edf9  lea     rax, [r14+30h]
0x18004edfd  lea     rcx, [rbp+1A0h+var_1E0]
0x18004ee01  lea     r8d, [rdx+7Dh]
0x18004ee05  movups  xmm0, xmmword ptr [rax]
0x18004ee08  movups  xmm1, xmmword ptr [rax+10h]
0x18004ee0c  movups  xmmword ptr [rcx], xmm0
0x18004ee0f  movups  xmm0, xmmword ptr [rax+20h]
0x18004ee13  movups  xmmword ptr [rcx+10h], xmm1
0x18004ee17  movups  xmm1, xmmword ptr [rax+30h]
0x18004ee1b  movups  xmmword ptr [rcx+20h], xmm0
0x18004ee1f  movups  xmm0, xmmword ptr [rax+40h]
0x18004ee23  movups  xmmword ptr [rcx+30h], xmm1
0x18004ee27  movups  xmm1, xmmword ptr [rax+50h]
0x18004ee2b  movups  xmmword ptr [rcx+40h], xmm0
0x18004ee2f  movups  xmm0, xmmword ptr [rax+60h]
0x18004ee33  movups  xmmword ptr [rcx+50h], xmm1
0x18004ee37  movups  xmm1, xmmword ptr [rax+70h]
0x18004ee3b  add     rax, r8
0x18004ee3e  movups  xmmword ptr [rcx+60h], xmm0
0x18004ee42  movups  xmmword ptr [rcx+70h], xmm1
0x18004ee46  add     rcx, r8
0x18004ee49  sub     rdx, 1
0x18004ee4d  jnz     short loc_18004EE05
0x18004ee4f  mov     rax, [rax]
0x18004ee52  lea     r9, [rbp+1A0h+var_1F8]
0x18004ee56  mov     [rcx], rax
0x18004ee59  lea     r8, [rbp+1A0h+var_220]
0x18004ee5d  mov     ecx, [rsp+2A0h+var_248]
0x18004ee61  lea     rax, [rbp+1A0h+var_210]
0x18004ee65  mov     [rsp+2A0h+var_278], rax
0x18004ee6a  lea     rdx, [rbp+1A0h+var_1E0]
0x18004ee6e  lea     rax, [rbp+1A0h+var_1F0]
0x18004ee72  mov     [rsp+2A0h+var_280], rax
0x18004ee77  call    ValidateFunctionTable
0x18004ee7c  mov     ebx, eax
0x18004ee7e  mov     r8d, r13d
0x18004ee81  test    eax, eax
0x18004ee83  jns     short loc_18004EEB8
0x18004ee85  mov     rax, [rsp+2A0h+pvBuffer]
0x18004ee8a  mov     r9d, ebx
0x18004ee8d  mov     rdx, r15
0x18004ee90  mov     dword ptr [rsp+2A0h+var_280], 3
0x18004ee98  mov     rcx, [rax+8]
0x18004ee9c  mov     rax, [rbp+1A0h+var_218]
0x18004eea0  mov     rcx, [rcx+rax*8]
0x18004eea4  mov     rcx, [rcx+10h]
0x18004eea8  call    _LogBCryptOpenProviderFailure
0x18004eead  mov     r9d, 883h
0x18004eeb3  jmp     loc_18004EDD4
0x18004eeb8  mov     r12, [rsp+2A0h+var_230]
0x18004eebd  lea     r15, [r14+18h]
0x18004eec1  mov     rax, [rbp+1A0h+var_220]
0x18004eec5  mov     rdx, r12
0x18004eec8  mov     rcx, r15
0x18004eecb  call    _guard_dispatch_icall
0x18004eed0  mov     ebx, eax
0x18004eed2  cmp     eax, 0C000A001h
0x18004eed7  jnz     short loc_18004EF06
0x18004eed9  cmp     [rsp+2A0h+var_248], 2
0x18004eede  jnz     short loc_18004EF0E
0x18004eee0  mov     eax, r13d
0x18004eee3  and     al, 68h
0x18004eee5  cmp     al, 8
0x18004eee7  jnz     short loc_18004EF0E
0x18004eee9  mov     rax, [rbp+1A0h+var_220]
0x18004eeed  mov     r8d, r13d
0x18004eef0  and     r8d, 0FFFFFFF7h
0x18004eef4  mov     rdx, r12
0x18004eef7  mov     rcx, r15
0x18004eefa  call    _guard_dispatch_icall
0x18004eeff  or      dword ptr [r14+8], 8
0x18004ef04  mov     ebx, eax
0x18004ef06  test    ebx, ebx
0x18004ef08  jns     loc_18004EFE5
0x18004ef0e  mov     rax, [rsp+2A0h+pvBuffer]
0x18004ef13  mov     r9d, ebx
0x18004ef16  mov     r8d, r13d
0x18004ef19  mov     dword ptr [rsp+2A0h+var_280], 4
0x18004ef21  mov     rdx, r12
0x18004ef24  mov     r15, r12
0x18004ef27  mov     rcx, [rax+8]
0x18004ef2b  mov     rax, [rbp+1A0h+var_218]
0x18004ef2f  mov     rcx, [rcx+rax*8]
0x18004ef33  mov     rcx, [rcx+10h]
0x18004ef37  call    _LogBCryptOpenProviderFailure
0x18004ef3c  mov     r9d, 8C3h
0x18004ef42  mov     r8, rsi
0x18004ef45  mov     rdx, rdi
0x18004ef48  mov     ecx, ebx
0x18004ef4a  call    DebugTraceError
0x18004ef4f  cmp     [rsp+2A0h+var_260], 1
0x18004ef54  jnz     loc_18004F0AF
0x18004ef5a  mov     rcx, [r14+28h]
  ... truncated ...
```

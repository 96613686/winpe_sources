# OpenEccAltSigKey

- ea: `0x18005e3c4`
- end: `0x18005e952`
- name: `OpenEccAltSigKey`
- size: `1422`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180003210`
- `0x180027120`

## callees

- `0x1800086d0`
- `0x18000af80`
- `0x18000bf20`
- `0x180016a38`
- `0x18005e3c4`
- `0x180062280`
- `0x180062310`
- `0x180063010`

## import_xrefs

- `bcrypt!BCryptImportKeyPair` at `0x18005e6dd`
- `bcrypt!BCryptImportKeyPair` at `0x18005e6dd`
- `bcrypt!BCryptDestroyKey` at `0x18005e90d`
- `bcrypt!BCryptDestroyKey` at `0x18005e90d`
- `bcrypt!BCryptExportKey` at `0x18005e539`
- `bcrypt!BCryptExportKey` at `0x18005e63b`
- `bcrypt!BCryptExportKey` at `0x18005e539`
- `bcrypt!BCryptExportKey` at `0x18005e63b`

## string_xrefs

- `0x18005e435`: `onecore\ds\security\cryptoapi\ncrypt\storage\sign.c`
- `0x18005e55a`: `onecore\ds\security\cryptoapi\ncrypt\storage\sign.c`
- `0x18005e65c`: `onecore\ds\security\cryptoapi\ncrypt\storage\sign.c`

## pseudocode

```c
__int64 __fastcall OpenEccAltSigKey(__int64 a1, int a2)
{
  __int64 v2; // rax
  int v4; // r13d
  void *v5; // r15
  __int64 v6; // rcx
  BCRYPT_KEY_HANDLE v7; // r12
  unsigned int BCryptHandle; // eax
  unsigned int v9; // edi
  __int64 v10; // r9
  _DWORD *v11; // r14
  UCHAR *p_cbInput; // rbx
  __int64 v13; // rcx
  const WCHAR *v14; // r13
  int v15; // r14d
  __int64 v16; // rax
  void *v17; // rcx
  NTSTATUS v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r9
  __int64 v21; // rcx
  unsigned __int64 v22; // rdi
  unsigned __int64 v23; // rcx
  __int64 v24; // rcx
  unsigned __int64 v25; // rcx
  void *v26; // rsp
  void *v27; // rsp
  UCHAR *v28; // rax
  NTSTATUS v29; // eax
  __int64 v30; // r9
  __int64 v31; // rcx
  __int64 v32; // rdx
  unsigned __int64 v33; // rdi
  unsigned __int64 v34; // rcx
  __int64 v35; // rcx
  unsigned __int64 v36; // rcx
  void *v37; // rsp
  void *v38; // rsp
  UCHAR *v39; // rax
  _BYTE v41[32]; // [rsp+0h] [rbp-40h] BYREF
  ULONG cbInput; // [rsp+40h] [rbp+0h] BYREF
  int v43; // [rsp+44h] [rbp+4h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+48h] [rbp+8h] BYREF
  char *v45; // [rsp+50h] [rbp+10h] BYREF
  BCRYPT_KEY_HANDLE hKey[2]; // [rsp+58h] [rbp+18h] BYREF

  v2 = *(_QWORD *)(a1 + 64);
  cbInput = 0;
  phKey = 0;
  v4 = a2;
  v43 = a2;
  v5 = 0;
  v6 = *(_QWORD *)(v2 + 80);
  v7 = 0;
  v45 = 0;
  hKey[0] = 0;
  if ( !v6 )
  {
    v11 = (_DWORD *)(a1 + 144);
LABEL_15:
    v5 = *(void **)(a1 + 120);
    goto LABEL_16;
  }
  if ( !*(_QWORD *)(a1 + 120) )
  {
    BCryptHandle = CNG_GetBCryptHandle(v6, &v45);
    v9 = BCryptHandle;
    if ( BCryptHandle )
    {
      v10 = 215;
LABEL_5:
      DebugTraceError(BCryptHandle, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\sign.c", v10);
      goto LABEL_99;
    }
    v5 = v45;
  }
  v11 = (_DWORD *)(a1 + 144);
  if ( *(_DWORD *)(a1 + 144) && !*(_QWORD *)(a1 + 160) )
  {
    BCryptHandle = CNG_GetBCryptIsoHandle(*(_QWORD *)(*(_QWORD *)(a1 + 64) + 80LL), hKey);
    v9 = BCryptHandle;
    if ( BCryptHandle )
    {
      v10 = 226;
      goto LABEL_5;
    }
    v7 = hKey[0];
  }
  if ( !v5 )
    goto LABEL_15;
LABEL_16:
  p_cbInput = 0;
  if ( !v7 )
  {
    if ( *v11 )
      v7 = *(BCRYPT_KEY_HANDLE *)(a1 + 160);
    else
      v7 = v5;
  }
  if ( v4 )
  {
    v13 = 128;
    v14 = L"ECCFULLPUBLICBLOB";
    v15 = 0;
    v16 = 104;
  }
  else
  {
    v14 = L"ISOPROTECTEDBLOB";
    v13 = 136;
    if ( !*v11 )
      v14 = L"ECCFULLPRIVATEBLOB";
    v16 = 112;
    v15 = *(_DWORD *)(a1 + 148) != 0 ? 4 : 0;
  }
  v45 = (char *)v13;
  if ( *(_QWORD *)(v13 + a1) )
  {
LABEL_91:
    if ( !*(_QWORD *)(a1 + 120) )
      *(_QWORD *)(a1 + 120) = v5;
    if ( !*(_QWORD *)(a1 + 160) )
      *(_QWORD *)(a1 + 160) = v7;
    v9 = 0;
    if ( !p_cbInput )
      goto LABEL_98;
    goto LABEL_96;
  }
  v17 = *(void **)(v16 + a1);
  hKey[0] = v17;
  if ( !v43 )
  {
    v18 = (*(__int64 (__fastcall **)(void *, _QWORD, const WCHAR *, _QWORD, _DWORD, ULONG *, int))(*(_QWORD *)(a1 + 168)
                                                                                                 + 120LL))(
            v17,
            0,
            v14,
            0,
            0,
            &cbInput,
            v15);
    v9 = v18;
    if ( v18 < 0 )
    {
      v20 = 366;
      goto LABEL_29;
    }
    v33 = cbInput;
    p_cbInput = 0;
    if ( !cbInput )
      goto LABEL_106;
    if ( cbInput > (unsigned __int64)g_ulMaxStackAllocSize )
      goto LABEL_106;
    v34 = cbInput + g_ulAdditionalProbeSize + 8;
    if ( v34 < cbInput || !(unsigned int)VerifyStackAvailable(v34, v32) )
      goto LABEL_106;
    v35 = v33 + 23;
    if ( v33 + 23 <= v33 + 8 )
      v35 = 0xFFFFFFFFFFFFFF0LL;
    v36 = v35 & 0xFFFFFFFFFFFFFFF0uLL;
    v37 = alloca(v36);
    v38 = alloca(v36);
    p_cbInput = (UCHAR *)&cbInput;
    if ( v41 == (_BYTE *)-64LL || (cbInput = 1801679955, (p_cbInput = (UCHAR *)&phKey) == 0) )
    {
LABEL_106:
      if ( v33 + 8 >= v33 )
      {
        v39 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
        p_cbInput = v39;
        if ( v39 )
        {
          *(_DWORD *)v39 = 1885431112;
          p_cbInput = v39 + 8;
        }
      }
    }
    if ( !p_cbInput )
    {
      v20 = 375;
      goto LABEL_44;
    }
    v29 = (*(__int64 (__fastcall **)(BCRYPT_KEY_HANDLE, _QWORD, const WCHAR *, UCHAR *, ULONG, ULONG *, int))(*(_QWORD *)(a1 + 168) + 120LL))(
            hKey[0],
            0,
            v14,
            p_cbInput,
            cbInput,
            &cbInput,
            v15);
    v9 = v29;
    if ( v29 < 0 )
    {
      v30 = 389;
      goto LABEL_47;
    }
    switch ( *(_DWORD *)p_cbInput )
    {
      case 0x324B4345:
        *(_DWORD *)p_cbInput = 844317509;
        break;
      case 0x344B4345:
        *(_DWORD *)p_cbInput = 877871941;
        break;
      case 0x364B4345:
        *(_DWORD *)p_cbInput = 911426373;
        break;
      case 0x564B4345:
        *(_DWORD *)p_cbInput = 1447314245;
        break;
      default:
        v30 = 420;
        goto LABEL_54;
    }
    v29 = (*(__int64 (__fastcall **)(BCRYPT_KEY_HANDLE, _QWORD, const WCHAR *, BCRYPT_KEY_HANDLE *, UCHAR *, ULONG, _DWORD))(*(_QWORD *)(a1 + 168) + 112LL))(
            v7,
            0,
            v14,
            &phKey,
            p_cbInput,
            cbInput,
            0);
    v9 = v29;
    if ( v29 < 0 )
    {
      v30 = 435;
      goto LABEL_47;
    }
    goto LABEL_89;
  }
  v18 = BCryptExportKey(v17, 0, v14, 0, 0, &cbInput, 0);
  v9 = v18;
  if ( v18 >= 0 )
  {
    v22 = cbInput;
    p_cbInput = 0;
    if ( !cbInput )
      goto LABEL_107;
    if ( cbInput > (unsigned __int64)g_ulMaxStackAllocSize )
      goto LABEL_107;
    v23 = cbInput + g_ulAdditionalProbeSize + 8;
    if ( v23 < cbInput || !(unsigned int)VerifyStackAvailable(v23, v19) )
      goto LABEL_107;
    v24 = v22 + 23;
    if ( v22 + 23 <= v22 + 8 )
      v24 = 0xFFFFFFFFFFFFFF0LL;
    v25 = v24 & 0xFFFFFFFFFFFFFFF0uLL;
    v26 = alloca(v25);
    v27 = alloca(v25);
    p_cbInput = (UCHAR *)&cbInput;
    if ( v41 == (_BYTE *)-64LL || (cbInput = 1801679955, (p_cbInput = (UCHAR *)&phKey) == 0) )
    {
LABEL_107:
      if ( v22 + 8 >= v22 )
      {
        v28 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
        p_cbInput = v28;
        if ( v28 )
        {
          *(_DWORD *)v28 = 1885431112;
          p_cbInput = v28 + 8;
        }
      }
    }
    if ( !p_cbInput )
    {
      v20 = 289;
LABEL_44:
      v9 = -2146893810;
      v21 = 2148073486LL;
      goto LABEL_30;
    }
    v29 = BCryptExportKey(hKey[0], 0, v14, p_cbInput, cbInput, &cbInput, 0);
    v9 = v29;
    if ( v29 < 0 )
    {
      v30 = 303;
LABEL_47:
      v31 = (unsigned int)v29;
LABEL_48:
      DebugTraceError(v31, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\sign.c", v30);
LABEL_96:
      if ( *((_DWORD *)p_cbInput - 2) == 1885431112 )
        ((void (*)(void))g_pfnFree)();
      goto LABEL_98;
    }
    switch ( *(_DWORD *)p_cbInput )
    {
      case 0x314B4345:
        *(_DWORD *)p_cbInput = 827540293;
        break;
      case 0x334B4345:
        *(_DWORD *)p_cbInput = 861094725;
        break;
      case 0x354B4345:
        *(_DWORD *)p_cbInput = 894649157;
        break;
      case 0x504B4345:
        *(_DWORD *)p_cbInput = 1346650949;
        break;
      default:
        v30 = 334;
LABEL_54:
        v9 = -2146893779;
        v31 = 2148073517LL;
        goto LABEL_48;
    }
    v29 = BCryptImportKeyPair(v5, 0, v14, &phKey, p_cbInput, cbInput, 0);
    v9 = v29;
    if ( v29 < 0 )
    {
      v30 = 349;
      goto LABEL_47;
    }
LABEL_89:
    if ( !_InterlockedCompareExchange64((volatile signed __int64 *)&v45[a1], (signed __int64)phKey, 0) )
      phKey = 0;
    goto LABEL_91;
  }
  v20 = 280;
LABEL_29:
  v21 = (unsigned int)v18;
LABEL_30:
  DebugTraceError(v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\sign.c", v20);
LABEL_98:
  v4 = v43;
LABEL_99:
  if ( phKey )
  {
    if ( v4 )
      BCryptDestroyKey(phKey);
    else
      (*(void (__fastcall **)(BCRYPT_KEY_HANDLE))(*(_QWORD *)(a1 + 168) + 136LL))(phKey);
  }
  return v9;
}

```

## disassembly

```asm
0x18005e3c4  push    rbp
0x18005e3c6  push    rbx
0x18005e3c7  push    rsi
0x18005e3c8  push    rdi
0x18005e3c9  push    r12
0x18005e3cb  push    r13
0x18005e3cd  push    r14
0x18005e3cf  push    r15
0x18005e3d1  sub     rsp, 78h
0x18005e3d5  lea     rbp, [rsp+40h]
0x18005e3da  mov     rax, cs:__security_cookie
0x18005e3e1  xor     rax, rbp
0x18005e3e4  mov     [rbp+70h+var_48], rax
0x18005e3e8  mov     rax, [rcx+40h]
0x18005e3ec  xor     r8d, r8d
0x18005e3ef  mov     rsi, rcx
0x18005e3f2  mov     [rbp+70h+cbInput], r8d
0x18005e3f6  mov     [rbp+70h+phKey], r8
0x18005e3fa  mov     r13d, edx
0x18005e3fd  mov     [rbp+70h+var_6C], edx
0x18005e400  mov     r15d, r8d
0x18005e403  mov     rcx, [rax+50h]
0x18005e407  mov     r12d, r8d
0x18005e40a  mov     [rbp+70h+var_60], r8
0x18005e40e  mov     [rbp+70h+hKey], r8
0x18005e412  test    rcx, rcx
0x18005e415  jz      short loc_18005E495
0x18005e417  cmp     [rsi+78h], r8
0x18005e41b  jnz     short loc_18005E453
0x18005e41d  lea     rdx, [rbp+70h+var_60]
0x18005e421  call    CNG_GetBCryptHandle
0x18005e426  xor     r8d, r8d
0x18005e429  mov     edi, eax
0x18005e42b  test    eax, eax
0x18005e42d  jz      short loc_18005E44F
0x18005e42f  mov     r9d, 0D7h
0x18005e435  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005e43c  mov     ecx, eax
0x18005e43e  lea     rdx, aStatus; "Status"
0x18005e445  call    DebugTraceError
0x18005e44a  jmp     loc_18005E8FF
0x18005e44f  mov     r15, [rbp+70h+var_60]
0x18005e453  lea     r14, [rsi+90h]
0x18005e45a  cmp     [r14], r8d
0x18005e45d  jz      short loc_18005E48E
0x18005e45f  cmp     [rsi+0A0h], r8
0x18005e466  jnz     short loc_18005E48E
0x18005e468  mov     rcx, [rsi+40h]
0x18005e46c  lea     rdx, [rbp+70h+hKey]
0x18005e470  mov     rcx, [rcx+50h]
0x18005e474  call    CNG_GetBCryptIsoHandle
0x18005e479  xor     r8d, r8d
0x18005e47c  mov     edi, eax
0x18005e47e  test    eax, eax
0x18005e480  jz      short loc_18005E48A
0x18005e482  mov     r9d, 0E2h
0x18005e488  jmp     short loc_18005E435
0x18005e48a  mov     r12, [rbp+70h+hKey]
0x18005e48e  test    r15, r15
0x18005e491  jnz     short loc_18005E4A0
0x18005e493  jmp     short loc_18005E49C
0x18005e495  lea     r14, [rsi+90h]
0x18005e49c  mov     r15, [rsi+78h]
0x18005e4a0  mov     rbx, r8
0x18005e4a3  test    r12, r12
0x18005e4a6  jnz     short loc_18005E4B9
0x18005e4a8  cmp     [r14], r8d
0x18005e4ab  jz      short loc_18005E4B6
0x18005e4ad  mov     r12, [rsi+0A0h]
0x18005e4b4  jmp     short loc_18005E4B9
0x18005e4b6  mov     r12, r15
0x18005e4b9  test    r13d, r13d
0x18005e4bc  jz      short loc_18005E4D2
0x18005e4be  mov     ecx, 80h
0x18005e4c3  lea     r13, aEccfullpublicb; "ECCFULLPUBLICBLOB"
0x18005e4ca  mov     r14d, r8d
0x18005e4cd  lea     eax, [rcx-18h]
0x18005e4d0  jmp     short loc_18005E4FE
0x18005e4d2  cmp     [r14], r8d
0x18005e4d5  lea     rax, aEccfullprivate; "ECCFULLPRIVATEBLOB"
0x18005e4dc  lea     r13, aIsoprotectedbl; "ISOPROTECTEDBLOB"
0x18005e4e3  mov     ecx, 88h
0x18005e4e8  cmovz   r13, rax
0x18005e4ec  mov     eax, [rsi+94h]
0x18005e4f2  neg     eax
0x18005e4f4  sbb     r14d, r14d
0x18005e4f7  lea     eax, [rcx-18h]
0x18005e4fa  and     r14d, 4
0x18005e4fe  mov     [rbp+70h+var_60], rcx
0x18005e502  cmp     [rcx+rsi], r8
0x18005e506  jnz     loc_18005E8C1
0x18005e50c  mov     rcx, [rax+rsi]; hKey
0x18005e510  xor     r9d, r9d; pbOutput
0x18005e513  mov     [rbp+70h+hKey], rcx
0x18005e517  cmp     [rbp+70h+var_6C], r8d
0x18005e51b  jz      loc_18005E701
0x18005e521  mov     [rsp+0B0h+dwFlags], r8d; dwFlags
0x18005e526  lea     rax, [rbp+70h+cbInput]
0x18005e52a  mov     [rsp+0B0h+pcbResult], rax; pcbResult
0x18005e52f  xor     edx, edx; hExportKey
0x18005e531  mov     [rsp+0B0h+cbOutput], r8d; cbOutput
0x18005e536  mov     r8, r13; pszBlobType
0x18005e539  call    cs:__imp_BCryptExportKey
0x18005e540  nop     dword ptr [rax+rax+00h]
0x18005e545  mov     edi, eax
0x18005e547  test    eax, eax
0x18005e549  jns     short loc_18005E56B
0x18005e54b  mov     r9d, 118h
0x18005e551  mov     ecx, eax
0x18005e553  lea     rdx, aStatus; "Status"
0x18005e55a  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005e561  call    DebugTraceError
0x18005e566  jmp     loc_18005E8FB
0x18005e56b  mov     edi, [rbp+70h+cbInput]
0x18005e56e  xor     ebx, ebx
0x18005e570  test    rdi, rdi
0x18005e573  jz      short loc_18005E5D6
0x18005e575  cmp     rdi, cs:g_ulMaxStackAllocSize
0x18005e57c  ja      short loc_18005E5D6
0x18005e57e  mov     rcx, cs:g_ulAdditionalProbeSize
0x18005e585  add     rcx, 8
0x18005e589  add     rcx, rdi
0x18005e58c  cmp     rcx, rdi
0x18005e58f  jb      short loc_18005E5D6
0x18005e591  call    VerifyStackAvailable
0x18005e596  test    eax, eax
0x18005e598  jz      short loc_18005E5D6
0x18005e59a  lea     rax, [rdi+8]
0x18005e59e  lea     rcx, [rax+0Fh]
0x18005e5a2  cmp     rcx, rax
0x18005e5a5  ja      short loc_18005E5B1
0x18005e5a7  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18005e5b1  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18005e5b5  mov     rax, rcx
0x18005e5b8  call    _alloca_probe
0x18005e5bd  sub     rsp, rcx
0x18005e5c0  lea     rbx, [rsp+0B0h+cbInput]
0x18005e5c5  test    rbx, rbx
0x18005e5c8  jz      short loc_18005E5D6
0x18005e5ca  mov     dword ptr [rbx], 6B637453h
0x18005e5d0  add     rbx, 8
0x18005e5d4  jnz     short loc_18005E5FD
0x18005e5d6  lea     rcx, [rdi+8]
0x18005e5da  cmp     rcx, rdi
0x18005e5dd  jb      short loc_18005E5FD
0x18005e5df  mov     rax, cs:g_pfnAllocate
0x18005e5e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e5eb  mov     rbx, rax
0x18005e5ee  test    rax, rax
0x18005e5f1  jz      short loc_18005E5FD
0x18005e5f3  mov     dword ptr [rax], 70616548h
0x18005e5f9  add     rbx, 8
0x18005e5fd  test    rbx, rbx
0x18005e600  jnz     short loc_18005E617
0x18005e602  mov     r9d, 121h
0x18005e608  mov     edi, 8009000Eh
0x18005e60d  mov     ecx, 8009000Eh
0x18005e612  jmp     loc_18005E553
0x18005e617  mov     rcx, [rbp+70h+hKey]; hKey
0x18005e61b  lea     rax, [rbp+70h+cbInput]
0x18005e61f  mov     [rsp+0B0h+dwFlags], 0; dwFlags
0x18005e627  mov     r9, rbx; pbOutput
0x18005e62a  mov     [rsp+0B0h+pcbResult], rax; pcbResult
0x18005e62f  mov     r8, r13; pszBlobType
0x18005e632  mov     eax, [rbp+70h+cbInput]
0x18005e635  xor     edx, edx; hExportKey
0x18005e637  mov     [rsp+0B0h+cbOutput], eax; cbOutput
0x18005e63b  call    cs:__imp_BCryptExportKey
0x18005e642  nop     dword ptr [rax+rax+00h]
0x18005e647  mov     edi, eax
0x18005e649  test    eax, eax
0x18005e64b  jns     short loc_18005E66D
0x18005e64d  mov     r9d, 12Fh
0x18005e653  mov     ecx, eax
0x18005e655  lea     rdx, aStatus; "Status"
0x18005e65c  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005e663  call    DebugTraceError
0x18005e668  jmp     loc_18005E8E3
0x18005e66d  cmp     dword ptr [rbx], 314B4345h
0x18005e673  jz      short loc_18005E6B7
0x18005e675  cmp     dword ptr [rbx], 334B4345h
0x18005e67b  jz      short loc_18005E6AF
0x18005e67d  cmp     dword ptr [rbx], 354B4345h
0x18005e683  jz      short loc_18005E6A7
0x18005e685  cmp     dword ptr [rbx], 504B4345h
0x18005e68b  jz      short loc_18005E69F
0x18005e68d  mov     r9d, 14Eh
0x18005e693  mov     edi, 8009002Dh
0x18005e698  mov     ecx, 8009002Dh
0x18005e69d  jmp     short loc_18005E655
0x18005e69f  mov     dword ptr [rbx], 50444345h
0x18005e6a5  jmp     short loc_18005E6BD
0x18005e6a7  mov     dword ptr [rbx], 35534345h
0x18005e6ad  jmp     short loc_18005E6BD
0x18005e6af  mov     dword ptr [rbx], 33534345h
0x18005e6b5  jmp     short loc_18005E6BD
0x18005e6b7  mov     dword ptr [rbx], 31534345h
0x18005e6bd  mov     eax, [rbp+70h+cbInput]
0x18005e6c0  lea     r9, [rbp+70h+phKey]; phKey
0x18005e6c4  mov     [rsp+0B0h+dwFlags], 0; dwFlags
0x18005e6cc  mov     r8, r13; pszBlobType
0x18005e6cf  mov     dword ptr [rsp+0B0h+pcbResult], eax; cbInput
0x18005e6d3  xor     edx, edx; hImportKey
0x18005e6d5  mov     rcx, r15; hAlgorithm
0x18005e6d8  mov     qword ptr [rsp+0B0h+cbOutput], rbx; pbInput
0x18005e6dd  call    cs:__imp_BCryptImportKeyPair
0x18005e6e4  nop     dword ptr [rax+rax+00h]
0x18005e6e9  xor     r8d, r8d
0x18005e6ec  mov     edi, eax
0x18005e6ee  test    eax, eax
0x18005e6f0  jns     loc_18005E8AB
0x18005e6f6  mov     r9d, 15Dh
0x18005e6fc  jmp     loc_18005E653
0x18005e701  mov     rax, [rsi+0A8h]
0x18005e708  lea     rdx, [rbp+70h+cbInput]
0x18005e70c  mov     [rsp+0B0h+dwFlags], r14d
0x18005e711  mov     [rsp+0B0h+pcbResult], rdx
0x18005e716  xor     edx, edx
0x18005e718  mov     [rsp+0B0h+cbOutput], r8d
0x18005e71d  mov     r8, r13
0x18005e720  mov     rax, [rax+78h]
0x18005e724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e729  mov     edi, eax
0x18005e72b  test    eax, eax
0x18005e72d  jns     short loc_18005E73A
0x18005e72f  mov     r9d, 16Eh
0x18005e735  jmp     loc_18005E551
0x18005e73a  mov     edi, [rbp+70h+cbInput]
0x18005e73d  xor     ebx, ebx
0x18005e73f  test    rdi, rdi
0x18005e742  jz      short loc_18005E7A5
0x18005e744  cmp     rdi, cs:g_ulMaxStackAllocSize
0x18005e74b  ja      short loc_18005E7A5
0x18005e74d  mov     rcx, cs:g_ulAdditionalProbeSize
0x18005e754  add     rcx, 8
0x18005e758  add     rcx, rdi
0x18005e75b  cmp     rcx, rdi
0x18005e75e  jb      short loc_18005E7A5
0x18005e760  call    VerifyStackAvailable
0x18005e765  test    eax, eax
0x18005e767  jz      short loc_18005E7A5
0x18005e769  lea     rax, [rdi+8]
0x18005e76d  lea     rcx, [rax+0Fh]
0x18005e771  cmp     rcx, rax
0x18005e774  ja      short loc_18005E780
0x18005e776  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18005e780  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18005e784  mov     rax, rcx
0x18005e787  call    _alloca_probe
0x18005e78c  sub     rsp, rcx
0x18005e78f  lea     rbx, [rsp+0B0h+cbInput]
0x18005e794  test    rbx, rbx
0x18005e797  jz      short loc_18005E7A5
0x18005e799  mov     dword ptr [rbx], 6B637453h
0x18005e79f  add     rbx, 8
0x18005e7a3  jnz     short loc_18005E7CC
0x18005e7a5  lea     rcx, [rdi+8]
0x18005e7a9  cmp     rcx, rdi
0x18005e7ac  jb      short loc_18005E7CC
0x18005e7ae  mov     rax, cs:g_pfnAllocate
0x18005e7b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e7ba  mov     rbx, rax
0x18005e7bd  test    rax, rax
0x18005e7c0  jz      short loc_18005E7CC
0x18005e7c2  mov     dword ptr [rax], 70616548h
0x18005e7c8  add     rbx, 8
0x18005e7cc  test    rbx, rbx
0x18005e7cf  jnz     short loc_18005E7DC
0x18005e7d1  mov     r9d, 177h
0x18005e7d7  jmp     loc_18005E608
0x18005e7dc  mov     rax, [rsi+0A8h]
0x18005e7e3  lea     rcx, [rbp+70h+cbInput]
0x18005e7e7  mov     [rsp+0B0h+dwFlags], r14d
0x18005e7ec  mov     r9, rbx
0x18005e7ef  mov     [rsp+0B0h+pcbResult], rcx
0x18005e7f4  mov     r8, r13
0x18005e7f7  mov     ecx, [rbp+70h+cbInput]
0x18005e7fa  xor     edx, edx
0x18005e7fc  mov     rax, [rax+78h]
0x18005e800  mov     [rsp+0B0h+cbOutput], ecx
0x18005e804  mov     rcx, [rbp+70h+hKey]
0x18005e808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e80d  mov     edi, eax
0x18005e80f  test    eax, eax
0x18005e811  jns     short loc_18005E81E
0x18005e813  mov     r9d, 185h
0x18005e819  jmp     loc_18005E653
0x18005e81e  cmp     dword ptr [rbx], 324B4345h
0x18005e824  jz      short loc_18005E861
0x18005e826  cmp     dword ptr [rbx], 344B4345h
0x18005e82c  jz      short loc_18005E859
0x18005e82e  cmp     dword ptr [rbx], 364B4345h
0x18005e834  jz      short loc_18005E851
0x18005e836  cmp     dword ptr [rbx], 564B4345h
0x18005e83c  jz      short loc_18005E849
0x18005e83e  mov     r9d, 1A4h
0x18005e844  jmp     loc_18005E693
0x18005e849  mov     dword ptr [rbx], 56444345h
0x18005e84f  jmp     short loc_18005E867
0x18005e851  mov     dword ptr [rbx], 36534345h
  ... truncated ...
```

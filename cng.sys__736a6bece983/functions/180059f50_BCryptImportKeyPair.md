# BCryptImportKeyPair

- ea: `0x180059f50`
- end: `0x18005a2a6`
- name: `BCryptImportKeyPair`
- size: `854`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE hAlgorithm, BCRYPT_KEY_HANDLE hImportKey, LPCWSTR pszBlobType, BCRYPT_KEY_HANDLE *phKey, PUCHAR pbInput, ULONG cbInput, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1800039d0`
- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x1800363a0`
- `0x180046ea0`
- `0x180059f50`
- `0x18005c074`
- `0x18009f616`
- `0x18009f6d0`

## string_xrefs

- `0x18005a023`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18005a227`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18005a27f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptImportKeyPair(
        BCRYPT_ALG_HANDLE hAlgorithm,
        BCRYPT_KEY_HANDLE hImportKey,
        LPCWSTR pszBlobType,
        BCRYPT_KEY_HANDLE *phKey,
        PUCHAR pbInput,
        ULONG cbInput,
        ULONG dwFlags)
{
  BCRYPT_KEY_HANDLE *v7; // r13
  const wchar_t *v8; // rbx
  __int64 v11; // rdx
  __int64 v12; // rdi
  __int64 v13; // r8
  __int64 v14; // r9
  NTSTATUS v15; // ebx
  __int64 v16; // r9
  __int64 v17; // rcx
  __int64 v18; // rax
  char *v19; // r14
  UCHAR *v20; // rsi
  __int64 (__fastcall *v21)(_QWORD, __int64, const wchar_t *, char *, PUCHAR, ULONG, ULONG); // rax
  __int64 v22; // rax
  __int64 v23; // r13
  __int64 v24; // r9
  __int64 v25; // rcx
  __int64 v26; // r12
  int v27; // ecx
  __int64 v28; // rax
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  ULONG v33; // ecx
  PUCHAR v34; // rax
  ULONG v36; // [rsp+50h] [rbp-68h] BYREF
  __int64 (__fastcall *v37)(_QWORD, __int64, const wchar_t *, char *, PUCHAR, ULONG, ULONG); // [rsp+58h] [rbp-60h]
  __int64 v38; // [rsp+60h] [rbp-58h]

  v7 = phKey;
  v36 = 0;
  v8 = pszBlobType;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_qqSqqdD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      (_DWORD)hImportKey,
      (_DWORD)pszBlobType,
      (_DWORD)hAlgorithm,
      (char)hImportKey,
      (__int64)pszBlobType,
      (char)phKey,
      (char)pbInput,
      cbInput,
      dwFlags);
  v12 = ValidateBaseAlgHandle(hAlgorithm);
  if ( !v12 )
  {
    v15 = -1073741816;
    v16 = 4858;
    v17 = 3221225480LL;
LABEL_47:
    DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v16);
    return v15;
  }
  if ( !v7 || !v8 )
  {
    v15 = -1073741811;
    v16 = 4866;
    v17 = 3221225485LL;
    goto LABEL_47;
  }
  v18 = MSCryptAlloc(32, v11, v13, v14);
  v19 = (char *)v18;
  if ( !v18 )
  {
    v15 = -1073741801;
    DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 4892);
    return v15;
  }
  *(_DWORD *)v18 = 32;
  v20 = 0;
  *(_DWORD *)(v18 + 4) = 1431655762;
  *(_QWORD *)(v18 + 8) = v12;
  if ( *(_DWORD *)(v12 + 36) != 3 )
  {
    if ( *(_DWORD *)(v12 + 36) == 4 )
    {
      v21 = *(__int64 (__fastcall **)(_QWORD, __int64, const wchar_t *, char *, PUCHAR, ULONG, ULONG))(v12 + 128);
      goto LABEL_17;
    }
    if ( *(_DWORD *)(v12 + 36) != 5 && *(_DWORD *)(v12 + 36) != 8 )
    {
      v15 = -1073741637;
LABEL_41:
      MSCryptFree(v19);
      goto LABEL_43;
    }
  }
  v21 = *(__int64 (__fastcall **)(_QWORD, __int64, const wchar_t *, char *, PUCHAR, ULONG, ULONG))(v12 + 120);
LABEL_17:
  v37 = v21;
  v38 = 0;
  if ( hImportKey )
  {
    v22 = ValidateBaseKeyHandle(hImportKey);
    v23 = v22;
    if ( !v22 )
    {
      v24 = 4934;
LABEL_20:
      v15 = -1073741816;
      v25 = 3221225480LL;
LABEL_40:
      DebugTraceError(v25, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v24);
      goto LABEL_41;
    }
    v26 = *(_QWORD *)(v22 + 8);
    v27 = wcscmp_0(v8, L"PKCS11RsaAesWrapBlob") != 0 ? 1 : 3;
    if ( !v26 )
    {
      v15 = -1073739510;
      v24 = 4946;
      v25 = 3221227786LL;
      goto LABEL_40;
    }
    if ( *(_DWORD *)(v26 + 36) != v27 )
    {
      v24 = 4953;
      goto LABEL_20;
    }
    if ( *(_QWORD *)(v26 + 40) != *(_QWORD *)(v12 + 40) )
    {
      v15 = -1073741788;
      v24 = 4960;
      v25 = 3221225508LL;
      goto LABEL_40;
    }
    v28 = *(_QWORD *)(v23 + 16);
    v7 = phKey;
    v38 = v28;
  }
  if ( !wcscmp_0(v8, L"RSAFULLPRIVATEBLOB") )
  {
    v29 = ConvertRsaFullPrivateBlob(pbInput, cbInput, 0, 0, &v36);
    v15 = v29;
    if ( v29 < 0 )
    {
      v24 = 4981;
LABEL_39:
      v25 = (unsigned int)v29;
      goto LABEL_40;
    }
    v20 = (UCHAR *)MSCryptAlloc(v36, v30, v31, v32);
    if ( !v20 )
    {
      v15 = -1073741801;
      v24 = 4990;
      v25 = 3221225495LL;
      goto LABEL_40;
    }
    v29 = ConvertRsaFullPrivateBlob(pbInput, cbInput, v20, v36, &v36);
    v15 = v29;
    if ( v29 < 0 )
    {
      v24 = 5002;
      goto LABEL_39;
    }
    v33 = v36;
    v8 = L"RSAPRIVATEBLOB";
    v34 = v20;
  }
  else
  {
    v33 = cbInput;
    v34 = pbInput;
  }
  v29 = v37(*(_QWORD *)(v12 + 24), v38, v8, v19 + 16, v34, v33, dwFlags);
  v15 = v29;
  if ( v29 < 0 )
  {
    v24 = 5210;
    goto LABEL_39;
  }
  *v7 = v19;
  _InterlockedIncrement((volatile signed __int32 *)(v12 + 16));
  v15 = 0;
LABEL_43:
  if ( v20 )
    MSCryptFree(v20);
  return v15;
}

```

## disassembly

```asm
0x180059f50  mov     [rsp+arg_18], r9
0x180059f55  push    rbx
0x180059f56  push    rbp
0x180059f57  push    rsi
0x180059f58  push    rdi
0x180059f59  push    r12
0x180059f5b  push    r13
0x180059f5d  push    r14
0x180059f5f  push    r15
0x180059f61  sub     rsp, 78h
0x180059f65  mov     r13, r9
0x180059f68  mov     [rsp+0B8h+var_68], 0
0x180059f70  mov     rbx, r8
0x180059f73  mov     r12, rdx
0x180059f76  mov     rdi, rcx
0x180059f79  mov     rcx, cs:WPP_GLOBAL_Control
0x180059f80  lea     rax, WPP_GLOBAL_Control
0x180059f87  mov     rbp, [rsp+0B8h+pbInput]
0x180059f8f  cmp     rcx, rax
0x180059f92  jz      short loc_180059FD1
0x180059f94  mov     eax, [rcx+2Ch]
0x180059f97  test    al, 4
0x180059f99  jz      short loc_180059FD1
0x180059f9b  mov     eax, [rsp+0B8h+dwFlags]
0x180059fa2  mov     rcx, [rcx+18h]
0x180059fa6  mov     [rsp+0B8h+var_70], eax
0x180059faa  mov     eax, [rsp+0B8h+cbInput]
0x180059fb1  mov     [rsp+0B8h+var_78], eax
0x180059fb5  mov     [rsp+0B8h+var_80], rbp
0x180059fba  mov     [rsp+0B8h+var_88], r9
0x180059fbf  mov     r9, rdi
0x180059fc2  mov     [rsp+0B8h+var_90], rbx
0x180059fc7  mov     [rsp+0B8h+var_98], rdx
0x180059fcc  call    WPP_SF_qqSqqdD
0x180059fd1  mov     rcx, rdi
0x180059fd4  call    ValidateBaseAlgHandle
0x180059fd9  mov     rdi, rax
0x180059fdc  test    rax, rax
0x180059fdf  jnz     short loc_180059FF6
0x180059fe1  mov     ebx, 0C0000008h
0x180059fe6  mov     r9d, 12FAh
0x180059fec  mov     ecx, 0C0000008h
0x180059ff1  jmp     loc_18005A27F
0x180059ff6  test    r13, r13
0x180059ff9  jz      loc_18005A26F
0x180059fff  test    rbx, rbx
0x18005a002  jz      loc_18005A26F
0x18005a008  mov     ecx, 20h ; ' '
0x18005a00d  mov     r15, rbp
0x18005a010  call    MSCryptAlloc
0x18005a015  mov     r14, rax
0x18005a018  test    rax, rax
0x18005a01b  jnz     short loc_18005A045
0x18005a01d  mov     r9d, 131Ch
0x18005a023  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005a02a  lea     rdx, aStatus; "Status"
0x18005a031  mov     ecx, 0C0000017h
0x18005a036  mov     ebx, 0C0000017h
0x18005a03b  call    DebugTraceError
0x18005a040  jmp     loc_18005A25B
0x18005a045  mov     dword ptr [rax], 20h ; ' '
0x18005a04b  xor     esi, esi
0x18005a04d  mov     dword ptr [rax+4], 55555552h
0x18005a054  mov     [rax+8], rdi
0x18005a058  mov     ecx, [rdi+24h]
0x18005a05b  sub     ecx, 3
0x18005a05e  jz      short loc_18005A082
0x18005a060  sub     ecx, 1
0x18005a063  jz      short loc_18005A079
0x18005a065  sub     ecx, 1
0x18005a068  jz      short loc_18005A082
0x18005a06a  cmp     ecx, 3
0x18005a06d  jz      short loc_18005A082
0x18005a06f  mov     ebx, 0C00000BBh
0x18005a074  jmp     loc_18005A23A
0x18005a079  mov     rax, [rdi+80h]
0x18005a080  jmp     short loc_18005A086
0x18005a082  mov     rax, [rdi+78h]
0x18005a086  mov     [rsp+0B8h+var_60], rax
0x18005a08b  mov     [rsp+0B8h+var_58], rsi
0x18005a090  test    r12, r12
0x18005a093  jz      loc_18005A135
0x18005a099  mov     rcx, r12
0x18005a09c  call    ValidateBaseKeyHandle
0x18005a0a1  mov     r13, rax
0x18005a0a4  test    rax, rax
0x18005a0a7  jnz     short loc_18005A0BE
0x18005a0a9  mov     r9d, 1346h
0x18005a0af  mov     ebx, 0C0000008h
0x18005a0b4  mov     ecx, 0C0000008h
0x18005a0b9  jmp     loc_18005A227
0x18005a0be  mov     r12, [rax+8]
0x18005a0c2  lea     rdx, aPkcs11rsaaeswr; "PKCS11RsaAesWrapBlob"
0x18005a0c9  mov     rcx, rbx; Str1
0x18005a0cc  call    wcscmp_0
0x18005a0d1  neg     eax
0x18005a0d3  sbb     ecx, ecx
0x18005a0d5  and     ecx, 0FFFFFFFEh
0x18005a0d8  add     ecx, 3
0x18005a0db  test    r12, r12
0x18005a0de  jnz     short loc_18005A0F5
0x18005a0e0  mov     ebx, 0C000090Ah
0x18005a0e5  mov     r9d, 1352h
0x18005a0eb  mov     ecx, 0C000090Ah
0x18005a0f0  jmp     loc_18005A227
0x18005a0f5  cmp     [r12+24h], ecx
0x18005a0fa  jz      short loc_18005A104
0x18005a0fc  mov     r9d, 1359h
0x18005a102  jmp     short loc_18005A0AF
0x18005a104  mov     rax, [rdi+28h]
0x18005a108  cmp     [r12+28h], rax
0x18005a10d  jz      short loc_18005A124
0x18005a10f  mov     ebx, 0C0000024h
0x18005a114  mov     r9d, 1360h
0x18005a11a  mov     ecx, 0C0000024h
0x18005a11f  jmp     loc_18005A227
0x18005a124  mov     rax, [r13+10h]
0x18005a128  mov     r13, [rsp+0B8h+arg_18]
0x18005a130  mov     [rsp+0B8h+var_58], rax
0x18005a135  lea     rdx, aRsafullprivate; "RSAFULLPRIVATEBLOB"
0x18005a13c  mov     rcx, rbx; Str1
0x18005a13f  call    wcscmp_0
0x18005a144  test    eax, eax
0x18005a146  jnz     loc_18005A1E1
0x18005a14c  mov     r12d, [rsp+0B8h+cbInput]
0x18005a154  lea     rax, [rsp+0B8h+var_68]
0x18005a159  mov     edx, r12d
0x18005a15c  mov     [rsp+0B8h+var_98], rax
0x18005a161  xor     r9d, r9d
0x18005a164  xor     r8d, r8d
0x18005a167  mov     rcx, rbp
0x18005a16a  call    ConvertRsaFullPrivateBlob
0x18005a16f  mov     ebx, eax
0x18005a171  test    eax, eax
0x18005a173  jns     short loc_18005A180
0x18005a175  mov     r9d, 1375h
0x18005a17b  jmp     loc_18005A225
0x18005a180  mov     ecx, [rsp+0B8h+var_68]
0x18005a184  call    MSCryptAlloc
0x18005a189  mov     rsi, rax
0x18005a18c  test    rax, rax
0x18005a18f  jnz     short loc_18005A1A6
0x18005a191  mov     ebx, 0C0000017h
0x18005a196  mov     r9d, 137Eh
0x18005a19c  mov     ecx, 0C0000017h
0x18005a1a1  jmp     loc_18005A227
0x18005a1a6  mov     r9d, [rsp+0B8h+var_68]
0x18005a1ab  lea     rax, [rsp+0B8h+var_68]
0x18005a1b0  mov     r8, rsi
0x18005a1b3  mov     [rsp+0B8h+var_98], rax
0x18005a1b8  mov     edx, r12d
0x18005a1bb  mov     rcx, rbp
0x18005a1be  call    ConvertRsaFullPrivateBlob
0x18005a1c3  mov     ebx, eax
0x18005a1c5  test    eax, eax
0x18005a1c7  jns     short loc_18005A1D1
0x18005a1c9  mov     r9d, 138Ah
0x18005a1cf  jmp     short loc_18005A225
0x18005a1d1  mov     ecx, [rsp+0B8h+var_68]
0x18005a1d5  lea     rbx, aRsaprivateblob; "RSAPRIVATEBLOB"
0x18005a1dc  mov     rax, rsi
0x18005a1df  jmp     short loc_18005A1EB
0x18005a1e1  mov     ecx, [rsp+0B8h+cbInput]
0x18005a1e8  mov     rax, rbp
0x18005a1eb  mov     edx, [rsp+0B8h+dwFlags]
0x18005a1f2  lea     r9, [r14+10h]
0x18005a1f6  mov     dword ptr [rsp+0B8h+var_88], edx
0x18005a1fa  mov     r8, rbx
0x18005a1fd  mov     rdx, [rsp+0B8h+var_58]
0x18005a202  mov     dword ptr [rsp+0B8h+var_90], ecx
0x18005a206  mov     rcx, [rdi+18h]
0x18005a20a  mov     [rsp+0B8h+var_98], rax
0x18005a20f  mov     rax, [rsp+0B8h+var_60]
0x18005a214  call    _guard_dispatch_icall
0x18005a219  mov     ebx, eax
0x18005a21b  test    eax, eax
0x18005a21d  jns     short loc_18005A244
0x18005a21f  mov     r9d, 145Ah
0x18005a225  mov     ecx, eax
0x18005a227  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005a22e  lea     rdx, aStatus; "Status"
0x18005a235  call    DebugTraceError
0x18005a23a  mov     rcx, r14; P
0x18005a23d  call    MSCryptFree
0x18005a242  jmp     short loc_18005A24E
0x18005a244  mov     [r13+0], r14
0x18005a248  lock inc dword ptr [rdi+10h]
0x18005a24c  xor     ebx, ebx
0x18005a24e  test    rsi, rsi
0x18005a251  jz      short loc_18005A25B
0x18005a253  mov     rcx, rsi; P
0x18005a256  call    MSCryptFree
0x18005a25b  test    r15, r15
0x18005a25e  jz      short loc_18005A292
0x18005a260  cmp     r15, rbp
0x18005a263  jz      short loc_18005A292
0x18005a265  mov     rcx, r15; P
0x18005a268  call    MSCryptFree
0x18005a26d  jmp     short loc_18005A292
0x18005a26f  mov     ebx, 0C000000Dh
0x18005a274  mov     r9d, 1302h
0x18005a27a  mov     ecx, 0C000000Dh
0x18005a27f  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005a286  lea     rdx, aStatus; "Status"
0x18005a28d  call    DebugTraceError
0x18005a292  mov     eax, ebx
0x18005a294  add     rsp, 78h
0x18005a298  pop     r15
0x18005a29a  pop     r14
0x18005a29c  pop     r13
0x18005a29e  pop     r12
0x18005a2a0  pop     rdi
0x18005a2a1  pop     rsi
0x18005a2a2  pop     rbp
0x18005a2a3  pop     rbx
0x18005a2a4  retn
```

# BCryptImportKeyPair

- ea: `0x180059660`
- end: `0x1800599b6`
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
- `0x1800358a0`
- `0x180046410`
- `0x180059660`
- `0x18005b784`
- `0x18009d746`
- `0x18009d860`

## string_xrefs

- `0x180059733`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180059937`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18005998f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
  __int64 v11; // rdi
  NTSTATUS v12; // ebx
  __int64 v13; // r9
  __int64 v14; // rcx
  __int64 v15; // rax
  char *v16; // r14
  UCHAR *v17; // rsi
  __int64 (__fastcall *v18)(_QWORD, __int64, const wchar_t *, char *, PUCHAR, ULONG, ULONG); // rax
  __int64 v19; // rax
  __int64 v20; // r13
  __int64 v21; // r9
  __int64 v22; // rcx
  __int64 v23; // r12
  int v24; // ecx
  __int64 v25; // rax
  int v26; // eax
  ULONG v27; // ecx
  PUCHAR v28; // rax
  ULONG v30; // [rsp+50h] [rbp-68h] BYREF
  __int64 (__fastcall *v31)(_QWORD, __int64, const wchar_t *, char *, PUCHAR, ULONG, ULONG); // [rsp+58h] [rbp-60h]
  __int64 v32; // [rsp+60h] [rbp-58h]

  v7 = phKey;
  v30 = 0;
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
  v11 = ValidateBaseAlgHandle(hAlgorithm);
  if ( !v11 )
  {
    v12 = -1073741816;
    v13 = 4858;
    v14 = 3221225480LL;
LABEL_47:
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v13);
    return v12;
  }
  if ( !v7 || !v8 )
  {
    v12 = -1073741811;
    v13 = 4866;
    v14 = 3221225485LL;
    goto LABEL_47;
  }
  v15 = MSCryptAlloc(32);
  v16 = (char *)v15;
  if ( !v15 )
  {
    v12 = -1073741801;
    DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 4892);
    return v12;
  }
  *(_DWORD *)v15 = 32;
  v17 = 0;
  *(_DWORD *)(v15 + 4) = 1431655762;
  *(_QWORD *)(v15 + 8) = v11;
  if ( *(_DWORD *)(v11 + 36) != 3 )
  {
    if ( *(_DWORD *)(v11 + 36) == 4 )
    {
      v18 = *(__int64 (__fastcall **)(_QWORD, __int64, const wchar_t *, char *, PUCHAR, ULONG, ULONG))(v11 + 128);
      goto LABEL_17;
    }
    if ( *(_DWORD *)(v11 + 36) != 5 && *(_DWORD *)(v11 + 36) != 8 )
    {
      v12 = -1073741637;
LABEL_41:
      MSCryptFree(v16);
      goto LABEL_43;
    }
  }
  v18 = *(__int64 (__fastcall **)(_QWORD, __int64, const wchar_t *, char *, PUCHAR, ULONG, ULONG))(v11 + 120);
LABEL_17:
  v31 = v18;
  v32 = 0;
  if ( hImportKey )
  {
    v19 = ValidateBaseKeyHandle(hImportKey);
    v20 = v19;
    if ( !v19 )
    {
      v21 = 4934;
LABEL_20:
      v12 = -1073741816;
      v22 = 3221225480LL;
LABEL_40:
      DebugTraceError(v22, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v21);
      goto LABEL_41;
    }
    v23 = *(_QWORD *)(v19 + 8);
    v24 = wcscmp_0(v8, L"PKCS11RsaAesWrapBlob") != 0 ? 1 : 3;
    if ( !v23 )
    {
      v12 = -1073739510;
      v21 = 4946;
      v22 = 3221227786LL;
      goto LABEL_40;
    }
    if ( *(_DWORD *)(v23 + 36) != v24 )
    {
      v21 = 4953;
      goto LABEL_20;
    }
    if ( *(_QWORD *)(v23 + 40) != *(_QWORD *)(v11 + 40) )
    {
      v12 = -1073741788;
      v21 = 4960;
      v22 = 3221225508LL;
      goto LABEL_40;
    }
    v25 = *(_QWORD *)(v20 + 16);
    v7 = phKey;
    v32 = v25;
  }
  if ( !wcscmp_0(v8, L"RSAFULLPRIVATEBLOB") )
  {
    v26 = ConvertRsaFullPrivateBlob(pbInput, cbInput, 0, 0, &v30);
    v12 = v26;
    if ( v26 < 0 )
    {
      v21 = 4981;
LABEL_39:
      v22 = (unsigned int)v26;
      goto LABEL_40;
    }
    v17 = (UCHAR *)MSCryptAlloc(v30);
    if ( !v17 )
    {
      v12 = -1073741801;
      v21 = 4990;
      v22 = 3221225495LL;
      goto LABEL_40;
    }
    v26 = ConvertRsaFullPrivateBlob(pbInput, cbInput, v17, v30, &v30);
    v12 = v26;
    if ( v26 < 0 )
    {
      v21 = 5002;
      goto LABEL_39;
    }
    v27 = v30;
    v8 = L"RSAPRIVATEBLOB";
    v28 = v17;
  }
  else
  {
    v27 = cbInput;
    v28 = pbInput;
  }
  v26 = v31(*(_QWORD *)(v11 + 24), v32, v8, v16 + 16, v28, v27, dwFlags);
  v12 = v26;
  if ( v26 < 0 )
  {
    v21 = 5210;
    goto LABEL_39;
  }
  *v7 = v16;
  _InterlockedIncrement((volatile signed __int32 *)(v11 + 16));
  v12 = 0;
LABEL_43:
  if ( v17 )
    MSCryptFree(v17);
  return v12;
}

```

## disassembly

```asm
0x180059660  mov     [rsp+arg_18], r9
0x180059665  push    rbx
0x180059666  push    rbp
0x180059667  push    rsi
0x180059668  push    rdi
0x180059669  push    r12
0x18005966b  push    r13
0x18005966d  push    r14
0x18005966f  push    r15
0x180059671  sub     rsp, 78h
0x180059675  mov     r13, r9
0x180059678  mov     [rsp+0B8h+var_68], 0
0x180059680  mov     rbx, r8
0x180059683  mov     r12, rdx
0x180059686  mov     rdi, rcx
0x180059689  mov     rcx, cs:WPP_GLOBAL_Control
0x180059690  lea     rax, WPP_GLOBAL_Control
0x180059697  mov     rbp, [rsp+0B8h+pbInput]
0x18005969f  cmp     rcx, rax
0x1800596a2  jz      short loc_1800596E1
0x1800596a4  mov     eax, [rcx+2Ch]
0x1800596a7  test    al, 4
0x1800596a9  jz      short loc_1800596E1
0x1800596ab  mov     eax, [rsp+0B8h+dwFlags]
0x1800596b2  mov     rcx, [rcx+18h]
0x1800596b6  mov     [rsp+0B8h+var_70], eax
0x1800596ba  mov     eax, [rsp+0B8h+cbInput]
0x1800596c1  mov     [rsp+0B8h+var_78], eax
0x1800596c5  mov     [rsp+0B8h+var_80], rbp
0x1800596ca  mov     [rsp+0B8h+var_88], r9
0x1800596cf  mov     r9, rdi
0x1800596d2  mov     [rsp+0B8h+var_90], rbx
0x1800596d7  mov     [rsp+0B8h+var_98], rdx
0x1800596dc  call    WPP_SF_qqSqqdD
0x1800596e1  mov     rcx, rdi
0x1800596e4  call    ValidateBaseAlgHandle
0x1800596e9  mov     rdi, rax
0x1800596ec  test    rax, rax
0x1800596ef  jnz     short loc_180059706
0x1800596f1  mov     ebx, 0C0000008h
0x1800596f6  mov     r9d, 12FAh
0x1800596fc  mov     ecx, 0C0000008h
0x180059701  jmp     loc_18005998F
0x180059706  test    r13, r13
0x180059709  jz      loc_18005997F
0x18005970f  test    rbx, rbx
0x180059712  jz      loc_18005997F
0x180059718  mov     ecx, 20h ; ' '
0x18005971d  mov     r15, rbp
0x180059720  call    MSCryptAlloc
0x180059725  mov     r14, rax
0x180059728  test    rax, rax
0x18005972b  jnz     short loc_180059755
0x18005972d  mov     r9d, 131Ch
0x180059733  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005973a  lea     rdx, aStatus; "Status"
0x180059741  mov     ecx, 0C0000017h
0x180059746  mov     ebx, 0C0000017h
0x18005974b  call    DebugTraceError
0x180059750  jmp     loc_18005996B
0x180059755  mov     dword ptr [rax], 20h ; ' '
0x18005975b  xor     esi, esi
0x18005975d  mov     dword ptr [rax+4], 55555552h
0x180059764  mov     [rax+8], rdi
0x180059768  mov     ecx, [rdi+24h]
0x18005976b  sub     ecx, 3
0x18005976e  jz      short loc_180059792
0x180059770  sub     ecx, 1
0x180059773  jz      short loc_180059789
0x180059775  sub     ecx, 1
0x180059778  jz      short loc_180059792
0x18005977a  cmp     ecx, 3
0x18005977d  jz      short loc_180059792
0x18005977f  mov     ebx, 0C00000BBh
0x180059784  jmp     loc_18005994A
0x180059789  mov     rax, [rdi+80h]
0x180059790  jmp     short loc_180059796
0x180059792  mov     rax, [rdi+78h]
0x180059796  mov     [rsp+0B8h+var_60], rax
0x18005979b  mov     [rsp+0B8h+var_58], rsi
0x1800597a0  test    r12, r12
0x1800597a3  jz      loc_180059845
0x1800597a9  mov     rcx, r12
0x1800597ac  call    ValidateBaseKeyHandle
0x1800597b1  mov     r13, rax
0x1800597b4  test    rax, rax
0x1800597b7  jnz     short loc_1800597CE
0x1800597b9  mov     r9d, 1346h
0x1800597bf  mov     ebx, 0C0000008h
0x1800597c4  mov     ecx, 0C0000008h
0x1800597c9  jmp     loc_180059937
0x1800597ce  mov     r12, [rax+8]
0x1800597d2  lea     rdx, aPkcs11rsaaeswr; "PKCS11RsaAesWrapBlob"
0x1800597d9  mov     rcx, rbx; Str1
0x1800597dc  call    wcscmp_0
0x1800597e1  neg     eax
0x1800597e3  sbb     ecx, ecx
0x1800597e5  and     ecx, 0FFFFFFFEh
0x1800597e8  add     ecx, 3
0x1800597eb  test    r12, r12
0x1800597ee  jnz     short loc_180059805
0x1800597f0  mov     ebx, 0C000090Ah
0x1800597f5  mov     r9d, 1352h
0x1800597fb  mov     ecx, 0C000090Ah
0x180059800  jmp     loc_180059937
0x180059805  cmp     [r12+24h], ecx
0x18005980a  jz      short loc_180059814
0x18005980c  mov     r9d, 1359h
0x180059812  jmp     short loc_1800597BF
0x180059814  mov     rax, [rdi+28h]
0x180059818  cmp     [r12+28h], rax
0x18005981d  jz      short loc_180059834
0x18005981f  mov     ebx, 0C0000024h
0x180059824  mov     r9d, 1360h
0x18005982a  mov     ecx, 0C0000024h
0x18005982f  jmp     loc_180059937
0x180059834  mov     rax, [r13+10h]
0x180059838  mov     r13, [rsp+0B8h+arg_18]
0x180059840  mov     [rsp+0B8h+var_58], rax
0x180059845  lea     rdx, aRsafullprivate; "RSAFULLPRIVATEBLOB"
0x18005984c  mov     rcx, rbx; Str1
0x18005984f  call    wcscmp_0
0x180059854  test    eax, eax
0x180059856  jnz     loc_1800598F1
0x18005985c  mov     r12d, [rsp+0B8h+cbInput]
0x180059864  lea     rax, [rsp+0B8h+var_68]
0x180059869  mov     edx, r12d
0x18005986c  mov     [rsp+0B8h+var_98], rax
0x180059871  xor     r9d, r9d
0x180059874  xor     r8d, r8d
0x180059877  mov     rcx, rbp
0x18005987a  call    ConvertRsaFullPrivateBlob
0x18005987f  mov     ebx, eax
0x180059881  test    eax, eax
0x180059883  jns     short loc_180059890
0x180059885  mov     r9d, 1375h
0x18005988b  jmp     loc_180059935
0x180059890  mov     ecx, [rsp+0B8h+var_68]
0x180059894  call    MSCryptAlloc
0x180059899  mov     rsi, rax
0x18005989c  test    rax, rax
0x18005989f  jnz     short loc_1800598B6
0x1800598a1  mov     ebx, 0C0000017h
0x1800598a6  mov     r9d, 137Eh
0x1800598ac  mov     ecx, 0C0000017h
0x1800598b1  jmp     loc_180059937
0x1800598b6  mov     r9d, [rsp+0B8h+var_68]
0x1800598bb  lea     rax, [rsp+0B8h+var_68]
0x1800598c0  mov     r8, rsi
0x1800598c3  mov     [rsp+0B8h+var_98], rax
0x1800598c8  mov     edx, r12d
0x1800598cb  mov     rcx, rbp
0x1800598ce  call    ConvertRsaFullPrivateBlob
0x1800598d3  mov     ebx, eax
0x1800598d5  test    eax, eax
0x1800598d7  jns     short loc_1800598E1
0x1800598d9  mov     r9d, 138Ah
0x1800598df  jmp     short loc_180059935
0x1800598e1  mov     ecx, [rsp+0B8h+var_68]
0x1800598e5  lea     rbx, aRsaprivateblob; "RSAPRIVATEBLOB"
0x1800598ec  mov     rax, rsi
0x1800598ef  jmp     short loc_1800598FB
0x1800598f1  mov     ecx, [rsp+0B8h+cbInput]
0x1800598f8  mov     rax, rbp
0x1800598fb  mov     edx, [rsp+0B8h+dwFlags]
0x180059902  lea     r9, [r14+10h]
0x180059906  mov     dword ptr [rsp+0B8h+var_88], edx
0x18005990a  mov     r8, rbx
0x18005990d  mov     rdx, [rsp+0B8h+var_58]
0x180059912  mov     dword ptr [rsp+0B8h+var_90], ecx
0x180059916  mov     rcx, [rdi+18h]
0x18005991a  mov     [rsp+0B8h+var_98], rax
0x18005991f  mov     rax, [rsp+0B8h+var_60]
0x180059924  call    _guard_dispatch_icall
0x180059929  mov     ebx, eax
0x18005992b  test    eax, eax
0x18005992d  jns     short loc_180059954
0x18005992f  mov     r9d, 145Ah
0x180059935  mov     ecx, eax
0x180059937  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005993e  lea     rdx, aStatus; "Status"
0x180059945  call    DebugTraceError
0x18005994a  mov     rcx, r14; P
0x18005994d  call    MSCryptFree
0x180059952  jmp     short loc_18005995E
0x180059954  mov     [r13+0], r14
0x180059958  lock inc dword ptr [rdi+10h]
0x18005995c  xor     ebx, ebx
0x18005995e  test    rsi, rsi
0x180059961  jz      short loc_18005996B
0x180059963  mov     rcx, rsi; P
0x180059966  call    MSCryptFree
0x18005996b  test    r15, r15
0x18005996e  jz      short loc_1800599A2
0x180059970  cmp     r15, rbp
0x180059973  jz      short loc_1800599A2
0x180059975  mov     rcx, r15; P
0x180059978  call    MSCryptFree
0x18005997d  jmp     short loc_1800599A2
0x18005997f  mov     ebx, 0C000000Dh
0x180059984  mov     r9d, 1302h
0x18005998a  mov     ecx, 0C000000Dh
0x18005998f  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180059996  lea     rdx, aStatus; "Status"
0x18005999d  call    DebugTraceError
0x1800599a2  mov     eax, ebx
0x1800599a4  add     rsp, 78h
0x1800599a8  pop     r15
0x1800599aa  pop     r14
0x1800599ac  pop     r13
0x1800599ae  pop     r12
0x1800599b0  pop     rdi
0x1800599b1  pop     rsi
0x1800599b2  pop     rbp
0x1800599b3  pop     rbx
0x1800599b4  retn
```

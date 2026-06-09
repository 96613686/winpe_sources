# BCryptImportKey

- ea: `0x18000d0b0`
- end: `0x18000d434`
- name: `BCryptImportKey`
- size: `900`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE hAlgorithm, BCRYPT_KEY_HANDLE hImportKey, LPCWSTR pszBlobType, BCRYPT_KEY_HANDLE *phKey, PUCHAR pbKeyObject, ULONG cbKeyObject, PUCHAR pbInput, ULONG cbInput, ULONG dwFlags)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000c9e0`

## callees

- `0x18000d0b0`
- `0x18000daf0`
- `0x18000dc30`
- `0x180010590`
- `0x18001155c`
- `0x1800123d0`
- `0x18003f910`
- `0x180065a5c`
- `0x180065ff4`
- `0x1800a4232`
- `0x1800a4300`

## string_xrefs

- `0x18000d294`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000d32d`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000d390`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000d3ca`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800a5422`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptImportKey(
        BCRYPT_ALG_HANDLE hAlgorithm,
        BCRYPT_KEY_HANDLE hImportKey,
        LPCWSTR pszBlobType,
        BCRYPT_KEY_HANDLE *phKey,
        PUCHAR pbKeyObject,
        ULONG cbKeyObject,
        PUCHAR pbInput,
        ULONG cbInput,
        ULONG dwFlags)
{
  void *v9; // rbp
  ULONG v13; // r14d
  PUCHAR v14; // rbx
  int v15; // edx
  __int64 v16; // rdi
  int v17; // r8d
  __int64 v18; // r15
  _DWORD *v19; // rsi
  __int64 (__fastcall *v20)(_QWORD, __int64, LPCWSTR, _DWORD *, unsigned __int64, int, PUCHAR, ULONG, ULONG); // r10
  int v21; // ecx
  int v22; // eax
  NTSTATUS v23; // ebx
  int v25; // eax
  __int64 v26; // rax
  __int64 v27; // r9
  __int64 v28; // r9
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rsi
  bool v32; // zf
  int v33; // eax
  size_t Size; // [rsp+30h] [rbp-98h]
  ULONG v35; // [rsp+60h] [rbp-68h] BYREF
  int v36; // [rsp+64h] [rbp-64h]
  void *v37; // [rsp+68h] [rbp-60h] BYREF
  __int64 v38; // [rsp+70h] [rbp-58h]

  v9 = 0;
  v37 = 0;
  v35 = 0;
  v13 = cbKeyObject;
  v14 = pbKeyObject;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_qqSqqdqdD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      (_DWORD)hImportKey,
      (_DWORD)pszBlobType,
      (_DWORD)hAlgorithm,
      (char)hImportKey,
      (__int64)pszBlobType,
      (char)phKey,
      (char)pbKeyObject,
      cbKeyObject,
      (char)pbInput,
      cbInput,
      dwFlags);
  v16 = ValidateBaseAlgHandle(hAlgorithm);
  if ( !v16 )
  {
    v23 = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v15,
        v17,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        36);
    return v23;
  }
  v36 = 0;
  if ( hImportKey )
  {
    v26 = ValidateBaseKeyHandle(hImportKey);
    v18 = v26;
    if ( v26 )
    {
      v31 = *(_QWORD *)(v26 + 8);
      if ( !pszBlobType || (v32 = wcscmp_0(pszBlobType, L"PKCS11RsaAesWrapBlob") == 0, v33 = 3, !v32) )
        v33 = 1;
      if ( !v31 )
      {
        v23 = -1073739510;
        v27 = 4666;
        v30 = 3221227786LL;
        goto LABEL_47;
      }
      if ( *(_DWORD *)(v31 + 36) == v33 )
      {
        if ( *(_QWORD *)(v31 + 40) != *(_QWORD *)(v16 + 40) )
        {
          if ( wcscmp_0(pszBlobType, L"Rfc3565KeyWrapBlob") )
          {
            v23 = -1073741811;
            v27 = 4687;
            v30 = 3221225485LL;
            goto LABEL_47;
          }
          v36 = 1;
        }
        v38 = *(_QWORD *)(v18 + 16);
        goto LABEL_5;
      }
      v27 = 4673;
    }
    else
    {
      v27 = 4654;
    }
    v23 = -1073741816;
    v30 = 3221225480LL;
LABEL_47:
    DebugTraceError(v30, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v27);
    return v23;
  }
  LODWORD(v18) = 0;
  v38 = 0;
LABEL_5:
  if ( !pbKeyObject && !cbKeyObject )
  {
    v25 = AllocateObjectBuffer(hAlgorithm, &v37, &v35);
    v23 = v25;
    if ( v25 < 0 )
    {
      DebugTraceError((unsigned int)v25, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 4703);
      v9 = v37;
      goto LABEL_30;
    }
    v9 = v37;
    v13 = v35;
    v14 = (PUCHAR)v37;
  }
  if ( phKey && v14 && pszBlobType )
  {
    if ( v13 < 0x3E )
    {
      v23 = -1073741789;
      goto LABEL_30;
    }
    v19 = (_DWORD *)((unsigned __int64)(v14 + 15) & 0xFFFFFFFFFFFFFFF0uLL);
    v19[1] = 1431655762;
    *((_QWORD *)v19 + 1) = v16;
    *v19 = (_DWORD)v14 - (_DWORD)v19 + v13;
    *((_QWORD *)v19 + 3) = v9;
    if ( *(_DWORD *)(v16 + 36) == 1 )
    {
      v20 = *(__int64 (__fastcall **)(_QWORD, __int64, LPCWSTR, _DWORD *, unsigned __int64, int, PUCHAR, ULONG, ULONG))(v16 + 112);
    }
    else
    {
      if ( *(_DWORD *)(v16 + 36) != 7 )
      {
        v23 = -1073741637;
        v28 = 4760;
        v29 = 3221225659LL;
LABEL_39:
        DebugTraceError(v29, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v28);
        goto LABEL_30;
      }
      v20 = *(__int64 (__fastcall **)(_QWORD, __int64, LPCWSTR, _DWORD *, unsigned __int64, int, PUCHAR, ULONG, ULONG))(v16 + 120);
    }
    v21 = (_DWORD)v14 + v13 - (((_DWORD)v19 + 47) & 0xFFFFFFF0);
    if ( v36 )
    {
      LODWORD(Size) = cbInput;
      v22 = RouterAesKeyUnwrap(v16, v18, (int)v19 + 16, ((_DWORD)v19 + 47) & 0xFFFFFFF0, v21, pbInput, Size);
      v23 = v22;
      if ( v22 >= 0 )
        goto LABEL_14;
      v28 = 4777;
    }
    else
    {
      v22 = v20(
              *(_QWORD *)(v16 + 24),
              v38,
              pszBlobType,
              v19 + 4,
              ((unsigned __int64)v19 + 47) & 0xFFFFFFFFFFFFFFF0uLL,
              v21,
              pbInput,
              cbInput,
              dwFlags);
      v23 = v22;
      if ( v22 >= 0 )
      {
LABEL_14:
        *phKey = v19;
        v23 = 0;
LABEL_15:
        _InterlockedIncrement((volatile signed __int32 *)(v16 + 16));
        return v23;
      }
      v28 = 4796;
    }
    v29 = (unsigned int)v22;
    goto LABEL_39;
  }
  v23 = -1073741811;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v15,
      v17,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
      114);
LABEL_30:
  if ( v9 )
    MSCryptFree(v9);
  if ( v23 >= 0 )
    goto LABEL_15;
  return v23;
}

```

## disassembly

```asm
0x18000d0b0  mov     [rsp+arg_18], r9
0x18000d0b5  push    rbx
0x18000d0b6  push    rbp
0x18000d0b7  push    rsi
0x18000d0b8  push    rdi
0x18000d0b9  push    r12
0x18000d0bb  push    r13
0x18000d0bd  push    r14
0x18000d0bf  push    r15
0x18000d0c1  sub     rsp, 88h
0x18000d0c8  xor     ebp, ebp
0x18000d0ca  mov     r12, r8
0x18000d0cd  mov     [rsp+0C8h+var_60], rbp
0x18000d0d2  mov     rsi, rdx
0x18000d0d5  mov     [rsp+0C8h+var_68], ebp
0x18000d0d9  mov     r13, rcx
0x18000d0dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d0e3  lea     r15, WPP_GLOBAL_Control
0x18000d0ea  mov     r14d, [rsp+0C8h+cbKeyObject]
0x18000d0f2  mov     rbx, [rsp+0C8h+pbKeyObject]
0x18000d0fa  cmp     rcx, r15
0x18000d0fd  jnz     loc_18000D21C
0x18000d103  mov     rcx, r13
0x18000d106  call    ValidateBaseAlgHandle
0x18000d10b  mov     rdi, rax
0x18000d10e  test    rax, rax
0x18000d111  jz      loc_18000D274
0x18000d117  mov     [rsp+0C8h+var_64], ebp
0x18000d11b  test    rsi, rsi
0x18000d11e  jnz     loc_18000D36B
0x18000d124  xor     r15d, r15d
0x18000d127  mov     [rsp+0C8h+var_58], rbp
0x18000d12c  test    rbx, rbx
0x18000d12f  jz      loc_18000D2C1
0x18000d135  mov     r13, [rsp+0C8h+arg_18]
0x18000d13d  test    r13, r13
0x18000d140  jz      loc_18000D30A
0x18000d146  test    rbx, rbx
0x18000d149  jz      loc_18000D30A
0x18000d14f  test    r12, r12
0x18000d152  jz      loc_18000D30A
0x18000d158  cmp     r14d, 3Eh ; '>'
0x18000d15c  jb      loc_18000D3AC
0x18000d162  lea     rsi, [rbx+0Fh]
0x18000d166  and     rsi, 0FFFFFFFFFFFFFFF0h
0x18000d16a  sub     ebx, esi
0x18000d16c  mov     dword ptr [rsi+4], 55555552h
0x18000d173  lea     edx, [rbx+r14]
0x18000d177  mov     [rsi+8], rdi
0x18000d17b  mov     [rsi], edx
0x18000d17d  mov     [rsi+18h], rbp
0x18000d181  mov     ecx, [rdi+24h]
0x18000d184  sub     ecx, 1
0x18000d187  jnz     loc_18000D2F8
0x18000d18d  mov     r10, [rdi+70h]
0x18000d191  lea     rax, [rsi+2Fh]
0x18000d195  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000d199  sub     edx, eax
0x18000d19b  cmp     [rsp+0C8h+var_64], 0
0x18000d1a0  lea     ecx, [rdx+rsi]
0x18000d1a3  jnz     loc_18000D3DB
0x18000d1a9  mov     r8d, [rsp+0C8h+dwFlags]
0x18000d1b1  lea     r9, [rsi+10h]
0x18000d1b5  mov     rdx, [rsp+0C8h+var_58]
0x18000d1ba  mov     [rsp+0C8h+var_88], r8d
0x18000d1bf  mov     r8d, [rsp+0C8h+cbInput]
0x18000d1c7  mov     dword ptr [rsp+0C8h+var_90], r8d
0x18000d1cc  mov     r8, [rsp+0C8h+pbInput]
0x18000d1d4  mov     [rsp+0C8h+Size], r8
0x18000d1d9  mov     r8, r12
0x18000d1dc  mov     dword ptr [rsp+0C8h+Src], ecx
0x18000d1e0  mov     rcx, [rdi+18h]
0x18000d1e4  mov     qword ptr [rsp+0C8h+var_A8], rax
0x18000d1e9  mov     rax, r10
0x18000d1ec  call    _guard_dispatch_icall
0x18000d1f1  mov     ebx, eax
0x18000d1f3  test    eax, eax
0x18000d1f5  js      loc_18000D41D
0x18000d1fb  mov     [r13+0], rsi
0x18000d1ff  xor     ebx, ebx
0x18000d201  lock inc dword ptr [rdi+10h]
0x18000d205  mov     eax, ebx
0x18000d207  add     rsp, 88h
0x18000d20e  pop     r15
0x18000d210  pop     r14
0x18000d212  pop     r13
0x18000d214  pop     r12
0x18000d216  pop     rdi
0x18000d217  pop     rsi
0x18000d218  pop     rbp
0x18000d219  pop     rbx
0x18000d21a  retn
0x18000d21c  mov     eax, [rcx+2Ch]
0x18000d21f  test    al, 4
0x18000d221  jz      loc_18000D103
0x18000d227  mov     eax, [rsp+0C8h+dwFlags]
0x18000d22e  mov     rcx, [rcx+18h]
0x18000d232  mov     [rsp+0C8h+var_70], eax
0x18000d236  mov     eax, [rsp+0C8h+cbInput]
0x18000d23d  mov     [rsp+0C8h+var_78], eax
0x18000d241  mov     rax, [rsp+0C8h+pbInput]
0x18000d249  mov     [rsp+0C8h+var_80], rax
0x18000d24e  mov     [rsp+0C8h+var_88], r14d
0x18000d253  mov     [rsp+0C8h+var_90], rbx
0x18000d258  mov     [rsp+0C8h+Size], r9
0x18000d25d  mov     r9, r13
0x18000d260  mov     [rsp+0C8h+Src], r12
0x18000d265  mov     qword ptr [rsp+0C8h+var_A8], rsi
0x18000d26a  call    WPP_SF_qqSqqdqdD
0x18000d26f  jmp     loc_18000D103
0x18000d274  mov     ebx, 0C0000008h
0x18000d279  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d280  cmp     rcx, r15
0x18000d283  jz      short loc_18000D205
0x18000d285  mov     eax, [rcx+2Ch]
0x18000d288  test    al, 1
0x18000d28a  jz      loc_18000D205
0x18000d290  mov     rcx, [rcx+18h]
0x18000d294  lea     rax, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d29b  mov     dword ptr [rsp+0C8h+Size], 1224h
0x18000d2a3  lea     r9, aStatus; "Status"
0x18000d2aa  mov     [rsp+0C8h+Src], rax
0x18000d2af  mov     [rsp+0C8h+var_A8], 0C0000008h
0x18000d2b7  call    WPP_SF_sDsd
0x18000d2bc  jmp     loc_18000D205
0x18000d2c1  test    r14d, r14d
0x18000d2c4  jnz     loc_18000D135
0x18000d2ca  lea     r8, [rsp+0C8h+var_68]
0x18000d2cf  mov     rcx, r13
0x18000d2d2  lea     rdx, [rsp+0C8h+var_60]
0x18000d2d7  call    AllocateObjectBuffer
0x18000d2dc  mov     ebx, eax
0x18000d2de  test    eax, eax
0x18000d2e0  js      loc_18000D38A
0x18000d2e6  mov     rbp, [rsp+0C8h+var_60]
0x18000d2eb  mov     r14d, [rsp+0C8h+var_68]
0x18000d2f0  mov     rbx, rbp
0x18000d2f3  jmp     loc_18000D135
0x18000d2f8  cmp     ecx, 6
0x18000d2fb  jnz     loc_18000D3B3
0x18000d301  mov     r10, [rdi+78h]
0x18000d305  jmp     loc_18000D191
0x18000d30a  mov     ebx, 0C000000Dh
0x18000d30f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d316  lea     rax, WPP_GLOBAL_Control
0x18000d31d  cmp     rcx, rax
0x18000d320  jz      short loc_18000D355
0x18000d322  mov     eax, [rcx+2Ch]
0x18000d325  test    al, 1
0x18000d327  jz      short loc_18000D355
0x18000d329  mov     rcx, [rcx+18h]
0x18000d32d  lea     rax, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d334  mov     dword ptr [rsp+0C8h+Size], 1272h
0x18000d33c  lea     r9, aStatus; "Status"
0x18000d343  mov     [rsp+0C8h+Src], rax
0x18000d348  mov     [rsp+0C8h+var_A8], 0C000000Dh
0x18000d350  call    WPP_SF_sDsd
0x18000d355  test    rbp, rbp
0x18000d358  jnz     loc_18000D427
0x18000d35e  test    ebx, ebx
0x18000d360  jns     loc_18000D201
0x18000d366  jmp     loc_18000D205
0x18000d36b  mov     rcx, rsi
0x18000d36e  call    ValidateBaseKeyHandle
0x18000d373  mov     r15, rax
0x18000d376  test    rax, rax
0x18000d379  jnz     loc_1800A543B
0x18000d37f  mov     r9d, 122Eh
0x18000d385  jmp     loc_1800A5406
0x18000d38a  mov     r9d, 125Fh
0x18000d390  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d397  lea     rdx, aStatus; "Status"
0x18000d39e  mov     ecx, eax
0x18000d3a0  call    DebugTraceError
0x18000d3a5  mov     rbp, [rsp+0C8h+var_60]
0x18000d3aa  jmp     short loc_18000D355
0x18000d3ac  mov     ebx, 0C0000023h
0x18000d3b1  jmp     short loc_18000D355
0x18000d3b3  mov     ebx, 0C00000BBh
0x18000d3b8  mov     r9d, 1298h
0x18000d3be  mov     ecx, 0C00000BBh
0x18000d3c3  lea     rdx, aStatus; "Status"
0x18000d3ca  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d3d1  call    DebugTraceError
0x18000d3d6  jmp     loc_18000D355
0x18000d3db  mov     r8d, [rsp+0C8h+cbInput]
0x18000d3e3  mov     r9, rax; int
0x18000d3e6  mov     dword ptr [rsp+0C8h+Size], r8d; Size
0x18000d3eb  mov     rdx, r15; int
0x18000d3ee  mov     r8, [rsp+0C8h+pbInput]
0x18000d3f6  mov     [rsp+0C8h+Src], r8; Src
0x18000d3fb  lea     r8, [rsi+10h]; int
0x18000d3ff  mov     [rsp+0C8h+var_A8], ecx; int
0x18000d403  mov     rcx, rdi; int
0x18000d406  call    RouterAesKeyUnwrap
0x18000d40b  mov     ebx, eax
0x18000d40d  test    eax, eax
0x18000d40f  jns     loc_18000D1FB
0x18000d415  mov     r9d, 12A9h
0x18000d41b  jmp     short loc_18000D423
0x18000d41d  mov     r9d, 12BCh
0x18000d423  mov     ecx, eax
0x18000d425  jmp     short loc_18000D3C3
0x18000d427  mov     rcx, rbp; P
0x18000d42a  call    MSCryptFree
0x18000d42f  jmp     loc_18000D35E
0x1800a5400  mov     r9d, 1241h
0x1800a5406  mov     ebx, 0C0000008h
0x1800a540b  mov     ecx, 0C0000008h
0x1800a5410  jmp     short loc_1800A5422
0x1800a5412  mov     ebx, 0C000000Dh
0x1800a5417  mov     r9d, 124Fh
0x1800a541d  mov     ecx, 0C000000Dh
0x1800a5422  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a5429  lea     rdx, aStatus; "Status"
0x1800a5430  call    DebugTraceError
0x1800a5435  nop
0x1800a5436  jmp     loc_18000D205
0x1800a543b  mov     rsi, [rax+8]
0x1800a543f  test    r12, r12
0x1800a5442  jz      short loc_1800A545C
0x1800a5444  lea     rdx, aPkcs11rsaaeswr; "PKCS11RsaAesWrapBlob"
0x1800a544b  mov     rcx, r12; Str1
0x1800a544e  call    wcscmp_0
0x1800a5453  test    eax, eax
0x1800a5455  mov     eax, 3
0x1800a545a  jz      short loc_1800A5461
0x1800a545c  mov     eax, 1
0x1800a5461  test    rsi, rsi
0x1800a5464  jnz     short loc_1800A5478
0x1800a5466  mov     ebx, 0C000090Ah
0x1800a546b  mov     r9d, 123Ah
0x1800a5471  mov     ecx, 0C000090Ah
0x1800a5476  jmp     short loc_1800A5422
0x1800a5478  cmp     [rsi+24h], eax
0x1800a547b  jnz     short loc_1800A5400
0x1800a547d  mov     rax, [rdi+28h]
0x1800a5481  cmp     [rsi+28h], rax
0x1800a5485  jz      short loc_1800A54A6
0x1800a5487  lea     rdx, aRfc3565keywrap; "Rfc3565KeyWrapBlob"
0x1800a548e  mov     rcx, r12; Str1
0x1800a5491  call    wcscmp_0
0x1800a5496  test    eax, eax
0x1800a5498  jnz     loc_1800A5412
0x1800a549e  mov     [rsp+0C8h+var_64], 1
0x1800a54a6  mov     rax, [r15+10h]
0x1800a54aa  mov     [rsp+0C8h+var_58], rax
0x1800a54af  jmp     loc_18000D12C
```

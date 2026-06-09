# BCryptImportKey

- ea: `0x180002f90`
- end: `0x180003314`
- name: `BCryptImportKey`
- size: `900`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE hAlgorithm, BCRYPT_KEY_HANDLE hImportKey, LPCWSTR pszBlobType, BCRYPT_KEY_HANDLE *phKey, PUCHAR pbKeyObject, ULONG cbKeyObject, PUCHAR pbInput, ULONG cbInput, ULONG dwFlags)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800028c0`

## callees

- `0x180002f90`
- `0x1800039d0`
- `0x180003b10`
- `0x180006470`
- `0x18000743c`
- `0x1800082b0`
- `0x1800358a0`
- `0x18005b88c`
- `0x18005be24`
- `0x18009d746`
- `0x18009d860`

## string_xrefs

- `0x180003174`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000320d`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180003270`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800032aa`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18009e684`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
0x180002f90  mov     [rsp+arg_18], r9
0x180002f95  push    rbx
0x180002f96  push    rbp
0x180002f97  push    rsi
0x180002f98  push    rdi
0x180002f99  push    r12
0x180002f9b  push    r13
0x180002f9d  push    r14
0x180002f9f  push    r15
0x180002fa1  sub     rsp, 88h
0x180002fa8  xor     ebp, ebp
0x180002faa  mov     r12, r8
0x180002fad  mov     [rsp+0C8h+var_60], rbp
0x180002fb2  mov     rsi, rdx
0x180002fb5  mov     [rsp+0C8h+var_68], ebp
0x180002fb9  mov     r13, rcx
0x180002fbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180002fc3  lea     r15, WPP_GLOBAL_Control
0x180002fca  mov     r14d, [rsp+0C8h+cbKeyObject]
0x180002fd2  mov     rbx, [rsp+0C8h+pbKeyObject]
0x180002fda  cmp     rcx, r15
0x180002fdd  jnz     loc_1800030FC
0x180002fe3  mov     rcx, r13
0x180002fe6  call    ValidateBaseAlgHandle
0x180002feb  mov     rdi, rax
0x180002fee  test    rax, rax
0x180002ff1  jz      loc_180003154
0x180002ff7  mov     [rsp+0C8h+var_64], ebp
0x180002ffb  test    rsi, rsi
0x180002ffe  jnz     loc_18000324B
0x180003004  xor     r15d, r15d
0x180003007  mov     [rsp+0C8h+var_58], rbp
0x18000300c  test    rbx, rbx
0x18000300f  jz      loc_1800031A1
0x180003015  mov     r13, [rsp+0C8h+arg_18]
0x18000301d  test    r13, r13
0x180003020  jz      loc_1800031EA
0x180003026  test    rbx, rbx
0x180003029  jz      loc_1800031EA
0x18000302f  test    r12, r12
0x180003032  jz      loc_1800031EA
0x180003038  cmp     r14d, 3Eh ; '>'
0x18000303c  jb      loc_18000328C
0x180003042  lea     rsi, [rbx+0Fh]
0x180003046  and     rsi, 0FFFFFFFFFFFFFFF0h
0x18000304a  sub     ebx, esi
0x18000304c  mov     dword ptr [rsi+4], 55555552h
0x180003053  lea     edx, [rbx+r14]
0x180003057  mov     [rsi+8], rdi
0x18000305b  mov     [rsi], edx
0x18000305d  mov     [rsi+18h], rbp
0x180003061  mov     ecx, [rdi+24h]
0x180003064  sub     ecx, 1
0x180003067  jnz     loc_1800031D8
0x18000306d  mov     r10, [rdi+70h]
0x180003071  lea     rax, [rsi+2Fh]
0x180003075  and     rax, 0FFFFFFFFFFFFFFF0h
0x180003079  sub     edx, eax
0x18000307b  cmp     [rsp+0C8h+var_64], 0
0x180003080  lea     ecx, [rdx+rsi]
0x180003083  jnz     loc_1800032BB
0x180003089  mov     r8d, [rsp+0C8h+dwFlags]
0x180003091  lea     r9, [rsi+10h]
0x180003095  mov     rdx, [rsp+0C8h+var_58]
0x18000309a  mov     [rsp+0C8h+var_88], r8d
0x18000309f  mov     r8d, [rsp+0C8h+cbInput]
0x1800030a7  mov     dword ptr [rsp+0C8h+var_90], r8d
0x1800030ac  mov     r8, [rsp+0C8h+pbInput]
0x1800030b4  mov     [rsp+0C8h+Size], r8
0x1800030b9  mov     r8, r12
0x1800030bc  mov     dword ptr [rsp+0C8h+Src], ecx
0x1800030c0  mov     rcx, [rdi+18h]
0x1800030c4  mov     qword ptr [rsp+0C8h+var_A8], rax
0x1800030c9  mov     rax, r10
0x1800030cc  call    _guard_dispatch_icall
0x1800030d1  mov     ebx, eax
0x1800030d3  test    eax, eax
0x1800030d5  js      loc_1800032FD
0x1800030db  mov     [r13+0], rsi
0x1800030df  xor     ebx, ebx
0x1800030e1  lock inc dword ptr [rdi+10h]
0x1800030e5  mov     eax, ebx
0x1800030e7  add     rsp, 88h
0x1800030ee  pop     r15
0x1800030f0  pop     r14
0x1800030f2  pop     r13
0x1800030f4  pop     r12
0x1800030f6  pop     rdi
0x1800030f7  pop     rsi
0x1800030f8  pop     rbp
0x1800030f9  pop     rbx
0x1800030fa  retn
0x1800030fc  mov     eax, [rcx+2Ch]
0x1800030ff  test    al, 4
0x180003101  jz      loc_180002FE3
0x180003107  mov     eax, [rsp+0C8h+dwFlags]
0x18000310e  mov     rcx, [rcx+18h]
0x180003112  mov     [rsp+0C8h+var_70], eax
0x180003116  mov     eax, [rsp+0C8h+cbInput]
0x18000311d  mov     [rsp+0C8h+var_78], eax
0x180003121  mov     rax, [rsp+0C8h+pbInput]
0x180003129  mov     [rsp+0C8h+var_80], rax
0x18000312e  mov     [rsp+0C8h+var_88], r14d
0x180003133  mov     [rsp+0C8h+var_90], rbx
0x180003138  mov     [rsp+0C8h+Size], r9
0x18000313d  mov     r9, r13
0x180003140  mov     [rsp+0C8h+Src], r12
0x180003145  mov     qword ptr [rsp+0C8h+var_A8], rsi
0x18000314a  call    WPP_SF_qqSqqdqdD
0x18000314f  jmp     loc_180002FE3
0x180003154  mov     ebx, 0C0000008h
0x180003159  mov     rcx, cs:WPP_GLOBAL_Control
0x180003160  cmp     rcx, r15
0x180003163  jz      short loc_1800030E5
0x180003165  mov     eax, [rcx+2Ch]
0x180003168  test    al, 1
0x18000316a  jz      loc_1800030E5
0x180003170  mov     rcx, [rcx+18h]
0x180003174  lea     rax, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000317b  mov     dword ptr [rsp+0C8h+Size], 1224h
0x180003183  lea     r9, aStatus; "Status"
0x18000318a  mov     [rsp+0C8h+Src], rax
0x18000318f  mov     [rsp+0C8h+var_A8], 0C0000008h
0x180003197  call    WPP_SF_sDsd
0x18000319c  jmp     loc_1800030E5
0x1800031a1  test    r14d, r14d
0x1800031a4  jnz     loc_180003015
0x1800031aa  lea     r8, [rsp+0C8h+var_68]
0x1800031af  mov     rcx, r13
0x1800031b2  lea     rdx, [rsp+0C8h+var_60]
0x1800031b7  call    AllocateObjectBuffer
0x1800031bc  mov     ebx, eax
0x1800031be  test    eax, eax
0x1800031c0  js      loc_18000326A
0x1800031c6  mov     rbp, [rsp+0C8h+var_60]
0x1800031cb  mov     r14d, [rsp+0C8h+var_68]
0x1800031d0  mov     rbx, rbp
0x1800031d3  jmp     loc_180003015
0x1800031d8  cmp     ecx, 6
0x1800031db  jnz     loc_180003293
0x1800031e1  mov     r10, [rdi+78h]
0x1800031e5  jmp     loc_180003071
0x1800031ea  mov     ebx, 0C000000Dh
0x1800031ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031f6  lea     rax, WPP_GLOBAL_Control
0x1800031fd  cmp     rcx, rax
0x180003200  jz      short loc_180003235
0x180003202  mov     eax, [rcx+2Ch]
0x180003205  test    al, 1
0x180003207  jz      short loc_180003235
0x180003209  mov     rcx, [rcx+18h]
0x18000320d  lea     rax, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003214  mov     dword ptr [rsp+0C8h+Size], 1272h
0x18000321c  lea     r9, aStatus; "Status"
0x180003223  mov     [rsp+0C8h+Src], rax
0x180003228  mov     [rsp+0C8h+var_A8], 0C000000Dh
0x180003230  call    WPP_SF_sDsd
0x180003235  test    rbp, rbp
0x180003238  jnz     loc_180003307
0x18000323e  test    ebx, ebx
0x180003240  jns     loc_1800030E1
0x180003246  jmp     loc_1800030E5
0x18000324b  mov     rcx, rsi
0x18000324e  call    ValidateBaseKeyHandle
0x180003253  mov     r15, rax
0x180003256  test    rax, rax
0x180003259  jnz     loc_18009E69D
0x18000325f  mov     r9d, 122Eh
0x180003265  jmp     loc_18009E668
0x18000326a  mov     r9d, 125Fh
0x180003270  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003277  lea     rdx, aStatus; "Status"
0x18000327e  mov     ecx, eax
0x180003280  call    DebugTraceError
0x180003285  mov     rbp, [rsp+0C8h+var_60]
0x18000328a  jmp     short loc_180003235
0x18000328c  mov     ebx, 0C0000023h
0x180003291  jmp     short loc_180003235
0x180003293  mov     ebx, 0C00000BBh
0x180003298  mov     r9d, 1298h
0x18000329e  mov     ecx, 0C00000BBh
0x1800032a3  lea     rdx, aStatus; "Status"
0x1800032aa  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800032b1  call    DebugTraceError
0x1800032b6  jmp     loc_180003235
0x1800032bb  mov     r8d, [rsp+0C8h+cbInput]
0x1800032c3  mov     r9, rax; int
0x1800032c6  mov     dword ptr [rsp+0C8h+Size], r8d; Size
0x1800032cb  mov     rdx, r15; int
0x1800032ce  mov     r8, [rsp+0C8h+pbInput]
0x1800032d6  mov     [rsp+0C8h+Src], r8; Src
0x1800032db  lea     r8, [rsi+10h]; int
0x1800032df  mov     [rsp+0C8h+var_A8], ecx; int
0x1800032e3  mov     rcx, rdi; int
0x1800032e6  call    RouterAesKeyUnwrap
0x1800032eb  mov     ebx, eax
0x1800032ed  test    eax, eax
0x1800032ef  jns     loc_1800030DB
0x1800032f5  mov     r9d, 12A9h
0x1800032fb  jmp     short loc_180003303
0x1800032fd  mov     r9d, 12BCh
0x180003303  mov     ecx, eax
0x180003305  jmp     short loc_1800032A3
0x180003307  mov     rcx, rbp; P
0x18000330a  call    MSCryptFree
0x18000330f  jmp     loc_18000323E
0x18009e662  mov     r9d, 1241h
0x18009e668  mov     ebx, 0C0000008h
0x18009e66d  mov     ecx, 0C0000008h
0x18009e672  jmp     short loc_18009E684
0x18009e674  mov     ebx, 0C000000Dh
0x18009e679  mov     r9d, 124Fh
0x18009e67f  mov     ecx, 0C000000Dh
0x18009e684  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18009e68b  lea     rdx, aStatus; "Status"
0x18009e692  call    DebugTraceError
0x18009e697  nop
0x18009e698  jmp     loc_1800030E5
0x18009e69d  mov     rsi, [rax+8]
0x18009e6a1  test    r12, r12
0x18009e6a4  jz      short loc_18009E6BE
0x18009e6a6  lea     rdx, aPkcs11rsaaeswr; "PKCS11RsaAesWrapBlob"
0x18009e6ad  mov     rcx, r12; Str1
0x18009e6b0  call    wcscmp_0
0x18009e6b5  test    eax, eax
0x18009e6b7  mov     eax, 3
0x18009e6bc  jz      short loc_18009E6C3
0x18009e6be  mov     eax, 1
0x18009e6c3  test    rsi, rsi
0x18009e6c6  jnz     short loc_18009E6DA
0x18009e6c8  mov     ebx, 0C000090Ah
0x18009e6cd  mov     r9d, 123Ah
0x18009e6d3  mov     ecx, 0C000090Ah
0x18009e6d8  jmp     short loc_18009E684
0x18009e6da  cmp     [rsi+24h], eax
0x18009e6dd  jnz     short loc_18009E662
0x18009e6df  mov     rax, [rdi+28h]
0x18009e6e3  cmp     [rsi+28h], rax
0x18009e6e7  jz      short loc_18009E708
0x18009e6e9  lea     rdx, aRfc3565keywrap; "Rfc3565KeyWrapBlob"
0x18009e6f0  mov     rcx, r12; Str1
0x18009e6f3  call    wcscmp_0
0x18009e6f8  test    eax, eax
0x18009e6fa  jnz     loc_18009E674
0x18009e700  mov     [rsp+0C8h+var_64], 1
0x18009e708  mov     rax, [r15+10h]
0x18009e70c  mov     [rsp+0C8h+var_58], rax
0x18009e711  jmp     loc_18000300C
```

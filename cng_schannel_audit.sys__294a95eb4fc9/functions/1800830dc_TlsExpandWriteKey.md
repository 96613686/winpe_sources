# TlsExpandWriteKey

- ea: `0x1800830dc`
- end: `0x1800833ca`
- name: `TlsExpandWriteKey`
- size: `750`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180081a10`

## callees

- `0x1800020c0`
- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x180035540`
- `0x180037730`
- `0x180082ee4`
- `0x1800830dc`
- `0x18009dd40`

## string_xrefs

- `0x18008317e`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180083349`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall TlsExpandWriteKey(__int64 a1, __int64 a2, _QWORD *a3)
{
  void *v3; // r13
  UCHAR *pbSecret; // rbp
  __int64 v6; // r14
  __int64 cbSecret; // r15
  __int64 v8; // r12
  __int64 v9; // r9
  __int64 v10; // rdi
  int CipherEntry; // eax
  unsigned int v12; // ebx
  __int64 v13; // r9
  __int64 v14; // rcx
  ULONG v15; // r13d
  ULONG v16; // ebx
  void *v17; // rax
  void *v18; // rdi
  ULONG v19; // esi
  __int64 v20; // rcx
  __int64 v21; // r9
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rax
  int v25; // eax
  NTSTATUS SymmetricKey; // eax
  int v27; // eax
  __int64 v28; // rcx
  _BYTE *v29; // rax
  __int64 v30; // rcx
  UCHAR *v31; // rax
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+40h] [rbp-48h]
  ULONG v34; // [rsp+90h] [rbp+8h]

  v3 = 0;
  pbSecret = 0;
  if ( a1 && a2 && (v6 = *(_QWORD *)(a2 + 16)) != 0 && a3 )
  {
    cbSecret = *(unsigned int *)(v6 + 32);
    if ( (unsigned int)cbSecret > 0xFFFF || (v8 = *(_QWORD *)(a2 + 32)) == 0 )
    {
      v12 = -2146893785;
      v13 = 4237;
      v14 = 2148073511LL;
      goto LABEL_10;
    }
    v9 = *(unsigned int *)(v6 + 40);
    v10 = a1 + 16 * (v9 + 1);
    if ( !*(_DWORD *)(v10 + 12) )
    {
      CipherEntry = I_GetCipherEntry((unsigned int)v9, *(unsigned int *)(a1 + 12), a1 + 16 * (v9 + 1));
      v12 = CipherEntry;
      if ( CipherEntry < 0 )
      {
        v13 = 4250;
        v14 = (unsigned int)CipherEntry;
LABEL_10:
        DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", v13);
        return v12;
      }
    }
    v15 = *(_DWORD *)(v10 + 8);
    if ( !v15 || (hAlgorithm = *(BCRYPT_ALG_HANDLE *)v10) == 0 )
    {
      v12 = -2146893783;
      v13 = 4258;
      v14 = 2148073513LL;
      goto LABEL_10;
    }
    v16 = v15 + 112;
    v34 = v15 + 112;
    v17 = (void *)MSCryptAlloc(v15 + 112, a2);
    v18 = v17;
    if ( !v17 )
    {
      v19 = v15 + 112;
      v12 = -2146893810;
      v20 = 2148073486LL;
      v21 = 4268;
      v3 = 0;
      goto LABEL_28;
    }
    memset(v17, 0, v16);
    *(_DWORD *)v18 = v16;
    *((_DWORD *)v18 + 1) = 1936944179;
    v22 = *(_DWORD *)(a2 + 8);
    *((_QWORD *)v18 + 2) = v6;
    *((_DWORD *)v18 + 26) = 12;
    *((_DWORD *)v18 + 2) = v22;
    *((_DWORD *)v18 + 27) = 5;
    v24 = MSCryptAlloc(cbSecret, v23);
    pbSecret = (UCHAR *)v24;
    if ( !v24 )
    {
      v12 = -2146893810;
      v20 = 2148073486LL;
      v21 = 4285;
LABEL_17:
      v19 = v15 + 112;
      v3 = 0;
      goto LABEL_28;
    }
    v25 = TlsExpandLabel(v8, "key", 0, 0, v24, cbSecret);
    v12 = v25;
    if ( v25 < 0 )
    {
      v20 = (unsigned int)v25;
      v21 = 4297;
      goto LABEL_17;
    }
    SymmetricKey = BCryptGenerateSymmetricKey(
                     hAlgorithm,
                     (BCRYPT_KEY_HANDLE *)v18 + 4,
                     (PUCHAR)v18 + 112,
                     v15,
                     pbSecret,
                     cbSecret,
                     0);
    v12 = SymmetricKey;
    if ( SymmetricKey < 0 )
    {
      v20 = (unsigned int)SymmetricKey;
      v21 = 4312;
      goto LABEL_17;
    }
    v3 = (void *)*((_QWORD *)v18 + 4);
    v27 = TlsExpandLabel(v8, "iv", 0, 0, (__int64)v18 + 56, 0xCu);
    v12 = v27;
    if ( v27 >= 0 )
    {
      *a3 = v18;
LABEL_35:
      v30 = (unsigned int)cbSecret;
      v31 = pbSecret;
      if ( (_DWORD)cbSecret )
      {
        do
        {
          *v31++ = 0;
          --v30;
        }
        while ( v30 );
      }
      MSCryptFree(pbSecret);
      return v12;
    }
    v19 = v34;
    v20 = (unsigned int)v27;
    v21 = 4327;
  }
  else
  {
    v18 = 0;
    v19 = 0;
    LODWORD(cbSecret) = 0;
    v12 = -2146893785;
    v20 = 2148073511LL;
    v21 = 4228;
  }
LABEL_28:
  DebugTraceError(v20, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", v21);
  if ( v18 )
  {
    if ( v3 )
      BCryptDestroyKey(v3);
    v28 = v19;
    v29 = v18;
    if ( v19 )
    {
      do
      {
        *v29++ = 0;
        --v28;
      }
      while ( v28 );
    }
    MSCryptFree(v18);
  }
  if ( pbSecret )
    goto LABEL_35;
  return v12;
}

```

## disassembly

```asm
0x1800830dc  mov     [rsp+arg_8], rbx
0x1800830e1  mov     [rsp+arg_10], r8
0x1800830e6  push    rbp
0x1800830e7  push    rsi
0x1800830e8  push    rdi
0x1800830e9  push    r12
0x1800830eb  push    r13
0x1800830ed  push    r14
0x1800830ef  push    r15
0x1800830f1  sub     rsp, 50h
0x1800830f5  xor     r13d, r13d
0x1800830f8  xor     ebp, ebp
0x1800830fa  mov     [rsp+88h+arg_18], r13
0x180083102  mov     rax, r8
0x180083105  mov     rsi, rdx
0x180083108  test    rcx, rcx
0x18008310b  jz      loc_180083332
0x180083111  test    rdx, rdx
0x180083114  jz      loc_180083332
0x18008311a  mov     r14, [rdx+10h]
0x18008311e  test    r14, r14
0x180083121  jz      loc_180083332
0x180083127  test    rax, rax
0x18008312a  jz      loc_180083332
0x180083130  mov     r15d, [r14+20h]
0x180083134  cmp     r15d, 0FFFFh
0x18008313b  ja      loc_18008331D
0x180083141  mov     r12, [rdx+20h]
0x180083145  test    r12, r12
0x180083148  jz      loc_18008331D
0x18008314e  mov     r9d, [r14+28h]
0x180083152  lea     rdi, [r9+1]
0x180083156  shl     rdi, 4
0x18008315a  add     rdi, rcx
0x18008315d  cmp     [rdi+0Ch], ebp
0x180083160  jnz     short loc_180083196
0x180083162  mov     edx, [rcx+0Ch]
0x180083165  mov     r8, rdi
0x180083168  mov     ecx, r9d
0x18008316b  call    I_GetCipherEntry
0x180083170  mov     ebx, eax
0x180083172  test    eax, eax
0x180083174  jns     short loc_180083196
0x180083176  mov     r9d, 109Ah
0x18008317c  mov     ecx, eax
0x18008317e  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180083185  lea     rdx, aStatus; "Status"
0x18008318c  call    DebugTraceError
0x180083191  jmp     loc_1800833AF
0x180083196  mov     r13d, [rdi+8]
0x18008319a  test    r13d, r13d
0x18008319d  jz      loc_180083308
0x1800831a3  mov     rax, [rdi]
0x1800831a6  mov     [rsp+88h+hAlgorithm], rax
0x1800831ab  test    rax, rax
0x1800831ae  jz      loc_180083308
0x1800831b4  lea     ebx, [r13+70h]
0x1800831b8  mov     ecx, ebx
0x1800831ba  mov     [rsp+88h+arg_0], ebx
0x1800831c1  call    MSCryptAlloc
0x1800831c6  mov     rdi, rax
0x1800831c9  test    rax, rax
0x1800831cc  jnz     short loc_1800831ED
0x1800831ce  mov     esi, [rsp+88h+arg_0]
0x1800831d5  mov     ebx, 8009000Eh
0x1800831da  mov     ecx, 8009000Eh
0x1800831df  mov     r9d, 10ACh
0x1800831e5  mov     r13, rbp
0x1800831e8  jmp     loc_180083349
0x1800831ed  mov     r8d, ebx; Size
0x1800831f0  xor     edx, edx; Val
0x1800831f2  mov     rcx, rdi; void *
0x1800831f5  call    memset
0x1800831fa  mov     [rdi], ebx
0x1800831fc  mov     rcx, r15
0x1800831ff  mov     dword ptr [rdi+4], 73736C33h
0x180083206  mov     eax, [rsi+8]
0x180083209  mov     [rdi+10h], r14
0x18008320d  mov     r14d, 0Ch
0x180083213  mov     [rdi+68h], r14d
0x180083217  mov     [rdi+8], eax
0x18008321a  mov     dword ptr [rdi+6Ch], 5
0x180083221  call    MSCryptAlloc
0x180083226  mov     rbp, rax
0x180083229  test    rax, rax
0x18008322c  jnz     short loc_180083252
0x18008322e  mov     ebx, 8009000Eh
0x180083233  mov     ecx, 8009000Eh
0x180083238  mov     r9d, 10BDh
0x18008323e  mov     esi, [rsp+88h+arg_0]
0x180083245  mov     r13, [rsp+88h+arg_18]
0x18008324d  jmp     loc_180083349
0x180083252  mov     word ptr [rsp+88h+cbSecret], r15w
0x180083258  lea     rdx, aKey; "key"
0x18008325f  xor     r9d, r9d
0x180083262  mov     [rsp+88h+pbSecret], rbp
0x180083267  xor     r8d, r8d
0x18008326a  mov     rcx, r12
0x18008326d  call    TlsExpandLabel
0x180083272  mov     ebx, eax
0x180083274  test    eax, eax
0x180083276  jns     short loc_180083282
0x180083278  mov     ecx, eax
0x18008327a  mov     r9d, 10C9h
0x180083280  jmp     short loc_18008323E
0x180083282  mov     rcx, [rsp+88h+hAlgorithm]; hAlgorithm
0x180083287  lea     r8, [rdi+70h]; pbKeyObject
0x18008328b  mov     [rsp+88h+dwFlags], 0; dwFlags
0x180083293  lea     rdx, [rdi+20h]; phKey
0x180083297  mov     [rsp+88h+cbSecret], r15d; cbSecret
0x18008329c  mov     r9d, r13d; cbKeyObject
0x18008329f  mov     [rsp+88h+pbSecret], rbp; pbSecret
0x1800832a4  call    BCryptGenerateSymmetricKey
0x1800832a9  mov     ebx, eax
0x1800832ab  test    eax, eax
0x1800832ad  jns     short loc_1800832B9
0x1800832af  mov     ecx, eax
0x1800832b1  mov     r9d, 10D8h
0x1800832b7  jmp     short loc_18008323E
0x1800832b9  mov     r13, [rdi+20h]
0x1800832bd  lea     rax, [rdi+38h]
0x1800832c1  mov     word ptr [rsp+88h+cbSecret], r14w
0x1800832c7  lea     rdx, aIv; "iv"
0x1800832ce  xor     r9d, r9d
0x1800832d1  mov     [rsp+88h+pbSecret], rax
0x1800832d6  xor     r8d, r8d
0x1800832d9  mov     rcx, r12
0x1800832dc  call    TlsExpandLabel
0x1800832e1  mov     ebx, eax
0x1800832e3  test    eax, eax
0x1800832e5  jns     short loc_1800832F8
0x1800832e7  mov     esi, [rsp+88h+arg_0]
0x1800832ee  mov     ecx, eax
0x1800832f0  mov     r9d, 10E7h
0x1800832f6  jmp     short loc_180083349
0x1800832f8  mov     rax, [rsp+88h+arg_10]
0x180083300  mov     [rax], rdi
0x180083303  jmp     loc_180083390
0x180083308  mov     ebx, 80090029h
0x18008330d  mov     r9d, 10A2h
0x180083313  mov     ecx, 80090029h
0x180083318  jmp     loc_18008317E
0x18008331d  mov     ebx, 80090027h
0x180083322  mov     r9d, 108Dh
0x180083328  mov     ecx, 80090027h
0x18008332d  jmp     loc_18008317E
0x180083332  xor     edi, edi
0x180083334  xor     esi, esi
0x180083336  xor     r15d, r15d
0x180083339  mov     ebx, 80090027h
0x18008333e  mov     ecx, 80090027h
0x180083343  mov     r9d, 1084h
0x180083349  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180083350  lea     rdx, aStatus; "Status"
0x180083357  call    DebugTraceError
0x18008335c  test    rdi, rdi
0x18008335f  jz      short loc_18008338B
0x180083361  test    r13, r13
0x180083364  jz      short loc_18008336E
0x180083366  mov     rcx, r13; hKey
0x180083369  call    BCryptDestroyKey
0x18008336e  mov     ecx, esi
0x180083370  mov     rax, rdi
0x180083373  test    esi, esi
0x180083375  jz      short loc_180083383
0x180083377  mov     byte ptr [rax], 0
0x18008337a  inc     rax
0x18008337d  sub     rcx, 1
0x180083381  jnz     short loc_180083377
0x180083383  mov     rcx, rdi; P
0x180083386  call    MSCryptFree
0x18008338b  test    rbp, rbp
0x18008338e  jz      short loc_1800833AF
0x180083390  mov     ecx, r15d
0x180083393  mov     rax, rbp
0x180083396  test    r15d, r15d
0x180083399  jz      short loc_1800833A7
0x18008339b  mov     byte ptr [rax], 0
0x18008339e  inc     rax
0x1800833a1  sub     rcx, 1
0x1800833a5  jnz     short loc_18008339B
0x1800833a7  mov     rcx, rbp; P
0x1800833aa  call    MSCryptFree
0x1800833af  mov     eax, ebx
0x1800833b1  mov     rbx, [rsp+88h+arg_8]
0x1800833b9  add     rsp, 50h
0x1800833bd  pop     r15
0x1800833bf  pop     r14
0x1800833c1  pop     r13
0x1800833c3  pop     r12
0x1800833c5  pop     rdi
0x1800833c6  pop     rsi
0x1800833c7  pop     rbp
0x1800833c8  retn
```

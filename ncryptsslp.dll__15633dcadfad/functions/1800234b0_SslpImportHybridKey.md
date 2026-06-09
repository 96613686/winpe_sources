# SslpImportHybridKey

- ea: `0x1800234b0`
- end: `0x18002379a`
- name: `SslpImportHybridKey`
- size: `746`
- prototype: `__int64 __fastcall(__int64, unsigned int, const wchar_t *, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180001010`

## callees

- `0x180003ef0`
- `0x18000b654`
- `0x180013e6c`
- `0x1800185e0`
- `0x180021778`
- `0x180022164`
- `0x1800222f0`
- `0x180022420`
- `0x180022608`
- `0x180022ca4`
- `0x180023234`
- `0x1800234b0`

## string_xrefs

- `0x18002353b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`
- `0x180023608`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`
- `0x18002364c`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`
- `0x18002369f`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`
- `0x180023732`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`

## pseudocode

```c
__int64 __fastcall SslpImportHybridKey(__int64 a1, unsigned int a2, const wchar_t *a3, _QWORD *a4)
{
  __int64 v4; // rsi
  __int64 v5; // r12
  PBYTE v6; // r15
  PBYTE v7; // rdi
  unsigned int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rcx
  const wchar_t *v14; // r15
  const wchar_t *v15; // rdi
  __int64 v16; // rcx
  int v17; // eax
  const WCHAR *v18; // r8
  int v19; // eax
  const WCHAR *v20; // r8
  int v21; // eax
  int v22; // ecx
  __int64 v23; // r9
  int BaseHybridKeyStruct; // eax
  __int64 v25; // rcx
  __int64 v26; // r9
  DWORD cbData; // [rsp+40h] [rbp-38h] BYREF
  PBYTE v29; // [rsp+48h] [rbp-30h] BYREF
  __int64 v30; // [rsp+50h] [rbp-28h] BYREF
  PBYTE pbData; // [rsp+58h] [rbp-20h] BYREF
  __int64 v32; // [rsp+60h] [rbp-18h] BYREF
  __int64 v33; // [rsp+68h] [rbp-10h] BYREF
  DWORD v34; // [rsp+C0h] [rbp+48h] BYREF

  v4 = 0;
  v33 = 0;
  v5 = 0;
  v30 = 0;
  v6 = 0;
  v32 = 0;
  v7 = 0;
  pbData = 0;
  v29 = 0;
  if ( !a1 || !a2 || !a3 || !a4 )
  {
    v11 = -2146893785;
    v25 = 2148073511LL;
    v26 = 1138;
    goto LABEL_31;
  }
  if ( wcscmp(a3, L"TLS_HYBRID_KEY") )
  {
    v11 = -2146893783;
    v12 = 1145;
    v13 = 2148073513LL;
LABEL_7:
    DebugTraceError(v13, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c", v12);
    return v11;
  }
  if ( a2 < 0x20 )
  {
    v12 = 1152;
LABEL_10:
    v11 = -2146893819;
    v13 = 2148073477LL;
    goto LABEL_7;
  }
  if ( *(_DWORD *)a1 != 1213418580 )
  {
    v12 = 1161;
    goto LABEL_10;
  }
  v14 = *(const wchar_t **)(a1 + 8);
  if ( wcscmp(v14, L"SSLECCPUBLICBLOB")
    || (v15 = *(const wchar_t **)(a1 + 16), wcscmp(v15, L"MLKEMPUBLICBLOB")) && wcscmp(v15, L"TLS_KEM_CIPHERTEXT") )
  {
    v12 = 1172;
    goto LABEL_10;
  }
  v16 = *(unsigned __int16 *)(a1 + 4);
  cbData = 0;
  v34 = 0;
  v17 = SslpConstructConstituentKeysFromKeyShare(v16, a1 + 32, a2 - 32, v15, &pbData, &cbData, &v29, &v34);
  v11 = v17;
  if ( v17 >= 0 )
  {
    v18 = v14;
    v6 = pbData;
    v19 = SslpImportEphemeralKeyWithNCrypt(pbData, cbData, v18, &v33);
    v11 = v19;
    if ( v19 < 0 )
    {
      DebugTraceError(
        (unsigned int)v19,
        "status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c",
        1204);
      v7 = v29;
LABEL_33:
      if ( v33 )
        SslpFreeEphemeralKey(v33);
      if ( v4 )
        SslpFreeKemKey(v4);
      goto LABEL_37;
    }
    if ( !wcscmp(v15, L"MLKEMPUBLICBLOB") )
    {
      v20 = v15;
      v7 = v29;
      v21 = SslpImportKemKeyWithNCrypt(v29, v34, v20, &v30);
      v11 = v21;
      if ( v21 < 0 )
      {
        v23 = 1217;
LABEL_23:
        DebugTraceError(
          (unsigned int)v21,
          "status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c",
          v23);
        v4 = v30;
        goto LABEL_33;
      }
    }
    else
    {
      v7 = v29;
      v21 = SslpImportKemCipherText(v29, v34, &v30);
      v11 = v21;
      if ( v21 < 0 )
      {
        v23 = 1229;
        goto LABEL_23;
      }
    }
    v4 = v30;
    BaseHybridKeyStruct = SslpCreateBaseHybridKeyStruct(v22, *(unsigned __int16 *)(a1 + 4), v33, v30, (__int64)&v32);
    v11 = BaseHybridKeyStruct;
    if ( BaseHybridKeyStruct >= 0 )
    {
      *a4 = v32;
      goto LABEL_33;
    }
    v5 = v32;
    v25 = (unsigned int)BaseHybridKeyStruct;
    v26 = 1246;
LABEL_31:
    DebugTraceError(v25, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c", v26);
    if ( v5 )
      SslpFreeHybridKey(v5);
    goto LABEL_33;
  }
  DebugTraceError((unsigned int)v17, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c", 1193);
  v6 = pbData;
  v7 = v29;
LABEL_37:
  if ( v6 )
    MSCryptFree(v6);
  if ( v7 )
    MSCryptFree(v7);
  return v11;
}

```

## disassembly

```asm
0x1800234b0  push    rbp
0x1800234b2  push    rbx
0x1800234b3  push    rsi
0x1800234b4  push    rdi
0x1800234b5  push    r12
0x1800234b7  push    r13
0x1800234b9  push    r14
0x1800234bb  push    r15
0x1800234bd  mov     rbp, rsp
0x1800234c0  sub     rsp, 78h
0x1800234c4  xor     esi, esi
0x1800234c6  mov     [rbp+var_10], 0
0x1800234ce  xor     r12d, r12d
0x1800234d1  mov     [rbp+var_28], rsi
0x1800234d5  xor     r15d, r15d
0x1800234d8  mov     [rbp+var_18], r12
0x1800234dc  xor     edi, edi
0x1800234de  mov     [rbp+pbData], r15
0x1800234e2  mov     [rbp+var_30], rdi
0x1800234e6  mov     r13, r9
0x1800234e9  mov     ebx, edx
0x1800234eb  mov     r14, rcx
0x1800234ee  test    rcx, rcx
0x1800234f1  jz      loc_180023722
0x1800234f7  test    edx, edx
0x1800234f9  jz      loc_180023722
0x1800234ff  test    r8, r8
0x180023502  jz      loc_180023722
0x180023508  test    r9, r9
0x18002350b  jz      loc_180023722
0x180023511  lea     rdx, aTlsHybridKey; "TLS_HYBRID_KEY"
0x180023518  mov     rcx, r8; String1
0x18002351b  call    wcscmp
0x180023520  test    eax, eax
0x180023522  jz      short loc_18002354C
0x180023524  mov     ebx, 80090029h
0x180023529  mov     r9d, 479h
0x18002352f  mov     ecx, 80090029h
0x180023534  lea     rdx, aStatus_0; "status"
0x18002353b  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180023542  call    DebugTraceError
0x180023547  jmp     loc_180023787
0x18002354c  cmp     ebx, 20h ; ' '
0x18002354f  jnb     short loc_180023563
0x180023551  mov     r9d, 480h
0x180023557  mov     ebx, 80090005h
0x18002355c  mov     ecx, 80090005h
0x180023561  jmp     short loc_180023534
0x180023563  cmp     dword ptr [r14], 48534C54h
0x18002356a  jz      short loc_180023574
0x18002356c  mov     r9d, 489h
0x180023572  jmp     short loc_180023557
0x180023574  mov     r15, [r14+8]
0x180023578  lea     rdx, aSsleccpublicbl; "SSLECCPUBLICBLOB"
0x18002357f  mov     rcx, r15; String1
0x180023582  call    wcscmp
0x180023587  test    eax, eax
0x180023589  jnz     loc_180023717
0x18002358f  mov     rdi, [r14+10h]
0x180023593  lea     rdx, aMlkempublicblo; "MLKEMPUBLICBLOB"
0x18002359a  mov     rcx, rdi; String1
0x18002359d  call    wcscmp
0x1800235a2  test    eax, eax
0x1800235a4  jz      short loc_1800235BD
0x1800235a6  lea     rdx, aTlsKemCipherte; "TLS_KEM_CIPHERTEXT"
0x1800235ad  mov     rcx, rdi; String1
0x1800235b0  call    wcscmp
0x1800235b5  test    eax, eax
0x1800235b7  jnz     loc_180023717
0x1800235bd  movzx   ecx, word ptr [r14+4]
0x1800235c2  lea     rax, [rbp+arg_0]
0x1800235c6  mov     [rsp+78h+var_40], rax
0x1800235cb  lea     r8d, [rbx-20h]
0x1800235cf  lea     rax, [rbp+var_30]
0x1800235d3  mov     [rbp+cbData], esi
0x1800235d6  mov     [rsp+78h+var_48], rax
0x1800235db  lea     rdx, [r14+20h]
0x1800235df  lea     rax, [rbp+cbData]
0x1800235e3  mov     [rbp+arg_0], esi
0x1800235e6  mov     [rsp+78h+var_50], rax
0x1800235eb  mov     r9, rdi
0x1800235ee  lea     rax, [rbp+pbData]
0x1800235f2  mov     [rsp+78h+var_58], rax
0x1800235f7  call    SslpConstructConstituentKeysFromKeyShare
0x1800235fc  mov     ebx, eax
0x1800235fe  test    eax, eax
0x180023600  jns     short loc_18002362A
0x180023602  mov     r9d, 4A9h
0x180023608  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002360f  lea     rdx, aStatus_0; "status"
0x180023616  mov     ecx, eax
0x180023618  call    DebugTraceError
0x18002361d  mov     r15, [rbp+pbData]
0x180023621  mov     rdi, [rbp+var_30]
0x180023625  jmp     loc_18002376D
0x18002362a  mov     edx, [rbp+cbData]; cbData
0x18002362d  lea     r9, [rbp+var_10]
0x180023631  mov     r8, r15; pszBlobType
0x180023634  mov     r15, [rbp+pbData]
0x180023638  mov     rcx, r15; pbData
0x18002363b  call    SslpImportEphemeralKeyWithNCrypt
0x180023640  mov     ebx, eax
0x180023642  test    eax, eax
0x180023644  jns     short loc_18002366A
0x180023646  mov     r9d, 4B4h
0x18002364c  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180023653  lea     rdx, aStatus_0; "status"
0x18002365a  mov     ecx, eax
0x18002365c  call    DebugTraceError
0x180023661  mov     rdi, [rbp+var_30]
0x180023665  jmp     loc_180023752
0x18002366a  lea     rdx, aMlkempublicblo; "MLKEMPUBLICBLOB"
0x180023671  mov     rcx, rdi; String1
0x180023674  call    wcscmp
0x180023679  mov     edx, [rbp+arg_0]; cbData
0x18002367c  test    eax, eax
0x18002367e  jnz     short loc_1800236BD
0x180023680  mov     r8, rdi; pszBlobType
0x180023683  lea     r9, [rbp+var_28]
0x180023687  mov     rdi, [rbp+var_30]
0x18002368b  mov     rcx, rdi; pbData
0x18002368e  call    SslpImportKemKeyWithNCrypt
0x180023693  mov     ebx, eax
0x180023695  test    eax, eax
0x180023697  jns     short loc_1800236DB
0x180023699  mov     r9d, 4C1h
0x18002369f  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800236a6  mov     ecx, eax
0x1800236a8  lea     rdx, aStatus_0; "status"
0x1800236af  call    DebugTraceError
0x1800236b4  mov     rsi, [rbp+var_28]
0x1800236b8  jmp     loc_180023752
0x1800236bd  mov     rdi, [rbp+var_30]
0x1800236c1  lea     r8, [rbp+var_28]
0x1800236c5  mov     rcx, rdi
0x1800236c8  call    SslpImportKemCipherText
0x1800236cd  mov     ebx, eax
0x1800236cf  test    eax, eax
0x1800236d1  jns     short loc_1800236DB
0x1800236d3  mov     r9d, 4CDh
0x1800236d9  jmp     short loc_18002369F
0x1800236db  mov     rsi, [rbp+var_28]
0x1800236df  lea     rax, [rbp+var_18]
0x1800236e3  mov     r8, [rbp+var_10]
0x1800236e7  mov     r9, rsi
0x1800236ea  movzx   edx, word ptr [r14+4]
0x1800236ef  mov     [rsp+78h+var_58], rax
0x1800236f4  call    SslpCreateBaseHybridKeyStruct
0x1800236f9  mov     ebx, eax
0x1800236fb  test    eax, eax
0x1800236fd  jns     short loc_18002370D
0x1800236ff  mov     r12, [rbp+var_18]
0x180023703  mov     ecx, eax
0x180023705  mov     r9d, 4DEh
0x18002370b  jmp     short loc_180023732
0x18002370d  mov     rax, [rbp+var_18]
0x180023711  mov     [r13+0], rax
0x180023715  jmp     short loc_180023752
0x180023717  mov     r9d, 494h
0x18002371d  jmp     loc_180023557
0x180023722  mov     ebx, 80090027h
0x180023727  mov     ecx, 80090027h
0x18002372c  mov     r9d, 472h
0x180023732  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180023739  lea     rdx, aStatus_0; "status"
0x180023740  call    DebugTraceError
0x180023745  test    r12, r12
0x180023748  jz      short loc_180023752
0x18002374a  mov     rcx, r12
0x18002374d  call    SslpFreeHybridKey
0x180023752  mov     rcx, [rbp+var_10]
0x180023756  test    rcx, rcx
0x180023759  jz      short loc_180023760
0x18002375b  call    SslpFreeEphemeralKey
0x180023760  test    rsi, rsi
0x180023763  jz      short loc_18002376D
0x180023765  mov     rcx, rsi
0x180023768  call    SslpFreeKemKey
0x18002376d  test    r15, r15
0x180023770  jz      short loc_18002377A
0x180023772  mov     rcx, r15
0x180023775  call    MSCryptFree
0x18002377a  test    rdi, rdi
0x18002377d  jz      short loc_180023787
0x18002377f  mov     rcx, rdi
0x180023782  call    MSCryptFree
0x180023787  mov     eax, ebx
0x180023789  add     rsp, 78h
0x18002378d  pop     r15
0x18002378f  pop     r14
0x180023791  pop     r13
0x180023793  pop     r12
0x180023795  pop     rdi
0x180023796  pop     rsi
0x180023797  pop     rbx
0x180023798  pop     rbp
0x180023799  retn
```

# TlsExportKeyingMaterial

- ea: `0x1800843c0`
- end: `0x18008470e`
- name: `TlsExportKeyingMaterial`
- size: `846`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180082dc0`

## callees

- `0x1800020c0`
- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x180036040`
- `0x18005a4d0`
- `0x180083800`
- `0x180083ed4`
- `0x1800843c0`
- `0x180084714`

## string_xrefs

- `0x180084476`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18008467f`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall TlsExportKeyingMaterial(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int16 a5,
        __int64 a6,
        __int16 a7)
{
  __int64 v7; // rdi
  UCHAR *pbSecret; // rsi
  _BYTE *v9; // r14
  void *v10; // r15
  __int64 v11; // rcx
  __int64 v12; // r13
  int PrfHashInfo; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  NTSTATUS v17; // ebx
  __int64 v18; // r9
  __int64 v19; // rax
  __int64 v20; // rcx
  NTSTATUS v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rax
  __int64 v26; // r9
  PUCHAR v27; // r13
  __int64 v28; // r9
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rax
  __int64 v33; // r9
  __int64 v34; // rax
  UCHAR *v35; // rcx
  __int64 v36; // rcx
  _BYTE *v37; // rax
  ULONG cbSecret; // [rsp+28h] [rbp-38h]
  ULONG cbSecreta; // [rsp+28h] [rbp-38h]
  ULONG cbSecretb; // [rsp+28h] [rbp-38h]
  ULONG v42; // [rsp+40h] [rbp-20h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+48h] [rbp-18h] BYREF
  PUCHAR pbInput[2]; // [rsp+50h] [rbp-10h] BYREF

  v42 = 0;
  LODWORD(v7) = 0;
  pbInput[0] = 0;
  pbSecret = 0;
  phKey = 0;
  v9 = 0;
  v10 = 0;
  if ( !a1
    || !a2
    || (v11 = *(_QWORD *)(a2 + 16)) == 0
    || (v12 = *(_QWORD *)(a2 + 32)) == 0
    || !a3
    || !a4 && a5
    || !a6
    || !a7 )
  {
    v18 = 4388;
    goto LABEL_40;
  }
  PrfHashInfo = GetPrfHashInfo(v11, pbInput, &v42);
  v17 = PrfHashInfo;
  if ( PrfHashInfo < 0 )
  {
    DebugTraceError(
      (unsigned int)PrfHashInfo,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      4395);
    LODWORD(v7) = v42;
    goto LABEL_42;
  }
  v7 = v42;
  if ( v42 > 0xFF )
  {
    v18 = 4401;
LABEL_40:
    v17 = -2146893785;
    v20 = 2148073511LL;
    goto LABEL_41;
  }
  v19 = MSCryptAlloc(v42, v14, v15, v16);
  v9 = (_BYTE *)v19;
  if ( v19 )
  {
    v21 = TlsHashContext(a1, 0, 0, pbInput[0], v19, (_BYTE)v7);
    v17 = v21;
    if ( v21 < 0 )
    {
      v18 = 4421;
LABEL_19:
      v20 = (unsigned int)v21;
      goto LABEL_41;
    }
    v25 = MSCryptAlloc(v7, v22, v23, v24);
    pbSecret = (UCHAR *)v25;
    if ( !v25 )
    {
      v18 = 4429;
      goto LABEL_16;
    }
    LOBYTE(v26) = v7;
    LOWORD(cbSecret) = v7;
    v17 = TlsExpandLabel(v12, a3, v9, v26, v25, cbSecret);
    if ( v17 >= 0 )
    {
      v17 = BCryptGenerateSymmetricKey((BCRYPT_ALG_HANDLE)0x391, &phKey, 0, 0, pbSecret, v7, 0);
      if ( v17 )
      {
        v18 = 4456;
      }
      else
      {
        v27 = pbInput[0];
        v28 = -1;
        do
          ++v28;
        while ( *(_WORD *)&pbInput[0][2 * v28] );
        v17 = BCryptSetProperty(phKey, L"HkdfHashAlgorithm", pbInput[0], 2 * v28 + 2, 0);
        if ( !v17 )
        {
          v21 = BCryptSetProperty(phKey, L"HkdfPrkAndFinalize", 0, 0, 0);
          v17 = v21;
          if ( v21 )
          {
            v18 = 4480;
          }
          else
          {
            v32 = MSCryptAlloc(v7, v29, v30, v31);
            v10 = (void *)v32;
            if ( !v32 )
            {
              v17 = -1073741801;
              v18 = 4489;
              v20 = 3221225495LL;
              goto LABEL_41;
            }
            LOBYTE(cbSecreta) = v7;
            v21 = TlsHashContext(a1, a4, a5, v27, v32, cbSecreta);
            v17 = v21;
            if ( v21 >= 0 )
            {
              LOBYTE(v33) = v7;
              LOWORD(cbSecretb) = a7;
              v21 = TlsExpandLabel(phKey, "exporter", v10, v33, a6, cbSecretb);
              v17 = v21;
              if ( v21 >= 0 )
                goto LABEL_42;
              v18 = 4509;
            }
            else
            {
              v18 = 4495;
            }
          }
          goto LABEL_19;
        }
        v18 = 4469;
      }
    }
    else
    {
      v18 = 4441;
    }
    v20 = (unsigned int)v17;
    goto LABEL_41;
  }
  v18 = 4414;
LABEL_16:
  v17 = -2146893810;
  v20 = 2148073486LL;
LABEL_41:
  DebugTraceError(v20, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", v18);
LABEL_42:
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( pbSecret )
  {
    v34 = (unsigned int)v7;
    v35 = pbSecret;
    if ( (_DWORD)v7 )
    {
      do
      {
        *v35++ = 0;
        --v34;
      }
      while ( v34 );
    }
    MSCryptFree(pbSecret);
  }
  if ( v9 )
  {
    v36 = (unsigned int)v7;
    v37 = v9;
    if ( (_DWORD)v7 )
    {
      do
      {
        *v37++ = 0;
        --v36;
      }
      while ( v36 );
    }
    MSCryptFree(v9);
  }
  if ( v10 )
    MSCryptFree(v10);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800843c0  mov     rax, rsp
0x1800843c3  mov     [rax+10h], rbx
0x1800843c7  mov     [rax+20h], r9
0x1800843cb  mov     [rax+18h], r8
0x1800843cf  mov     [rax+8], rcx
0x1800843d3  push    rbp
0x1800843d4  push    rsi
0x1800843d5  push    rdi
0x1800843d6  push    r12
0x1800843d8  push    r13
0x1800843da  push    r14
0x1800843dc  push    r15
0x1800843de  mov     rbp, rsp
0x1800843e1  sub     rsp, 60h
0x1800843e5  mov     rax, r8
0x1800843e8  xor     r8d, r8d
0x1800843eb  mov     [rbp+var_20], r8d
0x1800843ef  mov     edi, r8d
0x1800843f2  mov     [rbp+pbInput], r8
0x1800843f6  mov     esi, r8d
0x1800843f9  mov     [rbp+phKey], r8
0x1800843fd  mov     r14d, r8d
0x180084400  mov     r15d, r8d
0x180084403  test    rcx, rcx
0x180084406  jz      loc_18008466F
0x18008440c  test    rdx, rdx
0x18008440f  jz      loc_18008466F
0x180084415  mov     rcx, [rdx+10h]
0x180084419  test    rcx, rcx
0x18008441c  jz      loc_18008466F
0x180084422  mov     r13, [rdx+20h]
0x180084426  test    r13, r13
0x180084429  jz      loc_18008466F
0x18008442f  test    rax, rax
0x180084432  jz      loc_18008466F
0x180084438  test    r9, r9
0x18008443b  jnz     short loc_180084448
0x18008443d  cmp     [rbp+arg_20], r8w
0x180084442  jnz     loc_18008466F
0x180084448  cmp     [rbp+arg_28], r8
0x18008444c  jz      loc_18008466F
0x180084452  cmp     [rbp+arg_30], r8w
0x180084457  jz      loc_18008466F
0x18008445d  lea     r8, [rbp+var_20]
0x180084461  lea     rdx, [rbp+pbInput]
0x180084465  call    GetPrfHashInfo
0x18008446a  mov     ebx, eax
0x18008446c  test    eax, eax
0x18008446e  jns     short loc_180084493
0x180084470  mov     r9d, 112Bh
0x180084476  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18008447d  lea     rdx, aStatus; "Status"
0x180084484  mov     ecx, eax
0x180084486  call    DebugTraceError
0x18008448b  mov     edi, [rbp+var_20]
0x18008448e  jmp     loc_180084692
0x180084493  mov     edi, [rbp+var_20]
0x180084496  cmp     edi, 0FFh
0x18008449c  jbe     short loc_1800844A9
0x18008449e  mov     r9d, 1131h
0x1800844a4  jmp     loc_180084675
0x1800844a9  mov     rcx, rdi
0x1800844ac  call    MSCryptAlloc
0x1800844b1  mov     r14, rax
0x1800844b4  test    rax, rax
0x1800844b7  jnz     short loc_1800844CE
0x1800844b9  mov     r9d, 113Eh
0x1800844bf  mov     ebx, 8009000Eh
0x1800844c4  mov     ecx, 8009000Eh
0x1800844c9  jmp     loc_18008467F
0x1800844ce  mov     r9, [rbp+pbInput]
0x1800844d2  xor     r8d, r8d
0x1800844d5  mov     rcx, [rbp+arg_0]
0x1800844d9  xor     edx, edx
0x1800844db  mov     byte ptr [rsp+60h+cbSecret], dil
0x1800844e0  mov     [rsp+60h+pbSecret], r14
0x1800844e5  call    TlsHashContext
0x1800844ea  mov     ebx, eax
0x1800844ec  test    eax, eax
0x1800844ee  jns     short loc_1800844FD
0x1800844f0  mov     r9d, 1145h
0x1800844f6  mov     ecx, eax
0x1800844f8  jmp     loc_18008467F
0x1800844fd  mov     rcx, rdi
0x180084500  call    MSCryptAlloc
0x180084505  mov     rsi, rax
0x180084508  test    rax, rax
0x18008450b  jnz     short loc_180084515
0x18008450d  mov     r9d, 114Dh
0x180084513  jmp     short loc_1800844BF
0x180084515  mov     rdx, [rbp+arg_10]
0x180084519  mov     r9b, dil
0x18008451c  mov     word ptr [rsp+60h+cbSecret], di
0x180084521  mov     r8, r14
0x180084524  mov     rcx, r13
0x180084527  mov     [rsp+60h+pbSecret], rsi
0x18008452c  call    TlsExpandLabel
0x180084531  mov     ebx, eax
0x180084533  xor     eax, eax
0x180084535  test    ebx, ebx
0x180084537  jns     short loc_180084546
0x180084539  mov     r9d, 1159h
0x18008453f  mov     ecx, ebx
0x180084541  jmp     loc_18008467F
0x180084546  mov     [rsp+60h+dwFlags], eax; dwFlags
0x18008454a  lea     rdx, [rbp+phKey]; phKey
0x18008454e  mov     [rsp+60h+cbSecret], edi; cbSecret
0x180084552  xor     r9d, r9d; cbKeyObject
0x180084555  xor     r8d, r8d; pbKeyObject
0x180084558  mov     [rsp+60h+pbSecret], rsi; pbSecret
0x18008455d  mov     ecx, 391h; hAlgorithm
0x180084562  call    BCryptGenerateSymmetricKey
0x180084567  mov     ebx, eax
0x180084569  xor     eax, eax
0x18008456b  test    ebx, ebx
0x18008456d  jz      short loc_180084577
0x18008456f  mov     r9d, 1168h
0x180084575  jmp     short loc_18008453F
0x180084577  mov     r13, [rbp+pbInput]
0x18008457b  or      r9, 0FFFFFFFFFFFFFFFFh
0x18008457f  inc     r9
0x180084582  cmp     [r13+r9*2+0], ax
0x180084588  jnz     short loc_18008457F
0x18008458a  mov     rcx, [rbp+phKey]; hObject
0x18008458e  lea     r9d, ds:2[r9*2]; cbInput
0x180084596  mov     r8, r13; pbInput
0x180084599  mov     dword ptr [rsp+60h+pbSecret], eax; dwFlags
0x18008459d  lea     rdx, aHkdfhashalgori; "HkdfHashAlgorithm"
0x1800845a4  call    BCryptSetProperty
0x1800845a9  mov     ebx, eax
0x1800845ab  xor     eax, eax
0x1800845ad  test    ebx, ebx
0x1800845af  jz      short loc_1800845B9
0x1800845b1  mov     r9d, 1175h
0x1800845b7  jmp     short loc_18008453F
0x1800845b9  mov     rcx, [rbp+phKey]; hObject
0x1800845bd  lea     rdx, aHkdfprkandfina; "HkdfPrkAndFinalize"
0x1800845c4  xor     r9d, r9d; cbInput
0x1800845c7  mov     dword ptr [rsp+60h+pbSecret], eax; dwFlags
0x1800845cb  xor     r8d, r8d; pbInput
0x1800845ce  call    BCryptSetProperty
0x1800845d3  mov     ebx, eax
0x1800845d5  test    eax, eax
0x1800845d7  jz      short loc_1800845E4
0x1800845d9  mov     r9d, 1180h
0x1800845df  jmp     loc_1800844F6
0x1800845e4  mov     rcx, rdi
0x1800845e7  call    MSCryptAlloc
0x1800845ec  mov     r15, rax
0x1800845ef  test    rax, rax
0x1800845f2  jnz     short loc_180084606
0x1800845f4  mov     ebx, 0C0000017h
0x1800845f9  mov     r9d, 1189h
0x1800845ff  mov     ecx, 0C0000017h
0x180084604  jmp     short loc_18008467F
0x180084606  movzx   r8d, [rbp+arg_20]
0x18008460b  mov     r9, r13
0x18008460e  mov     rdx, [rbp+arg_18]
0x180084612  mov     rcx, [rbp+arg_0]
0x180084616  mov     byte ptr [rsp+60h+cbSecret], dil
0x18008461b  mov     [rsp+60h+pbSecret], r15
0x180084620  call    TlsHashContext
0x180084625  mov     ebx, eax
0x180084627  test    eax, eax
0x180084629  jns     short loc_180084636
0x18008462b  mov     r9d, 118Fh
0x180084631  jmp     loc_1800844F6
0x180084636  movzx   eax, [rbp+arg_30]
0x18008463a  lea     rdx, aExporter; "exporter"
0x180084641  mov     rcx, [rbp+phKey]
0x180084645  mov     r9b, dil
0x180084648  mov     word ptr [rsp+60h+cbSecret], ax
0x18008464d  mov     r8, r15
0x180084650  mov     rax, [rbp+arg_28]
0x180084654  mov     [rsp+60h+pbSecret], rax
0x180084659  call    TlsExpandLabel
0x18008465e  mov     ebx, eax
0x180084660  test    eax, eax
0x180084662  jns     short loc_180084692
0x180084664  mov     r9d, 119Dh
0x18008466a  jmp     loc_1800844F6
0x18008466f  mov     r9d, 1124h
0x180084675  mov     ebx, 80090027h
0x18008467a  mov     ecx, 80090027h
0x18008467f  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180084686  lea     rdx, aStatus; "Status"
0x18008468d  call    DebugTraceError
0x180084692  mov     rcx, [rbp+phKey]; hKey
0x180084696  test    rcx, rcx
0x180084699  jz      short loc_1800846A0
0x18008469b  call    BCryptDestroyKey
0x1800846a0  test    rsi, rsi
0x1800846a3  jz      short loc_1800846C2
0x1800846a5  mov     eax, edi
0x1800846a7  mov     rcx, rsi
0x1800846aa  test    edi, edi
0x1800846ac  jz      short loc_1800846BA
0x1800846ae  mov     byte ptr [rcx], 0
0x1800846b1  inc     rcx
0x1800846b4  sub     rax, 1
0x1800846b8  jnz     short loc_1800846AE
0x1800846ba  mov     rcx, rsi; P
0x1800846bd  call    MSCryptFree
0x1800846c2  xor     esi, esi
0x1800846c4  test    r14, r14
0x1800846c7  jz      short loc_1800846E6
0x1800846c9  mov     ecx, edi
0x1800846cb  mov     rax, r14
0x1800846ce  test    edi, edi
0x1800846d0  jz      short loc_1800846DE
0x1800846d2  mov     [rax], sil
0x1800846d5  inc     rax
0x1800846d8  sub     rcx, 1
0x1800846dc  jnz     short loc_1800846D2
0x1800846de  mov     rcx, r14; P
0x1800846e1  call    MSCryptFree
0x1800846e6  test    r15, r15
0x1800846e9  jz      short loc_1800846F3
0x1800846eb  mov     rcx, r15; P
0x1800846ee  call    MSCryptFree
0x1800846f3  mov     eax, ebx
0x1800846f5  mov     rbx, [rsp+60h+arg_8]
0x1800846fd  add     rsp, 60h
0x180084701  pop     r15
0x180084703  pop     r14
0x180084705  pop     r13
0x180084707  pop     r12
0x180084709  pop     rdi
0x18008470a  pop     rsi
0x18008470b  pop     rbp
0x18008470c  retn
```

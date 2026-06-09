# TlsExportKeyingMaterial

- ea: `0x18008d5c0`
- end: `0x18008d90e`
- name: `TlsExportKeyingMaterial`
- size: `846`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18008bfc0`

## callees

- `0x18000c1e0`
- `0x18000e090`
- `0x180010590`
- `0x18001155c`
- `0x18003f5b0`
- `0x180063db0`
- `0x18008ca00`
- `0x18008d0d4`
- `0x18008d5c0`
- `0x18008d914`

## string_xrefs

- `0x18008d676`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18008d87f`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

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
  NTSTATUS v15; // ebx
  __int64 v16; // r9
  __int64 v17; // rax
  __int64 v18; // rcx
  NTSTATUS v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 v22; // r9
  PUCHAR v23; // r13
  __int64 v24; // r9
  __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // r9
  __int64 v28; // rax
  UCHAR *v29; // rcx
  __int64 v30; // rcx
  _BYTE *v31; // rax
  ULONG cbSecret; // [rsp+28h] [rbp-38h]
  ULONG cbSecreta; // [rsp+28h] [rbp-38h]
  ULONG cbSecretb; // [rsp+28h] [rbp-38h]
  ULONG v36; // [rsp+40h] [rbp-20h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+48h] [rbp-18h] BYREF
  PUCHAR pbInput[2]; // [rsp+50h] [rbp-10h] BYREF

  v36 = 0;
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
    v16 = 4388;
    goto LABEL_40;
  }
  PrfHashInfo = GetPrfHashInfo(v11, pbInput, &v36);
  v15 = PrfHashInfo;
  if ( PrfHashInfo < 0 )
  {
    DebugTraceError(
      (unsigned int)PrfHashInfo,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      4395);
    LODWORD(v7) = v36;
    goto LABEL_42;
  }
  v7 = v36;
  if ( v36 > 0xFF )
  {
    v16 = 4401;
LABEL_40:
    v15 = -2146893785;
    v18 = 2148073511LL;
    goto LABEL_41;
  }
  v17 = MSCryptAlloc(v36, v14);
  v9 = (_BYTE *)v17;
  if ( v17 )
  {
    v19 = TlsHashContext(a1, 0, 0, pbInput[0], v17, (_BYTE)v7);
    v15 = v19;
    if ( v19 < 0 )
    {
      v16 = 4421;
LABEL_19:
      v18 = (unsigned int)v19;
      goto LABEL_41;
    }
    v21 = MSCryptAlloc(v7, v20);
    pbSecret = (UCHAR *)v21;
    if ( !v21 )
    {
      v16 = 4429;
      goto LABEL_16;
    }
    LOBYTE(v22) = v7;
    LOWORD(cbSecret) = v7;
    v15 = TlsExpandLabel(v12, a3, v9, v22, v21, cbSecret);
    if ( v15 >= 0 )
    {
      v15 = BCryptGenerateSymmetricKey((BCRYPT_ALG_HANDLE)0x391, &phKey, 0, 0, pbSecret, v7, 0);
      if ( v15 )
      {
        v16 = 4456;
      }
      else
      {
        v23 = pbInput[0];
        v24 = -1;
        do
          ++v24;
        while ( *(_WORD *)&pbInput[0][2 * v24] );
        v15 = BCryptSetProperty(phKey, L"HkdfHashAlgorithm", pbInput[0], 2 * v24 + 2, 0);
        if ( !v15 )
        {
          v19 = BCryptSetProperty(phKey, L"HkdfPrkAndFinalize", 0, 0, 0);
          v15 = v19;
          if ( v19 )
          {
            v16 = 4480;
          }
          else
          {
            v26 = MSCryptAlloc(v7, v25);
            v10 = (void *)v26;
            if ( !v26 )
            {
              v15 = -1073741801;
              v16 = 4489;
              v18 = 3221225495LL;
              goto LABEL_41;
            }
            LOBYTE(cbSecreta) = v7;
            v19 = TlsHashContext(a1, a4, a5, v23, v26, cbSecreta);
            v15 = v19;
            if ( v19 >= 0 )
            {
              LOBYTE(v27) = v7;
              LOWORD(cbSecretb) = a7;
              v19 = TlsExpandLabel(phKey, "exporter", v10, v27, a6, cbSecretb);
              v15 = v19;
              if ( v19 >= 0 )
                goto LABEL_42;
              v16 = 4509;
            }
            else
            {
              v16 = 4495;
            }
          }
          goto LABEL_19;
        }
        v16 = 4469;
      }
    }
    else
    {
      v16 = 4441;
    }
    v18 = (unsigned int)v15;
    goto LABEL_41;
  }
  v16 = 4414;
LABEL_16:
  v15 = -2146893810;
  v18 = 2148073486LL;
LABEL_41:
  DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", v16);
LABEL_42:
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( pbSecret )
  {
    v28 = (unsigned int)v7;
    v29 = pbSecret;
    if ( (_DWORD)v7 )
    {
      do
      {
        *v29++ = 0;
        --v28;
      }
      while ( v28 );
    }
    MSCryptFree(pbSecret);
  }
  if ( v9 )
  {
    v30 = (unsigned int)v7;
    v31 = v9;
    if ( (_DWORD)v7 )
    {
      do
      {
        *v31++ = 0;
        --v30;
      }
      while ( v30 );
    }
    MSCryptFree(v9);
  }
  if ( v10 )
    MSCryptFree(v10);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18008d5c0  mov     rax, rsp
0x18008d5c3  mov     [rax+10h], rbx
0x18008d5c7  mov     [rax+20h], r9
0x18008d5cb  mov     [rax+18h], r8
0x18008d5cf  mov     [rax+8], rcx
0x18008d5d3  push    rbp
0x18008d5d4  push    rsi
0x18008d5d5  push    rdi
0x18008d5d6  push    r12
0x18008d5d8  push    r13
0x18008d5da  push    r14
0x18008d5dc  push    r15
0x18008d5de  mov     rbp, rsp
0x18008d5e1  sub     rsp, 60h
0x18008d5e5  mov     rax, r8
0x18008d5e8  xor     r8d, r8d
0x18008d5eb  mov     [rbp+var_20], r8d
0x18008d5ef  mov     edi, r8d
0x18008d5f2  mov     [rbp+pbInput], r8
0x18008d5f6  mov     esi, r8d
0x18008d5f9  mov     [rbp+phKey], r8
0x18008d5fd  mov     r14d, r8d
0x18008d600  mov     r15d, r8d
0x18008d603  test    rcx, rcx
0x18008d606  jz      loc_18008D86F
0x18008d60c  test    rdx, rdx
0x18008d60f  jz      loc_18008D86F
0x18008d615  mov     rcx, [rdx+10h]
0x18008d619  test    rcx, rcx
0x18008d61c  jz      loc_18008D86F
0x18008d622  mov     r13, [rdx+20h]
0x18008d626  test    r13, r13
0x18008d629  jz      loc_18008D86F
0x18008d62f  test    rax, rax
0x18008d632  jz      loc_18008D86F
0x18008d638  test    r9, r9
0x18008d63b  jnz     short loc_18008D648
0x18008d63d  cmp     [rbp+arg_20], r8w
0x18008d642  jnz     loc_18008D86F
0x18008d648  cmp     [rbp+arg_28], r8
0x18008d64c  jz      loc_18008D86F
0x18008d652  cmp     [rbp+arg_30], r8w
0x18008d657  jz      loc_18008D86F
0x18008d65d  lea     r8, [rbp+var_20]
0x18008d661  lea     rdx, [rbp+pbInput]
0x18008d665  call    GetPrfHashInfo
0x18008d66a  mov     ebx, eax
0x18008d66c  test    eax, eax
0x18008d66e  jns     short loc_18008D693
0x18008d670  mov     r9d, 112Bh
0x18008d676  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18008d67d  lea     rdx, aStatus; "Status"
0x18008d684  mov     ecx, eax
0x18008d686  call    DebugTraceError
0x18008d68b  mov     edi, [rbp+var_20]
0x18008d68e  jmp     loc_18008D892
0x18008d693  mov     edi, [rbp+var_20]
0x18008d696  cmp     edi, 0FFh
0x18008d69c  jbe     short loc_18008D6A9
0x18008d69e  mov     r9d, 1131h
0x18008d6a4  jmp     loc_18008D875
0x18008d6a9  mov     rcx, rdi
0x18008d6ac  call    MSCryptAlloc
0x18008d6b1  mov     r14, rax
0x18008d6b4  test    rax, rax
0x18008d6b7  jnz     short loc_18008D6CE
0x18008d6b9  mov     r9d, 113Eh
0x18008d6bf  mov     ebx, 8009000Eh
0x18008d6c4  mov     ecx, 8009000Eh
0x18008d6c9  jmp     loc_18008D87F
0x18008d6ce  mov     r9, [rbp+pbInput]
0x18008d6d2  xor     r8d, r8d
0x18008d6d5  mov     rcx, [rbp+arg_0]
0x18008d6d9  xor     edx, edx
0x18008d6db  mov     byte ptr [rsp+60h+cbSecret], dil
0x18008d6e0  mov     [rsp+60h+pbSecret], r14
0x18008d6e5  call    TlsHashContext
0x18008d6ea  mov     ebx, eax
0x18008d6ec  test    eax, eax
0x18008d6ee  jns     short loc_18008D6FD
0x18008d6f0  mov     r9d, 1145h
0x18008d6f6  mov     ecx, eax
0x18008d6f8  jmp     loc_18008D87F
0x18008d6fd  mov     rcx, rdi
0x18008d700  call    MSCryptAlloc
0x18008d705  mov     rsi, rax
0x18008d708  test    rax, rax
0x18008d70b  jnz     short loc_18008D715
0x18008d70d  mov     r9d, 114Dh
0x18008d713  jmp     short loc_18008D6BF
0x18008d715  mov     rdx, [rbp+arg_10]
0x18008d719  mov     r9b, dil
0x18008d71c  mov     word ptr [rsp+60h+cbSecret], di
0x18008d721  mov     r8, r14
0x18008d724  mov     rcx, r13
0x18008d727  mov     [rsp+60h+pbSecret], rsi
0x18008d72c  call    TlsExpandLabel
0x18008d731  mov     ebx, eax
0x18008d733  xor     eax, eax
0x18008d735  test    ebx, ebx
0x18008d737  jns     short loc_18008D746
0x18008d739  mov     r9d, 1159h
0x18008d73f  mov     ecx, ebx
0x18008d741  jmp     loc_18008D87F
0x18008d746  mov     [rsp+60h+dwFlags], eax; dwFlags
0x18008d74a  lea     rdx, [rbp+phKey]; phKey
0x18008d74e  mov     [rsp+60h+cbSecret], edi; cbSecret
0x18008d752  xor     r9d, r9d; cbKeyObject
0x18008d755  xor     r8d, r8d; pbKeyObject
0x18008d758  mov     [rsp+60h+pbSecret], rsi; pbSecret
0x18008d75d  mov     ecx, 391h; hAlgorithm
0x18008d762  call    BCryptGenerateSymmetricKey
0x18008d767  mov     ebx, eax
0x18008d769  xor     eax, eax
0x18008d76b  test    ebx, ebx
0x18008d76d  jz      short loc_18008D777
0x18008d76f  mov     r9d, 1168h
0x18008d775  jmp     short loc_18008D73F
0x18008d777  mov     r13, [rbp+pbInput]
0x18008d77b  or      r9, 0FFFFFFFFFFFFFFFFh
0x18008d77f  inc     r9
0x18008d782  cmp     [r13+r9*2+0], ax
0x18008d788  jnz     short loc_18008D77F
0x18008d78a  mov     rcx, [rbp+phKey]; hObject
0x18008d78e  lea     r9d, ds:2[r9*2]; cbInput
0x18008d796  mov     r8, r13; pbInput
0x18008d799  mov     dword ptr [rsp+60h+pbSecret], eax; dwFlags
0x18008d79d  lea     rdx, aHkdfhashalgori; "HkdfHashAlgorithm"
0x18008d7a4  call    BCryptSetProperty
0x18008d7a9  mov     ebx, eax
0x18008d7ab  xor     eax, eax
0x18008d7ad  test    ebx, ebx
0x18008d7af  jz      short loc_18008D7B9
0x18008d7b1  mov     r9d, 1175h
0x18008d7b7  jmp     short loc_18008D73F
0x18008d7b9  mov     rcx, [rbp+phKey]; hObject
0x18008d7bd  lea     rdx, aHkdfprkandfina; "HkdfPrkAndFinalize"
0x18008d7c4  xor     r9d, r9d; cbInput
0x18008d7c7  mov     dword ptr [rsp+60h+pbSecret], eax; dwFlags
0x18008d7cb  xor     r8d, r8d; pbInput
0x18008d7ce  call    BCryptSetProperty
0x18008d7d3  mov     ebx, eax
0x18008d7d5  test    eax, eax
0x18008d7d7  jz      short loc_18008D7E4
0x18008d7d9  mov     r9d, 1180h
0x18008d7df  jmp     loc_18008D6F6
0x18008d7e4  mov     rcx, rdi
0x18008d7e7  call    MSCryptAlloc
0x18008d7ec  mov     r15, rax
0x18008d7ef  test    rax, rax
0x18008d7f2  jnz     short loc_18008D806
0x18008d7f4  mov     ebx, 0C0000017h
0x18008d7f9  mov     r9d, 1189h
0x18008d7ff  mov     ecx, 0C0000017h
0x18008d804  jmp     short loc_18008D87F
0x18008d806  movzx   r8d, [rbp+arg_20]
0x18008d80b  mov     r9, r13
0x18008d80e  mov     rdx, [rbp+arg_18]
0x18008d812  mov     rcx, [rbp+arg_0]
0x18008d816  mov     byte ptr [rsp+60h+cbSecret], dil
0x18008d81b  mov     [rsp+60h+pbSecret], r15
0x18008d820  call    TlsHashContext
0x18008d825  mov     ebx, eax
0x18008d827  test    eax, eax
0x18008d829  jns     short loc_18008D836
0x18008d82b  mov     r9d, 118Fh
0x18008d831  jmp     loc_18008D6F6
0x18008d836  movzx   eax, [rbp+arg_30]
0x18008d83a  lea     rdx, aExporter; "exporter"
0x18008d841  mov     rcx, [rbp+phKey]
0x18008d845  mov     r9b, dil
0x18008d848  mov     word ptr [rsp+60h+cbSecret], ax
0x18008d84d  mov     r8, r15
0x18008d850  mov     rax, [rbp+arg_28]
0x18008d854  mov     [rsp+60h+pbSecret], rax
0x18008d859  call    TlsExpandLabel
0x18008d85e  mov     ebx, eax
0x18008d860  test    eax, eax
0x18008d862  jns     short loc_18008D892
0x18008d864  mov     r9d, 119Dh
0x18008d86a  jmp     loc_18008D6F6
0x18008d86f  mov     r9d, 1124h
0x18008d875  mov     ebx, 80090027h
0x18008d87a  mov     ecx, 80090027h
0x18008d87f  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18008d886  lea     rdx, aStatus; "Status"
0x18008d88d  call    DebugTraceError
0x18008d892  mov     rcx, [rbp+phKey]; hKey
0x18008d896  test    rcx, rcx
0x18008d899  jz      short loc_18008D8A0
0x18008d89b  call    BCryptDestroyKey
0x18008d8a0  test    rsi, rsi
0x18008d8a3  jz      short loc_18008D8C2
0x18008d8a5  mov     eax, edi
0x18008d8a7  mov     rcx, rsi
0x18008d8aa  test    edi, edi
0x18008d8ac  jz      short loc_18008D8BA
0x18008d8ae  mov     byte ptr [rcx], 0
0x18008d8b1  inc     rcx
0x18008d8b4  sub     rax, 1
0x18008d8b8  jnz     short loc_18008D8AE
0x18008d8ba  mov     rcx, rsi; P
0x18008d8bd  call    MSCryptFree
0x18008d8c2  xor     esi, esi
0x18008d8c4  test    r14, r14
0x18008d8c7  jz      short loc_18008D8E6
0x18008d8c9  mov     ecx, edi
0x18008d8cb  mov     rax, r14
0x18008d8ce  test    edi, edi
0x18008d8d0  jz      short loc_18008D8DE
0x18008d8d2  mov     [rax], sil
0x18008d8d5  inc     rax
0x18008d8d8  sub     rcx, 1
0x18008d8dc  jnz     short loc_18008D8D2
0x18008d8de  mov     rcx, r14; P
0x18008d8e1  call    MSCryptFree
0x18008d8e6  test    r15, r15
0x18008d8e9  jz      short loc_18008D8F3
0x18008d8eb  mov     rcx, r15; P
0x18008d8ee  call    MSCryptFree
0x18008d8f3  mov     eax, ebx
0x18008d8f5  mov     rbx, [rsp+60h+arg_8]
0x18008d8fd  add     rsp, 60h
0x18008d901  pop     r15
0x18008d903  pop     r14
0x18008d905  pop     r13
0x18008d907  pop     r12
0x18008d909  pop     rdi
0x18008d90a  pop     rsi
0x18008d90b  pop     rbp
0x18008d90c  retn
```

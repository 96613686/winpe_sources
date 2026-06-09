# TlsExportKeyingMaterial

- ea: `0x180020718`
- end: `0x180020a69`
- name: `TlsExportKeyingMaterial`
- size: `849`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001edb0`

## callees

- `0x180003ef0`
- `0x180007940`
- `0x180009ca0`
- `0x18000b654`
- `0x18000e820`
- `0x18000eb00`
- `0x180020718`

## import_xrefs

- `bcrypt!BCryptSetProperty` at `0x1800208fd`
- `bcrypt!BCryptSetProperty` at `0x180020928`
- `bcrypt!BCryptSetProperty` at `0x1800208fd`
- `bcrypt!BCryptSetProperty` at `0x180020928`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800208ba`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800208ba`
- `bcrypt!BCryptDestroyKey` at `0x1800209f6`
- `bcrypt!BCryptDestroyKey` at `0x1800209f6`

## string_xrefs

- `0x1800207ce`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800209da`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall TlsExportKeyingMaterial(
        __int64 a1,
        __int64 a2,
        const char *a3,
        UCHAR *a4,
        unsigned __int16 a5,
        __int64 a6,
        unsigned __int16 a7)
{
  __int64 cbSecret; // rdi
  UCHAR *pbSecret; // rsi
  UCHAR *v9; // r14
  UCHAR *v10; // r15
  __int64 v11; // rcx
  __int64 v12; // r13
  int PrfHashInfo; // eax
  int v14; // ebx
  __int64 v15; // r9
  UCHAR *v16; // rax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rax
  const wchar_t *v20; // r13
  __int64 v21; // r9
  UCHAR *v22; // rax
  __int64 v23; // rax
  UCHAR *v24; // rcx
  __int64 v25; // rcx
  UCHAR *v26; // rax
  ULONG v28; // [rsp+40h] [rbp-20h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+48h] [rbp-18h] BYREF
  PUCHAR pbInput[2]; // [rsp+50h] [rbp-10h] BYREF

  v28 = 0;
  LODWORD(cbSecret) = 0;
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
    v15 = 4388;
    goto LABEL_40;
  }
  PrfHashInfo = GetPrfHashInfo(v11, pbInput, &v28);
  v14 = PrfHashInfo;
  if ( PrfHashInfo < 0 )
  {
    DebugTraceError(
      (unsigned int)PrfHashInfo,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      4395);
    LODWORD(cbSecret) = v28;
    goto LABEL_42;
  }
  cbSecret = v28;
  if ( v28 > 0xFF )
  {
    v15 = 4401;
LABEL_40:
    v14 = -2146893785;
    v17 = 2148073511LL;
    goto LABEL_41;
  }
  v16 = (UCHAR *)SafeAllocaAllocateFromHeap(v28);
  v9 = v16;
  if ( v16 )
  {
    v18 = TlsHashContext(a1, 0, 0, (const wchar_t *)pbInput[0], v16, cbSecret);
    v14 = v18;
    if ( v18 < 0 )
    {
      v15 = 4421;
LABEL_19:
      v17 = (unsigned int)v18;
      goto LABEL_41;
    }
    v19 = SafeAllocaAllocateFromHeap(cbSecret);
    pbSecret = (UCHAR *)v19;
    if ( !v19 )
    {
      v15 = 4429;
      goto LABEL_16;
    }
    v14 = TlsExpandLabel(v12, a3, v9, cbSecret, v19, cbSecret);
    if ( v14 >= 0 )
    {
      v14 = BCryptGenerateSymmetricKey((BCRYPT_ALG_HANDLE)0x391, &phKey, 0, 0, pbSecret, cbSecret, 0);
      if ( v14 )
      {
        v15 = 4456;
      }
      else
      {
        v20 = (const wchar_t *)pbInput[0];
        v21 = -1;
        do
          ++v21;
        while ( *(_WORD *)&pbInput[0][2 * v21] );
        v14 = BCryptSetProperty(phKey, L"HkdfHashAlgorithm", pbInput[0], 2 * v21 + 2, 0);
        if ( !v14 )
        {
          v18 = BCryptSetProperty(phKey, L"HkdfPrkAndFinalize", 0, 0, 0);
          v14 = v18;
          if ( v18 )
          {
            v15 = 4480;
          }
          else
          {
            v22 = (UCHAR *)SafeAllocaAllocateFromHeap(cbSecret);
            v10 = v22;
            if ( !v22 )
            {
              v14 = -1073741801;
              v15 = 4489;
              v17 = 3221225495LL;
              goto LABEL_41;
            }
            v18 = TlsHashContext(a1, a4, a5, v20, v22, cbSecret);
            v14 = v18;
            if ( v18 >= 0 )
            {
              v18 = TlsExpandLabel((__int64)phKey, "exporter", v10, cbSecret, a6, a7);
              v14 = v18;
              if ( v18 >= 0 )
                goto LABEL_42;
              v15 = 4509;
            }
            else
            {
              v15 = 4495;
            }
          }
          goto LABEL_19;
        }
        v15 = 4469;
      }
    }
    else
    {
      v15 = 4441;
    }
    v17 = (unsigned int)v14;
    goto LABEL_41;
  }
  v15 = 4414;
LABEL_16:
  v14 = -2146893810;
  v17 = 2148073486LL;
LABEL_41:
  DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", v15);
LABEL_42:
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( pbSecret )
  {
    v23 = (unsigned int)cbSecret;
    v24 = pbSecret;
    if ( (_DWORD)cbSecret )
    {
      do
      {
        *v24++ = 0;
        --v23;
      }
      while ( v23 );
    }
    MSCryptFree(pbSecret);
  }
  if ( v9 )
  {
    v25 = (unsigned int)cbSecret;
    v26 = v9;
    if ( (_DWORD)cbSecret )
    {
      do
      {
        *v26++ = 0;
        --v25;
      }
      while ( v25 );
    }
    MSCryptFree(v9);
  }
  if ( v10 )
    MSCryptFree(v10);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180020718  mov     rax, rsp
0x18002071b  mov     [rax+10h], rbx
0x18002071f  mov     [rax+20h], r9
0x180020723  mov     [rax+18h], r8
0x180020727  mov     [rax+8], rcx
0x18002072b  push    rbp
0x18002072c  push    rsi
0x18002072d  push    rdi
0x18002072e  push    r12
0x180020730  push    r13
0x180020732  push    r14
0x180020734  push    r15
0x180020736  mov     rbp, rsp
0x180020739  sub     rsp, 60h
0x18002073d  mov     rax, r8
0x180020740  xor     r8d, r8d
0x180020743  mov     [rbp+var_20], r8d
0x180020747  mov     edi, r8d
0x18002074a  mov     [rbp+pbInput], r8
0x18002074e  mov     esi, r8d
0x180020751  mov     [rbp+phKey], r8
0x180020755  mov     r14d, r8d
0x180020758  mov     r15d, r8d
0x18002075b  test    rcx, rcx
0x18002075e  jz      loc_1800209CA
0x180020764  test    rdx, rdx
0x180020767  jz      loc_1800209CA
0x18002076d  mov     rcx, [rdx+10h]
0x180020771  test    rcx, rcx
0x180020774  jz      loc_1800209CA
0x18002077a  mov     r13, [rdx+20h]
0x18002077e  test    r13, r13
0x180020781  jz      loc_1800209CA
0x180020787  test    rax, rax
0x18002078a  jz      loc_1800209CA
0x180020790  test    r9, r9
0x180020793  jnz     short loc_1800207A0
0x180020795  cmp     [rbp+arg_20], r8w
0x18002079a  jnz     loc_1800209CA
0x1800207a0  cmp     [rbp+arg_28], r8
0x1800207a4  jz      loc_1800209CA
0x1800207aa  cmp     [rbp+arg_30], r8w
0x1800207af  jz      loc_1800209CA
0x1800207b5  lea     r8, [rbp+var_20]
0x1800207b9  lea     rdx, [rbp+pbInput]
0x1800207bd  call    GetPrfHashInfo
0x1800207c2  mov     ebx, eax
0x1800207c4  test    eax, eax
0x1800207c6  jns     short loc_1800207EB
0x1800207c8  mov     r9d, 112Bh
0x1800207ce  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800207d5  lea     rdx, aStatus; "Status"
0x1800207dc  mov     ecx, eax
0x1800207de  call    DebugTraceError
0x1800207e3  mov     edi, [rbp+var_20]
0x1800207e6  jmp     loc_1800209ED
0x1800207eb  mov     edi, [rbp+var_20]
0x1800207ee  cmp     edi, 0FFh
0x1800207f4  jbe     short loc_180020801
0x1800207f6  mov     r9d, 1131h
0x1800207fc  jmp     loc_1800209D0
0x180020801  mov     rcx, rdi
0x180020804  call    SafeAllocaAllocateFromHeap
0x180020809  mov     r14, rax
0x18002080c  test    rax, rax
0x18002080f  jnz     short loc_180020826
0x180020811  mov     r9d, 113Eh
0x180020817  mov     ebx, 8009000Eh
0x18002081c  mov     ecx, 8009000Eh
0x180020821  jmp     loc_1800209DA
0x180020826  mov     r9, [rbp+pbInput]
0x18002082a  xor     r8d, r8d
0x18002082d  mov     rcx, [rbp+arg_0]
0x180020831  xor     edx, edx
0x180020833  mov     byte ptr [rsp+60h+cbSecret], dil
0x180020838  mov     [rsp+60h+pbSecret], r14
0x18002083d  call    TlsHashContext
0x180020842  mov     ebx, eax
0x180020844  test    eax, eax
0x180020846  jns     short loc_180020855
0x180020848  mov     r9d, 1145h
0x18002084e  mov     ecx, eax
0x180020850  jmp     loc_1800209DA
0x180020855  mov     rcx, rdi
0x180020858  call    SafeAllocaAllocateFromHeap
0x18002085d  mov     rsi, rax
0x180020860  test    rax, rax
0x180020863  jnz     short loc_18002086D
0x180020865  mov     r9d, 114Dh
0x18002086b  jmp     short loc_180020817
0x18002086d  mov     rdx, [rbp+arg_10]
0x180020871  mov     r9b, dil
0x180020874  mov     word ptr [rsp+60h+cbSecret], di
0x180020879  mov     r8, r14
0x18002087c  mov     rcx, r13
0x18002087f  mov     [rsp+60h+pbSecret], rsi
0x180020884  call    TlsExpandLabel
0x180020889  mov     ebx, eax
0x18002088b  xor     eax, eax
0x18002088d  test    ebx, ebx
0x18002088f  jns     short loc_18002089E
0x180020891  mov     r9d, 1159h
0x180020897  mov     ecx, ebx
0x180020899  jmp     loc_1800209DA
0x18002089e  mov     [rsp+60h+dwFlags], eax; dwFlags
0x1800208a2  lea     rdx, [rbp+phKey]; phKey
0x1800208a6  mov     [rsp+60h+cbSecret], edi; cbSecret
0x1800208aa  xor     r9d, r9d; cbKeyObject
0x1800208ad  xor     r8d, r8d; pbKeyObject
0x1800208b0  mov     [rsp+60h+pbSecret], rsi; pbSecret
0x1800208b5  mov     ecx, 391h; hAlgorithm
0x1800208ba  call    cs:__imp_BCryptGenerateSymmetricKey
0x1800208c0  mov     ebx, eax
0x1800208c2  xor     eax, eax
0x1800208c4  test    ebx, ebx
0x1800208c6  jz      short loc_1800208D0
0x1800208c8  mov     r9d, 1168h
0x1800208ce  jmp     short loc_180020897
0x1800208d0  mov     r13, [rbp+pbInput]
0x1800208d4  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800208d8  inc     r9
0x1800208db  cmp     [r13+r9*2+0], ax
0x1800208e1  jnz     short loc_1800208D8
0x1800208e3  mov     rcx, [rbp+phKey]; hObject
0x1800208e7  lea     r9d, ds:2[r9*2]; cbInput
0x1800208ef  mov     r8, r13; pbInput
0x1800208f2  mov     dword ptr [rsp+60h+pbSecret], eax; dwFlags
0x1800208f6  lea     rdx, aHkdfhashalgori; "HkdfHashAlgorithm"
0x1800208fd  call    cs:__imp_BCryptSetProperty
0x180020903  mov     ebx, eax
0x180020905  xor     eax, eax
0x180020907  test    ebx, ebx
0x180020909  jz      short loc_180020913
0x18002090b  mov     r9d, 1175h
0x180020911  jmp     short loc_180020897
0x180020913  mov     rcx, [rbp+phKey]; hObject
0x180020917  lea     rdx, aHkdfprkandfina; "HkdfPrkAndFinalize"
0x18002091e  xor     r9d, r9d; cbInput
0x180020921  mov     dword ptr [rsp+60h+pbSecret], eax; dwFlags
0x180020925  xor     r8d, r8d; pbInput
0x180020928  call    cs:__imp_BCryptSetProperty
0x18002092e  mov     ebx, eax
0x180020930  test    eax, eax
0x180020932  jz      short loc_18002093F
0x180020934  mov     r9d, 1180h
0x18002093a  jmp     loc_18002084E
0x18002093f  mov     rcx, rdi
0x180020942  call    SafeAllocaAllocateFromHeap
0x180020947  mov     r15, rax
0x18002094a  test    rax, rax
0x18002094d  jnz     short loc_180020961
0x18002094f  mov     ebx, 0C0000017h
0x180020954  mov     r9d, 1189h
0x18002095a  mov     ecx, 0C0000017h
0x18002095f  jmp     short loc_1800209DA
0x180020961  movzx   r8d, [rbp+arg_20]
0x180020966  mov     r9, r13
0x180020969  mov     rdx, [rbp+arg_18]
0x18002096d  mov     rcx, [rbp+arg_0]
0x180020971  mov     byte ptr [rsp+60h+cbSecret], dil
0x180020976  mov     [rsp+60h+pbSecret], r15
0x18002097b  call    TlsHashContext
0x180020980  mov     ebx, eax
0x180020982  test    eax, eax
0x180020984  jns     short loc_180020991
0x180020986  mov     r9d, 118Fh
0x18002098c  jmp     loc_18002084E
0x180020991  movzx   eax, [rbp+arg_30]
0x180020995  lea     rdx, aExporter; "exporter"
0x18002099c  mov     rcx, [rbp+phKey]
0x1800209a0  mov     r9b, dil
0x1800209a3  mov     word ptr [rsp+60h+cbSecret], ax
0x1800209a8  mov     r8, r15
0x1800209ab  mov     rax, [rbp+arg_28]
0x1800209af  mov     [rsp+60h+pbSecret], rax
0x1800209b4  call    TlsExpandLabel
0x1800209b9  mov     ebx, eax
0x1800209bb  test    eax, eax
0x1800209bd  jns     short loc_1800209ED
0x1800209bf  mov     r9d, 119Dh
0x1800209c5  jmp     loc_18002084E
0x1800209ca  mov     r9d, 1124h
0x1800209d0  mov     ebx, 80090027h
0x1800209d5  mov     ecx, 80090027h
0x1800209da  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800209e1  lea     rdx, aStatus; "Status"
0x1800209e8  call    DebugTraceError
0x1800209ed  mov     rcx, [rbp+phKey]; hKey
0x1800209f1  test    rcx, rcx
0x1800209f4  jz      short loc_1800209FC
0x1800209f6  call    cs:__imp_BCryptDestroyKey
0x1800209fc  test    rsi, rsi
0x1800209ff  jz      short loc_180020A1E
0x180020a01  mov     eax, edi
0x180020a03  mov     rcx, rsi
0x180020a06  test    edi, edi
0x180020a08  jz      short loc_180020A16
0x180020a0a  mov     byte ptr [rcx], 0
0x180020a0d  inc     rcx
0x180020a10  sub     rax, 1
0x180020a14  jnz     short loc_180020A0A
0x180020a16  mov     rcx, rsi
0x180020a19  call    MSCryptFree
0x180020a1e  xor     esi, esi
0x180020a20  test    r14, r14
0x180020a23  jz      short loc_180020A42
0x180020a25  mov     ecx, edi
0x180020a27  mov     rax, r14
0x180020a2a  test    edi, edi
0x180020a2c  jz      short loc_180020A3A
0x180020a2e  mov     [rax], sil
0x180020a31  inc     rax
0x180020a34  sub     rcx, 1
0x180020a38  jnz     short loc_180020A2E
0x180020a3a  mov     rcx, r14
0x180020a3d  call    MSCryptFree
0x180020a42  test    r15, r15
0x180020a45  jz      short loc_180020A4F
0x180020a47  mov     rcx, r15
0x180020a4a  call    MSCryptFree
0x180020a4f  mov     eax, ebx
0x180020a51  mov     rbx, [rsp+60h+arg_8]
0x180020a59  add     rsp, 60h
0x180020a5d  pop     r15
0x180020a5f  pop     r14
0x180020a61  pop     r13
0x180020a63  pop     r12
0x180020a65  pop     rdi
0x180020a66  pop     rsi
0x180020a67  pop     rbp
0x180020a68  retn
```

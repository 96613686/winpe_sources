# TlsExportKeyingMaterial

- ea: `0x1800833d0`
- end: `0x18008371e`
- name: `TlsExportKeyingMaterial`
- size: `846`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180081dd0`

## callees

- `0x1800020c0`
- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x180035540`
- `0x180059be0`
- `0x180082810`
- `0x180082ee4`
- `0x1800833d0`
- `0x180083724`

## string_xrefs

- `0x180083486`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18008368f`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

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
  NTSTATUS v14; // ebx
  __int64 v15; // r9
  __int64 v16; // rax
  __int64 v17; // rcx
  NTSTATUS v18; // eax
  __int64 v19; // rax
  __int64 v20; // r9
  PUCHAR v21; // r13
  __int64 v22; // r9
  __int64 v23; // rax
  __int64 v24; // r9
  __int64 v25; // rax
  UCHAR *v26; // rcx
  __int64 v27; // rcx
  _BYTE *v28; // rax
  ULONG cbSecret; // [rsp+28h] [rbp-38h]
  ULONG cbSecreta; // [rsp+28h] [rbp-38h]
  ULONG cbSecretb; // [rsp+28h] [rbp-38h]
  ULONG v33; // [rsp+40h] [rbp-20h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+48h] [rbp-18h] BYREF
  PUCHAR pbInput[2]; // [rsp+50h] [rbp-10h] BYREF

  v33 = 0;
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
    v15 = 4388;
    goto LABEL_40;
  }
  PrfHashInfo = GetPrfHashInfo(v11, pbInput, &v33);
  v14 = PrfHashInfo;
  if ( PrfHashInfo < 0 )
  {
    DebugTraceError(
      (unsigned int)PrfHashInfo,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      4395);
    LODWORD(v7) = v33;
    goto LABEL_42;
  }
  v7 = v33;
  if ( v33 > 0xFF )
  {
    v15 = 4401;
LABEL_40:
    v14 = -2146893785;
    v17 = 2148073511LL;
    goto LABEL_41;
  }
  v16 = MSCryptAlloc(v33);
  v9 = (_BYTE *)v16;
  if ( v16 )
  {
    v18 = TlsHashContext(a1, 0, 0, pbInput[0], v16, (_BYTE)v7);
    v14 = v18;
    if ( v18 < 0 )
    {
      v15 = 4421;
LABEL_19:
      v17 = (unsigned int)v18;
      goto LABEL_41;
    }
    v19 = MSCryptAlloc(v7);
    pbSecret = (UCHAR *)v19;
    if ( !v19 )
    {
      v15 = 4429;
      goto LABEL_16;
    }
    LOBYTE(v20) = v7;
    LOWORD(cbSecret) = v7;
    v14 = TlsExpandLabel(v12, a3, v9, v20, v19, cbSecret);
    if ( v14 >= 0 )
    {
      v14 = BCryptGenerateSymmetricKey((BCRYPT_ALG_HANDLE)0x391, &phKey, 0, 0, pbSecret, v7, 0);
      if ( v14 )
      {
        v15 = 4456;
      }
      else
      {
        v21 = pbInput[0];
        v22 = -1;
        do
          ++v22;
        while ( *(_WORD *)&pbInput[0][2 * v22] );
        v14 = BCryptSetProperty(phKey, L"HkdfHashAlgorithm", pbInput[0], 2 * v22 + 2, 0);
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
            v23 = MSCryptAlloc(v7);
            v10 = (void *)v23;
            if ( !v23 )
            {
              v14 = -1073741801;
              v15 = 4489;
              v17 = 3221225495LL;
              goto LABEL_41;
            }
            LOBYTE(cbSecreta) = v7;
            v18 = TlsHashContext(a1, a4, a5, v21, v23, cbSecreta);
            v14 = v18;
            if ( v18 >= 0 )
            {
              LOBYTE(v24) = v7;
              LOWORD(cbSecretb) = a7;
              v18 = TlsExpandLabel(phKey, "exporter", v10, v24, a6, cbSecretb);
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
    v25 = (unsigned int)v7;
    v26 = pbSecret;
    if ( (_DWORD)v7 )
    {
      do
      {
        *v26++ = 0;
        --v25;
      }
      while ( v25 );
    }
    MSCryptFree(pbSecret);
  }
  if ( v9 )
  {
    v27 = (unsigned int)v7;
    v28 = v9;
    if ( (_DWORD)v7 )
    {
      do
      {
        *v28++ = 0;
        --v27;
      }
      while ( v27 );
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
0x1800833d0  mov     rax, rsp
0x1800833d3  mov     [rax+10h], rbx
0x1800833d7  mov     [rax+20h], r9
0x1800833db  mov     [rax+18h], r8
0x1800833df  mov     [rax+8], rcx
0x1800833e3  push    rbp
0x1800833e4  push    rsi
0x1800833e5  push    rdi
0x1800833e6  push    r12
0x1800833e8  push    r13
0x1800833ea  push    r14
0x1800833ec  push    r15
0x1800833ee  mov     rbp, rsp
0x1800833f1  sub     rsp, 60h
0x1800833f5  mov     rax, r8
0x1800833f8  xor     r8d, r8d
0x1800833fb  mov     [rbp+var_20], r8d
0x1800833ff  mov     edi, r8d
0x180083402  mov     [rbp+pbInput], r8
0x180083406  mov     esi, r8d
0x180083409  mov     [rbp+phKey], r8
0x18008340d  mov     r14d, r8d
0x180083410  mov     r15d, r8d
0x180083413  test    rcx, rcx
0x180083416  jz      loc_18008367F
0x18008341c  test    rdx, rdx
0x18008341f  jz      loc_18008367F
0x180083425  mov     rcx, [rdx+10h]
0x180083429  test    rcx, rcx
0x18008342c  jz      loc_18008367F
0x180083432  mov     r13, [rdx+20h]
0x180083436  test    r13, r13
0x180083439  jz      loc_18008367F
0x18008343f  test    rax, rax
0x180083442  jz      loc_18008367F
0x180083448  test    r9, r9
0x18008344b  jnz     short loc_180083458
0x18008344d  cmp     [rbp+arg_20], r8w
0x180083452  jnz     loc_18008367F
0x180083458  cmp     [rbp+arg_28], r8
0x18008345c  jz      loc_18008367F
0x180083462  cmp     [rbp+arg_30], r8w
0x180083467  jz      loc_18008367F
0x18008346d  lea     r8, [rbp+var_20]
0x180083471  lea     rdx, [rbp+pbInput]
0x180083475  call    GetPrfHashInfo
0x18008347a  mov     ebx, eax
0x18008347c  test    eax, eax
0x18008347e  jns     short loc_1800834A3
0x180083480  mov     r9d, 112Bh
0x180083486  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18008348d  lea     rdx, aStatus; "Status"
0x180083494  mov     ecx, eax
0x180083496  call    DebugTraceError
0x18008349b  mov     edi, [rbp+var_20]
0x18008349e  jmp     loc_1800836A2
0x1800834a3  mov     edi, [rbp+var_20]
0x1800834a6  cmp     edi, 0FFh
0x1800834ac  jbe     short loc_1800834B9
0x1800834ae  mov     r9d, 1131h
0x1800834b4  jmp     loc_180083685
0x1800834b9  mov     rcx, rdi
0x1800834bc  call    MSCryptAlloc
0x1800834c1  mov     r14, rax
0x1800834c4  test    rax, rax
0x1800834c7  jnz     short loc_1800834DE
0x1800834c9  mov     r9d, 113Eh
0x1800834cf  mov     ebx, 8009000Eh
0x1800834d4  mov     ecx, 8009000Eh
0x1800834d9  jmp     loc_18008368F
0x1800834de  mov     r9, [rbp+pbInput]
0x1800834e2  xor     r8d, r8d
0x1800834e5  mov     rcx, [rbp+arg_0]
0x1800834e9  xor     edx, edx
0x1800834eb  mov     byte ptr [rsp+60h+cbSecret], dil
0x1800834f0  mov     [rsp+60h+pbSecret], r14
0x1800834f5  call    TlsHashContext
0x1800834fa  mov     ebx, eax
0x1800834fc  test    eax, eax
0x1800834fe  jns     short loc_18008350D
0x180083500  mov     r9d, 1145h
0x180083506  mov     ecx, eax
0x180083508  jmp     loc_18008368F
0x18008350d  mov     rcx, rdi
0x180083510  call    MSCryptAlloc
0x180083515  mov     rsi, rax
0x180083518  test    rax, rax
0x18008351b  jnz     short loc_180083525
0x18008351d  mov     r9d, 114Dh
0x180083523  jmp     short loc_1800834CF
0x180083525  mov     rdx, [rbp+arg_10]
0x180083529  mov     r9b, dil
0x18008352c  mov     word ptr [rsp+60h+cbSecret], di
0x180083531  mov     r8, r14
0x180083534  mov     rcx, r13
0x180083537  mov     [rsp+60h+pbSecret], rsi
0x18008353c  call    TlsExpandLabel
0x180083541  mov     ebx, eax
0x180083543  xor     eax, eax
0x180083545  test    ebx, ebx
0x180083547  jns     short loc_180083556
0x180083549  mov     r9d, 1159h
0x18008354f  mov     ecx, ebx
0x180083551  jmp     loc_18008368F
0x180083556  mov     [rsp+60h+dwFlags], eax; dwFlags
0x18008355a  lea     rdx, [rbp+phKey]; phKey
0x18008355e  mov     [rsp+60h+cbSecret], edi; cbSecret
0x180083562  xor     r9d, r9d; cbKeyObject
0x180083565  xor     r8d, r8d; pbKeyObject
0x180083568  mov     [rsp+60h+pbSecret], rsi; pbSecret
0x18008356d  mov     ecx, 391h; hAlgorithm
0x180083572  call    BCryptGenerateSymmetricKey
0x180083577  mov     ebx, eax
0x180083579  xor     eax, eax
0x18008357b  test    ebx, ebx
0x18008357d  jz      short loc_180083587
0x18008357f  mov     r9d, 1168h
0x180083585  jmp     short loc_18008354F
0x180083587  mov     r13, [rbp+pbInput]
0x18008358b  or      r9, 0FFFFFFFFFFFFFFFFh
0x18008358f  inc     r9
0x180083592  cmp     [r13+r9*2+0], ax
0x180083598  jnz     short loc_18008358F
0x18008359a  mov     rcx, [rbp+phKey]; hObject
0x18008359e  lea     r9d, ds:2[r9*2]; cbInput
0x1800835a6  mov     r8, r13; pbInput
0x1800835a9  mov     dword ptr [rsp+60h+pbSecret], eax; dwFlags
0x1800835ad  lea     rdx, aHkdfhashalgori; "HkdfHashAlgorithm"
0x1800835b4  call    BCryptSetProperty
0x1800835b9  mov     ebx, eax
0x1800835bb  xor     eax, eax
0x1800835bd  test    ebx, ebx
0x1800835bf  jz      short loc_1800835C9
0x1800835c1  mov     r9d, 1175h
0x1800835c7  jmp     short loc_18008354F
0x1800835c9  mov     rcx, [rbp+phKey]; hObject
0x1800835cd  lea     rdx, aHkdfprkandfina; "HkdfPrkAndFinalize"
0x1800835d4  xor     r9d, r9d; cbInput
0x1800835d7  mov     dword ptr [rsp+60h+pbSecret], eax; dwFlags
0x1800835db  xor     r8d, r8d; pbInput
0x1800835de  call    BCryptSetProperty
0x1800835e3  mov     ebx, eax
0x1800835e5  test    eax, eax
0x1800835e7  jz      short loc_1800835F4
0x1800835e9  mov     r9d, 1180h
0x1800835ef  jmp     loc_180083506
0x1800835f4  mov     rcx, rdi
0x1800835f7  call    MSCryptAlloc
0x1800835fc  mov     r15, rax
0x1800835ff  test    rax, rax
0x180083602  jnz     short loc_180083616
0x180083604  mov     ebx, 0C0000017h
0x180083609  mov     r9d, 1189h
0x18008360f  mov     ecx, 0C0000017h
0x180083614  jmp     short loc_18008368F
0x180083616  movzx   r8d, [rbp+arg_20]
0x18008361b  mov     r9, r13
0x18008361e  mov     rdx, [rbp+arg_18]
0x180083622  mov     rcx, [rbp+arg_0]
0x180083626  mov     byte ptr [rsp+60h+cbSecret], dil
0x18008362b  mov     [rsp+60h+pbSecret], r15
0x180083630  call    TlsHashContext
0x180083635  mov     ebx, eax
0x180083637  test    eax, eax
0x180083639  jns     short loc_180083646
0x18008363b  mov     r9d, 118Fh
0x180083641  jmp     loc_180083506
0x180083646  movzx   eax, [rbp+arg_30]
0x18008364a  lea     rdx, aExporter; "exporter"
0x180083651  mov     rcx, [rbp+phKey]
0x180083655  mov     r9b, dil
0x180083658  mov     word ptr [rsp+60h+cbSecret], ax
0x18008365d  mov     r8, r15
0x180083660  mov     rax, [rbp+arg_28]
0x180083664  mov     [rsp+60h+pbSecret], rax
0x180083669  call    TlsExpandLabel
0x18008366e  mov     ebx, eax
0x180083670  test    eax, eax
0x180083672  jns     short loc_1800836A2
0x180083674  mov     r9d, 119Dh
0x18008367a  jmp     loc_180083506
0x18008367f  mov     r9d, 1124h
0x180083685  mov     ebx, 80090027h
0x18008368a  mov     ecx, 80090027h
0x18008368f  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180083696  lea     rdx, aStatus; "Status"
0x18008369d  call    DebugTraceError
0x1800836a2  mov     rcx, [rbp+phKey]; hKey
0x1800836a6  test    rcx, rcx
0x1800836a9  jz      short loc_1800836B0
0x1800836ab  call    BCryptDestroyKey
0x1800836b0  test    rsi, rsi
0x1800836b3  jz      short loc_1800836D2
0x1800836b5  mov     eax, edi
0x1800836b7  mov     rcx, rsi
0x1800836ba  test    edi, edi
0x1800836bc  jz      short loc_1800836CA
0x1800836be  mov     byte ptr [rcx], 0
0x1800836c1  inc     rcx
0x1800836c4  sub     rax, 1
0x1800836c8  jnz     short loc_1800836BE
0x1800836ca  mov     rcx, rsi; P
0x1800836cd  call    MSCryptFree
0x1800836d2  xor     esi, esi
0x1800836d4  test    r14, r14
0x1800836d7  jz      short loc_1800836F6
0x1800836d9  mov     ecx, edi
0x1800836db  mov     rax, r14
0x1800836de  test    edi, edi
0x1800836e0  jz      short loc_1800836EE
0x1800836e2  mov     [rax], sil
0x1800836e5  inc     rax
0x1800836e8  sub     rcx, 1
0x1800836ec  jnz     short loc_1800836E2
0x1800836ee  mov     rcx, r14; P
0x1800836f1  call    MSCryptFree
0x1800836f6  test    r15, r15
0x1800836f9  jz      short loc_180083703
0x1800836fb  mov     rcx, r15; P
0x1800836fe  call    MSCryptFree
0x180083703  mov     eax, ebx
0x180083705  mov     rbx, [rsp+60h+arg_8]
0x18008370d  add     rsp, 60h
0x180083711  pop     r15
0x180083713  pop     r14
0x180083715  pop     r13
0x180083717  pop     r12
0x180083719  pop     rdi
0x18008371a  pop     rsi
0x18008371b  pop     rbp
0x18008371c  retn
```

# SPSslExtractHandshakeKey

- ea: `0x18000dea0`
- end: `0x18000e30f`
- name: `SPSslExtractHandshakeKey`
- size: `1135`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x180003ef0`
- `0x180005860`
- `0x1800068e0`
- `0x180007940`
- `0x180009ca0`
- `0x18000b594`
- `0x18000b654`
- `0x18000cfb0`
- `0x18000dea0`
- `0x18000e7f0`
- `0x18000e820`
- `0x180013f08`
- `0x180021efc`
- `0x180022fa8`
- `0x180025660`

## string_xrefs

- `0x18000df2c`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000df71`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000e054`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000e1dc`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000e277`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000e296`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslExtractHandshakeKey(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 *a5)
{
  __int64 v7; // r9
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // r12d
  __int64 v12; // r15
  __int64 v13; // rdi
  __int64 v14; // rsi
  __int64 v15; // r9
  unsigned int v16; // ebx
  __int64 v17; // rcx
  __int64 v18; // rbx
  wchar_t *v19; // rbx
  __int64 HashInfoFromAlgorithmName; // rax
  UCHAR *v21; // rax
  int v22; // eax
  _BYTE *v23; // rsi
  __int64 v24; // r9
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // r9
  __int64 v28; // rax
  ULONG v29; // edx
  UCHAR *v30; // rcx
  int v31; // edx
  __int64 v32; // rax
  _BYTE *v33; // rcx
  PUCHAR v34; // rax
  __int64 v35; // rcx
  _BYTE *v36; // rax
  int v38; // [rsp+28h] [rbp-28h]
  UCHAR *v39; // [rsp+40h] [rbp-10h]
  __int64 v40; // [rsp+48h] [rbp-8h]
  ULONG cbSecret; // [rsp+98h] [rbp+48h] BYREF
  PUCHAR pbSecret; // [rsp+A0h] [rbp+50h] BYREF

  v40 = SslpValidateProvHandle(a1);
  v8 = SslpValidateKeyHandle(v7);
  v11 = 0;
  v12 = v8;
  pbSecret = 0;
  v13 = 0;
  cbSecret = 0;
  v14 = 112;
  if ( !v9 || !a2 || !v10 || !v8 )
  {
    v16 = -2146893786;
    DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", 5656);
LABEL_61:
    v34 = pbSecret;
    if ( pbSecret )
    {
      v35 = cbSecret;
      if ( cbSecret )
      {
        do
        {
          *v34++ = 0;
          --v35;
        }
        while ( v35 );
      }
      MSCryptFree(pbSecret);
    }
    if ( v13 )
    {
      v36 = (_BYTE *)v13;
      do
      {
        *v36++ = 0;
        --v14;
      }
      while ( v14 );
      MSCryptFree(v13);
    }
    return v16;
  }
  if ( *(_DWORD *)(a2 + 4) != *(_DWORD *)(v10 + 4) )
  {
    v15 = 5663;
LABEL_7:
    v16 = -2146893785;
    v17 = 2148073511LL;
LABEL_8:
    DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v15);
    return v16;
  }
  if ( !a5 )
  {
    v16 = -2146893785;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        38);
    return v16;
  }
  if ( *(_DWORD *)(v8 + 8) == 772 && *(_DWORD *)(v8 + 108) == 1 )
  {
    v18 = *(_QWORD *)(v8 + 16);
    if ( v18 )
    {
      v19 = *(wchar_t **)(v18 + 136);
      if ( !v19 || !*v19 )
        v19 = L"SHA256";
      HashInfoFromAlgorithmName = I_GetHashInfoFromAlgorithmName(v19);
      if ( HashInfoFromAlgorithmName )
      {
        v11 = *(_DWORD *)(HashInfoFromAlgorithmName + 8);
        if ( v11 > 0xFF )
        {
          v15 = 5693;
          goto LABEL_7;
        }
      }
      else
      {
        v19 = 0;
      }
      v21 = (UCHAR *)SafeAllocaAllocateFromHeap(v11);
      v39 = v21;
      if ( !v21 )
      {
        v16 = -2146893810;
        v15 = 5709;
        v17 = 2148073486LL;
        goto LABEL_8;
      }
      v22 = TlsHashContext(v40, 0, 0, v19, v21, v11);
      v16 = v22;
      if ( v22 < 0 )
      {
        v23 = 0;
        v24 = 5715;
LABEL_28:
        v25 = (unsigned int)v22;
LABEL_29:
        DebugTraceError(v25, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v24);
LABEL_52:
        MSCryptFree(v39);
        if ( v23 )
        {
          v32 = v11;
          v33 = v23;
          if ( v11 )
          {
            do
            {
              *v23++ = 0;
              --v32;
            }
            while ( v32 );
          }
          MSCryptFree(v33);
          v14 = 112;
        }
        else
        {
          v14 = 112;
        }
        goto LABEL_61;
      }
      v26 = SafeAllocaAllocateFromHeap(v11);
      v23 = (_BYTE *)v26;
      if ( v26 )
      {
        LOBYTE(v27) = v11;
        LOWORD(v38) = v11;
        v22 = TlsExpandLabel(*(_QWORD *)(v12 + 32), "derived", v39, v27, v26, v38);
        v16 = v22;
        if ( v22 < 0 )
        {
          v24 = 5739;
          goto LABEL_28;
        }
        switch ( *(_DWORD *)(a2 + 4) )
        {
          case 0x73736C36:
            v22 = SslpExtractEcdhSharedKey(a2, a3, &pbSecret, &cbSecret);
            v16 = v22;
            if ( v22 < 0 )
            {
              v24 = 5758;
              goto LABEL_28;
            }
            break;
          case 0x73736C3B:
            v22 = SslpExtractHybridSharedKey(a2, a3, &pbSecret, &cbSecret);
            v16 = v22;
            if ( v22 < 0 )
            {
              v24 = 5788;
              goto LABEL_28;
            }
            break;
          case 0x73736C3C:
            v22 = SslpExtractKemSharedKey(a2, a3, (__int64 *)&pbSecret, &cbSecret);
            v16 = v22;
            if ( v22 < 0 )
            {
              v24 = 5773;
              goto LABEL_28;
            }
            break;
          default:
            v16 = -2146893783;
            v24 = 5797;
            v25 = 2148073513LL;
            goto LABEL_29;
        }
        v28 = SafeAllocaAllocateFromHeap(112);
        v13 = v28;
        if ( v28 )
        {
          memset((void *)(v28 + 8), 0, 0x68u);
          v29 = cbSecret;
          v30 = pbSecret;
          *(_DWORD *)v13 = 112;
          *(_DWORD *)(v13 + 4) = 1936944179;
          *(_DWORD *)(v13 + 8) = *(_DWORD *)(v12 + 8);
          *(_QWORD *)(v13 + 16) = *(_QWORD *)(v12 + 16);
          *(_DWORD *)(v13 + 108) = 2;
          v16 = TlsHkdfExtract(v30, v29, v13);
          if ( (v16 & 0x80000000) == 0 )
          {
            *a5 = v13;
            v13 = 0;
          }
          else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v31,
              (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
              (unsigned int)"Status",
              v16,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
              202);
          }
          goto LABEL_52;
        }
        v24 = 5810;
      }
      else
      {
        v24 = 5727;
      }
      v16 = -2146893810;
      v25 = 2148073486LL;
      goto LABEL_29;
    }
  }
  v16 = -2146893783;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
      (unsigned int)"Status",
      41,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
      48);
  return v16;
}

```

## disassembly

```asm
0x18000dea0  mov     [rsp-38h+arg_0], rbx
0x18000dea5  push    rbp
0x18000dea6  push    rsi
0x18000dea7  push    rdi
0x18000dea8  push    r12
0x18000deaa  push    r13
0x18000deac  push    r14
0x18000deae  push    r15
0x18000deb0  mov     rbp, rsp
0x18000deb3  sub     rsp, 50h
0x18000deb7  mov     r13, r8
0x18000deba  mov     r14, rdx
0x18000debd  call    SslpValidateProvHandle
0x18000dec2  mov     rcx, r9
0x18000dec5  mov     [rbp+var_8], rax
0x18000dec9  mov     rdx, rax
0x18000decc  call    SslpValidateKeyHandle
0x18000ded1  xor     r12d, r12d
0x18000ded4  mov     r15, rax
0x18000ded7  mov     [rbp+pbSecret], r12
0x18000dedb  mov     edi, r12d
0x18000dede  mov     [rbp+cbSecret], r12d
0x18000dee2  lea     esi, [r12+70h]
0x18000dee7  test    rdx, rdx
0x18000deea  jz      loc_18000E290
0x18000def0  test    r14, r14
0x18000def3  jz      loc_18000E290
0x18000def9  test    r8, r8
0x18000defc  jz      loc_18000E290
0x18000df02  test    rax, rax
0x18000df05  jz      loc_18000E290
0x18000df0b  mov     eax, [r8+4]
0x18000df0f  cmp     [r14+4], eax
0x18000df13  jz      short loc_18000DF3D
0x18000df15  mov     r9d, 161Fh
0x18000df1b  mov     ebx, 80090027h
0x18000df20  mov     ecx, 80090027h
0x18000df25  lea     rdx, aStatus; "Status"
0x18000df2c  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000df33  call    DebugTraceError
0x18000df38  jmp     loc_18000E2F5
0x18000df3d  cmp     [rbp+arg_20], r12
0x18000df41  jnz     short loc_18000DF9A
0x18000df43  mov     ebx, 80090027h
0x18000df48  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df4f  lea     rax, WPP_GLOBAL_Control
0x18000df56  cmp     rcx, rax
0x18000df59  jz      loc_18000E2F5
0x18000df5f  test    byte ptr [rcx+1Ch], 1
0x18000df63  jz      loc_18000E2F5
0x18000df69  mov     [rsp+50h+var_20], 1626h
0x18000df71  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000df78  mov     [rsp+50h+var_28], r8
0x18000df7d  mov     dword ptr [rsp+50h+var_30], 80090027h
0x18000df85  mov     rcx, [rcx+10h]
0x18000df89  lea     r9, aStatus; "Status"
0x18000df90  call    WPP_SF_sDsd
0x18000df95  jmp     loc_18000E2F5
0x18000df9a  cmp     dword ptr [r15+8], 304h
0x18000dfa2  jnz     loc_18000E249
0x18000dfa8  cmp     dword ptr [r15+6Ch], 1
0x18000dfad  jnz     loc_18000E249
0x18000dfb3  mov     rbx, [r15+10h]
0x18000dfb7  test    rbx, rbx
0x18000dfba  jz      loc_18000E249
0x18000dfc0  mov     rbx, [rbx+88h]
0x18000dfc7  test    rbx, rbx
0x18000dfca  jz      short loc_18000DFD2
0x18000dfcc  cmp     [rbx], r12w
0x18000dfd0  jnz     short loc_18000DFD9
0x18000dfd2  lea     rbx, aSha256; "SHA256"
0x18000dfd9  mov     rcx, rbx; String1
0x18000dfdc  call    I_GetHashInfoFromAlgorithmName
0x18000dfe1  test    rax, rax
0x18000dfe4  jnz     short loc_18000E011
0x18000dfe6  xor     ebx, ebx
0x18000dfe8  mov     ecx, r12d
0x18000dfeb  mov     esi, r12d
0x18000dfee  call    SafeAllocaAllocateFromHeap
0x18000dff3  mov     [rbp+var_10], rax
0x18000dff7  test    rax, rax
0x18000dffa  jnz     short loc_18000E029
0x18000dffc  mov     ebx, 8009000Eh
0x18000e001  mov     r9d, 164Dh
0x18000e007  mov     ecx, 8009000Eh
0x18000e00c  jmp     loc_18000DF25
0x18000e011  mov     r12d, [rax+8]
0x18000e015  cmp     r12d, 0FFh
0x18000e01c  jbe     short loc_18000DFE8
0x18000e01e  mov     r9d, 163Dh
0x18000e024  jmp     loc_18000DF1B
0x18000e029  mov     rcx, [rbp+var_8]
0x18000e02d  xor     r8d, r8d
0x18000e030  mov     byte ptr [rsp+50h+var_28], r12b
0x18000e035  mov     r9, rbx
0x18000e038  xor     edx, edx
0x18000e03a  mov     [rsp+50h+var_30], rax
0x18000e03f  call    TlsHashContext
0x18000e044  mov     ebx, eax
0x18000e046  test    eax, eax
0x18000e048  jns     short loc_18000E06C
0x18000e04a  xor     esi, esi
0x18000e04c  mov     r9d, 1653h
0x18000e052  mov     ecx, eax
0x18000e054  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e05b  lea     rdx, aStatus; "Status"
0x18000e062  call    DebugTraceError
0x18000e067  jmp     loc_18000E20B
0x18000e06c  mov     rcx, rsi
0x18000e06f  call    SafeAllocaAllocateFromHeap
0x18000e074  mov     rsi, rax
0x18000e077  test    rax, rax
0x18000e07a  jnz     short loc_18000E08E
0x18000e07c  mov     r9d, 165Fh
0x18000e082  mov     ebx, 8009000Eh
0x18000e087  mov     ecx, 8009000Eh
0x18000e08c  jmp     short loc_18000E054
0x18000e08e  mov     r8, [rbp+var_10]
0x18000e092  lea     rdx, Src; "derived"
0x18000e099  mov     rcx, [r15+20h]
0x18000e09d  mov     r9b, r12b
0x18000e0a0  mov     word ptr [rsp+50h+var_28], r12w
0x18000e0a6  mov     [rsp+50h+var_30], rsi
0x18000e0ab  call    TlsExpandLabel
0x18000e0b0  mov     ebx, eax
0x18000e0b2  test    eax, eax
0x18000e0b4  jns     short loc_18000E0BE
0x18000e0b6  mov     r9d, 166Bh
0x18000e0bc  jmp     short loc_18000E052
0x18000e0be  mov     ecx, [r14+4]
0x18000e0c2  sub     ecx, 73736C36h
0x18000e0c8  jz      short loc_18000E131
0x18000e0ca  sub     ecx, 5
0x18000e0cd  jz      short loc_18000E10D
0x18000e0cf  cmp     ecx, 1
0x18000e0d2  jz      short loc_18000E0E9
0x18000e0d4  mov     ebx, 80090029h
0x18000e0d9  mov     r9d, 16A5h
0x18000e0df  mov     ecx, 80090029h
0x18000e0e4  jmp     loc_18000E054
0x18000e0e9  lea     r9, [rbp+cbSecret]
0x18000e0ed  mov     rdx, r13
0x18000e0f0  lea     r8, [rbp+pbSecret]
0x18000e0f4  mov     rcx, r14
0x18000e0f7  call    SslpExtractKemSharedKey
0x18000e0fc  mov     ebx, eax
0x18000e0fe  test    eax, eax
0x18000e100  jns     short loc_18000E155
0x18000e102  mov     r9d, 168Dh
0x18000e108  jmp     loc_18000E052
0x18000e10d  lea     r9, [rbp+cbSecret]
0x18000e111  mov     rdx, r13
0x18000e114  lea     r8, [rbp+pbSecret]
0x18000e118  mov     rcx, r14
0x18000e11b  call    SslpExtractHybridSharedKey
0x18000e120  mov     ebx, eax
0x18000e122  test    eax, eax
0x18000e124  jns     short loc_18000E155
0x18000e126  mov     r9d, 169Ch
0x18000e12c  jmp     loc_18000E052
0x18000e131  lea     r9, [rbp+cbSecret]
0x18000e135  mov     rdx, r13
0x18000e138  lea     r8, [rbp+pbSecret]
0x18000e13c  mov     rcx, r14
0x18000e13f  call    SslpExtractEcdhSharedKey
0x18000e144  mov     ebx, eax
0x18000e146  test    eax, eax
0x18000e148  jns     short loc_18000E155
0x18000e14a  mov     r9d, 167Eh
0x18000e150  jmp     loc_18000E052
0x18000e155  mov     ebx, 70h ; 'p'
0x18000e15a  mov     ecx, ebx
0x18000e15c  call    SafeAllocaAllocateFromHeap
0x18000e161  mov     rdi, rax
0x18000e164  test    rax, rax
0x18000e167  jnz     short loc_18000E174
0x18000e169  mov     r9d, 16B2h
0x18000e16f  jmp     loc_18000E082
0x18000e174  xor     edx, edx; Val
0x18000e176  lea     rcx, [rax+8]; void *
0x18000e17a  lea     r8d, [rdx+68h]; Size
0x18000e17e  call    memset
0x18000e183  mov     edx, [rbp+cbSecret]; cbSecret
0x18000e186  mov     r9d, r12d
0x18000e189  mov     rcx, [rbp+pbSecret]; pbSecret
0x18000e18d  mov     r8, rsi
0x18000e190  mov     [rdi], ebx
0x18000e192  mov     dword ptr [rdi+4], 73736C33h
0x18000e199  mov     eax, [r15+8]
0x18000e19d  mov     [rdi+8], eax
0x18000e1a0  mov     rax, [r15+10h]
0x18000e1a4  mov     [rdi+10h], rax
0x18000e1a8  mov     dword ptr [rdi+6Ch], 2
0x18000e1af  mov     [rsp+50h+var_30], rdi; __int64
0x18000e1b4  call    TlsHkdfExtract
0x18000e1b9  mov     ebx, eax
0x18000e1bb  test    eax, eax
0x18000e1bd  jns     short loc_18000E202
0x18000e1bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e1c6  lea     rax, WPP_GLOBAL_Control
0x18000e1cd  cmp     rcx, rax
0x18000e1d0  jz      short loc_18000E20B
0x18000e1d2  test    byte ptr [rcx+1Ch], 1
0x18000e1d6  jz      short loc_18000E20B
0x18000e1d8  mov     rcx, [rcx+10h]
0x18000e1dc  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e1e3  mov     [rsp+50h+var_20], 16CAh
0x18000e1eb  lea     r9, aStatus; "Status"
0x18000e1f2  mov     [rsp+50h+var_28], r8
0x18000e1f7  mov     dword ptr [rsp+50h+var_30], ebx
0x18000e1fb  call    WPP_SF_sDsd
0x18000e200  jmp     short loc_18000E20B
0x18000e202  mov     rax, [rbp+arg_20]
0x18000e206  mov     [rax], rdi
0x18000e209  xor     edi, edi
0x18000e20b  mov     rcx, [rbp+var_10]
0x18000e20f  call    MSCryptFree
0x18000e214  test    rsi, rsi
0x18000e217  jz      short loc_18000E23F
0x18000e219  mov     eax, r12d
0x18000e21c  mov     rcx, rsi
0x18000e21f  xor     r12d, r12d
0x18000e222  test    rax, rax
0x18000e225  jz      short loc_18000E233
0x18000e227  mov     [rsi], r12b
0x18000e22a  inc     rsi
0x18000e22d  sub     rax, 1
0x18000e231  jnz     short loc_18000E227
0x18000e233  call    MSCryptFree
0x18000e238  mov     esi, 70h ; 'p'
0x18000e23d  jmp     short loc_18000E2B3
0x18000e23f  mov     esi, 70h ; 'p'
0x18000e244  xor     r12d, r12d
0x18000e247  jmp     short loc_18000E2B3
0x18000e249  mov     ebx, 80090029h
0x18000e24e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e255  lea     rax, WPP_GLOBAL_Control
0x18000e25c  cmp     rcx, rax
0x18000e25f  jz      loc_18000E2F5
0x18000e265  test    byte ptr [rcx+1Ch], 1
0x18000e269  jz      loc_18000E2F5
0x18000e26f  mov     [rsp+50h+var_20], 1630h
0x18000e277  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e27e  mov     [rsp+50h+var_28], r8
0x18000e283  mov     dword ptr [rsp+50h+var_30], 80090029h
0x18000e28b  jmp     loc_18000DF85
0x18000e290  mov     r9d, 1618h
0x18000e296  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e29d  lea     rdx, aStatus; "Status"
0x18000e2a4  mov     ecx, 80090026h
0x18000e2a9  mov     ebx, 80090026h
0x18000e2ae  call    DebugTraceError
0x18000e2b3  mov     rax, [rbp+pbSecret]
0x18000e2b7  test    rax, rax
0x18000e2ba  jz      short loc_18000E2D9
0x18000e2bc  mov     ecx, [rbp+cbSecret]
0x18000e2bf  test    rcx, rcx
0x18000e2c2  jz      short loc_18000E2D0
0x18000e2c4  mov     [rax], r12b
0x18000e2c7  inc     rax
0x18000e2ca  sub     rcx, 1
0x18000e2ce  jnz     short loc_18000E2C4
0x18000e2d0  mov     rcx, [rbp+pbSecret]
0x18000e2d4  call    MSCryptFree
0x18000e2d9  test    rdi, rdi
0x18000e2dc  jz      short loc_18000E2F5
0x18000e2de  mov     rax, rdi
0x18000e2e1  mov     [rax], r12b
0x18000e2e4  inc     rax
0x18000e2e7  sub     rsi, 1
0x18000e2eb  jnz     short loc_18000E2E1
0x18000e2ed  mov     rcx, rdi
0x18000e2f0  call    MSCryptFree
0x18000e2f5  mov     eax, ebx
0x18000e2f7  mov     rbx, [rsp+50h+arg_0]
0x18000e2ff  add     rsp, 50h
0x18000e303  pop     r15
0x18000e305  pop     r14
0x18000e307  pop     r13
0x18000e309  pop     r12
0x18000e30b  pop     rdi
0x18000e30c  pop     rsi
0x18000e30d  pop     rbp
0x18000e30e  retn
```

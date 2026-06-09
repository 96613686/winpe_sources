# Tls13DecryptPacket

- ea: `0x180011880`
- end: `0x180011c6d`
- name: `Tls13DecryptPacket`
- size: `1005`
- prototype: `__int64 __fastcall(int, int, int, int, PUCHAR, ULONG, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800115b0`

## callees

- `0x18001155c`
- `0x180011880`
- `0x180011c80`
- `0x1800123d0`

## string_xrefs

- `0x180011a79`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180011acf`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180011b17`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180011b75`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180011bd3`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180011bfb`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180011c23`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180011c4b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800a5df9`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall Tls13DecryptPacket(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        unsigned int a4,
        PUCHAR pbOutput,
        ULONG cbOutput,
        ULONG *a7,
        unsigned __int64 a8)
{
  ULONG *v8; // rbx
  unsigned __int16 v9; // ax
  unsigned __int16 v10; // ax
  int v11; // esi
  void *v12; // rcx
  NTSTATUS v13; // edi
  int v15; // edx
  int v16; // edx
  int v17; // edx
  int v18; // edx
  __int128 v19; // [rsp+50h] [rbp-78h] BYREF
  _DWORD pPaddingInfo[2]; // [rsp+60h] [rbp-68h] BYREF
  char *v21; // [rsp+68h] [rbp-60h]
  __int64 v22; // [rsp+70h] [rbp-58h]
  unsigned __int64 v23; // [rsp+78h] [rbp-50h]
  int v24; // [rsp+80h] [rbp-48h]
  int v25; // [rsp+84h] [rbp-44h]
  __int128 v26; // [rsp+88h] [rbp-40h]
  __int128 v27; // [rsp+98h] [rbp-30h]
  __int128 v28; // [rsp+A8h] [rbp-20h]
  ULONG pcbResult; // [rsp+D0h] [rbp+8h] BYREF

  pPaddingInfo[0] = 88;
  pPaddingInfo[1] = 1;
  v21 = (char *)&v19 + 4;
  pcbResult = 0;
  v22 = 12;
  v25 = 0;
  v19 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  if ( !a1 || !a2 || !a3 || !pbOutput || (v8 = a7) == 0 )
  {
    DebugTraceError(
      2148073511LL,
      "NTE_INVALID_PARAMETER",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      4912);
    return 2148073511LL;
  }
  if ( *(_DWORD *)(a2 + 8) != 772 || *(_DWORD *)(a2 + 108) != 5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v17 = *((_DWORD *)WPP_GLOBAL_Control + 11);
      if ( (v17 & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v17,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
          (unsigned int)"NTE_NOT_SUPPORTED",
          41,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
          55);
    }
    return 2148073513LL;
  }
  if ( a4 - 22 > 0x40EA )
  {
    DebugTraceError(2148073477LL, "NTE_BAD_DATA", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", 4927);
    return 2148073477LL;
  }
  if ( (PUCHAR)(a3 + 5) != pbOutput )
  {
    if ( a3 <= (unsigned __int64)pbOutput )
    {
      if ( (unsigned __int64)pbOutput < a3 + a4 )
        goto LABEL_43;
      if ( a3 < (unsigned __int64)pbOutput )
        goto LABEL_10;
    }
    if ( a3 >= (unsigned __int64)&pbOutput[cbOutput] )
      goto LABEL_10;
LABEL_43:
    DebugTraceError(
      2148073515LL,
      "NTE_BUFFERS_OVERLAP",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      4936);
    return 2148073515LL;
  }
LABEL_10:
  if ( *(_BYTE *)(a3 + 1) == 0xFE )
  {
    DebugTraceError(2148073477LL, "NTE_BAD_DATA", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", 4956);
    return 2148073477LL;
  }
  else
  {
    v9 = _byteswap_ushort(*(_WORD *)(a3 + 3));
    if ( v9 > 0x10u && v9 + 5 == a4 )
    {
      v10 = v9 - 16;
      v11 = v10;
      if ( cbOutput < v10 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          v18 = *((_DWORD *)WPP_GLOBAL_Control + 11);
          if ( (v18 & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v18,
              (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
              (unsigned int)"NTE_BUFFER_TOO_SMALL",
              40,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
              105);
        }
        return 2148073512LL;
      }
      else
      {
        DWORD1(v19) = *(_DWORD *)(a2 + 56);
        *((_QWORD *)&v19 + 1) = *(_QWORD *)(a2 + 60) ^ _byteswap_uint64(a8);
        v23 = a3;
        *(_QWORD *)&v26 = v10 + a3 + 5;
        v12 = *(void **)(a2 + 32);
        v24 = 5;
        DWORD2(v26) = 16;
        v13 = BCryptDecrypt(v12, (PUCHAR)(a3 + 5), v10, pPaddingInfo, 0, 0, pbOutput, cbOutput, &pcbResult, 0);
        if ( v13 < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            v16 = *((_DWORD *)WPP_GLOBAL_Control + 11);
            if ( (v16 & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v16,
                (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                (unsigned int)"Status",
                v13,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                137);
          }
        }
        else
        {
          if ( pcbResult != v11 )
          {
            DebugTraceError(
              2148073516LL,
              "NTE_DECRYPTION_FAILURE",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
              5006);
            return 2148073516LL;
          }
          *v8 = pcbResult;
        }
        return (unsigned int)v13;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        v15 = *((_DWORD *)WPP_GLOBAL_Control + 11);
        if ( (v15 & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v15,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
            (unsigned int)"NTE_BAD_DATA",
            5,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
            98);
      }
      return 2148073477LL;
    }
  }
}

```

## disassembly

```asm
0x180011880  mov     r11, rsp
0x180011883  mov     [r11+20h], rbx
0x180011887  push    rbp
0x180011888  sub     rsp, 0C0h
0x18001188f  mov     [rsp+0C8h+pPaddingInfo], 58h ; 'X'
0x180011897  lea     rax, [r11-74h]
0x18001189b  mov     [rsp+0C8h+var_64], 1
0x1800118a3  xorps   xmm0, xmm0
0x1800118a6  xor     ebp, ebp
0x1800118a8  mov     [r11-60h], rax
0x1800118ac  xor     eax, eax
0x1800118ae  mov     [r11+8], ebp
0x1800118b2  mov     qword ptr [r11-58h], 0Ch
0x1800118ba  mov     r10, rdx
0x1800118bd  mov     [r11-44h], eax
0x1800118c1  movups  [rsp+0C8h+var_78], xmm0
0x1800118c6  movups  xmmword ptr [r11-40h], xmm0
0x1800118cb  movups  xmmword ptr [r11-30h], xmm0
0x1800118d0  movups  xmmword ptr [r11-20h], xmm0
0x1800118d5  test    rcx, rcx
0x1800118d8  jz      loc_180011C45
0x1800118de  test    rdx, rdx
0x1800118e1  jz      loc_180011C45
0x1800118e7  test    r8, r8
0x1800118ea  jz      loc_180011C45
0x1800118f0  mov     rdx, [rsp+0C8h+arg_20]
0x1800118f8  test    rdx, rdx
0x1800118fb  jz      loc_180011C45
0x180011901  mov     rbx, [rsp+0C8h+arg_30]
0x180011909  test    rbx, rbx
0x18001190c  jz      loc_180011C45
0x180011912  cmp     dword ptr [r10+8], 304h
0x18001191a  jnz     loc_180011AF8
0x180011920  cmp     dword ptr [r10+6Ch], 5
0x180011925  jnz     loc_180011AF8
0x18001192b  lea     eax, [r9-16h]
0x18001192f  cmp     eax, 40EAh
0x180011934  ja      loc_180011C1D
0x18001193a  mov     [r11+18h], rdi
0x18001193e  lea     r11, [r8+5]
0x180011942  mov     edi, [rsp+0C8h+arg_28]
0x180011949  cmp     r11, rdx
0x18001194c  jnz     loc_180011BA7
0x180011952  cmp     byte ptr [r8+1], 0FEh
0x180011957  jz      loc_180011BF5
0x18001195d  movzx   eax, byte ptr [r8+3]
0x180011962  movzx   ecx, byte ptr [r8+4]
0x180011967  shl     ax, 8
0x18001196b  or      ax, cx
0x18001196e  cmp     ax, 10h
0x180011972  jbe     loc_180011A5A
0x180011978  movzx   ecx, ax
0x18001197b  add     ecx, 5
0x18001197e  cmp     ecx, r9d
0x180011981  jnz     loc_180011A5A
0x180011987  sub     ax, 10h
0x18001198b  mov     [rsp+0C8h+arg_8], rsi
0x180011993  movzx   esi, ax
0x180011996  cmp     edi, esi
0x180011998  jb      loc_180011B56
0x18001199e  mov     eax, [r10+38h]
0x1800119a2  lea     rcx, [r8+5]
0x1800119a6  mov     dword ptr [rsp+0C8h+var_78+4], eax
0x1800119aa  lea     r9, [rsp+0C8h+pPaddingInfo]; pPaddingInfo
0x1800119af  mov     rax, [rsp+0C8h+arg_38]
0x1800119b7  add     rcx, rsi
0x1800119ba  mov     [rsp+0C8h+dwFlags], ebp; dwFlags
0x1800119be  bswap   rax
0x1800119c1  xor     rax, [r10+3Ch]
0x1800119c5  mov     qword ptr [rsp+0C8h+var_78+8], rax
0x1800119ca  lea     rax, [rsp+0C8h+arg_0]
0x1800119d2  mov     [rsp+0C8h+pcbResult], rax; pcbResult
0x1800119d7  mov     [rsp+0C8h+cbOutput], edi; cbOutput
0x1800119db  mov     [rsp+0C8h+pbOutput], rdx; pbOutput
0x1800119e0  mov     rdx, r11; pbInput
0x1800119e3  mov     [rsp+0C8h+var_50], r8
0x1800119e8  mov     r8d, esi; cbInput
0x1800119eb  mov     [rsp+0C8h+var_40], rcx
0x1800119f3  mov     rcx, [r10+20h]; hKey
0x1800119f7  mov     [rsp+0C8h+cbIV], ebp; cbIV
0x1800119fb  mov     [rsp+0C8h+pbIV], rbp; pbIV
0x180011a00  mov     [rsp+0C8h+var_48], 5
0x180011a0b  mov     [rsp+0C8h+var_38], 10h
0x180011a16  call    BCryptDecrypt
0x180011a1b  mov     edi, eax
0x180011a1d  test    eax, eax
0x180011a1f  js      loc_180011AA8
0x180011a25  mov     eax, [rsp+0C8h+arg_0]
0x180011a2c  cmp     eax, esi
0x180011a2e  jnz     loc_180011BCD
0x180011a34  mov     [rbx], eax
0x180011a36  mov     eax, edi
0x180011a38  mov     rsi, [rsp+0C8h+arg_8]
0x180011a40  mov     rdi, [rsp+0C8h+arg_10]
0x180011a48  mov     rbx, [rsp+0C8h+arg_18]
0x180011a50  add     rsp, 0C0h
0x180011a57  pop     rbp
0x180011a58  retn
0x180011a5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a61  lea     rax, WPP_GLOBAL_Control
0x180011a68  cmp     rcx, rax
0x180011a6b  jz      short loc_180011AA1
0x180011a6d  mov     edx, [rcx+2Ch]
0x180011a70  test    dl, 1
0x180011a73  jz      short loc_180011AA1
0x180011a75  mov     rcx, [rcx+18h]
0x180011a79  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011a80  mov     dword ptr [rsp+0C8h+pbOutput], 1362h
0x180011a88  lea     r9, aNteBadData; "NTE_BAD_DATA"
0x180011a8f  mov     qword ptr [rsp+0C8h+cbIV], r8
0x180011a94  mov     dword ptr [rsp+0C8h+pbIV], 80090005h
0x180011a9c  call    WPP_SF_sDsd
0x180011aa1  mov     eax, 80090005h
0x180011aa6  jmp     short loc_180011A40
0x180011aa8  mov     rcx, cs:WPP_GLOBAL_Control
0x180011aaf  lea     rax, WPP_GLOBAL_Control
0x180011ab6  cmp     rcx, rax
0x180011ab9  jz      loc_180011A36
0x180011abf  mov     edx, [rcx+2Ch]
0x180011ac2  test    dl, 1
0x180011ac5  jz      loc_180011A36
0x180011acb  mov     rcx, [rcx+18h]
0x180011acf  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011ad6  mov     dword ptr [rsp+0C8h+pbOutput], 1389h
0x180011ade  lea     r9, aStatus; "Status"
0x180011ae5  mov     qword ptr [rsp+0C8h+cbIV], r8
0x180011aea  mov     dword ptr [rsp+0C8h+pbIV], edi
0x180011aee  call    WPP_SF_sDsd
0x180011af3  jmp     loc_180011A36
0x180011af8  mov     rcx, cs:WPP_GLOBAL_Control
0x180011aff  lea     rax, WPP_GLOBAL_Control
0x180011b06  cmp     rcx, rax
0x180011b09  jz      short loc_180011B3F
0x180011b0b  mov     edx, [rcx+2Ch]
0x180011b0e  test    dl, 1
0x180011b11  jz      short loc_180011B3F
0x180011b13  mov     rcx, [rcx+18h]
0x180011b17  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011b1e  mov     dword ptr [rsp+0C8h+pbOutput], 1337h
0x180011b26  lea     r9, aNteNotSupporte; "NTE_NOT_SUPPORTED"
0x180011b2d  mov     qword ptr [rsp+0C8h+cbIV], r8
0x180011b32  mov     dword ptr [rsp+0C8h+pbIV], 80090029h
0x180011b3a  call    WPP_SF_sDsd
0x180011b3f  mov     rbx, [rsp+0C8h+arg_18]
0x180011b47  mov     eax, 80090029h
0x180011b4c  add     rsp, 0C0h
0x180011b53  pop     rbp
0x180011b54  retn
0x180011b56  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b5d  lea     rax, WPP_GLOBAL_Control
0x180011b64  cmp     rcx, rax
0x180011b67  jz      short loc_180011B9D
0x180011b69  mov     edx, [rcx+2Ch]
0x180011b6c  test    dl, 1
0x180011b6f  jz      short loc_180011B9D
0x180011b71  mov     rcx, [rcx+18h]
0x180011b75  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011b7c  mov     dword ptr [rsp+0C8h+pbOutput], 1369h
0x180011b84  lea     r9, aNteBufferTooSm; "NTE_BUFFER_TOO_SMALL"
0x180011b8b  mov     qword ptr [rsp+0C8h+cbIV], r8
0x180011b90  mov     dword ptr [rsp+0C8h+pbIV], 80090028h
0x180011b98  call    WPP_SF_sDsd
0x180011b9d  mov     eax, 80090028h
0x180011ba2  jmp     loc_180011A38
0x180011ba7  cmp     r8, rdx
0x180011baa  ja      loc_1800A5DE6
0x180011bb0  mov     eax, r9d
0x180011bb3  add     rax, r8
0x180011bb6  cmp     rdx, rax
0x180011bb9  jb      loc_1800A5DF3
0x180011bbf  cmp     r8, rdx
0x180011bc2  jb      loc_180011952
0x180011bc8  jmp     loc_1800A5DE6
0x180011bcd  mov     r9d, 138Eh
0x180011bd3  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011bda  lea     rdx, aNteDecryptionF; "NTE_DECRYPTION_FAILURE"
0x180011be1  mov     ecx, 8009002Ch
0x180011be6  call    DebugTraceError
0x180011beb  mov     eax, 8009002Ch
0x180011bf0  jmp     loc_180011A38
0x180011bf5  mov     r9d, 135Ch
0x180011bfb  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011c02  lea     rdx, aNteBadData; "NTE_BAD_DATA"
0x180011c09  mov     ecx, 80090005h
0x180011c0e  call    DebugTraceError
0x180011c13  mov     eax, 80090005h
0x180011c18  jmp     loc_180011A40
0x180011c1d  mov     r9d, 133Fh
0x180011c23  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011c2a  lea     rdx, aNteBadData; "NTE_BAD_DATA"
0x180011c31  mov     ecx, 80090005h
0x180011c36  call    DebugTraceError
0x180011c3b  mov     eax, 80090005h
0x180011c40  jmp     loc_180011A48
0x180011c45  mov     r9d, 1330h
0x180011c4b  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011c52  lea     rdx, aNteInvalidPara; "NTE_INVALID_PARAMETER"
0x180011c59  mov     ecx, 80090027h
0x180011c5e  call    DebugTraceError
0x180011c63  mov     eax, 80090027h
0x180011c68  jmp     loc_180011A48
0x1800a5de6  lea     rax, [rdx+rdi]
0x1800a5dea  cmp     r8, rax
0x1800a5ded  jnb     loc_180011952
0x1800a5df3  mov     r9d, 1348h
0x1800a5df9  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a5e00  lea     rdx, aNteBuffersOver; "NTE_BUFFERS_OVERLAP"
0x1800a5e07  mov     ecx, 8009002Bh
0x1800a5e0c  call    DebugTraceError
0x1800a5e11  mov     eax, 8009002Bh
0x1800a5e16  jmp     loc_180011A40
```
